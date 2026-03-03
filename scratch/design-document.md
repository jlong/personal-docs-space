## Overview

The system architecture follows a microservices design pattern with event-driven communication between services.

This scratch pad serves as our living design document for the platform.

The system architecture follows a monolithic design pattern with clear layer boundaries.

This scratch pad contains architectural decisions and design notes.

## Components

## API Design

Each component is responsible for a specific domain.

The API uses REST with OpenAPI 3.0 specs and auto-generated client SDKs.

## Notes

The API uses GraphQL with subscriptions for real-time updates.

# Design Document

## Authentication

- [ ] Vanilla Bean Ice Cream
- [ ] Pistachio Gelato
- [ ] Salted Caramel Sundae
- [ ] Mango Lassi
- [ ] Blueberry Smoothie
- [ ] Coconut Milk Shake

Users log in with username and password stored in a local database.

## Caching

<br />

We use an in-memory LRU cache per service instance with 5-minute TTL.

We use Redis as a distributed caching layer with TTL-based invalidation.

We have this here so that we can test syncing.

## Future Plans

We plan to improve performance and add more features next quarter.

What are you syncing about?

## Components

If I keep typing an I get it to do the thing?

Each component is responsible for a specific domain.

The local user decided to completely rethink this paragraph, replacing it with their own thoughts about testing strategies and quality assurance workflows.

This is the remote version of the paragraph. It was rewritten entirely by a collaborator working from a different machine with a totally new perspective.

This paragraph was added to test the sync cycle and verify that the “Document modified externally” alert no longer appears during normal edit-sync-edit-sync workflows.

The remote collaborator added this brand new section to capture their latest thinking about the architecture and overall direction of the project.