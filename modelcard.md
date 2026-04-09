# Model Card

## Model name

**Synthetic variant prioritization model**

## Model summary

This model is a proof-of-concept supervised classifier that ranks simulated genomic variants according to their likelihood of being pathogenic within a synthetic genomics workflow. It is intended to demonstrate how molecular annotation features can be integrated to separate likely damaging from likely benign variants in a research-style setting.

## Model objective

The model estimates a prioritization score for each variant based on annotation-style features that reflect molecular consequence, rarity, conservation, splice disruption, and technical support. The aim is to support candidate ranking for downstream review rather than to make clinical claims.

## Intended use

### Appropriate uses

- demonstrating a variant prioritization workflow,
- teaching how annotation-driven ranking works in genomics,
- showing model evaluation using ROC and precision–recall analysis,
- illustrating feature importance in a molecular genomics context,
- portfolio and proof-of-concept applications.

### Inappropriate uses

- clinical diagnosis,
- patient care decisions,
- regulatory use,
- interpretation of real patient variants without external validation,
- replacement of ACMG/AMP clinical classification.

## Model inputs

The model takes synthetic annotation-style features such as:

- molecular consequence class,
- allele frequency, represented in transformed form,
- CADD-like integrated deleteriousness score,
- REVEL-like missense pathogenicity score,
- phyloP-like conservation score,
- SpliceAI-like splice disruption score,
- gene constraint-style feature,
- read depth,
- long-read support indicator or score.

## Model outputs

The model returns:

- a pathogenicity-oriented prioritization score,
- a predicted pathogenic versus non-pathogenic class,
- evaluation outputs such as ROC and precision–recall curves,
- feature importance estimates from permutation analysis.

## Training data

The training data are fully synthetic. Variant labels, annotation features, and technical covariates were simulated to reflect broad biological logic rather than real measured truth. The simulated design intentionally enriches predicted loss-of-function and severe splice classes for higher pathogenic probability, while leaving synonymous and many intronic variants with lower baseline pathogenic probability.

## Evaluation

The proof-of-concept model was evaluated using:

- receiver operating characteristic area under the curve,
- precision–recall analysis,
- average precision,
- permutation feature importance.

These metrics were used because variant prioritization commonly operates under class imbalance, where pathogenic variants are less common than benign variants.

## Factors influencing performance

Performance is influenced by:

- how strongly the simulation separates pathogenic from benign variants,
- the assigned relationship between consequence class and pathogenicity,
- the simulated allele-frequency distribution,
- the strength of annotation-style features,
- the amount of overlap between classes.

## Key strengths

- integrates multiple biologically meaningful features,
- demonstrates a realistic genomics triage workflow,
- provides interpretable feature importance,
- links molecular logic to statistical prioritization,
- supports downstream burden and locus-level analyses.

## Key limitations

- trained only on simulated data,
- does not include real clinical evidence,
- does not perform formal ACMG/AMP interpretation,
- may overstate performance relative to real-world noisy datasets,
- not benchmarked against external truth sets,
- not suitable for direct deployment in healthcare.

## Ethical considerations

Because this model is synthetic and not clinically validated, it must not be used to make real medical decisions. Real genomic interpretation requires rigorous case-level evidence, ancestry-aware context, disease-specific knowledge, and expert review.

## Caveats for interpretation

A high prioritization score means that a variant looks suspicious under the synthetic rules of the model. It does not prove causality, pathogenicity, or clinical relevance. Variant ranking should be understood as a first-pass research step, not an endpoint.

## Maintenance

This model card describes the current proof-of-concept version included in the repository notebook. Future versions could incorporate:

- richer synthetic regulatory features,
- improved fine-mapping integration,
- calibrated probability outputs,
- real benchmark datasets for methodological comparison,
- more explicit uncertainty modeling.
