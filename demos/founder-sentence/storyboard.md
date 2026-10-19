# Storyboard · the empty question that killed a render

1080x1350, 60 fps, 1620 frames = 27.0 s, recomposed to 1920x1080 (`index.html?fmt=wide`, groups rearranged,
nothing cropped). Beat = 36 frames (100 bpm); every cut in `timing.json.hits` is on the grid, secondary motion
deliberately is not. One object carries the film: the render the bot was writing. Every word on screen traces to
`facts.json` (F1–F6) and to the rulings at the bottom of that file.

Frame one is the failure, finished and still: the bot's card as it was actually posted — the sentence about a
question, the empty slot where that question should be, the note that its text could not be read, a dark
half-written sheet, and `0 attachments`. A stranger can see what is wrong before anything moves. Only then does
the film cut back to that same sheet being written, so the thing that dies is one we have already met.

| f (s) | On screen | Purpose | Audio | Carry-over |
|---|---|---|---|---|
| 0–72 (0.0–1.2) | **Cold open.** The card as posted, open and still: `Social Media Manager`, `13 Oct 2026`, `08:53:00.940 UTC`, **The run stopped to ask a question** / *(it cannot answer itself, so it was ended)*, the empty slot, *(the question text could not be read / from the session log)*, the dark half-written sheet, and `0 attachments`. Nothing moves but the caret and the grain | A stranger sees the failure itself, whole, before anything is explained. This is the frame X shows first, and `poster.png` is byte-identical to it | room tone only, no ticks | every element here returns, earned, from f216 |
| 72–108 (1.2–1.8) | A hard cut back in time. The compact card at 1.18: `Social Media Manager`, `08:53:00.940 UTC`, `13 Oct 2026`, and a sheet of distinct amber frames with a scan head painting the newest one top to bottom | A real tool mid-job, identified and in motion before the thumb stops | low room tone, one tick per written frame | the sheet keeps the same pixels for the whole film |
| 108–216 (1.8–3.6) | The head stops mid-frame. At f132 it twitches once and fails. Written frames stay written; their light goes out by f168, with the camera creeping in throughout so nothing parks | A tool dying, not a meter emptying | the tick train stops dead, one dull cut | the half-painted frame stays half painted to the end |
| 216–432 (3.6–7.2) | The card unfolds downwards; from f252 the posted body types in: **The run stopped to ask a question** / *(it cannot answer itself, so it was ended)*, an empty slot with a caret, and beside it *(the question text could not be read / from the session log)*. At f360 the attachment slot lands as `0 attachments` | The reveal is the content, not the object: this is what got delivered | key ticks, low thud on the zero | the empty slot |
| 432–540 (7.2–9.0) | Full-frame type, masked in and out: `it was killed to ask nothing.` | The hook, once, 1.8 s, then never again | a soft swell | — |
| 540–684 (9.0–11.4) | The founder's two sentences land as weighted objects on the card: *I got this but no image*, then *can you fix it?* No clock time is attached to either | A person is in the loop and wants it fixed | two soft wooden taps | the card is pressed down by their weight |
| 684–936 (11.4–15.6) | The card lifts and the machinery appears. The detached render switches to a **cold** language — blue outlines, a slow cold head — so it reads as still running with nobody holding it, never as the bug un-happening. f720 the `120 s` mark lights on `the call`. f756 `the render`'s tail drops into the `background`, tether cut, a dashed ghost where it should have stayed. f792 `AskUserQuestion questions: [ ]` arrives, its brackets visibly empty with a caret still blinking in them, and falls into f828 `question = normalizeQuestion(tu.input) \|\| { questions: [ ] };`, and comes out underneath as a **solid** object labelled `truthy`. f864 `killReason=question` lights red. f900 `exit 129` runs up the margin and crosses the gap to the detached render, which goes black | The cause, in order, with the conjunction as an event, and the one idea worth reposting said in one word: an empty array came out of that `\|\|` as an object, so it counted as a question | snap on the detach, paper on the envelope, a semitone-out pair on the fallback, hard hit on exit | the dead sheet is the same sheet from f108 |
| 936–1296 (15.6–21.6) | **The fix.** A panel rises over the mechanism, which stays lit behind it at 10%: `60f0e18`, `2026-10-13  09:17:23 UTC`, and the commit's own subject. f1044 a red rule sweeps left to right through the line we have been watching, `question = normalizeQuestion(tu.input)` / `\|\| { questions: [] };`. f1116 the lines that replaced it arrive one after another, beginning `const asked = normalizeQuestion(tu.input);`. f1188 `tests/claude-run.test.ts` reports `tests 29  pass 29  fail 0`, with one test named in full. f1260 the panel leaves and the kill chain is exactly where it was | The thing that broke, fixed, with the real characters and the counts the run actually printed — and nothing joining it to what follows. The commit is verified; its deployment is not | a low rise, a dry scrape on the strike, five rising notes as the lines land, two plain notes on the counts. No fanfare: it is a count, not a victory | the struck line is the same line from f828 |
| 1296–1368 (21.6–22.8) | A held breath. At f1332 the time **cuts** from `08:53:00.940 UTC` to `11:55:54.668 UTC`, `+3 h 2 min` lands above the card, and the sheet clears to empty. The `0 attachments` chip is retired in the 24 frames before the cut, so the later time is never shown carrying the earlier delivery | Time passed. The clock never rolls through times that did not happen, and no two facts are paired that were not true together | rising sweep, soft bell | both causes stay lit below, unchanged |
| 1368–1512 (22.8–25.2) | The same card writes a second, separate sheet from empty, faster, and completes it | The payoff is the same object working | the tick train returns | the full sheet |
| 1512–1620 (25.2–27.0) | `video_post_en.mp4  1679022 bytes` lands, a pass of light crosses the finished sheet, the card comes forward and the machinery drops to 32% at 0.8 scale | A real file, a real second delivery, with the causes still on the board but no longer the subject | click, then a resolve | the Lab page uses the same composition |

Sound-off read it must produce: a bot posted a question with nothing in it and no video; rewind — a render is
being written, and it stops dead; a person asks for it to be fixed; an empty question was treated as a real one
and the kill reached a render that had already been pushed into the background; that line was rewritten the same
morning and its tests pass; three hours and two minutes after the dead message the same flow posts a playable
file, while both causes are still sitting there.

## The playable page
One draggable handle: the shell timeout, the first of the two conditions. Two things are deliberately **not**
draggable. The repair: the fix is a commit, not a state of this model, so nothing on the page may enact it. And
the delivery: no handle position can produce the file.

The handle has exactly one evidenced position, `120 s`, and the page is built on that single test rather than on
a branch. At 120 the card wears `08:53:00.940 UTC` and the `0 attachments` chip, and the copy may call it the run
we measured. At every other value — on either side of the render — the card reads `model run`, carries no
timestamp and has no attachment row, and the copy says we never ran it there. The pointer has a 9 s detent on 120
and the arrow keys may not step over it, so the evidence is always reachable and never passed by accident.
`11:55:54.668 UTC`, `video_post_en.mp4`, `1679022 bytes` and `+3 h 2 min` exist only in the replay, where they
are shown as a separate, later run.

## Refusals
- No two verified facts are shown together unless they were true together: the `0 attachments` chip is retired
  before the clock cuts, so `11:55:54.668 UTC` never appears beside it.
- Minimum type on the canvas is 36 px, and 40 px or more for anything a claim rests on, measured as drawn:
  when the card steps back to 0.86 the evidence keeps about 40 px of ink, because the stated viewer sees
  1080 px of picture at about 390. The one exception is the quoted parenthetical at 34 px, which is source
  text rather than a number anything rests on.
- The diff, the commit hash and the test counts are shown because they were read and run for this piece (F5, F6)
  — but no progress bar, no ticking green check, and no claim that the fix was deployed. The revival is still
  never edited as the *result* of anything: no element of the mechanism changes state between f900 and the last
  frame, the fix panel is drawn *over* it rather than altering it, and the kill chain is exactly as lit at f1296
  as it was at f1260. No arrow, join or wipe is drawn between the commit and the 11:55 delivery.
- The clock never animates between the two verified timestamps. Interpolating them would put dozens of
  millisecond-precision UTC values on a message card that never existed; it cuts instead.
- The word "hours" never appears without its minutes. The replay button says `Replay the 3 h 2 min`.
- No invented value is drawn on the canvas. The dial's own position is HTML, a control, and the only timeout
  value printed inside the picture is the measured `120 s`.
- `1.68 MB` never reaches the screen or the copy (it is a rounded restatement of F4; the raw `1679022 bytes` is used).
- No second Discord message, no avatar, no sidebar, no server name, no customer data, no named fixer.
- No counter, frame count, percentage or render duration anywhere: none of those numbers is verified.
- `it was killed to ask nothing.` is declared editorial, traced to F3 (`questions: []` treated as a real question)
  and F1 (the run was ended, nothing was delivered).
- The compressed timeline and the stylised frames are disclosed in `post.txt`, `alt.txt` and on the page.
