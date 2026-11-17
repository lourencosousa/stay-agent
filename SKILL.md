---
name: stay-agent
description: Finds small independent places to stay for a trip, writes to them from the user's Gmail, handles the replies over the following days, and brings back the best offer. Every email waits for the user's OK. Use when the user wants a place to stay somewhere and says things like "find me a stay in", "find accommodation in", "write to places in", "start a stay search", or asks for an update on a stay search ("any replies?", "update my stay search", "how is the Azores search going").
---

# Stay agent

Booking sites show the big places at their listed price. Small independent places, especially off season, often answer an email with better prices, better conditions and real availability. Nobody has the patience to write to fifteen of them and keep track of the answers. This skill does that legwork, and the user decides every step.

## The flow

A trip goes through these stages, in order. The tracker (see below) records where each trip is, so the user can come back days later and carry on.

1. **Questionnaire.** Always first, for every new trip. Read `references/questionnaire.md` and run it: start straight with the question cards, no typed questions. End with the brief shown back for a yes.
2. **Find.** Read `references/find.md`. Search wide, with no fixed limit, and score every place against the brief.
3. **The list and the template.** Read `references/emails.md`. Show the ranked list, the first wave (the top 10 by default), and one email template with a table of what changes per place. The user approves the template once, removes places or changes the template. Nothing is sent before their OK.
4. **Send.** On OK, create the approved emails as Gmail drafts, send them, and label every thread (see Gmail below).
5. **Update.** Whenever the user asks for one: read the replies, record the offers, draft answers and follow ups, flag anything that commits the user, and wait for their OK to send. Read `references/emails.md` and `references/board.md`.
6. **Next wave or choose.** If the offers do not meet the brief, propose the next wave from the ranked list. If they do, show the board, and when the user picks, draft the confirmation and the polite no thanks to the others.

When the user comes back with "any replies?" or similar, find the trip in the tracker and run step 5. If there are several open trips, ask which one.

## Rules

- **Nothing leaves without an OK.** Every email, first contact, follow up or reply, is shown to the user before it goes. Send only after the user says so in this conversation, and only the emails they named. "Send them" means the emails just listed, nothing else.
- **Never commit the user.** Never accept an offer, book, pay, sign, or agree to a deposit. Never send the user's ID, card, address, phone number or date of birth. When a place asks for any of these, flag it to the user and draft nothing that gives it.
- **Waves, not blasts.** Contact in waves ranked by fit. Send in batches of 5 with a short pause between them. One follow up per place, never a second.
- **Honest emails.** A real enquiry from a real person. No invented details, no fake urgency, no pretending to be a travel agent. Never claim a competing offer that does not exist.
- **Respect a no.** A place that declines, is full, or asks not to be contacted is closed in the tracker and never written to again.
- **Plain and short.** No em dashes. Write every email in the language the user writes to Claude in, never mixed.

## The tracker

Each trip has a folder: `~/stay-agent/<trip>/`, where `<trip>` is short, like `faial-jan-2027`.

- `brief.md`: the answers from the questionnaire.
- `tracker.json`: every place found, its score, its email, its wave, its Gmail thread id, its status and its offer. Format in `references/board.md`.
- `board.md`: the current board, rewritten after every update.

Read the tracker at the start of every turn about a trip, and write it after every change. It is the memory between sessions.

If files cannot be written (for example in the Claude chat), keep the brief and the tracker as a block at the end of each message and tell the user once: "Keep this chat for the whole trip, it holds the search."

## Gmail

The skill needs the Gmail connector. If its tools are not available, say so plainly and stop: "Connect Gmail in Settings, Connectors, then ask me again."

- **Drafts first.** Create each email as a Gmail draft. For a reply, pass the id of the message being answered so it lands in the same thread. The user can read and edit the drafts in Gmail too.
- **Send on OK.** Send each approved draft by its draft id, so any edit the user made in Gmail is what goes out.
- **Label.** Create one label per trip, like `Stay agent/Faial Jan 2027`, and add it to every thread after sending. Replies then stay together, and the update searches `label:` that name.
- **Never touch anything else** in the user's inbox: no reading other threads, no deleting, no archiving.

## Where it runs

Best in the Claude desktop app's Code tab with Gmail connected: the tracker is saved and a search can run over days. Claude Code in the browser forgets the tracker when the session ends, so warn the user if that is where they are.
