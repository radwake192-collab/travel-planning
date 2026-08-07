# How to check flights and get the best deal

A browser-only playbook. **No API keys, no subscriptions, no Docker.** Works today.

Both trips are domestic economy at 4 seats. That profile is not where exotic award
routing pays off — the winner is almost always whichever of Southwest, cash, or the Chase
portal is cheapest all-in. The goal here is to check the five places that matter, in about
30 minutes, and not miss anything.

Always search **4 passengers** (2 adults + 2 children). Lap infant is added separately and
flies free domestically. A price quoted at 1 passenger is not your price — fare buckets
sell out, and the 4th seat often prices higher than the 1st.

---

## The 30-minute check, in order

Do these in one sitting so the prices are comparable. Record every number in the table at
the bottom.

### 1. Southwest — `southwest.com` (5 min)

The most important stop, because **Southwest appears in no other search tool.** Not Google
Flights, not Kayak, not Expedia, not Seats.aero. If you skip it you have no idea what the
market looks like.

- Search 4 passengers, your dates.
- Toggle between **Dollars** and **Points** — the site shows both for the same flight.
  Record both.
- Note the fare class. **Avoid "Basic"** — it is not changeable or refundable. Wanna Get
  Away Plus and above retain the free-cancellation behavior that makes Southwest useful as
  a placeholder (see "The free option" below). Verify current fare rules at booking;
  Southwest changed these recently.
- Two free checked bags per person is worth roughly **$280 round trip for four people**
  against most carriers. Factor that into every comparison.

### 2. Delta — `delta.com` (5 min)

- Search 4 passengers, same dates. Record the cash price.
- Re-run with **"Shop with Miles"** checked. Record the SkyMiles price + taxes.
- You have ~120K SkyMiles and no way to add to them, so the question is whether this
  specific redemption is worth spending them on.

### 3. Google Flights — `google.com/travel/flights` (5 min)

- 4 passengers, then open the **date grid** and **price graph** for ±3 days.
- This shows the whole market except Southwest, and tells you whether shifting a day saves
  real money.
- Use it to spot any carrier you hadn't considered.

### 4. Chase Travel portal — log in at `chase.com` (5 min)

- Price the same itinerary. The portal shows the points cost directly.
- Your rate is **1.25 cpp** (Sapphire Preferred) or **1.5 cpp** (Sapphire Reserve).
  Confirm which card you have — across 220K points that's a $550 difference.
- Portal bookings are paid tickets, so they still earn airline miles and count toward
  status.

### 5. Flying Blue and Virgin Atlantic (10 min, free)

Both take Chase points 1:1 and both can book Delta-operated flights.

- Flying Blue: `airfrance.com` or `klm.com` → award search, 4 passengers.
- Virgin Atlantic: `virginatlantic.com` → Flying Club award search, 4 passengers.
- **You do not need to transfer points to search.** Create a free account and look.
- These see only the *partner saver* space Delta releases, which is thin — especially at
  4 seats on peak dates. Low odds, but it's the only path that might beat everything else
  outright, and checking costs nothing.

**Never transfer points before confirming the exact award is bookable and priced on the
partner's own site.** Transfers are irreversible and these programs don't reliably hold
awards.

---

## Then do the math

For each points option:

```
cents per point = (cash price − taxes you still pay on the award) ÷ points × 100
```

Compare against these, from `data/points-valuations.json`:

| Currency | Floor | Ceiling | Read |
|---|---|---|---|
| Chase UR | 1.7 | 2.05 | Redeeming below 1.7 spends a premium currency at a discount |
| Delta SkyMiles | 1.0 | 1.25 | Mediocre miles. Spend them somewhere defensible. |
| Southwest | 1.2 | 1.3 | Revenue-linked, so it lands here almost every time |

**Don't be a purist about it.** Those floors answer "is this a *good* use of points,"
which is a different question from "what should I do." If you'd otherwise pay cash and the
points genuinely save you money you'd have spent, use the points — the floor only matters
if you have a better redemption actually lined up. For a family of four on a domestic
holiday route, the lowest real out-of-pocket number usually wins.

---

## The free option (the actual trick)

If Southwest is anywhere near competitive, **book it early with points on a refundable
fare.** Southwest returns the points to your account and refunds the taxes if you cancel
before departure — so an early booking is a free hedge against holiday prices climbing,
not a commitment. Keep checking, and cancel if something better shows up.

This is the single most useful move available on the Thanksgiving trip, because the risk
there is entirely one-directional: peak holiday fares rise as you approach.

Two supporting rules:

- **US DOT 24-hour rule:** any ticket booked 7+ days before departure can be cancelled
  free within 24 hours, on any US carrier. You always have a one-day free look.
- **Most US carriers issue a travel credit if the fare drops after you book.** So booking
  early is rarely a mistake — use the `gardening` skill against `trips/reservations.json`
  to catch drops.

---

## Do you need a Seats.aero subscription?

**For these two trips, probably not.** It's ~$8/month and its value is finding saver space
on international premium cabins — a completely different problem from four economy seats
on CMH–MSP. Step 5 above checks the same partner space by hand for free.

Get it if you start planning international business class. Skip it for now.

---

## Record your results

| Option | Cash (4 seats) | Points | Taxes | Bags | **All-in** | cpp |
|---|---|---|---|---|---|---|
| Southwest cash | | — | | $0 | | — |
| Southwest points | — | | | $0 | | |
| Delta cash | | — | | | | — |
| Delta SkyMiles | — | | | | | |
| Chase portal | — | | | | | |
| Flying Blue | — | | | | | |
| Virgin Atlantic | — | | | | | |
| Other carrier | | — | | | | — |

Lowest **All-in** wins. Paste this back into a session and the toolkit can do the cpp math
and the recommendation.
