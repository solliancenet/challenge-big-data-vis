


# Big Data analytics and visualization



## Hands-on lab unguided



**Contents**

<!-- TOC -->

- [Big Data Analystics hands-on lab unguided](#app-modernization-hands-on-lab-unguided)
    - [Abstract and learning objectives](#abstract-and-learning-objectives)
    - [Overview](#overview)
    - [Solution architecture](#solution-architecture)
    - [Excercise 0: Setup](#setup)
        - [Task 1: Complete Before The Challenge](before-challenge.md)
    - [Exercise 1: Retrieve lab environment information and create Databricks cluster](#exercise-1-retireve-lab-environment-information-and-create-databricks-cluster)
        - [Task 1: Retrieve Azure Storage account information and Subscription Id](#task-1-retrieve-azure-storage-account-information-and-subscription-id)
        - [Task 2: Create an Azure Databricks cluster](#task-2-create-an-azure-databricks-cluster)
    - [Exercise 2: Load Sample Data and Databricks Notebooks](#exercise-2-load-sample-data-and-databricks-notebooks)
        - [Task 1: Upload the Sample Datasets](#task-1-upload-the-sample-datasets)
        - [Task 2: Open Azure Databricks and complete lab notebooks](#task-2-open-azure-databricks-and-complete-lab-notebooks)
    - [Exercise 3: Setup Azure Data Factory](#exercise-3-setup-azure-data-factory)
        - [Task 1: Download and stage data to be processed](#task-1-download-and-stage-data-to-be-processed)
        - [Task 2: Install and configure Azure Data Factory Integration Runtime on your machine](#task-2-install-and-configure-azure-data-factory-integration-runtime-on-your-machine)
        - [Task 3: Configure Azure Data Factory](#task-3-configure-azure-data-factory)
    - [Exercise 4: Develop a data factory pipeline for data movement](#exercise-4-develop-a-data-factory-pipeline-for-data-movement)
         - [Task 1: Create copy pipeline using the Copy Data Wizard](#task-1-create-copy-pipeline-using-the-copy-data-wizard)
    - [Exercise 5: Operationalize ML scoring with Azure Databricks and Data Factory](#exercise-5-operationalize-ml-scoring-with-azure-databricks-and-datafactory)
        - [Task 1: Create Azure Databricks Linked Service](#task-1-create-azure-databricks-linked-service)
        - [Task 2: Trigger workflow](#task-2-trigger-workflow)
    - [Exercise 6: Summarize data using Azure Databricks](#exercise-6-summarize-data-using-azure-databricks)
        - [Task 1: Summarize delays by airport](#task-1-summarize-delays-by-airport)
    - [Exercise 7: Visualizing in Power BI Desktop](#exercise-7-visualizing-in-powwer-bi)
        - [Task 1: Obtain the JDBC connection string to your Azure Databricks cluster](#task-1-obtain-the-jdbc-connection-string-to-your-azure-databricks-cluster)
        - [Task 2: Connect to Azure Databricks using Power BI Desktop](#task-2-connect-to-azure-databricks-using-power-bi-desktop)
        - [Task 3: Create Power BI report](#task-3-create-power-bi-report)
    - [Exercise 8: Deploy intelligent web app (Optional)I](#exercise-8-deploy-intelligent-web-app-optional)
        - [Task 1: Register for an OpenWeather account](#task-1-register-for-an-openweather-account)
        - [Task 2: Deploy web app from GitHub](#task-2-deploy-web-app-from-github)
        - [Task 3: Manual deployment (optional)](#task-3-manual-deployment-optional)
    - [After the hands-on lab](#after-the-hands-on-lab)
        - [Task 1: Delete resource group](#task-1-delete-resource-group)
<!-- /TOC -->

## Abstract and learning objectives

This hands-on lab is designed to provide exposure to many of Microsoft's transformative line of business applications built using Microsoft big data and advanced analytics.

By the end of the lab, you will be able to show an end-to-end solution, leveraging many of these technologies but not necessarily doing work in every component possible.

## Overview

Margie's Travel (MT) provides concierge services for business travelers. In an increasingly crowded market, they are always looking for ways to differentiate themselves and provide added value to their corporate customers.

They are looking to pilot a web app that their internal customer service agents can use to provide additional information useful to the traveler during the flight booking process. They want to enable their agents to enter in the flight information and produce a prediction as to whether the departing flight will encounter a 15-minute or longer delay, considering the weather forecast for the departure hour.

## Solution architecture

Below is a diagram of the solution architecture you will build in this lab. Please study this carefully, so you understand the whole of the solution as you are working on the various components.

![The high-level overview diagram of the end-to-end solution is displayed. Flight delay data and historical airport weather data are provided to Azure Data Factory. Azure Data Factory provides this data to both blob storage and Azure Databricks. Azure Databricks scores the data and saves the results to a local table. Azure Databricks also creates, trains, and exports a machine learning model to the Azure Machine Learning Service. Azure Machine Learning service provides a containerized services that is consumed by the web portal. The web portal also consumes 3rd party API data for forecasted weather. Map data visualization is provided by Power BI using web portal information and the Azure Databricks table.](media/high-level-overview.png 'High-level overview diagram')

## Excercise 0: Setup

1. Microsoft Azure subscription must be pay-as-you-go or MSDN.

   - Trial subscriptions will not work.

2. If you are not a Service Administrator or Co-administrator for the Azure subscription, or if you are running the lab in a hosted environment, you will need to install [Visual Studio 2019 Community](https://visualstudio.microsoft.com/downloads/) with the **ASP.NET and web development** and **Azure development** workloads.

3. Follow all the steps provided in [Before the Challenge](before-challenge.md).
## Exercise 1: Retrieve lab environment information and create Databricks cluster

Duration: 10 minutes

In this exercise, you will retrieve your Azure Storage account name and access key and your Azure Subscription Id and record the values to use later within the lab. You will also create a new Azure Databricks cluster.

### Task 1: Retrieve Azure Storage account information and Subscription Id

You will need to have the Azure Storage account name and access key when you create your Azure Databricks cluster during the lab. You will also need to create storage containers in which you will store your flight and weather data files.

#### Tasks to complete

-   Retrieve Strorage Account Name, Access Keys

Hints / tips:
this can be done via the portal, Azure CLI ior PowerShell

#### Exit criteria 

-   You have the necessary storage account information

### Task 2: Create an Azure Databricks cluster

You have provisioned an Azure Databricks workspace, and now you need to create a new cluster within the workspace. Part of the cluster configuration includes setting up an account access key to your Azure Storage account using the Spark Config within the new cluster form. This will allow your cluster to access the lab files.

Expected configuration:
   - **Cluster Name**: `lab`

   - **Cluster Mode**: **Standard**

   - **Databricks Runtime Version**: **Runtime: 9.1 LTS ML (Scala 2.12, Spark 3.1.2)**

   - **Enable Autoscaling**: **Uncheck** this option.

   - **Terminate after**: **Check** the box and enter `120`

   - **Worker Type**: **Standard_F4**

   - **Driver Type**: **Same as worker**

   - **Workers**: `1`


#### Tasks to complete

-   Create a Databricks cluster with the required configuration
-   Create an Access Token
-   Import the sample notebooks 
-   Mount or configure access to remote storage

#### Exit criteria 

    - create and document an accesss token (for use later)  

    - Import sample notebooks from: https://github.com/microsoft/MCW-Big-data-analytics-and-visualization/blob/main/Hands-on%20lab/lab-files/BigDataVis.dbc?raw=true

## Exercise 2: Load Sample Data and Databricks Notebooks

Duration: 60 minutes

In this exercise, you will implement a classification experiment. You will load the training data from your local machine into a dataset. Then, you will explore the data to identify the primary components you should use for prediction and use two different algorithms for predicting the classification. You will then evaluate the performance of both algorithms and choose the algorithm that performs best. The model selected will be exposed as a web service integrated with the optional sample web app at the end.

### Task 1: Upload the Sample Datasets

1. Before you begin working with machine learning services, there are three datasets you need to load.

2. Download the three CSV sample datasets from here: <http://bit.ly/2wGAqrl> (If you get an error, or the page won't open, try pasting the URL into a new browser window and verify the case sensitive URL is exactly as shown). If you are still having trouble, a zip file called AdventureWorksTravelDatasets.zip is included in the lab-files folders.

3. Extract the ZIP and verify you have the following files:

   - FlightDelaysWithAirportCodes.csv
   - FlightWeatherWithAirportCode.csv
   - AirportCodeLocationLookupClean.csv

#### Tasks to complete
    - Load Sample Data From Storage (Local or remote) by creating external tables

#### Exit criteria 
  - the following external tables exist
    -   flight_delays_with_airport_codes
    -   airport_code_location_lookup_clean
    -   flight_weather_with_airport_code


-   You are able to access the database and tables in Azure SQL Database via SSMS.

### Task 2: Open Azure Databricks and complete lab notebooks

#### Tasks to complete

 - Run through each activity in the notebook where needed complete missing code or resolve any errors that occur
    -   01 Data Preparation
    -   02 Train and Evaluate Models
    -   03 Deploy as Web Service

#### Exit criteria 

 - Data Preparation 
 - train and Evaluate model
 - Deploy Model as Web Service

## Exercise 3: Setup Azure Data Factory

Duration: 20 minutes

In this exercise, you will create a baseline environment for Azure Data Factory development to further operationalize data movement and processing. You will create a Data Factory service and then install the Data Management Gateway, which is the agent that facilitates data movement from on-premises to Microsoft Azure.

### Task 1: Download and stage data to be processed

#### Tasks to complete

-   Configure Azure Data Factory
-   Install and configure Azure Data Factory Integration Runtime on your machine

#### Exit criteria 

-  

### Task 2: Configure Azure Data Factory

#### Tasks to complete

-   Provision Azure Data Factory
-   Connect to Azure DevOps / Github for Source Control Integration
-   install and Configure Self-hosted integration runtime on On-Premises VM

#### Exit criteria 

-   Exit Criteria 1

### Task 3: Install and configure Azure Data Factory Integration Runtime on your machine


#### Tasks to complete

-   Task 1

#### Exit criteria 

-   Exit Criteria 1

## Exercise 4: Develop a data factory pipeline for data movement

Duration: 20 minutes

In this exercise, you will create an Azure Data Factory pipeline to copy data (.CSV files) from an on-premises server (your machine) to Azure Blob Storage. The goal of the exercise is to demonstrate data movement from an on-premises location to Azure Storage (via the Integration Runtime).

#### Tasks to complete

-  Copy Flight Delay Data from parquet file to ADLS gen2 storage
-  Copy Airport code data from On-premises SQL server to ADLS gen2 storage  
-  Copy Flights and weather data from On-premises Server to ADLS gen2 Storage

#### Exit criteria 

-   The flight Delay data exists in ADLS Gen2 as a parquet file
-   The airport code data exists in ADLS Gen2 Storage as a parquet file


## Exercise 5: Operationalize ML scoring with Azure Databricks and Data Factory

Duration: 20 minutes

In this exercise, you will extend the Data Factory to operationalize data scoring using the previously created machine learning model within an Azure Databricks notebook.

#### Tasks to complete

-   Create Azure Databricks Linked Service

#### Exit criteria 

-   Exit Criteria 1


## Exercise 6: Summarize data using Azure Databricks

Duration: 10 minutes

In this exercise, you will prepare a summary of flight delay data using Spark SQL.


#### Tasks to complete
-   Create Azure Databricks Linked Service

#### Exit criteria 

-   Exit Criteria 1



## Exercise 7: Visualizing in Power BI Desktop

Duration: 20 minutes

In this exercise, you will create visualizations in Power BI Desktop.

## Exercise 8: Deploy intelligent web app (Optional)

#### Tasks to complete

-   Create Azure Databricks Linked Service

#### Exit criteria 

-   Exit Criteria 1
