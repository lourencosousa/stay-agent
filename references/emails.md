# Emails

Every email is short, polite and specific. It reads like a person who chose this place, because they did.

## Language

Every email is in the language the user writes to Claude in, and only that one. Never two languages in one email. Place names stay as they are.

## The template

The first email is one template, the same for every place. Only what is in brackets changes per place.

Subject: `<dates> · <n> guests · enquiry`, for example `1 to 8 February · 2 people · enquiry`.

Body:

1. A greeting to [the place by name].
2. [One sentence on why this place]: the specific detail from the "why it fits" line. Never generic praise.
3. The ask: the exact dates, number of nights, people, and [the kind of room or unit].
4. What to ask them, only what matters for the brief, in one short list:
   - availability for the dates
   - the total price for the stay, and what it includes
   - the conditions: deposit, cancellation, minimum nights
   - one or two things from "take into account" in the brief that their site does not answer (for example "is there a desk and good wifi?")
5. If the stay is off season or longer than 4 nights, one plain line inviting their best rate: "If you have a better rate for a stay of this length in January, we would be glad to hear it." Never more than that, never a demand.
6. Thanks, and the name from the brief.

Under 120 words. No links, no attachments, no signature block beyond the name.

Show the template once, in full, with the brackets visible. Under it, a table of what fills the brackets for each place in the wave:

| # | Place | Why this place | Unit |
|---|---|---|---|

The user approves the template once. On their OK, fill it in for every approved place, create the drafts and send. If they change the template, the change applies to every email.

## Sending

- Create every draft first. Then send by draft id, in batches of 5 with a short pause between batches.
- After each send, add the trip label to the thread and record the thread id, the sent message id, the date sent and `status: sent` in the tracker.
- If a send fails, stop, say which one, and keep the rest as drafts.

## The update

When the user asks for an update:

1. Search the trip label for threads with new messages since the last update.
2. Read each new reply in full. Record in the tracker: available yes or no, total price, what it includes, deposit, cancellation, minimum nights, anything else that matters for the brief, and the date of the reply.
3. Decide what each reply needs:
   - **A clear offer, nothing asked:** no reply needed yet. It goes on the board.
   - **A question** (arrival time, number of guests, how they found the place): draft a short answer using only the brief. If the answer is not in the brief, ask the user.
   - **A partial answer:** draft one short reply asking only for what is missing.
   - **Full, closed or a no:** mark it closed. If they were kind, draft a one line thank you, optional.
   - **A request that commits the user** (a deposit, a booking form, a card, ID, address, phone, a signed contract, "shall I hold it for you?"): draft nothing. Flag it at the top of the update in bold, with what they ask and by when.
4. **Follow ups.** For every place with no reply 3 days after the first email, draft one follow up. Never a second.
5. Show the update in this order: flags first, then the board (see `references/board.md`), then the drafts waiting, numbered, each with one line on what it says.
6. Ask: "Send these?" The user can say "send all", "send 1 and 3", or change one first. Send only what they named.

## The follow up

In the same thread, in the user's language:

"Hello again, just checking whether you had a chance to see our message about <dates>. Thank you, <name>."

One line. Nothing else.

## Choosing

When the user picks a place:

- **To the chosen place:** a short reply saying they would like to go ahead, and asking how the place would like to confirm. Never include payment or personal details. The user takes it from there.
- **To the others that made an offer:** a short, warm no thanks. Optional, the user decides.
- Mark the trip `chosen` in the tracker.

## Never

- Never send a draft the user has not approved in this conversation.
- Never answer a commitment request: deposit, payment, card, ID, address, phone, contract.
- Never invent a competing offer, a deadline or a detail about the user.
- Never write a second follow up, or write again to a place that said no.
- Never use an address found only on a booking platform.
