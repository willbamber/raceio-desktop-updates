# raceio-desktop-updates
RaceIO desktop installers and beta update metadata. Application source remains private.

## Approved desktop updates

Super Admin owns approval. The scheduled publisher reads only approved release metadata,
verifies staged manifest and installer hashes, and advances the signed platform feed.
It never builds or approves releases and never downgrades an existing feed. Testing
installers remain immutable downloads. Windows is skipped until a verified signed
Windows manifest is attached to an approved release.

The workflow checks every five minutes (GitHub scheduling can be delayed). A manual
workflow run can check immediately. `node scripts/promote-approved.cjs --verify-only`
checks without changing the feed. `npm test` covers approval and integrity gates.
