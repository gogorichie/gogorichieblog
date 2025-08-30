# Richard Lewis' Personal Blog

This repository houses my personal blog where I share insights, experiences, and knowledge on DevOps, Azure, home automation, technology, and more. Built with Hugo and deployed to both Netlify and Azure Static Web Apps.

[![Netlify Status](https://api.netlify.com/api/v1/badges/39889879-51d5-498b-b921-9ad98fcb9734/deploy-status)](https://app.netlify.com/sites/gogorichie/deploys)
[![Azure Static Web Apps](https://github.com/gogorichie/gogorichieblog/actions/workflows/azure-static-web-apps-witty-sand-0f714bf10.yml/badge.svg)](https://github.com/gogorichie/gogorichieblog/actions/workflows/azure-static-web-apps-witty-sand-0f714bf10.yml)
[![Stale Management](https://github.com/gogorichie/gogorichieblog/actions/workflows/stale.yml/badge.svg)](https://github.com/gogorichie/gogorichieblog/actions/workflows/stale.yml)
[![Repository Size](https://img.shields.io/github/repo-size/gogorichie/gogorichieblog)](https://github.com/gogorichie/gogorichieblog)
[![Top Language](https://img.shields.io/github/languages/top/gogorichie/gogorichieblog)](https://github.com/gogorichie/gogorichieblog)
[![Last Commit](https://img.shields.io/github/last-commit/gogorichie/gogorichieblog)](https://github.com/gogorichie/gogorichieblog/commits)
[![Open Issues](https://img.shields.io/github/issues/gogorichie/gogorichieblog?color=important)](https://github.com/gogorichie/gogorichieblog/issues)
[![Open Pull Requests](https://img.shields.io/github/issues-pr/gogorichie/gogorichieblog?color=yellowgreen)](https://github.com/gogorichie/gogorichieblog/pulls)
[![Dependency Review](https://github.com/gogorichie/gogorichieblog/actions/workflows/dependency-review.yml/badge.svg)](https://github.com/gogorichie/gogorichieblog/actions/workflows/dependency-review.yml)

## 📋 About

This blog is built using [Hugo](https://gohugo.io/), a fast and modern static site generator, with the [Mainroad](https://github.com/vimux/mainroad) theme. The site is deployed to both Netlify and Azure Static Web Apps for redundancy and performance.

Visit the live site: [www.gogorichie.com](https://www.gogorichie.com/)


## 📝 Content Management

### Creating New Posts

```bash
hugo new blog/post-name.md
```

This will create a new markdown file with the proper front matter template.

### Post Front Matter

```yaml
---
title: "Your Post Title"
date: 2025-08-30T12:34:56-06:00
draft: false
tags: ["tag1", "tag2"]
---

Post content goes here...
```

## 🔄 Deployment

The site is automatically deployed when changes are pushed to the `main` branch:

- **Netlify**: Provides the primary hosting
- **Azure Static Web Apps**: Provides backup hosting

## 📁 Repository Structure

- `content/`: All blog post markdown files
- `static/`: Static assets like images and files
- `layouts/`: Custom layout templates
- `themes/mainroad/`: The Mainroad theme (submodule)
- `.github/workflows/`: GitHub Actions workflows

## �️ Tech Stack

- **Static Site Generator**: [Hugo](https://gohugo.io/)
- **Theme**: [Mainroad](https://github.com/vimux/mainroad)
- **Hosting**:
  - Primary: [Netlify](https://www.netlify.com/)
  - Secondary: [Azure Static Web Apps](https://azure.microsoft.com/en-us/services/app-service/static/)
- **CI/CD**: GitHub Actions
- **Content**: Markdown files

## �📜 License

This project is licensed under the Creative Commons Zero (CC0) license - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

As this is a personal blog, contributions are generally not accepted. However, if you spot any issues or have suggestions, feel free to open an issue.

## 🔧 Useful Commands

### Building for Production

```bash
hugo --minify


hugo new \blog\new_post.md