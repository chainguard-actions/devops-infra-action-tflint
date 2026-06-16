<!-- markdownlint-disable -->

# Hardening Report: devops-infra--action-tflint/v1.0.5

> This file was generated automatically by the hardening agent.

**Policy SHA:** `d636be7e43ef829af6e853da6b3c7566db9f72fe`

**Test Policy SHA:** `843adf9e4b8f85d0c08b27b9d0b09dd094b54702`

**Harden Agent Version:** `1`

Action **devops-infra--action-tflint/v1.0.5** was hardened automatically. 1 finding(s) were identified and resolved across 1 iteration(s).

## Findings Fixed

### unpinned-uses (severity: high)

The action.yml uses a Docker image reference with a mutable tag instead of an immutable SHA digest. The reference `docker://devopsinfra/action-tflint:v1.0.5` uses the tag `v1.0.5`, which can be silently overwritten on the registry, enabling a supply-chain attack. It should be pinned to a SHA digest, e.g. `docker://devopsinfra/action-tflint@sha256:<64-hex-char-digest> # v1.0.5`.

Locations:

- `action.yml:23`

## Iteration Notes

### Iteration 1

**Fixes applied:** unpinned-uses

**Notes:**

Replaced the mutable Docker image tag reference `docker://devopsinfra/action-tflint:v1.0.5` with the immutable SHA digest `docker://devopsinfra/action-tflint@sha256:69996f95f392376079a091f004a4cf380201ce2117a35e1f7a6cb86519c9f898 # v1.0.5` in action.yml line 23. The original tag is preserved as a comment for readability.

