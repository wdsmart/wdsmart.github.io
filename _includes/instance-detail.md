{% assign instances = site.data.class_instances | where: 'subject', include.subject | where: 'number', include.number | uniq | sort: 'term' | sort: 'year' %}

{% assign number = instances | size %}
{% assign last_instance = instances | last %}

{%- if number == 0 %}
  Never taught.
{% else %}
  {%- if number == 1 %}
    Taught 1 time in
  {%- else %}
    Taught {{ number }} times.  Last taught in
  {% endif %}
  {%- case last_instance.term %}
    {% when '0' %}
      Summer
    {% when '1' %}
      Fall
    {% when '2' %}
      Winter
    {% when '3' %}
      Spring
  {% endcase %}
  {{- last_instance.year }}.
{% endif %}