# Module 06: Microsoft Defender for Cloud Integration

## Lab Scenario

In this lab, you connected your GitHub account to Microsoft Defender for Cloud (formerly Azure Defender), enhancing security monitoring and threat detection capabilities. 

## Lab objectives
In this lab, you will perform:

- Task 1: Connect your GitHub account to Microsoft Defender for Cloud

## Estimated timing: 20 minutes

## Architecture Diagram

   ![Picture1](./images/ar06.png)

## Task 1: Connect your GitHub account to Microsoft Defender for Cloud

1. In the Search bar of the Azure portal, type *Defender*, then select **Microsoft Defender for Cloud**.

   ![Picture1](./images/image1.png)

1. The **Getting Started** page will open; select **skip**.

   ![Picture1](./images/image12.jpg)

1. In the left menu for Microsoft Defender for Cloud, under Management, select **Environment settings (1)**, select **Add environment (2)** from the top and select **GitHub (3)** from dropdown.

   ![Picture1](./images/image2.png)

1. On the **GitHub Connection** page, under Account details, provide the below settings.

   | Setting  | Value |
   -----------|---------
   | Connector name | ghaz-github |
   | Resource group | Lab-VM |
   | Location | East US |
   
   ![Picture1](./images/image3.png)

1. Select **Next: Configure access**.

1. Click **Authorize** button.
       
   ![Picture1](./images/image4.png)

1. Click on **Authorize Microsoft Security Devops** to *Authorize*.
   
   ![Picture1](./images/image5.png)

1. After the authorization is complete, click on the **Install** under *Install DevOps security app*.
   
   ![Picture1](./images/image6.png)

1. Select your github organization for **All repositories** and click to **Install**.
   
   ![Picture1](./images/image7.png)
   
   ![Picture1](./images/image8.png)

1. Click on **Next : Review and generate**.
   
   ![Picture1](./images/image9.png)

1. Review your details and click on **Create**.

   ![Picture1](./images/image10.png)
   
1. After some minutes you will see the GitHub connector in the **Environment settings** page and about 15 minutes.
   
   ![Picture1](./images/image11.png)                  
   
## Review

In this lab you have completed the following:
+ Connect your GitHub account to Microsoft Defender for Cloud
