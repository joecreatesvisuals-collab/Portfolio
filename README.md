# Joe Schaefer Portfolio

Astro site: landing page, a four-tile workspace (Post, Filmmaker, Colorist, Reel), a grid page per discipline, and About.

## Run it locally

```bash
npm install
npm run dev        # http://localhost:4321
```

## Where things live

| What | File |
| --- | --- |
| Name, email, headline, announcement bar, reel embed, client list | `src/data/site.json` |
| The four tiles and every project | `src/data/projects.json` |
| Stills, loops, logos | `public/media/` (reference them as `/media/your-file.jpg`) |
| Colors and fonts | `src/styles/global.css` |

### Adding a project

Copy any entry in `projects.json` and fill it in:

- `disciplines`: which grid pages it shows on (`post`, `filmmaker`, `colorist`), can be more than one
- `still`: thumbnail image, e.g. `/media/after-the-visitors.jpg`
- `loop`: short muted hover clip, e.g. `/media/after-the-visitors.mp4` (5 to 10 sec, H.264, under ~3MB)
- `embed`: Vimeo/YouTube embed URL for the full piece, e.g. `https://player.vimeo.com/video/123456789`
- `hero: true`: also show it as a file card in the homepage app window (first 6 are used)

Tile hover loops: set `loop` on each discipline in the same file.

## Deploy (Vercel)

1. Push this folder to a new GitHub repo.
2. vercel.com → Add New Project → import the repo → Deploy. Astro is detected automatically.
3. Project → Settings → Domains → add your domain, then paste the DNS records Vercel shows into Squarespace Domains.
4. Update `site` in `astro.config.mjs` to the final domain.

## Still to fill in

- `email` in `site.json`
- `reel.embed` in `site.json`
- Real stills, loops, and embeds per project; replace the `[Grade title]`, `[Client]`, `[Role]` placeholders
- `public/og.png` is the social share image: replace with a 1200x630 frame of your choice
