# Questionnaire

Every new trip starts here. Keep it short and objective: the emails do the narrowing, so a brief that is too picky only shrinks the list.

## How to ask

Start with the question card (the AskUserQuestion tool) as the very first thing, with no message before it. Never ask anything as typed text. Every question has an "Other" box for anything the buttons do not cover.

Skip any question the user's request already answers. If the request answers everything, go straight to the brief.

## Card 1: the trip

1. **Where to?** (single choice) Header: `Place`. Description: type the place in "Other".
   Options: Not sure yet (suggest three places that fit the month and budget, then carry on) · A few in mind (type them in "Other", the search covers all of them)
2. **When?** (single choice) Header: `When`. Description: exact dates or a month go in "Other".
   Options: Next month · In 2 to 3 months · Any time, flexible
3. **How long?** (single choice) Header: `Length`.
   Options: A weekend · 4 to 5 nights · 1 week · 2 weeks
4. **How many people?** (single choice) Header: `People`. More than 4, or children and their ages, go in "Other".
   Options: 1 · 2 · 3 · 4

If the answer to "When?" is not exact dates, follow with one card that offers the specific weeks of that month (for example 1 to 8 Feb, 8 to 15 Feb), with "Any week" first, and a note on anything that matters for those dates, like a festival.

## Card 2: the stay

5. **Budget per night?** (single choice) Header: `Budget`. Use the user's currency if they gave one. An exact amount goes in "Other".
   Options: Under 60 € · 60 to 100 € · 100 to 150 € · Over 150 €
6. **What kind of place?** (several) Header: `Kind`.
   Options: Whole house or apartment · Room in a guesthouse · Small hotel · Any
7. **Anything else to take into account?** (single choice) Header: `Anything else`. Description: type anything in "Other": a view, pets, a desk, near the old town, no stairs.
   Options: Nothing else · Dates can move a day or two

Where the card tool is not available (for example in the Claude chat), ask the same questions as one short numbered message, with the options written out.

## Defaults, never asked

- **Budget** is a guide. A place up to 20% over makes the list only if it clearly fits better, and it is marked.
- **Ranking** is by fit, then price.
- **Name** for the emails: the first name on the Gmail account. Shown in the drafts, so the user can correct it.

## The brief

Write the answers to `brief.md` as a plain list, then show it back in chat as the same list, not a code block, and ask "Is this right?" Nothing is searched before a yes.

- **Trip:** <trip name>
- **Place:** <place>
- **Dates:** <arrival> to <departure>, <n> nights, <fixed or can move a day or two>
- **People:** <n>, <children and ages if any>
- **Budget:** <amount> per night
- **Kind:** <kinds>
- **Take into account:** <their words, or nothing>
- **Sign as:** <name>

The brief can change at any time: "make the budget 150", "add Pico". Update `brief.md`, say what changed, and re-score the places if it affects the fit.
