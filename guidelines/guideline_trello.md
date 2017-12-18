## Lists (columns)
- __Documents:__ Holds the most recent versions of every document related to the project development. Wireframes, annotated mockups, images, texts, all go here so that both we and our client know where to check anything.

- __Backlog:__ Holds TODO features and tasks.

- __Bugs:__ Holds TODO bugs.

- __Sprint:__ Holds features, tasks and bugs being worked at the current sprint.

- __WORK IN PROGRESS (optional):__ Holds up to date tasks being worked on.

- __Review:__ Holds features and bugs waiting for quality assurance (manual testing) and code review.

- __Done:__ Holds features and bugs done and deployed to production.

## Cards
- Cards are the single source of truth. The most up-to-date info should be on Trello cards, **not** in documents, Slack discussions, e-mails, etc.

- Feature cards shouldn't be too small nor too large, they should be at the size of a complete end user story, i.e., something new the user will be able to do with the product. That way it's guaranteed the feature will be complete enough to add value to the product once deployed. If the feature is too complicated to be implemented during the sprint, maybe a simpler version should be implemented first. Exceptions might happen, in which case a partial implementation can be deployed to staging or production with feature toggles. When creating a feature card, follow [this checklist](checklists.md#feature-card-creation).

- Task cards should be as small as possible and should detail a single task or a list of tasks that go together.

- Bug cards should be as small as possible and should detail only a single bug. This helps to make it possible to work on them independently (in any order), although this is not always feasible. When creating a bug card, follow [this checklist](checklists.md#bug-card-creation).

- Cards (except documents) should be created in the format of user stories:
  - __Examples:__
    - Feature: As a free user, I can become a premium user by paying a subscription plan with a credit card.
    - Bug: As a user, I expect an input to be focused after clicking on its label.
    - Task: As a developer, I see JavaScript errors on Sentry.

- If any card is related to others, link them

- The assigned person to a card always should be the one acting on it.Cards should always be back and forth.

- Features and tasks on the Backlog don't need to be as detailed as Sprint cards. Sprint cards details should be decided on meetings, then specified on cards. Remember: most up-to-date info should be on cards.

- Priorities should be always defined, together by both client and developer(s).

- The client should validate the card before moving it to Done and pushing to production.
