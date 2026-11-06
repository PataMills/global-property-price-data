# Methodology — Untera Global Property Price Datasets (June 2026)

## Source

Untera aggregates live property listings from 190+ portals, agencies, and partner
feeds across 70+ countries. The figures in these datasets summarize for-sale
listing records in Untera's database, recorded as separate **June 2026** captures
and frozen for citation stability.

## Capture dates and cohort clarification (2026-11-06)

The retained application source records the home-price snapshot as captured on
**2026-06-24** and the price-per-m² snapshot as re-captured on **2026-06-29**.
Both index CSVs published here are byte-identical to those historical application CSVs.
"June 2026" is an edition label, not evidence of a simultaneous extraction.

The contemporaneous query definitions differ:

- **Home-price index:** `publicationStatus='ready'`, `transactionType='sale'`,
  `type='residential'`, `normalizedPriceUsd` from **8,000 through 15,000,000**
  inclusive, `dataConfidence>=70`, and `sourceId` other than `finn_no`.
  Countries require at least **10,000 qualifying rows** and a two-uppercase-letter
  country code. The query has no explicit `status='active'` condition.
- **Price-per-m² index:** `status='active'`, `publicationStatus='ready'`,
  `transactionType='sale'`, `normalizedPriceUsd>1000`, recorded `sqm` from
  **15 through 10,000** inclusive, price per m² from **USD 50 through 30,000**
  inclusive, `sourceId` other than `imoti_bg`, and a nonempty country.
  Countries require at least **300 qualifying rows** and a median recorded area
  of at least **45 m²**. This June query has no residential-type or
  `dataConfidence>=70` condition. The snapshot source also records the Netherlands
  and Australia as intentionally excluded from this edition.

The price-per-m² sample is therefore **not directly nested within the home-price
sample**. Different recorded dates and eligibility rules mean one count can be
larger or smaller than the other. Their ratio must not be used as the share of
the home-price sample with floor-area information.

This is a reconstruction from retained source code, not a query-execution receipt.
The recorded capture dates do not supply exact extraction times or timezones.
Without the historical row-level inputs and execution records, this review cannot
apportion a country's count difference among timing and filter effects, establish
the amount of non-residential inclusion, or independently validate the frozen
figures or historical de-duplication.

Source-review references: home-price snapshot and query at application commit
`edf6d811c1c6dd42386f68204d08959bc0cda5ec`; price-per-m² snapshot and query at
`d55aebcc67b5cef43935598254fa6efa4fa4ed0a`. These application implementation
records are not included in this public bundle.

## How each measure is computed

**Median home price (`median_home_price_usd`).**
The recorded query reports the country **median** of normalized USD asking prices
for residential for-sale records, using the home-price eligibility rules above.
The median (not the mean) is used so a handful of ultra-prime listings don't distort
the figure.

**Price per square meter (`usd_per_sqm`).**
The recorded query computes normalized USD asking price ÷ recorded area for each
qualifying listing and reports the country **median**, using the bounds above.
Recorded area is not independently confirmed to be interior floor area. The
snapshot's source notes warn that some sources may report plot or land area
instead, which can lower the per-m² figure. Sample counts must be interpreted
separately from the home-price index, as explained above.

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

The datasets are frozen June-2026 captures. This documentation clarification does
not change the CSVs, the archived ZIP, or any separately published DOI edition.
Untera publishes updated figures periodically; for the live underlying coverage and per-source breakdown see
https://untera.io/data-quality. For questions about derivation or to request a custom
cut, contact William Marsh, Founder of Untera, via https://untera.io/press.
