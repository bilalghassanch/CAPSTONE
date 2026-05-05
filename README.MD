# BBO Capstone Project: Bayesian Optimization for Hyperparameter Tuning

## Non-Technical Summary (for general audience)

Imagine you're trying to bake the perfect chocolate chip cookie. You have many dials to turn: oven temperature, baking time, sugar amount, and chocolate chip density. Testing every combination would take forever. This project builds a smart "cookie optimizer" that learns from each batch it bakes and suggests which dials to turn next. Starting from a basic trial-and-error approach, I improved the optimizer week by week — swapping out its prediction engine, changing how it balances exploration versus trying new things, and adding practical constraints like evaluation time. The final optimizer finds high-quality solutions about 40% faster than random guessing, with results that are stable and reproducible.

## Project Overview

This repository contains my complete work for the BBO (Black-Box Optimization) capstone project. The goal was to optimize a set of mixed continuous and discrete hyperparameters for a machine learning pipeline using Bayesian optimization. Over five weeks, I iteratively improved the baseline implementation by modifying:

- Week 1: Added logging to diagnose poor early performance
- Week 2: Switched to hybrid surrogate (random forest + Gaussian process)
- Week 3: Changed acquisition function from EI to UCB with decay
- Week 4: Added parallel batching (3 candidates per iteration)
- Week 5: Added time penalty for slow-to-evaluate parameters

## Repository Structure

| File/Folder | Description |
|-------------|-------------|
| `README.md` | This file — project overview and instructions |
| `datasheet.md` | Dataset documentation following responsible AI guidelines |
| `model_card.md` | Model documentation including limitations and intended use |
| `notebooks/` | Jupyter notebooks documenting week-by-week development |
| `src/` | Python modules for surrogate models and acquisition functions |
| `results/` | Performance data, convergence plots, and analysis |
| `LICENSE` | MIT License for open-source sharing |

## Key Results

| Metric | Baseline | Final | Improvement |
|--------|----------|-------|--------------|
| Mean validation score | 0.62 ± 0.04 | 0.82 ± 0.01 | +32% |
| Convergence speed | 50 iterations | 45 iterations | 10% faster |
| Stability (std deviation) | 0.04 | 0.01 | 75% better |

**Most impactful change:** Hybrid surrogate (random forest + GP) → +12% score improvement

## Quick Start

### Requirements

- Python 3.8 or higher
- numpy
- pandas
- matplotlib
- scikit-learn

### Installation

```bash
git clone https://github.com/yourusername/bbo-capstone.git
cd bbo-capstone
pip install numpy pandas matplotlib scikit-learn
