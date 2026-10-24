---
layout: default
---
{% assign groups = site.posts | reverse | group_by: "category" %}
{% for group in groups %}
<h2 class="post-list-heading">{{ group.name | default: "Other" }}</h2>
<ul class="post-list">
  {% for post in group.items %}
  <li>
    <span class="post-meta">{{ post.date | date: "%b %-d, %Y" }}</span>
    <h3><a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h3>
  </li>
  {% endfor %}
</ul>
{% endfor %}