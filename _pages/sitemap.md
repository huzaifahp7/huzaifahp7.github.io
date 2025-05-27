---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

{% include base_path %}

A list of all the posts and pages found on the site. For you robots out there, there is an [XML version]({{ base_path }}/sitemap.xml) available for digesting as well.

<h2>Pages</h2>
{% for post in site.pages %}
  {% unless post.title == "Sitemap" or post.title == "Markdown" or post.title == "Terms" or post.title == "404" or post.title == "Talkmap" or post.title == "Talks" or post.title == "Teaching" or post.title == "Tag Archive" or post.title == "Year Archive" or post.title == "Collection Archive" or post.title == "Page Archive" or post.title == "Category Archive" or post.title == "Archive Layout" or post.title == "CV JSON" %}
    {% include archive-single.html %}
  {% endunless %}
{% endfor %}

{% comment %}
<h2>Posts</h2>
{% for post in site.posts %}
  {% include archive-single.html %}
{% endfor %}

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
{% unless collection.output == false or collection.label == "posts" %}
  {% capture label %}{{ collection.label }}{% endcapture %}
  {% if label != written_label %}
  <h2>{{ label }}</h2>
  {% capture written_label %}{{ label }}{% endcapture %}
  {% endif %}
{% endunless %}
{% for post in collection.docs %}
  {% unless collection.output == false or collection.label == "posts" %}
  {% include archive-single.html %}
  {% endunless %}
{% endfor %}
{% endfor %}
{% endcomment %}
