# Workflow and reusable prompts

This project was built through the Amazon QuickSuite interface. The prompts below reconstruct the research approach; they are not a complete exported conversation or a claim that every sentence was used verbatim.

## 1. Frame the decision

> Assess whether a hypothetical online retailer should commit inventory to a USB cable pilot on Amazon India. Define inclusions, exclusions, missing business inputs and what evidence would support a decision. Do not invent budgets, sales, margins or pilot thresholds.

## 2. Inspect the internal dataset

> Inspect the complete uploaded CSV if full-file processing is available. State the actual coverage and method. Report row and column counts, distinct product IDs, missing and invalid values, category counts and duplicate conflicts. Reconcile totals. Do not infer the collection date from URL parameters or describe rating counts as sales. If only retrieved excerpts are available, disclose that limitation.

## 3. Establish a reproducible baseline

> Filter the exact USB Cables category. Keep one row per product_id using first occurrence in original file order and document the rule. Report valid denominators for each numeric field. Compare with last-occurrence selection to identify sensitivity. Do not invent connector, brand, pack-size or review-frequency counts without an auditable mapping.

## 4. Gather external signals with Quick Research

> Investigate selected USB-C to USB-C offers relevant to an Amazon India pilot. Prioritize comparable prices and availability, advertised specifications, warranty terms and specific customer concerns. Record exact models, source URLs and access dates. Prefer primary product/policy sources and distinguish brand-direct pages from marketplace offers. Keep unresolved regulatory status explicit. Save the completed research with citations.

## 5. Produce the Market Analysis

> Combine the corrected dataset baseline with saved Quick Research. Produce four decision-relevant insights with specific evidence, implications, counterevidence, limitations and next actions. Separate undated sample statistics from dated external observations. Treat availability, demand and margin as unknown when not established.

## 6. Audit reliability

> Audit each major insight against its cited evidence. Assess source quality, consistency, timeliness, assumptions and what cannot be concluded. Assign one overall High, Medium or Low label to the bounded claim and explain separately the confidence in its commercial implication. Missing corroboration is not automatically conflicting evidence.

## 7. Produce and organize the leadership brief

> Produce a concise leadership brief with objective and scope, four insights, evidence, why each matters, confidence and limitations, prioritized actions, at least two non-conclusions, and a six-sentence leadership summary. Organize the dataset reference, inspection, completed research, analysis, brief and reliability evaluation in the project Space.

## Rebuild notes

Download the original dataset from the linked Kaggle source, keep its provided CSV format, and upload it to a project Space. Create a custom chat agent with that Space as knowledge. Run the research and synthesis in QuickSuite, preserving screenshots and exported outputs. Current interface labels and account permissions may differ from the lab used for this project.
