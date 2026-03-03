# My Document

The deployment strategy uses Kubernetes with blue-green deployments.

We deploy every two weeks on Friday afternoons after the team standup.

## Rollback Plan

If something goes wrong, we perform an instant rollback using the previous ReplicaSet.
