# Leap POS: one-month social media kit (Facebook, Instagram, LinkedIn)

Calendar: **Monday 12 October to Tuesday 10 November 2026**. Everything here was made from real screens of
the running product (retail only), with demo data. No customers, testimonials, prices, numbers or awards are claimed.

## What is in this folder

| Path | What it is |
|---|---|
| `calendar.md` | The 30-day plan: date, time, platform, format, language, media file(s), full caption, hashtags, WhatsApp link |
| `calendar.csv` | Same plan as a spreadsheet (UTF-8 with BOM, opens cleanly in Excel) |
| `metricool-import.csv` | One row per post in Metricool's bulk-upload column layout (see below) |
| `images/facebook/`, `images/instagram/`, `images/linkedin/` | Finished images, named `<date>-<slug>-<size>.png` (carousels `-01`, `-02`, …; LinkedIn documents also as `-document.pdf`) |
| `videos/instagram/` | Reels / Stories cuts, 1080×1920 (9:16) MP4 (H.264) |
| `videos/facebook/` | Feed cuts, 1080×1350 (4:5) MP4; also usable as Instagram feed videos |
| `videos/linkedin/` | 1920×1080 (16:9) MP4 |
| `raw/` | Raw 2× product screenshots (admin, web POS, desktop POS, customer display, price checker; EN/AR, light/dark) |
| `work/rec/` | Raw 1920×1080 screen recordings (.webm) the videos were cut from |
| `templates/` | HTML/CSS templates (`post.html`, `video/compositor.html`), brand fonts (IBM Plex Sans / Sans Arabic) and the Leap mark |
| `scripts/` | The Playwright scripts that took the screenshots, recorded the flows and rendered everything (re-runnable) |

## WhatsApp call to action

Every post points to WhatsApp click-to-chat with a pre-filled message:

- English: `https://wa.me/96178728894?text=Hello%20Leap%20POS%2C%20I%27d%20like%20to%20know%20more%20and%20book%20a%20demo.`
  → opens a chat with **+961 78 728 894** and the text "Hello Leap POS, I'd like to know more and book a demo."
- Arabic: `https://wa.me/96178728894?text=%D9%85%D8%B1%D8%AD%D8%A8%D8%A7%D9%8B%20Leap%20POS%D8%8C%20%D8%A3%D9%88%D8%AF%20%D9%85%D8%B9%D8%B1%D9%81%D8%A9%20%D8%A7%D9%84%D9%85%D8%B2%D9%8A%D8%AF%20%D9%88%D8%AD%D8%AC%D8%B2%20%D8%B9%D8%B1%D8%B6%20%D8%AA%D8%AC%D8%B1%D9%8A%D8%A8%D9%8A.`
  → "مرحباً Leap POS، أود معرفة المزيد وحجز عرض تجريبي."

Both links were checked by decoding them back to the exact message (the apostrophe is encoded as `%27` so no
platform cuts the link short). Buying = "Message us on WhatsApp to get a demo and a quote"; no prices are published.

**Instagram:** links in captions are not clickable. Put the English link in the bio (or a link-in-bio page with
both EN and AR links) and use the Link sticker on Stories. Captions already say "tap the link in our bio".
**Facebook / LinkedIn:** the link is in the caption and is clickable.

## Sizes

| Platform | Placement | Size | Ratio | Files |
|---|---|---|---|---|
| Instagram | Feed image / carousel slide | 1080×1350 | 4:5 | `images/instagram/*-1080x1350.png` |
| Instagram | Story / Reel cover | 1080×1920 | 9:16 | `images/instagram/*-1080x1920.png` |
| Instagram | Reel video | 1080×1920 | 9:16 | `videos/instagram/*.mp4` |
| Facebook | Feed image / multi-image | 1080×1350 | 4:5 | `images/facebook/*-1080x1350.png` |
| Facebook | Landscape / link image (alternative) | 1200×630 | 1.91:1 | `images/facebook/*-1200x630.png` |
| Facebook | Story | 1080×1920 | 9:16 | `images/facebook/*-1080x1920.png` |
| Facebook | Feed video | 1080×1350 | 4:5 | `videos/facebook/*.mp4` |
| LinkedIn | Single image | 1200×627 | 1.91:1 | `images/linkedin/*-1200x627.png` |
| LinkedIn | Square image (alternative) | 1200×1200 | 1:1 | `images/linkedin/*-1200x1200.png` |
| LinkedIn | Document (carousel) | 1080×1350 pages | 4:5 | `images/linkedin/*-document.pdf` (+ the PNG pages) |
| LinkedIn | Video | 1920×1080 | 16:9 | `videos/linkedin/*.mp4` |

Design rules used: Leap's own colours from `packages/ui/src/tokens.ts` (navy `#0E1A2E`, primary `#065ACC`,
brand mark `#2F6BFF`), IBM Plex Sans / IBM Plex Sans Arabic (the product's fonts), one short bold headline, small
"Leap POS" logo, a green "Chat with us on WhatsApp" pill. Headline + sub-line stay well under ~20% of the area and
pass WCAG AA contrast (white on navy, navy on light grey, white on `#065ACC` and on `#128C4B`). Stories and Reels keep
all text inside the central safe zone (nothing in the top ~250 px or bottom ~340 px). Arabic creatives are fully RTL
and keep numbers left-to-right.

## Videos

Ten real screen flows (recorded with Playwright at 1920×1080, then branded and captioned in a canvas compositor and
encoded to H.264 MP4 in Chrome; ffmpeg is not installed on this machine). Each cut has a headline, numbered on-screen
step captions (for muted viewing), the WhatsApp pill and a 3.5 s end card "Leap POS — chat with us on WhatsApp ·
wa.me/96178728894".

| Key | Flow | Length (approx.) |
|---|---|---|
| a | PIN sign-in → scan 3 items → 10% discount → cash with change → receipt | 34 s |
| b | Same kind of sale in Doha (QAR), then Beirut (USD + LBP mixed payment, change in both) | 45 s |
| c | Online → internet cut → offline sale "Waiting to sync" → back online → "Synced" | 29 s |
| d | Customer display updating live above the till | 24 s |
| e | Price checker: two scans | 19 s |
| f | Admin: home → owner dashboard → reports → country overview → daily trend by country | 40 s |
| g | Admin: stock → low stock & reorder → purchase orders → receiving | 26 s |
| h | Admin: roles & permissions → approval limits → approvals log | 32 s |
| i | Web POS in a browser and the desktop app, the same sale (stacked on 9:16/4:5, side by side on 16:9) | 21 s |
| j | Arabic RTL dark-mode tour: admin, then the till (Arabic captions) | 44 s |

Durations include the 3.5 s end card. Files are named `<key>-<slug>-<size>.mp4` in each platform folder.

## How to publish

1. Host the `images/` and `videos/` folders somewhere that serves direct file URLs (a public bucket, CDN, or a
   Google Drive / Dropbox share link in the format Metricool asks for).
2. In `metricool-import.csv` replace every `{{BASE_URL}}` with that host (for example
   `https://cdn.example.com/leap-pos-marketing`). Metricool only accepts direct links to images and videos.
3. In Metricool: Planning → calendar options → **Import CSV**. Choose date format `YYYY-MM-DD`, time `HH:MM:SS`,
   and make sure the brand time zone is **Asia/Beirut**. Every row is imported as a **draft** (`Draft = TRUE`) so
   the team reviews it before it goes live; switch to `FALSE` to schedule directly. Metricool recommends at most 50
   posts per file, so the same rows are also split into `metricool-import-part1-oct12-oct25.csv` and
   `metricool-import-part2-oct26-nov10.csv`; import those two instead of the full file.
4. Check each draft in the Metricool preview: Instagram carousels (up to 10 images), Reels (`Instagram Post Type =
   REEL`, shown on the feed), Stories (`STORY`; add the WhatsApp Link sticker in the app), Facebook stories, and
   LinkedIn documents (the PDF is in `Picture Url 1` with a `Document title`; if your Metricool plan does not accept
   PDFs for LinkedIn, upload the PDF natively on LinkedIn, or post the PNG pages with "LinkedIn Images as Carousel").
5. Where both a portrait and a landscape/square file exist, the calendar lists the primary one first; the other is an
   alternative for boosting or reposting.

Column layout reference: Metricool help centre, "How to schedule posts in batch with a CSV file in Metricool"
(https://help.metricool.com/en/article/how-to-schedule-posts-in-batch-with-a-csv-file-in-metricool-3wihqx/).

## Posting-time assumptions

No account analytics yet, so times follow common patterns for Lebanon and the Gulf (adjust after 2–3 weeks):
Facebook 19:30 weekdays / 12:30 Saturday, Instagram 20:30 weekdays / 13:00 Saturday, LinkedIn 09:30–10:00
Monday to Thursday only, Stories Friday 18:00. All times are Beirut time; Lebanon moves from UTC+3 to UTC+2 on
25 October while Riyadh/Doha stay UTC+3 and Dubai UTC+4.

## Honesty notes

Every feature mentioned was seen working in the product or is documented in `docs/` of the Leap POS repository:
offline selling with exactly-once sync, Lebanon/UAE/KSA/Qatar entities with their own currency and tax
(VAT 11% / 5% / 15%; Qatar receipts carry no VAT), USD + LBP mixed payments, discounts with manager-PIN approval,
blind cash count and Z-report, customer display, price checker, receipts by print/WhatsApp/A4, stock, reorder,
purchase orders and receiving, 60+ reports (63 in the demo), roles and approvals, web POS and desktop app,
English/Arabic, light/dark. Nothing about e-invoicing (ZATCA etc.), pricing, customers or certifications is claimed.
Screens show demo data only ("Leap Market", demo cashiers), no real personal data.
