# Linkit Beginner Challenge: Explainable ML using SHAP values

[![Lint](https://github.com/MoritzM00/Linkit-Beginner-Challenge-Explainable-ML/actions/workflows/lint.yml/badge.svg)](https://github.com/MoritzM00/Linkit-Beginner-Challenge-Explainable-ML/actions/workflows/lint.yml)
[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)][pre-commit]
[![Black](https://img.shields.io/badge/code%20style-black-000000.svg)][black]

[pre-commit]: https://github.com/pre-commit/pre-commit
[black]: https://github.com/psf/black

## Challenge Description

The goal of this challenge is to build a model that predicts whether a customer will subscribe to a term deposit or not and to explain the model using SHAP Values.

### What is a term deposit?

According to [Investopedia](https://www.investopedia.com/terms/t/termdeposit.asp), a **term deposit** (dt. Termineinlage, Termingeld) is a fixed-term investment that includes the deposit of money into an account at a financial institution. Term deposit investments usually carry short-term maturities ranging from one month to a few years and will have varying levels of required minimum deposits. The investor must understand when buying a term deposit that they can withdraw their funds _only after the term ends_. This means, that the money is locked up for some period of time.

### The dataset

The [dataset](https://archive.ics.uci.edu/ml/datasets/bank+marketing) is from the UCI Machine Learning Repository and contains information about customers of a Portuguese bank. The target variable is `deposit` and has two possible values: `yes` and `no`. For more information refer to the `challenge.ipynb` notebook.

## Evaluation

Your submissions will be evaluated based on the following criteria:

1. F1-Score on a hold-out test set
2. Explanation of the predictions:
   For a few selected test points, you will have to explain with SHAP values why the model made the prediction it did.

## Submissions

Your submission must include

- Your notebook with model training and explanation. Make sure that the submitted notebook still contains the output, i.e. do not clear the output before submitting.

## Development Instructions

You can either develop locally by cloning the repo or work in a cloud environment like Google Colab.

### Google Colab (Recommended)

You can use Google Colab to run the notebook. Just open the notebook in Colab and run the cells. No additional setup is needed.

The only downside is that google colab does not persist your data. So you have to download the data every time you open the notebook.

You may have to install some missing dependencies, that are not pre-installed in the colab environment like `shap`. This can be done by adding more libraries in the first code cell of the notebook to the line

```
%pip install -q dvc shap <more libraries here>
```

### Local Development

For local development, you can fork this repository and run the following commands to set up a virtual environment and install the required dependencies. You must have python installed on your machine. I used Python 3.10.7 for this project.

You can use your preferred method of creating a virtual environment, but we recommend using the builtin `venv`:

```bash
python3 -m venv venv
source venv/bin/activate
pip3 install -r requirements.txt
```

Pull the data from the remote storage by running:

```bash
dvc pull
```

Optionally, install development dependencies and pre-commit hooks:

```bash
pip3 install -r requirements-dev.txt
pre-commit install
```

These hooks will run on every commit and will check for linting errors and formatting issues. Optionally, you can remove the output of all cells to make it easier for version control. This part is commented out at the moment.
