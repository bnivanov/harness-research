# What they are selling

Portable Computer is sold as a packaged local agent, not as a model download. The pitch in company posts and in the 24 Aug 2026 (Monday) press briefing is: you already own (or will buy) NVIDIA hardware; they ship the harness, inference, sandbox, and connectors so you do not have to wire Ollama to a pile of MCP servers; local steps are not metered in credits; cloud is opt-in.

That is a product claim. The hardware bill is real. The credit claim is company plus briefing. Nobody public has published a metering trace.

## The sentence they want repeated

Company, Portable Computer launch post, 25 Aug 2026 (search index):

> Portable Computer lets users run Perplexity Computer entirely on device, analyzing data, synthesizing files, and running complex workflows. Private data stays local and on-device work doesn't consume credits.

Company, research post, 25 Aug 2026:

> local models carry no inference fee: the system is private and cost-effective by construction.

NVIDIA local-AI blog, 25 Aug 2026: local workflows "don't count towards token limits."

VentureBeat, 25 Aug 2026, Kupp demo: the on-screen credit tally "is just parked at zero, because all of this is happening on the device."

What "on-device work" excludes is the interesting part. Search, connectors, and advisor calls leave the machine and, in the briefing, consume credits. Computerworld quotes the announcement: customers "are only charged if the system is explicitly told to move compute to the cloud for more advanced research and reasoning." Whether a Gmail CLI call is "compute" or a separate connector quota is [unanswered](open-questions.md).

## Who can install it

| Source | Tiers named | OS | Hardware |
| --- | --- | --- | --- |
| Company launch post (search index) | Pro and Max | Linux now, Windows "coming soon" | DGX Spark now, RTX PCs soon |
| Company product page (search index) | Pro and Max | apt on Linux | DGX Spark setup documented |
| Kupp briefing via VentureBeat and The New Stack | Pro, Max, Enterprise Pro, Enterprise Max | Linux now, Windows in September | DGX Spark, or Ubuntu ARM/x64 with RTX ≥ 24GB VRAM |
| NVIDIA blog | not specific | Windows "working on"; also DGX Station | DGX Spark now; GeForce RTX and RTX PRO "coming soon" |

Use the briefing for Enterprise inclusion and the September Windows date. Use the company post for Pro/Max and Linux-first. NVIDIA adding DGX Station is NVIDIA's sentence, not Perplexity's launch post.

macOS: The New Stack, Kupp. Portable Computer is not available on Mac. "For now" they are "very focused on Nvidia across DGX and RTX," while "considering other hardware." VentureBeat, same question: "We're very focused right now on Nvidia hardware." Apple silicon is absent from the Portable Computer roadmap in that briefing. Personal Computer remains the Mac product.

## Hardware bar

DGX Spark, company launch post: Grace Blackwell GB10, 20-core Arm CPU, NVIDIA GPU, 128 GB unified memory. The New Stack: about $4,800.

RTX floor, Kupp via VentureBeat: "Any RTX GPU with at least 24GB of VRAM, roughly a GeForce RTX 3090 or newer," described as "sort of the floor where we really want to make sure that we can deliver a great experience, but balance that with making it broadly available."

The New Stack: Ubuntu on ARM or x64 plus that RTX bar, or DGX OS on Spark. An RTX 3090 "currently costs well over $1,500."

**Conflict.** How-To Geek (independent, launch week) wrote that the official requirement is 32GB VRAM, with 3090 as the weakest card if you "restrict the context or swap in a quantized model." That contradicts Kupp's 24GB floor and The New Stack's 24GB/3090 line. This notebook keeps 24GB as the briefing number and flags 32GB as unverified secondary.

MarkTechPost (independent, 25 Aug 2026) published extra figures I could not confirm on a loaded official page: Qwen 3.8 27B as a 17.4 GB 3-bit download needing 32 GB RAM; Nemotron 3.5 Lightning as 4-bit, 19 GB, 36 GB RAM; 1 TB storage on Spark; clustering not shipped. Treat those as independently reported, possibly scraped from a product page I could not fetch. They are not in the research post.

NVIDIA's Nader (director of developer technology), VentureBeat briefing: connecting two Sparks can run larger open models; four can run GLM 5.2 or Nemotron Ultra. That is NVIDIA hardware talk. Kupp / MarkTechPost: Portable Computer supports one Spark at launch. Do not assume the app clusters.

## Install path (cited, not executed)

Product page search-index excerpt, 26 Aug 2026, [Portable Computer: Local-First AI](https://www.perplexity.ai/hub/products/portable-computer):

```
sudo curl -fsSL https://packages.perplexity.ai/perplexity.gpg -o /usr/share/keyrings/perplexity.gpg
echo "deb [signed-by=/usr/share/keyrings/perplexity.gpg] https://packages.perplexity.ai/deb stable main" | sudo tee /etc/apt/sources.list.d/perplexity.list
sudo apt-get update
sudo apt-get install perplexity
```

Company launch post also says one-click setup via the Perplexity app.

This notebook does not run those commands and does not fetch `perplexity.gpg` or the `.deb`.

## Subscription prices

Official Help Center, [Perplexity Max](https://www.perplexity.ai/help-center/en/articles/11680686-perplexity-max.html) (search index, 26 Aug 2026): Max is **$200/month or $2000/year**. Annual billing "only available for the web app version."

Pro is widely reported as $20/month. I did not get a clean load of the full plan-comparison Help Center article from this environment. CryptoBriefing (independent, 25 Aug 2026) restates Pro $20/month (~$17 annual) and Max $200/month (~$167 annual) as the Portable Computer software side. Hardware is extra.

Computer *credits* are a different meter from Portable local inference. Secondary pricing explainers in June 2026 say Max includes a monthly Computer credit pool (often 10,000) and that Pro's Computer access is not the same recurring pool. Those numbers move. Check the live Help Center ([How credits work](https://www.perplexity.ai/help-center/en/articles/13838041-how-credits-work-on-perplexity.html), [Which plan](https://www.perplexity.ai/help-center/en/articles/11187416-which-perplexity-subscription-plan-is-right-for-you.html)) before treating any credit integer as current. Portable Computer's local-zero-credit claim does not make Computer in the cloud free.

## Quotes

### Nate Kupp (Perplexity VP; titles vary by outlet)

VentureBeat: "vice president of engineering for infrastructure and enterprise." The New Stack: "vice president of Computer Enterprise and Infrastructure." Same person, briefing 24 Aug 2026.

On packaging:

> We've basically brought the exact same UI to a fully local app. This incorporates the entirety of the agent harness and inference and everything needed to do work locally.

On DIY local stacks:

> Historically it's just been really painful to bring up the local AI stack. With Portable Computer, we really focused on just making this a really straightforward experience where you can get up and running very quickly.

On vLLM / BYO (VentureBeat):

> The majority of the effort here has been at the agent harness level.

He said they use vLLM underneath, with an advanced mode for a user-supplied inference endpoint, and that they post-trained the Qwen and Nemotron models they ship.

On not assembling the stack yourself (The New Stack):

> You don't have to fiddle around with inference.

On computer-use (The New Stack):

> we're not doing computer use at this point

On Apple silicon / other GPUs (VentureBeat):

> We're very focused right now on Nvidia hardware.

The New Stack: "very focused on Nvidia across DGX and RTX," while considering other hardware.

On the VRAM floor (VentureBeat): 24GB as "sort of the floor..."

On the smaller model (The New Stack): they had to "revisit almost everything throughout the stack."

### Aravind Srinivas

Ask 2026, quoted by THE NEXT WEB, 12 Mar 2026, about Personal Computer / Computer, not Portable:

> A traditional operating system takes instructions; an AI operating system takes objectives.

I did not find a Portable Computer launch quote from Srinivas in the pages that loaded.

### Nader (NVIDIA, director of developer technology)

VentureBeat, 25 Aug 2026:

> Local AI reached an inflection point. For the longest time, it was hobbyists and enthusiasts, and they were running these quantized models that were quantized down to be super tiny... And while that's cool, it's not super practical. But all that changed with a lot of these new open source models that have come out that are super useful.

On agents and tokens:

> With agents, you want these agents always on if you can. You want the agents to really consume as many tokens as they can. What we're seeing is an insatiable demand for tokens, and that's something that makes local AI so great. ... You were not metered by the token. You were not paying for the token.

On Ollama versus a full agent stack: getting inference running on a Spark is a "smooth path" with Ollama; agentic work is "kind of like the ocean. The deeper you go, the deeper it gets."

### Beejoli Shah (Perplexity communications)

Computerworld, 25 Aug 2026, emailed statement. Escalation requires a settings toggle *and* per-action approval. Local document content cannot self-authorize. "Escalation is only allowed once, not across the remainder of the task, or in future sessions." This is company, via comms, and stricter than the research post. See [architecture.md](architecture.md#cloud-advisor).

## The Pi / Hermes shot

This is the chart Perplexity posted and the research post titled "Scores on the Local Knowledge Work Bench." Tweet: [x.com/perplexity_ai/status/2092321896721432824](https://x.com/perplexity_ai/status/2092321896721432824), 25 Aug 2026. Same numbers in the research post.

Setup they disclose: 53 tasks, 3 trials per task, 159 rollouts per condition, NVIDIA DGX Spark, 95% confidence whiskers. PPLX 27B is their post-train. Categories (company table):

| Category | Tasks | Share |
| --- | --- | --- |
| Deep research | 20 | 37.7% |
| Data, finance, and procurement | 9 | 17.0% |
| Documents, presentations, and design | 7 | 13.2% |
| Engineering, IT, and incidents | 5 | 9.4% |
| Contracts, evidence, and compliance | 5 | 9.4% |
| Dashboards, software, and visualization | 4 | 7.5% |
| People, projects, and meetings | 3 | 5.7% |

Headline scores (company):

| Condition | Score | Tokens / task | Wall time / task |
| --- | --- | --- | --- |
| Computer + PPLX 27B | 85.4% | 678k | 250 s (estimated) |
| Computer + Qwen 3.8 27B | 82.6% | 520k | 218 s |
| Pi + Qwen 3.8 27B | 77.6% | 681k | 176 s |
| Hermes + Qwen 3.8 27B | 74.0% | 634k | 292 s |

Pi is fastest on this bench. Computer is most accurate and, with base Qwen, stingiest on tokens. Post-training buys 2.8 points and spends more tokens.

What they are actually claiming: a harness built for a 27B, plus a post-train on that harness, beats two popular *general* harnesses on *their* knowledge-work mix, on *their* hardware, with *their* search stack on the research subset. VentureBeat, independent, notes the impressive numbers "come from the company's own evaluations" and that compact models still "trail the frontier meaningfully on hard reasoning tasks."

They say they will open-source the bench, not the harness. Until that ships, these bars are a company chart.

Comparison targets, public identity (independent READMEs, 26 Aug 2026):

- **Pi**: [earendil-works/pi](https://github.com/earendil-works/pi), "Pi Agent Harness," coding-agent CLI plus `pi-agent-core`. Runs as the launching user by default.
- **Hermes**: [NousResearch/hermes-agent](https://github.com/NousResearch/hermes-agent), Nous Research. Optional sandbox backends, skills, memory, messaging gateways. Brave is what Perplexity says they used as Hermes/Pi search.

Perplexity's research post calls both "popular open-source general-purpose harnesses" that "are not optimized for the capabilities of on-device models." That is the shot. It is also an admission that they compared against tools designed for a different job (often cloud-frontier coding agents) rather than against other local-27B knowledge-work harnesses, if any exist.

## What they will not sell as open source

Company, research post: open-source the Local Knowledge Work Bench. Technical report on training "soon." No promise to open the orchestrator, sandbox, connector CLIs, PPLX weights, or the apt package.

Kupp via VentureBeat on Ollama: different layer. They are selling the agent harness on top of vLLM, not a new inference engine.

## Related NVIDIA lines that are not this product

NVIDIA's 25 Aug local-AI post is a roundup. Qwen 3.8 27B on RTX via llama.cpp/Ollama, Nemotron 3.5 Lightning, clustering Sparks, NemoClaw, Hermes-on-NVIDIA are neighboring local-AI news. They are not Portable Computer. The Perplexity subsection is the only part that describes this app.
