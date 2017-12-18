___"Any fool can write code that a computer can understand. Good programmers write code that humans can understand."___ To follow Martin Fowler's directive we try to code as smart as possible, check out how we do it:

## Boilerplate
The use of our [boilerplate](https://github.com/vintasoftware/boilerplate) is standard when  starting new projects.

## Environments

### Staging
- Should be as similar as possible to production.
- It's OK to delete the database (but do tell the client before doing so).
- Keys should be the same as in production (.env). If the third-party service supports test-API keys (like Stripe), use them here.
- Like in production, developers need to receive errors via Sentry (configure it to send e-mails to the one responsible).

## Server access information
- Create a `DEPLOYMENT.md` file.
- That file should explain the basics how-to of the server (how to access app code, restart/stop the server and services).

## Principles
- KISS: Keep it simple, Sweetie (not stupid!)
- DRY: Don't Repeat Yourself
- YAGNI: You aren't gonna need it
- Small functions/methods
- Avoid side effects
- Design matters
- UX matters even more
- All code should be reviewed
- All features must be manually tested before going to production
- If there's no way to keep it simple, make sure there are comments
- Commit as often as possible (try not to have an "and" in commit messages)
- And again, Keep it simple


## Style Guides

### Python
- [PEP8](https://www.python.org/dev/peps/pep-0008/)

### JavaScript
- [Airbnb JS Style Guide](https://github.com/airbnb/javascript)

### HTML & Sass
- [Frontend Guide](guidelines/guideline_frontend.md)

## Daily reporting
We use the IN/OUT methodology for daily follow-up with project developers, as well as the Harvest app to track how much time has been  spent on the project. A quick report by the end of the day to the project manager also helps to keep the project on track.

Depending on the project, the client might have a project manager communicating in his/her behalf. Whenever that is the case, the  daily report should be sent to either the project manager or to the client, at their discretion. Among the Things that should be addressed are: features developed, bugs fixed, PRs submitted, PRs merged, PRs reviewed, deployments, problems encountered. Example:

- Merged PR on views authentication [link to Trello card].
- Fixed header responsiveness bug on home page.
- Deployed to staging.

## Developer’s attributions
- To Be able to contact the client directly to settle doubts about tasks (make sure everything is written where you can later reference).
- Ask the project manager in case something is not clear.
- Make sure you inform the manager when you are close to becoming idle.

## Config project files
- Create a Last Pass Secure note with your `.env` file.
- Add a link to your Last Pass note to Trello’s documents column.

## Production and Staging services
- ALWAYS have [Sentry](https://sentry.io/) configured and with correct e-mails to project developers.
- Setup alerts and health checks for critical parts of the project:
  - Setup the following [Papertrail](https://papertrailapp.com) alerts:
    * Web errors: `"app/web" Internal Server Error`
    * Worker errors: `"app/worker" ERROR/`
    * Platform errors: `"error code=H" OR "Error R" OR "Error L"`
  - Setup a [Librato](https://www.librato.com/) alert for slow response time.
  - Setup a [Uptime Robot](https://uptimerobot.com/) alert for uptime.

## Feature implementation
Once allocated to a feature, the developer should follow the [Feature development workflow](checklists/feature_development_workflow.md), which includes using [git-flow](http://nvie.com/posts/a-successful-git-branching-model/) and satisfying the [PR workflow](checklists/pull_request_workflow.md).


## Code and feature review
All code is reviewed before being merged to master. The reviewer not only checks code quality, but also if the feature was implemented according to what the client expects. It's very important for the allocated reviewer to strictly follow the [PR review workflow](checklists/pull_request_review_workflow.md).