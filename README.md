# groSINT v2.0 — Advanced iPhone OSINT PWA

## Included modules
- Phone: international formatting, country/calling code, possible/valid numbering-plan check, number type (via libphonenumber-js loaded from jsDelivr), public caller-report search links.
- IP: approximate public IP geolocation, ISP/organization/ASN, public reputation links.
- Domain: DNS A/AAAA/MX/NS/TXT/CNAME lookups, RDAP domain data, certificate-transparency and URL reputation links.
- Email: syntax and MX checks; manual links to breach/account research providers.
- Username: multi-site public search link generation.
- Image: local image dimensions and SHA-256; manual reverse-image-search links.
- Evidence: local case notebook, timestamped entries, optional source URLs and local file SHA-256, JSON and CSV export.

## Publish free with GitHub Pages
1. Create a GitHub account and a new repository named `grosint`.
2. Upload `index.html`, `manifest.webmanifest`, and `sw.js` to the repository root.
3. Open **Settings → Pages**.
4. Select **Deploy from a branch**, branch `main`, folder `/ (root)`, then Save.
5. Wait for the HTTPS Pages URL to appear.
6. On iPhone, open that URL in Safari.
7. Tap **Share → Add to Home Screen → Add**.

This is an installable Progressive Web App (PWA), not a native App Store binary. A native iOS app requires an Xcode/Swift build and Apple signing/distribution.

## APIs and privacy
- Phone metadata: libphonenumber-js is downloaded from jsDelivr when the phone module is used. It validates numbering-plan structure, not whether a line is active or who owns it.
- IP geolocation: ipwho.is. Approximate network location only.
- DNS: Google Public DNS-over-HTTPS.
- RDAP: rdap.org public domain registry data.
- No API keys are required for these basic lookups.
- Email breach checks are not automated; providers are opened manually. Never expose private API keys in frontend JavaScript.
- Image files are processed in-browser; groSINT does not upload them.
- Evidence entries are stored in localStorage on that device/browser. Export backups. Clearing website data may erase entries.
- Public lookups need an internet connection; the app shell may be cached for offline loading.
- Cross-origin APIs can change rate limits, availability, or browser access. If an API fails, use the manual provider links.

## Responsible use
Use lawful public sources and investigate only matters you are authorized to examine. Do not use the app to harass, dox, threaten, stalk, break into accounts, or locate a private person. IP locations are approximate and can represent VPNs, proxies, mobile gateways, or ISP infrastructure. Caller-ID and breach data can be incomplete or wrong. Preserve original evidence separately; this is not a certified chain-of-custody system.
