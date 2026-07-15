# BioE10 Fall 26 — Agent & Maintainer Guide

This is the course website for BioEngineering 10, Fall 2026 at UC Berkeley.
Built with Jekyll + Just the Docs, hosted on GitHub Pages at:
https://ucb-bioe.github.io/fall26/

---

## Repository Layout

| Path | Purpose |
|---|---|
| `README.md` | Homepage (announcements + schedule) |
| `content.md` | Course content / learning objectives |
| `policies.md` | Course policies |
| `schedule.md` | Schedule page wrapper |
| `staff.md` | Staff page wrapper |
| `_modules/week-XX.md` | Weekly lectures, sections, quizzes (weeks 01–15) |
| `_staffers/` | Staff bio cards |
| `_announcements/` | Announcement posts |
| `_schedules/` | Schedule data |
| `_layouts/`, `_includes/`, `_sass/` | Theme overrides |
| `_config.yml` | Site config, bCourses URL anchor, Jekyll excludes |
| `maintainer-local/` | Local-only notes — never pushed, never built |

---

## Local Development Setup

Requires Ruby 3.2+ managed via rbenv.

### First-time setup

```bash
# Install rbenv (if not present)
brew install rbenv ruby-build
eval "$(rbenv init -)"

# Install the pinned Ruby version
rbenv install 3.2.8        # skips if already installed

# From the repo root:
rbenv local 3.2.8          # already committed as .ruby-version
gem install bundler
bundle install
```

### Run local server

```bash
export PATH="/opt/homebrew/bin:$PATH"
eval "$(rbenv init -)"
bundle exec jekyll serve --livereload
```

Preview at: http://127.0.0.1:4000/fall26/

> **Note:** `_config.yml` changes require a full server restart — LiveReload does not pick them up automatically.

---

## Making Changes

### Weekly schedule (most common edit)
Edit the relevant `_modules/week-XX.md` file. Each file follows this pattern:

```markdown
---
title: Week N
---

Sep 5
: **Lecture N**{: .label} Lecture Title
  : [Slides]({{ site.bcourses_course_url }}/files/folder/Lectures?preview=XXXXXX)
: _Device N_
```

Always use `{{ site.bcourses_course_url }}` for bCourses links — never hardcode the URL.

### Updating the bCourses course URL for a new term
Change one line in `_config.yml`:

```yaml
bcourses_course_url: &bcourses_course_url 'https://bcourses.berkeley.edu/courses/XXXXXXX'
```

All links across all 15 week files update automatically.

---

## Pushing to GitHub

```bash
git add -A
git commit -m "Brief description of change"
git push origin main
```

GitHub Pages rebuilds automatically after every push to `main`.
Deployment typically takes 1–3 minutes. Verify at:
https://ucb-bioe.github.io/fall26/

---

## What NOT to commit

- `_site/` — Jekyll build output (in `.gitignore`)
- `maintainer-local/` — local-only notes (in `.git/info/exclude`)
- Any file with hardcoded bCourses course IDs outside of `_config.yml`
