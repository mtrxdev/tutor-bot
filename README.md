# Tutor (single-file adaptive tutor)

File: `tutor.html` (all HTML/CSS/JS inline, no internet needed).

## How to open
- **Easiest:** open the hosted link in Chrome (see bottom). The microphone works best there (HTTPS).
- **Offline:** double-click `tutor.html`. It opens in your default browser. For the voice + mic, use Chrome or Edge.
- Tap the big **Start** button (browsers need one tap before they can talk).
- First time: it offers a short 5-question "game" to find the starting level. You can tap **Skip**.

## Browser notes
- Chrome / Edge (desktop): speaking + listening. Chrome asks for microphone permission; allow it. On a double-clicked local file, Chrome may ask again each visit; the hosted HTTPS link remembers it.
- Safari / Firefox: speaking works; listening is usually not available, so it runs taps-only. No error is shown to the child.
- If the mic is blocked or unsupported, everything works with taps.

## The session (8-10 min, always the same order)
1. Preview (5 step icons) 2. Warm-up (2 review/strength questions) 3. New idea (one skill, with a picture) 4. Practice (3-4 adaptive questions) 5. Check (1-2 new questions) then Finish: one-line recap, star on the skill map, "Session done."

## Parent controls
Press and **hold the small gear in the bottom-right corner for 2 seconds**.
- Mastery map (levels, correct days, mastered, next review date)
- Weekly summary (common triggers, what helped, trend) and the frustration log
- Sound on/off, microphone on/off, voice speed, test voice
- Export log (JSON download), Reset all data
- "Testing tools" (click to open): **Treat today as a new day** (simulates the next day, so you can test mastery = correct on 2 different days), show placement game again.

Progress is saved in the browser (localStorage) on that computer only. Each browser/computer keeps its own progress. Clearing browser data erases it.

## How it adapts
- 2 correct in a row, each faster than her own median time -> harder level (or finish practice early at the top level).
- Wrong answer or long pause (> 2x her median, min 8 s) -> half step back: next question gets a picture hint / split steps; a second miss lowers the level. A long pause gets the same question repeated once in the same words. A wrong answer is never followed by the identical question.
- Mastered skills are not re-taught; they come back as warm-ups at 1 day, 3 days, 1 week, 1 month.
- A skill is only introduced when its prerequisites are mastered.

## Frustration handling
Signals: 3+ wrong in a row on one skill (not counted if answers are getting closer), very fast wrong answers, no response > 2x median, repeated taps off the targets, saying "stop", "I'm done", "I don't want to", "how many more" or off-topic words, pressing Break mid-problem or leaving the page. Two signals within 60 s -> pause, calm line, 3 choices: map question / break / smaller problem. A second trigger in one session ends it calmly with the normal recap. Every event is logged.

## Not implemented / limits
- Voice tone detection (not reliable in a browser).
- Speech recognition quality depends on Chrome's service (needs internet in Chrome); taps always work.
- Drag-and-drop works with mouse/touch; tap-to-place also works (tap the label/block, then tap the place).
- Flags warm-ups (optional) are not included.
- World map shapes are simplified.
