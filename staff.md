---
layout: page
title: Staff
description: A listing of all the course staff members.
---

# Staff

For a quicker response on homework or project help, please ask on [EdStem](https://edstem.org/us/courses/41289) rather than emailing staff members individually. On EdStem, all staff members (and students!) can see your question and answer it.

## Instructor

{% assign instructors = site.staffers | where: 'role', 'Instructor' %}
{% for staffer in instructors %}
{{ staffer }}
{% endfor %}

{% assign teaching_assistants = site.staffers | where: 'role', 'Teaching Assistant' %}
{% assign num_teaching_assistants = teaching_assistants | size %}
{% if num_teaching_assistants != 0 %}

## Fisk Teaching Assistants

{% for staffer in teaching_assistants %}
{{ staffer }}
{% endfor %}
{% endif %}
