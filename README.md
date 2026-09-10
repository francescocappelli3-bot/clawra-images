# clawra-images

Public asset archive for Clawra AI. The app links files from here by commit
sha (raw.githubusercontent.com/francescocappelli3-bot/clawra-images/<sha>/...),
so a published URL never changes meaning: replace a file by publishing a new
commit and pointing the app at the new sha.

Layout

- `step*_*.webp`, `misc_*` : funnel option cards and the creation-wait video
  (frontend/src/data/onboarding-options.ts).
- `characters/<slug>/cover.<jpg|png|webp>` : public catalog cover (SFW only,
  it is also the Open Graph image of the character page).
- `characters/<slug>/cover-400.webp`, `cover-800.webp` : thumbnails used by
  the cards and the character page hero (frontend/src/lib/thumb-url.ts).

Publishing covers: `scripts/publish-catalog-images.mjs` in the clawra-ai repo
writes the files, pushes, verifies every URL, then updates
`characters.card_image_url`. Nothing here should be edited by hand.
