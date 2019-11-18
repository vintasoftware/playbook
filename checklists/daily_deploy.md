# Daily Deploy Checklist

This checklist is based on the process of daily deploy used in one of the projects at Vinta. We're aware that this may not work for every project, but this checklist can work as a baseline for a different use case.

## Rules
- The release branch must be created the day before the release containing all the needed features;
- If there isn't any changes between master and production, the deploy will be skipped;
- After the deploy, all the deployed tasks must be tested in production;

## Process Setup
- Create a Release tag on Github to tag the release PRs;
- Create a PR template for Releases -- They should have a different one from other PRs;
- Have tags to categorize PRs: Feature, Fix, Tech Debt, etc;
- Have a #release channel on Slack, this channel will be used to inform the clients about the releases;

## Step by Step

### Pre-deploy
1. Make sure the release branch is created, if not create it from master. Use `release-yyyy-mm-dd.x` as branch name, where X is the number of the deploy on the same day -- X starts at zero;
2. Create a PR from the release branch to production. Use the Release PR template. This PR is usually called `Release YYYY-MM-DD`. Remember to tag it with the `Release` tag.;
3. List all the merged PRs on the Release PR description. Remember to also add the corresponding tags in the list items, and the PR number; Example: `[Feature] Adds a new functionality - #1234`.;

### Deploy
1. Check for status of relevant services -- CircleCI, Heroku, etc;
2. Merge the PR and watch CI to make sure the build and deploy workflow runs smoothly;
3. Make sure all the tasks ran successfully, like migrations;

### Post-deploy
1. After the deploy is done, test all the deployed tasks on production;
2. Create the Github Release, and include the Hotfix PRs as well as the Merged PRs, and link the Release PR. The release branch must be the production;
3. Message the #release channel on Slack with the list of all the merged PRs, with a link to the corresponding Github Release. This list should be the one on the Github Release but the PR IDs shouldn't be included on the Slack channel;
4. Make sure tasks that need documentation -- the ones that change behavior, like new features -- have the link to the documentation attached to the respective Asana card. This is an effort to make sure documentation is up to date with the application; 
5. Move the cards from the Sprint board @ Asana to Done. You may move to other columns depending on your needs, like `Success`, where some other person / team should know about this card being live.

