# Progress board

`index.html` is Ben's progress board, shown to his boss Baron. It's hosted on GitHub Pages:
https://doublenang69.github.io/progress-board/ (repo: Doublenang69/progress-board, branch `main`, public).

Only edit the JSON in `<script id="data">` at the top of `index.html`, then commit and `git push`. The site updates within a minute or two. (The old claude.ai Artifact copy is retired; don't publish there.)

- "Change what I'm working on" → update `now.title` (`now.since` is kept in the data but no longer shown).
- The greeting has a fixed two-line height so the page doesn't shift; keep new greetings about as short as the existing ones.
- Black background is a placeholder; a live wallpaper is planned.
- "Log today" → add `{ "date": "YYYY-MM-DD", "hours": <number or null>, "done": ["...", "..."] }` to `logs`. Same date again → merge into that entry.
- "Weekly report" / after a new log → set `reports["<Sunday YYYY-MM-DD>"]` = an array of 3-5 dot points combining that week's logs. Weeks run Sunday–Saturday (Israel). Total hours are computed by the page.
- "Set status: X" → `status`, one of the keys in `STATUS_SYMBOLS` in the page script (Deep focus ⚔, Available ✦, In meetings ♜, Researching ☉, Wrapping up ⌛, Out today ☾, On leave ⚓, Sick ⚕); null hides it. New status → add it to `STATUS_SYMBOLS` with a symbol. Shown as "Ben is: <symbol> <status>" between the two top boxes.
- "I need X from Baron" → add to `needs`; remove items once resolved (empty list hides the box).
- No hours chart: Ben rejected the per-day bars.
- Scheduled task `baron-weekly-summary` writes the weekly summary every Thursday 17:00 Israel time.

Write log items in plain, boss-readable language. Never invent work or hours. The repo is public, so never put anything confidential in it.
