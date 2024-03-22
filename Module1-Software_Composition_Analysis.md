# Module 1: Software Composition Analysis

## Getting Started

If you followed `Module 0 - Setup and Automation`, you will have already enabled _Dependency graph_, _Dependabot alerts_, and _Dependabot security updates_ at both the repository and the organization level. If you are starting this module without having taken these steps, below are the instructions for turning on these features at the organization level:

- Go to the Organization (`ghas-bootcamp-DATE-HANDLE`) and then **Settings** -> **Code Security and Analysis** and click `Enable all` for _Dependency graph_, _Dependablot alerts_, _Dependabot security updates_, and _GitHub Advanced Security_.

Once this is enabled, navigate to the `WebGoat` repository to begin working through this module.

## Dependabot

## GitHub Advisory Database

Open the [GitHub Advisory Database](https://github.com/advisories) and work through the talk track below, which is taken from comments made by @Moose0621 in [this issue](https://github.com/github/field-security-specialists/issues/177#issuecomment-1440704862) related to the GHAS Bootcamp Renovation project.

![github-advisory-database](https://user-images.githubusercontent.com/22803099/236020080-c4ab17ba-86b8-4e43-a762-92626d94c6c1.png)

- **The Problem**
  - Malicious actors have been leveraging open source to look for targets of opportunity
  - Organizations have a responsibility to ensure they are using open source in a safe manner
  - Dependabot provides automation to help scale dependency updates across your organization

- **What is the GitHub Advisory Database?**
  - Curated DB of known security vulnerabilities across the open source ecosystem
  - Community driven effort
  - GitHub is a Certified CVE Numbering Authority
    - Responsible for assigning CVEs to vulnerabilities in the open source ecosystem
    - Publishes the second most CVEs behind MITRE
  - DB -> [https://github.com/advisories](https://github.com/advisories)
  - DB has grown substantially over the last several years
    - 2022, added 3k newly reviewed CVEs
    - 2023, added 17.5 million [new package licenses](https://github.blog/changelog/2023-07-10-new-license-information-for-17-5-million-packages/) to our DB
      - Added support for Swift, Erlang, and Elixir packages

- **How does it work?**
  - Leverages the GitHub API to pull latest information
    - Used to determine if there are any known vulnerabilities
  - Dependabot will create an alert if vulnerabilities are found
  - Dependabot may create a pull request if there is an update to fix the vulnerability

- **How can I contribute?**
  - If you find a CVE that is not in our GHADB, please let your account team know
    - Share the CVE number with us, and we will prioritize it
    - Our curation team has built tooling to prioritize unreviewed CVEs

## Dependency submission API

- **Background**: GitHub's dependency submission API supports Software Composition Analysis (SCA). It provides a GitHub API that allows uploading a complete list of the dependencies used by a repository (or, more precisely, a particular build of the application in the repository).

- **How it works**
  - Add all dependencies from a repository to the dependency graph
    - Especially those that are resolved when software is compiled or built
      - Dependencies may not be listed in a manifest file, like a `pom.xml`
  - When a new version of a dependency is released, Dependabot can use the data submitted with the dependency submission API to create a pull request
    - Ensures that the application is always using the mose secure version of its dependencies
    - Helps improve security and compliance

- **How to use it**
  - In the `WebGoat` repository, go to the `.github/workflows/DepGraph.yml` file
  - Explain how this file will use the **Maven Dependency Tree Submission** action to identify the transitive dependencies
    - Transitive dependencies are pulled in as part of the build process for this project
  - Go to the **Actions** section, click on the **Dependency Graph Upload** action
  - Click the **Run workflow** -> **Run workflow** (in Green) button
  - Explain that this can also be used to create and upload SBOMs for analysis and alerting
    - However, for the purposes of this demonstration, we will be using WebGoat instead of an SBOM

![dependency-submission-api-action](https://user-images.githubusercontent.com/22803099/236020191-54e402b5-853c-4c72-9c3f-14e675eafaaf.png)

- Once this has completed, go to the **Dependency Graph** tab, under the **Insights** section
- Show the new critical vulnerabilities that have been identified in transitive dependencies

## Dependency Review Action

- **What is it?**
  - A GitHub Action that can be used to prevent vulnerable dependencies from being merged into a repository
  - Can be used in tandem with the dependency submission API
  - Can be configured to fail at a certain severity or license type

- **How to use it**
  - Go back to the **Actions** tab and click on the **New workflow** button on the top-left
    - Search **_Dependency Review_** to find and configure the action.
    - Click the _Configure_ button.

![dependency-review-action](https://user-images.githubusercontent.com/22803099/236020357-5ed786d6-1a0b-40f2-aa7f-2b6654c82e5e.png)

> Note:
>
> The workflow is already in the repository, but we are going to walk through the configuration of this workflow to understand how it works. Modify the existing workflow to demonstrate the functionality of the action (file: `dependency-review.yml`).

- On `Line 5` of the Action workflow configuration there is a [link to the Action's repository](https://github.com/actions/dependency-review-action). Highlight this and open it in a new tab where you can scroll down to the **Configuration options**. We can copy the the example that includes the `fail-on-severity` and `deny-licenses` stanzas below the configuration options over our existing workflow.

- Modify the `WebGoat/pom.xml` file between `Line 154` and `Line 161`:
  - Uncomment the following code block:

```xml
        <dependency>
            <groupId>org.apache.logging.log4j</groupId>
            <artifactId>log4j-core</artifactId>
            <version>2.13.1</version>
        </dependency>
```

- Submit a pull request with the changes to the `pom.xml` file.
- Note that the **_Dependency Review Action_** has failed due to the dependency review finding the introduction of a vulnerable `Log4j` version.


Next, introduce a branch protection rule on the `main` branch and watch as the failing status check is tagged with required and now your PR merge button is grayed out

![dependency-review-branch-protection](https://user-images.githubusercontent.com/22803099/236020409-7bec4c4a-097c-480d-9dca-32799c321bfe.png)

<img width="435" alt="image" src="https://github.com/ghas-bootcamp-admin/training-material/assets/1760475/85d3b6a5-59a1-4508-a6a7-3aa73432661f">


- **Wrap up**
  - Summarize what you have covered so far:
    - GitHub Advisory Database
    - Dependabot Alerts
    - Dependency Graph
    - Dependency Submission API
    - Dependency Review Action
  - Ask if there are any questions before moving on to the next section
  - Reinforce the need for SCA and how this happens in a developer-friendly fashion
