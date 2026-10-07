# Marketing agents — shared brief (Oct 2026)

Product: **Leap POS** (by Leapcoder) — retail point of sale: desktop POS (Electron, counter PC with
receipt printer and drawer), **web POS** (same till in Chrome/Edge, installable, offline, browser or
silent USB printing), admin web app, customer display, price checker. Lebanon (USD+LBP, VAT 11%),
UAE (AED 5%), KSA (SAR 15%, scannable ZATCA e-invoice QR on receipts), Qatar (QAR, no VAT).
English/Arabic, light/dark. **Never show or mention restaurant features.**

## Read first
- `research.md` (checklist: hooks, safe zones top 250/bottom 450/left 80/right 140 on 1080x1920,
  captions, lengths, covers, Google Business takes images in posts) — follow it.
- `calendar.md` — the 96 posts ALREADY scheduled 12 Oct–10 Nov (FB 19:30 / Stories 18:00, IG 20:30,
  TikTok 21:00, Google 12:00 Beirut). Do not duplicate their topics/media in the same week.
- `README.md`, `scripts/`, `templates/` — reuse the existing render (HTML→PNG via Playwright) and
  recording/encoding pipeline (Playwright video + Chrome MP4 H.264; ffmpeg is NOT installed).
- `raw/` — 70 existing real screenshots; reuse before capturing new ones.

## Environments (do not start/stop servers yourself unless your brief says so)
- Web POS http://localhost:5181 → API http://localhost:3700 (DB `leap_web`). Owner `owner` /
  `ChangeMe123!`, PINs owner 1234, cashier 3456 (HAM), doh-cashier 7777. Use only terminals named
  "Marketing till" (codes MKT1/MKT2) or create your own "Marketing till N"; never "* web till".
- Admin for screenshots: http://localhost:5173 (client demo, API :3500) — READ-ONLY browsing.
- If :3700 or :5173 is down, poll `curl localhost:3700/v1/health` every 30 s for up to 20 min (the
  ops agent is restarting them); meanwhile work with `raw/`.
- Never touch DBs `leap`/`leap_demo` data, never pair demo terminals, never change user prefs
  permanently (reset en/system). Kill only your own processes. One browser at a time per agent.
- `export PATH=~/.nvm/versions/node/v24.21.0/bin:$PATH`. Never pnpm install. No git commits —
  the coordinator commits and pushes the marketing repo.

## Output contract (each agent writes ONLY its own files)
- Media: `images/<platform>/<YYYY-MM-DD>-<slug>-<WxH>.png`, `videos/<platform>/<slug>-<WxH>.mp4`,
  `images/google/<YYYY-MM-DD>-<slug>.png`. Use your own slugs so names never collide.
- Schedule part: `schedule/part-<agent>.json` — array of
  `{ "date": "2026-10-08T19:30:00+03:00", "platform": "facebook|instagram|tiktok|gmb",
     "type": "POST|REEL|STORY|publication", "media": ["images/..."], "text": "...",
     "tiktokTitle": "≤90 chars (TikTok only)", "lang": "en|ar", "topic": "..." }`
  Media paths are repo-relative (coordinator prefixes https://leapcoder-co.github.io/leap-pos-marketing/).
  Offsets: +03:00 until 24 Oct, +02:00 from 25 Oct.
- Captions: hook line, 3–6 concrete feature bullets (✅ FB, ▪️ IG/TikTok, ✔️ Arabic), who it's for,
  CTA. FB + Google: `https://wa.me/96178728894?text=Hello%20Leap%20POS%2C%20I%27d%20like%20to%20know%20more%20and%20book%20a%20demo.`
  (Arabic text param: `%D9%85%D8%B1%D8%AD%D8%A8%D8%A7%D9%8B%20Leap%20POS%D8%8C%20%D8%A3%D9%88%D8%AF%20%D9%85%D8%B9%D8%B1%D9%81%D8%A9%20%D8%A7%D9%84%D9%85%D8%B2%D9%8A%D8%AF%20%D9%88%D8%AD%D8%AC%D8%B2%20%D8%B9%D8%B1%D8%B6%20%D8%AA%D8%AC%D8%B1%D9%8A%D8%A8%D9%8A.`).
  IG + TikTok: "👉 Message us on WhatsApp for a demo and a quote: +961 78 728 894 (link in bio)."
  Google: no hashtags. IG/TikTok 8–15 hashtags. About 1/3 Arabic.
- Every post has media (IG/TikTok/FB Reels video 1080x1920; FB/IG feed 1080x1350; Google image).
- Spacing: per platform ≥ 4 h between posts, and never at the same time as an existing post.
  Use: FB 13:00 (new daily slot) / 19:30 only if that day is free; IG 14:00 / 20:30 if free;
  TikTok 17:00 / 21:00 if free; Google 10:00; Stories 18:00 only if free.
- STRICT HONESTY: only real features (check /Volumes/EXT/Projects/leap-pos/docs/architecture/00-index.md
  and docs/guides). No prices, customers, testimonials, numbers, awards, discounts.
- LOOK at every image you produce (Read tool) and a few frames of each video; redo broken ones.

## Report (≤150 words)
Files produced, the part JSON path, post count per platform, anything you could not do.
