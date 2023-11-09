# Chapter 3: This is How We Work

## Management

### Seamless Team Management

When launching a new project, whether it's initiating an MVP or integrating as a staff augmentation team, we inquire about our clients' preferred management approaches before offering our recommendations.

The management framework for each project is determined by agreements reached with our clients at the project's outset. In our consulting work, we typically advocate for our team to take full ownership of the adopted management approach. Additionally, we propose the autonomy to designate an internal leader who translates our client's vision into a tactical plan while coordinating the team's efforts.

Depending on team size and project scope, we may assign a project manager responsible for ensuring the team progresses toward our client's vision efficiently. Having a dedicated project manager on our side eliminates the need for clients to invest effort in project management.


### Continuous Delivery & Flexibility to Changes

Throughout the years, Vinta has leaned on Agile principles to sustain its management toolbox. While we mainly followed Scrum, we started to notice there were components on the framework that weren’t ideal for us because they didn't allow for flexibility required by our different client profiles. That’s why we decided to come up with our own modernized management framework version, the one that's been adopted by all of our ongoing projects: The Vinta Management Framework.

That framework is true to our values and flexible to adapt to our client's needs. It has Kanban as a basis, and enables our teams to work with continuous delivery enabled, as we'll constantly be shipping value. This framework proposes a straightforward structure of how the work will be organized in boards operated by the team, offering transparency to our client. Within this framework, our clients can also expect some structured routine meetings to ensure we have a constant alignment with our stakeholders.

Additionally, our team also conducts a series of internal ceremonies such as strategy syncs to make sure that the team is up to date with the client's vision, daily or weekly progress review meetings where we assess our team's progress, tech review meetings, design review meetings, feature kickoff meetings, and more.
Influencing Product Strategy 


In addition to the tactical work and operational duties associated with the role of a project manager, Vinta's managers are also well-versed in the product management domain. They possess the knowledge to offer guidance on strategic matters and can have a hands-on approach when it comes to shaping product strategy and supporting our clients with roadmap decisions. 


## Design 

### Adaptive Design Operations
At Vinta, we recognize that design is not merely an aesthetic choice but a strategic tool that can be leveraged according to the maturity level of each client.

For New Ventures, design is about rapidly validating market fit and user appeal, often with limited resources. Our operations are built to adapt, providing the agility these early-stage companies need to pivot and iterate quickly. For Established Businesses, design becomes a tool for scaling and refining, ensuring that as they grow, their digital products remain cutting-edge and user-centric.

Whether it's a startup seeking to make its mark or a mature company looking to innovate, our design operations flex to meet the distinct challenges and goals at each stage of the business lifecycle.

To ensure the success of our strategic work, we:

Collaboration and Real-Time Communication: Utilizing reliable communication tools and task management systems, we foster a collaborative environment. This ensures real-time updates, feedback, and discussions, keeping our projects organized and on track, facilitating quick decision-making, and maintaining project momentum. We maintain open lines of communication with our clients, actively involving them in the design process to ensure that the final design meets their vision and expectations. This collaborative approach ensures alignment and satisfaction.

Data-Driven and Informed Design: Leveraging data to inform our design decisions, we work closely with developers to implement analytics and gather user feedback. This approach enables us to measure the success of our design solutions and make continuous improvements, ensuring that our designs are always aligned with user needs and business objectives.

Comprehensive Design Documentation: We create detailed design specifications, style guides, and pattern libraries, providing a single source of truth for product design. This ensures consistency across the team and clarity in design decisions, facilitating a smoother design-development collaboration."


### Our philosophy: User-centered and scalable design.
Central to our design philosophy is a user-centered approach. We tailor our methods to meet business needs and resources, utilizing user personas, user journeys, and usability testing to forge intuitive and engaging user experiences. Our aim is not only to meet but to exceed user expectations, crafting designs that are both functional and captivating.

Furthermore, our designs are crafted with future growth in mind, ensuring that they can evolve and adapt as the product expands. By considering future features and enhancements from the start, we lay a foundation for long-term success. An important part of scaling design successfully involves maintaining clear, organized documentation, and we achieve this through two main strategies:

Choosing the Right Design System: Whether it's a proprietary design system tailored to a unique brand identity or a third-party design system for faster implementation, we help our clients choose the best fit for their needs. Our expertise with tools like Figma enhances our ability to create, collaborate, and maintain consistency across projects, ensuring quality and efficiency.

Managing design debt: As design projects accumulate, we stay vigilant in tracking and managing design debt, ensuring that all design work is completed efficiently, and maintaining the integrity of the design operation.


## Development

### Code Quality
Code is the primary source of truth for us. We keep it easy to read and understand. At the start of each project, we reach an agreement with the client on the code quality threshold that makes sense for them. From then on, we enforce it during code reviews, testing, linters, and other tools and practices we’ll list in this section.

We understand that projects shift between the need for speed and focusing on code quality. Neglecting speed impacts competitiveness, while overlooking code quality results in missed opportunities and lost sprints on bug fixes. That's why our code is designed to be either easily maintainable for quick development or easily removable for smooth refactoring when a more robust solution is required.

This section will now focus on the practices to reach and maintain the level of code quality your project needs:
- Testing
- Code review
- Documentation
- Security

### Testing
A robust test coverage is essential to any successful digital product. The types of tests we use vary, but we commonly focus more on unit tests rather than integration ones, while ensuring a good portion of integration tests are in place. Tests not only guarantee the code is working correctly, but also guide developers on the expected behavior of a piece of code. Throughout our work, we write several tests to fulfill various roles. Usually we use TDD, changing our approach whenever a different one would fit the client’s needs better.

We strive for elevated test coverage, but we also understand that, after we meet a particular bar (each client has their bar), the product benefits more from improved and more comprehensive tests than from increased coverage.
Shipping Early and Often
At Vinta, we make the cycle from defining requirements to putting changes in front of production users as short and painless as possible. It doesn’t mean we will be intransigent or unable to plug with your team or existing processes. It does mean that we’ll strive to deploy in the smallest batch possible to avoid delays and cluttering natural to big releases. One of such practices we can apply, if aligned with your team, is pushing unfinished work behind feature flags to production rather than having long-running undeployed branches, for example.

We’ve reached this level due to our pragmatic testing culture and our infrastructure skills. We can discuss these smaller deliveries internally while keeping it all transparent to our clients. We can also involve the client in these discussions if that would be valuable for a business objective or to show an investor.

### Code review
Code reviews are potent means to improve code quality, establish best practices, and spread knowledge within the team. We have battle-tested code review guidelines. They help us to guarantee a more resilient project in the long run, as specific knowledge will never be in the hands of a single team member. They also empower every developer to deploy valuable code to production, no matter the maturity level.

#### How-to
We review every piece of code that goes to production over several aspects. Here are a some of the checks we run to make sure you don’t need to worry about it:

- Correctness - Does the solution behave strictly as intended?
- Style - Is the style of the code familiar to the team?
- Naming - Did the developer choose clear names for variables, classes, methods, and other parts of the code?
- Complexity - Is the solution more complex than it should be?
- Security - Are there any security issues?
- Conciseness - Has the developer implemented things that might be needed in the future with no explicit need now?
- Testability - Does the code have a correct and well-designed unit, integration, or end-to-end tests?
- Comments - Are the comments clear and valuable?
- Configurability - Are the configurable values stored in places such as XML settings files or databases?
- Documentation - Has the developer also updated relevant documentation?
- Performance - Does the solution have performance bottlenecks?
- Risk of Failure - Does the solution work well on edge scenarios on the infrastructure?
- Technical debt
- We know that no process is fail proof, and every team will introduce technical debt as the project becomes increasingly complex. We also understand that business objectives determine the priority of fixing them. Naturally, businesses will oscillate between periods when speed is more important and others when delays to ensure quality will be the way to go. We’ve worked on both ends of the spectrum and are comfortable adapting processes and practices depending on the client’s best interests.

### Technical Documentation
Efficient documentation is what keeps people working at a nice pace even as the project grows in complexity. Code in production is more important than documenting, for sure. But, investing time to document guarantees speedy deliveries and less time spent solving issues later on.

We have described an array of our practices and philosophy about technical documentation in this blogpost one of our partners wrote. 
How we deal with incidents in production
We monitor a multitude of aspects of our software. Even then, incidents or emergencies are bound to happen in production, requiring our immediate attention. During these situations, we understand that always keeping the client informed is paramount. They should have a transparent view of where our investigation is leading us and a time frame for resolving the issue. We also allocate specific roles and responsibilities during the crisis.

When investigating the occurrence, the first step in the investigation is to assess the impact of the incident, we first take a closer look at:
- Which services did it hit?
- Which SLOs did it affect?
- How many users has it impacted?
- Are users reporting the issue?
- Is there data loss?
- Is this a security issue?
- Is it a problem with an external service?

Then, we look for a way to diminish the severity of the impact as soon as possible. If a recently deployed feature is causing the issue, we can make a rollback, for instance. After that, we start an incident report, where the client (and whomever they decide to share it with) can see what we are trying to fix the issue in real-time. After solving the problem, we do more thorough research and write a postmortem document. This final document assesses the incident's root cause and what we need to do so it won’t happen again.

### Software Development Security

#### Processes for security
We take several precautions to ensure the security of every project we work on. We understand security measures are mandatory inclusions in every project. Here are some of our processes on that matter:
We renew domain names regularly;
We train non-technical and technical employees against phishing attacks;
All machines are password-protected and have encrypted hard drives;
All supporting services use Two-factor Authentication;
We handle all cloud services' passwords with a password manager for solid password generation and protection;
We don't share accounts between employees.
Backups of all system data happen automatically and in time windows where they won't harm application performance;
We store them in a separate infrastructure from the application, and access is limited to a small group of system admins;
We never download backups to a local machine;
We run Backup restoring tests with a frequency of at least once every two months;

#### Coding measures for security
- Real-time monitoring for detecting outdated software libraries and tools;
- Automated tests to check for common security vulnerabilities;
- Compliance with accessibility and payment gateways;
- Separate testing, staging, and production environments;
- Protected branches on all of our project’s versioning;
- Database encrypted at rest using industry-grade AES-256, block-level storage encryption;
- Sensitive fields (such as Tax ID No.) are encrypted in the database using a Symmetric-key Algorithm;
- Read-only access for any third-party partner that will access the database;
- All communication is encrypted via 2048-bit SSL, including file transfers;
- All login attempts are logged and monitored;
- Users go through email verification and account-level verification. Sophisticated passwords to enhance account security are also required;
- Password hashed with PBKDF2 algorithm, a password stretching mechanism recommended by NIST (National Institute of Standards and Technology). All passwords are hashed and salted with 10,000+ iterations for complete security;
- We use secure industry-standard third parties like Stripe with direct integration from the user frontend to the third-party backend to avoid storing credit card data.
- Frontend data is never trusted and constantly checked for permissions and submitted through validations/sanitizations on the backend;
- Logs are extensively used and stored in a centralized place;
- Logs include auditable user activity data, but they don’t include Personally Identifiable Information (PII);
- We obfuscate code sent to the browser and strip out all comments;
- Error messages sent to the frontend don’t contain sensitive information about the application (paths, traces, debug messages, software version, or any other);
- We never commit keys/secrets in the code;
- We never do cryptography ourselves. We always rely on existing mechanisms, libraries, and tools;
- All system resources check for user authentication and permissions;
- Application administrative areas are hidden and restricted to power users;
- We automatically monitor code dependencies for updates and security issues;
- Alerts on security issues are issued as soon as they’re identified (not only at commit/push time);
- Production applications use TLS/HTTPS;
- We use a Web Application Firewall (WAF) to protect from common attacks and DDoS;
- We watch for unusual patterns in your metrics, such as CPU, memory, disk usage, and bandwidth usage;

We strictly follow the security guidelines of the tools and open-source frameworks we use, such as PostgreSQL documentation, Django documentation, Python security guidelines, and Stripe security documentation. In addition, we perform upgrades as necessary to ensure the highest level of security.

Here are the links to the security documentation for these tools and frameworks:
- PostgreSQL documentation;
- Django documentation;
- Python security guidelines;
- Stripe security documentation.

## Measuring Success
In order to be cost-effective, software companies must measure whether their investments in developing new features or products actually yield the expected return. Vinta employs an end-to-end development process that includes measuring the impact of what we ship through the analysis of product metrics.
Product metrics incorporate a time component and comparison model, allowing us to determine if product decisions actually had a quantifiable impact. Not analyzing metrics means operating blindly, leading to missing opportunities to enhance products and user experiences, and may also result in money loss.
Furthermore, product metrics empower software companies to demonstrate their value to stakeholders, whether they are investors, customers, or internal teams. Tangible data showcases the impact and performance of the product, fostering trust and confidence, which can attract more investment and customer loyalty. 
As opinionated consultants, the Vinta team collaborates with stakeholders to define the appropriate metrics for measuring the success of their deliveries before initiating the development of any product or specific features. Our goal is to assist clients in making more informed decisions by transforming metric results into actionable insights that can shape the future of their products.

## Embedded Customer Service
In a competitive market, companies need to be aware of what makes them indispensable to their customers. For many of them, especially startups that are looking to increase their presence in the market, support is a huge differentiating factor.

According to Zendesk’s 2020 CX Trends Report, 74% of customers feel loyal to a particular brand or company. Younger generations and Americans are the most loyal to their favorite brands. Right after price, customer service comes as one of the main players in the top attributes when customers are queried about brand loyalty.

Our support package is offered as a part of our regular consultancy and staff augmentation services. All of our engineers are able to work in support and our team leaders are capable of implementing a support structure and best practices from scratch if our clients do not yet have one, including:

- Setting up and managing major ticketing management systems;
- Implementing a system for categorizing customer conversations (triage) to extract UX insights and identify common points of confusion;
- Maintaining status pages to keep end-users informed;
- Implementing structured incident reporting processes;
- Conducting transparent post-mortems with incident timelines, impact analysis, root causes, and prevention steps;
- Utilizing battle-tested prioritization frameworks based on ticket severity and SLA;
- Developing documentation writing methods and templates for an effective help center.

We follow a multi-channel approach, leverage custom work to ensure our clients’ companies provide tailored solutions to their customers as a differentiator and most importantly, ensure that each and every service we provide is flexible enough to fit our clients’ needs.



