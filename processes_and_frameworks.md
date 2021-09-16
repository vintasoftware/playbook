# OKRs

Objectives and key results is a high-level prioritization framework, important to work in a goal-focused mindset. Do we know what is most important for a team in the short term? The idea is to increase productivity and improve work quality.

The OKRs cycle works in 3 phases: first, we need to set a plan for the quarter and make it visible for the whole company, then follow up on the progress, and resume by ending the OKR plan and sharing results. 

> In one California study, people who recorded their goals and sent weekly progress reports to a friend attained 43% more of their objectives than those who merely thought about goals without sharing them.

Here are some guidelines from John Doerr in his book Measure What Matters:
- Less is more. The ideal number of quarterly OKRs will range between 2 and 5. Too many objectives can blur focus on what matters.
- Objectives should be ambitious, pushing us out of our comfort zone. They should, however, be realistic. 
- Try to strike a balance between aspirational and grounded objectives. That depends on the risk our company is willing to take.
- OKRs are neither a catch-all wishlist nor the sum of a team’s mundane tasks. They’re curated goals that will move people forward in the here and now. 
- OKRs should not be dictated, but decided in agreement with the team, taking into account the long-term goals and the company strategy.
- If an objective is well-framed, 3 to 5 KRs will usually be adequate to reach it.
- KRs should be succinct, specific, and measurable.
- Completion of all KRs must result in the attainment of the objective. If not, it’s not an OKR. 
- Each key result should be a challenge in its own right. 
- Pair KRs to ensure we will deliver quality, not only quantity (i.e. if we’re delivering lots of effort points every week but our UIs are full of inconsistencies, the effort KR is poorly formatted).
- KRs should be easily trackable by the entire team, without requiring lots of manual work from managers.
- A KR can be adjusted or even abandoned mid-quarter if we feel like it’s not that relevant, it’s poorly formatted or is unrealistic.

# Sprint Planning

The Sprint Planning occurs in the sprint’s previous week. It involves a series of different steps performed by the Manager.

## Pre-planning 
Before starting the planning, it’s important to have synced with the Product Owner in order to ensure that upcoming goals are clear and that we are on the same page.

## How-to
- Gather tasks that should enter the upcoming sprint.
- Hydrate user stories making sure the cards are ready to be estimated in case they are not already estimated.
- Estimations should follow the Planning Poker process.
- Consult the team to know if there will be tasks rolling over from the previous sprint. This is part of the Sprint Review process. 
- Analyse team metrics to understand how many points are expected to be completed, what’s the effort each engineer is doing per day or per sprint, and how many points are rolling over to the upcoming sprint.
- Based on the points that are rolling over, the tasks that were estimated, the client’s goals, and how many engineers effort points are available, define a sprint proposal.
- Assign tasks making sure the effort points per engineer is in accord with the team’s standard.
- Add any additional details on the task, such as custom fields or tags.
- Document the sprint plan in Asana or a document including:
  - Goals and the expected value outcome;
  - Tasks;
- Validate the plan with the Product Owner and make adjustments as necessary.
- Once the plan is ready, update the sprint goals on the Sprints Points report.

# User Story Hydration

This is the process of producing ready for development user stories. The main goal is to have sized and well contextualized stories that gather all the information needed to kickoff a feature.

## How-to
1. Demand Identification: This is the process of managing demand and expectations from customers and business stakeholders and aligning them to a product roadmap. It is expected that at the end of it the PO communicates to the PM [in a verbal or written form] what is the demand.
2. Business Goals Gathering: The output of this activity is a milestone (AKA: epic) with a general description of the intended goal placed in the backlog. It might require a light investigation in the form of a simplified discovery and a quick tech review to assess feasibility and the rough cost. The goal is to have enough context for the milestone to be prioritized. Although this is primarily done by the PM, it can also be executed by the PO or a designer with enough context.
3. Backlog Refinement: This is the process of periodically re-prioritizing milestones in the backlog as we learn from the product and adapt to changes. During this process it's expected that more context is included in the milestone card. Once a milestone is selected as the topmost priority, it moves to the next step.
4. Discovery & Assessment: Executed by an assigned designer from the team. This is the process of understanding the problem with the customer and proposing a solution path. The assigned designer must be in constant sync with the stakeholders proposing solutions and listening to feedback, risk assessment and the constraints that should be taken into account. Stakeholders are: customer, PO, PM, TL or an experienced developer. At the end of this process it's expected that there's enough technical context (design and software) so it's possible to estimate the work needed to deliver design assets.
5. Design Estimation: This is executed by everyone in the design team and optionally the PM.
6. Design Interface Development: Executed by an assigned designer. This is the process that results in the delivery of design assets: lo-fi mocks, hi-fi mocks, documentation, ... . Just like in the “Discovery & Assessment”, it’s expected that stakeholders (customer, PO, PM and experienced developer) are involved in this process.
7. User Story Breakdown: This is the process of breaking milestones into sized user stories that can more precisely be estimated by the development team and that will latter enable paced feature deliveries.
8. Design Assets Filling: Executed by the designer who executed the design interface development. It's expected that at the end all the user stories contain references to the design assets produced earlier.
9. Technical Context Filling: Executed by any experienced developer. It's expected that at the end each user story has information about the caveats of implementing the feature, risk assessment and references to the code base and documentation that might help the developer working on it.
10. Technical Estimation: This is executed by everyone in the development team and optionally the PM.

# Estimation

The estimation meeting is a ceremony to discuss and estimate in story points the user stories that went through our user story hydration process. The project manager is in charge of deciding which user stories will be subjected to estimation. We use the [planning poker](https://www.mountaingoatsoftware.com/agile/planning-poker) technique in order to reach a consensus on the effort points estimation of each user story.

## Story Points
In order to provide a more precise estimate, we use the Fibonacci sequence rather than a linear sequence. It can be easier to decide, for example, if something is “a 5 or an 8” instead of if it's “a 6 or a 7”. Ideally, the story points should be limited to:
- 0.5 for a set of quick changes (like adding some text on a page). Should take approximately 1 day of work
- 1 for a small change that requires a bit more care and may not affect other parts of the system
- 2 for a change that might require further testing and can change how other parts of the system work
- 3 or 5 for larger changes

Any user story that’s estimated beyond the upper limit (5 points) should be reconsidered for discussion and possibly divided into more user stories. On the other hand, any user story that is below the lower limit (0.5 points) should be grouped with other stories to form a single story of 0.5 points.

## Bias
Keep in mind that we need to avoid biasing the members' decisions in order to reach a more precise estimate, so each decision must be anonymous. There are a few ways to deal with this:
- Directly messaging the meeting organizer
- Using a bot to host the planning poker session
- Using an online application (e.g.  Planning Poker Online)
- Using a planning poker app on mobile

## How-to
- User stories should be identified beforehand or located on a dedicated estimates board. This might vary depending on what issue tracking tool is being used.
- Each user story will then be selected by the manager and the Tech Lead will brief the team.
- For each story, the members will have some time (2 minutes max) to think about how many story points should be assigned through a planning poker session. If the manager ensures there is a consensus, the team will move on to the next user story.
  - [What are story points and how you estimate them](https://www.atlassian.com/agile/project-management/estimation)
  - [The planning poker technique](https://www.mountaingoatsoftware.com/agile/planning-poker)
- When there is a large discrepancy between each team member estimation, the manager decides if the feature needs to be estimated again. If so, the members will have some time to explain their thoughts and then the team will estimate again.
- If the estimate reaches 5 points, it is recommended that the user story gets divided in several stories of 1 or 2 points.

## Avoid Nitpicking
Estimations of individual tasks do **not** need to be precise. The goal of estimating is to have well-defined Sprints (bundles of tasks). Variance of task estimations vs. actual effort is natural and should not be addressed. But the estimated vs. actual effort variance of a Sprint should be low. It's fine if tasks are estimated incorrectly. It's bad when a Sprint is estimated incorrectly. The former doesn't necessarily cause the latter, because estimations SHOULD vary both UP and DOWN. Therefore, although there could be high variance per task, there should be low variance per Sprint (bundle of tasks). 

# Daily meeting

The Daily meeting is a short, time-boxed meeting held every working day to provide faster feedback and enable quick adjustments to the sprint flow. It aims to align team members around short-term goals, allowing them identify and address challenges that prevent priority work completion.

## How-to
- The meeting should last between 5 and 15 minutes and be held at the same time every day.
- At a scheduled time, team members should meet or join a video call. If the meeting is in person, everyone should stand up. If it is remote, remember to turn on the camera.
- Each team member should then answer the following questions:
  - What did I accomplish since the last meeting?
  - What will I do today?
  - What obstacles, if any, are impeding my progress?
- If a team member brings up a topic that requires further discussion, track for solutions after the meeting.
- If there are any announcements, save them for the end of the meeting.

# Retrospective Meetings

The main purpose of a retrospective meeting is to create a supportive, positive atmosphere where team members feel empowered to share their valuable feedback, and suggest changes that can lead to future improvements. It provides the team with an opportunity to reflect upon failures and celebrate success. It is structured in a way that makes sure every aspect of the learning process within a sprint has been targeted.

# Onboarding

The Onboarding process is divided into meetings, and each meeting will present a different aspect of the project. For every new member, an old member will volunteer to be their buddy, who will be in charge of taking care of the onboarding process and guiding the newcomer. The main goal is to approach important topics a new member on the team should be familiar with and help them in the process to make it as comfortable and effective as possible. Also, it’s important to have the whole team involved to make integration easier and natural.

# Release Notes

Like other user-facing documentation, release notes are an opportunity to communicate with your end-user. If produced periodically, they are an important part of a delightful user experience. Here are some tips you should consider if you’re applying this process to your project:
- Use plain language: remember who you’re writing the notes for, and avoid technical jargons. Speak for the team and write them as if you’re telling the news to a friend making sure the benefit is perceivable. For example, use “We”, instead of a passive voice and complement with “this should make X easier/faster/more straightforward/more secure/etc“.
- Keep it simple: if your notes are too long, chances are fewer people will read them. Be objective when describing your releases and link to longer user guides, if it’s the case.
- Group them logically: category headers help users focus on areas they are most interested in. At Vinta, we recommend these sections: “Feature Spotlight”, “Special Attention“, “Minor Improvements”, “Bug Fixes“, and “Upcoming”. For sections that have exciting news, make sure you add a title to each item. 
- Be consistent: ideally, you should have a periodic schedule to post your notes. We recommend at the end of the team’s sprint.
- Use visual aids: include gifs, images or videos to make the experience more engaging. 

> “The most important function of release notes is to let customers know that something has changed in the product, particularly when that something may affect the way the customer uses the product. The change may be a new feature in the product, an entirely new product, a change to the way the product works, a change to the way the customer uses the product, the removal of a feature, or even the deprecation of the entire product.” - Sara Maddox, Google Technical Writer
