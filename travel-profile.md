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
| Party size (default) | TODO |
| Adults | TODO |
| Children + ages at travel | TODO |
| Lap infants | TODO |
| Names as on ID / KTN / Global Entry | TODO (needed only at booking time) |

## Loyalty programs

Fill in the programs you actually hold. Balances drive the cents-per-point math, so
approximate is fine but "unknown" is not useful.

### Airline miles

| Program | Balance | Elite status | Notes |
|---|---|---|---|
| TODO (e.g. Delta SkyMiles) | TODO | TODO | |

### Hotel points

| Program | Balance | Elite status | Notes |
|---|---|---|---|
| TODO (e.g. Marriott Bonvoy) | TODO | TODO | |

### Transferable currencies

These are the flexible points that decide which airline programs are actually reachable.
Cross-reference with the `transfer-partners` and `transfer-bonuses` skills.

| Currency | Balance | Cards held |
|---|---|---|
| Chase Ultimate Rewards | TODO | TODO |
| Amex Membership Rewards | TODO | TODO |
| Capital One miles | TODO | TODO |
| Citi ThankYou | TODO | TODO |
| Bilt | TODO | TODO |

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
