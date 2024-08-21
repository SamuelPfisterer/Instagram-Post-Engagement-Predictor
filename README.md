# Instagram Engagement Predictor

## Project Overview

The "Instagram Engagement Predictor" project is designed to predict the engagement (likes) of Instagram posts based on various features extracted from the post metadata. The project follows a structured pipeline, where each step is captured in a series of Jupyter notebooks. We start with a directory containing json files and end up 
with a python notebook, where we train thee type of models that we evaluate. Furthermore, we also use one of these models to predict the effect of posting on the right weekday for example. 

## Repository Structure

The project consists of the following key notebooks, each performing a specific task in the data pipeline:

1. **json_files_to_csv.ipynb**
2. **extracting_location_data.ipynb**
3. **feature_engineering.ipynb**
4. **cleaning.ipynb**
5. **Modelling.ipynb**

Below is a detailed explanation of each notebook, including the input and output files associated with each step.

---

### 1. `json_files_to_csv.ipynb`

**Description**: 
This notebook converts JSON files (each representing metadata for one Instagram post) into a single CSV file. The resulting CSV contains metadata for all posts, with each row corresponding to a post and each column representing specific metadata.

**Key Processes**:
- Converts all JSON files into a single CSV file.

**Input**: 
- Directory containing JSON files of Instagram post metadata.

**Output**: 
- `posts_metadata.csv`: A CSV file containing combined metadata for all Instagram posts.

---

### 2. `extracting_location_data.ipynb`

**Description**: 
This notebook extracts and processes location data from the metadata, adding geographical features to the dataset. This step is crucial for analyzing how the location of a post might influence engagement.

**Input**: 
- `posts_metadata.csv`: The CSV file generated in the previous step.

**Output**: 
- `posts_with_location_data.csv`: A CSV file with additional columns for location-based features.

---

### 3. `feature_engineering.ipynb`

**Description**: 
This notebook engineers features that could be useful for predicting engagement. It includes tasks such as processing and extracting information from the captions, and creating new features that can improve the predictive performance of the model.

**Input**: 
- `posts_with_location_data.csv`: The CSV file with location data.

**Output**: 
- `posts_with_engineered_features.csv`: A CSV file with additional engineered features.

---

### 4. `cleaning.ipynb`

**Description**: 
This notebook handles data cleaning, including removing "irrelevant" features and handling missing values. This step ensures the dataset is clean and ready for modeling.

**Input**: 
- `posts_with_engineered_features.csv`: The CSV file with engineered features.

**Output**: 
- `cleaned_data.csv`: A cleaned and preprocessed CSV file ready for modeling.

---

### 5. `Modelling.ipynb`

**Description**: 
This notebook builds first prepares the features to be processed by the models. Then we train and evaluates a machine learning models to predict Instagram post engagement. It includes hyperparameter tuning, model evaluation, and feature importance analysis.

**Key Processes**:
- Encoding features, scaling features, removing outliers.
- Trains a Multi Perceptron model, Random Forest model, and a Gradient Boosting Regressor on the cleaned dataset.
- Evaluates model performance using various metrics.
- Analyzes feature importance using SHAP values.
- Analyzes the impact of posting on the 'right' weekday for example. 

**Input**: 
- `cleaned_data.csv`: The cleaned dataset prepared in the previous step.
- `influencers.csv`: This file contains information for each influencer (e.g. #Followers, #Posts, etc.)

**Output**: 
- *No output files generated in this notebook.*

---
