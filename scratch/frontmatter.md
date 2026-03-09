---
title: My Document Title
slug: my-document-title
tags: [writing, tutorial, markdown]
categories: [guides, reference]
aliases: [/old-url, /another-old-url]
redirects: [/very/long/old/path/that/would/make/inline/ugly, /another/long/old/path, /yet/another/one]
empty_tags: []
author:
  name: John Doe
  email: john@example.com
  url: https://johndoe.com
  avatar: /images/authors/john.png

# Array of objects
authors:
  - name: Jane Smith
    email: jane@example.com
    role: lead
  - name: John Doe
    email: john@example.com
    role: contributor

# ─── Dates ──────────────────────────────────────────────────────────────────
date: 2026-03-08 00:00:00 +0000
updated: 2026-03-08 00:00:00 +0000
publishedAt: 2026-03-08 09:00:00 +0000
draft: false
published: true
status: published
layout: post
image: /images/cover.png
thumbnail: /images/thumb.png
featured: true
order: 3
weight: 10
sidebar: true
toc: true
reading_time: 5
seo:
  title: "Custom SEO Title"
  description: "Override description for search engines."
  canonical: "https://example.com/my-document-title"
  noindex: false

# ─── Open Graph (nested) ─────────────────────────────────────────────────────
description: A long description that stays as one clean sentence without a trailing newline at the end.
og:
  title: "Social Share Title"
  image: /images/og-cover.png
  type: article

# ─── Related content (array of objects) ─────────────────────────────────────
related:
  - slug: another-post
    title: "Another Post"
  - slug: yet-another
    title: "Yet Another"

# ─── Multi-line strings ──────────────────────────────────────────────────────

# Literal block (|) — newlines preserved, trailing newline kept
body_prefix: This line is first.
This line is second.

This line follows a blank line.

redirect_message: This page has moved. Please update your bookmarks.
excerpt: This is a long excerpt that wraps across multiple lines in the source file but will be collapsed into a single paragraph when parsed.

subtitle: Line one. Line two. Line three.
---

# Frontmatter

This document contains front matter. Front matter is a convention that is shared by many systems that use markdown documents to add additional properties to the document.

| Syntax    | Description |   Test Text |
| :-------- | :---------: | ----------: |
| Header    |    Title    | Here's this |
| Paragraph |     Text    |    And more |

I can make changes without the frontmater being nuked.