# The Oscar Ledger

A single-page tracker for Academy Award–nominated films.

- **97th Oscars (2025)** and **98th Oscars (2026):** every nominated film across all categories, with winners marked. Mark films as seen, rate them, keep notes, see how many nominees you've seen in each category, and fill out a ballot to compare against the actual winners.
- **99th Oscars (2027):** the predicted contenders, ranked, the four acting races (likely nominees plus the next five), plus a countdown to nominations (January 21, 2027) and the ceremony (March 14, 2027). Swap in the real nominees once they're announced.

- **Website:** https://antass.github.io/oscar-ledger/ (progress saves in your browser)
- **Claude artifact:** https://claude.ai/artifact/BSSFLY7WpwmG8tF9yjQttq (progress saves to your Claude account)

## Files

- `oscar-ledger.html` is the whole app: data, styles and script in one file. Published as a Claude artifact, it saves progress to your Claude account. Opened anywhere else, it saves to the browser's localStorage.
- `.github/workflows/pages.yml` deploys to GitHub Pages on every push to `main`. It wraps `oscar-ledger.html` in the document skeleton (doctype, viewport) that the artifact platform normally adds.

## Data sources

- Nominees and winners: Wikipedia's pages for the 97th and 98th Academy Awards.
- 99th contenders: AwardsWatch Best Picture and Best Director predictions (September 17, 2026) and Gold Derby odds (October 2026). These are predictions, not nominations.

## Adding a new ceremony

Add a `Fxx` films map and a `Cxx` categories array, then register both in `SEASONS`. Film ids must be unique across ceremonies, because seen and rating state is keyed by film id.
