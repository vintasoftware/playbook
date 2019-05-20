# Asana Guideline

## Projects
- __Product Roadmap:__ Comprised of Epics, a high-level user story that will fulfill a product goal (usually broken down into smaller user stories).

- __Product Trackings:__ Holds experiments, metrics, A/B tests, heatmaps, etc.

- __Development Backlog:__ Holds TODO features and tasks (usually Subtasks that are part of an Epic's user story).

- __Design Backlog:__ Holds TODO tasks that are part of an Epic.

- __Sprint:__ Holds features, tasks and bugs being worked at the current sprint (usually a Kanban board representing the development workflow).

- __Bugs:__ Holds bugs that weren't classified as urgent.

- __Tech Debt:__ Holds tech debt tasks.

- __Ideas Drawer:__ Ideas that were put on hold and are not on our track.


## Sprint Board

- __To Do:__ Holds features, tasks and bugs that are part of the current sprint.

- __Doing:__ Holds up to date tasks being worked on.

- __Code Review:__ Holds features and bugs waiting for code review.

- __QA:__ Holds features and bugs waiting for quality assurance (manual testing) on the Staging envinronment.

- __Ready to Deploy:__ Holds features and bugs that were approved during quality assurance.

- __Done:__ Holds features and bugs done and deployed to production.

## Cards
- Cards are the single source of truth. The most up-to-date info should be on Asana, **not** in documents, Slack discussions, e-mails, etc.

- Feature cards shouldn't be too small nor too large, they should be at the size of a complete end user story, i.e., something new the user will be able to do with the product. That way it's guaranteed the feature will be complete enough to add value to the product once deployed. If the feature is too complicated to be implemented during the sprint, maybe a simpler version should be implemented first, or it should be broken into smaller deliverables. Exceptions might happen, in which case a partial implementation can be deployed to staging or production with feature toggles. When creating a feature card, follow [this checklist](checklists.md#feature-card-creation).

- Task cards should be as small as possible and should detail a single task or a list of tasks that go together. A feature card may be broken into smaller task cards to delimit a deliverable.

- Bug cards should be as small as possible and should detail only a single bug. This helps to make it possible to work on them independently (in any order), although this is not always feasible. When creating a bug card, follow [this checklist](checklists.md#bug-card-creation).

- Cards should describe a user stories:
  - __Examples:__
    - Feature: As a free user, I can become a premium user by paying a subscription plan with a credit card.
    - Bug: As a user, I expect an input to be focused after clicking on its label.
    - Task: As a developer, I see JavaScript errors on Sentry.

- If any card is related to others, they should be grouped as subtasks of the Epic or linked.

- Features and tasks on the Backlog don't need to be as detailed as Sprint cards. Sprint cards details should be decided on meetings, then specified on cards. Remember: most up-to-date info should be on cards.

- Priorities should be always defined, together by both client and developer(s).

- The client should validate the card before moving it to Done and pushing to production.


## Productivity Tips
- A single card can be on different projects! Be sure to not duplicate tasks.
- Asana has many cool keyboard shortcuts, take a look before getting started.
- You can copy/paste a list to a project and a card will be created for each list item.
