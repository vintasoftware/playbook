___"Artists know that there is no creativity without a system of formal restraints."___ What Kathy Galloway said also applies to projects, the best and most creative work comes from a set of refrains that doesn’t  choke anyone and guides them to a better result. Here are ours.

## Methodology overview
Vinta works following an [Agile](http://www.agilemanifesto.org/)-like methodology:
- Sprints, one-week long. Sprints are a lightweight process aligned to "Responding to change over following a plan".
- Use of [Trello](https://trello.com/) as the main management tool. There we align expectations, because we want "Customer collaboration over contract negotiation".
- Use of [GitHub](https://github.com/) for Git repository hosting and code review, along with a  continuous integration tool, like [CircleCI](http://circleci.com/) or [Travis CI](https://travis-ci.org), so  we ensure "Working software over comprehensive documentation".
- Use of [Slack](https://slack.com/) for real-time communication, since we consider "Individuals and interactions over processes and tools".

## Project Manager’s duties
- A Project Manager's most important duty is to manage client's expectations and keep them realistic. We realize most of the problems in software development come from communication issues, and the Project Manager at Vinta is the 'Communication Person'. The Project Manager should always track the deliverables for the next sprint and, if any problems are to appear, features must be simplified, development strategies re-evaluated, and priorities re-defined, always sided with the client. That's easier said than done in some cases, but surely brings benefits for us and the clients.
- The Project Manager will be the main point of contact with the client. It's good for everyone to have an open communication channel directly with the client, but the Project Manager should be aware of all project-related decisions. However, regarding assigned tasks, each developer is free to discuss and validate it directly with the client. Should the client ask the developer to do another task, this needs to be tracked and communicated to the Project Manager. Maybe the manager knows better the priority, even better than the client, so s/he needs to step in.
- Project Manager will work on the project as a developer too.
- Project Manager should encourage everyone to manually test all features before validating them with the client.
- Project Manager should remember developers to report daily on what they are working on.
- Project Manager should alert everyone to turn off Slack "do not disturb" option so the client can reach them in case of emergencies.

### Daily Attibutions

- Make sure process is being followed by everyone in the team: code is being reviewed, tests are being written, ...
- Assert team is writing quality code.
- Guarantee technical debt is not being overlooked and allocate accordingly when payment is urgent. Be emphatic when needed about this with the client.
- Advise less experienced team members.
- Watch for tools and processes that can improve the team's and project's wellness and performance.
- Create a healthy environment for people to grow. This includes making sure everyone: has active voice in decisions and feels safe to ask, learn and give opinions.
- Guide the team towards the best decisions.
- Be tough when the team is heading in the wrong direction. When the team lacks consensus or when it feels appropriate, PM will have the final say.
- Delegate and trust the team to execute any kind of job. There's no such thing as a task that can only be performed by a PM. 

### Not team lead attributions:

- Review every single piece of code.
- QA every single functionality.
- Solely assume responsibility during crisis.
- Micromanage people's work.

## Sprints
- Managed on Trello ([See our Trello Guideline](guidelines/guideline_trello.md)).
- One-week.
- Friday to Thursday.
- Never deploy to production on Fridays.
- Weekly Sprint Meetings.
- [Sprint Meeting checklist](checklists/sprint_meeting.md) must be followed.
- [Daily development reports](development.md#daily-reporting).

### Development
Read [Development section](development.md#development) to understand how features should be implemented and what are the coding guidelines.

## Team Augmentation Project
Questions to ask a client before starting the project:

- In which platform was the project built?
- Was it some JS MVC framework?
- Is Django the backend?
- Django template or only Django as API?
- Will we work on features, bugs, or both?
- Which tool will be used to manage issues?
- Uses Slack?
- Who will be the main point of contact?
- Do you follow any kind of Git process? Git flow?
- How is the test coverage?
- Are the continuous integration tools working?
- Code patterns? Html? Js? Python?
- Do you have a QA team?

## Postmortem
After the project ends, the Project Manager must write a postmortem and share it with the client. Language should be professional, but kind. A Postmortem serves as future lessons for Vinta to know where our process might need improvement. Here is what the Project Manager needs to answer in it:

- Are you proud of finished deliverables (project work products)? If yes, what's so good about them? If not, what's wrong with them?
- What was the single most frustrating part of the project?
- What was the most professionally gratifying part of the project for you?
- Which of our methods or processes worked particularly well?
- Which of our methods or processes were difficult or frustrating to use?
- Which libraries did we  use? Which were good? Which were bad?
- Which tools did we use? Which were good? Which were bad?
- Which APIs and external services did we use? Which were good? Which were bad?
- Did we write tests? How much was the coverage?
- Did you see any early warning signs that resulted in problems in the project? Please describe the signs you saw. What could we do in the future to better react to those signs?
- Did we get timely feedback about deliverables?
- Were there things you did that you thought were not under your responsibility? What were they?
- Did project stakeholders, senior managers, customers, and sponsor(s) participate effectively? If not, how could we have improved their participation?
- If you could wave a magic wand and change anything about the project, what would you change?
- Any additional things you'd like to mention?
