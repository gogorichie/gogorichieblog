# Agent Instructions — gogorichieblog

## Purpose

This repository is Richard Lewis’s personal blog, written since 2001.
Create and update posts in his established voice: personal, practical,
conversational, and grounded in real experience.

## Content Guidelines

- Write Hugo-compatible Markdown.
- Review two or three related existing posts before drafting or revising content.
- Match the front matter and file naming conventions used by similar posts.
- Preserve Richard’s first-person voice and straightforward tone.
- Use clear headings, short paragraphs, and practical examples.
- Do not invent personal experiences, technical results, quotes, or sources.
- Keep technical explanations accurate but accessible.

## Required Post Header

Every new blog post must begin as a Hugo draft using this front-matter template.
Replace the title and date values for the new post; keep `draft: true`.

```yaml
---
title: "Post Title"
date: "YYYY-MM-DDTHH:MM:SS-05:00"
draft: true
---
```

Do not change a post to `draft: false` unless explicitly asked to prepare it
for publication.

## Repository Structure

- `content/` contains blog posts and pages.
- `themes/` contains the Hugo theme.
- Site configuration controls navigation, taxonomy, and publishing behavior.
- Do not modify generated output unless the repository explicitly tracks it.

## Branch Naming

Create draft branches for new blog posts using the date they are started and a
kebab-case version of the post title:

```text
draft/YYYY-MM-DD/post-title
```

For example:

```text
draft/2026-08-07/backlog-bankruptcy
```

Use one draft branch per post or focused update. Keep the branch scoped to
that work and avoid unrelated changes.

## Pull Requests

Every repository change must be made through a pull request.

- Never commit directly to `main`.
- Create or update a focused draft branch, then open a pull request targeting
  `main`.
- Keep the pull request scoped to one post or focused update.
- Do not merge a pull request unless explicitly asked.

## Authoring Workflow

1. Find two or three related existing posts for tone, structure, and front matter.
2. Draft or update the Markdown source under `content/`.
3. Verify internal links, image paths, code fences, headings, and front matter.
4. Build the site locally before considering the work complete.

## Validation

Run the appropriate Hugo build command before finishing:

```bash
hugo --minify
```

Resolve build errors and avoid unrelated formatting or theme changes.

## Guardrails

- Do not publish, deploy, or change Netlify or Azure settings unless explicitly asked.
- Do not rewrite unrelated posts.
- Preserve existing URLs and filenames when editing published content.
- Prefer small, focused commits and explain what changed.
