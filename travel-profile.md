# Traveler Profile

This file is the standing context for every trip in this repo. The toolkit's skills
(`plan-trip`, `compare-flights`, `trip-calculator`, `gardening`) should read it before
asking basic questions. Keep it current — stale balances produce bad cpp math.

> Fields marked `TODO` are not filled in yet. Anything left as TODO gets asked for at
> search time instead, which is slower but not blocking.

## Home base

| Field | Value |
|---|---|
| Primary airport | **CMH** — John Glenn Columbus International |
| Alternate airports | TODO — e.g. DAY (~70 mi), CVG (~110 mi), CLE (~140 mi), IND (~175 mi) |
| Willing to drive to alternates? | TODO (and how far / how much savings makes it worth it) |
| Home time zone | America/New_York |

## Travelers

| Field | Value |
|---|---|
| Party size (default) | **5 people / 4 seats** |
| Adults | 2 (self + wife) |
| Children | 2 — TODO: ages at time of travel |
| Lap infants | 1 — TODO: date of birth |
| Names as on ID / KTN / Global Entry | TODO (needed only at booking time) |

**Search award space for 4 seats.** This is the single most important constraint in this
file. Availability for 1 or 2 seats says nothing about 4, and on peak holiday dates
4-seat saver space is where most award plans die. Any recommendation that hasn't been
confirmed at 4 seats isn't a recommendation.

### Why the ages matter

Two TODOs above carry real money and need answering before booking:

- **Lap infant's date of birth.** The infant must be under 2 **for every segment,
  including the return**. A second birthday mid-trip means buying a seat for the flight
  home. Domestically, lap infants fly free on Delta, Southwest, and United — but they
  must still be added to the reservation, and most aircraft rows allow only one lap
  infant because of the oxygen-mask count.
- **The two children's ages.** Under 2 flies as a lap infant; 2 and over needs a purchased
  seat at (usually) full fare. For Disney specifically, **under 3 gets into the parks
  free**, ages 3–9 pay child pricing, and 10 and up pays full adult pricing. On a
  multi-day park ticket that gap is worth several hundred dollars.

### What a 4-seat party changes strategically

Programs with fixed award charts and limited saver inventory (partner awards, saver space)
get much harder at 4 seats. Programs with **revenue-linked pricing** — Southwest awards,
Delta dynamic SkyMiles, and the Chase Travel portal — don't have a scarcity problem at
all, only a price problem: if the seats are for sale, you can have them. For a family of
four on peak holiday dates, that reliability is worth more than chasing a thin saver rate.

## Loyalty programs

Fill in the programs you actually hold. Balances drive the cents-per-point math, so
approximate is fine but "unknown" is not useful.

### Airline miles

| Program | Balance | Elite status | Notes |
|---|---|---|---|
| Delta SkyMiles | **100,026** | TODO | Corrected from ~120K — figure read off delta.com 2026-08-07. SkyMiles do not expire. |

### Hotel points

| Program | Balance | Elite status | Notes |
|---|---|---|---|
| None held directly | 0 | — | Hyatt/IHG/Marriott are reachable via Chase transfer |

### Transferable currencies

These are the flexible points that decide which airline programs are actually reachable.
Cross-reference with the `transfer-partners` and `transfer-bonuses` skills.

| Currency | Balance | Cards held |
|---|---|---|
| Chase Ultimate Rewards | **~220,000** | TODO — which Chase card(s)? Determines portal rate |
| Amex Membership Rewards | 0 | — |
| Capital One miles | 0 | — |
| Citi ThankYou | 0 | — |
| Bilt | 0 | — |

**Wife's signup bonus: ~100,000 points, expected in a few months (roughly Oct–Nov 2026).**
TODO — *which card / which currency?* This is the highest-value unknown in this file:

- If **Chase**, it pools with the existing 220K (Chase permits point transfers between
  household members), giving ~320K UR.
- If **Amex**, it is a completely different and strategically valuable asset, because
  **Amex MR is the only card currency that transfers to Delta.** That would be the one
  way to top up the Delta balance, which currently cannot be topped up at all.

Do not plan any booking around these points until they actually post. Signup bonuses
require meeting minimum spend first and typically land ~3 months after approval.

### Effective balances (direct + reachable via transfer)

Verified against `data/transfer-partners.json` (updated 2026-07-12). The Chase-derived
figures all draw on the **same** 220K pool — spending it in one program spends it in all.

| Program | Direct | Via Chase UR (1:1) | Effective |
|---|---|---|---|
| Delta SkyMiles (the *currency*) | 120,000 | ✗ no path | 120,000 |
| Air France-KLM Flying Blue | 0 | 220,000 | 220,000 |
| Virgin Atlantic Flying Club | 0 | 220,000 | 220,000 |
| Southwest Rapid Rewards | 0 | 220,000 | 220,000 |
| United MileagePlus | 0 | 220,000 | 220,000 |
| JetBlue TrueBlue | 0 | 220,000 | 220,000 |
| World of Hyatt | 0 | 220,000 | 220,000 |
| IHG One Rewards | 0 | 220,000 | 220,000 |
| Marriott Bonvoy | 0 | 220,000 | 220,000 |

### Delta access: four doors, not one

**Do not confuse the SkyMiles balance with access to Delta flights.** The SkyMiles
*currency* is capped at 120K and only Amex MR can add to it. But **Delta-operated seats
are reachable four different ways**, three of them funded by Chase:

| Door | Currency | Inventory it can see | Pricing |
|---|---|---|---|
| Delta SkyMiles direct | 120K SkyMiles | **All Delta seats** — no capacity control | Dynamic, often poor value |
| Flying Blue | Chase UR 1:1 | Delta *partner saver* space only | Dynamic + monthly Promo Rewards |
| Virgin Atlantic Flying Club | Chase UR 1:1 | Delta *partner saver* space only | Chart-based per repo data — verify |
| Chase Travel portal | Chase UR direct | Any purchasable seat — no award space needed | Fixed 1.25–1.5 cpp |

Both Flying Blue and Virgin Atlantic are full SkyTeam members that book Delta online.
`data/partner-awards.json` says it plainly in the Delta entry: *"Often poor value for
SkyMiles redemptions. Better to use Flying Blue or Korean Air SKYPASS to book
Delta/SkyTeam flights,"* and in the Flying Blue entry: *"Great for Delta metal (often
cheaper than SkyMiles)."* Korean Air SKYPASS is not reachable from Chase, so Flying Blue
and Virgin Atlantic are the two partner doors available here.

**The real tradeoff is inventory, not price.** SkyMiles can book any Delta seat at a bad
rate. The partner programs get a much better rate but can only touch the saver space Delta
chooses to release, which is thin — and thinnest exactly when a party needs 4 seats on
peak dates. The portal sidesteps award space entirely at a guaranteed fixed rate.

Search order for any Delta route: **seats.aero first** (it covers Flying Blue and Virgin
Atlantic and answers the partner-space question in one query), then Delta direct for the
dynamic price, then the portal as the floor.

> ⚠️ `data/partner-awards.json` was last updated 2026-03-31 and is past its 90-day TTL.
> Virgin Atlantic in particular is listed as a fixed chart; verify current Delta pricing
> live before committing to a transfer, since transfers are irreversible.

### Card benefits worth stacking

| Benefit | Card | Notes |
|---|---|---|
| Amex FHR / THC hotel credits | TODO | |
| Chase Edit hotel credits | TODO | |
| Airline incidental / travel credits | TODO | |
| **Delta SkyMiles Amex card** | Confirmed held | Observed on a delta.com award booking 2026-08-07 — "Card Member Savings" and "TakeOff 15" both applied |
| **TakeOff 15** — 15% off Delta award tickets | Delta SkyMiles Amex | Applies automatically. Verified live: 105,600 → 89,600 miles on a 4-passenger award. |
| **First checked bag free**, cardholder + up to 8 companions on the same reservation | Delta SkyMiles Amex | Confirm the exact companion count for your card tier. Materially narrows Southwest's free-bag advantage. |
| Southwest Companion Pass | TODO | Changes the math a lot if held |
| Lounge access | TODO | |

## Preferences

| Field | Value |
|---|---|
| Cash vs points default | Best of both (change if you prefer one) |
| Currency allocation rule | Chase UR is the workhorse and reaches Delta metal three ways (Flying Blue, Virgin Atlantic, portal). SkyMiles are the narrow asset — spend them when Delta's own dynamic price beats every Chase-funded door. See the four-doors table above. |
| Cabin default (domestic) | Economy |
| Cabin default (long-haul) | TODO |
| Nonstop preference | TODO — strong / prefer / don't care |
| Bag situation | TODO — carry-on only, or checked bags (changes airline cost comparisons) |
| Seat preference | TODO |
| Red-eyes / early departures | TODO — acceptable or avoid |
| Refundability | TODO — how much premium is worth paying for flexibility |
| Risk tolerance on tight connections | TODO |

## Standing rules

- Never transfer points speculatively. Confirm award space first — see the `award-holds`
  and `booking-guidance` skills for which programs allow holds.
- Always search for the full party size. Award space for 1 seat does not mean space for N.
- Show cents-per-point on every award option and compare against the floors in
  `points-valuations`.
