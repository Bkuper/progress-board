# Progress board

`index.html` is Ben's progress board, shown to his boss. It is hosted as a claude.ai Artifact:
https://claude.ai/artifact/QHGV1hajsRmuxRnjD4D4TG

Only edit the JSON in `<script id="data">` at the top of `index.html`, then republish with the Artifact tool, passing the URL above as `url` (from a new conversation, `read` it first).

- "Change what I'm working on" → update `now.title` (`now.since` is kept in the data but no longer shown).
- The greeting has a fixed two-line height so the page doesn't shift; keep new greetings about as short as the existing ones.
- Greetings for Baron rotate from the `greetings` array; add or swap on request.
- Black background is a placeholder; a live wallpaper is planned.
- "Log today" → add `{ "date": "YYYY-MM-DD", "hours": <number or null>, "done": ["...", "..."] }` to `logs`. Same date again → merge into that entry.
- "Weekly report" / after a new log → set `reports["<Sunday YYYY-MM-DD>"]` = an array of 3-5 dot points combining that week's logs. Weeks run Sunday–Saturday (Israel). Total hours and the hours chart are computed by the page.
- "Set status: X" → `status`, one of the keys in `STATUS_SYMBOLS` in the page script (Deep focus ⚔, Available ✦, In meetings ♜, Researching ☉, Wrapping up ⌛, Out today ☾, On leave ⚓, Sick ⚕); null hides it. New status → add it to `STATUS_SYMBOLS` with a symbol.
- No hours chart: Ben rejected the per-day bars.
- "I need X from Baron" → add to `needs`; remove items once resolved (empty list hides the box).
- Scheduled task `baron-weekly-summary` writes the weekly summary every Thursday 17:00 Israel time.

Write log items in plain, boss-readable language. Never invent work or hours.
