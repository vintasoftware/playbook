# Launch

Before launching to production, assert following steps are guaranteed.

## Frontend Checklist

- [ ] Spell-check copy.
- [ ] Set favicon.
- [ ] Customize [default error views](https://docs.djangoproject.com/en/2.0/howto/deployment/checklist/#customize-the-default-error-views).
- [ ] Run [Observatory](https://observatory.mozilla.org/).
- [ ] Check [Google Page Speed](https://developers.google.com/speed/pagespeed/).
- [ ] Run [Google Webmaster Tools](https://www.google.com/webmasters/tools/home).
- [ ] Guarantee [Mobile-Friendly](https://search.google.com/test/mobile-friendly).
- [ ] Guarantee the [viewport](https://getbootstrap.com/docs/4.0/getting-started/introduction/#starter-template) is correct: `<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">`.
- [ ] Make `robots.txt`.
- [ ] Make a `sitemap.xml` using Django.

## Django Checklist

- [ ] Follow [Django Deployment checklist](https://docs.djangoproject.com/en/dev/howto/deployment/checklist/)
- [ ] Run `python manage.py check --deploy` in production
- [ ] Anonymize the URLs for Admin, Celery Flower, etc.
- [ ] Check redirections, especially if it's a new platform replacing an old one.
- [ ] Set `upload_to` argument for all `FileField` and `ImageField`.
- [ ] Check environment variables are being used, not hardcoded settings.
- [ ] Properly set `ALLOWED_HOSTS`.
- [ ] Guarantee `DEBUG = False`.
- [ ] Change `SECRET_KEY`.
- [ ] Set `APPEND_SLASH = True`.
- [ ] Set `CSRF_COOKIE_SECURE = True`.
- [ ] Set `SESSION_COOKIE_SECURE = True`.
- [ ] Check `SECURE_PROXY_SSL_HEADER`. See [documentation](https://docs.djangoproject.com/en/2.0/ref/settings/#std:setting-SECURE_PROXY_SSL_HEADER).
- [ ] Set `SECURE_SSL_REDIRECT = True`.
- [ ] Check `XFrameOptionsMiddleware` is being used. See [documentation](https://docs.djangoproject.com/en/2.0/ref/clickjacking/#clickjacking-prevention).
- [ ] Set *HTTP Strict Transport Security*. See [documentation](https://docs.djangoproject.com/en/2.0/ref/middleware/#http-strict-transport-security).
- [ ] Set `SECURE_CONTENT_TYPE_NOSNIFF = True`.
- [ ] Set `SECURE_BROWSER_XSS_FILTER = True`.
- [ ] If using subdomains, set `SESSION_COOKIE_DOMAIN`. See [documentation](https://docs.djangoproject.com/en/2.0/topics/http/sessions/#session-security).
- [ ] Consider `ATOMIC_REQUESTS` for DB integrity. See [documentation](https://docs.djangoproject.com/en/2.0/topics/db/transactions/#tying-transactions-to-http-requests).
- [ ] Check `DEFAULT_FROM_EMAIL` is set to a friendly replyable email.
- [ ] Set and test *ADMINS* for 500 errors emails.
- [ ] Set and test *MANAGERS* for 404 errors emails.
- [ ] Check email templates are correct.
- [ ] Save metadata of every email sent, use [Anymail signals](http://anymail.readthedocs.io/en/stable/sending/signals/).
- [ ] Check CORS settings, use [django-cors-headers](https://github.com/ottoyiu/django-cors-headers).
- [ ] Have a high delta between choices:
```
PLAN_TYPES = Choices((0, 'free', _('Free')), (100, 'basic', _('Basic')),
                     (200, 'premium', _('Premium')), (300, 'multimedia', _('Multimedia')))
```

## Third-party Checklist

- [ ] Add all accesses of third-party tools to *[LastPass](https://www.lastpass.com/)*.
- [ ] Add development env to *[LastPass](https://www.lastpass.com/)*.
- [ ] Configure *[Papertrail](https://papertrailapp.com)*, or other logging service.
- [ ] On Papertrail, configure alerts for common errors like `"app/web" Internal Server Error`, `"app/worker" ERROR/`, `"error code=H" OR "Error R" OR "Error L"`
- [ ] Configure [Librato](https://www.librato.com/) to track slow response time.
- [ ] Configure *[Sentry](https://sentry.io/)* for backend, including Celery.
- [ ] Configure *[Sentry](https://sentry.io/)* for frontend.
- [ ] Configure *[Mailgun](https://www.mailgun.com/)*, or other transactional email service.
- [ ] Configure *[Cloudflare](https://www.cloudflare.com/)* cache for frontend assets.
- [ ] Configure *[Uptime Robot](https://uptimerobot.com/)*.
- [ ] Setup [Google Tag Manager](https://developers.google.com/tag-manager/quickstart) container ID.
- [ ] Update OAuth callback/deauthorize URLs in all third-party services.
- [ ] Rotate OAuth keys of all third-party services.
- [ ] Change passwords of all third-party services.
- [ ] Check buckets/blob storages of AWS/Azure are private.
- [ ] Check the [SaaS CTO Security Checklist](https://www.sqreen.io/checklists/saas-cto-security-checklist).

## Server Checklist
- [ ] Check latest Heroku stack is being used.
- [ ] Check latest server OS version is being used.
- [ ] Check latest server Python version is being used.
- [ ] Set a Heroku "Standard" database or higher.
- [ ] Configure database backup generation scripts.
- [ ] Configure full disk backups for the database server. Make sure it's stored in another resource group (not production), it's locked against deletion it's and easy and fast to restore it.
- [ ] Tune [PostgreSQL settings](http://pgtune.leopard.in.ua/).
- [ ] Configure SSL for everything.
- [ ] Configure SSL certificates autorenewal.
- [ ] Test [SSL health](https://www.ssllabs.com/ssltest/index.html).
- [ ] Configure Redis maxmemory and eviction policy (likely noeviction).
- [ ] Configure [RabbitMQ](https://www.rabbitmq.com/production-checklist.html).
- [ ] Configure application firewall for application servers.
- [ ] Guarantee Celery and other services aren't running as `sudo`.
- [ ] Limit file size for uploads.
- [ ] Validate uploads media types. See [here](http://blog.hayleyanderson.us/2015/07/18/validating-file-types-in-django/).
- [ ] Configure throttling.

## DNS Checklist

- [ ] Check records.
- [ ] Check TTL. Set low when launching, set high after everything is fine.
- [ ] Move API to a different subdomain *(`api.example.org`, for example)*. This allows a different server for the frontend.
- [ ] Enforce or remove *www* subdomain (and set `PREPEND_WWW` in Django if necessary).

## SEO Checklist
- [ ] Follow [SEO For Web Engineers](https://www.johnwdefeo.com/articles/seo-for-engineers).
- [ ] Follow [A technical guide to SEO](https://ma.ttias.be/technical-guide-seo/)
