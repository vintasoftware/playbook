## Pull request workflow

- [ ] Read thoroughly feature description to check if everything is implemented.
- [ ] Run code and use it as the end user would. Double check requested feature’s description.

## Creating the pull request

- [ ] Create Pull Request (but don't assign it yet).
- [ ] Describe how to test PR: urls and other needs.
- [ ] Refer to issue(s)/Trello card(s) the PR solves.
- [ ] Refer back to PR on Trello card(s).
- [ ] Fix any conflicts that might appear. Merge target branch into PR branch.
- [ ] Add screenshot of new behavior if applicable.
- [ ] Add description including context and chosen implementation strategy.
- [ ] If you feel the need to add PR comments to code lines which reviewer might understand incorrectly, don't do it there. Do it on the code itself as comments. Consider refactoring and changing variable/function/method names to make it clearer.

## Self review the PR

Look for the following problems:
- [ ] Check if code is following code style guidelines (*TODO* add links here).
- [ ] Naming.
- [ ] KISS: Keep it simple, Sweetie (not stupid!).
- [ ] DRY: Don't Repeat Yourself.
- [ ] YAGNI: You aren't gonna need it (PS: Fowler said "Yagni only applies to capabilities built into the software to support a presumptive feature, it does not apply to effort to make the software easier to modify").
- [ ] Architecture errors, basically good separation of concerns and no leaky abstractions.
- [ ] Unclear behavior.
- [ ] Performance (but fine if good enough).
- [ ] Complicated constructions that need refactoring or comments.
- [ ] Forgotten TODOs and noop lines.
- [ ] Grammar errors.
- [ ] Continuous Integration errors, including tests and coverage (configure CI to send you an e-mail when tests are done).
- [ ] If the feature needs regression tests, write them.
- [ ] Other possible improvements (add to this Guidebook if it's a general concept).
- [ ] Once all problems are addressed, allocate the reviewer.

## Responding to feedbacks

- [ ] If any problem hasn’t been addressed and PR needs to be accepted ASAP, create new issue for remaining problems.
- [ ] Respond all reviewer comments ASAP:
    * Be grateful for reviewer's suggestions. ("Good call. I'll make that change.").
    * Don't take it personally. The review is of the code, not yourself.
    * Seek to understand the reviewer's perspective.
- [ ] Once you receive feedbacks and address all issues, merge and close the PR.
