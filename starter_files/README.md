
# Operationalizing Machine Learning

Project Overview: In this project we have used the Bank Marketing Dataset which I have downloaded from the link provided in the project information.
In the project I have used Azure to configure a cloud based machine learning production model, deployed it and then consumed it. I have also created, published and consumed a pipeline using Python SDK.

Project Link: https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv


## Architectural Diagram
 ![Architectural Diagram](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Architectural%20Diagram.png "Architectural Diagram")

## Key Steps
In the first section we will configure a cloud based machine learning production model, deployed it and then consumed it

*Step 1*: Authentication
>Since I have used the Udacity workspace to complete this project I skipped this step as I did not have authorization to create a security principal.

*Step 2*: Create and run AUto ML Experiment

>a. I have uploaded the dataset into the Azure Studio and created a Registered Dataset

>Registered Dataset

>![Registered Dataset](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step1-Registered%20Dataset.JPG "Registered Dataset")

>b. Configure a new compute cluster (VM size is Standard_VS12_v2 and minimum nodes is 1) and create a new Automated ML Run. Once the Experiment is completed you can see the Best Model.

>AutoMl Experiment Completed

>![AutoML Experiment Completed](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step1-Experiment%20Completed.JPG "AutoML Experiment Completed")


>Best Model

>![Best Model](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step1-Best%20Model.JPG "Best Model-Voting Ensemble")


*Step 3*: Deploy the Model

>I have selected the Best Model for Deployment, enabled authentication and deployed the model using Azure Container Instance.

>Deployment Settings

>![Deployment Settings](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step3-Deploying%20the%20Model%20Settings.JPG "Deploying the Best Model")


*Step 4*: Enable Application Insights and retrieve logs

>a. Enabled Application Insights using Python SDK

>Application Insights enabled by running logs.py script

>![Application Insights](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step4-Application%20Insights-Enabled.JPG "Application Insights")

>b. View the logs in the terminal after we run the logs.py script

>Logs

>![Logs](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step4-Logs%20by%20logs.py-a.JPG "logs")
>![Logs](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step4-Logs%20by%20logs.py-b.JPG "logs")
>![Logs](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step4-Logs%20by%20logs.py-c.JPG "logs")


*Step 5*:Swagger Documentation

>Azure provides swagger json file for deployed models. Heading to the Endpoints section->Details tab we can find the Swagger URL which we can use to download the file and save locally in the same folder as swagger.sh and serve.py files. When we run the swagger.sh script we will download the latest Swagger container and run it on port 9000. Running the script serve.py will start a python server on port 8000.

>Screenshot showing that swagger runs on localhost showing the HTTP API methods and responses for the model.

>![Swagger](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step5-Swagger%20runs%20on%20localhost.JPG "swagger runs on localhost")

*Step 6*:Consume Model Endpoints and Benchmark the endpoint using Apache Benchmark

>a. Consume Model Endpoints- Head to the consume tab in the Endpoints section and then note the REST Endpoint URI and Primary Key and then in the endpoint.py file modify the scoring_uri and key to match them respectively. Now execute the enddpoint.py file and you will see the json output from the model in the terminal.

>Consume Model Endpoints

>![endpoint](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step6-Endpoint%20result.JPG "Endpoint result")

>b. Benchmarking-Make changes in the benchmark.sh file by replacing the authentication key with the primary key of the model and the REST uri with that of the model. After we have run the endpoint.py file a data.json file appears in the folder and then we will run the benchmark.sh script.

>Screenshot showing that Apache Benchmark runs against the HTTP API using authentication keys to retrieve performance results.

>![Benchmarking](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step6-Benchmark.sh%20log-a.JPG "Benchmarking")
>![Benchmarking](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step6-Benchmark.sh%20log-b.JPG "Benchmarking")
>![Benchmarking](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step6-Benchmark.sh%20log-c.JPG "Benchmarking")

Now that we have used Azure to configure a cloud based machine learning production model, deployed and consumed it we will move to the next section where we will use Python SDK to create, publish and consume a Pipeline.

*Step 7*: Create , Publish and Consume a Pipeline

> a. We will use the Auto ML Experiment which we have already run and the compute cluster we created earlier to create the Pipeline

>Pipeline Created

>![Pipeline](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step7-Pipeline%20Created%20Completed.JPG "Pipeline Created")

>BankMarketing Dataset with AutoML Module

>![Pipeline](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step7-BankMarketing%20Dataset%20with%20AutoML%20Module-Completed.JPG "AutoML Module")

>b. After the pipeline_run object is created we publish the Pipeline

>Pipeline section shows Pipeline Endpoint

>![Pipeline](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step7-Pipeline-Endpoint.JPG "published pipeline")

>Published Pipeline Overview showing a REST Endpoint and status Active

>![Pipeline](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step7-Published%20Pipeline%20Overview.JPG "Published Pipeline")

>c. Consume a Pipeline endpoint-The first step was to authenticate and then the published Pipeline was used to retrieve the endpoint using Python SDK.

>Scheduled Run in the ML Studio

>![Pipeline](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step7-Scheduled%20Run.JPG "Pipeline run")

>![Pipeline](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step7-5.JPG "Pipeline")

## Screen Recording
[Screencast Link](https://youtu.be/rdz4DlNq-pE "Screencast for Project2-Operationalizing ML)

## Standout Suggestions
>While creating the Automated ML run I would like to chose validation type instead of using auto. I would also like to enable featurization for feature selection and make changes in feature type and impute with options for the features. Examine imbalanced classes which were detected in input and rectify the issue.

>I would like to try the low priority option when creating the compute cluster and experiment with virtual machine sizes so that I can try and find a cheaper option without affecting the production model and endpoint consumption.

>Use Batch Inference Pipeline to do predictions using parallelism. This increases productivity and optimized costs.

#### The Udacity Course material and Microsoft Documentation has been used as reference.
