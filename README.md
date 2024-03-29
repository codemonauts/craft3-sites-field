# Sites Field for Craft 3

This plugin provides a field type for choosing sites. Entries using this field can then access the site ID in their templates.

---

## Requirements

* Craft CMS 3.0.0-RC1 or above

## Example Usage

To display only events related to the current site you could use the following logic:

```twig
{% set events = craft.entries.site('main').section('blog').type('event').orderBy('date asc').all() %}
{% for event in events %}
  {% if craft.app.sites.currentSite.id in event.siteIds %}
    {# show this event... #}
  {% endif %}
{% endfor %}
```

> Note: `siteIds` returns an array of site ID's which you can use the twig [in](https://twig.symfony.com/doc/2.x/templates.html#containment-operator) operator.
