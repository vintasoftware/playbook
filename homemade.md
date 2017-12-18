# Home-Made Projects

## [Fix-my-Django](http://www.fixmydjango.com/)

### About the project:
Fix My Django is a library to help Django developers find solutions for common Django exceptions. While developing a Django project, if you get any exception in the development server and fixmydjango.com has a solution for it, this library will display a link to the solution in the error 500 debug template.

As creators of Fix My Django, Vinta developers should add exceptions with solutions to it!

### Install Fix My Django on all projects
Add `fixmydjango` only to your `local.py` settings:
```
    # local.py
    INSTALLED_APPS += ('fixmydjango',)
    FIX_MY_DJANGO_ADMIN_MODE = True
```
