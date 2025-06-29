# titanic-ml-prediction
 Predicting survival on the Titanic using machine learning (Kaggle competition)

## 📁 Repository Structure
titanic-ml-prediction/
├── train.csv # Training dataset provided by Kaggle
├── test.csv # Test dataset for submission
├── titanic_model.py # Core Python script for preprocessing and model training
├── submission.csv # Output predictions for Kaggle submission
├── .gitignore # Files ignored by Git
└── README.md # Project documentation

## 🧪 Data Preprocessing & Feature Engineering

The following transformations are applied to both training and test datasets:

- **Missing Values**:
  - `Age`: Filled with the column mean
  - `Embarked`: Filled with the most frequent value ("S")
  - `Cabin`: Dropped due to high proportion of missing values

- **Categorical Encoding**:
  - `Sex`: Converted to numeric (male = 0, female = 1)
  - `Embarked`: Mapped to numeric (S = 0, C = 1, Q = 2)
  - `Title`: Extracted from `Name` and mapped:
    - Mapped titles: Mr=0, Miss=1, Mrs=2, Master=3, Rare=4
    - Rare titles grouped (e.g. "Dr", "Rev", "Col", "Lady")

- **Feature Creation**:
  - `FamilySize` = `SibSp` + `Parch` + 1

## ⚙️ Model Details

- **Model**: `RandomForestClassifier` from `sklearn.ensemble`
- **Hyperparameters**: Default settings with `random_state=42`
- **Evaluation**: Accuracy on the private Kaggle test set

## 🧾 Usage

```bash
# Install dependencies (if needed)
pip install pandas scikit-learn

# Run the script
python titanic_model.py
