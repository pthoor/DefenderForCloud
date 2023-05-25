# DefenderForCloud

## Objectives
In this exercise, you will learn how to enable Defender for CSPM, and leverage Defender for CSPM Capabilities

## Exercise 1: Preparing the Environment for DCSPM plan

Pre-requisites: Deploy the Environment in **Module 1 - Preparing the Environment**

If you already finished Module 1 of this lab, (Module 1 – Preparing the Environment), you will deploy an extended environment for Defender CSPM plan.
As part of this exercise, you will create an environment using an automated deployment based on ARM template. 

The following list of resources will be deployed during the provisioning process (including dependencies like disks, network interfaces, public IP addresses, etc.):
Name | Resource Type | Purpose
-----| ------------- | -------
dcspmlab-winsrv | Virtual machine | Windows Server
dcspmlab-nix | Virtual machine | Linux Server


1.	Prepare your lab environment by clicking on the blue **Deploy to Azure** button below:

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fpthoor%2FDefenderForCloud%2Fmain%2Fdcspmlabdeploy.json)

2.	You will be redirected to **Azure Portal** > **custom deployment** page where you should specify mandatory fields for deployment.

![image](https://user-images.githubusercontent.com/102209701/215821808-99521c72-065c-4078-af9c-893ac8719e24.png)

 
3.	On the **subscription** field, select Azure subscription used in **Module 1**.
4.	On the **Resource group** field, click on **select existing** and select asclab (you can pick any name you want or keep the default).
5.	On the Instance Details section, select the data center **region** you deployed the ARM Template in **Module 1** (all downstream resources will be created in the same region as the resource group).
6.	Select **Admin Username** and **Admin password** that will be used for Windows Virtual Machine and Linux Virtual Machine you are deploying.
Notice that password must be between 12 and 72 characters and have 3 of the following: 1 lower case, 1 upper case, 1 number and 1 special character.
7.	Select **Storage Account Name** (asclabsa[uniqestring]), **Key Vault Name** (asclab-kv-[uniqestring]), and **Sql Server Name** (asclab-sql-[uniqestring]) you already deployed in Module 1. 
8.	Click **Review + create** to start the validation process. Once validation passed, click on **Create** to start the ARM deployment on your subscription.
9.	The deployment takes about **10 minutes** to complete.
The deployment is in progress page continues to update and show the resources being uploaded to the environment assuming the deployment is successful.

You can also check the progress of your deployment if you click on your created resource group details, then click on **Deployments** (1 deploying).
When the deployment is complete, you should see the following:
Name | Resource Type | Purpose
-----| ------------- | -------
dcspmlab-winsrv | Virtual machine | Windows Server
dcspmlab-nix | Virtual machine | Linux Server
