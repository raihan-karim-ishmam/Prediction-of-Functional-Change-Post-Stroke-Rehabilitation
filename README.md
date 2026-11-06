# Predicting Functional Change After Stroke Rehabilitation

This project explores whether rehabilitation records from other diagnostic groups help us predict functional change in stroke patients. We compare models trained on stroke patients only with models trained on a mixed-diagnosis population.

The project is being developed for **COMP6601 Programming for Data Scientists** at **Sultan Qaboos University**.

## What we predict

Our target is the change in the Barthel Index between admission and discharge:

**Barthel Index change = discharge score − admission score**

Positive values indicate improvement, zero indicates no change, and negative values indicate deterioration. We retain valid records from all three groups.

We can also estimate the discharge score by adding the predicted change to the admission score.

## Dataset

We use the public rehabilitation dataset described by **Seccia et al. (2020)**, collected at San Raffaele in Rome between 2015 and 2018.

The data include demographic information, diagnostic categories, comorbidities, admission assessments and functional outcomes. We use the original records and document our own preparation steps.

**Dataset reference:**  
R. Seccia et al., “Data of patients undergoing rehabilitation programs,” *Data in Brief*, vol. 30, Art. no. 105419, 2020.  
https://doi.org/10.1016/j.dib.2020.105419

Dataset access and supplementary files are available through the source publication. The original data remain subject to their source licence and attribution requirements.

## Planned experiments

### Case 1: Prediction for stroke patients

We will compare stroke-only training with mixed-diagnosis training on **the same held-out stroke patients**. This is our main experiment.

### Case 2: Prediction for the wider population

We will evaluate both training strategies on the wider held-out rehabilitation population, reporting stroke and non-stroke results separately.

### Model comparison

We will compare:

- Linear regression
- Ridge regression
- Random Forest regression
- A baseline that predicts the training-group mean change

Individual admission activity scores will be our main functional inputs, alongside eligible demographic and clinical assessments. Discharge measurements and actual rehabilitation length of stay will be excluded from admission-time predictors.

## Data analysis and preparation

A substantial part of the project will involve understanding and preparing the data. We will examine distributions, missing values, diagnostic groups and relationships with functional change.

Preparation will include checking variable definitions, valid ranges, duplicate records and special scoring codes. We will not impute missing outcomes. Predictor imputation, encoding and scaling will be fitted within the training data to avoid information leakage.

## Evaluation

Our primary metric will be **mean absolute error (MAE)** in Barthel Index points. Supporting results will include RMSE, R² and prediction plots.

We will compare training strategies using identical evaluation patients and estimate uncertainty in their MAE difference through paired bootstrap resampling. We will also describe errors for patients who improved, remained unchanged or deteriorated.

All evaluation will be internal to this dataset. Testing on an independent hospital or population remains future work.

## Tools

We plan to use Python with:

- pandas and NumPy
- matplotlib
- scikit-learn
- Jupyter Notebook

Environment details, dependencies and instructions for running the notebooks will be added as implementation progresses.

## Project status

The proposal and data acquisition are complete. Exploratory analysis, preprocessing and modelling are the next stages. This repository will be updated with notebooks, documented experiments and results as the project develops.

## Author

**Raihan Karim Ishmam**  
MSc in Data Science and Machine Learning  
Sultan Qaboos University

This is an academic project. Its predictions are intended for research and coursework, not clinical decision-making.