# Methodology — Untera Global Property Price Datasets (June 2026)

## Source

Untera aggregates live property listings from 190+ portals, agencies, and partner
feeds across 70+ countries. The figures in these datasets are derived from the
**live for-sale listings** in Untera's database as of **June 2026**, then frozen for
citation stability.

## How each measure is computed

**Median home price (`median_home_price_usd`).**
For each country we take the set of live for-sale residential listings with a valid
price, convert every price to USD at the prevailing exchange rate, and report the
**median**. The median (not the mean) is used so a handful of ultra-prime listings
don't distort the figure. Countries are included only when the sample is large enough
to be meaningful.

**Price per square meter (`usd_per_sqm`).**
For listings that publish a usable interior area, we compute price ÷ area for each
listing, convert to USD per m², and report the country **median**. Listings without a
reliable area, or with areas that fail sanity checks, are excluded — which is why the
`listings_sampled` count here is smaller than the home-price sample for some countries.

**What $250k buys (`listings_under_250k`, `median_price_usd`, `cheapest_usd`).**
We count live for-sale listings priced at or below **USD 250,000** per country,
report the median price within that sub-250k set, and record the single cheapest
valid listing. This reflects breadth of affordable supply, not just a single average.

## Currency

All prices are converted to **US dollars** using exchange rates at snapshot time.
Currency movement between the snapshot and your reading date will shift the real-world
equivalents; the USD figures here are fixed to June 2026.

## Sampling and known limitations

- **Asking prices, not transaction prices.** These are list prices, which typically
  sit above final sale prices and vary by market negotiation norms.
- **Listing-based, not census-based.** Coverage reflects what is actively listed
  online in each country, which over-represents urban and higher-liquidity markets and
  under-represents informal or off-market segments.
- **Composition varies by country.** The mix of apartments vs. houses, and of cities
  vs. rural areas, differs between markets and affects cross-country comparison. Use the
  `listings_sampled` column to judge how robust each country's figure is.
- **Small samples flagged.** Some countries appear with low `listings_sampled` values;
  treat those as indicative rather than definitive.
- **De-duplication.** Listings are de-duplicated before aggregation to avoid the same
  property (re-listed across multiple portals) being counted more than once.

## Reproducibility

The datasets are a frozen June-2026 snapshot. Untera publishes updated figures
periodically; for the live underlying coverage and per-source breakdown see
https://untera.io/data-quality. For questions about derivation or to request a custom
cut, contact William Marsh, Founder of Untera, via https://untera.io/press.
