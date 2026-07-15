---
layout: page
title: Schedule
description: The weekly event schedule.
nav_order: 1
permalink: /
---

# Weekly Schedule

{% for schedule in site.schedules %}
{{ schedule }}
{% endfor %}
