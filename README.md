# MLflow Project: Iris Model Tracking and Deployment
A comprehensive example of using **MLflow** for tracking, managing, and deploying machine learning models. This project demonstrates best practices for experiment tracking, artifact storage, and model versioning using the Iris dataset.

## Features

### 1. **Experiment Tracking**
- Tracks key metrics like accuracy, parameters, and tags for every model training run.
- Stores metadata, including training information, run names, and source scripts.

### 2. **Artifact Management**
- Logs models with supporting files such as:
  - `MLmodel` for model metadata.
  - `conda.yaml` and `requirements.txt` for environment reproducibility.
  - Serialized model (`model.pkl`).

### 3. **Model Versioning**
- Maintains multiple versions of models.
- Allows tagging of versions (e.g., `production`, `staging`).

### 4. **Deployment-Ready Models**
- Provides `serving_input_example.json` for REST API input testing.
- Logs environment files for easy deployment using MLflow's built-in tools.

## Setup

### Prerequisites
- Python 3.8+
- Install dependencies:

```bash
pip install -r requirements.txt
```

### MLflow Setup
- Start the MLflow Tracking Server:

```bash
mlflow ui
```

- Access the UI at `http://127.0.0.1:5000`.

## Usage

### 1. **Run the Example Notebook**
- Open `get-started.ipynb` to explore the basics of MLflow.
- Navigate to `MLproject/project.ipynb` for model training and artifact logging.

### 2. **Track Experiments**
- Use the `mlruns/` directory to review tracked metrics, parameters, and tags.
- View experiment runs in the MLflow UI.

### 3. **Manage Artifacts**
- Locate model artifacts in `mlartifacts/[Experiment ID]/artifacts/iris_model/`.

### 4. **Model Deployment**
- Use the `models/` directory to deploy models via:
  - **MLflow REST API**
  - **MLflow Serving**

```bash
mlflow models serve -m models:/tracking-quickstart/1
```

## Key Files and Their Purpose

### Notebooks
- **`get-started.ipynb`**: Introduction to MLflow tracking and project structure.
- **`project.ipynb`**: Main notebook for training, logging, and analyzing the Iris model.

### Artifacts
- **`MLmodel`**: Metadata for the logged model.
- **`model.pkl`**: Serialized model file for prediction.
- **Environment files**: `conda.yaml` and `requirements.txt` for reproducibility.

### Metadata
- **`meta.yaml`**: Metadata for experiment and model runs.
- **`accuracy`**: Logged metrics for model evaluation.
- **`params/`**: Hyperparameter configurations for each run.

### Tags
- Tags such as `mlflow.runName` and `mlflow.source.type` for tracking run context.
