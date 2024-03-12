To initiate .yml based a conda env 
```
conda create --name exploratory python=3.8
conda activate coursera-exploratory
conda env export --name coursera-exploratory > conda_env.yml
```

To update env based on updated .yml file. Note that `prune` gets rid of what's no longer needed.
```
conda env update --file conda_env.yml --prune
```

To run the ML project within this directory
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

