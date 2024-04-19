# Module 06: Microsoft Defender for Cloud Integration

## Lab Scenario

In this lab, you connected your GitHub account to Microsoft Defender for Cloud (formerly Azure Defender), enhancing security monitoring and threat detection capabilities. 

## Lab Objectives
In this lab, you will perform:

- Task 1: Connect your GitHub account to Microsoft Defender for Cloud

## Estimated Timing: 20 minutes

## Architecture Diagram

   ![Picture1](./images/ar06.png)

## Task 1: Connect your GitHub account to Microsoft Defender for Cloud

1. In the search bar of the Azure portal, type *Defender*, then select **Microsoft Defender for Cloud**.

   ![Picture1](./images/image1.png)

1. The **Getting Started** page will open; select **skip**.

   ![Picture1](./images/image12.jpg)

1. In the left menu for Microsoft Defender for Cloud, under **Management**, select **Environment settings (1)**, select **Add environment (2)** from the top and then select **GitHub (3)** from the dropdown.

   ![Picture1](./images/image2.png)

1. On the **GitHub Connection** page, under Account details, provide the below settings.

   | Setting  | Value |
   -----------|---------
   | Connector name | ghaz-github |
   | Resource group | Lab-VM |
   | Location | East US |
   
   ![Picture1](./images/image3.png)

1. Select **Next: Configure access**.

1. Click the **Authorize** button.
       
   ![Picture1](./images/image4.png)

1. Click on **Authorize Microsoft Security Devops** to **Authorize**.
   
   ![Picture1](./images/image5.png)

1. After the authorization is complete, click on **Install** under the **Install DevOps security app** option.
   
   ![Picture1](./images/image6.png)

1. Select your GitHub organization for **All repositories** and click on **Install**.
   
   ![Picture1](./images/image7.png)
   
   ![Picture1](./images/image8.png)

1. Click on **Next: Review and generate**.
   
   ![Picture1](./images/image9.png)

1. Review your details and click on **Create**.

   ![Picture1](./images/image10.png)
   
1. You will get GitHub connector in the **Environment settings** page.
   
   ![Picture1](./images/image11.png)                  
   
   >**Note:** It takes around 15 minutes to arrive.

Please feel free to go through the below links for further understanding:
1. [Public Roadmap](https://github.com/orgs/github/projects/4247/views/6)
2. [Application Security](https://info.microsoft.com/US-DevOps-VDEO-FY24-02Feb-12-GitHub-and-AI-A-Powerful-Duo-for-Application-Security-Testing-SRGCM11732_LP01-Registration---Form-in-Body.html)
3. [Application Security Testing](https://www.microsoft.com/en-us/industry?rtc=1)
4. [Introducing AI-powered application security testing with GitHub Advanced Security](https://github.blog/2023-11-08-ai-powered-appsec/)

## Review

In this lab, you have completed the following:
+ Connected your GitHub account to Microsoft Defender for Cloud
