---
layout: default
---

# Publications
{% for item in site.data.publications %}
{% capture links %}
{%- if item.pdf -%} [[pdf]]({{ item.pdf }}) {% endif %}
{%- if item.bib -%} [[bib]]({{ item.bib }}) {% endif %}
{%- if item.slides -%} [[slides]]({{ item.slides }}) {% endif %}
{%- if item.talk -%} [[talk]]({{ item.talk }}) {% endif %}
{% endcapture %}

* **{{ item.title }}**  
	{{ item.authors }} {% if item.pub-type %}  
	{{ item.pub-type }} {% endif %} {% if item.date %}   
	{{ item.date }} {% endif %} {% if item.award %}  
	**{{ item.award }}** {% endif %}  
	{{ links }}	{% if item.note %}  
	\* {{ item.note }} {% endif %}
{% endfor %}