---
layout: default
---

# Data

## Features
Although we only propose a small number of base HCS parameters in our paper, they can be combined in many ways to capture different structural information about the instance. The following table is a comprehensive list of all the computed features which were used for our machine learning classification and regression results. This includes our proposed HCS parameters as well as other parameters which we believe to be important, such as mergeability. The table contains the name of the feature as it appears in our code, as well as a description of each basic feature.

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

## Feature Clusters
In the following table, we list the representative feature and its parent cluster for predicting solving time and classification of an instance into its category.

<table>
{% assign header = "**Feature** | **Cluster**" | split: "|" %}
{% tablerow col in header %} {{ col | markdownify }} {% endtablerow %}
{% for item in site.data.clusters %}
{% assign col1 = item.name | split: "|" %}
{% if item.desc %}{% assign col2 = item.desc | split: "|" %}{% else %}{% assign col2 = " " | split: "" %}{% endif %}
{% assign row = col1 | concat: col2 %}
{% tablerow col in row cols:2 %} {{ col }} {% endtablerow %}
{% endfor %}
</table>
