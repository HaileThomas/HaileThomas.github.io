<h2 id="{{ include.key }}" style="margin: 2px 0px -15px;">{{ include.title }}</h2>

<div class="experience">
<ul class="experience-list">

{% for job in site.data.experience[include.key] %}

<li>
  <div class="title">{{ job.role }}, {{ job.org }}</div>
  <div class="periodical"><em>{{ job.dates }}</em>{% if job.notes %} · {{ job.notes | markdownify | remove: '<p>' | remove: '</p>' | strip }}{% endif %}</div>
  {% if job.bullets %}
  <ul>
    {% for b in job.bullets %}
    <li>{{ b | markdownify | remove: '<p>' | remove: '</p>' | strip }}</li>
    {% endfor %}
  </ul>
  {% endif %}
</li>

{% endfor %}

</ul>
</div>
