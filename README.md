# Molecular Toxicity Prediction Pipeline

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-latest-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A complete machine learning pipeline for predicting molecular toxicity using ensemble methods with robust cross-validation.

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Methodology](#methodology)
- [Results](#results)
- [Project Structure](#project-structure)
- [Contributing](#contributing)

## 🎯 Overview

This project implements an end-to-end machine learning solution for classifying chemical compounds as **Toxic** or **Non-Toxic** based on molecular descriptors. The pipeline handles high-dimensional data (1,139 features) through advanced feature selection and ensemble modeling techniques.

**Key Capabilities:**
- Automated exploratory data analysis (EDA) for molecular datasets
- Robust preprocessing for chemical descriptor data
- Consensus-based feature selection from multiple methods
- Ensemble modeling with cross-validation
- Model interpretability through feature importance analysis

## ✨ Features

### Data Processing
- ✅ Handles missing and infinite values in molecular descriptors
- ✅ Removes constant/low-variance features automatically
- ✅ Robust scaling for outlier-resistant normalization

### Feature Selection (Consensus Approach)
| Method | Description | Selection Criteria |
|--------|-------------|------------------|
| **F-Score (ANOVA)** | Univariate statistical test | Top 50 features |
| **Mutual Information** | Information-theoretic relevance | Top 50 features |
| **Random Forest** | Tree-based importance | Top 50 features |
| **RFECV** | Recursive feature elimination with CV | Optimal subset |
| **Consensus** | Features with ≥2 votes | Final selection (~40-50) |

### Machine Learning Models
- **Random Forest** with hyperparameter tuning (GridSearchCV)
- **Gradient Boosting** with optimized parameters
- **Voting Ensemble** (Soft voting: RF + GBM + SVM)
- **Stacking Ensemble** (Meta-learner: Logistic Regression)

### Evaluation
- 5-Fold Stratified Cross-Validation
- Metrics: Accuracy, Precision, Recall, F1-Score, ROC-AUC
- Confusion matrix and ROC curve visualization

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
