---
date_searched: null
origin: CMH
destinations: [MSP]
travel_dates: 2026-11-25 to 2026-11-29   # ASSUMED — confirm exact days
cabin: economy
status: planning        # planning | researched | booked | completed | cancelled
booked_option: null
tags: [thanksgiving, domestic, holiday-peak, family]
points_at_search: {}    # fill from travel-profile.md at search time
---

# Thanksgiving — Columbus to Minneapolis

**Route:** CMH → MSP → CMH
**Travel window:** Thanksgiving 2026. Thanksgiving Day is **Thursday, November 26, 2026**.
**Cabin:** Economy
**Travelers:** TODO (see `travel-profile.md`)
**Status:** Planning — nothing searched or booked yet.

---

## Open questions

These need answers before a real search. Everything else can be inferred.

1. **Exact dates.** The assumed window is out **Wed Nov 25**, back **Sun Nov 29** — the
   single most expensive pairing of the year. Alternatives worth pricing:
   - Out **Tue Nov 24** instead of Wed — usually materially cheaper.
   - Back **Mon Nov 30** instead of Sun — Sunday after Thanksgiving is the peak
     domestic travel day in the US.
   - Out Thanksgiving morning itself (Thu Nov 26) — often the cheapest departure of
     the week if the schedule works.
2. **Party size.** Award space for one seat does not mean space for four.
3. **Bags.** Changes which carrier is actually cheapest all-in.
4. **Driving as a fallback.** CMH→MSP is roughly 700 miles / ~11 hours. Not a serious
   substitute for most parties, but it caps what the flights are worth.

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
