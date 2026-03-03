# Scratch

The app uses a modular architecture with clear separation of concerns.

This paragraph is stable context that both sides agree on and will not change. It provides enough buffer for git to detect separate conflict regions.

## Database

We store data in SQLite with a simple schema.

The database layer is well-tested with comprehensive integration tests covering all CRUD operations and edge cases around concurrent access.

## Networking

All API calls go through a centralized HTTP client.

The networking stack has been stable for months and handles retries, timeouts, and certificate pinning correctly across all supported platforms.

## Notes

This document tracks our architectural decisions.
