# Corrected Dataset Inspection and Baseline

Portfolio adaptation of the project document. Original research observations are retained as dated or undated evidence, as applicable. Final editorial qualifications are reflected in the [executive brief](market-intelligence-brief.md). Private lab URLs and account identifiers are not included.

USB Cable Research Evidence

Corrected dataset inspection, research framing and verified baseline

Nike Nsikak-Nelson | Validation date: 15 September 2026

This document establishes the dataset evidence for a potential USB cable launch pilot in India. The full Kaggle file and the numerical USB baseline have been checked. Current competitor research and a launch recommendation remain pending.

### 1 Dataset identity and coverage

| Measure | Verified result |
| --- | --- |
| Source file | amazon(1).csv; browser download filename for amazon.csv |
| Full dataset | 1,465 rows; 16 columns; 1,351 distinct product IDs |
| Repeated product IDs | 92 IDs appear two or three times; 114 excess rows |
| USB cable subset | 233 rows; 161 distinct product IDs |
| USB repetitions | 50 repeated IDs occupy 122 rows; 72 excess rows |
| Unit of observation | Product listing record with embedded reviewer information; not a transaction or an individual review |

### Geography and dates

All 1,465 product links point to www.amazon.in and both price columns use INR symbols. This establishes Amazon India listing coverage, not manufacturing origin, seller location or buyer location.

Collection date is unconfirmed. There are no date columns. URL qid values decode to 5 January 2023, but neither their precise meaning nor the collection date is established by the file. Prices and ratings must not be labelled current.

### Source reference

Karkavelrajaj, Amazon Sales Dataset, Kaggle: https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset

The original CSV is retained unchanged. The name suffix “(1)” is not treated as evidence of a new dataset version. The validation date above is not a collection or download date.

## 2 Columns and data quality

| Column | Meaning |
| --- | --- |
| product_id | Product identifier used for distinct counts |
| product_name | Listing title |
| category | Pipe-separated category hierarchy |
| discounted_price | Recorded selling-price field, in INR |
| actual_price | Recorded reference/list-price field, in INR |
| discount_percentage | Advertised percentage discount |
| rating | Product star rating; one invalid value |
| rating_count | Number of ratings; two missing values |
| about_product | Product description and advertised feature text |
| user_id | Embedded reviewer identifiers |
| user_name | Embedded reviewer names |
| review_id | Embedded review identifiers |
| review_title | Embedded review titles; boundaries may be ambiguous |
| review_content | Embedded review text; boundaries are ambiguous |
| img_link | Image URL |
| product_link | Product URL |

### Numeric handling

Remove ₹, comma separators and percent symbols as appropriate, then parse numbers. Preserve missing or invalid values as unavailable, never zero. In the full dataset, rating has 1,464 valid values and rating_count has 1,463. The other three numeric fields each have 1,465 valid values.

### Review parsing limitation

Category paths use pipes. Reviewer IDs and review IDs use commas, but natural commas inside names, titles and review prose prevent reliable review-level parsing. Equal fragment counts do not prove correct alignment. Use review text only for carefully attributed qualitative observations; do not calculate per-review sentiment rates from naive comma splitting.

## 3 Categories and duplicate conflicts

| Top-level category | Rows | Distinct products |
| --- | --- | --- |
| Electronics | 526 | 490 |
| Computers&Accessories | 453 | 375 |
| Home&Kitchen | 448 | 448 |
| OfficeProducts | 31 | 31 |
| MusicalInstruments | 2 | 2 |
| HomeImprovement | 2 | 2 |
| Car&Motorbike | 1 | 1 |
| Health&PersonalCare | 1 | 1 |
| Toys&Games | 1 | 1 |
| Total | 1,465 | 1,351 |

There are 211 distinct full category paths. No product ID crosses top-level categories; both totals reconcile. A within-category distinct count cannot exceed its row count.

### Price conflicts

| Product ID | Conflicting field | Observed values |
| --- | --- | --- |
| B096MSW6CT | actual_price | ₹1,899 / ₹999; selling price stays ₹199 |
| B0B5B6PQCT | discounted_price | ₹1,999 / ₹1,799 |
| B0B5LVS732 | discounted_price | ₹1,898 / ₹1,999 |
| B09MT84WV5 | discounted_price | ₹1,149 / ₹1,059 |

Only B096MSW6CT is a USB cable. Its zero-based source indices are 2, 379 and 623. Its calculated discounts are (1,899 − 199) / 1,899 × 100 = 89.52% and (999 − 199) / 999 × 100 = 80.08%, which round to the stated 90% and 80%. The file does not establish which reference price is preferable.

### Reconciliation of repeated IDs

Of 92 repeated IDs, 31 have differing rating counts, with within-product differences of 1–13. Two IDs overlap the four price-conflict IDs. Therefore 4 + 31 − 2 = 33 IDs have either conflict; 59 have neither. Those 59 agree on title, category and all five numeric fields, but differ in other fields. The reason records repeat is unconfirmed.

## 4 Research framing

### Business decision and objective

Should a hypothetical online retailer proceed to a small USB cable launch pilot in India, and what product specification and positioning should it test? Combine the undated Amazon India listing sample with current external evidence to assess competing offers, pricing, customer concerns and gaps. Deferring the pilot is an acceptable recommendation.

| Scope | Included | Excluded |
| --- | --- | --- |
| Products | USB charging and data cables sold online in India | Chargers, power banks and unrelated electronics |
| Attributes | Connector endpoints, stated power/data capability, length, pack size, listing price, ratings and warranty information | Unverified performance or safety claims |
| Competitors | Three to five relevant brands with verified current offers | Exhaustive catalog or brand census |
| Timeframe | Undated dataset; external research prioritizes the preceding 12 months | Price trends inferred by comparing unmatched historical and current products |
| Decision limits | Conditional pilot recommendation and validation steps | Sales, profit, market-size or market-share estimates from this sample |

### Constraints and success criteria

Research allowance is limited but the number of available hours has not been supplied. Use publicly accessible sources. No launch budget, costs or transaction data are available. Success means three to five supported insights, a confidence assessment for each, at least two explicit non-conclusions and practical next steps.

### Research approach and status

Completed: AI-assisted dataset inspection, framing and baseline in QuickSuite, followed by independent CSV verification. The original file is the project knowledge source; this supporting document records methods, corrections and limitations.

Planned: use Quick Research to compare current offers and investigate customer concerns; use Quick Chat and the agent to refine questions and synthesize evidence. Prioritize comparable competitor products first, decision-relevant customer signals second, and additional investigation only for gaps that could change the recommendation. Organize source outputs and final deliverables in the Space.

External research, the Market Analysis, insight-level confidence evaluation and final Market Intelligence Brief are not yet complete. The provided assignment template remains the final submission framework.

## 5 USB cable price baseline

### Filter and calculation method

Use exact category equality: Computers&Accessories|Accessories&Peripherals|Cables&Accessories|Cables|USBCables

The filter produces 233 rows and 161 distinct product IDs. Retain the first occurrence in original file order for each product_id. This is a reproducible rule, not evidence of recency or accuracy. Repeat calculations keeping the last occurrence to assess sensitivity. These are unweighted product-level statistics, not transaction or rating-count-weighted measures.

| Discounted listing price | Value |
| --- | --- |
| Valid products | 161 |
| Minimum | ₹57.89 |
| 25th percentile | ₹199.00 |
| Median | ₹299.00 |
| 75th percentile | ₹399.00 |
| Maximum | ₹1,599.00 |
| Mean | ₹378.00 |

| Price band | Products | Share of 161 |
| --- | --- | --- |
| Below ₹200 | 51 | 31.7% |
| ₹200 to below ₹400 | 73 | 45.3% |
| ₹400 to below ₹600 | 11 | 6.8% |
| ₹600 to below ₹1,000 | 22 | 13.7% |
| ₹1,000 or more | 4 | 2.5% |
| Total | 161 | 100.0% |

### Interpretation and limits

124 of 161 sampled products (77.0%) have recorded prices below ₹400. This describes the listing sample only. ₹299 is a baseline reference, not a proposed launch price or a measure of willingness to pay.

The subset mixes connector types, lengths, advertised capabilities and pack sizes. Price comparisons require comparable specifications. Do not infer a price premium caused by a connector type without controlling for these differences. Percentiles use linear interpolation; displayed prices are rounded to two decimals.

## 6 Ratings and sensitivity checks

| Rating band | Products | Share of 161 |
| --- | --- | --- |
| Below 3.5 | 2 | 1.2% |
| 3.5–3.9 | 25 | 15.5% |
| 4.0–4.4 | 123 | 76.4% |
| 4.5–5.0 | 11 | 6.8% |
| Total | 161 | 100.0% |

All 161 USB products have valid ratings: median 4.2, mean 4.15, range 3.0–5.0. 123 of 161 products (76.4%) fall between 4.0 and 4.4. Ratings describe recorded platform feedback, not independently measured quality or representative customer satisfaction. Rounded shares may not sum to exactly 100%.

### First versus last occurrence

| Measure | First | Last |
| --- | --- | --- |
| Median discounted price | ₹299.00 | ₹299.00 |
| Mean discounted price | ₹378.00 | ₹378.00 |
| Median rating | 4.2 | 4.2 |
| Mean reference price | ₹944.29 | ₹938.70 |
| Mean advertised discount | 59.74% | 59.68% |
| Maximum advertised discount | 90% | 89% |
| Valid rating counts | 159 | 159 |
| Mean rating count | 13,972.77 | 13,972.75 |

The complete first/last vectors for discounted_price and rating are equal, so their displayed summaries are unchanged. Reference-price and discount results change because of B096MSW6CT; rating counts also vary for some repeated IDs. Stability does not establish that the dataset is current or representative.

### Missing rating counts

Two USB products have missing rating_count values: B0B94JPY2N, B0BQRJ3C47. Therefore rating-count statistics use 159 products, while price and star-rating statistics use 161. Do not fill missing counts with zero or use rating counts as sales.

## 7 Classification limits and next research

### Classification evidence still required

Connector, length, pack-size, power, data-speed and brand totals from the earlier agent output are not adopted as validated findings. The connector-keyword table totals 136 products despite a stated total of 161, and pack-size narratives disagree. Labelling numerical counts “qualitative” does not resolve these issues.

Before using a classification result, retain one auditable row per product ID containing the original text, extracted attribute, rule, uncertainty and reviewer decision. Distinguish actual connector endpoints from compatibility mentions. “2-in-1” describes multi-function or connector configuration; it does not establish two physical cables. Missing pack-size text is unknown, not a default pack of one.

### Warranty text screening

| Literal case-insensitive text match | Distinct products |
| --- | --- |
| Contains warrant | 63 |
| Contains guarantee | 3 |
| Contains either | 66 |
| Contains neither | 95 |

These counts screen about_product text only; they do not verify enforceable warranty terms, duration or coverage. The previous 63/98 split omitted the separate guarantee matches under its stated combined-keyword rule.

### Corrections incorporated

This consolidated version removes duplicate tables and incomplete correction instructions, restores a standalone baseline, corrects the Sounce row index to 2, retains the 59-ID duplicate reconciliation, fixes discount arithmetic and rating percentages, and uses the actual valid count of 159 for USB rating_count. Unsupported classification totals are withheld pending evidence.

### Next research and deliverables

Run one focused Quick Research investigation of current, comparable USB cable offers in India, using three to five verified competing brands. Capture source links, publication or update dates where available, access dates, model identifiers and advertised specifications. Check warranty claims and customer concerns; investigate contradictions that could alter the pilot decision.

Then produce the Market Analysis, assess each insight for source quality, consistency and timeliness, and prepare the leadership brief. No recommendation to launch, demand estimate, profitability conclusion or claim of current market share follows from this baseline alone.
