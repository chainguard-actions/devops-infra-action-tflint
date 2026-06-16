<!-- markdownlint-disable -->

# Hardening Report: devops-infra--action-tflint/v1.0.2

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `1`

Action **devops-infra--action-tflint/v1.0.2** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The action.yml uses a Docker image reference with a mutable tag (`v1.0.2`) instead of an immutable SHA digest. This means the image could be replaced with a different (potentially malicious) version without changing the action reference. The failing reference is: `image: docker://devopsinfra/action-tflint:v1.0.2`. It should be pinned to a SHA digest, e.g. `image: docker://devopsinfra/action-tflint@sha256:<64-hex-char-digest>`.

Locations:

- `action.yml:22`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Replaced the mutable Docker image tag reference `docker://devopsinfra/action-tflint:v1.0.2` with the immutable SHA256 digest `docker://devopsinfra/action-tflint@sha256:f6273f4a076bfb7e979337272bb3e025521690c1ae90f8e3ae29c841816bb733 # v1.0.2` in actions/hardened/devops-infra--action-tflint/v1.0.2/action.yml.

