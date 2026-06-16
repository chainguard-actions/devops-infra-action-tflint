<!-- markdownlint-disable -->

# Hardening Report: devops-infra--action-tflint/v1.0.3

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `1`

Action **devops-infra--action-tflint/v1.0.3** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The action.yml `runs.image:` field references `docker://devopsinfra/action-tflint:v1.0.3`, which uses a mutable tag (`v1.0.3`) instead of an immutable SHA digest. If the tag is moved or the registry is compromised, a different (potentially malicious) image could be pulled silently. The image reference should be pinned to a full SHA256 digest, e.g. `docker://devopsinfra/action-tflint@sha256:<64-hex-char-digest> # v1.0.3`.

Locations:

- `action.yml:23`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Pinned the Docker image reference in action.yml from `docker://devopsinfra/action-tflint:v1.0.3` to `docker://devopsinfra/action-tflint@sha256:6ff7a17eefe1dc74d8b8ac8dd8d9a7632debaa119d1c1df5468a78fe02a0d473 # v1.0.3`. The mutable tag was replaced with the immutable SHA256 digest resolved via the Docker Registry API, with the original tag preserved as a comment for readability.

