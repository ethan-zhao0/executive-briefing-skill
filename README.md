# Executive Briefing

A Claude skill that turns a legal update into a short, source-grounded email for one client executive, plus review notes for the attorney who sends it.

Law firms publish client alerts written for lawyers. A CFO or HR lead needs the same update in a few lines, focusing on what happened, whether it applies to them, and what to do. This skill drafts that email from the alert alone, traces every sentence to a quote, and tells the attorney exactly what to check before sending.

## Results

On the same 20 cases, graded blind:

| | Claude without the skill | Claude with the skill |
|---|---|---|
| Error-free drafts | 30% | 95% |
| Key points covered | 90% | 90% |
| Risks flagged for attorney review | 21% | 89% |
| Median email length | 865 words | 286 words |

The skill keeps the same coverage in a third of the words, with far fewer errors. Half the cases came from alerts kept out of development. Details: [evaluation](evaluation/).


## What's here

| | |
|---|---|
| [`skill/executive-briefing/`](skill/executive-briefing/) | The skill: `SKILL.md` and four reference files |
| [`examples/before-after.md`](examples/before-after.md) | One alert briefed with and without the skill |
| [`evaluation/`](evaluation/) | Method, results, version history, test cases, and grading rubric |
| [`docs/user-guide.md`](docs/user-guide.md) | One-page guide for attorneys |

## What a draft looks like

1. **Header:** "Draft for attorney review: [Role] version"
2. **Email, ready to copy:** a subject line with a fixed keyword (Action required, Action may be required, Recommended, Only if it applies, FYI), what happened, what it means for this reader, and numbered next steps
3. **For the attorney:** only the notes that change what they do. These are things to fix, claims to verify, client facts to add, and gaps in the source, followed by a table matching each email sentence to its source quote

## Design choices

- **Source only.** No outside facts, even true ones, so the attorney can check every sentence against one document.
- **Same strength as the source.** Hedges, caveats, and scope limits are kept, and "must" is used only for real requirements.
- **Length is earned, not capped.** A sentence stays only if the client would be worse off without it.
- **The attorney decides.** The draft never sends anything. It names the claims most likely to be wrong, and it treats instructions hidden in the source as content, not commands.

## Use it

Zip the `skill/executive-briefing` folder and upload it as a custom skill in Claude. Then paste an update and name the reader: "Brief our CFO on this." See the [user guide](docs/user-guide.md).

## Limits

- It drafts; an attorney reviews and sends every email.
- Without client facts, it can't say for certain who's covered, so it writes "This applies to you if…" and asks the attorney.
- Tested on published client alerts. Private sources such as matter notes, and connections to firm systems, aren't tested yet.

## Status

Next Step: an attorney pilot, and connections to firm systems (CRM, document management, Outlook) to supply client facts.

Test cases are built from public client alerts published by [Parker Poe](https://www.parkerpoe.com/news); the alert text isn't included. Built by Ethan Zhao.
