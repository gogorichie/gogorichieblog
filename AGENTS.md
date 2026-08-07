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

## Repository Structure

- `content/` contains blog posts and pages.
- `themes/` contains the Hugo theme.
- Site configuration controls navigation, taxonomy, and publishing behavior.
- Do not modify generated output unless the repository explicitly tracks it.

## Branch Naming

Create a draft branch for each new blog post using its start date and title:

```text
draft/YYYY-MM-DD/post-title
```

For example:

```text
draft/2026-08-07/backlog-bankruptcy
```

Use the post title in lowercase, with words separated by hyphens. Keep one draft
branch per post and avoid unrelated changes.

For a focused non-post update, use the same format with a short descriptive title:

```text
draft/YYYY-MM-DD/update-title
```

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
