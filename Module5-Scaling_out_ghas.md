# Module : Scaling out GHAS (HOL)

## Lab Scenario

## Lab objectives
In this lab, you will perform:

- Task 1: How to grow adoption? How to communicate about GHAS internally?  
- Task 2: View the security overview dashboard and reports 
- Task 3: Review webhooks and how they can be used to push events to an outside reporting tool, like a SIEM 
- Task 4: Talk about repository rulesets and how they can be used at scale 

### Estimated timing:  minutes

## Task 1: How to grow adoption? How to communicate about GHAS internally?  
Adopting GitHub Advanced Security (GHAS) can be approached in multiple ways and requires a strategic approach for success, especially in larger enterprises and organisations with thousands of repositories. The purpose of this to lay down a foundation for enterprises on how to adopt GHAS, but most importantly, scale it quickly and eciently.Enabling GitHub Advanced Security across a large organisation can be broken down into **six** core phases:

1. **Align on your rollout strategy and goals**: Think about what success will look like, and align on how GHAS will be implemented in your company. This phase may only take a few days or a week, but it lays a solid foundation for the rest of the rollout.

1. **Preparing to enable at scale:** Prepare developers, collect data about your repositories, and ensure you're ready for the next phase.

1. **Pilot programs:** Optionally, pilot an initial rollout to a few high-impact projects and teams. This will allow an initial group within your company to get familiar with GHAS before you roll out to the remainder of your company.

1. **Create internal documentation:** Create and communicate internal documentation for the consumers of GHAS. Without proper documentation provided to developers, security engineers, and others who will be using GHAS, the value will get lost in the rollout.

1. **Rollout and scale code scanning:** Leveraging the available APIs, automatically rollout code scanning by team and by language across your enterprise, using the repository data you collected earlier.

1. **Rollout and scale secret scanning:** Roll out secret scanning, which involves less configuration and is therefore simpler to adopt than code scanning. Still, it's critical to have a strategy for handling new and old results.
   
1. Phase One - Strategic Enablement Alignment

Although it's appealing to rush into the implementation phase, take the time to align
on how GHAS will be implemented in your enterprise. Additionally, think about what
success could look like in the 3,6 and 9 months after adoption. This phase may only
take a few days or a week, but it lays a solid foundation for the rest of the rollout.

2. Phase Two - Create Internal Documentation

Like the above phase, organisations tend to rush into the implementation phase, as
that stage is perceived to provide the quickest time-to-value. However, without the
proper documentation and asynchronous resources provided to aid developers,
security engineers, etc., in consuming GHAS correctly, usually, the value gets lost in
the rollout due to people not consuming GHAS in the correct way. Take the time to
create internal documentation (such as training, how to remediate, where to go for
questions, etc.), and then communicate this documentation (email, teams, slack, etc.)
to the consumers of GHAS so once you rollout GHAS, teams and people know what to
do.

3. Phase Three - Enable & Scale Code Scanning

GHAS is an ecosystem of multiple solutions; it's essential to start somewhere focused,
not just with the rollout of GHAS. Typically, we see teams focus on code scanning, to
begin with. Leverage the API's available and rollout code scanning by team and by
language across your organisation automatically. This allows you to scale in an
automated fashion and removes a lot of manual repeatable groundwork for developers
and consumers of code scanning. Doing this will increase adoption.

### Task 2: View the security overview dashboard and reports 
In this task, you will explore the security overview dashboard and reports provided by GHAS to gain insights into your repository's security posture.

1. Navigate to the security tab of your GitHub repository.
  
1. Explore the security overview dashboard, which provides an overview of security alerts, code scanning results, dependency insights, and other security-related metrics.
   
1. Review the various reports available, such as vulnerability alerts, code scanning alerts, and dependency insights.
   
1. Analyze the metrics and data provided in the reports to identify areas of improvement and prioritize security efforts.
