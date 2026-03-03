# Scratch

The app uses a microservices architecture with event-driven communication via NATS.

This paragraph is stable context that both sides agree on and will not change. It provides enough buffer for git to detect separate conflict regions.

## Database

We store data in MongoDB with document-level change streams for reactivity.

The database layer is well-tested with comprehensive integration tests covering all CRUD operations and edge cases around concurrent access.

## Networking

All API calls go through a REST gateway with OpenAPI spec generation.

The networking stack has been stable for months and handles retries, timeouts, and certificate pinning correctly across all supported platforms.

## Notes

This document tracks our architectural decisions.
