# Services Architecture

We use Django to write the backend of our projects and we want to use its functionalities as much as we can to assist us getting the job done. Django has a very opinionated way on how things should be done and this is good. But one thing that it does not do is to get in the way of how and where to place business logic in your project.

There are many approaches available and you can read about them all around the internet. The one we adopt to our projects is to have a shared services module where all the business logic should be placed. This means that you are encouraged to use Django tools as long as the business logic is in the `services` module. For instance, you should use Django's class based views but instead of writing the [business] logic in the Django class you will write it as a function in the `services` module, import and call the function. Django related code (including code that glues `services` code so it adapts to Django) should be in the Django apps, everything else should go in the `services` module. 

Here are some practical guides on how you should organize services:

- Service directory looks like this:

```
services/
├── __init__.py
├── {service_name}                          # This is a toplevel namespace
│   ├── __init__.py
│   ├── {service_module1}.py                # This is the specific namespace for a group of services
│   ├── {service_module2}.py
│   └── tests                               # Tests folder is always in the root of the service
│       ├── __init__.py
│       ├── test_{service_module1}.py
│       └── test_{service_module2}.py
├── {other_service}
│   ├── __init__.py
│   ├── ...
│   └── tests
│       ├── __init__.py
│       └── ...
└── tasks                                   # The `tasks` service is the only place were tasks should live
    ├── __init__.py
    ├── {identifier}_tasks.py
    └── tests
        ├── __init__.py
        └── test_{identifier}_tasks.py
```

- Services are Python code that happen to import from Django `models`. They are not tied to any specific way of writing code defined by the framework. 

- Services never import from a Django app except for `models`.

- No business logic goes inside the a Django app. You import it from a service and call it.

- When using a service you should never import (or chain) more than 3 levels down in the module. Eg.: 

```
from services.integrations import google_calendar  # good
from services.integrations.google_calendar import get_credentials # bad

google_calendar.get_credentials(user) # good
google_calendar.credentials.get_credentials(user) # bad
```

- Exceptions should be available at the root of the service. 

Explanation: it would be misleading to do `from services.service_name import exception`. You might need exceptions from multiple services in a single module and this would lead to the need of aliases. Also we don't want to use exceptions as `service_name.Exception`, for most cases the exception name is enough to identify what it means.

- All service tests should be in a folder on the top level of the service module.

- All tasks should be defined inside the `tasks` service. This is a special service and all modules in it should have `_tasks` in its name. 

Explanation: although we will be calling this as standard functions, it should be clear that this code is going to run asynchronously.

- All functions wrapped by `@celery_app.task` should be private (its name should start with `_`) and there should be (in the same module) a public interface to the task that calls `.delay`. This means there should never be a `.delay`  call in the code besides inside the tasks service. 

Explanation: it should be possible to define a piece of code to run before the task is called (or prevent it from be called). This architecture also helps decoupling and simplifying tests (mocking). Another benefit is that it allows  better APIs as it can be designed for usability without the restrictions imposed by a Celery task (eg.: no passing of obejects that are complex to serialize).

- Services that delay tasks should start with `delay_`.

- Business logic is never inside a task. They import from a service and run it.