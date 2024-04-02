# Module : Scaling out GitHub Advanced Security (HOL)

## Lab Scenario

## Lab objectives
In this lab, you will perform:

- Task 1: How to grow adoption? How to communicate about GHAS internally?  
- Task 2: View the security overview dashboard and reports 
- Task 3: Review webhooks and how they can be used to push events to an outside reporting tool, like a SIEM 
- Task 4: Talk about repository rulesets and how they can be used at scale 

### Estimated timing:  minutes

## Task 1: How to grow adoption? How to communicate about GHAS internally? 

Adopting GitHub Advanced Security can be approached in multiple ways and requires a strategic approach for success, especially in larger enterprises and organisations with thousands of repositories. The purpose of this to lay down a foundation for enterprises on how to adopt GHAS, but most importantly, scale it quickly and eciently.Enabling GitHub Advanced Security across a large organisation can be broken down into **six** core phases:

1. **Align on your rollout strategy and goals**: Think about what success will look like, and align on how GHAS will be implemented in your company. This phase may only take a few days or a week, but it lays a solid foundation for the rest of the rollout.

1. **Preparing to enable at scale:** Prepare developers, collect data about your repositories, and ensure you're ready for the next phase.

1. **Pilot programs:** Optionally, pilot an initial rollout to a few high-impact projects and teams. This will allow an initial group within your company to get familiar with GHAS before you roll out to the remainder of your company.

1. **Create internal documentation:** Create and communicate internal documentation for the consumers of GHAS. Without proper documentation provided to developers, security engineers, and others who will be using GHAS, the value will get lost in the rollout.

1. **Rollout and scale code scanning:** Leveraging the available APIs, automatically rollout code scanning by team and by language across your enterprise, using the repository data you collected earlier.

1. **Rollout and scale secret scanning:** Roll out secret scanning, which involves less configuration and is therefore simpler to adopt than code scanning. Still, it's critical to have a strategy for handling new and old results.
   
1. Phase One - Strategic Enablement Alignment

Although it's appealing to rush into the implementation phase, take the time to align on how GHAS will be implemented in your enterprise. Additionally, think about what success could look like in the 3,6 and 9 months after adoption. This phase may only take a few days or a week, but it lays a solid foundation for the rest of the rollout.

2. Phase Two - Create Internal Documentation

Like the above phase, organisations tend to rush into the implementation phase, as that stage is perceived to provide the quickest time-to-value. However, without the proper documentation and asynchronous resources provided to aid developers, security engineers, etc., in consuming GHAS correctly, usually, the value gets lost in the rollout due to people not consuming GHAS in the correct way. Take the time to create internal documentation (such as training, how to remediate, where to go for questions, etc.), and then communicate this documentation (email, teams, slack, etc.) to the consumers of GHAS so once you rollout GHAS, teams and people know what to do.

3. Phase Three - Enable & Scale Code Scanning

GHAS is an ecosystem of multiple solutions; it's essential to start somewhere focused, not just with the rollout of GHAS. Typically, we see teams focus on code scanning, to begin with. Leverage the API's available and rollout code scanning by team and by language across your organisation automatically. This allows you to scale in an automated fashion and removes a lot of manual repeatable groundwork for developers and consumers of code scanning. Doing this will increase adoption.

### Task 2: View the security overview dashboard and reports 

In this task, you will explore the security overview dashboard and reports provided by GHAS to gain insights into your repository's security posture.

1. On GitHub.com, navigate to the main page of the organization.
   
1. Navigate to the **security** tab of your GitHub repository.

   ![Picture1](./images/security-tab.png)
  
1. Explore the security overview dashboard, Use the options at the top of the overview page to filter the group of alerts you want to see metrics for. All of the data and metrics on the page will change as you adjust the filters.

   ![Picture1](./images/dashboard1.png)
   
1. For the alert trends graph at the top of the page, you can click  Open alerts or  Closed alerts to toggle between showing the trends for open or closed alerts. The toggle will only affect the alert trends graph.

   ![Picture1](./images/dashboard2.png)
   
1. Analyze the metrics and data provided in the reports to identify areas of improvement and prioritize security efforts.


### Task 3: Review webhooks and how they can be used to push events to an outside reporting tool, like a SIEM 

GitHub webhooks are a mechanism for automatically triggering actions or notifications in external systems when events occur within a GitHub repository. Users can configure webhooks to listen for specific events, such as pushes to a repository, pull request creation or closure, issue creation or comment, etc. When the specified event occurs, GitHub sends an HTTP POST payload to a designated URL, known as the payload URL, containing information about the event. This allows users to integrate GitHub with external services, such as CI/CD pipelines, issue trackers, or chat platforms, enabling automated workflows and real-time notifications based on repository activities.

#### Task 3.1: Installing necessary tools.

1. Paste the following commands to install ***nodejs (1)*** and click on **Run (2)** button.

     ```
    #Install nodejs v16.8.0
    $WebClient = New-Object System.Net.WebClient
    $WebClient.DownloadFile("https://nodejs.org/download/release/v16.8.0/node-v16.8.0-x64.msi","C:\node-v16.8.0-x64.msi")
    $arguments = "/i `"C:\node-v16.8.0-x64.msi`" /quiet"
    Start-Process msiexec.exe -ArgumentList $arguments -Wait
    sleep 5
      ```

1. In the command prompt, run the following npm command.

      ```
      npm.cmd install --loglevel error eslint@7.32.0 typescript@4.3.2 @microsoft/eslint-plugin-sdl@0.1.7 eslint-plugin-react@7.24.0 eslint-plugin-security@1.4.0 @typescript-eslint/typescript-estree@4.27.0 @typescript-eslint/parser@4.27.0 @typescript-eslint/eslint-plugin@4.27.0 @microsoft/eslint-formatter-sarif@2.1.5 eslint-plugin-node@11.1.0 --prefix C:\a\_msdo\packages\node_modules\eslint –global
      ```

1. To install the **Scoop** run the following command.

      ```
      iex "& {$(irm get.scoop.sh)} -RunAsAdmin"
      ```

1. Install git

      ```
      $WebClient = New-Object System.Net.WebClient
      $WebClient.DownloadFile("https://github.com/git-for-windows/git/releases/download/v2.44.0.windows.1/Git-2.44.0-64-bit.exe","C:\Git-2.44.0-64-bit.exe")
      $arguments = "/install /quiet /norestart"
      Start-Process "C:\dotnet-sdk-8.0.201-win-x64.exe" -ArgumentList $arguments -Wait
      sleep 5
      ```
