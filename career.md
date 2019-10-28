__" I am convinced that nothing we do is more important than hiring and developing people. At the end of the day, you bet on people not on strategies."__ We agree with Lawrence Bossidy regarding the importance of hiring and the effort that should be put into it. Here are some of the traits we look for in candidates for different levels of seniority and how someone might apply to Vinta.

# Career Paths

## Tech Leadership
Technical Leadership is a relatively new role in the world of software development. There's little structured content about it available in either books or blog posts. Most content is presented as reports on the goals and experiences of individuals or companies. This is a natural process as the industry adapts and learns what combination of attributions are best suited for the role, quite similar to what happened to the now much less obscure role of DevOps engineer. In the spirit of learning from feedback and collaboration, we want to be part of the debate by sharing what it means to be a Tech Leader at Vinta.

For us, Tech Leaders are accountable for various monitoring and guidance activities for a wide-range of perspectives, from systems to individuals. They need to have technology and architecture fluency to support business goals from a technical standpoint, as well as to keep up with co-workers' individual needs and goals. There are two big cornerstones to the role: People and Technology. I'd say they are equally important and will probably require about the same mental effort on daily activities. 

The Tech Leader of a project is not necessarily the most technically experienced person in the team and forcing such a thing is not wise. Primarily because the team would be losing productive time from someone that could be best allocated as a full-time programmer and also because that person might not be interested or willing to act on the People part of the job. So a Tech Leader is someone that can both smoothly deal with people and that has a very good understanding of the project in business and technical terms.

Here is the breakdown of the most important activities Vinta expects from a person in this role.

### The People Cornerstone

#### Communication
Tech leaders need to have an open and safe channel with team members. The goal is to build a relationship where people feel that they have the [psychological safety](https://rework.withgoogle.com/blog/five-keys-to-a-successful-google-team/) to impact the project. But at the same time they trust the Tech Leader's final decisions and will do their best to make them successful. Keeping up that kind of communication should also provide a better understanding about each team member's strengths and needs, allowing for a clearer overview of the team. It's not possible to be a good leader without knowing who you are leading.

#### Project Leadership
Technical decisions should always be backed by business goals. The language or framework choice for a particular project should be based on the knowledge of the current project's status and the vision of the business' next steps. The same goes for technical debts and refactorings: the decision to tackle them should be backed by precise project or business-related goals, e.g.: "this will help us to be more productive in the medium-term", or "there will be a change in feature X so we need to refactor this part of the code for it to be more flexible". This means that Tech Leaders need to keep up with the other project leaders. They need to be in sync with areas such as business, marketing and finance so they can take better technical decisions based on those. Keep in mind that other leaders will need inputs from the Tech Leader to better accomplish their work as well. It's the Tech Leader's job to push for the technical tasks to get included and accounted for during product planning. Communicating technical risks and negotiating trade-offs are very important activities here.

#### Mentorship
In-company mentorship programs are a great way to help people grow their careers and understand how to navigate through the company's processes and hierarchy. Everyone at Vinta has a mentor that will be available from time to time to hear and advise on those high level topics. This is a great resource, but in general it's aimed at medium/long-term goals. Tech Leaders can serve as great resources to fill in the gap of short-term advisory. Teams often have processes and specific needs and that require someone inside the project to pass them on. Also, Tech Leaders are experienced people that can advise on more specific things (i.e. people skills) that can be worked on, technologies that are more important to that particular project and also provide daily feedback on various aspects.

#### Pairing
Pairing is a great tool to pass knowledge on within a team. Teams that don't do full time pairing should be encouraged to pair from time to time. The more you mix people around, the better. Junior developers should pair with more experienced developers and experienced people should pair with each other now and then. Due to their understanding of the codebase and architecture, Tech Leaders should dedicate some of their time to pairing. This has some of the same goals as mentoring but from a more hands-on perspective.

#### Connecting People / Knowledge Matching
Time is limited and it's not always possible to be available to assist teammates. That means Tech Leaders should be smart about when to directly jump in and help or when someone else can be assigned. To do this it's very important that she knows not only what are the strengths of the people in the team but also build a strong network of people in the company that can assist on specific subjects. This will allow her to optimize how can people meet and help each other. Matching the right people is a great way to improve the performance of the team while also accelerating individual growth.

#### Managing Ownership
As we'll see later in "The Technology Cornerstone", there are many activities which the Tech Leader is ultimately accountable for (from a business perspective), but other people can be responsible to work on them. Those people should have the autonomy to execute key technical activities beyond feature development, but always receiving timely feedback from the Tech Leader to ensure continuous improvement. The Tech Leader must empower people to be owners of key aspects of the software product, like security or backups. That ownership can also rotate periodically to avoid creating gatekeepers or increasing risk due to concentrated skills. Rotating roles can also force people to document better, create processes, and consolidate knowledge. Additionally, the Tech Leader must ensure no activity is being forgotten, i.e., there are no ownership gaps.

#### Hearing / Trusting the Team
Under no circumstances should Tech Leaders act as gatekeepers. Although they are experienced developers, this doesn't mean that technical decisions should be taken without consulting the team. Everyone in the team, regardless of experience level, should be encouraged to speak and have a saying in all parts of the code. Ultimately it's up to the Tech Leader to decide what will be done, but all decisions should take the team's inputs into account. This also means that Tech Leaders should not own any part of the code. There's no architecture or feature that can only be implemented by the Tech Leader. Such a thing is a red flag and can lead to disastrous situations like burnout for the Tech Leader. A much healthier approach is to act as coach, unblocking and helping other people to work on those complex tasks.

### The Technology Cornerstone

#### Monitor the Codebase
As one of the most experienced programmers in the team, the Tech Leader should have control of the codebase. What languages and libraries are being used? How long since they've been updated? Are there any security updates available? What architecture will be used for that new feature? Are code practices standardized? Are tests being properly written? How fast is technical debt growing? Are the gains really worth the compromises of acquiring that debt? Those are some of the questions the Tech Leader should be constantly thinking and also inquiring the team. Here is a list of tasks that need continuous monitoring:
- Libraries' and tools' updates
- Security releases (especially for the major tools and frameworks)
- Development processes and methodologies
- Linters (to easily standardize practices)
- Test coverage and depth (unit, integration, acceptance, etc)
- Permission tests in all endpoints
- Technical Debt (tracking and paying)
- Continuous Deployment
- Database Migrations (forwards, backwards)
- Feature Flags (managing and cleaning)
- Configurability (hard-coded values vs. environment vars vs. admin toggles)

#### Guide Architecture
Good architecture decisions can save a lot of development time. Regardless of the size of the feature, insights from an experienced person can reduce a lot the effort to complete a task, simplify solutions and improve the code quality. This kind of insight can only come from someone that is an experienced developer and also has a good understanding of the project business logic. Therefore, it's a perfect task for Tech Leaders. It's important to emphasize here that although Tech Leaders should have the final call on architectural decisions, they should always take into account inputs from the team and should act as mentors, not gatekeepers of complex tasks.

#### Monitor Application Service-level
Growing is painful, so preparing for growth can avoid a lot of stressful situations. At the beginning of new projects, is common to trade system performance and robustness for development speed. While in many cases those are worthwhile tradeoffs, they should be taken carefully as the software product grows. Tech Leaders should keep an eye on application metrics to foresee increasing demands and prepare for them at the appropriate time. Additionally, they should always be closely looking to the most critical points of the application, i.e., the key transactions where failure is the riskiest for the business. Some key activities related to service-level monitoring are:
- Scaling up application infrastructure (including optimizing settings)
- Setting up and reacting to alerts for application performance and uptime (using New Relic, for example)
- Setting up and reacting to alerts for errors (including end-user specific errors, like 4xx HTTP errors or frontend errors, using Sentry, for example)
- Enforcing backup policy (including periodic verification of backups)
- Enforcing logging policy (including end-user activity logs)
- Ensuring proper platform compatibility (specific browser versions, network conditions, etc)
- Documenting and enforcing quality-ensuring processes (downtime recovery, error postmortems, QA, deploy and release, end-user support, …)
- Other [non-functional requirements](http://evolutionarytesting.blogspot.com/2012/12/non-functional-requirements-checklist.html)

Note that the Tech Leader isn't the sole responsible for those activities, but she's the one Accountable (the A in the [RACI matrix](https://en.wikipedia.org/wiki/Responsibility_assignment_matrix)) for them. If anything goes wrong, the blame ultimately goes to the Tech Leader, because from a business perspective she's the one that should ensure the proper execution of tech-related activities.

#### Support and Monitor Customer Success
Happy customers is the goal of the best products. There's no point in having a great codebase, with the perfect architecture, if customers are not satisfied with the product. Customer Success (CS) is often the role of a full time person (or a whole team, depending on the size of the product) so it's not something a Tech Leader can keep up all by herself. But it is her job to make sure the people doing it have the tools and the data to support their work. This involves adding functionalities that will facilitate the CS job, adding as many metrics and logs as possible to the product (especially to the critical flows and key transactions). Besides the service-level metrics and logs, [UX KPIs](https://designmodo.com/ux-kpi/) like *Time on Task* are other important Customer Success goals that Tech Leads can help the CS person to track and improve. Also, the Tech Leader should empower the team to answer questions and solve bugs swiftly (by ensuring good communication channels and processes, for example).

#### Code Reviews
A great way to keep up with all parts of the system and mentor coworkers is by reviewing PRs. PRs are a great place to give feedback, identify when architecture is tilting to the wrong side and keep a good overview of different parts of the codebase. Tech Leaders should do as much PR reviewing as possible but doing all or close to all reviews is considered a bad practice. Everyone in the team should be reviewing each other's code for the same reasons previously mentioned, with the added bonus that it's a good way for less experienced people to learn.

#### Experiment
Tools get outdated and new improved stuff is constantly released. Many times those can improve code quality, speed up development or automatize some process. Tech Leaders should keep an eye on those and systematically experiment and review if they are useful in the team's context.

#### Guide through Crises
Crises will eventually arise in all projects. It's important that Tech Leaders are prepared for them because many times there will be people in the team that are not. Keeping calm and thinking straight during those situations is required and will also give the confidence the team needs to sail smoothly through crises. Tech Leaders should know who among the team are the best to tackle the situation while also asserting how many people should be deviated from their planned tasks to work on it.

#### Tackle Tasks
Last but not least, Tech Leaders should keep actively working in project tasks. The hard part of this is actually choosing the right kind of task that will fit the schedule. Tech Leaders need to be very smart so they keep up with technical work without leaving aside all the other important activities. It's normally a good idea to look for challenging tasks with a stretched deadline. What is the best kind of task will vary according to the current project needs, but the key thing is to keep working on things that you enjoy and that you will be proud of at the end of the day. There's no such thing as a non technical Tech Leader. 

# Career Levels

We believe in creating the best learning environment possible here at Vinta. In order to do so, we need to show a clear way ahead for all employees. We also know that everyone grows in their own way so there is no point in creating a line for people to follow, we need to go wider than that. That's why our levels are an unordered list of treats we think our employees need in order to become experts in our field. The overall is this:

* We have four levels (Junior Developer, Developer, Senior Developer, Leader Developer);
* Each level is divided in a number of sub-levels:
    * Junior Developer: 3 sub-levels.
    * Developer: 6 sub-levels.
    * Senior Developer: 10 sub-levels.
    * Leader Developer: ∞ sub-levels.
* We review salaries at the end of experience period (when someone starts at Vinta) and every 6 months after that.
* We evaluate subjectively alongside the employee (it's not a top-down assessment, it's a mutual evaluation). Points are evaluated granularly, so every effort counts.
* Each point can be evaluated as a Strenght, In process, Weakness or In need of Validation.
* Each employee has a personal spreadsheet where his/her plan is listed.
* To reach level X+1, the employee needs:
    * Strengths judged important from level X-1 and lower.
    * Substantial amount of Strengths in his own level.
    * Some Strengths from level X+1.
* Points can be added or removed in the future, this is a snapshot, not set in stone.

## Levels

Junior Programmer:

* Minimum of 1 year of experience with web development.
* Masters the basics of at least one of the stacks: Frontend or Backend.
* Comfortable with routine features.
* Can post and solve internal easy picks (playbook/boilerplate/site).
* Can communicate in English (slack and meetings).
* Gives talks in local events.
* Writes simple blogposts.
* Can post and solve opensource easy picks.
* Gives internal talks at Pyzzas.
* Posts relevant content in Lessons Learned.
* Keeps in track allocated activities.

Programmer:

* Minimum of three years of experience with web development.
* Masters one of our Stacks: Frontend or Backend.
* Helps less-experienced Developers.
* Identifies and solves internal issues (playbook/boilerplate/site).
* Can give opinions and argument about technical decisions and project architecture.
* Is responsive in cases of emergencies.
* Can organize ideas and make complex arguments in English.
* Gives talks at Regional/National conferences.
* Writes intermediate blogposts.
* Comfortable in contributing, submitting fixes and improvements on opensource tools he/she uses.
* Can specify features with team and client.
* Capable of self-management, organizing activities and keeping them on track.

Senior Programmer:
* Minimum of four years of experience with web development.
* Can work well with management and development activities.
* Comfortable in managing client's expectations.
* Keeps team motivated and learning.
* Conceives and implements new processes within Vinta.
* Gives talks at International conferences.
* Writes advanced blogposts.
* Maintains Vinta's internal libs, either by finding bugs, listing possible improvements, coding on the lib or delegating accordingly.
* Capable of mapping demands on development process and suggesting improvements.
* Capable of giving well-referenced opinions about technical and architectural project decisions.
* Can anticipate client demands about team size and possible opportunities for Vinta to aggregate more value on project.
* Comfortable in crisis management.
* Deep understanding of at least one web development area (API, SPA, SQL, etc.).

Leader Programmer:

* Minimum of six years of experience with web development.
* Comfortable in leading big projects, with interdisciplinary teams.
* Attracts projects to Vinta due to market and community presence.
* Has relevant contributions in large-scale opensource projects.
* Is nationally recognized by the community as an expert in one area of knowledge.
* Talks to outside of the company and dictates development tendencies.

# Internal Growth

## Pyzza Internal talks
Every 15 days we gather some people to discuss a topic of interest. This is a very good moment for people to hone their presentation skills, study about something they like, and spread their diverse learnings around the company. It's also another good moment for those "I think that's worth a blogpost!" quotes. Beer and pizza are on us!

## Courses and Books
Just name it, Vinta will buy technical books and courses (online and offline) for anyone. It helps to sustain  the learning atmosphere we’ve come to believe in.  A delightful not-too-farfetched chaos theory bit: a book read turns into a blogpost, that turns into a better delivery for our client, that turns into a new client.

# Open spots and requirements

Here is an overview of what positions we hire. The requirements, work-routine, work-benefits and everything else is described (in Portuguese) in the [career section of our website](https://www.vinta.com.br/careers/).

* Developer: Works to create technical solutions to our clients in the best way possible. All developers here are full-stack and have full ownership of the code-base. Discussing architecture, developing in Python/JS and defending processes that implement quality are the central tasks for this spot.

* Senior Developer: Beyond what the regular developer works, this spot is also responsible for the technical growth of the team, the ever-lasting search for processual and architectural improvements in the project, and the product concerns of the project.

* UX designer: Works to guarantee that value is delivered the best way possible to the end user of our client. Discussing, mocking interfaces and conducting research are the main directives for this spot.

* Intern: This spot's only concern is to learn and be available and fit for hire in the shortest time possible. Our training process described below in this section ensure that happens within six months.

# Our Hiring Process

The hiring process for developers is divided into three steps aimed at measuring technical prowess, communication skills, and management abilities. The designer hiring process works slightly different, if you want to know more about that, please send an email to contact@vinta.com.br The steps are as following:

* Interview: here we have an open conversation with the candidate, that's the best way we found so far to evaluate culture-fitness and professional experience;

* Pairing: This step focuses on the ability to explain your technical process and problems and common difficulties and problems that happen along the way;

* Project: in this step, we send the specs for a project that needs to be delivered in a fortnight. Our point here is to evaluate good practices and expectation-management on the client side.

## Go straight to the code

You can implement a project and get a head-start on everyone else!

Explaining: knowing how to choose a good programmer is a very difficult task. There is not a single way that works for most companies and there is a lot of talk about why one way is better than the other. For us, the process is divided into three parts, the third being a small project. When the project is given to a candidate, we also state that it’s to evaluate **good software practices, testing, and problem-solving skills**. In order to mimic our open-scope environment, we set an initial deadline that can be rescheduled if more time is needed (when correctly reported, this saves both the candidate and us a lot of stress).

### What you need to do?

* Read carefully every requirement on the specification;
* Make sure you understood what is a necessary requirement and what is optional;
* Setup a github/bitbucket repository for your code;
* Deploy your project on a host service (we recommend [heroku](https://heroku.com/));
* When you finish the project and feel it's ready, [apply here!](https://vintasoftware.typeform.com/to/Xb6aIu)

### Specifications for the project

Here you can check the [requirements of the project](https://docs.google.com/document/d/1Evi-kghklIcwJ33SFqPyGREB4OVfNJXX4EOfrWuhhwY/edit?usp=sharing). It's in Portuguese cause we don't want the candidate to misunderstand anything (that could lead to a final delivery that doesn't match the expectations and we'd miss the candidate only because of a misunderstanding).

# Internship at Vinta
We know it’s tough to start working at the tech industry. At Vinta, we developed our process to prepare anyone for a full-stack job using Python and Javascript. We've compiled all the courses, relevant content, philosophy, activities, and tips from our interns to help you go all the way through our tech stack.

## Philosophy behind the whole process
We always hire interns with a clear goal (we also make that goal clear to them from day one), that is to hire them as juniors in a year time. The whole process is designed to maximize learning opportunities, knowledge sharing, and professional development. In order to do that, we believe three things are essential:
- Code best practices and development process should be a concern from day one;
- The person’s only focus should be on learning and growing professionally, so books, online courses, and more experienced developers should always be available;
- Knowledge should be demonstrated and consolidated through building things. Reading is awesome and necessary, but true growth is achieved through projects.

## Steps of the process
First, every intern here develops a toy project. Then the person is integrated into a project (with full access to production environment) working non-billable hours for the client and finally, the person is hired as a junior and starts working billably for the client. This whole process lasts on the maximum 12 months, but eight months is usually more than enough.

## What you’ll learn
- General
    - APIs
    - Object Relational Model (ORM)
- Python
    - Django
    - Django Rest Framework
    - Celery
    - Celery Beat (to schedule tasks)
- JavaScript
    - React
    - Jest (frontend tests)
    - Redux
    - Redux Thunk
    - Normalizr

## Internship project on Trello
We try to avoid overwhelming people that are beginning to learn a stack. So the first thing every intern does here is to receive this Trello board. The cards are already separated and ordered to maximize learning. The idea is to start with a Django app and then to rewrite the front using React. The lists are ordered according to the priority of deliveries, it’s important to follow the order and develop every feature without parallelization so that you’ll learn faster. **Remember to read the card named Project Specs first to get an overview of the project!** You can check it below:

https://trello.com/b/oRHqnioo/template-pokebattle

To copy the board, press <kbd>W</kbd> and click on **More > Copy Board**.

## First step: become an intern
If you've read it until here and enjoyed our way of thinking, [come forward and join us!](https://www.vinta.com.br/careers/)
