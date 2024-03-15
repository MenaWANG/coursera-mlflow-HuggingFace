An MLflow project configuration file specify the conda environment and entry point scripts (see `MLProject` in this folder). Here entry pionts refer to the scripts that can be executed within the project workflow. One cool thing to note is that mlflow project can be used to run workflow from both local files and remote git repo.

To run the demo MLflow project in this folder: 

To initiate .yml based a conda env 
```
conda create --name coursera-exploratory python=3.8
conda activate coursera-exploratory
conda env export --name coursera-exploratory > conda_env.yml
```

To update env based on updated .yml file. Note that `prune` gets rid of what's no longer needed.
```
conda env update --file conda_env.yml --prune
```

To run the ML project within this directory, just pass on the value of project parameters and run like below
```
mlflow run . -P filename=carriage.csv

```
Notice that a conda env will be created following conda_env.yml to run the project ([troubleshooting on that](https://github.com/conda/conda/issues/11795) in case needed).

mlflow will not create a new env for the next test, as the env already exist from the above run. BTW, the below command will throw an error because test.csv doesnt exist. 
```
mlflow run . -P filename=test.csv
```

To leverage mlflow ui, simply run
```
mlflow ui
```

In theory, we should be able to run a mlflow project from a remode git repo ([demo here](https://github.com/mlflow/mlflow-example/tree/master)), which is super cool (see below example from `mlflow`). Note to run the code below we need to [add ssh key to github account](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) first. But on windows machine there is [an known issue reported](https://github.com/mlflow/mlflow/issues/1670). 

```
mlflow run git@github.com:mlflow/mlflow-example.git
```

