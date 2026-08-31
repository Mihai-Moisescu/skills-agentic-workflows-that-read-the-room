---
name: update-github-info

on:
  schedule: daily
  workflow_dispatch:

permissions:
  contents: read

tools:
  edit:
  web-fetch:

network:
  allowed:
    - defaults
    - github.blog
    - github.com
    - awesome-copilot.github.com

safe-outputs:
  create-pull-request:
    title-prefix: "[github-info] "
    labels: [automation]
---

# Update GitHub Info

Keep [site/content/github-info.md](../../site/content/github-info.md) current with the latest GitHub Blog and Changelog news, following Mona's editorial guidance.

## Steps

1. Read [notes/mona-notes.md](../../notes/mona-notes.md) for Mona's editorial preferences.
2. Fetch `https://github.blog/latest/` to review the latest GitHub Blog posts.
3. Fetch `https://github.blog/changelog/` to review the latest Changelog entries.
4. Fetch `https://awesome-copilot.github.com/workflows/` to review notable Awesome Copilot workflows.
5. Update `site/content/github-info.md` to reflect noteworthy recent stories from these sources, following Mona's notes:
   - Keep summaries short and practical.
   - Prefer updates that help developers learn GitHub faster.
   - Mention the source (GitHub Blog, GitHub Changelog, or Awesome Copilot) for each update.
6. Open a pull request with the changes so Mona can review them before they go live. Do not push directly to the default branch.
