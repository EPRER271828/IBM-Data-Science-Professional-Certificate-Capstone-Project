# IBM-Data-Science-Professional-Certificate-Capstone-Project
This is the repository created to house and document the Capstone Project , that is required to be completed for the IBM Data Science Professional Certificate. The project is about predicting whether SpaceX can successfully land the first stage of its Falcon 9 rocket back on earth.  It can predict the cost of the operation.

# SpaceX Falcon 9 First Stage Landing Prediction

## 🚀 Project Overview
SpaceX is able to offer rocket launches at a fraction of the cost of its competitors ($62M vs $165M+) primarily because of its groundbreaking ability to recover and reuse the first stage booster of the Falcon 9 rocket. 

In this capstone project, I played the role of a data scientist working for a fictional data analytics firm competing against SpaceX. The goal of this project is to predict whether the Falcon 9 first stage will land successfully so our firm can determine the true operational costs of a launch and submit accurate competitive bids.

---

## 🛠️ Data Science Lifecycle & Workflow

### 1. Data Collection
* **REST API:** Interrogated SpaceX's developer endpoints to extract structural details such as payload mass, booster serial numbers, core configurations, and destination orbits.
* **Web Scraping:** Wrote a `BeautifulSoup` script to scrape the official Wikipedia timeline page of Falcon 9 launches to pull historical metadata not captured in the raw API payloads.

### 2. Data Wrangling & SQL Analysis
* Engineered a binary target variable `Class` where `1` represents a successful booster recovery (e.g., landing on a drone ship or landing pad) and `0` indicates a landing failure or loss of core.
* Loaded the unified datasets into a SQLite database and queried key aggregate insights using SQL (e.g., total payload distributions, successful landing rates per launch site).

### 3. Exploratory Data Analysis & Feature Engineering
* Generated visual correlation graphs using `Seaborn` and `Matplotlib` to discover patterns between flight numbers, launch site locations, payload masses, and success trends.
* Converted critical categorical columns (`Orbit`, `LaunchSite`, `LandingPad`, `Serial`) into numerical arrays using **One-Hot Encoding** (`pd.get_dummies`), expanding the feature matrix to **83 columns** optimized for mathematical algorithms.

### 4. Interactive Geospatial Mapping & Dashboards
* **Folium Mapping:** Constructed an interactive, zoomable map displaying launch site clusters color-coded by performance (Green for success, Red for failure).
* **Plotly Dash Application:** Built a complete local analytical dashboard application featuring drop-down interaction triggers connected to dynamic callback engines that instantly render real-time pie charts and scatter trends.

### 5. Predictive Machine Learning Classification
Split the processed dataset into 80/20 train/test records and tuned hyperparameters across four major machine learning algorithms using `GridSearchCV`:
* Logistic Regression
* Support Vector Machine (SVM)
* Decision Tree Classifier
* K-Nearest Neighbors (KNN)

---

## 📊 Final Results & Model Evaluation

The accuracy metrics achieved by the machine learning models on the validation data are summarized below:

| Predictive Model | Accuracy Score |
| :--- | :--- |
| **Decision Tree** | **83.33%** |
| **Logistic Regression** | **83.33%** |
| **Support Vector Machine (SVM)** | **83.33%** |
| **K-Nearest Neighbors (KNN)** | **83.33%** |

### Key Conclusion:
While all four algorithms converged on an identical baseline accuracy score due to the dataset size constraints, the **Decision Tree Classifier** emerged as a highly practical choice due to its explicit rules-based layout and fast optimization performance during parameter tuning. 

---
