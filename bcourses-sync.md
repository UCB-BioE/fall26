---
layout: page
title: bCourses Sync
description: How to keep this companion outline aligned with bCourses.
---

# bCourses Sync

This site pulls all bCourses links from one course root URL:

- `site.bcourses_course_url` in `_config.yml`

## Update for a New Term

1. Update `bcourses_course_url` in `_config.yml`.
2. Verify the top navigation bCourses link on the home page.
3. Spot-check several weekly pages in `_modules/` to confirm links resolve.

## Weekly Content Sync Checklist

1. Add or update lecture links in the relevant `_modules/week-XX.md` file.
2. Add assignment links with due dates in the matching week.
3. Confirm naming consistency between bCourses items and outline labels.
4. Publish both systems in the same update window.

## Quick Audit Command

From the repo root, run:

```bash
rg "bcourses\.berkeley\.edu|site\.bcourses_course_url" _modules README.md
```

This helps verify bCourses links are present and still centralized.
