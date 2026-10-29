# GMT Shooting Lessons landing page

Single static page (`index.html`) for Give More Training's Saturday Shooting Lessons. The GHL booking calendar ("GMT Shooting Lessons", on `online.gmbm.com`) is the first thing on the page, above the fold on phones.

## Booking calendar

The widget iframe is created by a small inline script right after the calendar placeholder, so it starts loading before the rest of the page. The page's own URL params (`utm_*`, `fbclid`, etc.) are passed through to the widget URL so GHL attributes the booking. `form_embed.js` sizes the iframe; the iframe `id` (`HT7YX93D2NCj6Hrv1fwF_1793294217275`) must match what GHL gave us.

A skeleton shaped like the widget shows until the embed script reveals the iframe, then crossfades (same approach as the MCM page). `--cal-h` on `.calendar-mount` is the widget's first-render height at each breakpoint (760px phone, 805px at 900px+, 817px at 1100px+). If the widget's layout changes, re-measure and update those values so nothing jumps on the swap.

## Images

Everything in `assets/` was exported from the GMT folder in the Posted Social shared drive (Media/Photo, Brand Assets) and from givemoretraining.com (Jeff's career photos, player headshots, league logos). Photos are WebP, sized to about 2x their largest display size.

## Run locally

```bash
python3 -m http.server 8790
```

Then open http://localhost:8790.

## Deploy (Cloudflare Pages)

Connect this repo in Cloudflare Pages: framework preset **None**, build command empty, output directory `/`.
