# Module 05: GitHub Advisory Database [Read Only]

## Lab Scenario

In this lab, you'll explore the GitHub Advisory Database to identify, manage, and contribute security vulnerability information for open-source dependencies in your project.

## Lab Objectives
In this lab, you will perform:

- GitHub Advisory Database

## Estimated Timing: 30 minutes

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