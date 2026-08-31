# Product names

Perplexity reused "Computer" until the words stopped distinguishing products. This page is a naming table, then a short file on each surface. Dates below are when the *named product* was announced or said to ship, not when an internal prototype existed.

## At a glance

| Name | What public text says it is | Where it runs | Models, as described | First public date |
| --- | --- | --- | --- | --- |
| **Search / answer engine** | Cited answers to questions | Perplexity cloud | Perplexity Sonar and successors | Core product, pre-2026 |
| **Comet** | Chromium AI browser with an in-browser assistant | User's desktop/mobile browser | Perplexity assistant in the browser | 9 Jul 2025 Max launch; later free |
| **Computer** | Cloud multi-model agent that plans workflows and runs them in an isolated environment | Perplexity cloud sandbox | At launch: Opus 4.6 core, plus named specialists. Later pages say 15+ / 20 / 20+ | 25 Feb 2026 |
| **Personal Computer** | Always-on Mac (later Windows) agent that uses local files and native apps *and* cloud Computer | User's Mac, recommended Mac mini; Windows product page exists | Cloud Computer's multi-model roster, plus local file/app access | Waitlist 12 Mar 2026; Max Mac rollout 16 Apr 2026 |
| **Portable Computer** | Local-first agent: local model + local harness on NVIDIA hardware, optional cloud advisor | Linux on DGX Spark at launch; RTX 24GB+ in the briefing; Windows promised | Qwen 3.8 27B, PPLX 27B; Nemotron 3.5 Lightning "coming soon" | 25 Aug 2026 |
| **Agent API** | Developer HTTP API for multi-model agents with tools and presets | `POST https://api.perplexity.ai/v1/agent` | OpenAI, Anthropic, Google, xAI, others, plus Sonar | Documented 2026; Sonar chat completions retire 27 Sep 2026 |
| **Search API / Search as Code / `pplx` CLI** | Ranked web results and snippets, plus an agents-first SDK | Perplexity search infra | Not an LLM product | Separate from Computer |

None of these is the Portable Computer apt package, and none of the public `perplexityai` GitHub repos *is* Computer. See [Official GitHub](#official-github-what-is-and-is-not-computer).

## Computer (cloud)

Company, [Introducing Perplexity Computer](https://www.perplexity.ai/hub/blog/introducing-perplexity-computer), 25 Feb 2026 (page itself Cloudflare-blocked here; quotes from search index plus Ars Technica, 25 Feb 2026):

- "a general-purpose digital worker"
- "a system that creates and executes entire workflows, capable of running for hours or even months"
- available to Max at launch, Enterprise Max "soon"

Launch model list, same post, restated by Ars Technica:

- **Claude Opus 4.6** as "core reasoning engine"
- **Gemini** for deep research / creating sub-agents
- **Nano Banana** for images
- **Veo 3.1** for video
- **Grok** for speed on lightweight tasks
- **ChatGPT 5.2** for "long-context recall and wide search"
- "model agnostic harness" so that list can change

Company, same era: "Every task runs in an isolated compute environment with access to a real filesystem, a real browser, and real tool integrations."

**Conflict on how many models.** Starter notes said "~19." Public pages do not agree on one integer:

- Feb launch post names the six above, and says the harness is model-agnostic.
- [Everything is Computer](https://www.perplexity.ai/hub/blog/everything-is-computer) (Ask 2026, March): "an orchestration harness of 20 frontier models" (search index).
- THE NEXT WEB, 12 Mar 2026: "orchestrate 20 frontier models."
- Portable Computer product page, Aug 2026: "15+ cloud models."
- Deep Research product page: "20+ models."
- Personal Computer for Windows product page: "15+ models."

There is no public, dated roster of 19 or 20 model IDs. Do not treat "~19" as a measured fact. Treat "multi-model, Opus-class reasoner at the center at launch, later marketed as 15+ or 20+" as what the pages support.

Ars Technica (independent, 25 Feb 2026) placed Computer against OpenClaw and Claude Cowork: cloud-hosted, curated integrations, not a local agent with unverified plugins.

Availability later widened. Independent writeups in mid-2026 say Computer moved onto Pro as well as Max (for example a 13 Mar 2026 changelog cited by secondary blogs). I did not load the live Computer product page from this environment. Local-vs-cloud *credits* for Computer remain a Max/Enterprise story in most coverage. See [marketing.md](marketing.md).

## Personal Computer

This is not Portable Computer. Nate Kupp said so out loud.

### Announcement

THE NEXT WEB, 12 Mar 2026, reporting Ask 2026:

- Personal Computer is software on a user-supplied Mac mini, merging local files, apps, and sessions with cloud Computer.
- Max, $200/month, Mac-only at launch, waitlist.
- Sensitive actions need approval, full audit trail, kill switch.
- Aravind Srinivas: "A traditional operating system takes instructions; an AI operating system takes objectives."

Company, [Everything is Computer](https://www.perplexity.ai/hub/blog/everything-is-computer) (search index): "a Personal Computer that can merge your local files with Perplexity Computer and work 24/7," "connected to your local apps and Perplexity's secure servers," "a digital proxy for you."

Ars Technica (March 2026 URL, independent) described early access by invite, running on a Mac mini, local files and apps, remote control "from any device, anywhere," and the same safeguard list.

Starter notes said "Mar 2026." That is the *announcement and waitlist*, not the Max Mac ship date.

### Ship dates

Company, [Personal Computer Is Here](https://www.perplexity.ai/hub/blog/personal-computer-is-here), dated 16 Apr 2026 in related-post lists:

- "beginning the rollout"
- "brings the multi-model orchestration of Computer to your machine"
- local files, native applications, connectors, and the web
- Mac mini as the 24/7 host
- Max subscribers; waitlist prioritized
- example: press both Command keys in Notes, ask it to do a to-do list across local files, iMessage, email, connected apps, and the web

Independent (Ry Walker research page, citing Digital Trends): general availability to paid Pro and Max Mac users on 7 May 2026. I could not load the Digital Trends article (CloudFront 403). Treat 7 May as independently reported, not company-primary.

### Windows

A company product page exists: [Personal Computer for Windows](https://www.perplexity.ai/hub/products/computer-for-windows) (search index, 26 Aug 2026): "Orchestrate agents across 15+ models," "runs on your machine," Outlook named, "Rolling out to Pro and Max subscribers in the new Perplexity app for Windows."

That is Personal Computer, not Portable Computer. Portable Computer's Windows date is a separate promise (September 2026 in the Kupp briefing).

### Hybrid routing, June 2026

See [architecture.md](architecture.md#june-versus-august). The June post is about Personal Computer gaining a local/cloud *router*, announced with Intel, "coming in July." It is not the August Portable Computer loop.

## Portable Computer

Company, [Introducing Portable Computer](https://www.perplexity.ai/hub/blog/introducing-portable-computer-for-local-first-ai), 25 Aug 2026 (search index; full page Cloudflare-blocked here) plus the research post that did load:

- "a version of Perplexity Computer that runs entirely on a local machine"
- built with NVIDIA, first on DGX Spark, RTX PCs "soon"
- private data stays local; on-device work does not consume credits
- local model may escalate to cloud when the user authorizes it
- Qwen 3.8 27B or PPLX 27B; Nemotron 3.5 Lightning coming
- "The orchestrator, planner, tool router, scheduler, durable task queue, and local search index all run on device"
- Pro and Max on DGX Spark in the launch post; press briefing also names Enterprise Pro and Enterprise Max
- Linux first, Windows "coming soon"
- DGX Spark: Grace Blackwell GB10, 20-core Arm CPU, NVIDIA GPU, 128 GB unified memory
- "one-click setup via the Perplexity app"
- apt instructions on the product page (see [marketing.md](marketing.md)); **this repo did not download that package**

The Verge, 25 Aug 2026 (independent, short): "Unlike the computer-controlling AI tool Perplexity launched earlier this year, the Portable Computer feature runs AI models fully locally." That sentence treats original Computer as "computer-controlling" and Portable as local-model. It is a naming convenience, not a teardown.

Kupp, The New Stack, 25 Aug 2026:

> Despite the similar name, Portable Computer isn't Personal Computer, Perplexity's Mac and Windows application for working with local files and native apps. Portable Computer runs the model and harness locally, but "we're not doing computer use at this point."

That is the cleanest public distinction. Personal Computer is computer-use adjacent (native apps, Notes, iMessage). Portable Computer is local inference plus sandboxed tools plus connectors, not GUI control of the user's desktop.

## Comet

Company, [Introducing Comet](https://www.perplexity.ai/hub/blog/introducing-comet), 9 Jul 2025: an AI-native browser, Max-first.

Later company posts: Comet free worldwide; Comet Enterprise 17 Mar 2026.

Comet is a browser with an assistant that acts in the user's tabs and sessions. Computer is a long-running workflow engine in a cloud sandbox. Personal Computer is a desktop agent with local files and apps. Portable Computer is a local-model harness on NVIDIA boxes. Mixing Comet "agent mode" with any of the Computer products is how the names get mashed.

## Search, Sonar, Agent API

These are developer and search surfaces. They are not Portable Computer.

Company docs, fetched 26 Aug 2026:

- [Search API](https://docs.perplexity.ai/docs/search/quickstart): ranked web results as structured data. Use when you want hits, not a synthesized answer.
- [Agent API](https://docs.perplexity.ai/docs/agent-api/quickstart): `POST https://api.perplexity.ai/v1/agent` (OpenAI-style `/v1/responses` alias). Multi-provider models, tools (web search, fetch URL, sandbox, MCP, finance, people search), presets `fast` / `low` / `medium` / `high` / `xhigh`.
- Sonar Chat Completions: still up, retire **27 Sep 2026**. Official forum post by andrewmadson-pplx, 13 Aug 2026: "Sonar endpoints are fully available today and retire on September 27, in 45 days." Docs banner: "Sonar Chat Completions is now Agent API. Sonar will be supported until September 27, 2026."
- [Search as Code](https://research.perplexity.ai/articles/rethinking-search-as-code-generation), 1 Jun 2026: Computer-side search architecture. Portable Computer's research post says the local harness uses that interface. The public Search SDK ([docs](https://docs.perplexity.ai/docs/search-sdk/overview), [perplexityai/perplexity-search-sdk](https://github.com/perplexityai/perplexity-search-sdk)) is the externalized version for other agents.

A cloud Computer task that "invokes hundreds or even thousands of retrieval operations" (Search as Code article) is a Computer/search fact. It is not evidence about the 27B local loop.

## Official GitHub: what is and is not Computer

Org: [github.com/perplexityai](https://github.com/perplexityai). 48 public repos as of 26 Aug 2026. There is no `computer`, `portable-computer`, or harness source dump.

Repos people will trip over:

| Repo | What the README says | Computer? |
| --- | --- | --- |
| [search_evals](https://github.com/perplexityai/search_evals) | Runner for BrowseComp, DeepSearchQA, HLE, WideSearch against Agent API and rivals | Eval harness for *search APIs*, not Computer |
| [wandr](https://github.com/perplexityai/wandr) | Wide-and-deep research benchmark, Harbor tasks, arXiv:2608.14747 | Benchmark. Relay agent is generic Harbor glue |
| [perplexity-cli](https://github.com/perplexityai/perplexity-cli) | `pplx search web` / content fetch. JSON to stdout. Not a chat client | Search CLI for humans and coding agents |
| [perplexity-search-sdk](https://github.com/perplexityai/perplexity-search-sdk) | Python Search as Code SDK | Search primitives, not the Computer app |
| [modelcontextprotocol](https://github.com/perplexityai/modelcontextprotocol) | Official MCP server for the API platform | API MCP. Portable Computer's research post says they *avoided* putting full MCP schemas in the local harness |
| [numbat](https://github.com/perplexityai/numbat) | Endpoint visibility into third-party coding agents (Claude, Codex, Cursor, …) | Observes other agents. Not Computer |
| [bumblebee](https://github.com/perplexityai/bumblebee) | Supply-chain scanner for developer endpoints | Unrelated |
| [pplx-kernels](https://github.com/perplexityai/pplx-kernels) | Deprecated MoE GPU kernels; points at pplx-garden | Cluster inference, not the Spark app |
| [pplx-garden](https://github.com/perplexityai/pplx-garden) | fabric-lib RDMA, tokenizer, trillion-param / EFA writeups | Datacenter inference research |
| [api-cookbook](https://github.com/perplexityai/api-cookbook), [perplexity-py](https://github.com/perplexityai/perplexity-py), [pplx-rs](https://github.com/perplexityai/pplx-rs), [ai-sdk](https://github.com/perplexityai/ai-sdk) | API clients and examples | API, not Computer |

The Local Knowledge Work Bench is promised as a future open-source eval. It is not in this org today.

## Timeline

| Date | Event | Kind |
| --- | --- | --- |
| 9 Jul 2025 | Comet launched to Max | Company |
| 25 Feb 2026 | Computer launched to Max | Company |
| 12 Mar 2026 | Ask 2026: Personal Computer waitlist, Computer for Enterprise, finance tools, APIs | Independent (TNW); company "Everything is Computer" |
| 16 Apr 2026 | Personal Computer Max rollout on Mac | Company |
| 7 May 2026 | Personal Computer said to go to all paid Mac users | Independent |
| 1 Jun 2026 | Search as Code research article | Company |
| ~3 Jun 2026 | Hybrid local-server orchestrator for Personal Computer, with Intel, local inference "coming in July" | Company |
| 13 Aug 2026 | Sonar API retirement announced for 27 Sep 2026 | Company (forum + docs) |
| 25 Aug 2026 | Portable Computer + local-first research post + Local Knowledge Work Bench chart | Company |
