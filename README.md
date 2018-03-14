# Sites Field for Craft 3

This plugin provides a field type for choosing sites. Entries using this field can then access the site ID in their templates.

---

## Requirements

* Craft CMS 3.0.0-RC1 or above

## Example Usage

To display only entries related to the current site you could use the following logic:

```twig
{% for entry in entries %}
  {% if craft.app.sites.currentSite.id in entry.siteIds %}
    ...
  {% endif %}
{% endfor %}
```

> Note: `siteIds` is the field name defined for this fieldtype and returns an array of site ID's which you can use the twig [in](https://twig.symfony.com/doc/2.x/templates.html#containment-operator) operator.
