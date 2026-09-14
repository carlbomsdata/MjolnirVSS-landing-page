# MjolnirVSS landing page

Static landing page for [MjolnirVSS](https://github.com/carlbomsdata/MjolnirVSS), a portable bare metal backup and recovery tool for Windows 10, Windows 11 and Windows Server.

The page is deliberately plain about what has and has not been proven: every figure on it was measured in a virtual machine, and no real computer has been restored from a MjolnirVSS backup. If a claim on the page cannot be traced to a measurement, it should not be on the page.

## Local preview

No build step or dependencies are required. Open `index.html` directly, or serve the repository with any static HTTP server.

For example:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

## Screenshots

Everything in `assets/screenshots` is a real screenshot of the application running in a virtual machine, not a mockup. Replace them when the interface changes; a screenshot of an older build is worse than none, because it advertises bugs that have since been fixed.

## Hosting

Plain HTML, CSS and JavaScript, suitable for GitHub Pages or any static host. There is no `CNAME`, so it serves from the repository's own Pages address until a domain is pointed at it.
