# Code Quality

- Code is the main source of truth, so it's important to keep it easy to read and understand. If you can’t avoid your code being complex, use comments and docs. 
- Consider readability while doing code reviews, if it could be easier to understand it should be improved.
- Be considerative when designing abstractions and generalizations. Wrong abstractions can be very costly to maintain. You can read more about this topic in [this article from Sandi Metz](https://sandimetz.com/blog/2016/1/20/the-wrong-abstraction).
- Setup project linters and formatters in your IDE or text editor. 
- Always fix linting errors; In case a particular rule does not applies to a file or a specific code, relax the rule it in the lowest level possible and comment the motivation to do so;

# Testing

- All code should be tested [ideally using TDD];
- You can have more unit tests than integration ones but always make sure you have integration tests in place. They're more stable and tend to stay valid on refactoring (see [Test Pyramid](https://martinfowler.com/bliki/TestPyramid.html));
- When refactoring, avoid changing existing integration tests. Sometimes it will be necessary to do so though.
- If you’re introducing new services or pieces of code that contains business logic, you should unit test them. Unit tests help us finding where the problems are when we introduce new bugs.
- On the frontend, prioritize integration tests. Most tests should be related to what the users see, so you should refer to pieces of the interface to check or interact with identifiers that are visible to users like labels and a11y attributes. This helps maintaining the frontend tests more stable over time.
- Every time you’re fixing a bug, write a regression test (write the test first to capture the bug and only then fix it). This will help you ensuring you’ve fixed the correct underlying issue. It also helps to prevent the bug from being introduced again in the future.
- Coverage should be above 80%. If your project has more coverage then be careful not to lower it with new code. If your project has less coverage than the threshold, try to always increase the coverage with the new code that you’re shipping.

## Test Driven Development (TDD)
The TDD methodology defines a 3 step cycle to aid software development, they are often described as  RED →  GREEN →  REFACTOR cycle. This process is simple enough and easy to remember but it carries a bunch of insights and benefits to the software development process. 

### Breaking down the problem into smaller steps
TDD reduces the anxiety of working with big features. Instead of trying to write a full solution to the problem, you can calm down and focus on smaller bits of it. Remember: you just need to write enough code to make the test pass. Focus on that single thing, then move on to another small thing and before you notice it you will have a complete solution.

### Building on solid ground
As you repeat the cycle you will gradually build a robust test suit that backs up all the work you’ve done so far. There’s far less risk of accidentally breaking things. By ensuring the test first fails and then passes you are also ensuring that the code you wrote does exactly what it was intended for. It will also free you up to be more adventurous with your refactoring and enable you to try different architecture approaches. 

### Know were it broke
Because tests are focused on small parts of your code you will know straight away where to fix things when something breaks.

### TDD is not about testing
Despite the benefit of producing a robust test suit, the TDD process is a methodology to assist writing code, not tests. Test are nice side-effects of it. 

### TDD requires discipline
It’s very likely that you will have a hard time in the first few times you try to do TDD. It will possibly seem unnatural or boring. Until you get used to it you will need a bit of faith, your mind will eventually adapt to it and you will start noticing the benefits. Do not give up, keep forcing yourself, it will pay off! 

### The feedback loop
One of the things that will help in this process is the feedback loop, the sense of making progress. One caveat is that it will only work if you keep the cycles short. It’s rewarding to strike through a bunch of quick wins and it will help you feeling productive and happy with your work, but you will loose it all if you start writing tests that require too much code to pass or if tests take long to run.

# Pair Programming

Pair programming essentially means that two people write code together on one screen. It is a very collaborative way of working and involves a lot of communication. While a pair of developers work on a task together, they do not only write code, they also plan and discuss their work. They clarify ideas on the way, discuss approaches, and come to better solutions.

## Pair programming styles

### Driver-Navigator
It consists of one person ‘driving’, taking the keyboard and coding or doing the work, while the other one is ‘navigating.’ The Navigator’s job is to pay attention to the work being done by the driver while keeping the big picture in mind. They should guide the driver in the right direction. The driver must explain verbally every decision they make; otherwise, the navigator might lose interest and may stop paying attention. It’s healthy to switch roles every X minutes.

### Ping-Pong
This technique embraces Test-Driven Development (TDD) and is perfect for a clearly defined task implemented in a test-driven way. A good strategy for this approach is to have one person writing the tests while the other tries to pass them. As in the previous approach, you should be switching roles often.

### Strong-Style
This technique is handy for knowledge transfer, described in much more detail by [Llewellyn Falco](https://llewellynfalco.blogspot.com/2014/06/llewellyns-strong-style-pairing.html). The rule: "For an idea to go from your head into the computer, it MUST go through someone else's hands.” In this style, the navigator is usually the person much more experienced with the setup or task at hand, while the driver is a novice (with the language, the tool, the codebase, ...). The experienced person mostly stays in the navigator role and guides the novice.

## Challenges
- Pairing requires practice. While pair programming has many benefits, it also requires practice and might not work smoothly from the start.
- Pairing can be exhausting. When working alone, you can take breaks whenever you want, and your mind can drift off or shut down for a bit when it needs to. Pairing forces you to keep focus for potentially longer stretches of time and find common ground with the other person's rhythm and ways of thinking. The increased focus is one of the benefits of pairing and makes it quite intense and exhausting.
- Intense collaboration can be hard. 
  - Working so closely with another person for long stretches of time is intense. It would be best if you communicated constantly, and it requires empathy and interpersonal skills. 
  - You might have differences in techniques, knowledge, skills, extraversion, personalities, or approaches to problem-solving. Some combinations of those might not match well and give you a rocky start. In that case, you need to invest some time to improve collaboration and make it a mutual learning experience instead of a struggle.
- Pairing with lots of unknowns.
  - When you work on a large topic where both of you don't know how to solve a problem, the usual pairing styles often don't work. Let's say you need to use technology for the first time or try out a new approach or pattern. Researching and experimenting together works in some constellations. Still, it can also be frustrating because we all have different approaches to figuring out how things work, and we read and learn at different paces.
  - When there are many unknowns, e.g., you’re working with new technology, think about doing a spike to explore the topic and learn about the technology before you actually start working.
- No time for yourself.
  - Being in a constant conversation with each other can be pretty energy draining. Most people also need some time on their own throughout the day. That is especially true for introverts.
  - Keep the pair programming to a maximum of 4 hours per day.
  - When a pair feels that they don't have the collective knowledge to approach a problem, split up to read up and share back, then continue implementation.
- Pairing requires vulnerability.
  - Vulnerability is often connected with weakness, and in most modern cultures, the display of strength is the norm. But as the researcher Brené Brown has laid out in several talks and books, vulnerability is actually a crucial ingredient for innovation and change.

# Code Review

Code Review is an integrated software development process that helps identify bugs and defects before the testing phase. This is often overlooked as an ongoing practice during the development phase, but countless studies show it's an effective quality assurance strategy.

## How-to
- You must check if the PR is under 400 lines of code;
- You must look at every line of code that you have been assigned to review;
- Read thoroughly feature description to check if everything is implemented;
- You must comment on any issue (see Checklist below);
- Each project must have a PR template and use the GitHub feature of PR templates to add the section Checklist to it;
- Run code and use it as the end user would. Double check requested feature’s description;
- Changes should have a narrow, well-defined, self-contained scope that they cover exhaustively;
- If you are not in the middle of a focused task, you should do a code review shortly after it comes in;

## Cultivate Healthy Reviews

Code reviews are powerful means to improve code quality, establish best practices, and spread knowledge. However, they can come to nothing or harm interpersonal relations when they are done wrong. Hence, it’s important to pay attention to the human aspects of code reviews understanding they require a certain mindset and phrasing techniques to be successful.

## Tips on receiving reviews
- Making mistakes is accepted, and admitting them is desired;
- You != Your code;
- Be humble. You are not perfect, and you can also improve.

## Tips on commenting
- Be kind and thankful;
- Mind the [IKEA effect](https://phauer.com/2018/code-review-guidelines/#mind-the-ikea-effect), people value things that require assembly more than pre-assembled things. This means you might place a too high value on your own code, for example, preventing its replacement by an external library;
- Mind the [OIR-Rule](https://phauer.com/2018/code-review-guidelines/#mind-the-oir-rule-of-giving-feedback) (Observation, Impact, Request) of giving feedback. Describe your Observation (this method is too large), explain the Impact (it doesn’t follow the pattern of small methods the project has), and make a Request (could you please break it up on the part that saves the file?)
- Explain your reasoning;
- Balance giving explicit directions with just pointing out problems and letting the developer decide;
- Encourage developers to simplify code or add code comments instead of just explaining the complexity to you.
- Use I-Messages: "I suggest...", "I think...", "I believe...", "I would...", "It's hard for me to...", "For me, it seems like...", "The way I see it...";

# Architectural Decision Records (ADRs)

> “An architecture decision record is a short text file in a format similar to an Alexandrian pattern. [...] Each record describes a set of forces and a single decision in response to those forces.” - [Michael Nygard, November 2011](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions.html)

An ADR is a file that describes and documents an architectural decision within a project. They follow a simple and well defined format agreed by the team and should be stored in a place that can be easily accessed by all stakeholders. It’s very important that they follow a lightweight process so they can be easily integrated into the day to day of developers.

## Immutability
Once an ADR is created it should never be deleted. The information in an ADR that was rejected or superseded by a more recent one still important and should be always available for further reference. We should be able to learn from mistakes and be able to review why something was rejected or deprecated.

## Size
As a reference, you should try to keep ADRs no longer than 2 pages in Google Docs.

## What should generate an ADR?
The key here is to not over nor under do ADRs. Too little and you are probably missing some important decisions, too much you are probably documenting things that are not worthy of an ADR. Here are some examples of things that should normally trigger the writing of an ADR, this list should be used as a guideline but teams are free to fine tune it to their context:
- Decisions made during team meeting / pairing;
- Any strategic decision;
- New feature architecture;
- New code formatting style;
- New programming pattern;
- New library / tool / integration (what were the options? why was this chosen over the others?);

## What should NOT generate an ADR?
- Changes that are too small / too local or that are not architectural concerns;
- Things that do not need to be synced among all team members;
- Code details;

## Good Practices
- Link ADRs to relevant user stories. They can give more context and also be used for validation.
- ADRs are a process for everyone in the team, not just the Tech Lead.
- Submit ADRs for team review and feedback.
- Bring ADRs to team meetings for discussion and for syncing the team about changes.
- Share ADRs with customers for validation (after it was reviewed by the team). They can help you confirming the decision is aligned with business goals and identifying issues early on. Make sure to level up what ADRs are worth sharing accordingly to the customer technical level.

# Technical Documentation Writing Guidelines

- Lots of: parameter tables, steps-by-steps, internal links to sections and external links, script examples, configuration examples, screenshots, warnings, caveats, things to watch for, etc;
- Use Markdown;
- Use [tables](https://docs.github.com/en/free-pro-team@latest/github/writing-on-github/organizing-information-with-tables);
- Use [ordered lists](https://guides.github.com/features/mastering-markdown/);
- Use [section anchor links](https://gist.github.com/rachelhyman/b1f109155c9dafffe618);
- Set the language of fenced code to [enable syntax highlighting](https://docs.github.com/en/free-pro-team@latest/github/writing-on-github/creating-and-highlighting-code-blocks#syntax-highlighting );
- Add [images](https://stackoverflow.com/questions/14494747/how-to-add-images-to-readme-md-on-github);
- Put warnings, use [emojis](https://github.com/scotch-io/All-Github-Emoji-Icons) :warning:;
- Define [principles](https://www.writethedocs.org/guide/writing/docs-principles/) such as ARID: Accept (some) Repetition In Documentation;

# Software Development Security

## Backups
Application backups are both a critical component that need proper securing and an important way to recover data in the case of an exploit.
- Backups of all system data must happen automatically and in time windows where they won't harm application performance;
- They must be stored in an separated infrastructure from the the application and access should be limited to a small group of system admins;
- Backups must never be downloaded to a local machine;
- Run backup restoring tests with a frequency of at least once every two months;

## Web Application Development
Security should be considered in every step of the software development process. The following list covers the basics and most important practices but this is a whole field of study that you should be aware of and get educated on as you grow in your career.
- Data from the frontend must never be trusted and should always be checked for permissions and submitted through validations / sanitizations on the backend;
- Logs should be extensively used and stored in a centralized place;
- Logs should include auditable user activity data but they should not include Personally Identifiable Information (PII);
- Code sent to the browser must be obfuscated and all comments should stripped out;
- Error messages sent to the frontend must not contain sensitive information about the application (paths, traces, debug messages, software version…);
- Never commit key/secrets in the code;
- Never do cryptography yourself. Always rely on existing mechanisms, libraries, and tools;
- All system resources should check for user authentication and permissions;
- Application administrative areas must be hidden and restricted to power users;
- Code dependencies should be automatically monitored for updates and security issues;
- Server operational system and packages should be monitored for updates and security issues;
- Alerts on security issues must be issued as soon as they’re identified (not only at commit/push time);
- Production applications must use TLS/HTTPS;
- Use a Web Application Firewall (WAF) to protect from common attacks and DDoS;
- Watch for unusual patterns in your metrics such as CPU, memory, disk usage, and bandwidth usage;