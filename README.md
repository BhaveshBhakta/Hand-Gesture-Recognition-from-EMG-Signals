## Hand Gesture Recognition from EMG Signals

### Project Overview

This project aims to classify **hand gestures based on Electromyography (EMG) signals**. By analyzing the electrical activity produced by muscles during different hand movements, the goal is to develop a machine learning model that can accurately recognize specific gestures. This technology has applications in human-computer interaction, prosthetics control, and rehabilitation.

-----

### Technical Highlights

  * **Dataset**: [Kaggle - EMG Dataset for 4 Gestures](https://www.kaggle.com/datasets/kyr7plus/emg-4)
  * **Size**: 11674 entries (after concatenating data files), 156 columns (initial, after loading)
  * **Key Features**: Numerous unnamed columns representing EMG sensor readings over time (e.g., `26.0`, `4.0`, `5.0`, etc.)
  * **Approach**:
      * Data Loading and Concatenation of multiple CSV files (0.csv, 1.csv, 2.csv, 3.csv).
      * Data Cleaning (No duplicates found; Missing values are present and were implicitly handled by Label Encoding, which would assign a numerical value).
      * Exploratory Data Analysis (Histograms for numerical features).
      * Label Encoding for all features, including the target, which were originally float-like columns.
      * Feature Selection (The code selects columns 0 to 63 as features (X) and column 64 as the target (y)). This implies that the '3' column from the original data (which seems to be the gesture label) was implicitly mapped to column 64 after concatenating and renaming columns.
      * Binary/Multi-class Classification (depending on the range of values in column 64 after encoding). The output shows 2 classes (0 and 1), suggesting a binary classification after encoding.
      * Models Used:
          * Logistic Regression, Ridge Classifier, SVC, Random Forest, XGBoost, AdaBoost, Gradient Boosting, Bagging, Decision Tree
  * **Best Accuracy**:
      * 100% across all models (Logistic Regression, Ridge Classifier, XGBoost, Random Forest, AdaBoost, Gradient Boosting, Bagging, Decision Tree, SVC). This extremely high accuracy might indicate potential data leakage or a very simple, separable dataset for the selected target.

-----

### Purpose and Applications

  * Develop **intuitive human-computer interfaces** controlled by hand gestures.
  * Enable more natural and functional control of robotic prosthetics.
  * Aid in rehabilitation exercises by providing feedback on muscle activity.
  * Advance research in biosignal processing and machine learning for wearable technology.

-----

### Installation

Clone the repository:

```bash
git clone https://github.com/BhaveshBhakta/Hand-Gesture-Recognition-from-EMG-Signals.git
cd Hand-Gesture-Recognition-from-EMG-Signals
```

Install the necessary libraries:

```bash
pip install pandas numpy seaborn matplotlib scikit-learn xgboost
```

-----

### Collaboration

We welcome contributions to improve the project. You can help by:

  * Thoroughly investigating the source of the 100% accuracy to identify and mitigate any potential data leakage or overfitting.
  * Clearly defining the target variable and its encoding, especially given the anonymous column names.
  * Exploring more sophisticated feature engineering techniques for EMG signals (e.g., time-domain, frequency-domain features).
  * Implementing cross-validation for more robust model evaluation.
  * Visualizing raw EMG signals to gain better domain understanding.
