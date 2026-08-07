---
date_searched: null
origin: CMH
destinations: [MSP]
travel_dates: 2026-11-24 to 2026-11-30   # confirmed by traveler
cabin: economy
status: planning        # planning | researched | booked | completed | cancelled
booked_option: null
scope: flights_only     # lodging is already handled
tags: [thanksgiving, domestic, holiday-peak, flights-only]
points_at_search:
  delta_skymiles: 120000
  chase_ultimate_rewards: 220000
---

# Thanksgiving — Columbus to Minneapolis (flights only)

**Route:** CMH → MSP → CMH
**Travel dates:** Out **Tuesday, November 24, 2026**, back **Monday, November 30, 2026**.
Thanksgiving Day is Thu Nov 26. Six nights.
**Cabin:** Economy
**Travelers:** 5 people — 2 adults, 2 children, 1 lap infant. **4 purchased seats.**
**Status:** Planning — strategy set, no live pricing pulled yet.

> **Scope: flights only.** Lodging is already sorted. Do not search hotels for this trip.

---

## The dates are the good ones

Tue-out / Mon-back deliberately straddles the two worst days to fly in the American year:
the Wednesday before Thanksgiving and the Sunday after. That pairing is typically well
cheaper than Wed/Sun on both cash and award pricing, and it is the single largest lever on
this trip. Nothing below is worth more than having picked these days.

## Currency strategy — four doors to Delta

Two corrections to an earlier version of this brief, both material.

**Correction 1: Chase reaches Delta metal.** Chase cannot mint SkyMiles — only Amex MR
does that — but Delta-operated seats are bookable with Chase points three separate ways:
**Flying Blue** (1:1), **Virgin Atlantic Flying Club** (1:1), and the **Chase Travel
portal** at a fixed rate. Both partner programs are full SkyTeam members that book Delta
online. `data/partner-awards.json` is explicit: Delta's own entry says *"Often poor value
for SkyMiles redemptions. Better to use Flying Blue or Korean Air SKYPASS,"* and Flying
Blue's says *"Great for Delta metal (often cheaper than SkyMiles)."* (Korean Air SKYPASS
is not a Chase partner, so it's out of reach here.)

**Correction 2: the constraint is inventory, not currency.** The question was never
"can Chase pay for Delta." It's *which door can seat four people on peak Thanksgiving
dates*:

| Door | Currency | Inventory visible | 4 seats on Nov 24/30? |
|---|---|---|---|
| Chase portal | 220K UR @ 1.25–1.5 cpp | Any seat that's for sale | **Yes — guaranteed** |
| Southwest | 220K UR → 1:1 | Any seat that's for sale | **Yes — guaranteed** |
| Delta SkyMiles | 120K, no top-up | All Delta seats, no capacity control | Yes, but 120K likely covers only 1–2 of 4 |
| Flying Blue | 220K UR → 1:1 | Delta **partner saver** space only | Unlikely, but the best value if it exists |
| Virgin Atlantic | 220K UR → 1:1 | Delta **partner saver** space only | Unlikely, but the best value if it exists |

Delta releases only a slice of its inventory to partners as saver award space. That slice
is thinnest on peak holiday dates, and needing **four** of it is the hard part. So Flying
Blue and Virgin Atlantic are genuinely the highest-value options *and* the least likely to
come through at this party size. That makes them cheap to check and wrong to count on.

### Run this first (nothing below has been checked live)

No award search has been run for this trip. The planning container had no
`SEATS_AERO_API_KEY` and its network policy blocked seats.aero, delta.com, and
southwest.com outright, so every number in this brief is derived from
`data/*.json` reference files — **not one is a live price or a confirmed seat.**

From a local shell with the key set, this is the query that settles the partner-saver
question. `flyingblue` and `virginatlantic` are the two Chase-reachable SkyTeam doors:

```bash
curl -s -H "Partner-Authorization: $SEATS_AERO_API_KEY" \
  "https://seats.aero/partnerapi/search?origin_airport=CMH&destination_airport=MSP&start_date=2026-11-23&end_date=2026-12-01&cabins=economy&order_by=lowest_mileage&include_trips=true&minify_trips=true" | jq '.'
```

Deliberately unfiltered by `sources` — pull every program first, then narrow. Filtering to
one program upfront is the documented way to miss the good result. Widening the dates to
Nov 23–Dec 1 catches the ±1 day on each end.

Then check `RemainingSeats` on anything promising: **you need 4**, and the cached
availability object reports the *maximum* across grouped flights, so confirm the specific
flight has four before counting on it. Check `ComputedLastSeen` for staleness, and verify
on the airline's own site before transferring — Seats.aero data is cached, and phantom
availability is common.

### Plan

1. **Run seats.aero first, at 4 seats.** One query covers both Flying Blue and Virgin
   Atlantic and settles whether Delta partner saver space exists on Nov 24 / Nov 30. If
   four seats show up, that is very likely the best value on the table — take it. Verify
   live on the airline site before transferring, since transfers are irreversible.
2. **Price Delta direct** for the dynamic SkyMiles number at 4 seats. 120K covers
   roughly 30K per person round trip; peak holiday domestic often exceeds that. Consider
   2-on-miles / 2-on-cash if it's close.
3. **Southwest via the `southwest` skill.** Revenue-linked awards, so no saver-space
   problem, plus two free checked bags per person — about $280 round trip for four people
   against Delta.
4. **Chase portal** as the guaranteed floor: fixed 1.25–1.5 cpp on any airline including
   Delta, no award space required, and it still earns miles as a paid ticket.

The realistic expectation is that option 1 fails on availability and the decision lands
between Southwest and the portal — but option 1 costs one search and has the highest
upside, so it goes first.

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

Every search must be run at **4 seats**. A price quoted at 1 or 2 seats is not usable
here, and per-seat prices commonly rise as cheap fare buckets sell out.

- **seats.aero across all programs, unfiltered, 4 seats.** Runs first. Covers Flying Blue
  and Virgin Atlantic in one query and answers the Delta partner-saver question directly.
  Do not pre-filter to one program.
- **Delta direct** for the dynamic SkyMiles price at 4 seats, Nov 24 / Nov 30, ±1 day each
  end — dynamic pricing moves sharply day to day.
- **Southwest, by hand via the `southwest` skill.** In no GDS and no API, so nothing else
  surfaces it. Price 4 seats in both cash and Rapid Rewards, and confirm the schedule is
  open that far out.
- **Cash across the board:** Duffel, Ignav, Skiplagged, Kiwi, Google Flights.
- **Chase Travel portal** at whichever rate the card earns.
- **No transfer bonus is relevant.** The only active Chase bonus is 70% to IHG, which
  Frequent Miler explicitly says to skip, and it's a hotel program with no bearing here.

## Decision rule

Compare all-in totals for 4 seats **including checked bags**, and compute cpp on every
points option against the cash fare:

| Option | Currency | Capacity of the balance | Availability risk |
|---|---|---|---|
| Flying Blue / Virgin Atlantic | 220K UR 1:1 | Best value if space exists | **High** — partner saver only |
| Southwest award | 220K UR 1:1 | ~$2,860 of fare at 1.3 cpp | None |
| Chase portal | 220K UR direct | $2,750–$3,300 at 1.25–1.5 cpp | None |
| Delta award | 120K SkyMiles | ~1–2 of the 4 tickets | None, but price is dynamic |
| Cash | — | — | None |

Take the lowest real out-of-pocket cost for four seats plus bags. Chase UR's own floor is
1.7 cpp per `data/points-valuations.json`, so any UR redemption below that is spending a
premium currency at a discount — the portal at 1.25–1.5 cpp is a *floor*, not a win.
That's the argument for checking Flying Blue and Virgin Atlantic first: they're the only
doors that plausibly clear UR's floor on this route.

**Before any transfer:** confirm the exact award is bookable and priced on the partner's
own site. Transfers are irreversible, and neither Flying Blue nor Virgin Atlantic reliably
offers a hold — load the `award-holds` skill before moving points.

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
