Project Overview
Chicago is one of the most densely populated cities in the U.S., with a complex socio-economic landscape that makes crime prevention especially challenging. This project leverages historical crime records from the Chicago Data Portal to build predictive models that classify whether a given incident will result in an arrest (True / False).
By identifying key patterns — such as crime type, location, time of occurrence, and community area — the models provide actionable insights for smarter law enforcement resource allocation.
Academic Context
Program: MS in Artificial Intelligence & Business Analytics
Institution: University of South Florida
Problem Statement
Law enforcement agencies manage enormous volumes of crime data with constrained resources. Accurately predicting arrest likelihood based on incident characteristics enables:
•	Better prioritization of cases
•	Smarter deployment of officers to high-risk locations and times
•	Data-driven policy decisions that support community safety
Target Variable: Arrest — binary classification (True = arrest made, False = no arrest)
Data Sources
Dataset	Source
Crimes 2001 to Present	Chicago Data Portal

Community Area Boundaries	Chicago Data Portal – Community Areas

Dataset Summary
•	~220,000+ crime records
•	22 features including crime type, location, timestamp, district, community area, and arrest status
•	Target variable: Arrest (binary)
Methodology
1. Exploratory Data Analysis (EDA)
•	Theft and Battery were the most frequently reported crime types
•	Domestic-related crimes showed a significantly higher arrest rate
•	Certain community areas were identified as consistent crime and arrest hotspots
•	Arrest rates showed year-over-year variation, potentially reflecting shifts in policing strategies
2. Data Preprocessing
•	Removed rows with missing values (< 1% of data)
•	Addressed severe class imbalance (~80% non-arrest vs ~20% arrest) using oversampling
•	Applied one-hot encoding to categorical features (Primary Type, Location Description)
•	Applied Min-Max scaling to numerical features (Community Area, Year)
•	Used a stratified 80/20 train-test split
3. Models Trained
•	Logistic Regression — interpretable baseline model
•	Random Forest — ensemble approach for handling non-linear feature interactions
•	Neural Network (MLP Classifier) — deep model for capturing complex patterns
Results
Model	Accuracy	Precision	Recall	F1-Score	ROC-AUC
Logistic Regression	0.75	0.74	0.76	0.75	0.84
Random Forest	0.74	0.72	0.78	0.75	0.83
Neural Network (MLP)	0.79	0.80	0.76	0.78	0.88
Best Model: Neural Network (MLP)
The Neural Network outperformed other models with the highest accuracy (79%), precision (0.80), F1-score (0.78), and ROC-AUC (0.88). Its ability to model complex, non-linear relationships made it the most robust choice for this high-dimensional dataset.
Getting Started
Prerequisites
bash
pip install numpy pandas scikit-learn matplotlib seaborn jupyter
Run the Notebook
bash
# Clone the repository
git clone https://github.com/your-username/chicago-crime-arrest-prediction.git
cd chicago-crime-arrest-prediction

# Launch Jupyter
jupyter notebook notebooks/Final_ML_Project.ipynb
Repository Structure
chicago-crime-arrest-prediction/
│
├── notebooks/
│   └── Final_ML_Project.ipynb       # Full ML pipeline: EDA → preprocessing → modeling → evaluation
│
├── docs/
│   ├── ML_Documentation.pdf         # Detailed project write-up and methodology
│   └── Chicago-Crime-PROJECT.pptx   # Presentation deck
│
└── README.md
Ethical Considerations
This project is built on historical arrest data, which may carry systemic biases related to over-policing in certain communities or uneven reporting practices. Any attempt to deploy this model in a real-world context should include:
•	Fairness audits across demographic and geographic subgroups
•	Bias assessments to flag disparate impact
•	Stakeholder review involving community representatives and legal experts
Predictive models should support — not replace — human judgment in law enforcement contexts.
License
This project is licensed under the MIT License.

<img width="451" height="688" alt="image" src="https://github.com/user-attachments/assets/4eab47c9-a768-47bc-81cb-e75d981f7f73" />
