# Module 0: Setup and Automation

## Org Creation Automation

Please see [the automation repository](https://github.com/ghas-bootcamp-admin/bootcamp-automation) for more information on how to automate the creation of the participants' organizations. You will need to create an issue with the following information to kick off the automation.

Here is a snippet from the README.md in that repository if you need a quick primer on how to activate the automation:

### Creating a new environment

To create a new bootcamp environment you will need a couple things:

* The list of attendee handles (in comma separated [csv] format)
* The list of facilitator handles (csv format)
* The date of the bootcamp.  

That's it!  Once you have that information, click the button below.

[Start new issue](https://github.com/ghas-bootcamp-admin/bootcamp-automation/issues/new?assignees=&labels=bootcamp::new&projects=&template=create-ghas-bootcamp.yml&title=GHAS+bootcamp+request)

> **Note**
>
> You may need permission to access the repository to start the automation.
> Creating a new environment will notify the attendees via email.

Once the automation is complete, a comment will be added to the issue describing the completion state.  The bot will also share a table with links to the learner bootcamp orgs, as well as the facilitator orgs.  

### Decomissioning a bootcamp environment

The process for decomissioning a bootcamp environment is not fully automated (on a schedule) yet. You can manually kick off the teardown process by following these steps:

1. Navigate to **Actions** in this repository
2. Select the **GHAS Bootcamp Teardown** workflow
   ![image](https://github.com/ghas-bootcamp-admin/bootcamp-automation/assets/4910518/f0556468-f9cb-4cab-b1f9-1c12e18802dc)
3. Select **Run Workflow** dropdown
   ![image](https://github.com/ghas-bootcamp-admin/bootcamp-automation/assets/4910518/30b72285-ab1b-4254-9ecb-c2239e3eb294)
4. Enter the issue number from the creation process that you would like to tear down
   ![image](https://github.com/ghas-bootcamp-admin/bootcamp-automation/assets/4910518/a7c56b8d-3ca8-49f7-b040-998fc4480dc9)

The automation process will run and notify you of the completion status.

------

## Kicking-off the bootcamp

Start by having participants confirm they have access to their own organziation. Each student should have an organization with the following naming convention: `ghas-bootcamp-DATE-HANDLE`. To have participants check that they have access to (and are in) the correct organization, share screens and walk through the following steps:

* On the top right section of the Web UI, have the user click on their avatar.
* Click on `Your organizations` approximately halfway down the list that pops-out.

![your-organizations](https://user-images.githubusercontent.com/22803099/225999438-36f3d1d7-0adb-4a5c-a01a-0070e1ed0caa.png)

* Have participants search for `ghas-bootcamp-DATE-HANDLE` to find their organization.
* So long as the student has an organization, make sure they either select the `Join` button or accept the invitation. Once they have completed this step, have them confirm that they have `5` repositories in their organization.

![join-organization](https://user-images.githubusercontent.com/22803099/225999658-cd6b3508-57c6-4998-bdd9-642874abd4b2.png)
![view-invitation](https://user-images.githubusercontent.com/22803099/225999731-3b6aeb9f-8139-4b67-9def-b9fbe5c9f30a.png)
![accept-invitation](https://user-images.githubusercontent.com/22803099/225999671-731e3f4c-1495-44ca-8f10-bdc1b7a41946.png)

------

## Turning on GHAS at the Repo and Org levels

Once the participants have located their organization, start by walking through the process of how to turn GitHub Advanced Security (GHAS) on at the repository level, and then at the organization level. You will likewise have participants turn on Dependency Graph and some of the Dependabot capabilities during this process. The steps are as follows:

* As of march 17th, 2023: Within the `ghas-bootcamp-webgoat` repo, go to **Settings** -> **Code Security and Analysis** and then click `Enable` for _Dependency graph_, _Dependabot alerts_, _Dependabot security updates_, and _GitHub Advanced Security_.

![enable-repo](https://user-images.githubusercontent.com/22803099/225999816-a43384e7-9931-4d41-8c19-18b4f1b2b549.png)

* For the org example, go to the Organization (`ghas-bootcamp-DATE-HANDLE`) and then **Settings** -> **Code Security and Analysis** and click `Enable all` for _Dependency graph_, _Dependablot alerts_, _Dependabot security updates_, and _GitHub Advanced Security_.

![enable-org](https://user-images.githubusercontent.com/22803099/225999862-dbbf108d-7511-487a-9118-9e450270c65b.png)

And with that, you've now concluded **Module 0: Setup and Automation**. You can now move on to your next module (in most cases that will be **Module 1: Software Composition Analysis**).
