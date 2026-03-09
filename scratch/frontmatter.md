---
# ─── Identity & Discovery ───────────────────────────────────────────────────
title: "My Document Title"
slug: my-document-title

# Inline arrays
tags: [writing, tutorial, markdown]
categories: [guides, reference]
aliases: [/old-url, /another-old-url]

# Block arrays
redirects:
  - /very/long/old/path/that/would/make/inline/ugly
  - /another/long/old/path
  - /yet/another/one

# Empty array
empty_tags: []

# ─── Authorship ─────────────────────────────────────────────────────────────
# Nested object
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
date: 2026-03-08
updated: 2026-03-08
publishedAt: 2026-03-08T09:00:00Z

# ─── Publishing State ────────────────────────────────────────────────────────
draft: false
published: true
status: published # draft | review | published | archived

# ─── Display & Layout ────────────────────────────────────────────────────────
layout: post
image: /images/cover.png
thumbnail: /images/thumb.png
featured: true
order: 3
weight: 10
sidebar: true
toc: true
reading_time: 5

# ─── SEO (nested) ────────────────────────────────────────────────────────────
seo:
  title: "Custom SEO Title"
  description: "Override description for search engines."
  canonical: "https://example.com/my-document-title"
  noindex: false

# ─── Open Graph (nested) ─────────────────────────────────────────────────────
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
body_prefix: |
  This line is first.
  This line is second.

  This line follows a blank line.

# Literal strip (|-) — newlines preserved, trailing newline trimmed
redirect_message: |-
  This page has moved.
  Please update your bookmarks.

# Folded block (>) — newlines become spaces, trailing newline kept
excerpt: >
  This is a long excerpt that wraps across
  multiple lines in the source file but will
  be collapsed into a single paragraph when parsed.

# Folded strip (>-) — newlines become spaces, trailing newline trimmed
description: >-
  A long description that stays as one clean
  sentence without a trailing newline at the end.

# Inline escaped newlines — less common but valid
subtitle: "Line one.\nLine two.\nLine three."
---

# Frontmatter

This document contains front matter. Front matter is a convention that is shared by many systems that use markdown documents to add additional properties to the document.

| Syntax    | Description |   Test Text |
| :-------- | :---------: | ----------: |
| Header    |    Title    | Here's this |
| Paragraph |    Text     |    And more |

I can make changes without the frontmater being nuked.
