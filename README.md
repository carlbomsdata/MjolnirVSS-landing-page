# MjolnirVSS landing page

Static marketing page for [MjolnirVSS](https://github.com/carlbomsdata/MjolnirVSS),
portable bare metal backup and recovery for Windows.

Published at <https://carlbomsdata.github.io/MjolnirVSS-landing-page/>.

## Rules for the content

The MjolnirVSS repository is the source of truth. If a claim on this page cannot
be traced to something measured and written down there, it does not belong here.

- **Say that it is early alpha, once, where it matters**, and keep the exact test
  provenance in the MjolnirVSS repository's own
  [`docs/testing.md`](https://github.com/carlbomsdata/MjolnirVSS/blob/main/docs/testing.md).
  The page is a product page, not a test report: it should not read as though the
  absence of one particular test is the defining fact about the product.
- **No invented proof.** No testimonials, user counts, uptime figures,
  benchmarks, reviews, certifications or logos that do not exist. Every figure on
  the page is traceable to a measurement written down in that repository.
- **The download button points at a real release.** If the releases page is ever
  emptied, the button goes and *View on GitHub* becomes the primary call to
  action again.
- **No competitor claims.** Say what MjolnirVSS does, not what other products
  supposedly want from you.
- Absolute safety claims are out. State the specific behaviour instead, for
  example that the backup is declared `VSS_BT_COPY`, rather than "safe to run on
  a server".

## Structure

| File | Purpose |
|---|---|
| `index.html` | The whole page: hero, trust strip, differentiators, how it works, product, tested, safety, design, FAQ, why the name, call to action |
| `styles.css` | All styling. Dark navy shell, Windows blue accent, light content sections |
| `assets/screenshots/` | Real screenshots of the application. No mockups |
| `robots.txt` | Allows everything |

No framework, no build step and no JavaScript. The page must keep working with
scripting disabled, so the FAQ is built from `<details>` elements rather than a
scripted accordion.

## Screenshots

Everything in `assets/screenshots` is a real screenshot of the application
running in a virtual machine. They are kept byte identical to `docs/images` in
the MjolnirVSS repository; refresh both together when the interface changes. A
screenshot of an older build is worse than none, because it advertises an
interface that no longer exists.

| File here | Source in MjolnirVSS |
|---|---|
| `app-backup.png` | `docs/images/main-window.png` |
| `app-progress.png` | `docs/images/backup-progress.png` |
| `recovery-choose-disk.png` | `docs/images/recovery-choose-disk.png` |
| `recovery-confirm.png` | `docs/images/recovery-confirm-erase.png` |

The recovery screenshots are taken in real Windows PE, booted from media
MjolnirVSS built, and the wizard in them was driven from the keyboard alone.

## Local preview

No dependencies. Open `index.html` directly, or serve the repository:

```bash
python3 -m http.server 8080
```

Then open <http://localhost:8080>.

Before pushing a change, check it at a phone width as well as a desktop one, tab
through the page to confirm focus is visible everywhere, and load it once with
JavaScript disabled.

## Hosting

GitHub Pages from `main`. There is no `CNAME`, so it serves from the
repository's own Pages address until a domain is pointed at it. The canonical
URL and the Open Graph tags in `index.html` have to be updated if that changes.
