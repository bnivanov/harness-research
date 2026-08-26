# Open questions

Public text does not answer these. That is the point of the list. Do not fill the gaps with guesses from similar agents.

## The shipping binary

1. What is inside `apt-get install perplexity`? Package name aside, the product page does not list binaries, daemons, Python vs native, or whether the desktop UI is Electron. **Not to be answered by unpacking the package in this repo.**

2. Is the "one-click" Perplexity app installer the same payload as the apt repo?

3. Does the Linux app talk to `api.perplexity.ai`, and if so for what (auth, search, advisor, connectors, telemetry) when the user has disabled cloud?

## Orchestrator internals

4. What language is the deterministic orchestrator? The research post only says it is not an LLM.

5. Are "planner, tool router, scheduler, durable task queue, and local search index" (product page) separate processes, or marketing names for harness modules?

6. What is the local search index over? Files the user selects, the whole home directory, conversation history, skill docs?

7. How is a "durable task queue" persisted across reboots? SQLite, a local service, something else?

8. How does the June 2026 automatic local/cloud *router* relate to the August tool loop? Same code with a new policy? Different product? Abandoned?

## Tools, skills, connectors

9. What is the "small set of core tools"? File I/O, shell, Python, browser, something else? Unnamed.

10. Skill format. Files on disk? Prompt snippets? Agent-skills.io? Load/unload implementation?

11. Connector CLIs: do they call vendor APIs from the box (user OAuth locally), or Perplexity-hosted connectors? If hosted, local-first is local *inference*, not local *Gmail*.

12. Outlook and Google Calendar appear in the research post. Slack and Drive appear on the product page and in NVIDIA's blog. What actually ships on day one?

13. MCP: they say they converted "the most-used MCPs" to CLIs. Can a user still attach an MCP server? The research post reads like no, for context reasons. Not explicit.

## Sandbox

14. Implementation: OS primitives, container runtime, custom supervisor?

15. Policy: which paths are readable by default? Home? A workspace directory? Downloads?

16. Network: default-deny except connectors? Who allowlists?

17. "If the sandbox is unavailable, the harness disables itself." Disables the whole app, or only tool execution? Can chat-only still run?

18. Does fail-closed apply on Windows the same way, once Windows exists?

## Advisor / privacy

19. Research post: user may approve advisor calls "manually or automatically." Shah: explicit per-action plus a toggle, and "only allowed once" per task. Which is in the build?

20. What does the PII classifier actually flag, and can it be wrong in either direction? No evaluation published.

21. Product page lists "browser use" as a cloud escalation reason. Kupp says Portable is not doing computer-use. Is cloud browser-use a Computer sandbox browser, and local GUI control out of scope? Unstated.

22. Can an enterprise admin set a network-level or MDM policy that the local model cannot override? Computerworld's enterprise interviewees asked. Shah answered with in-app consent, not with a central policy object.

23. Shah: local document content cannot authorize escalation. Good. Is that enforced in the orchestrator, or is it a statement of intended UX?

## Models and inference

24. Will PPLX 27B weights be released, or only used inside the app?

25. Quantization of the shipped Qwen 3.8 27B. MarkTechPost says 3-bit / 17.4 GB. Not in the loaded research post.

26. Is Nemotron 3.5 Lightning in the picker a stock NVIDIA checkpoint, or a Perplexity post-train (NVIDIA blog and Kupp say they are working on a fine-tune)?

27. BYO model and BYO vLLM endpoint: briefing, not the research post. Is it a settings field in 1.0?

28. Context compaction algorithm. Summary model? Extractive? Does compaction run locally always?

29. Multimodal path for PDFs. Research post says pages and images go "directly to the model." Is Qwen 3.8 27B used as a VLM here, or is there a separate encoder?

## Metering and tiers

30. Exact credit rules for search, connectors, and advisor. Local inference is "zero." Everything else is fuzzy.

31. Launch post: Pro and Max. Briefing: also Enterprise Pro and Enterprise Max. Is Enterprise in the apt login on day one?

32. Does a Pro user on Portable Computer get the same advisor models as Max?

33. Windows date: "September" in the briefing, "coming soon" on the company post, NVIDIA also mentions DGX Station. Which train is real?

## Benchmarks

34. When does the Local Knowledge Work Bench actually ship, and with what license? Tasks are 37.7% deep research, which depends on web access. A local-only reimplementation will not match without Perplexity search.

35. BrowseComp comparison used Perplexity search for Computer and Brave for Pi/Hermes. How much of the 16.5 point gap is search quality vs harness?

36. ParseBench-100 layout scores are poor for everyone (Computer 16.2%). Is that a model limit or a harness limit?

37. Terminal Bench advisor cost is "estimated." Estimated how?

38. No independent replication. Until the bench is out, the 85.4 / 82.6 / 77.6 / 74.0 chart is a company chart.

## Cloud Computer, still underspecified

39. There is still no dated public roster that adds up to 19, 20, or 15+ models.

40. Isolated cloud environment: VM size, browser, filesystem, network egress, retention. Ars quotes "real filesystem, real browser, real tool integrations." That is the whole specification.

41. How Computer's sub-agent spawn relates to Portable's single local model loop. Kupp said they reused capabilities and changed the harness. Reused *which*?

## Personal Computer versus Portable Computer

42. Does Personal Computer on a Mac mini run any local weights today, or only local *access* with cloud inference? June promised local inference "in July." August's local-first writeup is about Portable on NVIDIA, not about Mac.

43. If both are installed, do they share connectors, memory, or a queue?

44. "Computer use" on Personal Computer: accessibility APIs, screenshots, synthetic input? Unspecified beyond native apps, Notes, iMessage, email.

## Adjacent surfaces that look like Computer and are not

45. Agent API sandbox tool vs Computer cloud sandbox vs Portable OS sandbox. Three products, word "sandbox" on all of them. No public statement that they share code.

46. `perplexity-cli` / Search SDK vs the Search as Code path inside Portable Computer. Same primitives, or a cousin API?

47. numbat observes Claude, Codex, Cursor. Does it observe Portable Computer? The coverage matrix is in that repo, not checked here beyond the README's "supported desktop, CLI, IDE, and gateway agents" line. Likely not, given Portable is closed.

## What would actually close questions

In rough order of evidence quality, without touching the binary:

1. The promised Local Knowledge Work Bench dump, with harness-free task definitions.
2. The promised training technical report.
3. A dated model roster and a dated connector list on a product page that loads.
4. Help Center article that states Portable credit rules in one table.
5. A Kupp or engineering talk with a real diagram of processes, not six nouns.
6. An independent Spark owner writing down what `ps` and network egress look like while idle, in local-only mode, and during an advisor call. That would be observational, not reverse engineering of the package, and it does not exist yet in the coverage above.
