# Local Model serving with MLflow

By serving a model you have the ability to interact with the model over an HTTP API. MLflow can serve models locally with a single command but there are some constraints you need to be aware of. In this example you'll serve a previously registered model.

## Start the server locally

Start the local server so that you can try this out. Try to use the default port (5000) and address (127.0.0.1) so that everything matches. Take note of the uri, making sure it is exactly the same as what you will use later. For example:

```
mlflow server --backend-store-uri sqlite:///mlflow.db --default-artifact-root /tmp/ --host 127.0.0.1:5000
```


## Serving a model by run

See the `log_model.py` file to programmatically retrieve a T5 model with HuggingFace Transformers and then register it into the UI. Then run inferece using the `curl` command on the `/invocations` API endpoint:

Inspect all tracked ml runs
```
ls mlruns/0/
```
Find ones that have model available
```
find mlruns/0/ | grep "/model$"
```
Inspect one of these models. We should be able to see the standard ML model structure for the particular model flavor. For example for pyfunc flavor, we should see at least `MLmodel`, `conda.yaml`, `python_env.yaml`, `python_model.pkl`, and `requirements.txt`. 
```
tree mlruns/0/<run-id>/artifacts/model
```
Serve one of the models as a rest API using port 5000
```
mlflow models serve -m runs:/<run-id>/model -p 5000
```
Open a different terminal window to utilize the model through the API
```
curl -X POST -H "Content-Type:application/json; format=pandas-split" --data '{"columns":["text"],"data":[["Today is a perfect day to practice automation skills"]]}' http://127.0.0.1:5000/invocations
```




