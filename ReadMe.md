# 🗄️ mlflow for Machine Learning Model and Project Management

This repo explors `mlflow`, a toolset to centralizes tracking, packaging, and deploying machine learning experiments for reproducibility and efficient model and project management. The majority of the content comes from a coursera course offered by Duke Univ on MLOps. 

* **ML projects**: see `exploratory` folder for how to configure and run an mlproject. Each ML project utilizes an `MLproject` file to define its conda environment and entry point scripts. 
* **ML models**: see `registry` folder for model registry and versioning; and see `serve` forlder for model serving. Also below is a comparison between MLflow projects and models. 

## Difference between MLflow Projects and MLflow Models

- **Purpose**:
    - Projects: MLflow Projects are focused on packaging and reproducing machine learning code. They provide a standardized format for organizing code, specifying dependencies, and defining entry points for running machine learning experiments in a consistent and reproducible manner.
    - Models: MLflow Models, on the other hand, are focused on managing and deploying machine learning models. They provide tools for packaging models in various formats, serving them for inference, and deploying them to different environments or deployment targets.

- **Content**:
    - Projects: In MLflow Projects, you package and organize your entire machine learning codebase, including data preprocessing, model training, evaluation, and any other necessary steps. Projects can contain multiple scripts, notebooks, or other files needed to run an experiment.
    - Models: MLflow Models, on the other hand, focus specifically on the machine learning model itself. They package the trained model along with any necessary preprocessing or postprocessing steps, making it ready for serving or deployment.
    
- **Lifecycle Stage**:
    - Projects: MLflow Projects are primarily used during the development and experimentation phase of the machine learning lifecycle. They facilitate collaboration, versioning, and reproducibility of machine learning experiments.
    - Models: MLflow Models are used during the deployment and production phase of the machine learning lifecycle. They provide tools for packaging, serving, and deploying trained models to production environments.

## 🔗Useful links:

* Link to course **MLOps Tools: MLflow and Hugging Face**: https://www.coursera.org/learn/mlops-mlflow-huggingface-duke/
* Relavent repo from the course: https://github.com/alfredodeza/mlflow-demo

