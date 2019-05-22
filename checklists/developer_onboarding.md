## Developer Onboarding

Being a new developer on an established team can be overwhelming. There are many parts of the process, culture and technical aspects the new dev will need to learn. Effective teams have good onboarding documents available so the process is clear. Ideally, onboarding should happen in stages. The suggested steps are described below, but each team must adapt according to context. It's not a manager's responsibility to onboard every new dev. Thus, all team members must be prepared. This is also important so that different people can iterate over the onboarding process and evaluate how it can improve.

### Step 1 - Processes
The goal of this step is to provide an overall understanding of both the client and the team. Who they are and how they operate.

- [ ] Ask the dev to introduce themselves. What's their past experience? What languages, databases, servers have they worked with?
- [ ] Present the client. Who is the client? What is the business model? What are the goals Vinta helps the client achieve?
- [ ] Present the team. Detail each persons' roles, if there's a support manager, a deploy manager. Mention how the project started, and how the team grew.
- [ ] Explain the team's processes and workflows:
    - [ ] Explain [sprints](https://github.com/vintasoftware/playbook/blob/master/project_management.md#sprints).
    - [ ] Make sure the developer understands their responsibilities and features ownership.
    - [ ] Explain the [development workflow](https://github.com/vintasoftware/playbook/blob/master/checklists/feature_development_workflow.md).
    - [ ] Explain the project's repository. Differences between feature PRs, and deploy PRs. What branches represent Staging and Production?
    - [ ] Explain Staging and Production environments. More details [here](https://12factor.net/dev-prod-parity).
    - [ ] Ask the new developer to read the [development guideline](https://github.com/vintasoftware/playbook/blob/master/development.md#development) and the [frontend guideline](https://github.com/vintasoftware/playbook/blob/master/guidelines/guideline_frontend.md).
    - [ ] Explain the Roadmap, and how the long-term planning is assessed.
    - [ ] Explain how and when [sprints meetings](https://github.com/vintasoftware/playbook/blob/master/checklists/sprint_meeting.md) with the client occur. How meeting notes are organized, where they are stored.
    - [ ] Show them the project's assets. They should be available on the project's Drive folder.
- [ ] Ask the developer to set up the project using the README. If any issues are encountered, they should modify the document. This benefits new future hires.
- [ ] Assert the developer has access to:
  - [ ] LastPass
  - [ ] The project's Drive folder
  - [ ] The project's Google group
  - [ ] The project's Google Calendar events
  - [ ] The project's Github repository
  - [ ] The project's Asana
  - [ ] Both Production and Staging environments
  - [ ] The client's Slack


### Step 2 - Product and Project
The new dev should already be familiarized with the processes. Now, it's time they learn details of the project.

- [ ] Start explaining main use cases and where they're implemented on the code.
- [ ] Show how they can manually test the system on Staging.
- [ ] Complete the main flows on Staging with them.
- [ ] Go through administrative tools. What are the most accessed parts?
- [ ] Explain which parts of the code are most critical and why. How does the team handle them?
- [ ] Explain how async tasks run and what is used to monitor them.
- [ ] Explain what types of async tasks run on the project, especially periodic tasks, and if there's any priority queue.
- [ ] Explain the tech stack. Show which external services and technologies are being used (DB, Redis, Elasticsearch...).
- [ ] Explain what third-party integrations are there.
- [ ] If there's a project wiki, ask them to read.
- [ ] Explain what were the biggest problems in the past.
- [ ] Be empathic. Assure them you know it's a lot of information and we don't expect them to learn all at once.
- [ ] Ask them if they have any questions and if they understand what was explained. If they give you feedbacks, use them to improve this process!
- [ ] Ask them to spend some time browsing Staging, going through the system as a user and as an admin.


### Step 3 - Feature development
It's time to start coding! At this stage, the manager should assign a task according to the seniority of the new developer. This is important to initiate them in the development flow. Ideally, the first task should be self-contained, but this may vary according to the new hire's seniority. The manager should be extra careful when detailing the task, and remember the new dev is not familiar with the project.

- [ ] If the feature is related with existing models, provide UML class diagrams to facilitate the understanding. Here's [a guide on how to generate class diagrams using Graphviz](https://simpleit.rocks/generate-uml-class-diagrams-from-django-models/). This will especially be needed for complex systems.
- [ ] Go over the dev's task explaining what's expected of them. For example, what to add to the card, when to move columns, etc.
- [ ] Make sure the expected git flow is clear to the developer.
- [ ] Explain the expected Trello flow. When the cards should move columns.
- [ ] Feature ownership matters. It must be clear to the new hire is responsible for the feature until it's live.
- [ ] Ask for feedbacks! How was the onboarding process for them? What parts could improve?