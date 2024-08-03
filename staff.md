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

{% assign student_teaching_assistants = site.staffers | where: 'role', 'Student Teaching Assistant' %}
{% assign num_student_teaching_assistants = student_teaching_assistants | size %}
{% if num_student_teaching_assistants != 0 %}

{% assign googler_teaching_assistants = site.staffers | where: 'role', 'Googler Teaching Assistant' %}
{% assign num_googler_teaching_assistants = googler_teaching_assistants | size %}
{% if num_googler_teaching_assistants != 0 %}

## Fisk Teaching Assistants

{% for staffer in student_teaching_assistants %}
{{ staffer }}
{% endfor %}
{% endif %}

## Googler Teaching Assistants

{% for staffer in googler_teaching_assistants %}
{{ staffer }}
{% endfor %}
{% endif %}