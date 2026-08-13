# CPSC 4880: Frontier AI Models (Fall 2026)

**Architectures, Training, and Agentic Systems**

Instructor: Arman Cohan
Format: Seminar, Tue/Thu, 16 weeks, 2 sessions per week
Audience: Advanced undergraduates and graduate students with prior exposure to deep learning and NLP (transformers, backprop, basic pretraining concepts assumed).

---

## 1. Course overview

This course examines how frontier AI models are built, trained, and deployed as agentic systems. It moves past foundational material and focuses on the design decisions behind current frontier models: what architectures they use and why, how pretraining and post-training pipelines produce capable and aligned models, how reasoning is elicited with reinforcement learning and test-time compute, and how models are wrapped in harnesses to act as agents. A shorter final unit covers multimodal models as an extension of the architecture and training story.

The course is organized around four themes:

1. **Theme 1: Frontier LLM architectures** (weeks 2-5). The modern decoder stack, mixture-of-experts, attention alternatives (state-space models, hybrids), long context, and emerging paradigms (byte-level models, diffusion LLMs).
2. **Theme 2: Training and post-training** (weeks 5-9). Data curation, scaling laws, open training recipes, preference optimization, RL with verifiable rewards, and test-time compute.
3. **Theme 3: Agents and harnesses** (weeks 10-12). Tool use, harness/scaffold design, coding and computer-use agents, agent evaluation, RL for agents, and agent safety.
4. **Theme 4: Multimodal frontier models** (weeks 14-15). Vision-language models, native/early-fusion multimodal architectures, and speech. Framed as a continuation of Themes 1 and 2.

### Format

Modeled on discussion-driven seminars (cf. JHU CS 601.771). Each theme opens with 1-2 instructor lectures that establish shared vocabulary. The remaining sessions are student-led paper discussions: a team presents and critiques 2 assigned papers, and the rest of the class participates having written short reviews. Each theme also includes one guest lecture from a researcher working on that theme at the frontier.

Session budget (29 teaching sessions after recesses, out of 32 slots):

| Component | Sessions |
|---|---|
| Intro + foundations refresher (instructor) | 2 |
| Instructor lectures within themes | 7 |
| Student paper presentations | 14 |
| Guest lectures | 4 |
| Final project presentations | 2 |
| Recesses (Oct recess Thu, Thanksgiving week) | 3 slots lost |

---

## 2. Course mechanics and grading

Suggested grading (adjust to taste):

| Component | Weight | Notes |
|---|---|---|
| Participation | 15% | Attendance and discussion quality. "Step up / step back" norms. |
| Paper reviews | 20% | Short structured review (0.5-1 page) of one required paper before each student-led session. Strengths, weaknesses, one discussion question. Lowest 3 dropped. |
| Paper presentation + discussion lead | 25% | Teams of 2-3. Two papers per session, ~35 min presentation + critique, then lead ~30 min discussion. Slides due 48 hours ahead for instructor feedback. Assignments announced at least 10 days in advance. |
| Final project | 40% | Teams up to 3. Proposal (wk 6, 10%), midway report (wk 11, 20%), final report (50%), presentation/poster (20%). Must connect to a course theme. |

Notes:
- Reviews are due 9pm the night before each discussion session.
- Encourage projects that involve training/finetuning open models (OLMo, Qwen, Llama), building or evaluating agents, or careful empirical analysis of frontier model behavior.
- Consider an AI-use policy that embraces LLM tools while requiring disclosure, since the course subject is the tools themselves.

---

## 3. Guest lectures (4 slots)

One per theme. Suggested profiles (names are suggestions to invite, not commitments):

| Slot | Theme | Example speakers |
|---|---|---|
| Week 5, Tue | Architectures / efficiency | Tri Dao (Princeton/Together), Albert Gu (CMU/Cartesia), someone from the DeepSeek-style MoE/MLA line of work |
| Week 9, Thu | Post-training / reasoning RL | Nathan Lambert or Hanna Hajishirzi (Ai2, Tulu/OLMo), someone from an RLVR/reasoning team |
| Week 12, Thu | Agents | Ofir Press or John Yang (SWE-bench/SWE-agent), an industry agent-products researcher (Anthropic, OpenAI, Cursor) |
| Week 15, Thu | Multimodal | Molmo team (Ai2), Lucas Beyer, Qwen-VL or Gemini multimodal researcher |

---

## 4. Week-by-week schedule

Dates assume Tue/Thu classes starting Tue Sep 1, 2026, October recess cancelling Thu Oct 22, and Thanksgiving recess cancelling the week of Nov 24-26. **Verify all dates against the official Yale Fall 2026 calendar before publishing.**

Legend: [A] = instructor lecture, [S] = student presentations, [G] = guest.

### Week 1: Introduction and foundations

**Tue 9/1 [A] Course intro: the frontier model landscape.**
What "frontier" means in 2026; open vs. closed models; course logistics and expectations.
Readings: GPT-4 Technical Report ([2303.08774](https://arxiv.org/abs/2303.08774)); The Llama 3 Herd of Models, skim ([2407.21783](https://arxiv.org/abs/2407.21783)).

**Thu 9/3 [A] Foundations refresher.**
Transformer recap, pretraining objectives, tokenization, compute analysis of transformers, the pretrain/post-train pipeline at a high level.
Readings: Attention Is All You Need ([1706.03762](https://arxiv.org/abs/1706.03762)); Scaling Laws for Neural Language Models ([2001.08361](https://arxiv.org/abs/2001.08361)).

### Theme 1: Frontier LLM architectures (weeks 2-5)

**Tue 9/8 [A] Lecture 1.1: The modern decoder stack.**
What changed since the 2017 transformer: RMSNorm, SwiGLU, RoPE and position handling, MQA/GQA, multi-head latent attention (MLA), KV caching and inference costs, FlashAttention, long-context via RoPE scaling.
Readings: RoFormer/RoPE ([2104.09864](https://arxiv.org/abs/2104.09864)); GQA ([2305.13245](https://arxiv.org/abs/2305.13245)); DeepSeek-V2, MLA sections ([2405.04434](https://arxiv.org/abs/2405.04434)); FlashAttention ([2205.14135](https://arxiv.org/abs/2205.14135)).

**Thu 9/10 [A] Lecture 1.2: Sparsity and attention alternatives.**
Mixture-of-experts: routing, load balancing, fine-grained experts. State-space models and linear attention. Hybrid architectures. Why frontier labs converged on sparse models.
Readings: Switch Transformers ([2101.03961](https://arxiv.org/abs/2101.03961)); Mixtral of Experts ([2401.04088](https://arxiv.org/abs/2401.04088)); Mamba ([2312.00752](https://arxiv.org/abs/2312.00752)).

**Tue 9/15 [S] Session 1: MoE at the frontier.**
- DeepSeek-V3 Technical Report ([2412.19437](https://arxiv.org/abs/2412.19437))
- OLMoE: Open Mixture-of-Experts Language Models ([2409.02060](https://arxiv.org/abs/2409.02060))
- Optional: Qwen3 Technical Report ([2505.09388](https://arxiv.org/abs/2505.09388)); Kimi K2 ([2507.20534](https://arxiv.org/abs/2507.20534))

**Thu 9/17 [S] Session 2: Beyond softmax attention.**
- Transformers are SSMs (Mamba-2) ([2405.21060](https://arxiv.org/abs/2405.21060))
- MiniMax-01: Scaling Foundation Models with Lightning Attention ([2501.08313](https://arxiv.org/abs/2501.08313))
- Optional: Jamba ([2403.19887](https://arxiv.org/abs/2403.19887)); Gated Delta Networks ([2412.06464](https://arxiv.org/abs/2412.06464))

**Tue 9/22 [S] Session 3: Long context.**
- YaRN: Efficient Context Window Extension ([2309.00071](https://arxiv.org/abs/2309.00071))
- NoLiMa: Long-Context Evaluation Beyond Literal Matching ([2502.05167](https://arxiv.org/abs/2502.05167))
- Optional: Ring Attention ([2310.01889](https://arxiv.org/abs/2310.01889)); RULER ([2404.06654](https://arxiv.org/abs/2404.06654)); Qwen2.5-1M ([2501.15383](https://arxiv.org/abs/2501.15383))

**Thu 9/24 [S] Session 4: New paradigms: bytes, memory, and diffusion.**
- Byte Latent Transformer: Patches Scale Better Than Tokens ([2412.09871](https://arxiv.org/abs/2412.09871))
- Large Language Diffusion Models (LLaDA) ([2502.09992](https://arxiv.org/abs/2502.09992))
- Optional: Titans: Learning to Memorize at Test Time ([2501.00663](https://arxiv.org/abs/2501.00663))

**Tue 9/29 [G] Guest lecture 1: Architectures and efficiency.**

### Theme 2: Training and post-training (weeks 5-9)

**Thu 10/1 [A] Lecture 2.1: Pretraining at the frontier.**
Data curation and filtering pipelines, dedup, mixing and curricula, annealing/midtraining, scaling laws in practice, muP and hyperparameter transfer, training infrastructure at a high level.
Readings: Training Compute-Optimal LLMs (Chinchilla) ([2203.15556](https://arxiv.org/abs/2203.15556)); FineWeb ([2406.17557](https://arxiv.org/abs/2406.17557)); Llama 3 Herd, pretraining sections ([2407.21783](https://arxiv.org/abs/2407.21783)).
Optional: Tensor Programs V (muP) ([2203.03466](https://arxiv.org/abs/2203.03466)); Observational Scaling Laws ([2405.10938](https://arxiv.org/abs/2405.10938)).

**Tue 10/6 [A] Lecture 2.2: Post-training: from RLHF to reasoning models.**
SFT and instruction tuning, reward models, RLHF/PPO, DPO and its family, RL with verifiable rewards (GRPO and successors), reasoning models and long chain-of-thought, distillation.
Readings: InstructGPT ([2203.02155](https://arxiv.org/abs/2203.02155)); DPO ([2305.18290](https://arxiv.org/abs/2305.18290)); DeepSeek-R1 ([2501.12948](https://arxiv.org/abs/2501.12948)).
Optional: Constitutional AI ([2212.08073](https://arxiv.org/abs/2212.08073)); STaR ([2203.14465](https://arxiv.org/abs/2203.14465)).

**Thu 10/8 [S] Session 5: Data is the product.**
- FineWeb: Decanting the Web for the Finest Text Data at Scale ([2406.17557](https://arxiv.org/abs/2406.17557))
- DataComp-LM ([2406.11794](https://arxiv.org/abs/2406.11794))
- Optional: Scaling Data-Constrained Language Models ([2305.16264](https://arxiv.org/abs/2305.16264)); Phi-4 ([2412.08905](https://arxiv.org/abs/2412.08905))

**Tue 10/13 [S] Session 6: Open training recipes.**
- The Llama 3 Herd of Models ([2407.21783](https://arxiv.org/abs/2407.21783))
- 2 OLMo 2 Furious ([2501.00656](https://arxiv.org/abs/2501.00656))
- Optional: Beyond Chinchilla-Optimal ([2401.00448](https://arxiv.org/abs/2401.00448))

**Thu 10/15 [S] Session 7: Preference optimization.**
- Direct Preference Optimization ([2305.18290](https://arxiv.org/abs/2305.18290))
- SimPO: Simple Preference Optimization ([2405.14734](https://arxiv.org/abs/2405.14734))
- Optional: Tulu 3 ([2411.15124](https://arxiv.org/abs/2411.15124))

**Tue 10/20 [S] Session 8: RL with verifiable rewards.**
- DeepSeek-R1 ([2501.12948](https://arxiv.org/abs/2501.12948))
- Understanding R1-Zero-Like Training (Dr. GRPO) ([2503.20783](https://arxiv.org/abs/2503.20783))
- Optional: DAPO ([2503.14476](https://arxiv.org/abs/2503.14476)); Kimi k1.5 ([2501.12599](https://arxiv.org/abs/2501.12599))

**Thu 10/22: October recess, no class.**

**Tue 10/27 [S] Session 9: Test-time compute.**
- s1: Simple Test-Time Scaling ([2501.19393](https://arxiv.org/abs/2501.19393))
- Scaling LLM Test-Time Compute Optimally ([2408.03314](https://arxiv.org/abs/2408.03314))
- Optional: Let's Verify Step by Step ([2305.20050](https://arxiv.org/abs/2305.20050))

**Thu 10/29 [G] Guest lecture 2: Post-training and reasoning.**

### Theme 3: Agents and harnesses (weeks 10-12)

**Tue 11/3 [A] Lecture 3.1: Anatomy of an agent.**
From chatbots to agents: tool use and function calling, the agent loop, harness/scaffold design, context management and memory, code as action space, MCP and tool ecosystems.
Readings: ReAct ([2210.03629](https://arxiv.org/abs/2210.03629)); Toolformer ([2302.04761](https://arxiv.org/abs/2302.04761)); CodeAct ([2402.01030](https://arxiv.org/abs/2402.01030)); Anthropic, "Building Effective Agents" ([blog](https://www.anthropic.com/research/building-effective-agents)).

**Thu 11/5 [A] Lecture 3.2: Evaluating agents, and agent safety.**
Agentic benchmarks and their pitfalls (SWE-bench, tau-bench, OSWorld, GAIA, Terminal-Bench), reward hacking and eval gaming, prompt injection and the security surface of agents.
Readings: SWE-bench ([2310.06770](https://arxiv.org/abs/2310.06770)); tau-bench ([2406.12045](https://arxiv.org/abs/2406.12045)); GAIA ([2311.12983](https://arxiv.org/abs/2311.12983)); Indirect Prompt Injection ([2302.12173](https://arxiv.org/abs/2302.12173)).

**Tue 11/10 [S] Session 10: Coding agents.**
- SWE-agent: Agent-Computer Interfaces Enable Automated Software Engineering ([2405.15793](https://arxiv.org/abs/2405.15793))
- Agentless: Demystifying LLM-Based Software Engineering Agents ([2407.01489](https://arxiv.org/abs/2407.01489))
- Optional: SWE-bench ([2310.06770](https://arxiv.org/abs/2310.06770))

**Thu 11/12 [S] Session 11: Computer and web use.**
- OSWorld: Benchmarking Multimodal Agents in Real Computer Environments ([2404.07972](https://arxiv.org/abs/2404.07972))
- UI-TARS: Pioneering Automated GUI Interaction with Native Agents ([2501.12326](https://arxiv.org/abs/2501.12326))
- Optional: WebArena ([2307.13854](https://arxiv.org/abs/2307.13854))

**Tue 11/17 [S] Session 12: Agents that learn.**
- Reflexion: Language Agents with Verbal Reinforcement Learning ([2303.11366](https://arxiv.org/abs/2303.11366))
- SWE-RL: Advancing LLM Reasoning via RL on Open Software Evolution ([2502.18449](https://arxiv.org/abs/2502.18449))
- Optional: Voyager ([2305.16291](https://arxiv.org/abs/2305.16291)); WebRL ([2411.02337](https://arxiv.org/abs/2411.02337)); Why Do Multi-Agent LLM Systems Fail? ([2503.13657](https://arxiv.org/abs/2503.13657)); MemGPT ([2310.08560](https://arxiv.org/abs/2310.08560))

**Thu 11/19 [G] Guest lecture 3: Agents in practice.**

**Week of 11/24: Thanksgiving recess, no classes.**

### Theme 4: Multimodal frontier models (weeks 14-15)

**Tue 12/1 [A] Lecture 4.1: Multimodal architectures.**
Continuation of Theme 1: vision encoders and CLIP, adapter-style VLMs vs. early fusion, native multimodal models, interleaved data, multimodal generation, speech.
Readings: CLIP ([2103.00020](https://arxiv.org/abs/2103.00020)); Flamingo ([2204.14198](https://arxiv.org/abs/2204.14198)); LLaVA ([2304.08485](https://arxiv.org/abs/2304.08485)).

**Thu 12/3 [S] Session 13: Open vision-language models.**
- Molmo and PixMo ([2409.17146](https://arxiv.org/abs/2409.17146))
- Qwen2.5-VL ([2502.13923](https://arxiv.org/abs/2502.13923))
- Optional: Gemma 3 ([2503.19786](https://arxiv.org/abs/2503.19786)); Gemini 1.5 ([2403.05530](https://arxiv.org/abs/2403.05530))

**Tue 12/8 [S] Session 14: Native multimodality.**
- Chameleon: Mixed-Modal Early-Fusion Foundation Models ([2405.09818](https://arxiv.org/abs/2405.09818))
- Transfusion: Predict the Next Token and Diffuse Images ([2408.11039](https://arxiv.org/abs/2408.11039))
- Optional: Moshi: A Speech-Text Foundation Model ([2410.00037](https://arxiv.org/abs/2410.00037))

**Thu 12/10 [G] Guest lecture 4: Multimodal frontier + course wrap-up.**

### Week 16: Final projects

**Tue 12/15: Final project presentations, session 1.**
**Thu 12/17: Final project presentations, session 2 (or poster session).**
Final reports due end of exam period.

---

## 5. Keeping the reading list fresh

The paper list above is current as of early 2026. Before the semester starts:

- Swap in mid-2026 releases where they supersede listed papers (frontier model reports especially: sessions 1, 6, 8, 13 are the most likely to need updates).
- Consider designating sessions 4, 9, and 12 as "wildcard" sessions where presenting teams may propose a very recent paper subject to your approval. This keeps the course self-updating.
- Blog posts and system cards from frontier labs (Anthropic, OpenAI, Google DeepMind, DeepSeek, Qwen, Moonshot) are fair game as optional readings; several frontier systems no longer ship papers.

## 6. Alternates pool

Strong papers that did not make the main list. Use for swaps or as extra options for presentation teams:

- **Architectures:** Gemma 3 ([2503.19786](https://arxiv.org/abs/2503.19786)); RWKV; BitNet b1.58 ([2402.17764](https://arxiv.org/abs/2402.17764)); Mixture-of-Depths ([2404.02258](https://arxiv.org/abs/2404.02258))
- **Training:** Muon is Scalable for LLM Training ([2502.16982](https://arxiv.org/abs/2502.16982)); Tulu 3 ([2411.15124](https://arxiv.org/abs/2411.15124)) as a required paper; Self-Rewarding Language Models ([2401.10020](https://arxiv.org/abs/2401.10020)); Spurious Rewards ([2506.10947](https://arxiv.org/abs/2506.10947))
- **Agents:** Toolformer as required; AutoGen ([2308.08155](https://arxiv.org/abs/2308.08155)); multiagent debate ([2305.14325](https://arxiv.org/abs/2305.14325)); Terminal-Bench ([site](https://www.tbench.ai))
- **Multimodal:** InternVL series; PaliGemma ([2407.07726](https://arxiv.org/abs/2407.07726)); Movie Gen ([2410.13720](https://arxiv.org/abs/2410.13720))
