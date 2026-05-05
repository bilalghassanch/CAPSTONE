# Datasheet: BBO Capstone Evaluation Dataset

## Motivation

- **Why was this dataset created?** This dataset was created for a black-box optimization capstone project to evaluate hyperparameter tuning algorithms. It simulates a machine learning pipeline where different hyperparameter combinations produce different validation scores.
- **Who created it?** Course instructors for the BBO capstone project.
- **Funding source?** Educational institution internal funding.

## Composition

- **What does the dataset contain?** This is not a static file but an evaluation function. It takes hyperparameter values as input and returns a validation score as output.
- **What are the hyperparameters?**
  - Continuous: learning rate (1e-5 to 1e-1), regularization coefficient (1e-6 to 1e-2), dropout rate (0.0 to 0.5)
  - Discrete/categorical: activation function (ReLU, Tanh, Sigmoid), optimizer (Adam, SGD, RMSprop)
- **How many instances?** Infinite — the function can be queried any number of times.
- **Is there noise?** Yes, minor stochastic variation to simulate real-world conditions.
- **Does it contain sensitive information?** No.
- **License?** Educational use only for enrolled students.

## Collection Process

- **How was the data generated?** The evaluation function was designed to have multiple local optima, mixed parameter types, and diminishing returns — mimicking real hyperparameter optimization problems.

## Preprocessing and Cleaning

- **Was preprocessing performed?** No. The function accepts raw hyperparameter values directly.

## Uses

- **What tasks is this suitable for?** Benchmarking Bayesian optimization, random search, and other black-box optimization algorithms.
- **What tasks is it NOT suitable for?** Any task requiring real human subjects or large-scale supervised learning.
- **Known limitations:** The function is synthetic and may not perfectly reflect real-world optimization landscapes.

## Distribution and Maintenance

- **How can others access it?** Access is restricted to course participants.
- **Will it be updated?** No.
- **Contact for maintenance:** Course instructors.

## Legal and Ethical Considerations

- **Privacy concerns:** None.
- **Copyright constraints:** The evaluation function is proprietary to the course. Results and analysis are freely shareable.
