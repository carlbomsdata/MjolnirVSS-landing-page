# MjolnirVSS landing page

Static marketing page for [MjolnirVSS](https://github.com/carlbomsdata/MjolnirVSS),
portable bare metal backup and recovery for Windows.

Published at <https://carlbomsdata.github.io/MjolnirVSS-landing-page/>.

## Rules for the content

The MjolnirVSS repository is the source of truth. If a claim on this page cannot
be traced to something measured and written down there, it does not belong here.

- **Never soften the test status.** Everything end to end was done in virtual
  machines. Complete bare metal recovery has never been performed on physical
  hardware, and the page says so in the hero note, the proof section and the
  status section.
- **Four states, kept distinct:** implemented, verified on physical Windows
  hardware (read only), tested end to end in a VM, not yet proven.
- **No invented proof.** No testimonials, user counts, uptime figures,
  benchmarks, reviews, certifications or logos that do not exist.
- **No download button** until there is a binary release. The single primary
  call to action is *View on GitHub*.
- Absolute safety claims are out. State the specific behaviour instead, for
  example that the backup is declared `VSS_BT_COPY`, rather than "safe to run on
  a server".

## Structure

| File | Purpose |
|---|---|
| `index.html` | The whole page: hero, trust strip, benefits, how it works, product, proof, safety, status, design, FAQ, call to action |
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
screenshot of an older build is worse than none, because it advertises bugs that
have since been fixed.

| File here | Source in MjolnirVSS |
|---|---|
| `app-backup.png` | `docs/images/main-window.png` |
| `recovery-choose-disk.png` | `docs/images/recovery-choose-disk.png` |
| `recovery-confirm.png` | `docs/images/recovery-confirm-erase.png` |
| `recovery-finished.png` | `docs/images/recovery-finished.png` |

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
