# Stellar Object Classification using XGBoost on Sloan Digital Sky Survey (SDSS) Data

**Introduction**
Astronomy generates massive amounts of observational data every day. One of the most important tasks in modern astronomy is identifying and classifying celestial objects based on their observed properties.
This project focuses on classifying astronomical objects into three categories:
• Galaxy  
• Star  
• Quasar (QSO)
Using machine learning techniques and data collected from the Sloan Digital Sky Survey (SDSS), an XGBoost classifier was trained to automatically distinguish between these object types with high accuracy.
The project demonstrates a complete machine learning workflow including data exploration, feature selection, preprocessing, model training, hyperparameter tuning, evaluation, and model persistence.

**Project Objective**
The objective of this project is to build a machine learning model capable of accurately classifying celestial objects based on their observational and spectral measurements.
The model predicts whether an observed object is:
• Star  
• Galaxy  
• Quasar (QSO)

**About the Dataset**
This project uses the Stellar Classification Dataset derived from the Sloan Digital Sky Survey (SDSS).
SDSS is one of the largest astronomical surveys ever conducted and provides detailed measurements of celestial objects observed throughout the universe.
Dataset Characteristics:
• 100,000 observations  
• 17 input features  
• 3 target classes  
• Real astronomical survey data
--> Target Classes:
STAR - A luminous celestial object generating energy through nuclear fusion 
GALAXY - A large system of stars, gas, dust, and dark matter 
QSO - Quasi-Stellar Object, an extremely luminous active galactic nucleus 

**Features Used for Training**
alpha  Right Ascension (Celestial Longitude) 
delta Declination (Celestial Latitude) 
u Ultraviolet brightness 
g - Green wavelength brightness 
r - Red wavelength brightness 
i - Near Infrared brightness 
z - Infrared brightness 
redshift - Amount by which light shifts toward longer wavelengths 

**Features Removed**
The following columns were removed because they mainly serve as identifiers and provide little predictive value:
obj_ID
run_ID
rerun_ID
cam_col
field_ID
spec_obj_ID
plate
MJD
fiber_ID

**Project Workflow**
1. Data Loading
The dataset is loaded into a Pandas DataFrame for analysis and preprocessing.
2. Exploratory Data Analysis
The notebook examines:
• Dataset structure  
• Statistical summaries  
• Missing values  
• Data types  
• Class distribution
This helps understand the dataset before training.
3. Feature Selection
Identifier columns are removed to reduce noise and improve model quality.
4. Label Encoding
Target labels are converted into numerical form.
Example:
GALAXY → 0
QSO → 1
STAR → 2
5. Train-Test Split
The dataset is split into:
• 80% Training Data  
• 20% Testing Data
Stratified sampling is used to preserve class distributions.
6. Model Training
XGBoost is selected because of its strong performance on structured tabular data.
7. Hyperparameter Tuning
RandomizedSearchCV is used to optimize:
• n_estimators  
• max_depth  
• learning_rate  
• subsample  
• colsample_bytree
Cross-validation helps identify the best-performing configuration.
8. Model Evaluation
Performance is evaluated using:
• Accuracy  
• Precision  
• Recall  
• F1 Score  
• Confusion Matrix
9. Feature Importance Analysis
XGBoost feature importance scores are used to identify which astronomical measurements contribute most to predictions.
10. Model Saving
The final model is saved using Joblib so that it can be reused without retraining.

**Results**
The tuned XGBoost model achieved approximately 98% accuracy on unseen test data.
Key observations:
• Excellent precision across all classes  
• Excellent recall across all classes  
• Strong F1 scores  
• Very low misclassification rates
The confusion matrix shows that most prediction errors occur between galaxies and quasars, while stars are classified with near-perfect accuracy.

**Technologies Used**
• Python  
• Pandas  
• NumPy  
• Matplotlib  
• Seaborn  
• Scikit-Learn  
• XGBoost  
• Joblib  
• Jupyter Notebook

**Repository Structure**
stellar_classification_notebook.ipynb
README.md
classification report.png
confusion_matrix.png

**Author** 
Atharva Ambilwade
