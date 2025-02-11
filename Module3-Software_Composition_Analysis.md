# Module 04: Software Composition Analysis

## Lab Scenario

In this lab, you will be focusing on improving security within your GitHub repositories using Dependabot and Software Composition Analysis (SCA) features.

## Lab Objectives

In this lab, you will perform:
 
- Task 1: Use the dependency submission action on a Java project and review results 
- Task 2: Use the dependency review action to stop a pull request that contains the log vulnerability. 

## Estimated Timing: 40 minutes

## Task 1: Use the dependency submission action on a Webgoat project and review results

GitHub's dependency submission API supports Software Composition Analysis (SCA). It provides a GitHub API that allows uploading a complete list of the dependencies used by a repository (or, more precisely, a particular build of the application in the repository).
The process involves adding all dependencies from a repository to the dependency graph. Particularly those resolved during software compilation or building. Even if they are not listed in a manifest file like pom.xml. When new dependency versions are released, Dependabot utilizes data submitted via the dependency submission API to generate Pull requests.

## Task 2: Use the dependency review action to stop a pull request that contains the log vulnerability

### Dependency Review Action

The dependency review action is a GitHub Action designed for this purpose, preventing vulnerable dependencies from being merged into a repository. This action serves as a proactive measure to maintain the integrity and security of the repository by identifying and mitigating potential risks associated with third-party dependencies.

1. In the **ghas-bootcamp-webgoat** repo navigate to **Actions**, and in the **Actions**, click on **New workflow** from the left navigation pane.

   ![github-advisory-database](images/g2.1.png)

   ![github-advisory-database](images/g3at.png)
 
1. Now, search **Dependency Review** to find and configure the action by clicking the **Configure** button.
   
   ![github-advisory-database](images/g4.png)

1. In the  `fail-on-severity` in the workflow file and make sure you uncomment the line removing **#** as shown in the below screenshot and click on **Commit Changes** in the top right corner.

   >**Note**: Please ensure that the indentation is correct according to the provided screenshots. Make sure that the **fail-on-severity: low, moderate, high, critical** is directly below the **comment-summary-in-pr: always** line, as shown below:

   >**Note:** The default value of **fail-on-severity** will work as well, but here we demonstrate how to modify your severity level.

   ![github-advisory-database](images/g7at.png)
   ![github-advisory-database](images/uncmtat.png)

1. If prompted, click on **Commit Changes** once again in the pop-up that appears.

   ![github-advisory-database](images/g8.png)

1. Now back in the **ghas-bootcamp-webgoat** repository, go to the **pom.xml** file.

   ![github-advisory-database](images/g9.png)
   
1. Add the provided code to the **WebGoat/pom.xml** file as shown in the screenshot by clicking on the pencil icon and delete the existing lines as mentioned.

   - **Security Vulnerabilities:** Log4j has been known to have critical security vulnerabilities. This vulnerability allowed attackers to execute arbitrary code on a server or other computer running Log4j, leading to severe security risks such as remote code execution.

   - **Impact:** If a project uses a vulnerable version of Log4j, it can be exploited by attackers to compromise the application or the server it runs on. This can lead to unauthorized access, data breaches, and other security issues. 

		```xml
		<dependency>
		   <groupId>org.apache.logging.log4j</groupId>
		   <artifactId>log4j-core</artifactId>
		   <version>2.13.1</version>
		</dependency>
		```

      ![github-advisory-database](images/gx2at.png)

      ![github-advisory-database](images/gx2.png)

1. Click on **Commit Changes** and make sure you select **create a new branch** option and click on **Propose Changes** .

   ![github-advisory-database](images/proposechanges.png)

1. Click on **Create pull request**. 

   ![github-advisory-database](images/createpr.png)

1. On the **Open a pull request** tab, click on **Create pull request**. No need to merge the PR.   

   ![github-advisory-database](images/sec-3.png)

1. Scroll down, You will see after few seconds that all the checks got failed due to the dependency review action.

   - **Dependency Review Action:** The Dependency Review action in GitHub Actions is designed to identify and mitigate risks associated with third-party dependencies, including libraries like `Log4j`. When a pull request introduces or updates a dependency, the action checks if the dependency has known vulnerabilities.

   - **Failure of Pull Requests:** If the Dependency Review action detects that a pull request introduces a version of `Log4j` (or any other dependency) that has known vulnerabilities, it will mark the pull request as failed. This is done to prevent merging code that could introduce security risks into the main codebase.

      ![github-advisory-database](images/prfail.png)

1. You can also see the error details on *Actions* section, navigate to **Action** section and from the left navigation pane, click on **Dependency review**. Notice the failed **Dependency review** due to the dependency review finding the introduction of a vulnerable `Log4j` version.

   ![github-advisory-database](images/gx1.png)

<!--
   > **Congratulations** on completing the task! Now, it's time to validate it. Here are the steps:
	
   - Hit the Validate button for the corresponding task. If you receive a success message, you can proceed to the next task.
     >**Note:** Upon clicking the **Validate** button for this exercise, you'll receive a prompt to input your Organization name. Provide your **Organization name** which looks like **ghas-bootcamp-xxxx-xx-xx-cloudlabsxxx**.
    
     >**Note:** Make sure to update the name of your organization, **ghas-bootcamp-xxxx-xx-xx-cloudlabsxxx**.
    
     ![github-advanced-security](images/ghas-exercise1-8.png)
   
   - If not, carefully read the error message and retry the step, following the instructions in the lab guide.
   - If you need any assistance, please contact us at cloudlabs-support@spektrasystems.com. We are available 24/7 to help you out.

   <validation step="401a8107-d558-4bed-a5b6-4b1e5ca50132" />
-->

## Review

In this module, we have completed the following:
-  Used the dependency submission action on a Java project
-  Used the dependency review action to stop a Pull Request that contains the log vulnerability
