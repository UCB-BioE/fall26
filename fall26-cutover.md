---
layout: page
title: Fall 26 Cutover
description: Rename or copy this course site for Fall 2026.
---

# Fall 26 Cutover

This repo is now configured for Fall 26 publishing:

- `url: https://ucb-bioe.github.io`
- `baseurl: /fall26`

## Recommended Path: Make a New Copy

Use a separate `fall26` repository so prior terms remain frozen.

1. Create a new GitHub repo named `fall26` under `UCB-BioE`.
2. In your local repo, repoint `origin`:

```bash
git remote set-url origin https://github.com/UCB-BioE/fall26.git
```

3. Push current history:

```bash
git push -u origin main
```

4. In GitHub repo settings, enable Pages from the default branch.
5. Verify live URL:

```text
https://ucb-bioe.github.io/fall26/
```

## Alternate Path: Rename Existing Repo

Only use this if you do not need `fall25` as an independent archived site.

1. Rename GitHub repository from `fall25` to `fall26`.
2. Update local remote URL:

```bash
git remote set-url origin https://github.com/UCB-BioE/fall26.git
```

3. Confirm remote:

```bash
git remote -v
```

4. Confirm Pages URL in repository settings.

## Term Start Checklist

1. Update `bcourses_course_url` in `_config.yml` for the new bCourses shell.
2. Verify home, content, schedule, and policy pages render correctly.
3. Spot-check all links under `_modules/`.
4. Publish and verify from an incognito browser window.
