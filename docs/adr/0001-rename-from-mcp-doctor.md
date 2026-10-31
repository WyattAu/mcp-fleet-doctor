# ADR-0001: Rename from mcp-doctor to mcp-fleet-doctor

**Status:** Accepted
**Date:** 2026-10-31

## Context

The generic name `mcp-doctor` is taken by an unrelated and broader MCP
security scanner (scan/score/install across registries). The collision
splits search results and misattributes scope. This tool's scope is
narrow and different: auditing an OpenCode MCP fleet's configuration,
backend resolution, credential entitlement, and handshakes.

## Decision

Rename the repository to `mcp-fleet-doctor`. GitHub redirects the old
name. Crate names inside the workspace keep the old string until their
next breaking publish (none are published today; follow-up recorded).
Estate registry updated in the same sweep.

## Consequences

- Positive: unambiguous scope in the name; the audit niche stays
  defensible.
- Negative: old links rely on redirects; CI badges and bookmarks refresh
  lazily.
- Risks: stale references in estate docs; swept by the registry audit.

## Alternatives considered

| Alternative | Pros | Cons | Reason rejected |
|---|---|---|---|
| Keep the name, outbuild the scanner | no churn | confused discovery forever; the scanner owns the generic verb | brand on a contested name is a tax |
| Merge scope with the scanner | one tool | different trust model: fleet audit is local-first and config-driven | out of scope for this repo |
