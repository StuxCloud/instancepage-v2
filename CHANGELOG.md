# Changelog

All notable changes to instancepage-v2 are documented here.

Since v26.10.23 this project uses [Date Versioning](https://datevers.ing) (`YY.MM.DD`, the UTC release date, with `-1`, `-2`… for later releases the same day); earlier releases used Semantic Versioning.

## v26.10.26

### Security

- CI uses Node.js 24 instead of the end-of-life Node.js 20, which has no fix for the Brotli decoder vulnerability CVE-2026-111497

## v26.10.23-1

### Added

- A Discord link preview: every page except the 404 page carries a `discord:component-embed` in its `<head>` (pre-built JSON, kept under Discord's 3,000-byte limit) showing what this server page is, in Stux.Cloud's colours with its icon. The Open Graph fallback is unchanged
- A full favicon set at the site root: `favicon.ico` (16, 32 and 48 px), `apple-touch-icon.png`, `icon-192.png`, `icon-512.png`, `icon-maskable-512.png` and `site.webmanifest`, all made from Stux.Cloud's own icon, and the matching tags in every page's `<head>`
- `tests/site.sh`, which checks every embed is valid JSON under 3,000 bytes with no stray `$1`, that the 404 page has none, that the favicon files exist at the right sizes, and that every `<head>` carries the tag set
- `.htmlvalidate.json` relaxes `valid-id` so the validator accepts the embed's required `discord:component-embed` id
- The local dev server (`dev-server.sh` / `dev-server.bat`) serves `site.webmanifest` as `application/manifest+json`, as GitHub Pages does

## v26.10.23

### Added

- `tests/version.sh`, which checks that `VERSION.md` is a valid Date Version, a real calendar date not in the future, and the same as the newest entry in this changelog

### Changed

- Switched from Semantic Versioning to [Date Versioning](https://datevers.ing): releases are numbered by their UTC release date as `YY.MM.DD`, with `-1`, `-2`… for later releases the same day. This release follows v2.0.3
- `commit.sh` and `commit.bat` refuse a `VERSION.md` that isn't a valid Date Version or is dated in the future (UTC), and warn when it's dated before today
- `README.md` and `CONTRIBUTING.md` describe Date Versioning and the release steps

## v2.0.3

### Fixed

- The footer's copyright line had a second, hidden copy of the © icon inside its screen-reader text; it's gone, leaving the visible icon and a plain "©" for screen readers. Nothing changes on screen

## v2.0.2

### Changed

- The footer no longer says "Stux.Cloud is operated by Stux Group Ltd."; that belongs on the Imprint, which still says it. The copyright line names Stux.Cloud instead of Stux.Group ("© 2026 Stux.Cloud. All rights reserved.")

## v2.0.1

### Fixed

- The light/dark choice was saved in the browser under `stuxedo-theme`, a name left over from the Stuxedo page this design was built from; it's now `stuxcloud-theme` on every page, and the Cookies Policy names it correctly. Nothing else in this archived design changes

## v2.0.0

### Added

- Archived [StuxCloud/instancepage](https://github.com/StuxCloud/instancepage) at commit `faa842e` (`v1.3.2`), the last state before Stux.Cloud's rebrand from two-tone green to single teal, preserving history up to that point as this repository's own `main` branch

### Changed

- Served from `instancepage-v2.stux.cloud` instead of `instancepage.stux.cloud` (CNAME, canonical URLs, sitemap and robots.txt)
- Logo, icon and favicon now point at the archived green assets under `https://global.media.stux.cloud/v2/` instead of the live Stux.Cloud brand assets, which are now teal
- README and CONTRIBUTING describe this repository as an archive
