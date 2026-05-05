# Model Card: Hybrid Bayesian Optimizer

## Model Details

- **Model type:** Bayesian optimization with hybrid surrogate model
- **Surrogate:** Random forest (for discrete parameters) + Gaussian process (for continuous parameters)
- **Acquisition function:** Upper Confidence Bound (UCB) with adaptive exploration
- **Exploration coefficient (κ):** Starts at 2.5, decays linearly to 0.5
- **Batching:** q-EI with constant liar, batch size = 3
- **Date:** May 2026
- **Author:** [Your Full Name]

## Intended Use

- **Primary use case:** Hyperparameter optimization for ML pipelines with mixed continuous and discrete parameters
- **Intended users:** Data scientists, ML engineers, AutoML researchers
- **Out-of-scope uses:** Problems with >50 dimensions, real-time optimization (millisecond responses)

## Factors

- **Relevant factors:** Performance varies with search space size, evaluation budget, and noise level.
- **Evaluation factors:** Tested on synthetic optimization problem with known structure.

## Metrics

- **Primary metric:** Mean validation score (higher is better)
- **Secondary metrics:** Standard deviation across seeds, time to convergence
- **Baseline comparison:** Random search

## Performance Results

| Week | Score (mean ± std) | Key Change |
|------|-------------------|-------------|
| 1 | 0.62 ± 0.04 | Baseline with logging |
| 2 | 0.74 ± 0.03 | Hybrid surrogate (random forest + GP) |
| 3 | 0.82 ± 0.02 | UCB acquisition function |
| 4 | 0.83 ± 0.02 | Parallel batching (speed only) |
| 5 | 0.82 ± 0.01 | Time penalty (more stable) |

**Final improvement:** +32% from baseline, +12% from single best change

## Training and Evaluation Data

- **Training data:** None — Bayesian optimization learns online during evaluation.
- **Evaluation data:** 50 iterations per run, repeated across 10 random seeds.

## Ethical Considerations

- **Potential harms:** None directly. However, this optimization approach could be applied to domains with ethical consequences (healthcare, finance). Users should always validate outputs.
- **Mitigations:** Provided as a research tool, not a turnkey decision system.

## Caveats and Recommendations

- **Limitations:** Uncertainty estimates near search space boundaries are less reliable. High-dimensional spaces (>50 parameters) untested.
- **Recommendations:** 
  - For budgets under 20 iterations, start with random search
  - For mixed continuous/discrete spaces, prefer hybrid surrogates over pure GPs
  - Always log intermediate results for debugging
