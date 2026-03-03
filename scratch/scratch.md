# Scratch

## Overview

This scratch pad serves as our living design document for the platform.

This scratch pad contains architectural decisions and design notes.

## API Design

The API uses REST with OpenAPI 3.0 specs and auto-generated client SDKs.

The API uses GraphQL with subscriptions for real-time updates.

## Authentication

Users log in with username and password stored in a local database.

## Caching

We use an in-memory LRU cache per service instance with 5-minute TTL.

We use Redis as a distributed caching layer with TTL-based invalidation.

## Future Plans

We plan to improve performance and add more features next quarter.