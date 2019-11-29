# Alerts

## Sentry

- [ ] Exceptions that the system may raise - <a href="#alert-1">[1]</a>
- [ ] Highly repetitive exceptions within a short time window - <a href="#alert-2">[2]</a>

## Papertrail

- [ ] Error keyword - <a href="#alert-3">[3]</a>
- [ ] Exception keyword - <a href="#alert-3">[3]</a>
- [ ] Scheduled tasks within a time window (failure or didn't execute) - <a href="#alert-4">[4]</a>

## New Relic

- [ ] Response time (web) - <a href="#alert-5">[5]</a>
- [ ] Database transaction time - <a href="#alert-5">[5]</a>
- [ ] Error percentage - <a href="#alert-5">[5]</a>
- [ ] Third-party services downtime / high response time - <a href="#alert-5">[5]</a>
- [ ] Key transactions response time - <a href="#alert-6">[6]</a>
- [ ] Key transactions error percentage - <a href="#alert-6">[6]</a>
- [ ] Application web transaction time deviation baseline - <a href="#alert-7">[7]</a>
- [ ] Application transaction database time deviation baseline - <a href="#alert-7">[7]</a>

## Uptime Robot

- [ ] Django web application (production and staging) - <a href="#alert-8">[8]</a>
- [ ] Celery Flower (production and staging) - <a href="#alert-8">[8]</a>
- [ ] Frontend application (production and staging) - <a href="#alert-8">[8]</a>
- [ ] Third-party services - <a href="#alert-8">[8]</a>

## CircleCI

- [ ] Build failure - <a href="#alert-9">[9]</a>

## Codecov

- [ ] Coverage change on pull requests - <a href="#alert-10">[10]</a>
- [ ] Coverage change by direct commits to master branch that might not be coming from pull requests - <a href="#alert-10">[10]</a>

## CodeClimate

- [ ] Code issues - <a href="#alert-11">11</a>

## Sqreen

- [ ] Incidents - <a href="#alert-12">12</a>

## Monit

- [ ] Machine status change (start, stop, restart) - <a href="#alert-13">13</a>
- [ ] Memory usage - <a href="#alert-13">13</a>
- [ ] CPU usage - <a href="#alert-13">13</a>
- [ ] Disk usage - <a href="#alert-13">13</a>

## How to create alerts

<ul>
  <li><div id="alert-1">[1] <a href="https://docs.sentry.io/workflow/notifications/alerts/">https://docs.sentry.io/workflow/notifications/alerts/</a></div></li>
  <li><div id="alert-2">[2] <a href="https://sentry.io/_/resources/customer-success/alert-rules/">https://sentry.io/_/resources/customer-success/alert-rules/</a></div></li>
  <li><div id="alert-3">[3] <a href="https://help.papertrailapp.com/kb/how-it-works/alerts/#create-alert">https://help.papertrailapp.com/kb/how-it-works/alerts/#create-alert</a></div></li>
  <li><div id="alert-4">[4] <a href="https://help.papertrailapp.com/kb/how-it-works/alerts/#inactivity-alerts">https://help.papertrailapp.com/kb/how-it-works/alerts/#inactivity-alerts</a></div></li>
  <li><div id="alert-5">[5] <a href="https://docs.newrelic.com/docs/alerts/new-relic-alerts/defining-conditions/create-alert-conditions">https://docs.newrelic.com/docs/alerts/new-relic-alerts/defining-conditions/create-alert-conditions</a></div></li>
  <li><div id="alert-6">[6] <a href="https://docs.newrelic.com/docs/apm/transactions/key-transactions/view-key-transactions-alert-information">https://docs.newrelic.com/docs/apm/transactions/key-transactions/view-key-transactions-alert-information</a></div></li>
  <li><div id="alert-7">[7] <a href="https://docs.newrelic.com/docs/alerts/new-relic-alerts/defining-conditions/create-baseline-alert-conditions">https://docs.newrelic.com/docs/alerts/new-relic-alerts/defining-conditions/create-baseline-alert-conditions</a></div></li>
  <li><div id="alert-8">[8] <a href="https://blog.uptimerobot.com/need-only-the-down-or-up-notifications-you-are-covered/">https://blog.uptimerobot.com/need-only-the-down-or-up-notifications-you-are-covered/</a></div></li>
  <li><div id="alert-9">[9] <a href="https://circleci.com/docs/2.0/notifications/">https://circleci.com/docs/2.0/notifications/</a></div></li>
  <li><div id="alert-10">[10] <a href="https://docs.codecov.io/docs/notifications">https://docs.codecov.io/docs/notifications</a></div></li>
  <li><div id="alert-11">[11] <a href="https://docs.codeclimate.com/docs/user-email-preferences">https://docs.codeclimate.com/docs/user-email-preferences</a></div></li>
  <li><div id="alert-12">[12] <a href="https://docs.sqreen.com/using-sqreen/incidents/#notifications">https://docs.sqreen.com/using-sqreen/incidents/#notifications</a></div></li>
  <li><div id="alert-13">[13] <a href="https://mmonit.com/monit/documentation/monit.html#System">https://mmonit.com/monit/documentation/monit.html#System</a></div></li>
</ul>