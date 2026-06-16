<!-- markdownlint-disable -->

# Hardening Report: devops-infra--action-tflint/v1.0.4

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `1`

Action **devops-infra--action-tflint/v1.0.4** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The action.yml uses a Docker-based action (`runs.using: docker`) with `image: docker://devopsinfra/action-tflint:v1.0.4`. This references a mutable image tag (`v1.0.4`) rather than an immutable SHA digest (e.g., `docker://devopsinfra/action-tflint@sha256:<64-hex-char-digest>`). A mutable tag can be silently overwritten to point to a different (potentially malicious) image, enabling supply-chain attacks.

Locations:

- `action.yml:23`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Replaced the mutable Docker image tag `docker://devopsinfra/action-tflint:v1.0.4` with the immutable SHA256 digest `docker://devopsinfra/action-tflint@sha256:574c9e5302ba10759173e3b9f997b2201621528ec5c55cca2cce2847965881d1 # v1.0.4` in actions/hardened/devops-infra--action-tflint/v1.0.4/action.yml. The original tag is preserved as a comment for readability.

