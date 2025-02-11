# Module 03: Exploring Dependabot, Secret Scanning, and CodeQL in GHAS [Read Only]

## Lab Scenario

In this lab, you will explore Dependabot, Secret Scanning, and Code Scanning, gaining a deeper understanding of how each tool enhances software security and project maintenance within GitHub Advanced Security.

## Lab Objectives
In this lab, you will perform:

- Depandabot and its features
- Secret Scanning and its features
- Code Scanning

## Estimated Timing: 30 minutes

## Dependabot and its features

Dependabot manages your project’s dependencies according to the dependency file available in the repository in an automated way. Dependabot checks dependencies in your project and creates pull requests whenever a new version is available. It saves a significant amount of time and makes the process autonomous. Dependabot helps to elevate the project’s robustness and reduce system vulnerabilities by keeping dependencies up-to-date.

**[Dependabot alerts](https://docs.github.com/en/code-security/dependabot/dependabot-alerts/about-dependabot-alerts)**: Dependabot alerts tell you when your code depends on a package that is insecure. Often, software is built using open-source code packages from a large variety of sources. The complex relationships between these dependencies, and the ease with which malicious actors can insert malware into upstream code, mean that you may unknowingly be using dependencies that have security flaws, also known as vulnerabilities.

If your code depends on a package with a security vulnerability, this can cause a range of problems for your project or the people who use it. Using a vulnerable package makes you a soft target for malicious users looking to exploit your system. For example, they may seek to get access to your code and data from your customers or contributors. You should upgrade to a secure version of the package as soon as possible. If your code uses malware, you need to replace the package with a secure alternative.

**[Dependabot security updates](https://docs.github.com/en/code-security/dependabot/dependabot-security-updates/about-dependabot-security-updates)**: Dependabot security updates make it easier for you to fix vulnerable dependencies in your repository. You typically add a `dependabot.yml` file to your repository to enable Dependabot security updates. You then configure options in this file to tell Dependabot how to maintain your repository.

If you enable Dependabot security updates, when a Dependabot alert is raised for a vulnerable dependency in the dependency graph of your repository, Dependabot automatically tries to fix it

**[Grouped security updates](https://docs.github.com/en/code-security/dependabot/working-with-dependabot/dependabot-options-reference#groups)**: Groups all available updates that resolve a Dependabot alert into one pull request (per package manager and directory of requirement manifests). This option may be overridden by group rules specified in `dependabot.yml`.

**[Dependabot version updates](https://docs.github.com/en/code-security/dependabot/dependabot-version-updates/about-dependabot-version-updates)**: 

### Features of GitHub Dependabot

GitHub Dependabot offers several features that make it a reliable tool for automatic dependency management:

- **Integration with GitHub:** Dependabot is directly integrated into GitHub, so it works as a native feature. It allows seamless management of dependencies by analyzing dependencies mentioned in files in the GitHub repository.

- **Automatic pull requests:** Dependabot creates automatic pull requests whenever it finds new version updates. It creates pull requests with all the crucial details, such as release notes, change logs, and commits.

- **Security updates:** Dependabot creates pull requests to update dependencies with known vulnerability fixes.

- **Version updates:** Dependabot creates pull requests to keep dependencies up-to-date, even when they don’t have any vulnerabilities.

- **Security vulnerability alerts:** Dependabot sends alert notifications to users if it finds any known security vulnerability associated with the dependencies.

- **Compatibility scores:** Dependabot provides compatibility scores based on successful test runs of other projects using the same updates. These are calculated from CI test runs in other public repositories where the same update has been made.

- **Configurability:** Dependabot is highly configurable, allowing users to customize update schedules, target versions, assignees for PRs, and package managers, ignore specific dependencies, and much more.

### How does GitHub Dependabot work?

GitHub Dependabot works in a streamlined way to manage dependencies.

- **Dependency checking:** Dependabot continuously checks your project’s dependency files such as package.json, and requirements.txt based on your configuration settings.

- **Update identification:** Dependabot not only identifies a new version of a library or package but also finds a dependency with a known security vulnerability.

- **Pull request creation:** After identifying an update or vulnerability, Dependabot prepares and generates a pull request for the specific update or fix according to the nature of the change.

- **Dependabot alerts:** If Dependabot finds a dependency with a known security vulnerability, it creates a security alert.

## Secret Scanning and its features

Secret scanning is a security feature that automatically scans code repositories for accidentally committed sensitive information like API keys, passwords, tokens, and other private credentials, alerting the repository owner when it detects potential secrets, helping to prevent data leaks and security breaches.

### Benefits of secret scanning

Here is the some benfits of Secret Scanning.

- **Enhanced security:** Secret scanning scans your repositories for sensitive information like API keys, passwords, tokens, and other secrets. By detecting these early, you can mitigate potential security risks before they are exploited by malicious actors.

- **Automated detection:** The feature automatically scans your codebase, including commits, issues, and pull requests, ensuring continuous protection without requiring manual intervention. This automation helps in maintaining security even as your repository evolves.

- **Real-time alerts:** When a secret is detected, secret scanning provides real-time alerts to repository administrators and contributors. This immediate feedback allows for swift remediation actions.

- **Integration with service providers:** GitHub partners with various service providers to validate detected secrets. When a secret is identified, GitHub notifies the corresponding service provider to take appropriate actions, such as revoking the exposed credential.

### How secret scanning works?

Below is a typical workflow that explains how secret scanning works:

- **Detection:** Secret scanning automatically scans your repository's contents for sensitive data, such as API keys, passwords, tokens, and other secrets. It looks for patterns and heuristics that match known types of secrets.

- **Alerts:** When a potential secret is detected, GitHub generates an alert and notifies the relevant repository administrators and users. This notification includes details about the detected secret, such as its location in the repository.

- **Review:** When a secret is detected, you'll need to review the alert details provided.

- **Remediation:** You then need to take appropriate action to remediate the exposure. This should always include rotating the affected credential to ensure it is no longer usable. It may also include removing the secret from the repository's history (using tools like git-filter-repo; see Removing sensitive data from a repository for more details) though this will likely involve a heavy cost in time and effort, and is usually unnecessary if the credentials have been revoked.

- **Monitoring:** It's good practice to regularly audit and monitor your repositories to ensure no other secrets are exposed.

- **Integration with partners:** GitHub works with various service providers to validate secrets. When a partner secret is detected, GitHub notifies the provider so they can take appropriate action, such as revoking the credential.

## Code Scanning 

Code scanning in GitHub is a powerful feature designed to enhance the security of your software projects by automatically identifying and alerting you to potential security vulnerabilities in your codebase. Leveraging advanced static analysis techniques, and code scanning helps detect security flaws, bugs, and other issues early in the development process, enabling developers to address them proactively before they escalate into larger problems. 

**CodeQL** is the code analysis engine developed by GitHub to automate security checks. You can analyze your code using CodeQL and display the results as code scanning alerts.

CodeQL is a programming language and associated tools that treat code like data. It was created explicitly to make it easier to analyze code and find potential vulnerabilities in your code with greater confidence than traditional static analyzers.

- You generate a CodeQL database to represent your codebase.
- Then you run CodeQL queries on that database to identify problems in the codebase.
- The query results are shown as code scanning alerts in GitHub when you use CodeQL with code scanning.

### What is CodeQL and how is it different from other static analysis tools?

1. Code Scanning, powered by the CodeQL engine, performs thorough static analysis by accessing source code and integrating with the build process for compiled languages (or simulating compilation for interpreted languages). This approach ensures precise mapping of data flow and the ability to differentiate between remote and local sources. 

1. The fundamental difference is that all of the information about the application is aggregated in a relational database that allows for tracing complete data flows across the entire application.

1. For `compiled` languages, the CodeQL engine running under the hood of the Code Scanning process will hook into the compiler at build time. The CodeQL engine will then listen for the creation of data flows by the compiler, such as linkers and callbacks, and map those data flows as nodes in the database -- aptly called `DataFlow` nodes.

1.  This process allows CodeQL to avoid false positive vulnerability findings from dead code that has no existing dataflows. This is a common problem with other Static Analysis tools that do not have access to the compiler and instead rely on pattern matching and other techniques to identify vulnerabilities.

1. Once the data flow analysis is complete, an extraction of the code is then performed. Every variable, expression (combination or modification of variable(s)), method/function/class declaration, etc. is extracted as individual nodes in the database.

1. CodeQL then performs analysis by querying the database for _Remote_ flow sources that lead to sinks (where data is stored or executed) in ways that are exploitable and are otherwise not sanitized as part of that data flow.

1. For `interpreted` languages, like Javascript and Python, the CodeQL engine performs a depth-first, recursive extraction of the code where `DataFlow` nodes are created from things like `return` statements and passing variables from one function to another. We can gain a comprehensive view of the application and avoid flagging false positive vulnerabilities in code that is never called or executed.

### References

1. [Dependabot documentation](https://docs.github.com/en/code-security/dependabot)

1. [Automatically updating dependencies with known vulnerabilities with Dependabot security updates](https://docs.github.com/en/code-security/dependabot/dependabot-security-updates)

1. [Keeping your dependencies updated automatically with Dependabot version updates](https://docs.github.com/en/code-security/dependabot/dependabot-version-updates)
