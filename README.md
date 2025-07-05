# Pokemon Battle Outcome Prediction

A comprehensive machine learning project that predicts Pokemon battle outcomes using statistical analysis and advanced feature engineering techniques.

## Project Overview

This project analyzes Pokemon battle data to predict which Pokemon will win in a head-to-head battle. Using the [Pokedex Pokemon Data](https://www.kaggle.com/datasets/lmno3418/pokedex-pokemon-data) dataset from Kaggle, we achieved **95%+ accuracy** through strategic feature engineering and model optimization.

## Key Results

| Model | Accuracy | Precision | Recall | F1-Score |
|-------|----------|-----------|--------|-----------|
| **Random Forest (Optimized)** | **95.0%** | 0.95 | 0.95 | 0.95 |
| **XGBoost** | **95.4%** | 0.95 | 0.95 | 0.95 |
| Logistic Regression | 94.0% | 0.94 | 0.94 | 0.94 |
| Decision Tree | 93.0% | 0.93 | 0.93 | 0.93 |

## Technical Approach

### Feature Engineering Strategy
- **Statistical Differences**: Created difference features for all Pokemon stats (HP, Attack, Defense, etc.)
- **Type Encoding**: One-hot encoded all 18 Pokemon types for both competitors
- **Battle Mechanics**: Incorporated speed-based attack order features
- **Scaling**: Applied MinMax scaling to normalize feature ranges

### Model Development
- **Data Splitting**: 60% train, 20% validation, 20% test with stratified sampling
- **Hyperparameter Tuning**: GridSearchCV with 5-fold cross-validation
- **Model Comparison**: Evaluated multiple algorithms (Logistic Regression, Decision Tree, Random Forest, XGBoost)
- **Validation**: Robust evaluation methodology preventing overfitting


## Getting Started

### Prerequisites
```bash
pip install pandas numpy scikit-learn xgboost matplotlib seaborn
```

### Quick Start
1. Clone the repository
2. Download the dataset from [Kaggle](https://www.kaggle.com/datasets/lmno3418/pokedex-pokemon-data)
3. Run the preprocessing notebook: `01_data_preprocessing.ipynb`
4. Train models with: `02_model_training.ipynb`

## Feature Engineering Highlights

### 1. Statistical Difference Features
Instead of using absolute Pokemon stats, we created difference features:
- `HP_diff = HP_first - HP_second`
- `Attack_diff = Attack_first - Attack_second`
- And so on for all stats...

**Rationale**: Battle outcomes depend on relative advantages, not absolute values.

### 2. Pokemon Type Encoding
- One-hot encoded all 18 Pokemon types
- Captured both primary and secondary types
- Created 36 type-related features (18 for each Pokemon)

### 3. Battle Mechanics Features
- `First_pokemon_attacks_first`: Based on speed advantage
- Captures the strategic importance of turn order in Pokemon battles

## Model Performance Analysis

### Confusion Matrix (Test Set)
```
                 Predicted
Actual       0        1
    0     3817      211
    1      162     3421
```

### Key Metrics
- **Accuracy**: 95.4% (XGBoost)
- **Precision**: 0.95 (balanced across classes)
- **Recall**: 0.95 (strong true positive detection)
- **F1-Score**: 0.95 (excellent harmonic mean)

## Key Insights

### What Makes a Pokemon Win?
1. **Stat Advantages**: Higher attack, defense, and HP differences
2. **Speed Advantage**: Going first provides significant benefit
3. **Type Effectiveness**: Proper type matchups matter
4. **Legendary Status**: Legendary Pokemon have inherent advantages

### Model Interpretability
- Random Forest provides feature importance rankings
- XGBoost offers robust performance with gradient boosting
- Both models show consistent performance across validation and test sets

## Project Achievements

- **High Accuracy**: 95%+ prediction accuracy
- **Robust Validation**: Proper train/validation/test split methodology
- **Feature Engineering**: 48 engineered features from raw data
- **Model Optimization**: Hyperparameter tuning with GridSearchCV
- **Comprehensive Analysis**: Multiple algorithms compared and evaluated


## Learning Outcomes

This project demonstrates:
- **Domain Knowledge Application**: Understanding Pokemon battle mechanics
- **Feature Engineering**: Creating meaningful predictive features
- **Model Selection**: Comparing multiple algorithms systematically
- **Evaluation Methodology**: Proper validation and testing procedures
- **Performance Optimization**: Hyperparameter tuning and model selection

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Dataset provided by [Kaggle](https://www.kaggle.com/datasets/lmno3418/pokedex-pokemon-data)
- Pokemon battle mechanics knowledge from the Pokemon community
- Scikit-learn and XGBoost teams for excellent ML libraries

---
