# Scratch

## Overview

This scratch pad serves as our living design document for the platform.

## API Design

The API uses REST with OpenAPI 3.0 specs and auto-generated client SDKs.

## Authentication

Users log in with username and password stored in a local database.

## Caching

We use an in-memory LRU cache per service instance with 5-minute TTL.

## Future Plans

We plan to improve performance and add more features next quarter.
