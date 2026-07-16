---
layout: home
title: Outline
nav_order: 1
permalink: /
seo:
  type: Course
  name: Just the Class
---

# BioEngineering 10
[bCourses]({{ site.bcourses_course_url }}){: .btn .btn-blue .mr-2 }
[Ed](https://edstem.org/us/courses/41881/discussion/){: .btn .btn-purple }

## Announcements

{% assign announcements = site.announcements | reverse %}
{% for announcement in announcements %}
{{ announcement }}
{% endfor %}

## Schedule

{% for module in site.modules %}
{{ module }}
{% endfor %}

