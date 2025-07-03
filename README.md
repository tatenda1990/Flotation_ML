# Predicting Flotation Faults from a data set

This project is designed to explore and implement a machine learning script for predicting faults using 4 features and 2 target variables. 

## Methods employed
Started off by creating a working folder, downloading the data into the working folder
Proceeded to open Visual Studio Code, opened the folder, and created a Juyter notebook. 
Opened up a terminal, and navigated to the working folder
Created and activated a virtual environment using venv
pip installed required packages as I developed the solution

### Script development

#### Data Analysis
imported the required packages
Loaded the dataset and did some high level EDA (checked the data types, checked presence of null values, descriptive statistics)
Drew up a correlation matrix using corr() method of pd.DataFrame and then represented it visually using seaborn as a heatmap
Looked at the data to try and make sense of the presented relationships amongst features and between features and targets

#### Model Evaluation
Created the feature dataset and the 2 target datasets
split the data sets into 30% testing 70% training datasets (for both targets)

Imported the required models.
Logistic regression and 4 ensemble models were used.
Created and assigned instances of the models to different variables per model

created a dictionary of {key:value} pairs in the form of {model_name : model_instance}

##### compare_models function
created a script to evaluate a single model, and them wrapped it up in a function with a for loop iterating across the dictionary of models.
The function returns a tuple of important variables, including a variable holding an instance of the best model
Model ranking was conducted using weighted F1-score of the model

##### evaluate_best_model function
Created another function to evaluate the metrics of the best_model selected. 

##### evaluate_models function
Create a final function to call both functions above, and then also perform a cross validation using 5 folds on the best model selected from above. 
The function takes in
1. selected models for evlauation, 
2. training data, 
3. testing data and 
4. target data and 

calls on the 2 prior functions. 

The function returns
1. A ranked listing of the models wth decresing accuracy (f1-scores, best model at index 0)
2. Best model as a string together with it's f1-score
3. Individual cross_validation_scores and an average of the 5 scores
4. The selected best model instance (in case it needs to be called in  a susbequent use case, like a tuning application) and
5. Lastly a classification report for the best model. 

## Requirements  
- Required libraries listed in `requirements.txt`  

## File List  

Extract Zipped File into a single project folder  
The followinge files are contained   
1. data.csv,   
2. Mintek_ML.ipynb  
3. README.MD  
4. requirements.txt  

## Usage

### Install virtual environment

Create a virtual environment using python -m venv venv_ml_model  (venv_ml_model is the name of the environment)
Activate the virtual environment by navigating to venv_ml_model\Scritps and running activate (or sometimes .\activate)  
navigate back to the root folder by using ..\..\

### Install dependencies 

Install dependencies by running python install -r requirements.txt from the root folder

### Launch the notebook
Launch the Jupyter notebook from your preferred IDE. Visual Studio Code was used for development
Select the kernel from the venv_ml_model if not already selected
Select Run All
