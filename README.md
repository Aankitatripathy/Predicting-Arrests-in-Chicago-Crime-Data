# Chicago Crime Arrest Prediction

## 📌 Project Overview
Chicago is one of the most densely populated cities in the U.S., with a complex socio-economic landscape that makes crime prevention challenging. This project uses historical crime records from the Chicago Data Portal to build predictive models that classify whether a reported incident will result in an arrest (True or False).

By using patterns such as crime type, location, time of occurrence, and community area, the models support more informed analysis and better resource allocation.

## 🎓 Academic Context
- Program: MS in Artificial Intelligence & Business Analytics  
- Course: ISM6251 – Machine Learning  
- Institution: University of South Florida  
- Instructor: Reza Ebrahimi  
- Semester: Fall 2024  
- Team Members: Ankita Tripathy, Fabrizio Petrozzi, Muhammad Hammaz, Priyanka Jammu, Sai Praneetha Sigharam, Subham Mohanty

## ❓ Problem Statement
Law enforcement agencies manage large volumes of crime reports with limited resources. Predicting arrest likelihood using incident characteristics can support:
- Better prioritization of cases
- Smarter deployment of officers to high-risk locations and time windows
- Data-driven decisions that improve community safety

Target Variable: Arrest  
Type: Binary classification (True = arrest made, False = no arrest)

## 📂 Data Sources
| Dataset | Source |
| --- | --- |
| Crimes 2001 to Present | Chicago Data Portal |
| Community Area Boundaries | Chicago Data Portal – Community Areas |

Dataset Summary:
- ~220,000+ crime records
- 22 features including crime type, location, timestamp, district, community area, and arrest status
- Target variable: Arrest (binary)

## 🔧 Methodology

### 1) Exploratory Data Analysis (EDA)
- Theft and Battery were the most frequently reported crime types
- Domestic-related crimes showed a higher arrest rate
- Some community areas appeared as recurring crime and arrest hotspots
- Arrest rates varied across years, which may reflect policy or operational shifts

### 2) Data Preprocessing
- Removed rows with missing values (under 1%)
- Addressed class imbalance (about 80% non-arrest vs 20% arrest) using oversampling
- Applied one-hot encoding to categorical features (Primary Type, Location Description)
- Applied Min-Max scaling to numerical features (Community Area, Year)
- Used a stratified 80/20 train-test split

### 3) Models Trained
- Logistic Regression: interpretable baseline model
- Random Forest: ensemble model for non-linear feature interactions
- Neural Network (MLP Classifier): model for capturing complex patterns

## 📊 Results
| Model | Accuracy | Precision | Recall | F1-Score | ROC-AUC |
| --- | --- | --- | --- | --- | --- |
| Logistic Regression | 0.75 | 0.74 | 0.76 | 0.75 | 0.84 |
| Random Forest | 0.74 | 0.72 | 0.78 | 0.75 | 0.83 |
| Neural Network (MLP) | 0.79 | 0.80 | 0.76 | 0.78 | 0.88 |

## 🏆 Best Model: Neural Network (MLP)
The Neural Network delivered the best overall performance with the highest accuracy (79%), precision (0.80), F1-score (0.78), and ROC-AUC (0.88). It handled high-dimensional inputs well and captured non-linear relationships more effectively than the other models.

## 🚀 Getting Started

### Prerequisites
```bash
pip install numpy pandas scikit-learn matplotlib seaborn jupyter
# Clone the repository
git clone https://github.com/your-username/chicago-crime-arrest-prediction.git
cd chicago-crime-arrest-prediction

# Launch Jupyter
jupyter notebook notebooks/Final_ML_Project.ipynb
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
## ⚠️ Ethical Considerations
This project is built on historical arrest data, which may carry systemic biases related to over-policing in certain communities or uneven reporting practices. Any attempt to deploy this model in a real-world context should include:

- Fairness audits across demographic and geographic subgroups
- Bias assessments to flag disparate impact
- Stakeholder review involving community representatives and legal experts

Predictive models should support, not replace, human judgment in law enforcement contexts.

## 📄 License
This project is licensed under the MIT License.
