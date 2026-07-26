# LiveFrame

> A live event photo wall for Ontario venues.

Guests scan a QR code, take up to their photo limit, and watch their shots appear on the venue's live wall in real time. No app download. No account. The host walks away with everything.

## Structure

```
LiveFrame/
├── docs/               # PRD, decisions, privacy notes
├── src/
│   ├── frontend/
│   │   ├── guest/      # QR-scan → camera → upload web app
│   │   ├── wall/       # Full-screen live wall for venue TV
│   │   └── host/       # Event setup, moderation, download
│   └── backend/
│       ├── api/        # REST API
│       ├── realtime/   # WebSocket/SSE for live wall updates
│       ├── storage/    # Photo storage (Canadian region)
│       └── moderation/ # Content filtering & host controls
├── infra/terraform/    # Canadian cloud infrastructure
├── design/
│   ├── logos/          # Logo variants (SVG)
│   ├── wireframes/     # UI sketches
│   └── brand/          # Color palette, fonts
└── scripts/            # Dev & deploy helpers
```

## Phase 0 MVP scope
- Host creates event → gets QR code + wall URL
- Guest scans → shoots up to the cap → photos appear on wall
- Host can hide/remove photos, download full gallery
- One venue pilot

## Open decisions
- [ ] Camera approach (native webview vs custom in-browser)
- [ ] Moderation default (hide-after vs approve-before)
- [ ] Pricing model (per-event vs venue subscription)
- [ ] Data residency provider (Canadian S3-compatible)
