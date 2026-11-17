# Stay Agent

Writes to small independent places to stay for your trip, handles the replies, and brings back the best offer.

![An example board for a made-up trip to Faial: three offers inside the budget ranked by fit, with the total price, the price per night and the conditions for each, one deposit request flagged and left unanswered, four places still waiting, and two replies drafted for approval.](images/example-board.png)

## Why I built it

I work with travel and hospitality brands, and I know small places often answer an email with a better price than booking sites show, especially off season. But writing to fifteen of them, in their language, and keeping track of every answer takes hours. So almost nobody does it.

## What it does

- **Asks first.** A few quick questions: where, when, how long, how many people, budget, kind of place.
- **Finds the places.** Small independent stays with a public email on their own site, ranked by fit.
- **Writes to them.** One email you approve once, filled in for each place, sent from your Gmail.
- **Handles the replies.** Records each offer, drafts answers and one follow up, and flags anything that asks for a deposit or your details.
- **Brings back the best offer.** A board of the offers, ranked, with the conditions side by side.

Nothing is sent without your OK. It never books, pays or shares your details.

## How it works

You tell Claude where you want to go. It asks a few questions, then searches the places' own websites, small hotel guides and tourism boards for independent stays, and keeps the ones with a public email. You approve the list and one email template. It sends from your Gmail in small waves, best fit first, and labels every thread. When you ask for an update, it reads the replies and shows you the board.

## Install

**Best: the Claude desktop app, in the Code tab**

This is where it can keep track of a search over several days.

1. Open the Claude desktop app on your computer and go to the Code tab.
2. Connect Gmail in Settings, then Connectors.
3. Paste this and send it:

```
Install this skill: https://github.com/lourencosousa/stay-agent
```

4. Say yes when Claude asks to approve a step.

Use the desktop app, not Claude Code in the browser (claude.ai/code). The browser version runs on a computer in the cloud and forgets the search when the session ends.

Already use Claude Code in a terminal? Run:

```bash
git clone https://github.com/lourencosousa/stay-agent ~/.claude/skills/stay-agent
```

**Claude chat (claude.ai)**

1. Download [stay-agent.zip](https://github.com/lourencosousa/stay-agent/releases/latest/download/stay-agent.zip). Don't unzip it.
2. In Claude, open Settings, then Capabilities, and make sure code execution is on. Connect Gmail in Connectors.
3. Open Customize, then Skills. Click "+", then "Create skill", then "Upload a skill", and choose the zip.

Use this zip, not GitHub's "Download ZIP" button: that one renames the folder and Claude rejects it. In the chat, keep the same conversation for the whole trip, because it holds the search.

## Use

- "Find me a stay in Madeira."
- "Find me a stay in Faial, 10 to 17 January."
- "Any replies?"

## Good to know

- It is free. It runs on the Claude plan you already have, with no API keys.
- It writes only to places that publish an email on their own website, never through booking platforms.
- It only reads the threads it started. The rest of your inbox is left alone.

## Status

The questions, the search and the emails are tested. Handling the replies is next, on my own trip to the Azores.

Made by Lourenço Sousa · [GitHub](https://github.com/lourencosousa) · [LinkedIn](https://www.linkedin.com/in/louren%C3%A7o-sousa-948195304/)

## License

MIT
