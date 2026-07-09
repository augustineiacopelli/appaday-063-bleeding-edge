# Bleeding Edge

**AppADay 063** · Educational · AI-powered

Name a subject area. Bleeding Edge sends Claude out across the live web and comes back with a map of the research frontier: where the field currently stands, which fronts are in motion, what has actually been published recently and whether it was truly refereed, which neighboring fields hold methods this one has not picked up, and which questions nobody has claimed yet. Pick one of those open questions and it charts a first project plan. Come back in a month, re-scan, and it tells you what changed.

**Live:** https://augustineiacopelli.github.io/appaday-063-bleeding-edge/

**Portfolio:** https://augustineiacopelli.github.io/appaday/

---

## What it does

Type a subject into the console, choose who the brief is written for, and run a scan. Claude searches the web several times before answering, so the results reflect what is on the record right now rather than what a model half-remembers from training.

The brief comes back in two halves, divided by a glowing rule that runs across the page. Above the rule is charted territory: a three-sentence read on where the field stands, three or four active research fronts with a note on what recently made each one possible, and a short list of recent work with real retrieved links. Below the rule is open ground: three or four genuinely unanswered questions, each tagged Accessible, Ambitious, or Moonshot depending on how much apparatus it would take to attack.

Any of those questions can be pushed further. Choosing **Chart a course** sends the question back to Claude for a project plan: the question narrowed until it is answerable, what a strong result would contribute and to whom, the methodology that fits, three concrete opening moves, the data or instruments required, and the three ways it is most likely to go wrong.

## Who the brief is written for

Four audiences, and the selector governs register, access, and difficulty rather than vocabulary alone.

A **high school** brief defines every term and unpacks every acronym, but it does something more important than simplify. It restricts sources to work the reader can actually open without a university login, because a citation behind a paywall is worse than no citation to a sixteen-year-old. It also refuses to hand that reader an unattackable frontier problem, and instead surfaces open questions a determined student could make real progress on in a semester: a careful replication, a measurement nobody has taken in a local setting, a public dataset nobody has re-analyzed.

An **undergraduate** brief defines terms on first use, assumes an introductory course and no more, and takes paywalled articles for granted because a library proxy exists.

A **graduate** brief orients briefly, then gets specific. Schools of thought are named rather than explained.

A **researcher** brief refuses to explain fundamentals. It argues, naming the live disagreement and saying which side the current evidence favors and why, and where the evidence is balanced it says so and names what would break the tie. Then it judges the field as an institution, saying plainly which lines of work are overfunded relative to their yield, which are starved, and where the field is fooling itself.

The earlier build split that last tier into Doctoral and Faculty. In practice the distinction was between evaluating propositions and evaluating how a community has allocated its attention, which is a real difference but far too thin to be a control, and a doctoral student wants both reads anyway. Merging them freed a slot for the audience that was genuinely missing. Anyone whose browser still holds the old setting is migrated to Researcher silently.

## Tractability is relative

Accessible, Ambitious, and Moonshot are graded against what the chosen reader can plausibly command, not in the abstract. For a high school reader, Accessible means a public dataset, a classroom setup, and one email to a researcher who might reply. For a graduate reader it means feasible inside an existing lab within a year. For a researcher it means fundable with a standard grant using apparatus that already exists. Moonshot means the instrument or the theory does not exist yet, for anyone. The same question can therefore be Accessible to one reader and a Moonshot to another, and the app says so under the questions rather than pretending the grades are absolute.

## The guide

Three things on the page carry labels, so a question mark beside the audience pills opens a single modal explaining all of them: what each audience level changes, what the three provenance grades mean, and what the three tractability grades mean. The same modal is reachable from a link under the citation caution and another under the open questions, so the explanation is always one tap from the thing it explains. Tooltips were the obvious answer and the wrong one: they do not exist on touch, and a four-way comparison is a table, not a hover.

## Provenance grading

Every item in the recent-work list carries a grade. **Peer-reviewed** means a refereed journal or refereed conference proceedings. **Preprint** means arXiv, bioRxiv, SSRN, PhilPapers, or any server with no referee between the author and the reader. **Secondary coverage** means a news article, a magazine piece, or a press release describing work published elsewhere. Claude is instructed to grade down rather than up whenever it is uncertain whether a venue is refereed.

This exists because students routinely cite a preprint and a *Nature* paper as though they carry the same authority. Displaying the distinction on the card, in a different color, next to the finding itself, teaches it without a lecture. For the high school audience the grading matters twice over, since the sources it can reach skew toward preprints and press releases precisely because those are the ones that are free.

There is a fourth state the guide names: **Ungraded**, shown with a dashed amber border. It appears when Claude returned no grade or one that could not be read. Nothing defaults to peer-reviewed, because a badge that a record did not earn is worse than an honest blank. A recovered record missing its grade entirely is dropped from the page rather than shown.

The grades are Claude's judgment, not a database lookup, and the app says so on the page. Every link is displayed in full and every brief carries the same instruction: open the source, confirm the author, venue, and year, and read the paper before it reaches your bibliography. A citation you did not read is not a citation.

## What the neighbors have

Below the open questions is a block naming three adjacent fields that possess a method, instrument, or formalism this field has not adopted, with two sentences on what importing it would let the field see. Genuinely original work usually sits at the seam between two literatures that do not cite each other, and this is the section most likely to produce a thesis nobody else is writing.

## Watching a subject

Every scan is saved. Watched subjects appear as chips beneath the console with the age of the last scan, and clicking one restores the full brief instantly with no API call. Running **Re-scan for new work** searches again and compares the result against the previous scan: anything that was not in the last brief is marked **New**, and a line at the top reports how many findings and how many open questions have appeared since. If nothing has changed, it says so plainly.

Twelve subjects are kept, oldest evicted first. Charted courses persist across re-scans, keyed to the text of the question rather than its position, so a plan survives the frontier moving underneath it.

This is watching, not watching-for-you. The app has no backend and no scheduler, so it cannot wake up and tell you something landed. It can only tell you what changed since the last time you looked, which is what the browser can honestly do.

## Two exports

**Copy the brief** puts the whole thing on the clipboard as markdown, ready to become the first page of a proposal or a paper.

**Copy slide outline** produces something structurally different: a numbered deck with one active front per slide, a slide that reads only *past this line, the field has no answer yet*, one slide per open question, three slides for any charted course, and speaker notes under each telling you what that slide is for. It closes on a single next action rather than a summary. Both exports are built locally and cost nothing.

## Design notes

The subject is an instrument, so the interface is built like one. IBM Plex Mono carries the readouts, labels, and metadata; IBM Plex Sans carries the body; Instrument Serif carries the headlines and the research questions themselves, which are the one place in the app where a question deserves to look like a question rather than a data field.

The signature element is the edge itself. A hot crimson hairline crosses the full width of the page with the color bleeding downward into the dark beneath it, and it sits exactly where the charted material ends and the unclaimed questions begin. Everything above the line is a report. Everything below it is an invitation. The accent colors carry meaning rather than decoration: teal marks what has been verified, refereed, or newly arrived, amber marks the unrefereed and the ambitious, crimson marks the unresolved.

## The progress meter

A scan takes about a minute, which is long enough that a spinner becomes a lie. So the app streams the response rather than waiting for it, and reports what is actually happening.

Each search Claude issues appears in the panel as it is issued, showing the literal query text. The bar advances as results come back, giving the search phase the first forty percent of the run. When the first token of the brief arrives the phase changes to composing, and the bar fills against the expected length of the payload, capping at ninety-six percent so it never claims to be finished before it is. A clock counts up beside it. Nothing on that panel is invented: the queries are Claude's own, and the bar only moves when an event arrives.

The pacing constants are estimates, and the last stretch of the writing phase can crawl if the brief runs long. That is the honest failure mode of a determinate bar against an unknown output length, and it is preferable to a spinner that conveys nothing. Browsers without `ReadableStream` fall back to a non-streaming request and a rotating status line.

## When the brief is cut off

Sonnet 5 and Opus 4.8 spend part of the output budget thinking before they write, so the token ceiling has to sit well above the size of the brief. It is set at 16,000 for a scan and 4,000 for a charted course.

If a brief is cut off anyway, the app does not throw away a minute of searching. It walks the fragment backwards to the last complete value, closes whatever brackets are still open, and rebuilds what arrived. Half-written records are then dropped rather than rendered, because a paper missing its provenance grade would otherwise be displayed as though it had one. A banner at the top of a recovered brief says plainly that it is a fragment and that later sections may be missing.

When even that fails, the error panel reports whether the response hit the output ceiling and offers to show the raw text that came back, so a failure is diagnosable rather than merely annoying.

## Running it

Bleeding Edge calls the Anthropic API directly from the browser with a key you supply. Open the gear icon, paste an API key from [console.anthropic.com](https://console.anthropic.com), and save. The key is written to `localStorage` in your browser and is never sent anywhere except Anthropic.

## Choosing a model

The gear also holds a model selector, because this app asks two different things of Claude and the right answer is not the same for everyone.

**Sonnet 5** is the default. It beats Sonnet 4.6 on every published benchmark, and on Humanity's Last Exam with tools, which is about as close as a public benchmark gets to what this app does, it lands within half a point of Opus 4.8. Introductory pricing runs $2 per million input tokens and $10 per million output through August 31, 2026, after which it returns to the $3/$15 that Sonnet 4.6 charges today. Note that it uses the newer tokenizer, which counts roughly a third more tokens for the same text, so the saving is smaller than the rate card suggests.

**Opus 4.8** costs $5 and $25 per million and buys judgment. That matters in exactly two places here: the Researcher brief, which is asked to take a side and name what a field is fooling itself about, and the provenance grading, where a confidently wrong peer-reviewed badge is worse than no badge. If either of those is load-bearing for you, pay for it.

**Sonnet 4.6** remains in the list for parity with the rest of AppADay, and for keys that lack access to the newer models.

Web search is billed on top of tokens at $10 per thousand searches, and a scan uses up to six. Expect somewhere between a few cents and a couple of dimes per scan. The brief records which model produced it, on the page and in both exports, because a claim about the research frontier should carry the provenance of the thing that made it.

Sonnet 4.6 was the previous default and is now strictly dominated by Sonnet 5, which is better on every measure and cheaper until September. That has implications beyond this app.

## Built with

Vanilla HTML, CSS, and JavaScript in a single file. No frameworks, no build step, no dependencies beyond two Google font families. Claude via the Anthropic Messages API, streamed, with the `web_search_20250305` server tool and a ceiling of six searches per scan. Newer web search tool versions support dynamic filtering of results before they enter context, which is well suited to citation verification, but they require the code execution tool alongside them and are restricted to specific models. That is a future upgrade, not today's.

---

Part of [AppADay](https://augustineiacopelli.github.io/appaday/) — one complete, functional web app built and shipped every day.
