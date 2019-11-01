# Things we built

We love open-source and are always trying to give back to the community. That's why besides this playbook you are reading, we also have other open-source products.

## [Fix-my-Django](https://github.com/fixmydjango/fixmydjango-lib)

Fix My Django is a library to help Django developers find solutions for common Django exceptions. While developing a Django project, if you get any exception in the development server and fixmydjango.com has a solution for it, this library will display a link to the solution in the error 500 debug template.

As creators of Fix My Django, Vinta developers should add exceptions and their suggested solutions!

More details on how to install and use it can be found [here](https://github.com/fixmydjango/fixmydjango-lib#how-to-use).

## [Tapioca](https://github.com/vintasoftware/tapioca-wrapper)

Tapioca is an API wrapper maker. It provides an easy way to make explorable python API wrappers. APIs wrapped by Tapioca follow a simple interaction pattern that works uniformly, so developers don't need to learn how to use a new coding interface/style for each service API. You can find a full list of available API packages made with tapioca [here](http://tapioca-wrapper.readthedocs.io/en/stable/flavours.html).

For more detailed information, check [this blogpost](https://www.vinta.com.br/blog/2016/python-api-clients-with-tapioca/) about Tapioca.

## [Classy Django REST Framework](http://www.cdrf.co/)

CDRF is a web-based documentation with flattened information about Django REST Framework's class-based views and serializers. It's heavily based on [Classy Class-based View](http://ccbv.co.uk/).

## [Django React Boilerplate](https://github.com/vintasoftware/django-react-boilerplate)

It's a customizable boilerplate that comprises Vinta's main tech stack. Here's a list of what we deemed necessary and the technologies chosen to address those needs.

- Backend Framework ([Django](https://www.djangoproject.com/) and [Django.js](https://github.com/noirbizarre/django.js/))
- Email Sending ([Sendgrid](https://sendgrid.com/))
- Responsive Styling ([Bootstrap](https://getbootstrap.com/))
- Periodic Jobs ([Redis](https://redis.io/) and [Celery](http://www.celeryproject.org/))
- Interactive UI ([React](https://reactjs.org/))
- Continuous Integration ([CircleCI](https://circleci.com/))
- Handling Static Assets ([Webpack](https://webpack.js.org/))
- Static Files Serving ([WhiteNoise](http://whitenoise.evans.io/en/stable/))
- Database ([PostgreSQL](https://www.postgresql.org/))
- Easy Deployments ([Heroku Button](https://devcenter.heroku.com/articles/heroku-button))
- Logging ([Papertrail](https://papertrailapp.com/))
- Automated Quality Assurance ([Prospector](https://github.com/landscapeio/prospector) and [ESLint](https://eslint.org/) with [pre-commit](https://pre-commit.com/))


## [Django Celery Beat Status](https://github.com/vintasoftware/django-celerybeat-status)

We use Celery to deal with tasks in a queue-based fashion. It receives tasks from our Django application, and it runs them in the background. Periodic tasks are scheduled by Celery Beat, which runs them at regular intervals. Django Celerybeat Status is a library that integrates with django admin and displays in a simple GUI when your periodic tasks are going to run next.


## [Django Knowledge Share](https://github.com/vintasoftware/django-knowledge-share)
Microblog app used to share quick knowledge. This code powers Vinta's "Lessons Learned", running at http://www.vinta.com.br/lessons-learned/.

The posts are created via slack using a custom command and are automatically posted on Twitter.


## [Django Role Permissions](https://github.com/vintasoftware/django-role-permissions)
It's an app for role based permissions. It's built on top of Django's `contrib.auth` `User`, `Group` and `Permission` functionalities and does not add any other models to your project.


## [Dev Checklists](http://devchecklists.com/)
We love checklists. That's why we created a bunch of great checklists to guide developers on how to deliver the best possible software.

#### [Celery Tasks Checklist](http://celerytaskschecklist.com/)
Even if you have lots of experience and great configuration standards, we know that problems happen. This is a guide on how to build and configure great Celery async tasks, based on Filipe Ximenes' talk [Tasks: you gotta know how to run 'em...](https://www.youtube.com/watch?v=XjzyOyLbvN8) It contains best practices, resources, and instructions to avoid problems.

#### [Django Apps Checklist](http://djangoappschecklist.com/)
Our extensive experience with Django has allowed us to develop a checklist on how to build reusable Django apps. This checklist was based on Flavio Juvenal's talk [Qualities of great reusable Django apps](https://www.youtube.com/watch?v=AMg4Iind90Q&t=3s).

#### [Crisis Management Checklist](http://crisismanagement.devchecklists.com/)
A useful checklist for when you're facing a data recovery crisis. Based on Laís Varejão's [Saving Great Projects](https://www.youtube.com/watch?v=3g8mL-cOooY&t=125s) first presented at 2017 Python Brasil.

#### [Pull Requests Checklist](http://pullrequests.devchecklists.com/)
Do's and Don'ts for Pull Requests. Improve code quality and review speed.

#### [Python Api Checklist](http://python.apichecklist.com/)
Useful checklist for building good Python library APIs. Based on [How to make a good library API](https://www.youtube.com/watch?v=4mkFfce46zE) PyCon 2017 talk.


## [Django Templated Email](https://github.com/vintasoftware/django-templated-email)
It's a Django module to easily send templated emails. It allows you to send templated HTML or plaintext e-mails using Django template language, with all the available template tags and filters to easily build your e-mail templates.


## [Django REST Framework Read & Write Serializers](https://github.com/vintasoftware/drf-rw-serializers)
A small Django library that provides generic views, viewsets and mixins that extend the Django REST Framework ones, adding separate serializers for read and write operations.


## [Awesome Boilerplates](http://awesomeboilerplates.com/)
The Web's Most Awesome Directory of Boilerplate Projects


## [Python linters and Code Analysis](https://github.com/vintasoftware/python-linters-and-code-analysis)
A curated list made for the DjangoCon US talk [Preventing headaches with linters and automated checks](https://2017.djangocon.us/talks/preventing-headaches-with-linters-and-automated-checks/) by Flávio Juvenal.

# Conferences
Community is not only about producing open-source software (and playbooks), conferences are part of it as well. People are encouraged to give back as much as they can. With the interest of developing further exchange with other professionals, Vinta will buy tickets for any technical conferences deemed worthy by the employees, and if one of ours approves a talk in a conference, whether it's local or international, she/he is granted a bonus for their further collaboration in sustaining the community we are a part of. Keeping an eye on conference's submission deadlines helps everyone in doing so.

# Blogposts
We keep our blog updated. It helps twofold, we train people on how to write passing on what they've learned, and people from the community see Vinta as a reference, checking us for tips often. That's why whoever learns anything gets incentives to write it down. We count on everyone to keep an eye and say: "I think that's worth a blogpost!" whether in our day-to-day or in a weekly meeting.
