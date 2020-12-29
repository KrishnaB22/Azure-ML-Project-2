# Operationalizing Machine Learning

## Overview
This project is part of the Udacity Azure ML Nanodegree. In this project we use Microsoft Azure to configure a cloud based machine learning production model, deploy it, consume it.
<br><br>
## Summary 
The given dataset is bank marketing dataset.  We have to predict whether a client subscribed a term deposit or not. We first create a AutoML experiment with given dataset in ML Studio to find the optimal model. The optimal model is then deployed and is consumed via a REST-endpoint.
<br><br>

## Architectural Diagram
<br>
<img src ="Screenshots/block.png">
<br><br>
<br><br>
## Key Steps
### Step 1:
The dataset is registered in Azure ML Studio by uploading the file or by using the url.<br>
https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv<br>
<br>
<img src ="Screenshots/aml dataset.png">
<br><br>
<br><br>

### Step 2:
Next a AutoML run is crested to find the best model.<br>
The best model found is Voting Ensemble with 92% accuracy.<br>
<br>
<img src ="Screenshots/aml runcomp.png"><img src ="Screenshots/aml bestmodel.png"><br>
<br><br><br><br>
The other model parameters are<br><br>
<img src ="Screenshots/bestmodel param.png">
<br><br>
<br><br>

### Step 3:
The best run model is deployed by using ML Studio in Azure Container Instances.<br>
Authentication is enabled during the deployment.<br>
<br>
<img src ="Screenshots/aml deploy.png">
<br><br>
<br><br>

### Step 4:
Application Insights are enabled by running the logs.py script on the local machine in the terminal.<br>
The output of logs.py script are:<br><br>
<img src ="Screenshots/logs execute.png">
<br><br>
<br><br>

### Step 5:
Swagger.json file is downloaded from the swagger uri.<br>
The swagger-ui is run on port 9000. The serve.py is run at port 8000.<br>
<br>
<img src ="Screenshots/swagger.png">
<img src ="Screenshots/swagger2.png">
<br><br>
<br><br>

### Step 6:
For testing the REST endpoint the rest url and the appropriate keys are pasted in the endpoint.py file.<br>
The output after running the endpoint.py file is:<br><br>
<img src ="Screenshots/endpoint execution.png">
<br><br>
<br><br>

### Step 7(optional):
The apache benchmark is run by using the benchmark.sh script.<br>
The report of benchmark is:<br><br>
<img src ="Screenshots/benchmark.png">


