# Datasheet

## Dataset name

**Synthetic molecular genomics datasets for proof-of-concept analysis**

## Dataset summary

These datasets were generated to support a synthetic genomics workflow that demonstrates variant prioritization, rare-variant burden analysis, GWAS-style association, fine-mapping, and patient stratification. All datasets are simulated and were created for methodological demonstration, portfolio use, and teaching.

## Motivation

The datasets were designed to mimic the broad structure of human genomic analysis without using real patient data. The goal was to create a safe and interpretable dataset collection that still reflects key biological and statistical patterns seen in sequencing studies, including:

- enrichment of rare variants,
- stronger pathogenic potential for severe consequence classes,
- ancestry-related structure,
- sparse rare-variant burden,
- localized common-variant association signals,
- partially overlapping patient feature space.

## Dataset list

### 1. `synthetic_cohort_preview.csv`

A preview of individual-level data used in the notebook. Each row represents one synthetic individual and may include:

- ancestry group,
- rare disease-like case status,
- burden-related summary features,
- selected phenotype-style covariates,
- other compact features used in downstream embedding or analysis.

### 2. `top_prioritized_variants.csv`

A ranked table of the highest-priority variants from the synthetic variant interpretation workflow. Likely columns include:

- variant identifier,
- molecular consequence,
- allele frequency,
- annotation-style scores,
- prioritization score,
- simplified interpretation class.

### 3. `gene_burden_results.csv`

Gene-level results from the rare damaging burden analysis. Likely columns include:

- gene symbol,
- case burden count,
- control burden count,
- effect or burden summary,
- p-value,
- transformed significance metric.

### 4. `gwas_finemap_results.csv`

Variant-level summary from the synthetic common-variant locus analysis and fine-mapping workflow. Likely columns include:

- variant or locus identifier,
- position,
- effect estimate,
- standard error,
- p-value,
- posterior inclusion probability.

## Data generation process

The datasets were created through simulation rather than experimental measurement.

### Variant simulation

Variants were assigned:

- allele frequencies with a rare-variant–enriched distribution,
- molecular consequence classes,
- annotation-like features that mimic deleteriousness, conservation, and splice-disruption signals,
- technical features such as read depth and call rate.

### Cohort simulation

Individuals were assigned:

- ancestry groups,
- phenotype labels,
- genotype-derived burden features,
- selected synthetic phenotype covariates.

### Signal embedding

The simulation included:

- stronger pathogenic probability for severe coding and splice classes,
- a weak-to-moderate rare damaging burden structure,
- a planted common-variant association signal at a synthetic locus,
- partial disease-related structure in patient feature space.

## Recommended uses

These datasets are appropriate for:

- proof-of-concept demonstration,
- teaching computational genomics,
- showing how different genomics analyses connect,
- portfolio projects,
- testing notebooks and visualizations,
- explaining genomic inference in plain language.

## Non-recommended uses

These datasets are not appropriate for:

- clinical interpretation,
- benchmarking real diagnostic performance,
- population inference about real ancestries,
- causal claims about real genes or variants,
- direct comparison with real patient datasets as if they were measured truth.

## Data quality notes

Because the data are simulated:

- missingness and technical noise are simplified,
- annotation scores are synthetic proxies,
- disease architecture is intentionally stylized,
- cohort structure is controlled rather than naturally observed,
- statistical significance depends on simulation assumptions.

## Biases and limitations

Several limitations should be considered:

- the data reflect design assumptions made by the simulator,
- real genomes are more heterogeneous and noisier,
- real pathogenicity is more complex than a consequence-driven prior,
- ancestry structure is simplified into broad groups,
- rare-variant burden is especially sensitive to effect-size assumptions,
- fine-mapping is simplified and does not model full linkage disequilibrium complexity.

## Privacy and ethics

No real patient data were used. No personally identifiable information is present. The synthetic design avoids privacy risk while still allowing demonstration of human genomics workflows.

## Preprocessing and transformation

The notebook applies several transformations and analysis steps, including:

- allele-frequency transformation,
- variant filtering and summary preparation,
- principal component analysis,
- model fitting and scoring,
- burden aggregation,
- single-marker association testing,
- posterior normalization for fine-mapping,
- patient-level feature embedding.

## Maintenance and versioning

This datasheet describes the current synthetic dataset bundle distributed with the proof-of-concept notebook. Future versions may include:

- more genes,
- larger cohorts,
- richer phenotype labels,
- multi-omics style features,
- structural variant simulation,
- long-read–specific representations,
- more realistic linkage disequilibrium patterns.

## One-line descriptions

- `synthetic_cohort_preview.csv`: Preview of the simulated individual-level cohort used for genomics and phenotype analyses.
- `top_prioritized_variants.csv`: Highest-ranked candidate variants from the synthetic annotation and prioritization workflow.
- `gene_burden_results.csv`: Gene-level rare damaging burden statistics for the synthetic rare disease-like phenotype.
- `gwas_finemap_results.csv`: Variant-level association and fine-mapping summary for the synthetic common-variant locus.
