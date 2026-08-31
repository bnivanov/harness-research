# Harness research

Living public-source notes on how Perplexity Computer, Personal Computer, and Portable Computer are *said* to run.

This is a research notebook, not a product page and not a reconstruction. Every material claim is cited. Company text is labeled separately from press briefings and other independent reporting. Where public pages disagree, the disagreement is recorded instead of being averaged away.

## Hard limits

These notes use only public material: Perplexity research and hub posts, product pages, docs, official GitHub READMEs, NVIDIA's local-AI blog, official tweets, and reputable coverage.

They do **not**:

- download, install, unpack, decompile, disassemble, or reverse-engineer the Portable Computer apt package, desktop app, or any closed binary
- clone private repositories
- invent internals that the public text does not state

The Portable Computer install path `packages.perplexity.ai` is cited from Perplexity's product page. The package itself was not fetched.

## How to read a claim

| Label | Meaning |
| --- | --- |
| **Company** | Perplexity (or NVIDIA restating the launch) said this in a primary page. |
| **Briefing** | A named Perplexity or NVIDIA employee said this to the press. Independent reporting of a company claim, not a third-party measurement. |
| **Independent** | Reporter, analyst, or open-source README speaking for themselves. |
| **Conflict** | Two public sources do not agree. |

Benchmark numbers in these notes are Perplexity's own evaluations unless marked otherwise. Nobody outside the company has published a replication of the Local Knowledge Work Bench.

## Files

| File | What it is |
| --- | --- |
| [architecture.md](architecture.md) | Claimed Portable Computer loop: orchestrator, model, sandbox, skills, connectors, cloud advisor. |
| [products.md](products.md) | Computer vs Personal Computer vs Portable Computer vs Comet vs search / Agent API, so the names stay distinct. |
| [marketing.md](marketing.md) | What they are selling, who can install it, hardware bar, quotes, the Pi/Hermes comparison. |
| [sources.md](sources.md) | Annotated bibliography with URLs and dates. |
| [open-questions.md](open-questions.md) | What public text still does not answer. |

## Snapshot of what public text actually supports

Recovered with citations, as of 26 Aug 2026:

- **Computer** (25 Feb 2026) is a cloud multi-model agent. At launch it was Max-only. The core reasoner was named as Claude Opus 4.6, with other named models for research, media, speed, and long context.
- **Personal Computer** was announced at Ask 2026 (12 Mar 2026 waitlist), rolled out to Max on Mac on 16 Apr 2026, and is a Mac-local always-on agent that uses local files and apps *plus* cloud Computer. It is software on the user's Mac, not a Perplexity-sold box. Nate Kupp later said Portable Computer is not doing computer-use.
- **Portable Computer** (25 Aug 2026) is a local-first Linux agent on NVIDIA DGX Spark, with RTX 24GB+ also described in the launch briefing. Windows is promised. macOS is not on the current roadmap. It is bundled for Pro / Max / Enterprise subscribers. Local inference is described as having no per-token charge.
- The Aug 2026 research post describes a **deterministic orchestrator** (not an LLM) that maintains the loop, a local model that proposes actions, an always-on OS sandbox that disables tools if missing, on-demand skills, connectors recast as compact CLIs, and a user-gated cloud **advisor** that returns text only.
- That Aug loop is **not** the same description as the June 2026 "hybrid local-server inference orchestrator," which was framed as a compact local model that *automatically* routes work between device and cloud.
- Perplexity says it will open-source the **Local Knowledge Work Bench**, not the harness. On that internal bench, on a DGX Spark with three trials per 53 tasks: Computer + PPLX 27B 85.4%, Computer + Qwen 3.8 27B 82.6%, Pi + Qwen 77.6%, Hermes + Qwen 74.0%.
- Official `perplexityai` GitHub has search evals, inference kernels, a search CLI, and endpoint agent telemetry. It does not publish Computer or Portable Computer.

Still unknown, and listed in [open-questions.md](open-questions.md): the actual core tool list, sandbox implementation, whether "browser use" on the product page contradicts Kupp's "not doing computer use," the precise credit rules for local vs cloud steps, and whether BYO inference is a shipping control or a briefing remark.

## Method

Fetched 26 Aug 2026. Several `perplexity.ai/hub` product and older blog URLs returned Cloudflare interstitial pages from this environment. Where that happened, claims are taken from (a) the 25 Aug research post, which did load, (b) search-index excerpts of the official pages, and (c) press that quotes those pages. Search-index excerpts of official pages are still company text, but they are second-hand copies of it.

Pi and Hermes are the comparison harnesses Perplexity named. Their public READMEs were read. Their source was not mined for an exploit or a private fork.
