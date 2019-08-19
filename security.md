# Security

Security is no easy topic to talk about. There are many ways to explore vulnerabilities in a website, as well as security implications for day-to-day practices and processes. To address that we follow security guidelines and use well known and tested tools to reduce risks. Although writing code that is robust and tested against vulnerabilities is essential for secure applications, it's well known that [social engineering](https://en.wikipedia.org/wiki/Social_engineering_(security)) is many times the weakest link in the chain. For that, we enforce tools and practices that tackle this kind of problem. Below are our processes for reducing security-related risks:

## Employees and Accounts
- 2-factor authentication everywhere it's possible (enforced to everyone on our organization accounts on GitHub, Google G Suite, etc)
- Email managed by Google G Suite
- LastPass managed passwords for all shared accounts
- Encrypted disks on all computers
- Invalidation of all accounts and keys when a employee leaves the company
- No reuse of email addresses of employees that left the company
- Deletion of all code and assets after we leave a project

## Code Security
- Static analysis with [dodgy](https://github.com/landscapeio/dodgy) (to avoid secret keys on code) and [bandit](https://github.com/PyCQA/bandit) (to avoid common vulnerabilities), configured both in CI and pre-commit hooks.
- Dependency insecure version management with [safety](https://github.com/pyupio/safety) (on CI) and [GitHub Security Alerts](https://help.github.com/en/articles/about-security-alerts-for-vulnerable-dependencies)
- Critical flows review checklists during code review and QA

## Application Security
- [Sqreen](https://www.sqreen.com/)
- <a href="https://devchecklists.com/production-launch-checklist/" target="_blank">Launch checklist</a> that we run periodically, to check things like Django settings, oAuth keys rotations, SSL health, etc.
- Unprivileged run (we mostly use PaaS like Heroku)
- Avoiding downloads of production data, and if it's needed, it must be anonimyzed before download
- Exception monitoring with [Sentry](https://sentry.io/)

## Encrypting Sensitive Messages
Every once in a while it's necessary to transfer security sensitive information such as passwords to clients. Use GPG to encrypt that kind of information

- **Linux Users.** We recommended [GPA](https://www.gnupg.org/software/gpa/index.html), a graphical interface for GnuPGP. Follow [this tutorial](https://www.deepdotweb.com/2015/02/17/basic-guide-pgp-linux/) to install and learn the basics.
- **Mac Users.** [PGP tools is easy to install and use](https://gpgtools.org/).

## Additional resources
- [The SaaS CTO Security Checklist](https://www.sqreen.com/checklists/saas-cto-security-checklist)
