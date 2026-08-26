# BlockFuture

Business website for **BlockFuture** — a human-first AI integration consultancy.

> AI that keeps your human soul intact.

## Pages

| File | URL |
|---|---|
| `index.html` | `/` — homepage (hero, services, manifesto, process) |
| `about/index.html` | `/about/` — beliefs and team |
| `blog/index.html` | `/blog/` — featured post and post grid |
| `contact/index.html` | `/contact/` — contact form |
| `support.js` | Design Component runtime (generated — do not edit) |
| `agentiktok/tos/` | `/agentiktok/tos` — AgentikTok Terms of Service |
| `agentiktok/privacy/` | `/agentiktok/privacy` — AgentikTok Privacy Policy |

## How it works

Each page is a self-contained `.dc.html` Design Component: the markup lives in an
`<x-dc>` template block and the page data/logic in a `<script data-dc-script>`
block at the bottom of the same file. `support.js` loads React from a CDN and
renders the template at runtime — there is no build step.

To edit content (services, posts, team bios, stats), change the data objects in
the `renderVals()` method at the bottom of the relevant page file.

## Local development

Serve the folder with any static file server (the runtime fetches sibling files,
so opening via `file://` won't work):

```sh
python3 -m http.server 8000
# then open http://localhost:8000/
```

## Deployment

The site is fully static — deploy anywhere that serves files (GitHub Pages,
Netlify, Cloudflare Pages). For GitHub Pages: repo Settings → Pages → deploy
from the `main` branch, root folder.

Note: the contact form is front-end only (it shows a confirmation but doesn't
send anywhere yet). Wire it to a form backend (Formspree, Basin, a serverless
function) before launch.
