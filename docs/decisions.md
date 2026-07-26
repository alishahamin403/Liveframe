# Decisions

## Resolved (2026-07-20)

| # | Decision | Choice | Notes |
|---|----------|--------|-------|
| 1 | Camera approach | **Custom in-browser viewfinder** | Live viewfinder, big shutter, shot counter, flash. Falls back to native `<input capture>` if `getUserMedia` is blocked. Chosen for the disposable-camera feel + brand control. |
| 2 | Moderation default | **Instant + auto safety filter** | Photo hits the wall in seconds after an automated NSFW/content check; host can one-tap remove. Approve-before-display offered as a per-event opt-in (corporate/kids events). |
| 5 | Retake | **No retake — true disposable** | Tapping the shutter commits and sends. Guests can view their roll but not undo. Preserves the scarcity mechanic. |
| 6 | Guest identity | **Optional first name / initial** | Skippable; anonymous by default if skipped. Enables "📸 from Alex" attribution without accounts. |

## Still open

| # | Decision | Options | Status |
|---|----------|---------|--------|
| 3 | Pricing model | Per-event · Venue subscription · White-label | Open |
| 4 | Data residency | AWS ca-central-1 · Cloudflare R2 Canada · Hetzner CA | Open |

## Product flow (locked)
Three surfaces:
- **Host** — create event → configure (shots/moderation/window) → get QR + Wall URL + dashboard → moderate live (hide/feature) → download gallery + set retention.
- **Guest** — scan QR → one-screen onboarding (welcome + 1-tap consent + optional name) → custom viewfinder, 20 shots, no retake, "film develop" reveal → each shot lands on the wall → out of film → view gallery on own phone.
- **Wall** (venue TV) — attract state (giant QR + "Scan to join") → live: newest photo hero spotlight then flows into a mosaic; QR stays in corner; hidden photos vanish instantly.

## Notes
- Shot-limit enforcement lives on device (no login) — acceptable for Phase 0, document in T&C.
- PIPEDA consent wording needed before first pilot (one-tap consent at guest entry + host T&C at setup).
