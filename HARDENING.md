<!-- markdownlint-disable -->

# Hardening Report: devops-infra--action-tflint/v1.0.1

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `1`

Action **devops-infra--action-tflint/v1.0.1** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The action.yml uses a Docker image reference with a mutable version tag instead of an immutable SHA digest. `image: docker://devopsinfra/action-tflint:v1.0.0` uses the tag `v1.0.0`, which can be silently overwritten to point to a different (potentially malicious) image. It should be pinned to a SHA digest, e.g. `image: docker://devopsinfra/action-tflint@sha256:<64-hex-char-digest> # v1.0.0`.

Locations:

- `action.yml:27`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned the Docker image reference in action.yml from the mutable tag `devopsinfra/action-tflint:v1.0.0` to the immutable digest `devopsinfra/action-tflint@sha256:f47b0c2df266d8877f96f1b1424197e1a630fc1749f99532ba32f6cf6a0fe799 # v1.0.0`. The tag is preserved as a comment for readability.

