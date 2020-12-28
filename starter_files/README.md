
# Operationalizing Machine Learning

Project Overview: In this project we have used the Bank Marketing Dataset which I have downloaded from the link provided in the project information.
In the project I have used Azure to configure a cloud based machine learning production model, deployed it and then consumed it. I have also created, published and consumed a pipeline using Python SDK.

Project Link: https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv


## Architectural Diagram
 ![Architectural Diagram](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Architectural%20Diagram.png "Architectural Diagram")

## Key Steps
*Step 1*: Create and run AUto ML Experiment

>a. I have uploaded the dataset into the Azure Studio and created a Registered Dataset
>Registered Dataset
![Registered Dataset](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step1-Registered%20Dataset.JPG "Registered Dataset")

>b. Configure a new compute cluster (VM size is Standard_VS12_v2 and minimum nodes is 1) and create a new Automated ML Run. Once the Experiment is completed you can see the Best Model.
>AutoMl Experiment Completed
![AutoML Experiment Completed](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step1-Experiment%20Completed.JPG "AutoML Experiment Completed")

>Best Model
>![Best Model](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step1-Best%20Model.JPG "Best Model-Voting Ensemble")

*Step 2*: Deploy the Model

>I have selected the Best Model for Deployment, enabled authentication and deployed the model using Azure Container Instance.
>Deployment Settings
>![Deployment Settings](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step3-Deploying%20the%20Model%20Settings.JPG "Deploying the Best Model")

*Step 3*: Enable Application Insights and retrieve logs

>a. Enabled Application Insights using Python SDK 
>Application Insights enabled by running logs.py script
>![Application Insights](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step4-Application%20Insights-Enabled.JPG "Application Insights")

>b. View the logs in the terminal after we run the logs.py script
>Logs
>![Logs](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step4-Logs%20by%20logs.py-a.JPG "logs")
>![Logs](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step4-Logs%20by%20logs.py-b.JPG "logs")
>![Logs](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step4-Logs%20by%20logs.py-c.JPG "logs")

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
