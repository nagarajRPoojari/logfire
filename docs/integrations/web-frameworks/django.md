---
integration: otel
---

# Django

The [`logfire.instrument_django()`][logfire.Logfire.instrument_django] method can be used to instrument the [Django][django] web framework with **Logfire**.

## Installation

Install `logfire` with the `django` extra:

{{ install_logfire(extras=['django']) }}

## Usage

In the `settings.py` file, add the following lines:

```py
import logfire

# ...All the other settings...

# Add the following lines at the end of the file
logfire.configure()
logfire.instrument_django()
```

[`logfire.instrument_django()`][logfire.Logfire.instrument_django] uses the
**OpenTelemetry Django Instrumentation** package,
which you can find more information about [here][opentelemetry-django].

## Database

By default, the **Django** configuration [uses SQLite as the database engine].
To instrument it, you need to call [`logfire.instrument_sqlite3()`][logfire.Logfire.instrument_sqlite3].

If you are using a different database, check the available instrumentation methods in our [Integrations section].

[django]: https://www.djangoproject.com/
[opentelemetry-django]: https://opentelemetry-python-contrib.readthedocs.io/en/latest/instrumentation/django/django.html
[django-instrumentor]: https://opentelemetry-python-contrib.readthedocs.io/en/latest/instrumentation/django/django.html#opentelemetry.instrumentation.django.DjangoInstrumentor
[uses SQLite as the database engine]: https://docs.djangoproject.com/en/dev/ref/settings/#databases
[Integrations section]: ../index.md
