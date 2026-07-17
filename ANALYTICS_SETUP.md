# Analytics Setup — 2 steps, ~5 minutes total

## Step 1 — Google Analytics (GA4)

1. Go to https://analytics.google.com → sign in with nexus.network.ai@gmail.com
2. Click **Admin** (gear icon) → **Create Property**
3. Property name: `Orion Property Films`, timezone: your region, currency: USD
4. Platform: **Web** → URL: `nexusnetworkai-jpg.github.io/re-tour-videos`, stream name: `Studio`
5. Copy the **Measurement ID** (format: `G-XXXXXXXXXX`)
6. In both `studio.html` and `index.html`, replace every `G-XXXXXXXXXX` with the real ID (4 occurrences total — 2 per file)
7. Push: `git add -A && git commit -m "wire GA4 measurement ID" && git push`

## Step 2 — Google Search Console (GSC)

1. Go to https://search.google.com/search-console → **Add property**
2. Choose **URL prefix** → enter `https://nexusnetworkai-jpg.github.io/re-tour-videos/`
3. Select **HTML tag** verification method
4. Copy the `content="..."` value from the meta tag shown (looks like `abc123XYZ...`)
5. In both `studio.html` and `index.html`, replace `REPLACE_WITH_GSC_TOKEN` with that value (2 occurrences total)
6. Push: `git add -A && git commit -m "add GSC verification token" && git push`
7. Back in GSC, click **Verify** — it reads the meta tag from the live page and confirms ownership

## After setup

- GA4 dashboard shows live sessions, page views, buy-button clicks, and video plays within 24–48h
- GSC shows search impressions and click-through rates from Google Search within ~2 weeks
- When the custom domain is live, update the GSC property URL and re-verify (takes 2 min)
