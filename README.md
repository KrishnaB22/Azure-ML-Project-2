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

## Key Steps<br>
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
<img src ="Screenshots/applicationinsightenable.png">
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
The endpoint.py creates a data.json file to send over the API.<br>
The output after running the endpoint.py file is:<br><br>
<img src ="Screenshots/endpoint execution.png">
<br><br>
<br><br>

### Step 7(optional):
The apache benchmark is run by using the benchmark.sh script.<br>
The report of benchmark is:<br><br>
<img src ="Screenshots/benchmark.png">
<br><br>
<br><br>

## Notebook Output
We create consume and publish the pipeline in Azure by using the notebook.<br>
In the notebook we use a existing compute cluster and experiment to create a AutoML Pieline run.<br>
We load the already created dataset in the notebook or create a new one using <i>TabularDataset</i>.<br>
We configure AutoML using AutoMLConfig.<br>
Create the Pipeline and AutoML Step.<br>
<img src ="Screenshots/nb pipelinerun2.png">

Test the best fitted model.<br>
Generate the confusion matrix.<br>
<img src ="Screenshots/nb confusion matrix.png"><br><br>

Publish and run from REST endpoint.<br>
<img src ="Screenshots/nb pipeline end point.png">
<br><br>
<br><br>
## Outpus of Pipelne run
<br><br>
<b>Pipline Run completed.</b><br>
<img src ="Screenshots/nb pipelinecomp.png">
<br>
<img src ="Screenshots/nb runcomp.png">
<br><br>

<br><br>
<b>Pipline endpoint</b><br>
<img src ="Screenshots/ml studio pipeline endpoint.png">
<br><br>

<br><br>
<b>Published Pipline detail</b><br>
<img src ="Screenshots/ml studio pipelinedetail.png">
<br><br>

<br><br>
<b>Scheduled Pipeline running</b><br>
<img src ="Screenshots/endnb run.png">
<br><br>

<br><br>
## Screen Recording
<a href="https://drive.google.com/file/d/18t7mOZHJy5xqjgDilxeIkbCnJZSH6b_R/view">link</a>
