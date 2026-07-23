# Abby Rose Studio — website guide

## What's in here

```
index.html           → the whole public website (one page)
admin.html           → YOUR private studio tools: add paintings, build
                       early-access emails, open your analytics dashboards.
                       Not linked from anywhere public.
data/paintings.json  → every painting. Edit this to add/update/mark sold.
data/content.json    → every piece of TEXT on the site. Edit wording here.
assets/              → photos + logo, already web-sized
```

## Publishing an update (same every time)

1. Open GitHub Desktop
2. Make your change (edit a file, add a photo to `assets/`)
3. Type a short summary → **Commit to main** → **Push origin**
4. Live in ~1 minute

## Editing text or paintings without touching code

- **Any wording on the site** → `data/content.json`. Change words between
  the quote marks. Keep quote marks and commas.
- **Paintings** → `data/paintings.json`, or use the generator at
  `/admin.html` on your live site and paste what it gives you.
- Both can be edited on github.com directly: open the file → pencil icon
  → edit → Commit changes. No GitHub Desktop needed for small text edits.

## One-time setup (3 free accounts, ~20 min total)

### 1. Contact form — Formspree
1. formspree.io → free account **using awest125@gmail.com**
2. New form → copy the endpoint (looks like `https://formspree.io/f/abcd1234`)
3. In `index.html`, replace `YOUR_FORM_ID` (one place)
4. **Redirecting later:** when abbyrosestudio@gmail.com exists, change the
   destination email inside Formspree's settings. The website never changes.

### 2. Early-access list — Buttondown
1. buttondown.email → free account (free up to 100 subscribers)
2. In `index.html`, replace `YOUR-USERNAME` (two places, same form)
3. To send an early-access email: build it in `/admin.html` → copy →
   Buttondown → New email → paste → send. Unsubscribe links and the
   subscriber list are handled for you (this matters — Australian spam law
   requires a working unsubscribe on marketing email).
4. **Sender address:** set in Buttondown settings; swap to the studio Gmail
   later without touching the site.

### 3. Analytics — GoatCounter
1. goatcounter.com → free account → pick a site code (e.g. `abbyrosestudio`)
2. In `index.html`, replace `YOURCODE` (one place, near the top)
3. In `admin.html`, replace `YOURCODE` in the Analytics tab link
4. Your dashboard: `https://YOURCODE.goatcounter.com` — shows visitors,
   and every listing click / lightbox open / enquire click as named events.

## Payments (when you're ready)

Stripe Payment Links: stripe.com → free account → Payment links → New →
set price → copy link. Then in `data/paintings.json` change the available
painting's `"price"` line — or keep using the Enquire button, which many
artists prefer for originals so buyers talk to you first.

## About the image protection — honest note

The site blocks right-click-save, drag-to-save, and long-press-save on
every artwork photo, and the photos themselves are uploaded at screen
resolution only (nowhere near print quality). This stops casual copying.

But nothing can stop a determined person from screenshotting a screen —
that's true of every art website including major galleries. Your real
protections are: web-res-only images (already done), your visible
signature on the canvas, and your copyright line in the footer. If you
ever find a stolen image in use, you own the copyright and can demand a
takedown.

## Your admin page

`yoursite.com/admin.html` — bookmark it. It has no password (GitHub Pages
can't do passwords), it's just unlisted: nothing on the public site links
to it. It also contains nothing private — just form tools that generate
text for you to paste. All the genuinely private things (subscriber list,
messages, analytics) live behind your Formspree/Buttondown/GoatCounter
logins.

## Custom domain (when it arrives)

1. Registrar DNS → add a CNAME record pointing to `awest125-sketch.github.io`
2. Repo → Add file → name it exactly `CNAME` (no extension) → contents:
   your domain, e.g. `abbyrosestudio.com.au` → commit
3. Repo Settings → Pages → enter the domain → Save → tick Enforce HTTPS
   once it's offered (can take a few hours)
