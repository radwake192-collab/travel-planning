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
| Delta SkyMiles | **~120,000** | TODO | Self. SkyMiles do not expire. |

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
| Delta SkyMiles | 120,000 | ✗ **no path** | **120,000 — hard cap** |
| Southwest Rapid Rewards | 0 | 220,000 | 220,000 |
| United MileagePlus | 0 | 220,000 | 220,000 |
| JetBlue TrueBlue | 0 | 220,000 | 220,000 |
| World of Hyatt | 0 | 220,000 | 220,000 |
| IHG One Rewards | 0 | 220,000 | 220,000 |
| Marriott Bonvoy | 0 | 220,000 | 220,000 |

**The Delta balance is a closed silo.** No credit card currency you hold reaches Delta, so
120K is the ceiling — there is no topping it up mid-booking. Treat those miles as a
fixed, spend-it-on-Delta-or-nothing asset and deploy them where Delta is genuinely the
best carrier, rather than hoarding them.

### Card benefits worth stacking

| Benefit | Card | Notes |
|---|---|---|
| Amex FHR / THC hotel credits | TODO | |
| Chase Edit hotel credits | TODO | |
| Airline incidental / travel credits | TODO | |
| Southwest Companion Pass | TODO | Changes the math a lot if held |
| Lounge access | TODO | |

## Preferences

| Field | Value |
|---|---|
| Cash vs points default | Best of both (change if you prefer one) |
| Currency allocation rule | Delta miles → Delta-strong routes (MSP, DTW, ATL, SLC hubs). Chase UR → everything else, especially Hyatt. See the reasoning in the effective-balance table above. |
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
