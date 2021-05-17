---
layout: default
---

# Data

The following table is a comprehensive list of the features we computed and used in our experiments. The table contains the name of the feature as it appears in our code, as well as a description of each basic feature.

<table>
{% assign header = "**Feature Name** | **Description**" | split: "|" %}
{% tablerow col in header %} {{ col | markdownify }} {% endtablerow %}

{% for item in site.data.features %}
{% assign col1 = item.name | split: "|" %}
{% if item.desc %}{% assign col2 = item.desc | split: "|" %}{% else %}{% assign col2 = " " | split: "" %}{% endif %}
{% assign row = col1 | concat: col2 %}
{% tablerow col in row cols:2 %} {{ col }} {% endtablerow %}
{% endfor %}
</table>