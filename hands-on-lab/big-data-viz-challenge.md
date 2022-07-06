# Technical Applications Workshop: Big Data Analytics and Visualization Challenge

July 2022

- [Big Data analytics and visualization](#technical-applications-workshop-big-data-analytics-and-visualization-challenge)
  - [Abstract and learning objectives](#abstract-and-learning-objectives)
  - [Overview](#overview)
  - [Solution architecture](#solution-architecture)
  - [Challenge 0: Environment Setup](#challenge-0-environment-setup)
    - [Challenge 0 tasks to complete](#challenge-0-tasks-to-complete)
    - [Challenge 0 success criteria](#challenge-0-success-criteria)
  - [Challenge 1: Retrieve lab environment information and create Databricks cluster](#challenge-1-retrieve-lab-environment-information-and-create-databricks-cluster)
    - [Challenge 1 tasks to complete](#challenge-1-tasks-to-complete)
    - [Challenge 1 success criteria](#challenge-1-success-criteria)
    - [Challenge 1 Hints, Tips, and Resources](#challenge-1-hints-tips-and-resources)
  - [Challenge 2: Load Sample Data and Databricks Notebooks](#challenge-2-load-sample-data-and-databricks-notebooks)
    - [Challenge 2 tasks to complete](#challenge-2-tasks-to-complete)
    - [Challenge 2 success criteria](#challenge-2-success-criteria)
    - [Challenge 2 Hints, Tips, and Resources](#challenge-2-hints-tips-and-resources)
  - [Challenge 3: Setup Azure Data Factory](#challenge-3-setup-azure-data-factory)
    - [Challenge 3 tasks to complete](#challenge-3-tasks-to-complete)
    - [Challenge 3 success criteria](#challenge-3-success-criteria)
    - [Challenge 3 Hints, Tips, and Resources](#challenge-3-hints-tips-and-resources)
  - [Challenge 4: Develop a data factory pipeline for data movement](#challenge-4-develop-a-data-factory-pipeline-for-data-movement)
    - [Challenge 4 tasks to complete](#challenge-4-tasks-to-complete)
    - [Challenge 4 success criteria](#challenge-4-success-criteria)
    - [Challenge 4 Hints, Tips, and Resources](#challenge-4-hints-tips-and-resources)
  - [Challenge 5: Operationalize ML scoring with Azure Databricks and Data Factory](#challenge-5-operationalize-ml-scoring-with-azure-databricks-and-data-factory)
    - [Challenge 5 tasks to complete](#challenge-5-tasks-to-complete)
    - [Challenge 5 success criteria](#challenge-5-success-criteria)
    - [Challenge 5 Hints, Tips, and Resources](#challenge-5-hints-tips-and-resources)
  - [Challenge 6: Summarize data using Azure Databricks](#challenge-6-summarize-data-using-azure-databricks)
    - [Challenge 6 tasks to complete](#challenge-6-tasks-to-complete)
    - [Challenge 6 success criteria](#challenge-6-success-criteria)
    - [Challenge 6 Hints, Tips, and Resources](#challenge-6-hints-tips-and-resources)
  - [Challenge 7: Visualizing in Power BI Desktop](#challenge-7-visualizing-in-power-bi-desktop)
    - [Challenge 7 tasks to complete](#challenge-7-tasks-to-complete)
    - [Challenge 7 success criteria](#challenge-7-success-criteria)
    - [Challenge 7 Hints, Tips, and Resources](#challenge-7-hints-tips-and-resources)
  - [Challenge 8: Deploy intelligent web app (Optional)](#challenge-8-deploy-intelligent-web-app-optional)
    - [Challenge 8 tasks to complete](#challenge-8-tasks-to-complete)
    - [Challenge 8 success criteria](#challenge-8-success-criteria)
    - [Challenge 8 Hints, Tips, and Resources](#challenge-8-hints-tips-and-resources)
  - [Conclusion](#conclusion)
  - [References](#references)
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

## Challenge 0: Environment Setup

### Challenge 0 tasks to complete
1. Microsoft Azure subscription must be pay-as-you-go or MSDN.

   - Trial subscriptions will not work.

2. If you are not a Service Administrator or Co-administrator for the Azure subscription, or if you are running the lab in a hosted environment, you will need to install [Visual Studio 2019 Community](https://visualstudio.microsoft.com/downloads/) with the **ASP.NET and web development** and **Azure development** workloads.

3. Follow all the steps provided in [Before the Challenge](before-challenge.md).

### Challenge 0 success criteria

1. You have successfully created an Azure resource group and populated it with the services provisioned by the provided ARM template.

## Challenge 1: Retrieve lab environment information and create Databricks cluster

Duration: 10 minutes

In this Challenge, you will retrieve your Azure Storage account name and access key and your Azure Subscription Id and record the values to use later within the lab. You will also create a new Azure Databricks cluster.

### Challenge 1 Tasks to complete

1. Task 1: Retrieve Azure Storage account information and Subscription Id

You will need to have the Azure Storage account name and access key when you create your Azure Databricks cluster during the lab. You will also need to create storage containers in which you will store your flight and weather data files.

2. Task 2: Create an Azure Databricks cluster

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
3. Task 3: create and document an access token (for use later)  

4. Task 4: Import sample notebooks from: https://github.com/solliancenet/challenge-big-data-vis/blob/main/hands-on-lab/hands-on-lab/lab-files/BigDataVis.dbc?raw=true 

#### Challenge 1 Success criteria 

-   You have the necessary storage account information
-   You have a working databricks cluster
-   You have an access token
-   The sample notebooks have been imported

#### Challenge 1 Hints, Tips, and Resources

-   this can be done via the portal, Azure CLI ior PowerShell

## Challenge 2: Load Sample Data and Databricks Notebooks

Duration: 60 minutes

In this Challenge, you will implement a classification experiment. You will load the training data from your local machine into a dataset. Then, you will explore the data to identify the primary components you should use for prediction and use two different algorithms for predicting the classification. You will then evaluate the performance of both algorithms and choose the algorithm that performs best. The model selected will be exposed as a web service integrated with the optional sample web app at the end.

#### Challenge 2 Tasks to complete

1. Task 1: Upload the Sample Datasets
Download the three CSV sample datasets from here: <http://bit.ly/2wGAqrl> (If you get an error, or the page won't open, try pasting the URL into a new browser window and verify the case sensitive URL is exactly as shown). If you are still having trouble, a zip file called AdventureWorksTravelDatasets.zip is included in the lab-files folders.

Extract the ZIP and verify you have the following files:

   - FlightDelaysWithAirportCodes.csv
   - FlightWeatherWithAirportCode.csv
   - AirportCodeLocationLookupClean.csv

2. Task 2: Open Azure Databricks and complete lab notebooks

 - Run through each activity in the notebook where needed complete missing code or resolve any errors that occur
    -   01 Data Preparation
    -   02 Train and Evaluate Models
    -   03 Deploy as Web Service

#### Challenge 2 Success Criteria
 -   the following external tables exist
    -   flight_delays_with_airport_codes
    -   airport_code_location_lookup_clean
    -   flight_weather_with_airport_code
-   You are able to access the tables in Azure Databricks.
- Data Preparation 
- train and Evaluate model
- Deploy Model as Web Service

## Challenge 3: Setup Azure Data Factory

Duration: 20 minutes

In this Challenge, you will create a baseline environment for Azure Data Factory development to further operationalize data movement and processing. You will create a Data Factory service and then install the Data Management Gateway, which is the agent that facilitates data movement from on-premises to Microsoft Azure.

### Challenge 3 Tasks to complete

- Task 1: Download and stage data to be processed
- Task 2: Configure Azure Data Factory
- Task 3: Install and configure Azure Data Factory Integration Runtime on your machine

### Challenge 3 Success criteria 

-  the data exists on the VM at **C:\Data**
-  Azure Data Factory is configured
-  there is a working Self-hosted integration runtime on the Virtual machine

## Challenge 4: Develop a data factory pipeline for data movement

Duration: 20 minutes

In this Challenge, you will create an Azure Data Factory pipeline to copy data (.CSV files) from an on-premises server (your machine) to Azure Blob Storage. The goal of the Challenge is to demonstrate data movement from an on-premises location to Azure Storage (via the Integration Runtime).

### Challenge 4 Tasks to complete

-  Copy Flight Delay Data from parquet file to ADLS gen2 storage
-  Copy Airport code data from On-premises SQL server to ADLS gen2 storage  
-  Copy Flights and weather data from On-premises Server to ADLS gen2 Storage

### Challenge 4 Success criteria 

-   The flight Delay data exists in ADLS Gen2 as a parquet file
-   The airport code data exists in ADLS Gen2 Storage as a parquet file


## Challenge 5: Operationalize ML scoring with Azure Databricks and Data Factory

Duration: 20 minutes

In this Challenge, you will extend the Data Factory to operationalize data scoring using the previously created machine learning model within an Azure Databricks notebook.

### Challenge 5 Tasks to complete

-   Create Azure Databricks Linked Service
-   Add a notebook Activity to Data Factory pipeline. the notebook activity should execute the notebook in **Challenge 5** folder called ***01 Deploy for Batch Scoring**
-   Trigger the pipeline

### Challenge 3 success criteria 

-   you can connect to the Azure Databricks cluster from Azure Data Factory
-   The notebook Activity has executed successfully

##### Hints, Tips, and Resources

- if the Azure databricks cluster has terminated due to inactivity you may need to manually start it as an optional task build this step into the pipeline

## Challenge 6: Summarize data using Azure Databricks

Duration: 10 minutes

In this Challenge, you will prepare a summary of flight delay data using Spark SQL.


### Challenge 6 Tasks to complete

-   Summarize delays by airport using the notebook in **Challenge 6** folder called **01 Explore Data**

### Challenge 6 success criteria 

-   Notebook has been completed

### Challenge 3 Hints, Tips, and Resources

- N/A


## Challenge 7: Visualizing in Power BI Desktop

Duration: 20 minutes

In this Challenge, you will create visualizations in Power BI Desktop.

Before you begin, you must first obtain the JDBC connection string to your Azure Databricks cluster.

the JDBC Connection string is available from the cluster configuration you will need the Server Hostname and the HTTP Path (this information will be used to create a connection from Power BI Desktop)

Create a connection from Power BI Desktop to Azure Databricks

Create a Power BI Report with 3 visualizations:

- Map visualization with Number of delays By Origin (Lat, Long)
- Tree Map visualization With Number of Delays by Origin Airport Code
- Stacked Column Chart Visualization showing Number of Delays by Day of month

Here is a sample of the finished report:

![Sample Completed  Power BI Report](media/pbi-desktop-full-report.png 'Sample Completed  Power BI Report')

### Challenge 7 Tasks to complete

- Task 1: Obtain the JDBC connection string to your Azure Databricks cluster
- Task 2: Connect to Azure Databricks using Power BI Desktop
- Task 3: Create Power BI report   

### Challenge 7 Success criteria 

- you have a working connection to the databricks server
- you have created a PBIX Report with the 3 visualizations   

### Challenge 7 Hints, Tips, and Resources

-   the Azure Databricks connection should use **direct query** mode
-   the Azure databricks connection should use **token** for the user name and the password is the same as the Access token we generated from Azure Data Factory
-   All visualizations should be linked and provide cross filter functionality
-   Feel Free to experiment with or create alternate visualizations

## Challenge 8: Deploy intelligent web app (Optional)
Duration: 20 minutes

In this Challenge, you will deploy an intelligent web application to Azure from GitHub. This application leverages the operationalized machine learning model deployed in Challenge 1 to bring action-oriented insight into an already existing business process.

Follow the instructions here to deploy the app:

https://github.com/Microsoft/MCW-Big-data-analytics-and-visualization/blob/main/Hands-on%20lab/lab-files/BigDataTravel/README.md 

You will need to provide the following values:

- Subscription / Resource Group
- Region
- ML Url (from the Azure Databricks notebook #3 in Challenge 2 folder)
- Weather API Key

Try a few different combinations of origin, destination, date, and time in the application. The information you are shown is the result of both the ML API you published, as well as information retrieved from the OpenWeather API.
### Challenge 8 Tasks to complete

- Task 1: Deploy the WebApp
- Task 2: Deploy web app from GitHub
- Task 3: Navigate to the web app and verify functionality
### Challenge 8 Success criteria 

- The web app is deployed and functional

### Challenge 8 Hints, Tips, and Resources

- if the automated deployment from the link fails you may need to download the code and manually deploy from Visual studio

## Conclusion
Congratulations! You have built and deployed an intelligent system to Azure. We started by deploying resources to azure. we created a data movement pipeline.we then did some data prepartion and created a Machine learning model. while the datasets and model choices will be different for each use case the overall process and tools will be common across solutions and problem domains.

## References

| Description | Links  |
| ----------- | ------ |
| TBD | TBD |
