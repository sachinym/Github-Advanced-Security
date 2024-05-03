# Module 05: Scaling out GitHub Advanced Security

## Lab Scenario

The lab focuses on scaling out GitHub Advanced Security (GHAS) adoption, covering strategic approaches, security overview dashboards, webhooks integration, and repository rulesets. It emphasizes aligning GHAS rollout strategies, creating internal documentation, scaling code, and secret scanning. Additionally, it explores GHAS's security overview dashboard for insights and demonstrates webhook setup for external reporting tools like SIEM. Finally, it discusses the implementation of repository rulesets for enforcing branch and tag policies, enhancing security and compliance across repositories at scale.

## Lab Objectives
In this lab, you will perform:

- Task 1: How to grow adoption? How to communicate about GHAS internally?  
- Task 2: View the security overview dashboard and reports 
- Task 3: Review Webhooks and how they can be used to push events to an outside reporting tool, like a SIEM 
- Task 4: Talk about repository rulesets and how they can be used at scale 

## Estimated Timing: 60 minutes

## Architecture Diagram

   ![Picture1](./images/ar05.png) 

## Task 1: How to grow adoption? How to communicate about GHAS internally? [Read Only]

Adopting GitHub Advanced Security can be approached in multiple ways. It requires a strategic approach for success, especially in larger enterprises and organizations with thousands of repositories. This aims to lay the foundation for enterprises on how to adopt GHAS, but most importantly, scale it quickly and efficiently. Enabling GitHub Advanced Security across a large organization can be broken down into **six** core phases:

1. **Align your rollout strategy and goals**: Think about what success will look like, and align on how GHAS will be implemented in your company. This phase may only take a few days or a week, but it lays a solid foundation for the rest of the rollout.

1. **Preparing to enable at scale:** Prepare developers, collect data about your repositories, and ensure you're ready for the next phase.

1. **Pilot programs:** Optionally, pilot an initial rollout to a few high-impact projects and teams. This will allow an initial group within your company to get familiar with GHAS before you roll it out to the remainder of your company.

1. **Create internal documentation:** Create and communicate internal documentation for the GHAS consumers. Without proper documentation provided to developers, security engineers, and others who will be using GHAS. The value will get lost in the rollout.

1. **Rollout and scale code scanning:** Leverage the available APIs, automatically rollout code scanning by team and by language across your enterprise using the repository data you collected earlier.

1. **Rollout and scale secret scanning:** Roll out secret scanning, which involves less configuration and is therefore simpler to adopt than code scanning. Still, it's critical to have a strategy for handling new and old results.
   
**Phase One - Strategic Enablement Alignment**

Although it's appealing to rush into the implementation phase, take the time to align on how GHAS will be implemented in your enterprise. Additionally, think about what success could look like in the 3, 6, and 9 months after adoption. This phase may only take a few days or a week, but it lays a solid foundation for the rest of the rollout.

**Phase Two - Create Internal Documentation**

Like the above phase, organizations tend to rush into the implementation phase, as that stage is perceived to provide the quickest time-to-value. However, without the proper documentation and asynchronous resources provided to aid developers, security engineers, etc, in consuming GHAS correctly, the value gets lost in the rollout due to people not correctly consuming GHAS. Take the time to create internal documentation (such as training, how to remediate, where to go for questions, etc.), and then communicate this documentation (email, teams, slack, etc.) to the consumers of GHAS. So once you roll out GHAS, teams and people know what to do.

**Phase Three - Enable & Scale Code Scanning**

GHAS is an ecosystem of multiple solutions. It's essential to start somewhere focused, not just with the rollout of GHAS. Typically, teams focus on code scanning to begin with. Leverage the APIs available and rollout code scanning by the team and by language across your organization automatically. This allows you to scale in an automated fashion and removes a lot of manual repeatable groundwork for developers and consumers of code scanning. Doing this will increase adoption.

### Task 2: View the security overview dashboard and reports 

In this task, you will explore the GHAS security overview dashboard and reports to gain insights into your repository's security posture.

1. Go to your **profile icon** in the top right corner, and then select **Your organizations**.

   ![Picture1](./images/org.png) 
     
1. Select **github-bootcamp-cloudlabsaiuser-####** from **organizations**.

   ![Picture1](./images/org-new1.png) 

1. Navigate to the **security** tab of your **GitHub Organization**.

   ![Picture1](./images/g5c.png)

1. Explore the security overview dashboard. Use the options at the top of the **overview page** to filter the group of alerts for which you want to see metrics. As you adjust the filters, all of the data and metrics on the page will change.

   ![Picture1](./images/dashboard1.png)
   
1. For the alert trends graph at the top of the page, you can click **Open alerts or  Closed alerts** to toggle between showing the trends for Open or Closed alerts. The toggle will only affect the alert trends graph.

   ![Picture1](./images/dashboard2.png)
   
1. Analyze the metrics and data provided in the reports to identify areas for improvement and prioritize security efforts.


### Task 3: Review Webhooks and how they can be used to push events to an outside reporting tool, like an SIEM 

GitHub webhooks are a mechanism for automatically triggering actions or notifications in external systems when events occur within a GitHub repository. Users can configure webhooks to listen for specific events, such as pushes to a repository, pull request creation or closure, issue creation or comment, etc. When the specified event occurs, GitHub sends an HTTP POST payload to a designated URL, known as the payload URL, containing information about the event. This allows users to integrate GitHub with external services, such as CI/CD pipelines, issue trackers, or chat platforms. Thus enabling automated workflows and real-time notifications based on repository activities.


#### Push events to an outside reporting function in the App.

1. Navigate to the Azure Portal and search for **Function app (1)** in the search bar. Select **Function App (2)**.

   ![Picture1](./images/functionapp.png)

1. Click on **Create**.

1. On the basis of Create Function App, provide details as mentioned in the table below and select **Review + create** at the bottom of the page and subsequently click on **Create**.

    | Setting | Action |
    | -- | -- |
    | **Subscription** | Select your Subscription |
    | **Resource Group** | Select your Resource Group |
    | **Function App name** | **function-webhooks** |
    | **Run time stack** | **Node JS** |
    | **Do you want to deploy code or a container image?** | **Code** |
    | **Operating System** | **Windows** |
    | **Hosting options and plans** | **Consumption (Serverless)** |

   >**Note**: To make the **Function App name** unique, append a few random digits to the end of it, for example: **function-webhooks321**.

   ![Picture1](./images/functionapp1.png)
   
   ![Picture1](./images/functionapp2.png)
   
1. Once the deployment is completed, click on **Go to resource**.

1. On the **Overview (1)** page of the **Function app**, under the  **Function** tab, click on **Create function (2)**. It will open a  page for **Create function**. Search for and select **HTTP trigger (3)**. Click on **Next (4)**.

   ![Picture1](./images/functionapp3.png)

1. On Template details page, leave the default options and click on **Create**.

   ![Picture1](./images/mod5functionapp3.png)

1. Go to the **Developer** section of your **HttpTrigger** function, click on **Code + Test (1)**, then click on **Get function URL (2)**. Copy the **default (Function key) (3)** URL from **copy (4)** icon.
   
    ![Picture1](./images/trigger1.png)

1. Navigate to your repository, and click on **Settings**.

   ![Picture1](./images/ghasr1.png)

1. Click on **Webhook**.

   ![Picture1](./images/webhook1.png)

1. Click on **Add Webhooks** and give your GitHub password.

1. On the Webhook form displayed, paste the **Get function URL** generated by the HttpTrigger into the **Payload URL (1)** field.

   - **Content type**: Select **application/JSON (2)** so that you can receive the payload as a JSON object.
   - **Secret**: You can leave this blank.
   - **SSL verification**: Leave this as the default option of **Enable SSL verification (3)**.
   - **Which events would you like to trigger this webhook?** Select the **Just the push event option (4)**.
   - **Active (5)**: Leave this checked to receive event details when the GitHub Webhook is triggered.
   - Click on **Add Webhooks (6)**.

   ![Picture1](./images/payload1.png)

11. Now go to the **Repositories** section and click on **New Respsitories**.

    ![Picture1](./images/newrepo.png)

12. Give the **Repositories name** as **Test-webhook (1)**, select **Public (2)**, and click on **Create repositories (3)** to create them.

    ![Picture1](./images/newrepo1.png)
  
    >**Note**: You can make some more changes to your repositories. It will send the POST request to the function app.

13. Navigate to your repository, and click on **settings**.

     ![Picture1](./images/ghasr1.png)

14. Click on **Webhook** and select the Webhook you have created.

15. Scroll down to the bottom and you will find some **Recent Deliveries**.

    ![Picture1](./images/recentdelivery.png)

16.  Click on any deliveries. You will see their **Request** and **Response** column for more information.

     ![Picture1](./images/request.png)

     ![Picture1](./images/response.png)

17. Navigate back to your **Function app**. Click on **Monitor (1)** under the **Developers** section, and click on **Invocations (2)**. Here, it will give the most recent invocation traces.

     ![Picture1](./images/invocations.png)
   
     >**Note:** It will take 5-7 minutes to show.

#### Task 4: Talk about repository rulesets and how they can be used at scale [Read Only]

1. A ruleset is a named list of rules that applies to a repository. You can create rulesets to control how people interact with selected branches and tags in a repository. You can also control things like who can push commits to a certain branch or who can delete or rename a tag. For example, you could set up a ruleset for your repository's feature branch that requires signed commits and blocks force pushes for all users except repository administrators.

1. For each ruleset you create, you specify which branches or tags in your repository the ruleset applies to. You can use the **fnmatch syntax** to define a pattern and target specific branches and tags. For example, you could use the pattern releases/**/* to target all branches in your repository whose name starts with the string releases/.

1. When you create a ruleset, you can allow certain users to bypass the rules. This can be users with a certain role, such as repository administrator, or it can be specific teams or GitHub apps.

1. There is a limit of 75 rulesets per repository.

#### Creating rulesets for a repository

You can create rulesets to control how users interact with selected branches and tags in a repository. When you create a ruleset, you can allow certain users to bypass the rules. This can be users with certain permissions, specific teams, or GitHub apps.

1. Create a **branch** or tag **ruleset**.

1. On GitHub, navigate to the **main page** of the repository.

1. Under your repository name, click on **Settings**. If you cannot see the "Settings" tab, select the **...**  dropdown menu, then click on **Settings**.

   ![Picture1](./images/ghasr1.png)  

1. In the left sidebar, under **"Code and automation,"** click **Repository**, then click on **Rulesets**.

   ![Picture1](./images/rulesets.png)    

1. You can create a ruleset targeting branches, or a ruleset targeting tags.

   - To create a ruleset targeting branches, click on **New branch ruleset**.
   - To create a ruleset targeting tags, select **New tag ruleset**.

   ![Picture1](./images/rulesetbranch.png)  
  
1. In the **"General"** section, type a name for the ruleset, then select **Disabled**  and click one of the following enforcement statuses:

   - **Active**: Your ruleset will be enforced upon creation.
   - **Disabled**: Your ruleset will not be enforced.

In summary, repository rulesets enhance security, compliance, and consistency across repositories, especially when managing large-scale projects. 

For more details, refer to the [GitHub documentation on rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/about-rulesets)

## Review

In this lab, you have completed the following:

+ How to grow adoption? How to communicate about GHAS internally?  
+ View the security overview dashboard and reports 
+ Review Webhooks and how they can be used to push events to an outside reporting tool, like a SIEM 
+ Talk about repository rulesets and how they can be used at scale 
