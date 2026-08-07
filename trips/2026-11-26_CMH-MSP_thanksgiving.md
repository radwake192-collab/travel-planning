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
**Travelers:** 5 people — 2 adults, 2 children, 1 lap infant. **4 purchased seats.**
**Status:** Planning — strategy set, no live pricing pulled yet.

---

## The dates are the good ones

Tue-out / Mon-back deliberately straddles the two worst days to fly in the American year:
the Wednesday before Thanksgiving and the Sunday after. That pairing is typically well
cheaper than Wed/Sun on both cash and award pricing, and it is the single largest lever on
this trip. Nothing below is worth more than having picked these days.

## Currency strategy — revised for 4 seats

At two travelers this was cleanly "spend the Delta miles." At **four seats it no longer
is**, and the arithmetic is the reason:

> 120,000 Delta miles ÷ 4 passengers = **30,000 per person round trip**, i.e. 15,000 each
> way. Peak Thanksgiving domestic on dynamically-priced SkyMiles commonly runs 20K–40K+
> each way per person. The realistic outcome is that **120K covers one to two of the four
> tickets, not all four.**

Chase UR cannot cover the gap — verified against `data/transfer-partners.json` (updated
2026-07-12), Chase's airline partners are Aer Lingus, Aeroplan, Flying Blue, British
Airways, Iberia, JetBlue, Singapore, Southwest, United, and Virgin Atlantic. **Delta is
not among them**, and among major card currencies only Amex MR reaches Delta. So the
Delta balance is capped at 120K with no way to top it up mid-booking.

### The revised plan, in priority order

1. **Southwest via Chase UR — most likely winner.** Serves both CMH and MSP. Award pricing
   is pegged to the cash fare at roughly 1.2–1.3 cpp, so there is **no 4-seat saver-space
   problem** — if the seats are for sale you can buy them with points. Two free checked
   bags per person is worth roughly $280 round trip against Delta for a family of four,
   and awards are fully refundable to points if plans change. 220K UR at ~1.3 cpp is
   about $2,860 of Southwest fare, which should comfortably cover four holiday tickets.
2. **Chase Travel portal.** Fixed 1.25 cpp (Preferred) or 1.5 cpp (Reserve) against any
   airline's cash fare, including Delta. 220K UR is $2,750–$3,300 of travel. This is the
   reliable floor and it still earns airline miles, since a portal booking is a paid
   ticket.
3. **Delta miles as a partial play.** Price the Delta award at 4 seats anyway. If it
   comes in cheap enough that 120K covers all four round trips at 1.2 cpp or better, take
   it. Otherwise consider putting 2 travelers on miles and 2 on cash — Delta lets you book
   separate reservations on the same flights, though you should confirm seat assignments
   together afterward so the family isn't split across the cabin.
4. **Cash**, if it simply beats all of the above on the Tue/Mon dates.

The Delta balance keeps its long-run logic — MSP is a Delta fortress hub with a CMH
nonstop, and those miles have no other outlet — but "spend them here" only holds if the
award price at 4 seats is actually reasonable. Don't force it.

## Do not count on the 100K signup bonus

The wife's ~100K bonus is expected "in a few months," which realistically means Oct–Nov
after minimum spend clears. This trip needs booking **now**, in August. Plan and book it
on the 120K Delta / 220K UR that exist today. The 100K is a Disney-trip asset.

## Open questions

1. **Lap infant's date of birth.** Must be under 2 through **Nov 30**, the return date.
   A birthday during the trip means buying a fourth... fifth seat for the way home.
2. **The two children's ages.** Anyone 2 or over needs their own purchased seat, which is
   already assumed here (4 seats). Confirm neither child is young enough to fly as a
   second lap infant — and note that most rows permit only one lap infant, so a second
   would need to sit in a different row regardless.
3. **Which Chase card(s)?** Sapphire Reserve vs Preferred sets the portal rate at 1.5 vs
   1.25 cpp. Across 220K points that's a $550 swing, and it decides how competitive
   option 2 is.
4. **Which card is the 100K signup bonus on?** If Amex, that is the only route to more
   Delta miles that exists. Won't post in time to affect this booking.
5. **Bags.** Four people checking bags is roughly $280 round trip on Delta and $0 on
   Southwest. That difference alone is a meaningful share of the fare gap.

## Timing

It is **August 2026**, roughly 3.5 months out. For a peak domestic holiday this is already
the back half of the good booking window — holiday fares deteriorate from here. This is
the higher-priority of the two trips.

## Search plan

Every search below must be run at **4 seats**. A price quoted at 1 or 2 seats is not
usable here, and per-seat prices commonly rise as the cheap fare buckets sell out.

- **Southwest, by hand via the `southwest` skill.** Now the lead candidate, not the
  fallback. Southwest is in no GDS and no API, so nothing else will surface it. Price 4
  seats CMH–MSP on Nov 24 / Nov 30 in both cash and Rapid Rewards, and confirm Southwest's
  schedule is open that far out.
- **Delta award at 4 seats,** Nov 24 and Nov 30, ±1 day each end — dynamic pricing moves
  sharply day to day. Also price the 2-on-miles / 2-on-cash split.
- **Delta cash, for the cpp denominator.** An award is only good relative to cash. Delta's
  floor is 1.0 cpp and ceiling 1.25 cpp per `data/points-valuations.json`.
- **Cash across the board:** Duffel, Ignav, Skiplagged, Kiwi, Google Flights.
- **Chase Travel portal** at whichever rate the card earns, as the reliable floor.
- **seats.aero across all programs,** unfiltered, in case a partner rate beats Delta's own
  dynamic price. Expect thin 4-seat saver space on peak holiday dates.
- **No transfer bonus is relevant.** The only active Chase bonus is 70% to IHG, which
  Frequent Miler explicitly says to skip, and it's a hotel program with no bearing here.

## Decision rule

Compare four all-in totals for 4 seats, **including checked bags**:

| Option | Currency | Rough capacity of the balance |
|---|---|---|
| Southwest award | Chase UR → Southwest 1:1 | ~$2,860 of fare at 1.3 cpp |
| Chase portal | Chase UR direct | $2,750–$3,300 at 1.25–1.5 cpp |
| Delta award | Delta SkyMiles | 120K — likely 1–2 tickets, not 4 |
| Cash | — | — |

Take the lowest real out-of-pocket cost for four seats plus bags. If Delta's 4-seat award
price clears 1.2 cpp, use the miles and it's a clean outcome. If it doesn't, Southwest or
the portal wins and the Delta balance waits for a better Delta-strong route — that's a
fine result, not a failure.

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
