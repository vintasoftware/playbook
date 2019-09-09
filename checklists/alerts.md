# Alerts

## Sentry

- [ ] Exceptions that the system may raise
- [ ] Highly repetitive exceptions within a short time window

## Papertral

- [ ] Error keyword
- [ ] Exception keyword
- [ ] Scheduled tasks within a time window (success/failure)

## New Relic

- [ ] Response time (web)
- [ ] Database transaction time
- [ ] Error percentage
- [ ] Key transactions response time
- [ ] Key transactions error percentage
- [ ] Third-party services (redundant with Uptime Robot)
- [ ] Application web transaction time deviation baseline
- [ ] Application transaction database time deviation baseline

## Uptime Robot

- [ ] Django web application (production and staging)
- [ ] Flower (production and staging)
- [ ] Frontend application (production and staging)
- [ ] Third-party services

## CircleCI

- [ ] Build failure

## Codecov

- [ ] Coverage change on pull requests
- [ ] Coverage change by direct commits to master branch that might not be coming from pull-requests

## CodeClimate

- [ ] Code issues
- [ ] Maintainability improvements

## Sqreen

- [ ] Possible user leak
- [ ] Vulnerability discovery

## Monit

- [ ] Machine status change (start, stop, restart)
- [ ] Memory usage
- [ ] CPU usage
- [ ] Disk usage
