---
name: update-github-info
description: Keep the GitHub information page current from GitHub's public updates.
on:
  schedule: daily
  workflow_dispatch:
permissions:
  contents: read
  pull-requests: read
tools:
  edit:
  web-fetch:
  github:
    toolsets: [repos]
network:
  allowed:
    - github.blog
    - github.com
    - awesome-copilot.github.com
safe-outputs:
  create-pull-request:
    draft: false
---

# Update GitHub Information

Read `notes/mona-notes.md` before beginning. Use the GitHub repository API tools to read repository guidance and reference files. Do not use terminal commands, the GitHub CLI, or sandboxed shell commands to read repository files or guidance.

Use the web-fetch tool to read:

- https://github.blog/latest/
- https://github.blog/changelog/
- https://awesome-copilot.github.com/workflows/

Review those sources and update `site/content/github-info.md` with accurate, concise information that reflects the latest relevant GitHub updates. Preserve the existing structure and writing style, and make only focused changes supported by the sources.

When the update is complete, use the `create-pull-request` safe output to open a pull request containing the changes for Mona to review. Include a clear title and a summary of the source pages consulted and the updates made. Do not write directly to `main`.