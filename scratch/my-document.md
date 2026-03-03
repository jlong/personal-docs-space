# My Document

The deployment strategy uses Docker Compose on a dedicated VPS with zero-downtime deploys.

We deploy every two weeks on Friday afternoons after the team standup.

## Rollback Plan

If something goes wrong, we redeploy the previous tagged container image from our registry.
