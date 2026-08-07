---
date_searched: null
origin: CMH
destinations: [MSP]
travel_dates: 2026-11-24 to 2026-11-30   # confirmed by traveler
cabin: economy
status: planning        # planning | researched | booked | completed | cancelled
booked_option: null
tags: [thanksgiving, domestic, holiday-peak]
points_at_search:
  delta_skymiles: 120000
  chase_ultimate_rewards: 220000
---

# Thanksgiving — Columbus to Minneapolis

**Route:** CMH → MSP → CMH
**Travel dates:** Out **Tuesday, November 24, 2026**, back **Monday, November 30, 2026**.
Thanksgiving Day is Thu Nov 26. Six nights.
**Cabin:** Economy
**Travelers:** 2 adults
**Status:** Planning — strategy set, no live pricing pulled yet.

---

## The dates are the good ones

Tue-out / Mon-back deliberately straddles the two worst days to fly in the American year:
the Wednesday before Thanksgiving and the Sunday after. That pairing is typically well
cheaper than Wed/Sun on both cash and award pricing, and it is the single largest lever on
this trip. Nothing below is worth more than having picked these days.

## Currency strategy — settled

**Use Delta miles for this trip. Preserve Chase UR for Orlando.**

The reasoning, verified against `data/transfer-partners.json` (updated 2026-07-12):

1. **Chase UR cannot transfer to Delta.** Chase's airline partners are Aer Lingus,
   Aeroplan, Flying Blue, British Airways, Iberia, JetBlue, Singapore, Southwest, United,
   and Virgin Atlantic. Delta is not among them, and among all major card currencies only
   Amex MR reaches Delta. So the 120K Delta balance has a hard ceiling and **cannot be
   topped up** mid-booking.
2. **MSP is a Delta fortress hub** and Delta flies CMH–MSP nonstop. This route is close to
   the ideal use case for a trapped Delta balance — an airline-strong market where Delta
   should have both the best schedule and the deepest award inventory.
3. **Chase UR is the flexible asset** and is worth more elsewhere: it reaches Hyatt at
   1.4–1.7 cpp, which is the strongest redemption available on the Orlando trip.

Spending Delta here and UR there uses each currency where it is strongest. The reverse —
burning UR on Southwest for this trip while 120K Delta miles sit idle — wastes the
flexible currency and strands the inflexible one.

## Do not count on the 100K signup bonus

The wife's ~100K bonus is expected "in a few months," which realistically means Oct–Nov
after minimum spend clears. This trip needs booking **now**, in August. Plan and book it
on the 120K Delta / 220K UR that exist today. The 100K is a Disney-trip asset.

## Open questions

1. **Which card is the 100K signup bonus on?** If Amex, that is the only route to more
   Delta miles and changes the long-run picture considerably. Doesn't affect this booking.
2. **Which Chase card(s)?** Sapphire Reserve vs Preferred sets the Chase Travel portal
   rate (1.5 vs 1.25 cpp), which is the fallback if award space is bad.
3. **Bags.** Two checked bags each on Southwest is free; on Delta it's roughly $70 per
   person round trip. Changes the all-in comparison.

## Search plan

- **Delta award, first and most important.** Price CMH–MSP for **2 seats**, Nov 24 and
  Nov 30. SkyMiles is dynamically priced with no award chart, so the number could be
  anywhere from reasonable to absurd; peak holiday domestic commonly lands 25K–60K each
  way per person. At 2 travelers × round trip, 120K covers a moderate price and does not
  cover a bad one. Check ±1 day on both ends — Delta's dynamic pricing varies sharply
  day to day.
- **Delta cash, for the cpp denominator.** An award is only good relative to the cash
  price. Delta SkyMiles floor is 1.0 cpp and ceiling 1.25 cpp per
  `data/points-valuations.json`; below ~1.0 cpp, pay cash and keep the miles.
- **Southwest, by hand via the `southwest` skill.** Serves both CMH and MSP, appears in no
  GDS and no API, and is the fallback if Delta award pricing is bad. Southwest awards are
  pegged to cash fare at roughly 1.2–1.3 cpp, are fully refundable to points on cancel,
  and include two free checked bags each.
- **Cash across the board:** Duffel, Ignav, Skiplagged, Kiwi, Google Flights.
- **Chase Travel portal** as the last resort — fixed 1.25–1.5 cpp on the cash fare,
  which reliably beats a bad Delta award redemption and still earns Delta miles on a
  paid ticket.
- **No transfer bonus is relevant.** The only active Chase bonus is 70% to IHG, which
  Frequent Miler explicitly says to skip, and it's a hotel program with no bearing here.

## Decision rule

Compute cpp on the Delta award against the all-in cash price including bags. Above
~1.2 cpp, book the Delta award and the trapped miles have done their job. Between 1.0 and
1.2, it's close — lean award anyway, because these miles have no alternative use. Below
1.0 cpp, pay cash or use the Chase portal and keep the SkyMiles for a Delta-strong route
later.

## Timing

It is **August 2026**, roughly 3.5 months out. For a peak domestic holiday this is
already the back half of the good booking window — holiday fares and saver award space
both tend to deteriorate from here. Treat this trip as the higher-priority of the two.

## Search plan

Run via `plan-trip` or `compare-flights` once the profile has party size and balances:

- **Cash, in parallel:** Duffel and Ignav (need API keys), plus the free Skiplagged and
  Kiwi MCP servers, plus Google Flights.
- **Southwest separately.** Southwest is in no GDS and no API — it needs the dedicated
  `southwest` skill. It serves both CMH and MSP, so it must be checked by hand; a
  comparison that omits it is incomplete. If a Companion Pass is in play, that likely
  decides the trip on its own.
- **Award:** seats.aero across *all* programs, not filtered to one upfront. MSP is a
  Delta fortress hub, so expect Delta-heavy inventory and dynamic (not saver) pricing;
  check partner options and nearby-airport alternates before accepting a bad rate.
- **Cross-reference** transfer partners and any live transfer bonuses before moving
  points anywhere.

## Alternate airports

| Airport | Distance from MSP | Worth checking? |
|---|---|---|
| MSP | — | Primary |
| Origin alternates: DAY, CVG, CLE, IND | 70–175 mi from Columbus | Only if savings are large enough to justify the drive on a holiday weekend |

## Notes

- Holiday-peak pricing means the usual "wait for a fare drop" advice is inverted. Book
  when the number is acceptable, then let the `gardening` skill watch for drops — most
  US carriers will issue a travel credit if the fare falls after booking.
- Log the actual search results to `trips/logs/` via the `trip-log` skill (that
  directory is gitignored and stays local).
