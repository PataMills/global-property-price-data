# Upload guide — where to publish this bundle (Will / Codex)

Each of these is a passive backlink: the dataset's description page links back to
untera.io and stays live indefinitely. Account creation + the actual upload are your
side (I can't create accounts or submit forms). Paste the description block below into
each platform's description field — it carries the link.

## Targets (in priority order)

1. **Zenodo** — https://zenodo.org/uploads/new
   - Best target: gives a permanent **DOI** and is indexed by Google Dataset Search +
     OpenAIRE. Upload the whole folder (or a zip). Set licence = CC BY 4.0, type =
     Dataset, author = William Marsh (Untera).
   - The DOI badge can then be added to the GitHub repo and the /press page.

2. **GitHub** — new public repo, e.g. `untera/global-property-price-data`
   - The `README.md` renders as the repo home page (links back to untera.io throughout).
   - Add topics: `open-data`, `real-estate`, `housing`, `dataset`.

3. **Kaggle Datasets** — https://www.kaggle.com/datasets (New Dataset)
   - Strong discovery + a "Provenance / source" field — set it to https://untera.io/press.
   - Paste the description block below.

4. **Awesome-Public-Datasets** — open a PR adding a one-line entry under "Housing/Real Estate":
   - `- [Untera Global Property Price Datasets](https://untera.io/press) — Median home prices, price per m², and affordability across 60+ countries (CC BY 4.0).`

5. **Google Dataset Search** — picked up automatically once Zenodo/Kaggle host it
   (they emit the required schema.org/Dataset markup). No separate submission needed.

## Description block to paste (carries the backlink)

> **Untera Global Property Price Datasets — June 2026.** Open, citeable data on what
> homes actually cost around the world: median home prices, median price per square
> meter, and a "what $250,000 buys" affordability measure across 60+ countries.
> Compiled by Untera (https://untera.io) from 190+ international listing sources.
> Free to use with attribution under CC BY 4.0. Full reports and methodology at
> https://untera.io/press.

## Rules (from the launch guide)
- Always set the licence to **CC BY 4.0** and the source/provenance link to
  **https://untera.io** (or /press).
- Don't strip the attribution line — it's the whole point of the backlink.
- After Zenodo issues a DOI, add it to the GitHub README and the /press page.
