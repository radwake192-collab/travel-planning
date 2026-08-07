# Setup

This repo is a copy of [borski/travel-hacking-toolkit](https://github.com/borski/travel-hacking-toolkit)
plus a personal layer (`travel-profile.md` and `trips/`). Upstream is wired as a git
remote named `upstream`, so the toolkit can be refreshed later without losing that layer.

## 1. Clone it on the machine you'll actually use

The toolkit's live searches need API keys in your shell environment and browser
automation via Docker, so it wants to run on your own machine, not in a throwaway cloud
session.

```bash
git clone https://github.com/radwake192-collab/travel-planning.git
cd travel-planning
```

## 2. Add API keys

**Run this in your terminal, not in a chat window.** The script prompts for each key with
masked input and writes the exports to your shell rc with a backup. Keys pasted into a
chat end up in terminal scrollback, session logs, and API logs — this path avoids all
three.

```bash
bash scripts/setup-keys.sh
```

Then `source ~/.zshrc` (or `~/.bashrc`) or open a new terminal.

Nothing here is required to start. Five MCP servers — Skiplagged, Kiwi, Trivago,
Ferryhopper, Airbnb — need no keys at all, which already covers cash flight and hotel
search. The keys that matter most, in order:

| Key | Unlocks | Cost |
|---|---|---|
| `SEATS_AERO_API_KEY` | Award search across 27 mileage programs. The main event. | ~$8/mo |
| `DUFFEL_API_KEY_LIVE` | Real GDS cash fares | Free to search |
| `IGNAV_API_KEY` | Backup cash fares | 1,000 free req/mo |
| `AWARDWALLET_API_KEY` + `AWARDWALLET_USER_ID` | Auto-pull your balances | Business account |

For the two trips already in `trips/`, both domestic and both likely to come out cash-first,
the free servers plus the `southwest` skill get you most of the way. Seats.aero is worth it
if you're carrying a meaningful transferable-points balance.

## 3. Launch

From inside the repo:

```bash
claude --plugin-dir .
```

That loads the 40+ skills, the MCP servers, and the `travel-hacker` subagent straight from
this working tree — no plugin install, and any edits you make here take effect immediately.

If you'd rather have the toolkit available from any directory, install it as a plugin
instead:

```
/plugin marketplace add borski/travel-hacking-toolkit
/plugin install travel-hacker@borski
```

Note that the plugin install pulls upstream's copy, so it won't see `travel-profile.md` or
`trips/` unless you launch from inside this repo. Running `claude --plugin-dir .` here is
the setup that actually uses your profile.

## 4. Fill in your profile

Open `travel-profile.md` and replace the `TODO` fields. Party size, the cards you hold, and
rough points balances are the three that change recommendations the most — without them
every search stops to ask. Everything else can stay TODO.

## 5. Verify

```
/travel-hacker:getting-started
```

Reports which keys are live and gives sample prompts scaled to what you have configured.

## Docker (optional)

Five skills — Southwest, American Airlines, Chase Travel, Amex Travel, TicketsAtWork —
drive real websites in a browser because those sites have no public API. They auto-pull
their images on first use and need Docker running. **Southwest matters for both trips
already planned**, since it serves CMH, MSP, and MCO and appears in no other search source.

## Keeping the toolkit current

```bash
git fetch upstream
git merge upstream/main
```

Your personal files (`travel-profile.md`, `trips/`, `SETUP.md`) are additive, so upstream
changes should merge cleanly.
