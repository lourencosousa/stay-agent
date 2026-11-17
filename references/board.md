# Tracker and board

## tracker.json

One file per trip, rewritten after every change.

```json
{
  "trip": "faial-jan-2027",
  "label": "Stay agent/Faial Jan 2027",
  "status": "searching | wave 1 sent | choosing | chosen",
  "last_update": "2027-01-02",
  "places": [
    {
      "rank": 1,
      "name": "Casa do Cais",
      "kind": "whole house",
      "url": "https://...",
      "email": "info@...",
      "email_from": "contact page of their site",
      "score": 9,
      "why": "Stone house above Varadouro, wood stove, 10 min to Horta",
      "price_hint": "from 90 EUR per night",
      "season": "open all year",
      "wave": 1,
      "thread_id": "...",
      "sent_message_ids": ["..."],
      "sent": "2027-01-01",
      "followed_up": null,
      "status": "found | approved | drafted | sent | replied | offer | closed | chosen",
      "offer": {
        "available": true,
        "total": 450,
        "currency": "EUR",
        "includes": "breakfast, cleaning",
        "deposit": "30% on booking",
        "cancellation": "free until 14 days before",
        "min_nights": 3,
        "notes": "can lend a car for the stay",
        "replied": "2027-01-02"
      },
      "flag": null
    }
  ],
  "form_only": [
    { "name": "...", "url": "..." }
  ]
}
```

Places found but not yet approved keep `wave: null` and `status: found`. They are the next waves.

## The board

Shown after every update and written to `board.md`. Offers first, ranked; then everything still open.

```
## <trip>, <dates>, <guests> · board on <date>

<If anything is flagged: one bold line per flag first.>

### Offers
| # | Place | Total for the stay | Per night | Includes | Conditions | Read |
|---|---|---|---|---|---|---|
| 1 | Casa do Cais | 450 EUR | 90 EUR | breakfast, cleaning | 30% deposit, free cancel to 14 days | Best fit, can lend a car |

### Waiting
<n> places written to, no reply yet (<names>). Follow ups due on <date>.

### Closed
<names, with one word each: full, closed, declined>

### Next
<One line: the strongest option and why, or "offers do not meet the brief yet: wave 2 is ready with <n> places".>
```

## Ranking the offers

1. Drop offers that break the brief: well over the budget, something the user ruled out, not available.
2. Rank the rest by fit (the place's score), then by total price.
3. The "Read" column is one honest line: the strongest reason to pick it, or the catch.

Never present an estimate as an offer. A price only goes on the board when the place wrote it.

## When to propose the next wave

Propose it when any of these is true, and say why:

- Fewer than 2 offers meet the brief, 3 days after the last wave was sent.
- Every offer so far is over the budget guide.
- The user asks for more options.

Show the next places from the ranked list as before, and wait for the user's approval.
