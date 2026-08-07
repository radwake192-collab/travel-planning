---
date_searched: null
origin: CMH
destinations: [MCO]
travel_dates: 2027-01-11 to 2027-01-15   # given by traveler
cabin: economy
status: planning        # planning | researched | booked | completed | cancelled
booked_option: null
tags: [disney, orlando, family, theme-park]
points_at_search:
  delta_skymiles: 120000        # likely committed to the Thanksgiving trip
  chase_ultimate_rewards: 220000
  wife_signup_bonus: 100000     # expected Oct-Nov 2026, should be available for this trip
---

# Disney — Columbus to Orlando

**Route:** CMH → MCO → CMH
**Travel dates:** Depart **Monday, January 11, 2027**, return **Friday, January 15, 2027**.
**Nights:** 4
**Cabin:** Economy
**Travelers:** 2 adults
**Status:** Planning — currency strategy set, no live pricing pulled yet.

## Currency strategy — this is the Chase UR trip

Delta miles are earmarked for Thanksgiving (see that brief — Chase cannot reach Delta, so
those 120K miles have no other outlet). That leaves **220K Chase UR, plus the ~100K signup
bonus that should post around Oct–Nov**, for this trip. Timing works: booking happens
Nov–Dec for January travel.

The highest-value use of UR here is almost certainly **the hotel, not the flights**:

| Use of Chase UR | Rate | Verdict |
|---|---|---|
| Transfer to **World of Hyatt** 1:1 | 1.4–1.7 cpp | **Best available.** Most valuable hotel currency across all four valuation sources. |
| Chase Travel portal (cash fare) | 1.25–1.5 cpp fixed | Solid floor. Still earns airline miles since it's a paid ticket. |
| Transfer to **Southwest** 1:1 | 1.2–1.3 cpp | Fine, and bags fly free — worth it for a park trip with luggage. |
| Transfer to **Marriott Bonvoy** 1:1 | 0.6–0.7 cpp | **Avoid.** Roughly half the value of Hyatt. |

That Marriott line corrects something worth flagging: the Swan, Dolphin, and Swan Reserve
are a genuinely good Disney-adjacent option, but **on cash, for the on-property perks —
not on Bonvoy points.** At 0.6–0.7 cpp, paying with Bonvoy is one of the weaker
redemptions in the whole toolkit.

Burning UR on a cheap CMH–MCO economy fare is the classic low-value move. Price the
flights in cash first and reserve the points for lodging unless the fares come in high.

---

## Why the dates are good

Mid-January, after the New Year crowds clear and before Presidents' Day, is one of the
cheaper and quieter stretches of the Disney World year. A Monday–Friday trip also avoids
weekend fare premiums on both ends. This one has room to be optimized rather than rushed.

## Open questions

1. **Party size and ages.** Disney ticket pricing and hotel occupancy limits both turn on
   this, and child fares matter on the flights.
2. **Where are you staying?** Disney-owned resort vs off-property changes everything
   downstream — transport, park-access perks, and whether hotel points are usable at all.
   Disney resorts do not participate in hotel loyalty programs; the nearby Swan, Dolphin,
   and Swan Reserve are Marriott properties and *do* take Bonvoy points while keeping
   most on-property benefits.
3. **Park days and ticket type.** Number of days, park hopper or not, Genie+/Lightning
   Lane. Buy tickets before pricing hotels — ticket cost usually dwarfs the fare
   difference between carriers.
4. **Rental car or not.** Off-property almost always means a car. On-property usually
   doesn't.

## Search plan

- **Flights:** CMH→MCO is a heavily served leisure route. Check Southwest by hand via the
  `southwest` skill (bags fly free matters a lot for a Disney trip), plus Frontier and
  Spirit if the ultra-low-cost tradeoffs are acceptable, alongside the mainline carriers
  through Duffel/Ignav and the free Skiplagged and Kiwi MCP servers.
- **Alternate arrival airport:** **SFB** (Orlando Sanford) is served by Allegiant and sits
  about 45 minutes further from the parks. Worth pricing only if the gap is large and a
  car is already in the plan.
- **Hotels:** run `compare-hotels`. For Orlando specifically, check the `ticketsatwork`
  skill — corporate-perks pricing frequently beats portals by 10–30% on both Orlando
  hotels and theme park tickets, which is exactly this trip's cost profile.
- **Points:** run `trip-calculator` on the flights *and* the hotel together. On a
  short domestic leisure trip the hotel is usually the better points redemption; burning
  miles on a cheap CMH–MCO economy fare is often a poor cents-per-point outcome.

## Notes

- Ticket purchase and hotel booking generally lock in before flights here, since the
  flights are the most commoditized and least volatile piece.
- Log actual search results to `trips/logs/` via the `trip-log` skill (gitignored, local).
