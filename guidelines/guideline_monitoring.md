<!-- toc -->

- [1. Sentry](#1-sentry)
  - [1.1. What alerts should be set](#11-what-alerts-should-be-set)
  - [1.2. Why these alerts are important](#12-why-these-alerts-are-important)
    - [1.2.1. Exceptions that the system may raise](#121-exceptions-that-the-system-may-raise)
    - [1.2.2. Highly repetitive exceptions within a short time window](#122-highly-repetitive-exceptions-within-a-short-time-window)
- [2. Papertrail](#2-papertrail)
  - [2.1. What alerts should be set](#21-what-alerts-should-be-set)
  - [2.2. Why these alerts are important](#22-why-these-alerts-are-important)
    - [2.2.1. Error keyword](#221-error-keyword)
    - [2.2.2. Exception keyword](#222-exception-keyword)
    - [2.2.3. Scheduled tasks within a time window (success/failure)](#223-scheduled-tasks-within-a-time-window-successfailure)
- [3. New Relic](#3-new-relic)
  - [3.1. What alerts should be set](#31-what-alerts-should-be-set)
  - [3.2. Why these alerts are important](#32-why-these-alerts-are-important)
    - [3.2.1. Response time (web)](#321-response-time-web)
    - [3.2.2. Database transaction time](#322-database-transaction-time)
    - [3.2.3. Error percentage](#323-error-percentage)
    - [3.2.4. Key transactions response time](#324-key-transactions-response-time)
    - [3.2.5. Key transactions error percentage](#325-key-transactions-error-percentage)
    - [3.2.6. Third-party services](#326-third-party-services)
    - [3.2.7. Application metric baseline](#327-application-metric-baseline)
- [4. Uptime Robot](#4-uptime-robot)
  - [4.1. What alerts should be set](#41-what-alerts-should-be-set)
  - [4.2. Why these alerts are important](#42-why-these-alerts-are-important)
    - [4.2.1. Django web application (production and staging)](#421-django-web-application-production-and-staging)
    - [4.2.2. Flower (production and staging)](#422-flower-production-and-staging)
    - [4.2.3. Frontend application (production and staging)](#423-frontend-application-production-and-staging)
    - [4.2.4. Third-party services](#424-third-party-services)
- [5. CircleCI](#5-circleci)
  - [5.1 What alerts should be set](#51-what-alerts-should-be-set)
  - [5.2. Why these alerts are important](#52-why-these-alerts-are-important)
    - [5.2.1. Build failure](#521-build-failure)
- [6. Codecov](#6-codecov)
  - [6.1. What alerts should be set](#61-what-alerts-should-be-set)
  - [6.2. Why these alerts are important](#62-why-these-alerts-are-important)
    - [6.2.1. Coverage change on pull requests](#621-coverage-change-on-pull-requests)
- [7. CodeClimate](#7-codeclimate)
  - [7.1. What alerts should be set](#71-what-alerts-should-be-set)
  - [7.2. Why these alerts are important](#72-why-these-alerts-are-important)
    - [7.2.1. Maintainability stat changed](#721-maintainability-stat-changed)
- [8. Flower](#8-flower)
- [9. Sqreen](#9-sqreen)
  - [9.1. What alerts should be set](#91-what-alerts-should-be-set)
  - [9.2. Why these alerts are important](#92-why-these-alerts-are-important)
    - [9.2.1. Possible user leak](#921-possible-user-leak)
    - [9.2.2. Vulnerability discovery](#922-vulnerability-discovery)
- [10. Monit](#10-monit)
  - [10.1. What alerts should be set](#101-what-alerts-should-be-set)
  - [10.2. Why these alerts are important](#102-why-these-alerts-are-important)
    - [10.2.1. Machine status change (start, stop, restart)](#1021-machine-status-change-start-stop-restart)
    - [10.2.2. Memory usage](#1022-memory-usage)
    - [10.2.3. CPU usage](#1023-cpu-usage)
    - [10.2.4. Disk usage](#1024-disk-usage)

<!-- tocstop -->

## 1. Sentry

Sentry is mainly used for monitoring system misbehaviors, such as exceptions. This helps us better understand the context of failed work flows, so the team can better understand why a request, or a task, failed. We take advantage of Sentry SDK to set the environment keys it requires when running under async tasks, because since it's not under a request anymore, this information can be lost, making the errors to be claimed by the server user instead of the true origin user (the one that comes from the request).

Being responsible for it does not mean one should be the issue solver. By having a support schedule, the person responsible for support during that week will manage to keep the issues that show up in Sentry inbox. That means investigating the source of the problem or, at least, assigning someone to do so.

### 1.1. What alerts should be set

Ideally, every issue must be alerted at first on Sentry and only then filtering out or merging issues can take place. Although having email alerting is a must, we advise setting up Slack notifications in a channel with development team, and in order to avoid spamming messages, one can set up rules as to notify through Slack if a given issue happens 3 times or more for an hour.

- Exceptions that the system may raise
- Highly repetitive exceptions within a short time window

### 1.2. Why these alerts are important

#### 1.2.1. Exceptions that the system may raise

Every meaningful exception must be logged in order to track issues that system is raising. These exceptions may rise from different reasons, be it users misusing the system (which may indicate a possible rethink on how a certain feature should behave to proper adequate to how users expect the system to behave or a better indication on how the system was designed in order to teach users how they’re expected to use the system) or even programming errors, which will be handled as bug fixes or hot fixes depending on how critical the issue is.

#### 1.2.2. Highly repetitive exceptions within a short time window

Having the same issue being thrown repetitive times within a time window, e.g. 3 times within 10 minutes, indicates that this issue should be addressed soon. This is not the same as saying the issue will always determine that the issue highly critical if it falls under this alerting condition, but rather it means that it should be at least investigated as soon as possible in order to trace the root cause of the given issue.

## 2. Papertrail

Papertrail helps us promptly visualize log outputs. When properly configured, it facilitates log filtering. This help us filter out the web or workers logging, when looking for specific information. It's a great alternative for filtering log files directly into the server terminal.

Not every log file must be added to Papertrail, mostly due to cost. Some critical files can be kept out of Papertrail because the amount of log they generate are really huge, so keeping them out and leaving only some general workers and server log being written in there might be the solution. Nonetheless, all of them should be listed in a place can be easily accessible to the team in case of need.

### 2.1. What alerts should be set

Although it may feel like spamming, Papertrail can be set to notify of errors that may show up in any of the log files that it’s set to track. Other keywords can be tracked as well and set to notify a given email or Slack channel/user.

- Error keyword
- Exception keyword
- Scheduled tasks within a time window (success/failure)

### 2.2. Why these alerts are important

#### 2.2.1. Error keyword

This is not to be confused with exceptions as what may be listed in here would be more errors in general, which might eventually include server errors such as possible hack attempts.

#### 2.2.2. Exception keyword

While most errors will be listed under [Error keyword](#221-error-keyword), but sometimes one wants more specific messages, such as exceptions.

#### 2.2.3. Scheduled tasks within a time window (success/failure)

The point here is not to check when something failed during its execution, but rather whether it executed at all when it was expected to. This way, one can monitor expected routines to execute in a certain moment indeed executed or not, which may lead to something that went wrong.

## 3. New Relic

New Relic helps the team monitor transactions throughout the system. This helps the team properly understand what's the performance of requests and properly tracedown issues within them.

There are several options to set alerts: response time, error percentage, apdex, key transaction error percentage and response time, third-party services monitoring and application metric baseline.

In the context of New Relic, each endpoint/method combination is a different transaction, so one would see UserAuth.post endpoint in there listed as a transaction, as well as UserProfile.get and UserProfile.patch (or UserProfile.put). Key transactions are transactions that are important to the system in a sense that users can set specific alerts to each of them individually.

The baseline metric is a metric that will adjust to the rest of the system. This means that one can keep track of how the entire system performs and get notified whenever a request deviates from this baseline.

### 3.1. What alerts should be set

In their free plan, one can set up some alerts, although one can’t monitor key transactions which would be one of the most important sections to track in this tool. General response time for either web and database should be set, to check the average time of transactions within the system. User errors should also be set, this can be really helpful knowing what issues are most common to users and think through solutions to prevent them from keep on going. Thresholds will vary from project to project, so it’s important to keep on adjusting this value as to avoid spamming alerts into the notification channels, as this would lead to people start ignoring alerts sent through this tool. As prior mentioned, with a Pro Plan, one can configure key transactions, which will improve monitoring import requests and user transactions throughout the system.

- Response time (web)
- Database transaction time
- Error percentage
- Key transactions response time
- Key transactions error percentage
- Third-party services (redundant with Uptime Robot)
- Application metric baseline

### 3.2. Why these alerts are important

#### 3.2.1. Response time (web)

This corresponds to the entire request time. Really useful to track when a certain request took longer than expected to resolve. This will track no specific endpoint but rather the entire system. If one wants to have different thresholds for each endpoint, or only a handful endpoints, the proper way to check this is making use of key transactions.

#### 3.2.2. Database transaction time

This type of alert is useful to understand when a query is not performant.

#### 3.2.3. Error percentage

There are a certain amount of errors that can be tolerated within a time window. New Relic admins can set alert policies to track when an endpoint fails above this tolerated limit. This is important to understand when users are facing too many issues to deal with a certain part of the system.

#### 3.2.4. Key transactions response time

Similar to [Response time (web)](#321-response-time-web) but specific to key transactions.

#### 3.2.5. Key transactions error percentage

Similar to [Error percentage](#323-error-percentage) but specific to key transactions.

#### 3.2.6. Third-party services

This helps users detecting whenever a third-party service is facing issues. Sometimes what makes a transaction taking too long to respond is some third-party service. Even though one might have a service to monitor services, such as [Uptime Robot](#uptime-robot), this can be helpful in knowing when a given service of this third-party API is facing issue as not every endpoint of this third-party will be listed in the monitoring service.

#### 3.2.7. Application metric baseline

The sensitivity can be adjusted to how much can be tolerated when a request deviates from this average. As mentioned before, this will adjust itself to the system performance, so there’s no value to be set here to be watched but rather sensitivity in regards to performance deviation.

## 4. Uptime Robot

Uptime Robot comes really in handy for monitoring whether services are up and running. It’s good to list every possible service in here and set notifications right, production and staging environments included. The reaction of events triggered by the tool will depend on the reason of the event alert. When it’s case for a critical system downtime, the client must be notified and alerted of any possible workaround. If it’s a third-party that’s down and it’s critical for the system to consume from this resource, the client must be alerted of this and the third-party support contacted for follow ups on solution status (subscribing to the third-party service status alert might be the only way sometimes). If the latter takes too long to resolve, the client must be consulted on whether add an alert in the system to let users know that that given third-party service is down and features that depend on it will be affected.

### 4.1. What alerts should be set

One should map here entries to check for the web application, flower and third party services. Everytime one of these services is out, people should get notified. Preferences are over email and Slack.

- Django web application (production and staging)
- Flower (production and staging)
- Frontend application (production and staging)
- Third-party services

### 4.2. Why these alerts are important

#### 4.2.1. Django web application (production and staging)

Every time the Django application is down or crashing the team must be notified in order to act on it as soon as possible.

#### 4.2.2. Flower (production and staging)

Since Flower is the tool used to monitor Celery workers it should be watched as well. Losing the ability to keep track of tasks that will run, are running and already ran can be troublesome as it may lead to spending more time investigating issues than it'd take with the tool up and running.

#### 4.2.3. Frontend application (production and staging)

The frontend application must be checked for the same reason as the backend.

#### 4.2.4. Third-party services

All third-party services that the system depends on should be tracked, so one can know whether a specific endpoint or the entire third-party system is facing issues or even is under outage.

## 5. CircleCI

Every time code gets pushed to the repository, a build work flow is triggered. This helps us know when some code insertion broke the code (assuming that section of the code is properly tested). By taking advantage of the work flow functionality, we managed to break the build into different steps, while unblocking the build queue for other pushes into the repository.

`develop` branch triggers a deploy to the staging server upon success, meaning all written tests and linting tools were run and passed.

### 5.1 What alerts should be set

Notifications here are focused on any work flow step failure.

- Build failure

### 5.2. Why these alerts are important

#### 5.2.1. Build failure

More important than successful builds are knowing when some change breaks the system somehow, whether be it by making written test cases to fail, code style discrepancies or even when broken code pieces are pushed.

## 6. Codecov

Codecov enables us to easily keep track of code coverage throughout time. We configured it in order to make everyone who opens a PR understand how their code is impacting in the system coverage, being mainly informative than prohibitive as failure in the checkage, meaning a coverage decrease, won't block the contribution to be merged. Coverage impact is calculated in two ways:

1. _Application coverage_: changes impacting on the whole system coverage, set to keep a minimum of 70%.
2. _Diff coverage_: cover of the changed code, how much of the new or updated code is being covered, this is set to 70%.

Although we're using the same 70% as a measure here, diff and application coverage have different meanings. While the former refers to just the portion of the code that's being contributed, the latter refers to the whole code base.

Even though, code coverage decrease is not desirable, we shouldn’t be too strict on blocking PRs due to this reason, but it’s an indicator that should be considered from time to time.

### 6.1. What alerts should be set

Having intermittent alerts set might not be ideal, as this could spam a lot of work in progress. Notifying on pull-requests and master branch is the way to go as these are the most important points of tracking.

- Coverage change on pull requests

### 6.2. Why these alerts are important

#### 6.2.1. Coverage change on pull requests

Pull requests will often impact on the code coverage overall, so this should be tracked. Most code coverage analysis tools provide ways to use bots to analyze each opened PR given the coverage data got sent in a CI tool, such as [CircleCI](#circleci). This will help people involved in a given PR, be it the person who opened it or the reviewer, to know what impact those code changes will have on the system, coverage wise. This could be either a patch coverage, meaning how much of the changed code is covered as well as what will be the whole code base coverage after merging it.

## 7. CodeClimate

CodeClimate evaluates the quality of the code based on some criteria. Code smells, code complexity and some other code best practices.

By taking a look on how our code base looks like when evaluated against a quality tool like this, it helps us understand better how we can tackle some possible pain points such as duplicates and keep track of our maintainability.

### 7.1. What alerts should be set

Though no action would be taken upon code change right away, it’s recommended to keep on track of code quality. Anytime this quality is affected, people should be notified as this will affect code health, thus it might lead to bad-smells. Also, to encourage the team to keep on improving the maintainability of the codebase, it’s advised to alert on this type of change as well.

- Maintainability stat changed

### 7.2. Why these alerts are important

#### 7.2.1. Maintainability stat changed

Every time code is pushed to the repository, it tends to affect the maintainability of certain part of the system. This can either improve or worsen the state of the code base. Code Climate provides estimative of how long it'd take for one to refactor files that are not following some guidelines that were set in its configuration. Every time this estimative is impacted, for better or worse, it should notify of this change.

## 8. Flower

Flower behaves basically like a frontend to Celery worker queues. By having the information properly configured, it helps us know if there are tasks currently running and what are these tasks.

## 9. Sqreen

Sqreen is used to monitor the security of requests sent to the system. Another important use is to check user interaction in the system in a sense of login security, with this we can track how many successful and failed attempts, whether a given account is shared or not or if they connect to the system through TOR. These checks help us understand better how users are interacting with the system, e.g. if they're more familiar with username or email login. The output of these login attempts are also used on tracking why certain users are not able to login in their accounts.

### 9.1. What alerts should be set

Sqreen can be set to alert every time it identifies that some login credentials might have leaked or when someone is trying to discover vulnerabilities in the system.

- Possible user leak
- Vulnerability discovery

### 9.2. Why these alerts are important

#### 9.2.1. Possible user leak

Sqreen can tag usernames that were possibly leaked. Whenever it detects multiple logins, successful or not, from the same origin, it notifies that there is a possible hacking attack going on. This is useful to notify users that are have weak credentials to strengthen them.

#### 9.2.2. Vulnerability discovery

Known vulnerability discoveries are protected by default in Sqreen. Regardless of this, Sqreen will notify letting one decide what to do afterwards as one of the options is blocking the IP address that tried finding flaws in the web application security.

## 10. Monit

Monit is being used to monitor processes running in the production web and database servers. It should notify us whenever disk or memory usage reaches a certain threshold. This is really helpful as there are some tasks running that had previously hit any of the quotas mentioned before, leading to a fatal crash on the server.

### 10.1. What alerts should be set

- Machine status change (start, stop, restart)
- Memory usage
- CPU usage
- Disk usage

### 10.2. Why these alerts are important

#### 10.2.1. Machine status change (start, stop, restart)

Unexpected machine state should be monitored, so whenever a machine stops or restarts when not expected whoever is managing this infrastructure will be notified.

#### 10.2.2. Memory usage

Memory usage can impact on whether the system can keep on executing the processes or not, meaning that once it tops, everything tends to stop and there's a chance that the system might kill this process while it's still in execution, so this should be watched.

#### 10.2.3. CPU usage

High CPU usage should be alerted in the sense that this can indicate when the tasks are consuming too much of the available resources, and once it tops, it'll prevent new process to run.

#### 10.2.4. Disk usage

This alert has the utter-most importance among Monit alerts as disk usage can prevent access to system, reboot, resize and some other operations.
