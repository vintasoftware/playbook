# Development

## Style Guides

### Python
- [PEP8](https://www.python.org/dev/peps/pep-0008/).

### JavaScript
- [Airbnb JS Style Guide](https://github.com/airbnb/javascript).

### HTML & Sass
- [Frontend Guide](guidelines/guideline_frontend.md).

## Development principles
- KISS: Keep it simple, Sweetie (not stupid!).
- If there's no way to keep it simple, make sure there are comments.
- Functions/methods/classes/modules must have a single concern.
- Even commits must have a single concern, so commit as often as possible (try not to have an "and" in commit messages).
- Every piece of knowledge must have a single, unambiguous, authoritative representation within a system. Stay DRY: Don't Repeat Yourself.
- Reuse domain/business logic, because those must be always consistent.
- But prefer duplication over the wrong abstraction.
- After all, premature generalization, as well as premature optimization, is the root of all evil.
- Because probably YAGNI: You aren't gonna need it.
- Better to isolate code that changes often from code that doesn't.
- And write code that is easy to delete, not easy to extend. Things change in unexpected ways.
- Feature flags help with this. They decouple feature releases from merging branches and deploying. And help to decouple behaviors.
- Decoupling is good if it gives you power to easily add, change, or remove code. If not, forget it.
- Pure functions are always decoupled from state and time. Avoid side effects.
- But remember that complex is better than complicated.
- Write readable code. Readable code is less likely to contain bugs, because readability makes bugs more visible.
- Know that design matters.
- And UX matters even more.
- All code should be reviewed.
- All features must be manually tested before going to production.
- And again, keep it simple.
- Some in-depth resources related to those principles:
  * [KISS principle](https://en.wikipedia.org/wiki/KISS_principle)
  * [Separation of Concern vs Single Responsibility Principle](https://weblogs.asp.net/arturtrosin/separation-of-concern-vs-single-responsibility-principle-soc-vs-srp)
  * [Don't repeat yourself](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself)
  * [Premature Generalization](http://wiki.c2.com/?PrematureGeneralization)
  * [YAGNI](https://martinfowler.com/bliki/Yagni.html)
  * [The Wrong Abstraction](https://www.sandimetz.com/blog/2016/1/20/the-wrong-abstraction)
  * [The Wrong Abstraction, HN discussion](https://news.ycombinator.com/item?id=11032296)
  * [Write code that is easy to delete, not easy to extend](https://programmingisterrible.com/post/139222674273/write-code-that-is-easy-to-delete-not-easy-to)
  * [Feature Toggles (aka Feature Flags)](https://martinfowler.com/articles/feature-toggles.html)
  * [Zen of Python](https://www.python.org/dev/peps/pep-0020/)

## Environments

### Staging
- Should be as similar as possible to production.
- It's OK to delete the database (but do tell the client before doing so).
- Keys should be the same as in production (keep them in an untracked .env or .ini file so they are not pushed to the repository). If the third-party service supports test-API keys (like Stripe), use them here.
- Like in production, developers need to receive errors via Sentry (configure it to send e-mails to the one(s) responsible).

### Server access information
- Create a `DEPLOYMENT.md` file.
- That file should explain the basics how-to of the server (how to access app code, restart/stop the server and services).

### Config project files
- Create a Last Pass Secure note with your `.env` file.

## Production and Staging services
- Check the <a href="https://devchecklists.com/production-launch-checklist/" target="_blank">Launch Checklist</a>

## Libs and Tools we use
We use several open source projects as part of our tech stacks - both on backend (Python) and frontend (JavaScript/React).

* [Backend](stacks/backend.md)
* [Frontend](stacks/frontend.md)

## Feature implementation
Once allocated to a feature, the developer should follow the [Feature development workflow](checklists/feature_development_workflow.md), which includes using [git-flow](http://nvie.com/posts/a-successful-git-branching-model/) and satisfying the [PR workflow](checklists/pull_request_workflow.md).

## Code and feature review
All code is reviewed before being merged to master. The reviewer not only checks code quality, but also if the feature was implemented according to what the client expects. It's very important for the allocated reviewer to strictly follow the [PR review workflow](checklists/pull_request_review_workflow.md).

## * [Frontend](guidelines/guideline_frontend.md)
## * [Landing Pages](guidelines/guideline_landing_pages.md)
## * [Management with Asana](guidelines/guideline_asana.md)
## * [Presentation](guidelines/guideline_presentations.md)

# Security

Security is no easy topic to talk about. There are many ways to explore vulnerabilities in a website, as well as security implications for day-to-day practices and processes. To address that we follow security guidelines and use well known and tested tools to reduce risks. Although writing code that is robust and tested against vulnerabilities is essential for secure applications, it's well known that [social engineering](https://en.wikipedia.org/wiki/Social_engineering_(security)) is many times the weakest link in the chain. For that, we enforce tools and practices that tackle this kind of problem. Below are our processes for reducing security-related risks:

## Employees and Accounts
- 2-factor authentication everywhere it's possible (enforced to everyone on our organization accounts on GitHub, Google G Suite, etc)
- Email managed by Google G Suite
- LastPass managed passwords for all shared accounts
- Encrypted disks on all computers
- Invalidation of all accounts and keys when a employee leaves the company
- No reuse of email addresses of employees that left the company
- Deletion of all code and assets after we leave a project

## Code Security
- Static analysis with [dodgy](https://github.com/landscapeio/dodgy) (to avoid secret keys on code) and [bandit](https://github.com/PyCQA/bandit) (to avoid common vulnerabilities), configured both in CI and pre-commit hooks.
- Dependency insecure version management with [safety](https://github.com/pyupio/safety) (on CI) and [GitHub Security Alerts](https://help.github.com/en/articles/about-security-alerts-for-vulnerable-dependencies)
- Critical flows review checklists during code review and QA

## Application Security
- [Sqreen](https://www.sqreen.com/)
- <a href="https://devchecklists.com/production-launch-checklist/" target="_blank">Launch checklist</a> that we run periodically, to check things like Django settings, oAuth keys rotations, SSL health, etc.
- Unprivileged run (we mostly use PaaS like Heroku)
- Avoiding downloads of production data, and if it's needed, it must be anonimyzed before download
- Exception monitoring with [Sentry](https://sentry.io/)

## Encrypting Sensitive Messages
Every once in a while it's necessary to transfer security sensitive information such as passwords to clients. Use GPG to encrypt that kind of information

- **Linux Users.** We recommended [GPA](https://www.gnupg.org/software/gpa/index.html), a graphical interface for GnuPGP. Follow [this tutorial](https://www.deepdotweb.com/2015/02/17/basic-guide-pgp-linux/) to install and learn the basics.
- **Mac Users.** [PGP tools is easy to install and use](https://gpgtools.org/).

## Additional resources
- [The SaaS CTO Security Checklist](https://www.sqreen.com/checklists/saas-cto-security-checklist)

# Checklist index
## External
* [Dev Checklists](https://devchecklists.com/)

## Internal

* Creating cards on Asana:
  * [Feature card creation.](checklists/feature_card_creation.md)
  * [Bug card creation.](checklists/bug_card_creation.md)
* Meetings:
  * [How to prepare for meetings.](checklists/meeting_preparation.md)
  * [Sprint meeting.](checklists/sprint_meeting.md)
* Development:
  * [Developer Onboarding.](checklists/developer_onboarding.md)
  * [Landing Pages.](checklists/landing_pages.md)
  * [Feature workflow.](checklists/feature_development_workflow.md)
  * [Wiki](checklists/wiki.md)
  * [Daily Deploy](checklists/daily_deploy.md)
* Pull Request:
  * [PR workflow.](checklists/pull_request_workflow.md)
  * [PR review workflow.](checklists/pull_request_review_workflow.md)
* <a href="https://devchecklists.com/production-launch-checklist/" target="_blank">Production Launch</a>

# Agile Process Guidelines

___"Artists know that there is no creativity without a system of formal restraints."___ What Kathy Galloway said also applies to projects, the best and most creative work comes from a set of refrains that doesn’t  choke anyone and guides them to a better result. Here are ours.

## Methodology overview
Vinta works following an [Agile](http://www.agilemanifesto.org/)-like methodology:
- Sprints, two-weeks long. Sprints are a lightweight process aligned to "Responding to change over following a plan".
- Use of [Asana](https://asana.com/) as the main management tool. There we align expectations, because we want "Customer collaboration over contract negotiation".
- Use of [GitHub](https://github.com/) for Git repository hosting and code review, along with a  continuous integration tool, like [CircleCI](http://circleci.com/) or [Travis CI](https://travis-ci.org), so  we ensure "Working software over comprehensive documentation".
- Use of [Slack](https://slack.com/) for real-time communication, since we consider "Individuals and interactions over processes and tools".

## Product Managers duties
Usually, the product manager role is filled by someone on the client's side. These are our expectations:
- Keep the business and the development team closer.
  - Communicate strategic decisions to the development team and help it to update priorities accordingly.
- Be responsible for the product's decisions making, asking for advice when necessary.
  - Produce feedback for UI/UX deliverables. Also accepting input from the design team.
- Be responsible for communication with the technical team.
- Produce insights for mid and long-term product strategy (quarter-based).
  - By getting inputs from all stakeholders, including the development/design team.
  - By analyzing risks and tradeoffs.
- Keep Roadmap updated considering technical challenges and product strategy.
  - Together with the development team.
  - Warn team about changes ASAP to avoid development work loss.
- Be aware of the development team needs, such as new developers, designers, QAs, etc.
- Planning and syncing project major releases among development and business teams.
- Provide and analyze metrics and data from development team aiming to support product strategy.
- Validate technical team decisions that impact product strategy.
- Find, analyze, and sync strategic partners.
- Analyze regularly competitors features/flows.

## Project Managers duties
- A Project Manager's most important duty is to manage client's expectations and keep them realistic. We realize most of the problems in software development come from communication issues, and the Project Manager at Vinta is the 'Communication Person'. The Project Manager should always track the deliverables for the next sprint and, if any problems are to appear, features must be simplified, development strategies re-evaluated, and priorities re-defined, always sided with the client. That's easier said than done in some cases, but surely brings benefits for us and the clients.
- The Project Manager will be the main point of contact with the client. It's good for everyone to have an open communication channel directly with the client, but the Project Manager should be aware of all project-related decisions. However, regarding assigned tasks, each developer is free to discuss and validate it directly with the client. Should the client ask the developer to do another task, this needs to be tracked and communicated to the Project Manager. Maybe the manager knows better the priority, even better than the client, so s/he needs to step in.
- Project Manager will work on the project as a developer too.
- Project Manager should encourage everyone to manually test all features before validating them with the client.
- Project Manager should remember developers to report daily on what they are working on.
- Project Manager should alert everyone to turn off Slack "do not disturb" option so the client can reach them in case of emergencies.
- Project Manager should make sure there are no ownership gaps in the project. When everybody is responsible for some parts of the process, there might be gaps where no one acts. The project manager must be aware of those gaps and address them with the team. Critical aspects of the project such as support, deploys, QA, security, etc must have a person clearly responsible. Project Manager should also inform the client who's responsible for each aspect. This kind of ownership gives team members responsibility and autonomy.
- Project Manager should ensure the project's documentation is up-to-date and make sure it's shared with the Client.

### Daily Attributions

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
- Managed on Asana ([See our Asana Guideline](guidelines/guideline_asana.md)).
- Two-weeks.
- Friday to Thursday.
- Never deploy to production on Fridays.
- Weekly Sprint Meetings.
- [Sprint Meeting checklist](checklists/sprint_meeting.md) must be followed.
- [Daily development reports](development.md#daily-reporting).

## Sprint

### Development
Read [Development section](development.md#development) to understand how features should be implemented and what are the coding guidelines.

### Retrospective
The retrospective is the moment to evaluate the work that was done on the previous sprint(s). Every person must think on their own and collaborate with the team to propose solutions. There's no right answer as to how often retrospectives should happen, they can be weekly, biweekly, monthly. The periodicity depends on the team's needs.

There are different techniques that can be used such as **Daki Exercise**, **Stop, Start, Continue**, etc. However, the general idea is to have a clear vision of:
- What the team learned
- What was good
- What was bad
- What can improve

### Deployment

It is proven that a high deploy frequency is a good DevOps practice and gives a lot of benefits in the Agile process. Google considers multiple deploys per day as a [factor to consider a team as an Elite Performer](https://cloud.google.com/blog/products/devops-sre/the-2019-accelerate-state-of-devops-elite-performance-productivity-and-scaling.).

Deploying more frequently:
 - Represents having smaller changes, which means less risk.
 - Decreases the time between a feature being ready and being live.
 - Encourages better feature QA, since features will spend less time on Staging until they launch to Production.
 - Increases code review quality, since changes tend to be smaller.
 - Incentivizes breaking up bigger tasks in smaller ones that can be deployed as soon as they are ready.
 
 Visit our [Daily Deploy Checklist](checklists/daily_deploy.md), that describes a process for Daily Deployment at Vinta.

#### Good Practices
- Encourage the team to track topics they want to discuss at retrospectives.
- During the retrospective, take notes to keep track of feedbacks and goals defined.
- Open past notes and discuss how every feedback from the last retrospective was addressed.
- Brainstorm and discuss new inputs for each topic. But keep discussions objective.
- Don't sink into unnecessarily long dialogs. Some teams adopt a limited time frame.
- Try to keep discussions about processes. Avoid long technical discussions.
- Make sure topics discussed translates to actions.

**DAKI Exercise**

*D* for Drop: When team members want to drop or remove something that bothers them. For example, a team wants to remove (drop) weekly meeting with their manager because of micromanaging.
*A* for Add: What does the team want to add to improve the process? Perhaps adding a weekly breakfast for the whole team or a company to share feelings/feedback with the rest of the people.
*K* for Keep: When team members want to keep something. For example, the team decides to keep a stand up meeting with a song chosen by a team member.
*I* for Improve: Something that a team wants to improve. A good example is when a team reduces the technical debt from a legacy code to avoid fixing bugs all day long.
