


# Big Data analytics and visualization



## Hands-on lab unguided



**Contents**

<!-- TOC -->

- [Big Data Analystics hands-on lab unguided](#app-modernization-hands-on-lab-unguided)
    - [Abstract and learning objectives](#abstract-and-learning-objectives)
    - [Overview](#overview)
    - [Solution architecture](#solution-architecture)
    - [Requirements](#requirements)
    - [Exercise 1: Migrate the database to Azure SQL Database](#exercise-1-migrate-the-database-to-azure-sql-database)
        - [Task 1: Provision a SQL Server](#task-1-provision-a-sql-server)
            - [Tasks to complete](#tasks-to-complete)
            - [Exit criteria](#exit-criteria)
        - [Task 2: Configure SQL Server firewall](#task-2-configure-sql-server-firewall)
            - [Tasks to complete](#tasks-to-complete-1)
            - [Exit criteria](#exit-criteria-1)
        - [Task 3: Migrate the on-premises SQL database to Azure](#task-3-migrate-the-on-premises-sql-database-to-azure)
            - [Tasks to complete](#tasks-to-complete-2)
            - [Exit criteria](#exit-criteria-2)
    - [Exercise 2: Provision App Services](#exercise-2-provision-app-services)
        - [Task 1: Create a Web App](#task-1-create-a-web-app)
            - [Tasks to complete](#tasks-to-complete-3)
            - [Exit criteria](#exit-criteria-3)
        - [Task 1: Provision an API App](#task-1-provision-an-api-app)
            - [Tasks to complete](#tasks-to-complete-4)
            - [Exit criteria](#exit-criteria-4)
    - [Exercise 3: Identity and security](#exercise-3-identity-and-security)
        - [Task 1: Create a new Contoso user](#task-1-create-a-new-contoso-user)
            - [Tasks to complete](#tasks-to-complete-5)
            - [Exit criteria](#exit-criteria-5)
        - [Task 2: Register the Web API application](#task-2-register-the-web-api-application)
            - [Tasks to complete](#tasks-to-complete-6)
            - [Exit criteria](#exit-criteria-6)
        - [Task 3: Expose Web API to other applications](#task-3-expose-web-api-to-other-applications)
            - [Tasks to complete](#tasks-to-complete-7)
            - [Exit criteria](#exit-criteria-7)
        - [Task 4: Register the Desktop (WinForms) application](#task-4-register-the-desktop-winforms-application)
            - [Tasks to complete](#tasks-to-complete-8)
            - [Exit criteria](#exit-criteria-8)
        - [Task 5: Register the mobile application](#task-5-register-the-mobile-application)
            - [Tasks to complete](#tasks-to-complete-9)
            - [Exit criteria](#exit-criteria-9)
        - [Task 6: Configure access control for the PolicyConnect web application](#task-6-configure-access-control-for-the-policyconnect-web-application)
            - [Tasks to complete](#tasks-to-complete-10)
            - [Exit criteria](#exit-criteria-10)
        - [Task 7: Grant the ContosoInsurance Web app permissions to the Web API app](#task-7-grant-the-contosoinsurance-web-app-permissions-to-the-web-api-app)
            - [Tasks to complete](#tasks-to-complete-11)
            - [Exit criteria](#exit-criteria-11)
    - [Exercise 4: Upload PDFs to Blob storage](#exercise-4-upload-pdfs-to-blob-storage)
        - [Task 1: Provision a storage account](#task-1-provision-a-storage-account)
            - [Tasks to complete](#tasks-to-complete-12)
            - [Exit criteria](#exit-criteria-12)
        - [Task 2: Create container for storing PDFs in Azure storage](#task-2-create-container-for-storing-pdfs-in-azure-storage)
            - [Tasks to complete](#tasks-to-complete-13)
            - [Exit criteria](#exit-criteria-13)
        - [Task 3: Bulk upload PDFs to blob storage using AzCopy](#task-3-bulk-upload-pdfs-to-blob-storage-using-azcopy)
            - [Tasks to complete](#tasks-to-complete-14)
            - [Exit criteria](#exit-criteria-14)
    - [Exercise 5: Create serverless API for accessing PDFs](#exercise-5-create-serverless-api-for-accessing-pdfs)
        - [Task 1: Provision a Function App](#task-1-provision-a-function-app)
            - [Tasks to complete](#tasks-to-complete-15)
            - [Exit criteria](#exit-criteria-15)
        - [Task 2: Retrieve URL for policy documents in Azure stoage](#task-2-retrieve-url-for-policy-documents-in-azure-stoage)
            - [Tasks to complete](#tasks-to-complete-16)
            - [Exit criteria](#exit-criteria-16)
        - [Task 3: Create an Azure Functions Proxy](#task-3-create-an-azure-functions-proxy)
            - [Tasks to complete](#tasks-to-complete-17)
            - [Exit criteria](#exit-criteria-17)
        - [Task 4: Parameterize Azure Functions Proxy](#task-4-parameterize-azure-functions-proxy)
            - [Tasks to complete](#tasks-to-complete-18)
            - [Exit criteria](#exit-criteria-18)
    - [Exercise 6: Create an Azure Search service](#exercise-6-create-an-azure-search-service)
        - [Task 1: Create an Azure search service](#task-1-create-an-azure-search-service)
            - [Tasks to complete](#tasks-to-complete-19)
            - [Exit criteria](#exit-criteria-19)
        - [Task 2: Configure full-text search indexing](#task-2-configure-full-text-search-indexing)
            - [Tasks to complete](#tasks-to-complete-20)
            - [Exit criteria](#exit-criteria-20)
    - [Exercise 7: Configure Key Vault](#exercise-7-configure-key-vault)
        - [Task 1: Create a new Key Vault](#task-1-create-a-new-key-vault)
            - [Tasks to complete](#tasks-to-complete-21)
            - [Exit criteria](#exit-criteria-21)
        - [Task 2: Create a new secret to store the SQL connection string](#task-2-create-a-new-secret-to-store-the-sql-connection-string)
            - [Tasks to complete](#tasks-to-complete-22)
            - [Exit criteria](#exit-criteria-22)
        - [Task 3: Grant access to the secret to the Web API application](#task-3-grant-access-to-the-secret-to-the-web-api-application)
            - [Tasks to complete](#tasks-to-complete-23)
            - [Exit criteria](#exit-criteria-23)
    - [Exercise 8: Configure and deploy the Contoso Insurance Web API](#exercise-8-configure-and-deploy-the-contoso-insurance-web-api)
        - [Task 1: Add Application Settings to the API App](#task-1-add-application-settings-to-the-api-app)
            - [Tasks to complete](#tasks-to-complete-24)
            - [Exit criteria](#exit-criteria-24)
        - [Task 2: Deploy the Web API app from Visual Studio](#task-2-deploy-the-web-api-app-from-visual-studio)
            - [Tasks to complete](#tasks-to-complete-25)
            - [Exit criteria](#exit-criteria-25)
        - [Task 3: Verify the Web API deployment](#task-3-verify-the-web-api-deployment)
            - [Tasks to complete](#tasks-to-complete-26)
            - [Exit criteria](#exit-criteria-26)
    - [Exercise 9: Configure and deploy the Contoso Insurance web app](#exercise-9-configure-and-deploy-the-contoso-insurance-web-app)
        - [Task 1: Configure application settings in Azure](#task-1-configure-application-settings-in-azure)
            - [Tasks to complete](#tasks-to-complete-27)
            - [Exit criteria](#exit-criteria-27)
        - [Task 2: Deploy the Contoso Insurance Web App from Visual Studio](#task-2-deploy-the-contoso-insurance-web-app-from-visual-studio)
            - [Tasks to complete](#tasks-to-complete-28)
            - [Exit criteria](#exit-criteria-28)
        - [Task 3: Login and verify the Web App deployment](#task-3-login-and-verify-the-web-app-deployment)
            - [Tasks to complete](#tasks-to-complete-29)
            - [Exit criteria](#exit-criteria-29)
    - [Exercise 10: Configure and run the legacy desktop (Windows Forms) application](#exercise-10-configure-and-run-the-legacy-desktop-windows-forms-application)
        - [Task 1: Configure application settings in App.config](#task-1-configure-application-settings-in-appconfig)
            - [Tasks to complete](#tasks-to-complete-30)
            - [Exit criteria](#exit-criteria-30)
        - [Task 2: Run the desktop application](#task-2-run-the-desktop-application)
            - [Tasks to complete](#tasks-to-complete-31)
            - [Exit criteria](#exit-criteria-31)
    - [Exercise 11: Configure and run the mobile application](#exercise-11-configure-and-run-the-mobile-application)
        - [Task 1: Configure application settings in ApplicationSettings.cs](#task-1-configure-application-settings-in-applicationsettingscs)
            - [Tasks to complete](#tasks-to-complete-32)
            - [Exit criteria](#exit-criteria-32)
        - [Task 2: Run the mobile application](#task-2-run-the-mobile-application)
            - [Task to complete](#task-to-complete)
            - [Exit criteria](#exit-criteria-33)
    - [Exercise 12: Create a Flow app that sends push notifications](#exercise-12-create-a-flow-app-that-sends-push-notifications)
        - [Task 1: Sign up for a Flow account](#task-1-sign-up-for-a-flow-account)
            - [Tasks to complete](#tasks-to-complete-33)
            - [Exit criteria](#exit-criteria-34)
        - [Task 2: Create new flow](#task-2-create-new-flow)
            - [Tasks to complete](#tasks-to-complete-34)
            - [Exit criteria](#exit-criteria-35)
        - [Task 3: Test your flow](#task-3-test-your-flow)
            - [Tasks to complete](#tasks-to-complete-35)
            - [Exit criteria](#exit-criteria-36)
    - [Exercise 13: Create an app in PowerApps](#exercise-13-create-an-app-in-powerapps)
        - [Task 1: Sign up for a PowerApps account](#task-1-sign-up-for-a-powerapps-account)
            - [Tasks to complete](#tasks-to-complete-36)
            - [Exit criteria](#exit-criteria-37)
        - [Task 2: Create a new SQL connection](#task-2-create-a-new-sql-connection)
            - [Tasks to complete](#tasks-to-complete-37)
            - [Exit criteria](#exit-criteria-38)
        - [Task 3: Create a new app](#task-3-create-a-new-app)
            - [Tasks to complete](#tasks-to-complete-38)
            - [Exit criteria](#exit-criteria-39)
        - [Task 4: Design app](#task-4-design-app)
            - [Tasks to complete](#tasks-to-complete-39)
            - [Exit criteria](#exit-criteria-40)
        - [Task 5: Edit the app settings and run the app](#task-5-edit-the-app-settings-and-run-the-app)
            - [Tasks to complete](#tasks-to-complete-40)
            - [Exit criteria](#exit-criteria-41)
    - [Exercise 14: Add Azure Function to Azure API Management](#exercise-14-add-azure-function-to-azure-api-management)
        - [Task 1: Provision Azure API Management](#task-1-provision-azure-api-management)
            - [Tasks to complete](#tasks-to-complete-41)
            - [Exit criteria](#exit-criteria-42)
        - [Task 2: Add API Definition to Function App](#task-2-add-api-definition-to-function-app)
            - [Tasks to complete](#tasks-to-complete-42)
            - [Exit criteria](#exit-criteria-43)
        - [Task 3: Import the Funtion App to API Management(APIM)](#task-3-import-the-funtion-app-to-api-managementapim)
            - [Tasks to complete](#tasks-to-complete-43)
            - [Exit criteria](#exit-criteria-44)
        - [Task 4: Test the APIM Developer Portal](#task-4-test-the-apim-developer-portal)
            - [Tasks to complete](#tasks-to-complete-44)
            - [Exit criteria](#exit-criteria-45)
    - [After the hands-on lab](#after-the-hands-on-lab)
        - [Task 1: Delete the Resource group in which you placed your Azure resources.](#task-1-delete-the-resource-group-in-which-you-placed-your-azure-resources)
        - [Task 2: Delete the Azure Active Directory app registrations for Desktop and Mobile](#task-2-delete-the-azure-active-directory-app-registrations-for-desktop-and-mobile)
        - [Task 3: Delete Flow](#task-3-delete-flow)
    - [Appendix A: Create a self-signed certificate](#appendix-a-create-a-self-signed-certificate)
        - [Task 1: Create self-signed certificate](#task-1-create-self-signed-certificate)
        - [Task 2: Create and install your temporary service certificate](#task-2-create-and-install-your-temporary-service-certificate)
        - [Task 3: Configure the IIS Express self-signed certificate](#task-3-configure-the-iis-express-self-signed-certificate)

<!-- /TOC -->

# App modernization hands-on lab unguided

## Abstract and learning objectives

In this hands-on lab, you will implement the steps to modernize legacy on-premises applications and infrastructure by leveraging cloud services, while adding a mix of web and mobile services, all secured using Azure Active Directory.

At the end of this hands-on lab, you will be better able to build solutions for modernizing legacy on-premises applications and infrastructure using cloud services, and implement a mix of web and mobile services secured by Azure Active Directory.

## Overview

The App Modernization hands-on lab is an exercise that will challenge you to implement an end-to-end scenario using a supplied sample that is based on Microsoft Azure App Services and related services. The scenario will include implementing compute, storage, security, and search, using various components of Microsoft Azure. The hands-on lab can be implemented on your own, but it is highly recommended to pair up with other members at the lab to model a real-world experience and to allow each member to share their expertise for the overall solution.

## Solution architecture

After lawyers affirmed that Contoso, Ltd. could legally store customer data in the cloud, Contoso created a strategy that capitalized on the capabilities of Microsoft Azure. Below is a diagram of the solution architecture you will build in the lab. Please study this carefully, so you understand the whole of the solution as you are working on the various components.

![Architecture diagram of the preferred solution. Mobile and web apps connect APIs and Azure Functions Proxies, secured by Azure AD, with application secrets stored in Key Vault. Redis Cache is used to improve application performance, and data is stored in SQL Server and Azure Blob Storage. PowerApps and Flow are used to enable business users to build mobile and web (CRUD) applications. Azure API Management is used to provide an API Store experience for developers.](media/unguided-image2.png "Solution architecture")

The solution begins with mobile apps (built for Android and iOS using **Xamarin**) and a website, both of which provide access to PolicyConnect. The website, hosted in a **Web App**, provides the user interface for browser-based clients, whereas the Xamarin Forms-based apps provide the UI to mobile devices. Both mobile app and website rely on web services hosted in an **API App**. In addition to the API App, a lightweight, serverless API is provided by **Azure Functions Proxies** to provide access to policy documents stored in **Blob Storage**. **Azure API Management** is used as a proof of concept for the future goal to create a API Store for development teams and affiliated partners. Sensitive configuration data, like connection strings, are stored in **Key Vault** and accessed from the API App or Web App on demand so that these settings never live in their file system. Full-text search of policy documents is enabled by the Indexer for **Blob Storage** (which indexes text in the Word and PDF documents) and stores the results in an **Azure Search** index. **PowerApps** enable authorized business users to build mobile and web create, read, update, delete (CRUD) applications that interact with **SQL Database** and Azure Storage, while **Microsoft Flow** enables orchestrations between services such as Office 365 email and services for sending mobile notifications. These orchestrations can be used independently of PowerApps or invoked by PowerApps to provide additional logic. The solution uses user and application identities maintained in **Azure AD**.

## Requirements

-   Microsoft Azure subscription (non-Microsoft subscription).

-   **Global Administrator role** for Azure AD within your subscription.

-   Local machine or a virtual machine configured with (**complete the day before the lab!**):

    -   Visual Studio Community 2017 or greater

    -   Visual Studio 2017 workloads for:

        -   Azure development

        -   Mobile development with .NET

    -   SQL Server 2017 Express or greater

    -   SQL Server Management Studio (SSMS)

    -   PowerShell 1.1.0 or higher


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

#### Exit criteria 

-   Exit Criteria 1

-   Exit Criteria 1

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

-   

#### Exit criteria 

-   You are able to access the database and tables in Azure SQL Database via SSMS.

### Task 2: Open Azure Databricks and complete lab notebooks

#### Tasks to complete

-   Task 1

#### Exit criteria 

-   Exit Criteria 1
-   
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

-   Task 1

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

-   Task 1

#### Exit criteria 

-   Exit Criteria 1


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

## Exercise 7: Visualizing in Power BI Desktop

Duration: 20 minutes

In this exercise, you will create visualizations in Power BI Desktop.

## Exercise 8: Deploy intelligent web app (Optional)

#### Tasks to complete

-   Create Azure Databricks Linked Service

#### Exit criteria 

-   Exit Criteria 1
