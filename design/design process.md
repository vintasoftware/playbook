# Working on sprints

When a product is up and running, our design team is constantly proposing improvements or building new features for it. This section describes the design cycle for a feature within **regular 2-week sprints**, from the moment it's assigned to our team until it's deployed to production. 

All our product design activities are contextualized in terms of time in
[this flowchart](https://whimsical.com/QAEcUzTMDpJe1drziUZTkJ#2Ux7TurymLzUL8XmrUYH). It's important to note that the described timeframes for each activity are rough estimates, as a feature might end up being more complex than we've anticipated.

## 1. Feature briefing
The first step for every product design assignment, large or small, is to **understand its purpose**. This usually happens during our weekly design sync with the client, but can also be done asynchronously through our regular channels (Asana or Slack). We need to answer the following questions, reading the task description, talking to our client and the dev team: 

- Why does the product need this feature?
- What user need, desire or annoyance is behind it?
- What business need is behind it?
- What will be the impact on user experience?
- How much effort is likely to be involved?

At this point, we know what's the purpose and have a rough sense of its complexity. Designer and team manager, together, define if it should be treated as a minor new feature, an improvement, a major new feature or a hotfix. The workflow is slightly different for each of these categories, as well as the design effort.

This is also the moment when the team sets **success metrics**. For example, if the business need behind a feature is to increase engagement (keep users interacting with the product for a longer period), we need to pay attention at session time, drop-off rates and clicks on certain actions.


**Time estimate:** 1 day. Requires sync with client and team manager. This is the kickstart for a new feature, and should happen in the beginning of the sprint.

## 2. Discovery & research
Every feature or improvement (except for hotfixes, which have a particular workflow) needs some level of research, before we start working on the solution. The most common types of research we do are: 

### User base analysis
When a feature is going to have a big impact on our users, we need to know how many they are, what was their behavior in the recent past, how often they were performing related actions, what are their workarounds for solving a problem our product is not yet solving for them. There are two different approaches to this: 

**Data analysis**: this works really well when the product is B2C, and we have enough quantitative data to indicate trends and general behaviors. The main tools we use for this are Google Analytics, Hotjar, Mixpanel and Segment, that need to be setup beforehand with the main flows, funnels and events, to speed up the data retrieval process during this step.

**Interview users and stakeholders**: for products that are highly segmented and have a small but demanding user base, it's more efficient to run short (15-30 min) interviews with key users. This approach can give us deeper insights, especially when we're working on core functionalities. During the interview, we ask open-ended questions, avoid bias and keep the meetings short and straightforward. 

Understanding user behavior, either through data or interviews, can indicate if a feature is actually worth developing, and what should be its priority level. Sometimes, a hypothesis that the client (and even our team) has ends up being very far from reality, once we listen to actual people.

### Benchmark
Benchmark analysis consists in looking at other products and services that offer similar solutions to the one we're building, be it a core functionality (e.g. selling a subscription service) or a UI component that exists in various digital products (e.g. filters, menus, selectors, navigation). Running a benchmark is not about copying competition. It's more about understanding the products our user base interacts with in their daily lives, and building a solution that is consistent with that. 

A benchmark can be as simple or as complex as the feature needs. The analysis can range from a few insights on the use of drop-down menus to a document with a detailed taxonomy of content elements across a dozen websites. The biggest value delivered by a benchmark research is in gathering the best ideas from each product that's being analyzed, identifying patterns and best practices and proposing directions for the solution we're about to create. 


**Time estimate:** about 1 week. Different research approaches can run simultaneously, if more than one designer is allocated on the project. Results should be documented and presented to the client during our weekly sync. Based on the results from the discovery phase, our client should make the decision to move forward with the feature or de-prioritize it.

## 3. User flow & Lo-fi prototype
After the design team is armed with research and understands clearly what the new feature is, we start designing the user flow (in case it's a bigger feature or improvement) or new component's behavior. This process can be kick-started on our own, but ideally, the flow should be built together with the developer who will be working on the feature. 

### Building the flow
These session starts with us representing the behavior of the new feature in a low-fidelity prototype. Pen and paper are the best tools to start. While building a flow, we think in terms of intention (what the user wants to achieve), context (where the user is within the product), action (what they do here), outcome (what happens when they do this action) and pathway (where they go from here). All use cases must be specified, and this is the moment to explore all the possible "what ifs". What other paths can users follow inside this flow, besides the desired one? What constitutes a mistake? Where are the dead-ends? How do we inform users what they need to do to ensure an optimal journey from intention to outcome?

Then, we assess the feature's complexity and impact on the system (especially on the development side). When building features on top of an existing architecture, we need to understand how it connects to other parts of the product and the constraints that come from that. In many situations, it's hard to get an accurate idea of the feature's complexity until we design the flow. Things that look simple from a front-end perspective sometimes have a much larger impact on the system. The client must be informed if there's any change in estimates for development, as a longer  ETA might affect the product's strategy.

### Documenting the flow
After the session with the team (which is likely messy and full of poorly drawn sketches), the designer should represent the new feature or improvement in a way that's easy to understand. At Vinta, we use Whimsical as a tool to quickly produce user flows, behaviors and lo-fi prototypes. It will serve as documentation for the feature and basis for user stories (to be written by the team manager). 

All of the deliverables from the first sprint must be bundled together in a presentation for the client. Documenting our design process gives us a good base for arguments and decision-making down the road. Assembling it in a straightforward presentation (rather than a text-heavy document) makes it more digestible to clients, who have very little time available to discuss feature details, and also more likely to be revisited by all the stakeholders in the future.

### Validating the flow
Everything that was defined between designer and team manager (feature architecture, behavior, use cases and lo-fi prototype) should be discussed with the client on the next design sync. 

Depending on the team's schedule and general product roadmap, development for the new feature can already start on back-end at this point, since the main architecture and behaviors have been specified and validated. 


**Time estimate:** varies according to the feature's complexity. It may range from 1 day to a week, between defining the flow, documenting and validating it with the client. It will be the main documentation for a feature, so it needs to be very thoroughly reviewed and agreed upon by all stakeholders. 

## 4. UI design 
Once the flow has been validated by both the development team (technical viability) and the client (business needs), the design team starts translating all the behaviors and ideas into a high-fidelity interface. 

Depending on the size, complexity and characteristics of the feature, it can take from a day to an entire sprint until the UI is ready to be shipped for development. Some features require a set of completely new pages, with their own responsiveness rules, headings and visual assets; others are based on components that need to be allocated in various areas of the UI; some features might require us to specify many different states and use cases of a component in the same page. For all these cases, we must observe a few guidelines:

**Validate our design early and often,** with design peers, development team and client. UI design can be very time-consuming, and the earlier we validate a concept, the better. A design peer must be the first resource for getting early critique on our work. But more often than not, the insight from developers who will work on that feature is just as enlightening. After a few rounds of internal validation to rule out the weakest ideas, we should include the client in the discussion, remembering to adjust their expectations when asking for feedback on a work-in-progress. 

**Consider technical viability.** It's important to know if the visual elements, components and animations we're proposing are easy to implement, if they're readily available on a component library, if there's a simpler way of making it work. We should aim for the highest impact with the lowest effort. 

**Consider responsiveness.** Vinta's main expertise is on web-based systems, so it's crucial to take into account the main web browser viewports and breaking points, when designing our interfaces: 
- Mobile small: 320px
- Mobile: 360px
- Tablet: 768px
- Desktop: 1024px
- Desktop large: 1440px
- Desktop FullHD: 1920px

We generally start building our UIs from the Mobile viewport and work our way up. The behavior of visual components when a browser is resized must be predicted during the UI design phase, and well specified for the development team.

**Respect the project's component library.** Each project has its own design library file, comprised of UI components, color scheme, iconography and typography guidelines. These libs are always evolving, along with the product. But we must be mindful about introducing new components or altering existing ones, as any visual changes that we propose on the design need to be addressed in development as well. 

**Keep design files organized and up to date.** Different from what happens with developers, designers are not permanently allocated to projects. At any point, our work files must be ready and organized enough to be handed off to a colleague or even to the client, if asked for. Text and layer styles must be properly applied, non-approved layouts and WIP elements need to be identified as so, and UI for all pages and components already developed need to be consistent with the system in production. 

### UI documentation
Documentation for this step may vary depending on complexity. For complex features or improvements that touch a lot of areas in the product, we produce a presentation. If the feature is small and simple, a single artboard is enough, which we then upload to a Zeplin board accessible to both client and dev team. 

The feedback process on UI usually starts during our design sync and extends to the rest of the week, with clients going through our presentations and previews and providing input on our communication channels (Zeplin, Asana or Slack).  


**Time estimate:** from 2 days to 2 weeks (1 full sprint), depending on complexity and criticalness of the feature. 

## 5. Usability tests
### When to run a usability test
Vinta believes that learning from actual users is the best way to build a product. However, we don't run textbook usability tests for all the features we work on. Producing and testing a high-fidelity prototype with users requires some logistics, both on our end and on the client's. Therefore, we use this technique when we want to test a feature that:
- is crucial to the product;
- has a high development cost, or 
- brings a disruptive change to a key behavior. 

This is part of our mindset of measuring effort vs impact for all the work our team does. 

### Aspects to consider
When planning a usability test, it's important to have a clear focus about what we want to validate, and keep the test scope as narrow as possible (e.g. ask participants to perform one action rather than a series of interdependent actions). In our experience, trying to measure too many aspects of an interface in one test makes it too complex and reduces the certainty in the end.

Another big decision that needs to be made in the beginning is between running moderated or unmoderated tests. Our team uses Lookback as the main tool for usability tests, which allows both methods. 

Moderated tests are great in the early stages of a feature, when we're trying to validate a key behavior and. Moderating a session, we can nudge our participants to think out loud, describe the component they're seeing and talk more openly about what they thought and felt during the test. On the flip side, moderated tests require a lot more design time, and managing schedules for all participants tends to be cumbersome. 

Unmoderated tests or self-tests are better if we need a critical mass of users to be really sure if our interface is clear enough, and if people are taking the expected path to perform an action. However, self-test participants tend to go through the script much faster and don't provide us much insight to what's in their heads. This kind of test is also great for measuring how long a person takes to perform an action.

### Test outcomes

The usability test results will, very likely, inform improvements on the feature. These may range from simple UI adjustments to a complete reshaping of the feature. Depending on the magnitude of changes, we might go back to the beginning of the design cycle, which for the client might look like a setback, but is actually a good thing. Test results must be summarized in a brief document or presentation, and discussed with the client on the next design meeting. More often than not, our discoveries during test sessions go beyond the feature at hand, and might generate new design tasks, to be included in the product roadmap. 


**Time estimate:** about 2 weeks, between planning the test, scheduling participants, running the sessions and consolidating results. Some of the logistics can be done in parallel with the previous phase, if we have more than one designer working on the team, but if the test is with a high-fidelity prototype, the interface must be ready beforehand.

## 6. Specs for development
After an interface is approved by the client (and in the case of bigger features, validated with users), the design team must deliver the specs for development. Working in an organized way during the UI phase helps a lot in delivering good specs. Copy must be final and approved by the client, colors and text styles must be consistent with the style guide, spacing between components must follow the predefined rules, and assets such as photography, illustrations and vector icons must be available for download. Please refer to this checklist for details on all that needs to be considered when shipping a spec. 

At Vinta we use the Zeplin plugin for Sketch to handoff specs. Every screen, artboard and component gets its own link, that is conveniently attached to the task on Asana. The team manager should be consulted as to what is the best format for each spec, which depends a lot on the feature. For landing pages, the recommended format is a set of artboards for the page in each viewport. For a new component that will be used throughout the system, a page specifying all its states, variations and behaviors might be best. For features that rely heavily on animation, the designer must also provide a video prototype of the expected behavior, example of such behavior in a live website, or reference to an existing component in a code library. Navigation prototypes, along with the feature's flow, are also great to give developers a broader context on what they're working on.

During the development phase, designers must make themselves available for clearing doubts from the team about specs and adjusting behavior of visual components, animations and responsiveness, in case unanticipated constraints or difficulties come up. 

**Time estimate:** 1 to 3 days. This step needs to be conducted by the same designer who built the UI. 

## 7. Design QA
The Review and QA phase is traditionally when developers run tests to catch bugs and see if the feature is running according to the requirements and specified flows. Designers need to be part of this phase as well, to make sure the interface was built pixel-perfect, according to our specs. This process should happen, ideally, in a sync between developer and designer, and follow the steps described in this checklist. However, if schedules are too hard to manage in that particular week, the Design QA can be done asynchronously, to avoid delays in deployment. 

Minor fixes like animation timing, messages on error states, notification triggers and general copy edits can be done by the developer during the meeting, directly on the code. But the designer must keep track of any changes and update the UI afterwards, to avoid inconsistencies in the future and keep the design debt to a minimum. 

## 8. Dealing with hotfixes
Hotfixes are small pieces of code developed to correct software bugs or faults, and released as quickly as possible, without going through the regular development process. When a hotfix involves a design adjustment (e.g add or remove a button, fix a piece of copy, change the color of a component) but needs to be deployed quickly, the assigned developer must make all the decisions and push the fix to production. Designers may give some input, if asked for it, but **the responsibility for the fix lies with the developer**. 

After the hotfix, the design team must be reported of any changes in UI. We then evaluate what was deployed and check whether there's room for improvement. If so, a task is created and added to the backlog. It might come back to the design workflow as a minor improvement, or bundled together with other changes in a larger feature update, when prioritized by the client and the team.
