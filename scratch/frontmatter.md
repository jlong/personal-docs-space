---
title: "Frontmatter Test Document"
description: "A short summary used in previews and SEO meta tags."
date: 2026-03-08

# Nested fields (YAML mappings)
author:
  name: John Doe
  email: john@example.com
  url: https://johndoe.com
  avatar: /images/authors/john.png

seo:
  title: "Custom SEO Title"
  description: "Override description for search engines."
  canonical: "https://example.com/my-document-title"
  noindex: false

og:
  title: "Social Share Title"
  image: /images/og-cover.png
  type: article

# Nested list of objects
authors:
  - name: Jane Smith
    email: jane@example.com
    role: lead
  - name: John Doe
    email: john@example.com
    role: contributor

related:
  - slug: another-post
    title: "Another Post"
  - slug: yet-another
    title: "Yet Another"

# Multi-line strings
# Literal block scalar (|) — preserves newlines exactly
body_prefix: |
  This line is first.
  This line is second.

  This line follows a blank line.

# Folded block scalar (>) — newlines become spaces (good for long prose)
excerpt: >
  This is a long excerpt that wraps across
  multiple lines in the source file but will
  be collapsed into a single paragraph when parsed.

# Literal with strip modifier (|-) — trims the final newline
redirect_message: |-
  This page has moved.
  Please update your bookmarks.

# Multi-line inline (quoted with \n) — less common but valid
subtitle: "Line one.\nLine two.\nLine three."
---

# Frontmatter

This document contains front matter. Front matter is a convention that is shared by many systems that use markdown documents to add additional properties to the document.

| Syntax    | Description |   Test Text |
| :-------- | :---------: | ----------: |
| Header    |    Title    | Here's this |
| Paragraph |    Text     |    And more |
