
# Operationalizing Machine Learning

Project Overview: In this project we have used the Bank Marketing Dataset which I have downloaded from the link provided in the project information.
In the project I have used Azure to configure a cloud based machine learning production model, deployed it and then consumed it. I have also created, published and consumed a pipeline using Python SDK.

Project Link: https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv


## Architectural Diagram
 ![Architectural Diagram](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Architectural%20Diagram.png "Architectural Diagram")

## Key Steps
*Step 1*: Create and run AUto ML Experiment

>a. I have uploaded the dataset into the Azure Studio and created a Registered Dataset
![Registered Dataset](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step1-Registered%20Dataset.JPG "Registered Dataset")
>b. Configure a new compute cluster (VM size is Standard_VS12_v2 and minimum nodes is 1) and create a new Automated ML Run. Once the Experiment is completed you can see the Best Model.
![AutoML Experiment Completed](https://github.com/webpagearshi/Operationalizing-ML/blob/master/starter_files/Images/Step1-Experiment%20Completed.JPG "AutoML Experiment")

## Screen Recording
*TODO* Provide a link to a screen recording of the project in action. Remember that the screencast should demonstrate:

## Standout Suggestions
*TODO (Optional):* This is where you can provide information about any standout suggestions that you have attempted.
