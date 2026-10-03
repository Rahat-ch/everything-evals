# Free resources for learning LLM and AI evals

**Compiled:** 2026-10-03. **Audited:** 2026-10-03. Every linked resource was checked for an author who works in AI or is a researcher: 87 checked, none failed.

This is a reading list for a deep dive into evals: evaluating LLM apps and agents, error analysis, LLM-as-judge, statistics, benchmarks and their pitfalls, human labelling, online and offline evals, and safety evaluation. It was compiled with web search, and every link was fetched on 2026-10-03 to check that it resolves and is free to read or watch. Only four kinds of source made the cut: practitioners who have shipped eval systems, AI lab teams, peer-reviewed or widely cited research, and government or standards bodies. Vendor marketing, paywalled material and generic explainer channels were left out. Each entry has one line on what it is. Nothing here is summarised.

Each entry gives: **title (link)** · author or org · *why credible* · format · rough length · date.

---

## Start here

Read these in this order.

1. **[Your AI Product Needs Evals](https://hamel.dev/blog/posts/evals/)** (Hamel Husain). This is the shortest end-to-end picture of the eval loop for a real product.
2. **[A Field Guide to Rapidly Improving AI Products](https://hamel.dev/blog/posts/field-guide/)** (Hamel Husain). It makes the case for error analysis before metrics.
3. **[Using LLM-as-a-Judge For Evaluation: A Complete Guide](https://hamel.dev/blog/posts/llm-judge/)** (Hamel Husain). It shows how to build a judge and check it against a human expert.
4. **[Who Validates the Validators?](https://arxiv.org/abs/2404.12272)** (Shankar et al.). This is the research behind "criteria drift" and aligning judges with people.
5. **[A statistical approach to model evaluations](https://www.anthropic.com/research/statistical-approach-to-model-evals)** (Anthropic). It covers error bars, standard errors and paired comparisons for eval scores.
6. **[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)** (Anthropic). This is a lab's current view of how agent evals differ from single-turn evals.
7. **[CS336 Lecture 12: Evaluation](https://www.youtube.com/watch?v=x-R5l2HsXqM)** (Percy Liang, Stanford). It gives the benchmark and research side: what benchmarks measure and where they break.

---

## The catalogue

### 1. Foundations and methodology (6)

- **[Your AI Product Needs Evals](https://hamel.dev/blog/posts/evals/)** · Hamel Husain · *20+ years in ML at GitHub and Airbnb; his early code-understanding research was used by OpenAI; now runs eval consulting for product teams* · blog · ~16 min · 2024-03-29
- **[AI Evals: Everything You Need to Know (FAQ)](https://hamel.dev/blog/posts/evals-faq/)** · Hamel Husain and Shreya Shankar · *the two co-teach the AI Evals For Engineers & PMs course on Maven, which they say has taught 5,000+ engineers and PMs; Shankar's research is listed below* · blog (long FAQ) · ~18,000 words, ~75 min · first published 2025, current version 2026-09-21. The page advertises their paid course; the FAQ itself is free.
- **[Task-Specific LLM Evals that Do & Don't Work](https://eugeneyan.com/writing/evals/)** · Eugene Yan · *Principal Applied Scientist at Amazon 2020–2025, where he built LLM summarisation, translation and Q&A systems; now at Anthropic* · blog · ~30 min · 2024-03-31
- **[What We've Learned From A Year of Building with LLMs](https://applied-llms.org/)** · Eugene Yan, Bryan Bischof, Charles Frye, Hamel Husain, Jason Liu, Shreya Shankar · *six practitioners who built and shipped LLM products; first published by O'Reilly* · long essay (evals are one thread throughout) · ~60 min · 2024-06
- **[Successful language model evals](https://www.jasonwei.net/blog/evals)** · Jason Wei · *first author of the chain-of-thought prompting paper and of OpenAI's SimpleQA benchmark; now at Meta Superintelligence Labs* · blog · ~7 min · 2024-05-24
- **[LLM Evaluation Guidebook](https://huggingface.co/spaces/OpenEvals/evaluation-guidebook)** · Clémentine Fourrier and Hugging Face · *ran the Hugging Face Open LLM Leaderboard and co-built the `lighteval` library* · guide (many short chapters on benchmarks, human eval and LLM-as-judge) · ~43 pages in the [GitHub version](https://github.com/huggingface/evaluation-guidebook) · 2024-10, current version 2025-12

### 2. Error analysis and building evals for an app (4)

- **[A Field Guide to Rapidly Improving AI Products](https://hamel.dev/blog/posts/field-guide/)** · Hamel Husain · *see above* · blog · ~25 min · 2025-03-24
- **[An LLM-as-Judge Won't Save The Product—Fixing Your Process Will](https://eugeneyan.com/writing/eval-process/)** · Eugene Yan · *see above* · blog · ~5 min · 2025-04-20
- **[Do Automated Evals Work?](https://parlance-labs.com/blog/posts/auto-evals/)** · Antaripa Saha and Hamel Husain (Parlance Labs) · *an experiment comparing human-annotated traces with automated trace-review tools* · blog · ~9 min · 2026-07-11. This is a consultancy blog, but the post is a measured comparison, not a pitch. It names vendor tools as the objects being tested.
- **[There Are Only 6 RAG Evals](https://jxnl.co/writing/2025/05/19/there-are-only-6-rag-evals/)** · Jason Liu · *creator of the Instructor library; ran an AI consulting practice; now on the Codex team at OpenAI* · blog · ~8 min · 2025-05-19

### 3. LLM-as-judge and its calibration (6)

- **[Using LLM-as-a-Judge For Evaluation: A Complete Guide](https://hamel.dev/blog/posts/llm-judge/)** · Hamel Husain · *see above* · blog · ~30 min · 2024-10-29
- **[Evaluating the Effectiveness of LLM-Evaluators (aka LLM-as-Judge)](https://eugeneyan.com/writing/llm-evaluators/)** · Eugene Yan · *see above; it surveys about two dozen papers* · blog (literature review) · ~40 min · 2024-08-18
- **[Who Validates the Validators? Aligning LLM-Assisted Evaluation of LLM Outputs with Human Preferences](https://arxiv.org/abs/2404.12272)** · Shreya Shankar, J.D. Zamfirescu-Pereira, Björn Hartmann, Aditya Parameswaran, Ian Arawjo · *UC Berkeley EECS PhD research (EvalGen), published at UIST 2024; Shankar joins Carnegie Mellon as an assistant professor in 2027* · paper · 16 pp · 2024-04
- **[Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena](https://arxiv.org/abs/2306.05685)** · Lianmin Zheng et al. (LMSYS, UC Berkeley and others) · *the paper that named and measured position, verbosity and self-preference bias; NeurIPS 2023 Datasets and Benchmarks* · paper · 29 pp · 2023-06
- **[Large Language Models are not Fair Evaluators](https://arxiv.org/abs/2305.17926)** · Peiyi Wang et al. (Peking University and others) · *shows that swapping answer order flips judge verdicts, and proposes calibration fixes; ACL 2024* · paper · 11 pp · 2023-05
- **[Length-Controlled AlpacaEval: A Simple Way to Debias Automatic Evaluators](https://arxiv.org/abs/2404.04475)** · Yann Dubois, Balázs Galambosi, Percy Liang, Tatsunori Hashimoto (Stanford) · *the AlpacaEval maintainers correcting their own judge for length bias; COLM 2024* · paper · 12 pp · 2024-04

### 4. Statistics and rigour (5)

- **[A statistical approach to model evaluations](https://www.anthropic.com/research/statistical-approach-to-model-evals)** and the paper **[Adding Error Bars to Evals](https://arxiv.org/abs/2411.00640)** · Evan Miller, Anthropic · *Anthropic research; Miller is long known for his A/B-testing statistics writing and tools* · blog and paper · ~8 min and 14 pp · 2024-11
- **[Quantifying Variance in Evaluation Benchmarks](https://arxiv.org/abs/2406.10229)** · Lovish Madaan et al., Meta · *Meta researchers measuring seed-to-seed and checkpoint variance across common benchmarks* · paper · 23 pp · 2024-06
- **[Position: Don't Use the CLT in LLM Evals With Fewer Than a Few Hundred Datapoints](https://arxiv.org/abs/2503.01747)** · Sam Bowyer, Laurence Aitchison, Desi R. Ivanova · *ICML 2025 spotlight position paper; directly about small eval sets* · paper · 42 pp (much of it figures) · 2025-03
- **[Signal and Noise: A Framework for Reducing Uncertainty in Language Model Evaluation](https://arxiv.org/abs/2508.13144)** · David Heineman et al., Allen Institute for AI (Ai2) · *the team that builds and evaluates the open OLMo models* · paper · 35 pp · 2025-08
- **[With Little Power Comes Great Responsibility](https://aclanthology.org/2020.emnlp-main.745/)** · Dallas Card, Peter Henderson, Urvashi Khandelwal, Robin Jia, Kyle Mahowald, Dan Jurafsky · *EMNLP 2020; the standard NLP reference on statistical power and sample size* · paper · 12 pp · 2020

### 5. Benchmarks, leaderboards and their pitfalls (7)

- **[Holistic Evaluation of Language Models (HELM)](https://arxiv.org/abs/2211.09110)** · Percy Liang et al., Stanford CRFM · *the multi-metric, multi-scenario benchmark framework; published in TMLR* · paper · 162 pp (the main text is far shorter) · 2022-11
- **[Chatbot Arena: An Open Platform for Evaluating LLMs by Human Preference](https://arxiv.org/abs/2403.04132)** · Wei-Lin Chiang et al., LMSYS / UC Berkeley · *the team that ran the crowd-sourced pairwise leaderboard; ICML 2024* · paper · 29 pp · 2024-03
- **[The Leaderboard Illusion](https://arxiv.org/abs/2504.20879)** · Shivalika Singh et al., Cohere Labs with university co-authors · *a data-driven critique of how Chatbot Arena rankings can be gamed* · paper · 68 pp · 2025-04
- **[Lessons from the Trenches on Reproducible Evaluation of Language Models](https://arxiv.org/abs/2405.14782)** · Stella Biderman, Hailey Schoelkopf et al., EleutherAI · *the maintainers of lm-evaluation-harness, the most widely used open benchmark runner* · paper · 31 pp · 2024-05
- **[NLP Evaluation in trouble: On the Need to Measure LLM Data Contamination for each Benchmark](https://arxiv.org/abs/2310.18018)** · Oscar Sainz et al. · *position paper on contamination from NLP researchers; EMNLP Findings* · paper · 12 pp · 2023-10
- **[A Careful Examination of Large Language Model Performance on Grade School Arithmetic (GSM1k)](https://arxiv.org/abs/2405.00332)** · Hugh Zhang et al., Scale AI · *built a fresh GSM8K-style test set to measure overfitting directly; NeurIPS 2024 Datasets and Benchmarks* · paper · 45 pp · 2024-05
- **[Mapping global dynamics of benchmark creation and saturation in artificial intelligence](https://arxiv.org/abs/2203.04592)** · Simon Ott et al. · *peer-reviewed in Nature Communications (2022); measures how fast benchmarks saturate across AI* · paper · 27 pp · 2022-03

### 6. Agent evals (5)

- **[Demystifying evals for AI agents](https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents)** · Mikaela Grace, Jeremy Hadfield, Rodrigo Olivares, Jiri De Jonghe (Anthropic Engineering) · *written by the lab that builds and evaluates Claude's agent abilities* · blog · ~25 min · 2026-01-09
- **[AI Agents That Matter](https://arxiv.org/abs/2407.01502)** · Sayash Kapoor, Benedikt Stroebl, Zachary Siegel, Nitya Nadgir, Arvind Narayanan, Princeton · *Princeton CITP; Kapoor and Narayanan later built the Holistic Agent Leaderboard* · paper · 33 pp · 2024-07
- **[Establishing Best Practices for Building Rigorous Agentic Benchmarks](https://arxiv.org/abs/2507.02825)** · Yuxuan Zhu et al. (25 authors from academia and industry) · *audits popular agent benchmarks for broken tasks and graders, and proposes a checklist* · paper · 39 pp · 2025-07
- **[τ-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains](https://arxiv.org/abs/2406.12045)** · Shunyu Yao, Noah Shinn, Pedram Razavi, Karthik Narasimhan (Sierra) · *introduced the pass^k reliability metric; Yao is the lead author of ReAct* · paper · 50 pp · 2024-06
- **[Measuring AI Ability to Complete Long Software Tasks](https://arxiv.org/abs/2503.14499)** · Thomas Kwa et al., METR · *METR runs pre-deployment evaluations of frontier models; NeurIPS 2025. A shorter [blog version](https://metr.org/blog/2025-03-19-measuring-ai-ability-to-complete-long-tasks/) exists* · paper · 45 pp · 2025-03

### 7. Human labelling and agreement (3)

- **[Inter-Coder Agreement for Computational Linguistics](https://aclanthology.org/J08-4004/)** · Ron Artstein and Massimo Poesio · *Computational Linguistics journal survey; the standard NLP reference on kappa and alpha* · paper · 42 pp · 2008
- **[Best practices for the human evaluation of automatically generated text](https://aclanthology.org/W19-8643/)** · Chris van der Lee, Albert Gatt, Emiel van Miltenburg, Sander Wubben, Emiel Krahmer · *a peer-reviewed survey of human-eval practice in text generation (INLG 2019)* · paper · 14 pp · 2019
- **[All That's 'Human' Is Not Gold: Evaluating Human Evaluation of Generated Text](https://aclanthology.org/2021.acl-long.565/)** · Elizabeth Clark et al., University of Washington · *shows untrained raters cannot tell GPT-3 text from human text; ACL 2021* · paper · 15 pp · 2021

The guidebook's [human evaluation chapters](https://github.com/huggingface/evaluation-guidebook/tree/main/contents/human-evaluation) and Hamel Husain's judge guide (section 3) also cover labelling in practice.

### 8. Online evals and experiments (2)

- **[Practical Guide to Controlled Experiments on the Web: Listen to Your Customers not to the HiPPO](https://exp-platform.com/Documents/GuideControlledExperiments.pdf)** · Ron Kohavi, Randal Henne, Dan Sommerfield (Microsoft) · *Kohavi led Microsoft's experimentation platform; KDD 2007, author's copy* · paper (PDF) · 9 pp · 2007
- **[How Not To Run an A/B Test](https://www.evanmiller.org/how-not-to-run-an-ab-test.html)** · Evan Miller · *same author as Anthropic's error-bars paper; a classic on the danger of peeking at results early* · blog · ~7 min · 2010-04-18

Neither is about LLMs. They are here because online LLM evals are A/B tests, and these are the standard free references. The Hamel/Shankar FAQ and the OpenAI guide below cover the LLM side of production monitoring.

### 9. Frameworks and tools (docs) (5)

- **[Inspect](https://inspect.aisi.org.uk/)** · UK AI Security Institute (with Meridian Labs) · *the framework the UK government institute uses for its own model testing; lead developer JJ Allaire, founder of RStudio/Posit* · docs (tutorial, tasks, solvers, scorers, [agents](https://inspect.aisi.org.uk/agents.html)) · many pages · first released 2024-05, actively maintained. The companion [inspect_evals](https://github.com/UKGovernmentBEIS/inspect_evals) repo holds ready-made benchmark implementations.
- **[lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness)** · EleutherAI · *the runner behind the Hugging Face Open LLM Leaderboard (retired March 2025) and hundreds of papers* · repo and docs · README plus docs folder · 2020 onward, actively maintained
- **[HELM framework](https://crfm.stanford.edu/helm/)** ([code](https://github.com/stanford-crfm/helm)) · Stanford CRFM · *the open framework behind the HELM paper and leaderboards* · site, repo and docs · 2021 onward, actively maintained
- **[OpenAI Evals](https://github.com/openai/evals)** · OpenAI · *OpenAI's open-source framework and registry of evals* · repo · README plus docs folder · 2023 onward. This is separate from OpenAI's hosted Evals product, which is shutting down (see Notes).
- **[simple-evals](https://github.com/openai/simple-evals)** · OpenAI · *the reference code OpenAI published behind its benchmark numbers* · repo · short · 2024-04. Since July 2025 it gets no new model results. It still hosts HealthBench, BrowseComp and SimpleQA.

### 10. Lab guidance (3)

- **[Challenges in evaluating AI systems](https://www.anthropic.com/research/evaluating-ai-systems)** · Anthropic · *the lab's account of its own problems running MMLU, BBQ, red-teaming and third-party evals* · blog · ~14 min · 2023-10-04
- **[Define success criteria and build evaluations](https://platform.claude.com/docs/en/test-and-evaluate/develop-tests)** · Anthropic (Claude docs) · *official guidance from the model provider* · docs · ~20 min plus code examples · living doc, no date shown
- **[Evaluation best practices](https://developers.openai.com/api/docs/guides/evaluation-best-practices)** · OpenAI · *official guidance from the model provider* · docs · ~18 min · living doc, no date shown

Other lab work sits by topic: Anthropic's statistics post (section 4), Anthropic's agent post (section 6), Meta's variance paper (section 4), and Google DeepMind's extreme-risk paper (section 11).

### 11. Safety, capability and government frameworks (5)

- **[Model evaluation for extreme risks](https://arxiv.org/abs/2305.15324)** · Toby Shevlane et al., Google DeepMind with co-authors from other labs and universities · *the framing paper for dangerous-capability evals* · paper · 20 pp · 2023-05
- **[Early lessons from evaluating frontier AI systems](https://www.aisi.gov.uk/blog/early-lessons-from-evaluating-frontier-ai-systems)** · UK AI Security Institute · *the government body that tests frontier models before release* · blog · ~20 min · 2024-10-24
- **[We Need A 'Science of Evals'](https://www.apolloresearch.ai/science/we-need-a-science-of-evals)** · Marius Hobbhahn and Jérémy Scheurer, Apollo Research · *Hobbhahn is CEO and co-founder of Apollo, an independent evaluations organisation that tests frontier models for deceptive behaviour* · blog · ~13 min · 2024-01-22
- **[AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)** ([AI RMF 1.0 PDF](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf), [Generative AI Profile, NIST AI 600-1](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.600-1.pdf)) · NIST · *US standards body* · standard (PDFs) · 48 pp and 64 pp · 2023-01 and 2024-07
- **[Practices for Automated Benchmark Evaluations of Language Models (NIST AI 800-2, initial public draft)](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.800-2.ipd.pdf)** · NIST Center for AI Standards and Innovation (Drew Keller, Ryan Steed, Tony Wang, Stevie Bergman, Peter Cihon) ([announcement](https://www.nist.gov/news-events/news/2026/01/towards-best-practices-automated-benchmark-evaluations)) · *US standards body; covers measurement targets, running evals, and reporting with uncertainty* · draft standard (PDF) · 39 pp · 2026-01. Still a draft: comments closed 2026-03-31, and no final version was listed on 2026-10-03.

### 12. Courses and lectures (3)

- **[Stanford CS336, Lecture 12: Evaluation](https://www.youtube.com/watch?v=x-R5l2HsXqM)** · Percy Liang, Stanford (Stanford Online channel) · *director of Stanford CRFM and lead of HELM* · recorded lecture plus [executable lecture notes](https://cs336.stanford.edu/spring2025/) · 80 min · 2025 (uploaded 2025-06-04). A [Spring 2026 version](https://www.youtube.com/watch?v=JpAxdTWQJxM) (78 min, 2026-05-19) also exists.
- **[Instrumenting & Evaluating LLMs](https://parlance-labs.com/education/fine_tuning_course/workshop_3.html)** ([video](https://www.youtube.com/watch?v=SnbGD677_u0)) · Hamel Husain and Dan Becker with guest speakers · *a workshop from their free "Mastering LLMs" course* · recorded workshop, chapters and transcript · 153 min · 2024-07. Some guest segments demo commercial tools.
- **[AI Evals For Engineers: Course Preview (Chapters 1–3 of 8)](https://www.youtube.com/watch?v=OJItZndMUII)** · Hamel Husain and Shreya Shankar · *see above* · recorded lectures · 64 min · 2025-05-17. **The full course is paid (Maven). Only these first three chapters are free.**

### 13. Talks (3)

- **[Lessons From A Year Building With LLMs](https://www.youtube.com/watch?v=qBHfQT3YtyY)** · Yan, Bischof, Frye, Husain, Liu, Shankar (AI Engineer channel) · *closing keynote, AI Engineer World's Fair 2024* · talk · 35 min · 2024-07-19
- **[How to Construct Domain Specific LLM Evaluation Systems](https://www.youtube.com/watch?v=eLXF0VojuSs)** · Hamel Husain and Emil Sedgh (AI Engineer channel) · *a case study of evals built for a shipped real-estate assistant* · talk · 18 min · 2024-09-19
- **[A Deep Dive on LLM Evaluation](https://www.youtube.com/watch?v=IsZVCnViwhk)** ([page](https://parlance-labs.com/education/evals/schoelkopf.html)) · Hailey Schoelkopf, then a research scientist at EleutherAI · *maintainer of lm-evaluation-harness* · talk · 49 min · 2024-07-10

---

## Notes

### Excluded on purpose

- **Paid material.** The full "AI Evals For Engineers & PMs" course (Maven) is paid, so only its free preview is listed. Chip Huyen's *AI Engineering* (O'Reilly) has strong evaluation chapters but is a paid book. Ron Kohavi's book *Trustworthy Online Controlled Experiments* is paid, and the free copies that turn up in search (Scribd) are unauthorised, so they are excluded.
- **Vendor-led material.** The AI Engineer World's Fair "Evals" track playlist was hosted by an eval-tool vendor, and most of its talks are from tool companies, so the playlist was not listed. The same goes for the DeepLearning.AI short courses on evals, which are co-made with tool vendors.
- **Podcasts.** Hamel Husain and Shreya Shankar's interview on Lenny's Podcast (2025-09-25) was left out. It is a podcast interview by a host who doesn't work in AI, not a talk at a conference or lab venue, and it largely repeats their FAQ and course preview.
- **OpenAI's hosted Evals product docs.** The [Evals platform guide](https://developers.openai.com/api/docs/guides/evals) documents a product that goes read-only on 2026-10-31 and shuts down on 2026-11-30, according to OpenAI's own best-practices page. The best-practices guide is still listed.
- **Anthropic's "Evals for AI Agents" webinar** (2026-07-14) needs registration, so it was left out. The Anthropic agent-evals blog post covers the same ground.
- **Lilian Weng** (ex-OpenAI VP of Research and Safety) has no core evals piece. Her [Extrinsic Hallucinations in LLMs](https://lilianweng.github.io/posts/2024-07-07-hallucination/) (2024-07) has a section on hallucination benchmarks.
- **Simon Willison**'s blog notes on evals were left out. He builds LLM tools, but by his own description he isn't employed in AI or a researcher, which is this list's bar.
- **YouTube explainers** of the Anthropic agent-evals post by third-party channels were skipped. Read the original instead.

### Cut for length (all verified and free; worth a look later)

- LLM-as-judge: [G-Eval](https://arxiv.org/abs/2303.16634) (2023), [Replacing Judges with Juries](https://arxiv.org/abs/2404.18796) (Cohere, 2024), [Judging the Judges](https://arxiv.org/abs/2406.12624) (2024), [A Survey on LLM-as-a-Judge](https://arxiv.org/abs/2411.15594) (2024, 64 pp).
- Statistics: [The Hitchhiker's Guide to Testing Statistical Significance in NLP](https://aclanthology.org/P18-1128/) (ACL 2018).
- Benchmarks and contamination: [Proving Test Set Contamination in Black Box Language Models](https://arxiv.org/abs/2310.17623) (2023), [Benchmark Data Contamination of LLMs: A Survey](https://arxiv.org/abs/2406.04244) (2024), [AI and the Everything in the Whole Wide World Benchmark](https://arxiv.org/abs/2111.15366) (Raji et al., 2021), [What Will it Take to Fix Benchmarking in NLU?](https://arxiv.org/abs/2104.02145) (Bowman and Dahl, 2021), [Dynabench](https://arxiv.org/abs/2104.14337) (2021), [OLMES](https://arxiv.org/abs/2406.08446) (Ai2, 2024), and Hugging Face's [What's going on with the Open LLM Leaderboard?](https://huggingface.co/blog/open-llm-leaderboard-mmlu) (2023-06-23, on one benchmark giving three different scores).
- Agents: [SWE-bench](https://arxiv.org/abs/2310.06770) (ICLR 2024), the [Holistic Agent Leaderboard](https://hal.cs.princeton.edu/) and [its paper](https://arxiv.org/abs/2510.11977) (Princeton, 2025).
- Safety: [Evaluating Frontier Models for Dangerous Capabilities](https://arxiv.org/abs/2403.13793) (Google DeepMind, 2024, 81 pp), [Holistic Safety and Responsibility Evaluations of Advanced AI Models](https://arxiv.org/abs/2404.14068) (Google DeepMind, 2024).
- Production: [SPADE: Synthesizing Data Quality Assertions for LLM Pipelines](https://arxiv.org/abs/2401.03038) (Shankar et al., 2024).
- Methodology: [Repairing the Cracked Foundation](https://arxiv.org/abs/2202.06935) (Gehrmann, Clark, Sellam, Google, 2022).
- Practitioner posts: Eugene Yan's [Product Evals in Three Simple Steps](https://eugeneyan.com/writing/product-evals/) (2025-11-23) and [Evaluating Long-Context Question & Answer Systems](https://eugeneyan.com/writing/qa-evals/) (2025-06-22); Hamel Husain's ["It's Hard to Eval" Is a Product Smell](https://hamel.dev/blog/posts/eval-smell/) (2026-06-29); Jason Liu's [Systematically Improving Your RAG](https://jxnl.co/writing/2024/05/22/systematically-improving-your-rag/) (2024-05-22).
- Talks: JJ Allaire, [Inspect, an OSS Framework for LLM Evals](https://www.youtube.com/watch?v=kNaZU9bz-UM) (46 min, 2024-07); Google DeepMind, [Agentic Evaluations at Scale, For Everybody](https://www.youtube.com/watch?v=Ubwb6NzegyA) (AI Engineer, 20 min, 2026-05-25).

### Could not verify

- **OpenAI's [Introducing SWE-bench Verified](https://openai.com/index/introducing-swe-bench-verified/)** (2024-08) returned HTTP 403 to automated fetches, so it was not listed. It is a good case study of fixing a broken benchmark, and it may load fine in a normal browser. The same applies to OpenAI's Preparedness Framework page.
- **The Hugging Face guidebook Space** resolves, but its content renders in the browser and could not be read by the fetcher. The [GitHub version](https://github.com/huggingface/evaluation-guidebook) was read instead. Its README says the Space holds the newer version.
- **Undated pages.** The Claude docs and OpenAI docs pages show no publish date. They are living documents, checked on 2026-10-03.
- **Credentials** come from the authors' own about pages (Husain, Shankar, Yan, Liu, Wei, Hobbhahn), arXiv author lists, and org pages. Venue claims come from arXiv comments or the proceedings URL. Three venue details are not in the arXiv comments and were confirmed from the proceedings: UIST 2024 for Shankar et al. (https://dl.acm.org/doi/10.1145/3654777.3676450), ACL 2024 for Wang et al. (https://aclanthology.org/2024.acl-long.511/), and ICML 2024 for Chatbot Arena (https://proceedings.mlr.press/v235/chiang24b.html).

### Overlaps

- Evan Miller's Anthropic blog post and the "Adding Error Bars" paper are the same work, at two lengths.
- The applied-llms.org essay and the AI Engineer 2024 keynote come from the same six authors and say much the same things.
- The Hamel/Shankar FAQ, the course preview and Hamel's blog posts all share one method: error analysis, then binary judges validated against a human. Read one in depth and skim the rest.
- Hamel's judge guide, Eugene Yan's LLM-evaluators review and the Shankar et al. paper cover the same question from practice, from the literature and from research.
- Schoelkopf's talk, the "Lessons from the Trenches" paper and lm-evaluation-harness all come from the EleutherAI team.
- "AI Agents That Matter" and the Holistic Agent Leaderboard come from the same Princeton group.
- The METR paper and the METR blog post are the same work.
- The HELM paper and the HELM framework are the same project. Percy Liang's CS336 lecture draws on it.
- MT-Bench ("Judging LLM-as-a-Judge") and the Chatbot Arena paper come from the same LMSYS group.
- CS336 has 2025 and 2026 recordings of the evaluation lecture. Watch one.
