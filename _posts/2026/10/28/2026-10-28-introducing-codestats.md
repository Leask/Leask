---
layout: post
title: 'Introducing CodeStats'
author: Leask
date: '2026-10-28 21:42:37 -0400'
categories:
- Computers and Internet
tags:
- GitHub
- Open Source
- CodeStats
description: 'GitHub activity, coding time and AI usage in one self-hosted README card, with persistent caching and one-click Cloudflare deployment.'
image: '/assets/img/2026/10/2026-10-28-codestats.png'
---

![CodeStats showing GitHub activity, language statistics, coding time and AI usage]({{ '/assets/img/2026/10/2026-10-28-codestats.png' | relative_url }})

Introducing [CodeStats](https://github.com/Leask/CodeStats/)! 😄

Many people add [GitHub Readme Stats](https://github.com/anuraghazra/github-readme-stats) or [GitHub Stats Extended](https://github.com/stats-organization/github-stats-extended) to their [GitHub](https://github.com/) profile or project README. Of course, these numbers don’t prove how skilled someone is. They’re just for fun, and a nice way to show what you’ve been working on.

I liked the idea, but I kept running into slow refreshes, failed requests and GitHub API limits. My statistics were also scattered across several cards. I wanted one place to bring them together, with a persistent cache that could keep the last successful result visible when an upstream service was having a bad day.

While waiting for [Codex](https://chatgpt.com/codex) to finish an assignment, I started building my own version.

CodeStats combines data from **GitHub, [WakaTime](https://wakatime.com/), Codex, [OpenRouter](https://openrouter.ai/) and [Anthropic API](https://platform.claude.com/docs/en/manage-claude/usage-cost-api)** in one card. You can enable whichever sources you use. GitHub activity, coding hours and AI token usage each keep their own meaning and reporting period.

The language table puts GitHub code bytes and WakaTime coding hours side by side. Related languages are grouped together, so it’s easier to see both the code in your repositories and where you actually spend your time. GitHub public and private statistics are supported according to the permissions of your token. Each source has its own cache and refresh time, and a failed refresh keeps its previous successful snapshot available.

It’s built for [Cloudflare Workers](https://developers.cloudflare.com/workers/) with persistent storage and [one-click deployment](https://deploy.workers.cloudflare.com/?url=https%3A%2F%2Fgithub.com%2FLeask%2FCodeStats). You can also run it directly on Node.js. The [card builder](https://codestats.leask.workers.dev/build) lets you choose sources, appearance and layout, then copy a Markdown snippet into your README. The default card has a transparent background, and credentials stay in your service configuration.

Thanks to GitHub Readme Stats and GitHub Stats Extended for the inspiration. CodeStats has its own collection, rendering and caching engine, and fetches statistics directly from the providers.

The project is [open source on GitHub](https://github.com/Leask/CodeStats/). If you’d like your own card, [deploy a copy](https://deploy.workers.cloudflare.com/?url=https%3A%2F%2Fgithub.com%2FLeask%2FCodeStats) and give it a try. 😄
