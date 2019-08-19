___"Any fool can write code that a computer can understand. Good programmers write code that humans can understand."___ To follow Martin Fowler's directive we try to code as smart as possible, check out how we do it:

## Boilerplate
The use of our [boilerplate](https://github.com/vintasoftware/boilerplate) is standard when starting new projects.

## Environments

### Staging
- Should be as similar as possible to production.
- It's OK to delete the database (but do tell the client before doing so).
- Keys should be the same as in production (keep them in an untracked .env or .ini file so they are not pushed to the repository). If the third-party service supports test-API keys (like Stripe), use them here.
- Like in production, developers need to receive errors via Sentry (configure it to send e-mails to the one(s) responsible).

## Server access information
- Create a `DEPLOYMENT.md` file.
- That file should explain the basics how-to of the server (how to access app code, restart/stop the server and services).

## Principles
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

## Style Guides

### Python
- [PEP8](https://www.python.org/dev/peps/pep-0008/).

### JavaScript
- [Airbnb JS Style Guide](https://github.com/airbnb/javascript).

### HTML & Sass
- [Frontend Guide](guidelines/guideline_frontend.md).

## Daily reporting
In some projects we use the IN/OUT methodology for daily follow-up with project developers, as well as the Harvest app to track how much time has been spent on the project. A quick report by the end of the day to the project manager also helps to keep the project on track.

Depending on the project, the client might have a project manager communicating in his/her behalf. Whenever that's the case, the  daily report should be sent to either the project manager or to the client, at their discretion. Among the things that should be addressed are: features developed, bugs fixed, PRs submitted, PRs merged, PRs reviewed, deployments, problems encountered. Example:

- Merged PR on views authentication [link to Asana card].
- Fixed header responsiveness bug on home page.
- Deployed to staging.

## Developer’s attributions
- To be able to contact the client directly to settle doubts about tasks (make sure everything is written where you can later reference - add details and specs to the feature's card, DO NOT write it on paper only).
- Ask the project manager in case something is not clear.
- Make sure you inform the manager when you are close to becoming idle.

## Config project files
- Create a Last Pass Secure note with your `.env` file.

## Production and Staging services
- Check the <a href="https://devchecklists.com/production-launch-checklist/" target="_blank">Launch Checklist</a>

## Feature implementation
Once allocated to a feature, the developer should follow the [Feature development workflow](checklists/feature_development_workflow.md), which includes using [git-flow](http://nvie.com/posts/a-successful-git-branching-model/) and satisfying the [PR workflow](checklists/pull_request_workflow.md).

## Code and feature review
All code is reviewed before being merged to master. The reviewer not only checks code quality, but also if the feature was implemented according to what the client expects. It's very important for the allocated reviewer to strictly follow the [PR review workflow](checklists/pull_request_review_workflow.md).

## General tips
- Clear old sessions periodically
- Evaluate ALL 500 errors and make regression tests if necessary
- Provide fixtures to setup base data to the project