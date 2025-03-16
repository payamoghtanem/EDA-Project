[![Shipping files](https://github.com/neuefische/ds-eda-project-template/actions/workflows/workflow-03.yml/badge.svg?branch=main&event=workflow_dispatch)](https://github.com/neuefische/ds-eda-project-template/actions/workflows/workflow-03.yml)
# Exploratory Data Analysis (EDA) - King County House Prices

## Objective
The objective of this project is to perform Exploratory Data Analysis (EDA) on the King County House Prices dataset. The goal is to uncover insights about how various features influence house prices. This analysis will aid in understanding housing trends, identifying key price-driving factors, and providing valuable insights for potential buyers.

## Why is EDA Important?
EDA provides crucial insights into data, ensuring that the dataset is clean, well-structured, and free from inconsistencies before modeling. The process follows the principle of "Garbage In, Garbage Out"—if the input data is unreliable, any conclusions or models built on it will also be unreliable.

## General Methodology
EDA follows an iterative process, involving the following steps:
1. **Understanding the Data**: Load and examine dataset structure, descriptive statistics, and data types.
2. **Research Questions & Hypothesis Generation**: Define key questions and hypotheses based on domain knowledge.
3. **Exploring the Data**: Analyze distributions, missing values, and outliers.
4. **Cleaning the Data**: Handle missing values, outliers, and data transformations.
5. **Investigate Relationships**: Use correlation analysis and feature engineering to identify key predictors.
6. **Presentation & Documentation**: Summarize findings, create visualizations, and generate insights.

## Workflow
### 1. Understanding the Data
- The dataset `King_County_House_prices_dataset.csv` contains 21 features, including house characteristics, location, and sale price.
- Data was loaded using pandas, and basic information such as column names, data types, and missing values were examined.
- Summary statistics were generated to understand distribution patterns.

### 2. Research Questions & Hypotheses
**Main Questions:**
- Does property size in central neighborhoods impact affordability?
- Does the timing of purchase affect house prices?
- How do condition and grade affect house prices?

**Hypotheses:**
- Smaller properties in central neighborhoods tend to be more affordable than larger ones.
- House prices fluctuate seasonally, with peaks and dips throughout the year.
- Houses in better condition and higher grade classifications are generally more expensive.

### 3. Exploring the Data
- Missing values were analyzed and visualized using `missingno`.
- Distributions of numerical and categorical features were examined using histograms and count plots.
- Outliers were identified through box plots.

### 4. Cleaning the Data
- Missing values were handled through imputation and removal where necessary.
- Data was transformed where necessary, including log transformations for skewed features.
- Feature engineering was performed:
  - **Unit Price per Square Foot**
  - **House Age Group**
  - **Categorization of House Size**
  - **Seasonal Trends from Date Feature**
  - **House Size Group**
  - **Price Group**

### 5. Investigating Relationships
- Correlation analysis was performed to identify the strongest predictors of price.
- Visualizations were generated to explore relationships between price and:
  - House size
  - Number of bedrooms/bathrooms
  - Condition and grade
  - Seasonal trends

### 6. Presenting Results
- Insights were summarized for potential buyers, focusing on affordability trends and investment strategies.
- **Key Findings:**
  - **House size is the biggest price driver.**
  - **High-quality materials significantly impact value.**
  - **Prices are highest in early spring (Feb-May) and lowest in late summer (Aug-Sep).**
  - **Smaller houses in central neighborhoods are not necessarily more affordable.**

## Requirements
- pyenv
- python==3.11.3
- altair==5.3.0
- seaborn==0.13.2
- jupyterlab==4.0.1
- ipywidgets==8.0.6
- jupyterlab-dash==0.1.0a3
- python-dotenv==1.0.0
- psycopg2-binary==2.9.7
- SQLAlchemy==2.0.15
- missingno==0.5.2

## Setup
One of the first steps when starting any data science project is to create a virtual environment. For this project you have to create this environment from scratch yourself. However, you should be already familiar with the commands you will need to do so. The general workflow consists of... 

* setting the python version locally to 3.11.3
* creating a virtual environment using the `venv` module
* activating your newly created environment 
* upgrading `pip` (This step is not absolutely necessary, but will save you trouble when installing some packages.)
* installing the required packages via `pip`

At the end, you want to make sure that people who are interested in your project can create an identical environment on their own computer in order to be able to run your code without running into errors. Therefore you can create a `requirements file` and add it to your repository. You can create such a file by running the following command: 

```bash
pip freeze > requirements.txt
```

*Note: In rare case such a requirements file created with `pip freeze` might not ensure that another (especially M1 chip) user can install and execute it properly. This can happen if libraries need to be compiled (e.g. SciPy). Then it also depends on environment variables and the actual system libraries.*

### Unit testing (Optional)
If you write python scripts for your data processing methods, you can also write unit tests. In order to run the tests execute in terminal:

```bash
pytest
```

This command will execute all the functions in your project that start with the word **test**.

## Set up your Environment
This repo contains a requirements.txt file with a list of all the packages and dependencies you will need.

Before you can start with plotly in Jupyter Lab you have to install node.js (if you haven't done it before).
- Check **Node version**  by run the following commands:
    ```sh
    node -v
    ```
    If you haven't installed it yet, begin at `step_1`. Otherwise, proceed to `step_2`.

### **`macOS`** type the following commands : 

- `Step_1:` Update Homebrew and install Node by following commands:
    ```sh
    brew update
    brew install node
    ```

- `Step_2:` Install the virtual environment and the required packages by following commands:
    ```BASH
    pyenv local 3.11.3
    python -m venv .venv
    source .venv/bin/activate
    pip install --upgrade pip
    pip install -r requirements.txt
    ```

### **`WindowsOS`** type the following commands :

- `Step_1:` Update Chocolatey and install Node by following commands:
    ```sh
    choco upgrade chocolatey
    choco install nodejs
    ```

- `Step_2:` Install the virtual environment and the required packages by following commands.

   For `PowerShell` CLI :
    ```PowerShell
    pyenv local 3.11.3
    python -m venv .venv
    .venv\Scripts\Activate.ps1
    pip install --upgrade pip
    pip install -r requirements.txt
    ```

    For `Git-Bash` CLI :
    ```BASH
    pyenv local 3.11.3
    python -m venv .venv
    source .venv/Scripts/activate
    pip install --upgrade pip
    pip install -r requirements.txt
    ```