---
date_searched: null
origin: CMH
destinations: [MCO]
travel_dates: 2027-01-11 to 2027-01-15   # given by traveler
cabin: economy
scope: flights_only     # lodging and park tickets are already handled
status: planning        # planning | researched | booked | completed | cancelled
booked_option: null
tags: [disney, orlando, family, flights-only]
points_at_search:
  delta_skymiles: 120000
  chase_ultimate_rewards: 220000
  wife_signup_bonus: 100000     # expected Oct-Nov 2026, in time for this booking
---

# Disney — Columbus to Orlando (flights only)

**Route:** CMH → MCO → CMH
**Travel dates:** Depart **Monday, January 11, 2027**, return **Friday, January 15, 2027**.
**Cabin:** Economy
**Travelers:** 5 people — 2 adults, 2 children, 1 lap infant. **4 purchased seats.**
**Status:** Planning — no live pricing pulled yet.

> **Scope: flights only.** Lodging and park tickets are already sorted. Do not search
> hotels, rentals, or ticket pricing for this trip, and do not fold them into the cost
> comparison.

## Why the dates are good

Mid-January — after New Year crowds clear, before Presidents' Day — is one of the cheaper
stretches of the Orlando year, and Monday–Friday avoids weekend fare premiums on both
ends. There's room to optimize rather than rush.

## Currency strategy

Available for this trip: **220K Chase UR**, plus the **~100K signup bonus** expected
Oct–Nov, which lands in time for a Nov–Dec booking. The 120K SkyMiles are likely committed
to Thanksgiving; if that trip ends up going Southwest or portal instead, they're free
here too.

| Door | Currency | Rate | Notes |
|---|---|---|---|
| Southwest | Chase UR 1:1 | 1.2–1.3 cpp | Serves CMH–MCO. Two free checked bags each — meaningful for a park trip with four sets of luggage. Revenue-linked, so no 4-seat space problem. |
| Chase portal | Chase UR direct | 1.25–1.5 cpp fixed | Any airline, no award space needed. Still earns miles as a paid ticket. |
| Delta via Flying Blue / Virgin Atlantic | Chase UR 1:1 | Varies | Only if partner saver space exists at 4 seats. Verify live. |
| Delta SkyMiles | 120K direct | Dynamic | Sees all Delta inventory; often poor value per `data/partner-awards.json`. |

**The honest read: this is probably a cash or near-cash trip.** CMH–MCO in mid-January is
a heavily served leisure route and fares should be low. Chase UR's own floor is 1.7 cpp
per `data/points-valuations.json`, so redeeming UR at the portal's 1.25–1.5 cpp against a
cheap fare destroys value. Price the cash fare first; only reach for points if the fare
comes in unexpectedly high.

## Open questions

1. **The children's ages on January 11, 2027.** Anyone 2 or over needs a purchased seat —
   already assumed at 4 seats. Confirm.
2. **Lap infant's date of birth.** Must be under 2 through **Jan 15**, the return date. A
   second birthday mid-trip means buying a fifth seat for the way home. Most aircraft rows
   permit only one lap infant on oxygen-mask count.
3. **Bags.** Four people's luggage is the single biggest swing between Southwest and the
   ultra-low-cost carriers on this route.

## Search plan

Run every search at **4 seats**.

- **Southwest, by hand via the `southwest` skill.** In no GDS and no API. Serves CMH and
  MCO, and free bags matter here more than on most routes.
- **Cash across the board:** Duffel, Ignav, Skiplagged, Kiwi, Google Flights. Include
  Frontier and Spirit — they serve this leisure market and can be far cheaper, though bag
  and seat fees for a family of five often erase the gap. Compare all-in, not base fare.
- **seats.aero unfiltered at 4 seats**, in case any program shows saver space worth the
  transfer.
- **Chase portal** for the fixed-rate floor.
- **Alternate arrival: SFB** (Orlando Sanford), served by Allegiant, ~45 min further out.
  Worth pricing only if the gap is large — and check whether ground transport is already
  settled given lodging is booked.

## Notes

- Flights are the most commoditized piece of this trip and the least volatile. With
  lodging locked, there's no dependency forcing an early booking — but January fares
  generally don't improve inside 30 days.
- Log actual search results to `trips/logs/` via the `trip-log` skill (gitignored, local).
