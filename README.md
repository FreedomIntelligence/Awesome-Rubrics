
# Awesome-Rubrics

> **Definition**: Rubric-based Reinforcement Learning (Rubric RL) uses structured
> evaluation criteria (rubrics) as reward signals to train and align LLMs and AI agents.
> Rubrics span from verifiable rules (RLVR) to LLM-generated multi-dimensional scoring.


---

## Table of Contents
- [S1 Foundations & Motivation](#s1)
  - [S1.1 Reward Modeling and Alignment Techniques](#s1-1)
- [S2 Rubric Construction & Generation](#s2)
  - [S2.1 Human-defined & LLM-generated Rubrics](#s2-1)
  - [S2.2 Automated Reward Machine & Rubric Optimization](#s2-2)
  - [S2.3 Cross-Modal and Compositional Rubric Design](#s2-3)
- [S3 Rubric-driven Reward Signal Design](#s3)
  - [S3.1 Verifiable Binary Rewards (RLVR)](#s3-1)
  - [S3.2 Scalar Rubric Scoring & Contextual Rewards](#s3-2)
  - [S3.3 Process-level & Step-wise Rubric Rewards](#s3-3)
  - [S3.4 Multi-objective Rubric Aggregation](#s3-4)
- [S4 Training Algorithms for Rubric RL](#s4)
  - [S4.1 PPO with Rubric Rewards](#s4-1)
  - [S4.2 GRPO / Group Relative Policy Optimization](#s4-2)
  - [S4.3 Preference-based RL with Rubric Feedback (DPO/PbRL)](#s4-3)
  - [S4.4 Curriculum & Multi-stage Rubric Training](#s4-4)
- [S5 Applications: Reasoning and Code](#s5)
  - [S5.1 Mathematical and Logical Reasoning](#s5-1)
  - [S5.2 Code Generation and Software Engineering](#s5-2)
- [S6 Applications: Agents and Tool Use](#s6)
  - [S6.1 Tool-use and Web Agents](#s6-1)
  - [S6.2 Multi-agent and Collaborative Rubric RL](#s6-2)
- [S7 Applications: Multimodal and Embodied](#s7)
  - [S7.1 Vision-Language Model Alignment](#s7-1)
  - [S7.2 Image and Video Generation RL](#s7-2)
  - [S7.3 Embodied Agents and Robotics](#s7-3)
- [S8 Safety, Robustness and Scalable Oversight](#s8)
  - [S8.1 Constitutional AI and RLAIF](#s8-1)
  - [S8.2 Adversarial Robustness and Red-teaming](#s8-2)
  - [S8.3 Scalable Oversight and Weak-to-Strong](#s8-3)
- [S9 Evaluation, Benchmarks and Open Challenges](#s9)
  - [S9.1 Benchmarks and Datasets](#s9-1)
  - [S9.2 Rubric Quality and Meta-evaluation](#s9-2)
  - [S9.3 Open Challenges and Future Directions](#s9-3)

---

## S1 Foundations & Motivation {#s1}

> *Foundational aspects of Rubric RL: reward function design, the rubric definition spectrum from verifiable rules to LLM judges, and connections to RLHF and RLVR paradigms.*

S1 explores reward design challenges, alignment paradigms, and methodological innovations from scalar signals to rich structured rubrics including LLM-as-Judge, preference learning, and self-rewarding mechanisms.

**Key concepts**: `reward design`, `rubric spectrum`, `RLHF`, `RLVR`, `alignment`

**Papers in section**: [[1]](#cite-1), [[2]](#cite-2), [[9]](#cite-9), [[11]](#cite-11), [[17]](#cite-17), [[21]](#cite-21), [[30]](#cite-30), [[34]](#cite-34), [[36]](#cite-36), [[38]](#cite-38), [[39]](#cite-39), [[40]](#cite-40), [[45]](#cite-45), [[61]](#cite-61), [[74]](#cite-74), [[76]](#cite-76)

### S1.1 Reward Modeling and Alignment Techniques {#s1-1}

> *Methodological innovations in designing reward functions using rubrics: preference optimization, dynamic critic feedback, self-rewarding models, and domain-specific reward design.*

**Key concepts**: `reward modeling`, `preference optimization`, `LLM-as-Judge`, `dynamic critic`, `self-rewarding`

**Papers in section**: [[1]](#cite-1), [[2]](#cite-2), [[9]](#cite-9), [[11]](#cite-11), [[17]](#cite-17), [[21]](#cite-21), [[30]](#cite-30), [[34]](#cite-34), [[36]](#cite-36), [[38]](#cite-38), [[39]](#cite-39), [[40]](#cite-40), [[45]](#cite-45), [[61]](#cite-61), [[74]](#cite-74), [[76]](#cite-76)

#### S1.1.1 Rubric-as-Reward & LLM-as-Judge Foundations {#s1-1-1}

> *Core papers defining the rubric-RL paradigm: structured rubrics and LLM judges as reward signals, reward model training methodologies, and rubric quality benchmarking.*

**Key concepts**: `rubric reward`, `LLM-as-judge`, `reward model training`, `structured evaluation`

**Papers**: [[2]](#cite-2), [[11]](#cite-11), [[36]](#cite-36), [[39]](#cite-39)

#### S1.1.2 Preference Learning & Alignment Optimization {#s1-1-2}

> *Learning reward functions from human preferences: DPO variants, ordinal feedback, pluralistic alignment, cultural awareness, and preference calibration.*

**Key concepts**: `preference learning`, `DPO`, `RLHF`, `pluralistic alignment`, `ordinal reward`

**Papers**: [[1]](#cite-1), [[34]](#cite-34), [[45]](#cite-45), [[74]](#cite-74)

#### S1.1.3 Dynamic Critic & Self-Rewarding Mechanisms {#s1-1-3}

> *Models generating their own reward signals through self-evaluation, natural language gradient feedback, or dynamic critic models for free-form generation.*

**Key concepts**: `self-rewarding`, `dynamic critic`, `NL feedback`, `intrinsic reward`

**Papers**: [[9]](#cite-9), [[21]](#cite-21), [[30]](#cite-30), [[38]](#cite-38)

#### S1.1.4 Domain-Specific Reward Design {#s1-1-4}

> *Reward design tailored to specific domains: speech naturalness, visual generation, recommendation systems, story generation, and industrial optimization tasks.*

**Key concepts**: `domain rewards`, `speech reward`, `visual RL`, `recommendation RL`

**Papers**: [[17]](#cite-17), [[40]](#cite-40), [[61]](#cite-61), [[76]](#cite-76)

---

## S2 Rubric Construction & Generation {#s2}

> *Methods for designing, generating, and learning rubrics as dynamic evaluation criteria: multi-modal, compositional, and automated optimization techniques.*

Techniques for constructing rubrics: human-defined and LLM-generated criteria, automated reward machines, influence-guided optimization, and cross-modal compositional rubric design.

**Key concepts**: `rubric design`, `rubric generation`, `reward machines`, `compositional rubric`

**Papers in section**: [[2]](#cite-2), [[13]](#cite-13), [[26]](#cite-26), [[31]](#cite-31), [[36]](#cite-36), [[49]](#cite-49), [[53]](#cite-53)

### S2.1 Human-defined & LLM-generated Rubrics {#s2-1}

> *Specifying rubrics via human expertise or LLM-generated structured criteria from instructions, demonstrations, or preference data.*

**Key concepts**: `human rubrics`, `LLM-generated criteria`, `instruction rubric`, `demonstration learning`

**Papers**: [[2]](#cite-2), [[13]](#cite-13), [[31]](#cite-31), [[49]](#cite-49)

### S2.2 Automated Reward Machine & Rubric Optimization {#s2-2}

> *Automatically constructing or optimizing rubrics: influence-guided methods, synthetic data generation, and compositional reward machine design via foundation models.*

**Key concepts**: `reward machines`, `automated rubric`, `ARM-FM`, `OptimSyn`, `influence-guided`

**Papers**: [[26]](#cite-26), [[53]](#cite-53)

### S2.3 Cross-Modal and Compositional Rubric Design {#s2-3}

> *Integrating multiple modalities and compositional reasoning to create robust rubrics for evaluating complex multi-faceted behaviors and outputs.*

**Key concepts**: `multimodal rubric`, `compositional evaluation`, `cross-modal criteria`

**Papers**: [[26]](#cite-26), [[36]](#cite-36)

---

## S3 Rubric-driven Reward Signal Design {#s3}

> *Conversion of rubrics into RL reward signals: from verifiable binary rewards to dense LLM-scored rubrics, process-level supervision, and multi-objective aggregation.*

Papers on rubric-driven reward signals: RLVR binary rewards, scalar LLM scoring, step-wise process rewards, and multi-objective rubric aggregation.

**Key concepts**: `reward signal`, `RLVR`, `LLM-as-Judge`, `process supervision`, `multi-objective`

**Papers in section**: [[5]](#cite-5), [[6]](#cite-6), [[11]](#cite-11), [[13]](#cite-13), [[19]](#cite-19), [[27]](#cite-27), [[28]](#cite-28), [[29]](#cite-29), [[31]](#cite-31), [[33]](#cite-33), [[41]](#cite-41), [[47]](#cite-47), [[48]](#cite-48), [[49]](#cite-49), [[55]](#cite-55), [[57]](#cite-57), [[59]](#cite-59), [[63]](#cite-63), [[77]](#cite-77), [[80]](#cite-80), [[81]](#cite-81), [[84]](#cite-84)

### S3.1 Verifiable Binary Rewards (RLVR) {#s3-1}

> *Verifiable reward mechanisms providing binary or sparse outcome signals grounded in checkable correctness criteria for LLM training.*

**Key concepts**: `RLVR`, `verifiable rewards`, `binary reward`, `outcome verification`

**Papers in section**: [[5]](#cite-5), [[27]](#cite-27), [[28]](#cite-28), [[29]](#cite-29), [[47]](#cite-47), [[48]](#cite-48), [[49]](#cite-49), [[55]](#cite-55), [[57]](#cite-57), [[80]](#cite-80), [[81]](#cite-81), [[84]](#cite-84)

#### S3.1.1 RLVR Core Methods & Scaling {#s3-1-1}

> *Foundational RLVR methods: unsupervised RLVR, long-context verifiable rewards, rollout efficiency, and scaling approaches.*

**Key concepts**: `RLVR core`, `unsupervised RLVR`, `long-context reward`, `rollout efficiency`

**Papers**: [[5]](#cite-5), [[48]](#cite-48), [[80]](#cite-80), [[84]](#cite-84)

#### S3.1.2 Hybrid & Flexible Feedback Signals {#s3-1-2}

> *Methods bridging human feedback and verifiable rewards: binary flexible feedback, hybrid dense-sparse rewards, and emotion-verifiable reward signals.*

**Key concepts**: `hybrid rewards`, `RLBFF`, `flexible feedback`, `dense-sparse bridge`

**Papers**: [[27]](#cite-27), [[28]](#cite-28), [[29]](#cite-29), [[57]](#cite-57)

#### S3.1.3 Reward Robustness, Hacking & Calibration {#s3-1-3}

> *Addressing reward over-optimization, hacking, misspecification, causal rubrics for robustness, and confidence calibration in reward signals.*

**Key concepts**: `reward hacking`, `causal rubrics`, `reward robustness`, `reward calibration`

**Papers**: [[47]](#cite-47), [[49]](#cite-49), [[55]](#cite-55), [[81]](#cite-81)

### S3.2 Scalar Rubric Scoring & Contextual Rewards {#s3-2}

> *LLM-generated scalar scores or contextual reward signals enabling nuanced multi-dimensional evaluation beyond binary outcomes.*

**Key concepts**: `scalar rewards`, `LLM scoring`, `contextual reward`, `dense rubric`

**Papers**: [[6]](#cite-6), [[11]](#cite-11), [[19]](#cite-19), [[41]](#cite-41)

### S3.3 Process-level & Step-wise Rubric Rewards {#s3-3}

> *Step-by-step rewards aligned with rubric evaluations for fine-grained process supervision over reasoning and action chains.*

**Key concepts**: `process supervision`, `step-wise reward`, `PRM`, `incremental rubric`

**Papers**: [[59]](#cite-59), [[63]](#cite-63), [[77]](#cite-77)

### S3.4 Multi-objective Rubric Aggregation {#s3-4}

> *Combining multiple rubric dimensions into unified reward signals, balancing competing objectives in multi-criterion evaluation.*

**Key concepts**: `multi-objective`, `reward aggregation`, `composite rubric`, `Pareto`

**Papers**: [[13]](#cite-13), [[31]](#cite-31), [[33]](#cite-33), [[47]](#cite-47)

---

## S4 Training Algorithms for Rubric RL {#s4}

> *RL algorithms with rubric-derived rewards: policy gradient methods, group-relative optimization, preference-based RL, and curriculum learning.*

RL algorithms leveraging rubric-derived rewards: PPO variants, GRPO and group-relative methods, preference-based RL with rubric feedback, and curriculum/multi-stage training.

**Key concepts**: `PPO`, `GRPO`, `DPO`, `curriculum learning`, `RL algorithms`

**Papers in section**: [[1]](#cite-1), [[10]](#cite-10), [[15]](#cite-15), [[38]](#cite-38), [[45]](#cite-45), [[46]](#cite-46), [[51]](#cite-51), [[53]](#cite-53), [[60]](#cite-60), [[69]](#cite-69), [[79]](#cite-79), [[81]](#cite-81)

### S4.1 PPO with Rubric Rewards {#s4-1}

> *PPO applied with rubric-generated rewards, with innovations in reward shaping, policy constraints, training stability, and latent reasoning.*

**Key concepts**: `PPO`, `policy gradient`, `KL constraint`, `rubric reward shaping`

**Papers**: [[51]](#cite-51), [[69]](#cite-69)

### S4.2 GRPO / Group Relative Policy Optimization {#s4-2}

> *GRPO and variants for rubric-based policy refinement enabling efficient group-level advantage estimation without a separate value model.*

**Key concepts**: `GRPO`, `group-relative`, `advantage estimation`, `value-free RL`

**Papers**: [[10]](#cite-10), [[15]](#cite-15), [[46]](#cite-46), [[79]](#cite-79)

### S4.3 Preference-based RL with Rubric Feedback (DPO/PbRL) {#s4-3}

> *Preference-driven RL with rubric-derived feedback: DPO variants, offline preference optimization, and rubric-augmented comparative evaluation.*

**Key concepts**: `PbRL`, `DPO`, `preference learning`, `offline RL`, `rubric feedback`

**Papers**: [[1]](#cite-1), [[45]](#cite-45), [[45]](#cite-45), [[81]](#cite-81)

### S4.4 Curriculum & Multi-stage Rubric Training {#s4-4}

> *Multi-stage and curriculum training leveraging rubrics to progressively guide learning across difficulty levels and task distributions.*

**Key concepts**: `curriculum learning`, `multi-stage`, `progressive rubric`, `adaptive training`

**Papers**: [[38]](#cite-38), [[51]](#cite-51), [[53]](#cite-53), [[60]](#cite-60)

---

## S5 Applications: Reasoning and Code {#s5}

> *Applying rubric-RL to mathematical reasoning, coding, and logical problem-solving tasks, including chain-of-thought, step-wise reward, and code execution feedback.*

Rubric RL applied to complex reasoning and code tasks: from RLVR-trained math solvers to code-execution-graded RL, process-reward-guided reasoning, and competitive programming agents.

**Key concepts**: `math reasoning`, `code generation`, `chain-of-thought`, `execution feedback`, `RLVR reasoning`

**Papers in section**: [[4]](#cite-4), [[5]](#cite-5), [[18]](#cite-18), [[27]](#cite-27), [[42]](#cite-42), [[44]](#cite-44), [[59]](#cite-59), [[63]](#cite-63), [[64]](#cite-64), [[72]](#cite-72), [[78]](#cite-78), [[80]](#cite-80), [[83]](#cite-83), [[84]](#cite-84)

### S5.1 Mathematical and Logical Reasoning {#s5-1}

> *RL-trained LLMs on math/logic tasks using verifiable rubrics: outcome-based, process-based, and hybrid reward strategies.*

**Key concepts**: `math RL`, `RLVR math`, `PRM`, `reasoning chain`, `verification`

**Papers in section**: [[4]](#cite-4), [[5]](#cite-5), [[27]](#cite-27), [[42]](#cite-42), [[44]](#cite-44), [[59]](#cite-59), [[63]](#cite-63), [[64]](#cite-64), [[72]](#cite-72), [[80]](#cite-80), [[83]](#cite-83), [[84]](#cite-84)

#### S5.1.1 Outcome-based Math Reasoning RL {#s5-1-1}

> *Training LLMs to solve math problems using verifiable final-answer rewards and rubric-graded outcomes.*

**Key concepts**: `outcome reward`, `math RLVR`, `answer verification`, `correctness rubric`

**Papers**: [[4]](#cite-4), [[5]](#cite-5), [[44]](#cite-44), [[72]](#cite-72)

#### S5.1.2 Process-reward and Step-wise Reasoning {#s5-1-2}

> *Step-level process reward models guiding chain-of-thought reasoning via rubric-based intermediate supervision.*

**Key concepts**: `PRM`, `step reward`, `process supervision`, `CoT rubric`

**Papers**: [[42]](#cite-42), [[59]](#cite-59), [[63]](#cite-63), [[83]](#cite-83)

#### S5.1.3 Logical and Symbolic Reasoning {#s5-1-3}

> *Rubric RL for formal logic, constraint satisfaction, theorem proving, and symbolic reasoning tasks.*

**Key concepts**: `logical reasoning`, `theorem proving`, `constraint rubric`, `symbolic RL`

**Papers**: [[27]](#cite-27), [[64]](#cite-64), [[80]](#cite-80), [[84]](#cite-84)

### S5.2 Code Generation and Software Engineering {#s5-2}

> *Rubric-RL for code: execution-based rewards, test-case rubrics, code quality criteria, and agentic coding tasks.*

**Key concepts**: `code RL`, `execution reward`, `test rubric`, `agentic coding`

**Papers**: [[18]](#cite-18), [[42]](#cite-42), [[72]](#cite-72), [[78]](#cite-78)

---

## S6 Applications: Agents and Tool Use {#s6}

> *Rubric RL for agentic tasks: multi-step tool use, web navigation, GUI interaction, and multi-agent coordination under structured rubric feedback.*

Applying rubric RL to agentic settings: tool-augmented LLM agents, browser/web navigation, GUI grounding, and collaborative multi-agent systems with rubric-structured feedback.

**Key concepts**: `agent RL`, `tool use`, `web agent`, `GUI agent`, `multi-agent`

**Papers in section**: [[7]](#cite-7), [[8]](#cite-8), [[12]](#cite-12), [[14]](#cite-14), [[24]](#cite-24), [[37]](#cite-37), [[39]](#cite-39), [[56]](#cite-56), [[60]](#cite-60), [[65]](#cite-65), [[75]](#cite-75)

### S6.1 Tool-use and Web Agents {#s6-1}

> *Rubric-guided RL for agents using external tools, APIs, search, and web browsers to complete complex tasks.*

**Key concepts**: `tool-use RL`, `API agent`, `web navigation`, `search rubric`

**Papers in section**: [[24]](#cite-24), [[37]](#cite-37), [[39]](#cite-39), [[56]](#cite-56), [[60]](#cite-60), [[65]](#cite-65), [[75]](#cite-75)

#### S6.1.1 Tool-augmented Agent RL {#s6-1-1}

> *RL with rubric rewards for LLMs that call tools, APIs, or external functions to solve tasks.*

**Key concepts**: `tool calling`, `API RL`, `function calling rubric`, `tool-augmented`

**Papers**: [[24]](#cite-24), [[37]](#cite-37), [[56]](#cite-56), [[75]](#cite-75)

#### S6.1.2 Web and GUI Navigation {#s6-1-2}

> *Rubric-graded RL for agents navigating web pages, GUI environments, and interactive interfaces.*

**Key concepts**: `web agent`, `GUI RL`, `browser navigation`, `grounding rubric`

**Papers**: [[37]](#cite-37), [[39]](#cite-39), [[60]](#cite-60), [[65]](#cite-65)

### S6.2 Multi-agent and Collaborative Rubric RL {#s6-2}

> *Rubric RL in multi-agent settings: decentralized rubric assignment, collaborative reward shaping, and emergent cooperation.*

**Key concepts**: `multi-agent RL`, `cooperative rubric`, `decentralized reward`, `emergent behavior`

**Papers**: [[7]](#cite-7), [[8]](#cite-8), [[12]](#cite-12), [[14]](#cite-14)

---

## S7 Applications: Multimodal and Embodied {#s7}

> *Rubric RL for vision-language models, image/video generation, embodied agents, and robotics with multimodal rubric feedback.*

Rubric RL beyond text: vision-language model alignment with visual rubrics, image/video generation quality rubrics, and embodied/robotic agent training with environment-grounded rubric feedback.

**Key concepts**: `multimodal RL`, `VLM`, `embodied agent`, `visual rubric`, `robotics RL`

**Papers in section**: [[16]](#cite-16), [[18]](#cite-18), [[22]](#cite-22), [[23]](#cite-23), [[25]](#cite-25), [[35]](#cite-35), [[58]](#cite-58), [[62]](#cite-62), [[67]](#cite-67), [[73]](#cite-73), [[82]](#cite-82)

### S7.1 Vision-Language Model Alignment {#s7-1}

> *Aligning VLMs with rubric RL: visual preference optimization, multimodal rubric reward signals, and grounded visual evaluation criteria.*

**Key concepts**: `VLM alignment`, `visual reward`, `multimodal rubric`, `visual preference`

**Papers**: [[58]](#cite-58), [[62]](#cite-62), [[67]](#cite-67), [[73]](#cite-73)

### S7.2 Image and Video Generation RL {#s7-2}

> *Applying rubric RL to image/video generation: aesthetic rubrics, text-image alignment rewards, temporal consistency criteria.*

**Key concepts**: `image RL`, `video RL`, `aesthetic rubric`, `text-image alignment`

**Papers**: [[16]](#cite-16), [[25]](#cite-25), [[82]](#cite-82)

### S7.3 Embodied Agents and Robotics {#s7-3}

> *Rubric-guided RL for embodied navigation, manipulation, and robotic control with environment-grounded structured rewards.*

**Key concepts**: `embodied RL`, `robotics rubric`, `navigation reward`, `manipulation RL`

**Papers**: [[18]](#cite-18), [[22]](#cite-22), [[23]](#cite-23), [[35]](#cite-35)

---

## S8 Safety, Robustness and Scalable Oversight {#s8}

> *Using rubric RL for safety alignment, robustness to adversarial inputs, scalable oversight mechanisms, and constitutional AI principles.*

Rubric RL for safety: constitutional rubrics, RLAIF-based oversight, red-teaming with rubric graders, adversarial robustness via rubric constraints, and scalable supervision beyond human labels.

**Key concepts**: `safety RL`, `constitutional AI`, `scalable oversight`, `adversarial robustness`, `RLAIF`

**Papers in section**: [[3]](#cite-3), [[21]](#cite-21), [[32]](#cite-32), [[52]](#cite-52), [[70]](#cite-70), [[71]](#cite-71), [[78]](#cite-78)

### S8.1 Constitutional AI and RLAIF {#s8-1}

> *Training safe models using constitutional rubrics and AI feedback instead of human labels for scalable alignment.*

**Key concepts**: `constitutional AI`, `RLAIF`, `AI feedback`, `self-critique rubric`

**Papers**: [[3]](#cite-3), [[32]](#cite-32), [[52]](#cite-52), [[71]](#cite-71)

### S8.2 Adversarial Robustness and Red-teaming {#s8-2}

> *Rubric RL for robustness: adversarial training with rubric-based attack criteria, red-team RL, and jailbreak resistance.*

**Key concepts**: `adversarial RL`, `red-teaming`, `jailbreak rubric`, `robustness reward`

**Papers**: [[21]](#cite-21), [[52]](#cite-52), [[70]](#cite-70), [[78]](#cite-78)

### S8.3 Scalable Oversight and Weak-to-Strong {#s8-3}

> *Scalable oversight using rubric RL: debate, amplification, weak-to-strong generalization, and critiquing for superhuman alignment.*

**Key concepts**: `scalable oversight`, `debate`, `weak-to-strong`, `amplification`, `rubric critique`

**Papers**: [[32]](#cite-32)

---

## S9 Evaluation, Benchmarks and Open Challenges {#s9}

> *Benchmarks for rubric RL evaluation, meta-evaluation of rubric quality, open problems, and future directions in rubric-driven RL.*

Comprehensive evaluation infrastructure for rubric RL: benchmark datasets, rubric quality metrics, meta-evaluation frameworks, and a synthesis of open challenges and future research directions.

**Key concepts**: `benchmarks`, `evaluation`, `rubric quality`, `meta-evaluation`, `open problems`

**Papers in section**: [[3]](#cite-3), [[20]](#cite-20), [[28]](#cite-28), [[33]](#cite-33), [[34]](#cite-34), [[43]](#cite-43), [[44]](#cite-44), [[46]](#cite-46), [[50]](#cite-50), [[54]](#cite-54), [[55]](#cite-55), [[57]](#cite-57), [[66]](#cite-66), [[68]](#cite-68)

### S9.1 Benchmarks and Datasets {#s9-1}

> *Benchmark suites and datasets for evaluating rubric RL systems across reasoning, alignment, agent, and safety tasks.*

**Key concepts**: `benchmark`, `dataset`, `evaluation suite`, `leaderboard`

**Papers in section**: [[3]](#cite-3), [[20]](#cite-20), [[44]](#cite-44), [[50]](#cite-50), [[54]](#cite-54), [[57]](#cite-57), [[66]](#cite-66), [[68]](#cite-68)

#### S9.1.1 Reasoning and Alignment Benchmarks {#s9-1-1}

> *Benchmark datasets for evaluating rubric RL on mathematical reasoning, language understanding, and alignment quality.*

**Key concepts**: `math benchmark`, `alignment evaluation`, `reasoning dataset`

**Papers**: [[20]](#cite-20), [[44]](#cite-44), [[66]](#cite-66), [[68]](#cite-68)

#### S9.1.2 Agent and Safety Benchmarks {#s9-1-2}

> *Benchmarks targeting rubric RL in agentic, tool-use, and safety evaluation contexts.*

**Key concepts**: `agent benchmark`, `safety evaluation`, `rubric grading`

**Papers**: [[3]](#cite-3), [[50]](#cite-50), [[54]](#cite-54), [[57]](#cite-57)

### S9.2 Rubric Quality and Meta-evaluation {#s9-2}

> *Evaluating the quality, reliability, and validity of rubrics themselves: inter-annotator agreement, rubric consistency, and automated rubric validation.*

**Key concepts**: `rubric quality`, `meta-evaluation`, `inter-annotator`, `rubric validation`

**Papers**: [[20]](#cite-20), [[33]](#cite-33), [[34]](#cite-34)

### S9.3 Open Challenges and Future Directions {#s9-3}

> *Synthesis of open research questions: reward hacking at scale, rubric generalization, alignment tax, and next frontiers for rubric RL.*

**Key concepts**: `open problems`, `reward hacking`, `alignment tax`, `future directions`

**Papers**: [[28]](#cite-28), [[43]](#cite-43), [[46]](#cite-46), [[55]](#cite-55)

---

## References

<a id="cite-1"></a>[1] **Learning Ordinal Probabilistic Reward from Preferences**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=0Vf5trUAVF) [[PDF]](https://openreview.net/attachment?id=0Vf5trUAVF&name=pdf)  
<a id="cite-2"></a>[2] **RM-R1: Reward Modeling as Reasoning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=1ZqJ6jj75q) [[PDF]](https://openreview.net/attachment?id=1ZqJ6jj75q&name=pdf)  
<a id="cite-3"></a>[3] **AlphaAlign: Incentivizing Safety Alignment with Extremely Simplified Reinforcement Learning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=2XNb1JUKW3) [[PDF]](https://openreview.net/attachment?id=2XNb1JUKW3&name=pdf)  
<a id="cite-4"></a>[4] **Learning from Synthetic Data Improves Multi-hop Reasoning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=38nYZ5QBui) [[PDF]](https://openreview.net/attachment?id=38nYZ5QBui&name=pdf)  
<a id="cite-5"></a>[5] **A Simple "Motivation" Can Enhance Reinforcement Finetuning of Large Reasoning Models**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=3owSlsYDQf) [[PDF]](https://openreview.net/attachment?id=3owSlsYDQf&name=pdf)  
<a id="cite-6"></a>[6] **R1-Reward: Training Multimodal Reward Model Through Stable Reinforcement Learning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=4Ewgw9M2xE) [[PDF]](https://openreview.net/attachment?id=4Ewgw9M2xE&name=pdf)  
<a id="cite-7"></a>[7] **Unlocking the Power of Multi-Agent LLM for Reasoning: From Lazy Agents to Deliberation**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=5J6u03ObRZ) [[PDF]](https://openreview.net/attachment?id=5J6u03ObRZ&name=pdf)  
<a id="cite-8"></a>[8] **Learning to summarize user information for personalized reinforcement learning from human feedback**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=Ar078WR3um) [[PDF]](https://openreview.net/attachment?id=Ar078WR3um&name=pdf)  
<a id="cite-9"></a>[9] **Vision-SR1: Self-Rewarding Vision-Language Model via Reasoning Decomposition and Multi-Reward Policy Optimization**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=C1M4ETatgM) [[PDF]](https://openreview.net/attachment?id=C1M4ETatgM&name=pdf)  
<a id="cite-10"></a>[10] **Repurposing Synthetic Data for Fine-grained Search Agent Supervision**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=CByVWPpb8T) [[PDF]](https://openreview.net/attachment?id=CByVWPpb8T&name=pdf)  
<a id="cite-11"></a>[11] **QuRL: Rubrics As Judge For Open-Ended Question Answering**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=DrhWTuhtYq) [[PDF]](https://openreview.net/attachment?id=DrhWTuhtYq&name=pdf)  
<a id="cite-12"></a>[12] **REA-RL: Reflection-Aware Online Reinforcement Learning for Efficient Reasoning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=E6keG5QDct) [[PDF]](https://openreview.net/attachment?id=E6keG5QDct&name=pdf)  
<a id="cite-13"></a>[13] **ResearchRubrics: A Benchmark of Prompts and Rubrics For Evaluating Deep Research Agents**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=ErnvfmSX0P) [[PDF]](https://openreview.net/attachment?id=ErnvfmSX0P&name=pdf)  
<a id="cite-14"></a>[14] **Generate Any Scene: Scene Graph Driven Data Synthesis for Visual Generation Training**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=EwdWR6lfvW) [[PDF]](https://openreview.net/attachment?id=EwdWR6lfvW&name=pdf)  
<a id="cite-15"></a>[15] **DRPO: Efficient Reasoning via Decoupled Reward Policy Optimization**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=GP5RHZnEsw) [[PDF]](https://openreview.net/attachment?id=GP5RHZnEsw&name=pdf)  
<a id="cite-16"></a>[16] **RePrompt: Reasoning-Augmented Reprompting for Text-to-Image Generation via Reinforcement Learning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=HJ3vgg7TYQ) [[PDF]](https://openreview.net/attachment?id=HJ3vgg7TYQ&name=pdf)  
<a id="cite-17"></a>[17] **SpeechJudge: Towards Human-Level Judgment for Speech Naturalness**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=I9ED9VWZq6) [[PDF]](https://openreview.net/attachment?id=I9ED9VWZq6&name=pdf)  
<a id="cite-18"></a>[18] **ROSETTA: Constructing Code-Based Reward from Unconstrained Language Preference**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=Ig6goVdtjb) [[PDF]](https://openreview.net/attachment?id=Ig6goVdtjb&name=pdf)  
<a id="cite-19"></a>[19] **ContextIF: Enhancing Instruction-Following through Context Reward**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=IuscGSmfEf) [[PDF]](https://openreview.net/attachment?id=IuscGSmfEf&name=pdf)  
<a id="cite-20"></a>[20] **VerifyBench: Benchmarking Reference-based Reward Systems for Large Language Models**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=JfsjGmuFxz) [[PDF]](https://openreview.net/attachment?id=JfsjGmuFxz&name=pdf)  
<a id="cite-21"></a>[21] **Inverse Reinforcement Learning with Dynamic Reward Scaling for LLM Alignment**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=K0Zh6mzTzc) [[PDF]](https://openreview.net/attachment?id=K0Zh6mzTzc&name=pdf)  
<a id="cite-22"></a>[22] **Smarter Not Harder: Generative Process Evaluation with Intrinsic-Signal Driving and Ability‑Adaptive Reward Shaping**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=LZZENDlZt9) [[PDF]](https://openreview.net/attachment?id=LZZENDlZt9&name=pdf)  
<a id="cite-23"></a>[23] **Human-Object Interaction via Automatically Designed VLM-Guided Motion Policy**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=LfkPlFTfe0) [[PDF]](https://openreview.net/attachment?id=LfkPlFTfe0&name=pdf)  
<a id="cite-24"></a>[24] **Empowering LLM Tool Invocation with Tool-call Reward Model**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=LnBEASInVr) [[PDF]](https://openreview.net/attachment?id=LnBEASInVr&name=pdf)  
<a id="cite-25"></a>[25] **Diffusion Blend: Inference-Time Multi-Preference Alignment for Diffusion Models**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=M2DXbwO8le) [[PDF]](https://openreview.net/attachment?id=M2DXbwO8le&name=pdf)  
<a id="cite-26"></a>[26] **ARM-FM: Automated Reward Machines via Foundation Models for Compositional Reinforcement Learning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=OBpQdCWLfd) [[PDF]](https://openreview.net/attachment?id=OBpQdCWLfd&name=pdf)  
<a id="cite-27"></a>[27] **Process-Verified Reinforcement Learning for Theorem Proving via Lean**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=P00k4DFaXF) [[PDF]](https://openreview.net/attachment?id=P00k4DFaXF&name=pdf)  
<a id="cite-28"></a>[28] **RLBFF: Binary Flexible Feedback to bridge between Human Feedback & Verifiable Rewards**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=P3R3S6S5Km) [[PDF]](https://openreview.net/attachment?id=P3R3S6S5Km&name=pdf)  
<a id="cite-29"></a>[29] **RLVER: Reinforcement Learning with Verifiable Emotion Rewards for Empathetic Agents**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=P7wBg0vPTh) [[PDF]](https://openreview.net/attachment?id=P7wBg0vPTh&name=pdf)  
<a id="cite-30"></a>[30] **Text2Grad: Reinforcement Learning from Natural Language Feedback**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=SIE9fNq8lk) [[PDF]](https://openreview.net/attachment?id=SIE9fNq8lk&name=pdf)  
<a id="cite-31"></a>[31] **mR3: Multilingual Rubric-Agnostic Reward Reasoning Models**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=ST0wOB1bdX) [[PDF]](https://openreview.net/attachment?id=ST0wOB1bdX&name=pdf)  
<a id="cite-32"></a>[32] **Critique-RL: Training Language Models For Critiquing Through Two-Stage Reinforcement Learning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=SsUjdSVdUl) [[PDF]](https://openreview.net/attachment?id=SsUjdSVdUl&name=pdf)  
<a id="cite-33"></a>[33] **ProfBench: Multi-Domain Rubrics requiring Professional Knowledge to Answer and Judge**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=VwNzKPqBxk) [[PDF]](https://openreview.net/attachment?id=VwNzKPqBxk&name=pdf)  
<a id="cite-34"></a>[34] **Evaluating and Improving Cultural Awareness of Reward Models for LLM Alignment**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=WhSzqsMhfZ) [[PDF]](https://openreview.net/attachment?id=WhSzqsMhfZ&name=pdf)  
<a id="cite-35"></a>[35] **Aligning Deep Implicit Preferences by Learning to Reason Defensively**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=ZA7i5Otjqd) [[PDF]](https://openreview.net/attachment?id=ZA7i5Otjqd&name=pdf)  
<a id="cite-36"></a>[36] **Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=c1bTcrDmt4) [[PDF]](https://openreview.net/attachment?id=c1bTcrDmt4&name=pdf)  
<a id="cite-37"></a>[37] **WebArbiter: A Generative Reasoning Process Reward Model for Web Agents**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=canA6Ef0RP) [[PDF]](https://openreview.net/attachment?id=canA6Ef0RP&name=pdf)  
<a id="cite-38"></a>[38] **Reinforcement Learning from Dynamic Critic Feedback for Free-Form Generations**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=dBmjnRR1bC) [[PDF]](https://openreview.net/attachment?id=dBmjnRR1bC&name=pdf)  
<a id="cite-39"></a>[39] **J1: Incentivizing Thinking in LLM-as-a-Judge via Reinforcement Learning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=dnJEHl6DI1) [[PDF]](https://openreview.net/attachment?id=dnJEHl6DI1&name=pdf)  
<a id="cite-40"></a>[40] **Reinforced Latent Reasoning for LLM-based Recommendation**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=eUtIZT2ONS) [[PDF]](https://openreview.net/attachment?id=eUtIZT2ONS&name=pdf)  
<a id="cite-41"></a>[41] **KL-Regularized Reinforcement Learning is Designed to Mode Collapse**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=flBRtdIihA) [[PDF]](https://openreview.net/attachment?id=flBRtdIihA&name=pdf)  
<a id="cite-42"></a>[42] **Learn to Reason Efficiently with Adaptive Length-based Reward Shaping**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=hj9eKpqxQl) [[PDF]](https://openreview.net/attachment?id=hj9eKpqxQl&name=pdf)  
<a id="cite-43"></a>[43] **Cat-PO: Cross-modal Adaptive Token-rewards for Preference Optimization in Truthful Multimodal LLMs**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=iIbe6qDN0A) [[PDF]](https://openreview.net/attachment?id=iIbe6qDN0A&name=pdf)  
<a id="cite-44"></a>[44] **DeepMath-103K: A Large-Scale, Challenging, Decontaminated, and Verifiable Mathematical Dataset for Advancing Reasoning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=kHB5Te5IWm) [[PDF]](https://openreview.net/attachment?id=kHB5Te5IWm&name=pdf)  
<a id="cite-45"></a>[45] **Beyond Binary Preferences: A Principled Framework for Reward Modeling with Ordinal Feedback**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=mteZOi0xyu) [[PDF]](https://openreview.net/attachment?id=mteZOi0xyu&name=pdf)  
<a id="cite-46"></a>[46] **DenseGRPO: From Sparse to Dense Reward for Flow Matching Model Alignment**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=nIwFge9nW0) [[PDF]](https://openreview.net/attachment?id=nIwFge9nW0&name=pdf)  
<a id="cite-47"></a>[47] **Robust Reward Modeling via Causal Rubrics**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=oP99JQiDYp) [[PDF]](https://openreview.net/attachment?id=oP99JQiDYp&name=pdf)  
<a id="cite-48"></a>[48] **LongRLVR: Long-Context Reinforcement Learning Requires Verifiable Context Rewards**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=omVhYvyTPJ) [[PDF]](https://openreview.net/attachment?id=omVhYvyTPJ&name=pdf)  
<a id="cite-49"></a>[49] **Chasing the Tail: Effective Rubric-based Reward Modeling for Large Language Model Post-Training**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=pBjy4ek2QV) [[PDF]](https://openreview.net/attachment?id=pBjy4ek2QV&name=pdf)  
<a id="cite-50"></a>[50] **VitaBench: Benchmarking LLM Agents with Versatile Interactive Tasks in Real-world Applications**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=rtcX9qOBaz) [[PDF]](https://openreview.net/attachment?id=rtcX9qOBaz&name=pdf)  
<a id="cite-51"></a>[51] **All Roads Lead to Likelihood: The Value of Reinforcement Learning in Fine-Tuning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=sCL5mSTpKm) [[PDF]](https://openreview.net/attachment?id=sCL5mSTpKm&name=pdf)  
<a id="cite-52"></a>[52] **Critique-Coder: Enhancing Coder Models by Critique Reinforcement Learning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=tsuxIeLUsz) [[PDF]](https://openreview.net/attachment?id=tsuxIeLUsz&name=pdf)  
<a id="cite-53"></a>[53] **OptimSyn: Influence-Guided Rubrics Optimization for Synthetic Data Generation**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=vFcm5sOitq) [[PDF]](https://openreview.net/attachment?id=vFcm5sOitq&name=pdf)  
<a id="cite-54"></a>[54] **Doctor-R1: Mastering Clinical Inquiry with Experiential Agentic Reinforcement Learning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=vQGHTyL0Jw) [[PDF]](https://openreview.net/attachment?id=vQGHTyL0Jw&name=pdf)  
<a id="cite-55"></a>[55] **Rewarding Doubt: A Reinforcement Learning Approach to Calibrated Confidence Expression of Large Language Models**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=yResLmrVO1) [[PDF]](https://openreview.net/attachment?id=yResLmrVO1&name=pdf)  
<a id="cite-56"></a>[56] **Nemotron-Research-Tool-N1: Exploring Tool-Using Language Models with Reinforced Reasoning**. *ICLR2026*. [[OpenReview]](https://openreview.net/forum?id=yiE16lWzDj) [[PDF]](https://openreview.net/attachment?id=yiE16lWzDj&name=pdf)  
<a id="cite-57"></a>[57] **Reasoning as an Adaptive Defense for Safety**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=2NLHoWE0eS) [[PDF]](https://openreview.net/pdf/c036ebd40ea82ab94b9badc0028faf7e94456ca1.pdf)  
<a id="cite-58"></a>[58] **Rendering-Aware Reinforcement Learning for Vector Graphics Generation**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=2Twzlf6qFv) [[PDF]](https://openreview.net/pdf/2b05cd2ffc937becedaa135f83f56276f7da8709.pdf)  
<a id="cite-59"></a>[59] **Unlocking Multimodal Mathematical Reasoning via Process Reward Model**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=96I8PGPALv) [[PDF]](https://openreview.net/pdf/9bc76b4ee1cdbe244a893c162b08d3ed55059de4.pdf)  
<a id="cite-60"></a>[60] **BTL-UI: Blink-Think-Link Reasoning Model for GUI Agent**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=B0Gfxhr8V5) [[PDF]](https://openreview.net/pdf/ba5902ee29175bd53969957abcfa4c2349bdef9d.pdf)  
<a id="cite-61"></a>[61] **Q-Insight: Understanding Image Quality via Visual Reinforcement Learning**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=Bds54EfR9x) [[PDF]](https://openreview.net/pdf/29873597e5222d2d5aa68cd083390fc6fabf8acd.pdf)  
<a id="cite-62"></a>[62] **GoalLadder: Incremental Goal Discovery with Vision-Language Models**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=BiowiwzQaO) [[PDF]](https://openreview.net/pdf/1bd1725eab30686d6f19c7b22db26e952e0088e3.pdf)  
<a id="cite-63"></a>[63] **Unveiling Chain of Step Reasoning for Vision-Language Models with Fine-grained Rewards**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=D8nHwexHNv) [[PDF]](https://openreview.net/pdf/9393d795825dc403a5224e23b11e26237b1bf5ed.pdf)  
<a id="cite-64"></a>[64] **AceReason-Nemotron: Advancing Math and Code Reasoning through Reinforcement Learning**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=EgArbnS0BA) [[PDF]](https://openreview.net/pdf/4dbb7f099e0ae9ed52f26be78bbd5f18b4adc8a6.pdf)  
<a id="cite-65"></a>[65] **Web-Shepherd: Advancing PRMs for Reinforcing Web Agents**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=G2kMroO9UV) [[PDF]](https://openreview.net/pdf/db46564195dad40b9b174514d7d03b0336d2a8eb.pdf)  
<a id="cite-66"></a>[66] **Reasoning Models Hallucinate More: Factuality-Aware Reinforcement Learning for Large Reasoning Models**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=Igq7Dyc3OL) [[PDF]](https://openreview.net/pdf/31f57f113b7a0a8d53b00020bbcdabe6ac8a82cf.pdf)  
<a id="cite-67"></a>[67] **Unveiling the Compositional Ability Gap in Vision-Language Reasoning Model**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=J76cCYTJub) [[PDF]](https://openreview.net/pdf/64ee56c0512b904e0aebcd799494fb96e7bdedba.pdf)  
<a id="cite-68"></a>[68] **ShorterBetter: Guiding Reasoning Models to Find Optimal Inference Length for Efficient Reasoning**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=MJvwM5dBZM) [[PDF]](https://openreview.net/pdf/bde69f28fc3bc8b96d74cd959ffd7e961aa0e70e.pdf)  
<a id="cite-69"></a>[69] **Open-Reasoner-Zero: An Open Source Approach to Scaling Up Reinforcement Learning on the Base Model**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=NFM8F5cV0V) [[PDF]](https://openreview.net/pdf/afe1d28b1ce36a43b6b9635f485c7af91a6f8ffb.pdf)  
<a id="cite-70"></a>[70] **VisionThink: Smart and Efficient Vision Language Model via Reinforcement Learning**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=R6m6bNnmWm) [[PDF]](https://openreview.net/pdf/a1ce03f1786df2e67c61dd99ba4f40d2d92f913b.pdf)  
<a id="cite-71"></a>[71] **Checklists Are Better Than Reward Models For Aligning Language Models**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=RPRqKhjrr6) [[PDF]](https://openreview.net/pdf/490597cf8f353f8b01b8474e2f98c045eba8f5f4.pdf)  
<a id="cite-72"></a>[72] **SWE-RL: Advancing LLM Reasoning via Reinforcement Learning on Open Software Evolution**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=ULblO61XZ0) [[PDF]](https://openreview.net/pdf/ddd60c79265a4298a0592f27ac7d58b00b035132.pdf)  
<a id="cite-73"></a>[73] **Enhancing the Outcome Reward-based RL Training of MLLMs with Self-Consistency Sampling**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=cGkfMGQdCy) [[PDF]](https://openreview.net/pdf/29edb9ad7e36190f61e9e0b17ae1d99a6df5fb11.pdf)  
<a id="cite-74"></a>[74] **Pairwise Calibrated Rewards for Pluralistic Alignment**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=dtH7hOwTeS) [[PDF]](https://openreview.net/pdf/ef69c75af64f81a288945ec20c335d30642960ce.pdf)  
<a id="cite-75"></a>[75] **ToolRL: Reward is All Tool Learning Needs**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=eOLdGbXT6t) [[PDF]](https://openreview.net/pdf/097ae4a34c2eb2b82b2bb8fccc279fb0e3585304.pdf)  
<a id="cite-76"></a>[76] **Think before Recommendation: Autonomous Reasoning-enhanced Recommender**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=fVs2BCjCqC) [[PDF]](https://openreview.net/pdf/dabe28fda98c6afcff77d9aaf707bc000be4bf15.pdf)  
<a id="cite-77"></a>[77] **Process vs. Outcome Reward: Which is Better for Agentic RAG Reinforcement Learning**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=h3LlJ6Bh4S) [[PDF]](https://openreview.net/pdf/863197fcba5eb83767ace1f59ea8fa5f81958eb6.pdf)  
<a id="cite-78"></a>[78] **RSafe: Incentivizing proactive reasoning to build robust and adaptive  LLM safeguards**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=heJ7NRInjs) [[PDF]](https://openreview.net/pdf/04dac969863242564dac530962d0596f2d7cf2ad.pdf)  
<a id="cite-79"></a>[79] **Towards Unified Multimodal Interleaved Generation via Group Relative Policy Optimization**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=lUHwUuQGdV) [[PDF]](https://openreview.net/pdf/be81012c4b8d2224b305eb1f109bd4f030fe2ac2.pdf)  
<a id="cite-80"></a>[80] **QiMeng-CodeV-R1: Reasoning-Enhanced Verilog Generation**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=ly5DnRIgCZ) [[PDF]](https://openreview.net/pdf/09c10d014999eae477f919d98b0b392a60db1ab1.pdf)  
<a id="cite-81"></a>[81] **Rectifying Shortcut Behaviors in Preference-based Reward Learning**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=m51t6RKfGH) [[PDF]](https://openreview.net/pdf/68f64407c11f7fe9069c3e63b8c90bfbf679caa6.pdf)  
<a id="cite-82"></a>[82] **Improving Video Generation with Human Feedback**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=nHkg4yc7SP) [[PDF]](https://openreview.net/pdf/9300b9bfa061e0fc09e2514b1515f9d8296c8da3.pdf)  
<a id="cite-83"></a>[83] **Search and Refine During Think: Facilitating Knowledge Refinement for Improved Retrieval-Augmented Reasoning**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=rBlWKIUQey) [[PDF]](https://openreview.net/pdf/55cb62683b4084a45b97fd43ed7c483dbae3acc3.pdf)  
<a id="cite-84"></a>[84] **Co-Evolving LLM Coder and Unit Tester via Reinforcement Learning**. *NeurIPS2025*. [[OpenReview]](https://openreview.net/forum?id=wPdBe9zxNr) [[PDF]](https://openreview.net/pdf/f11013ca9dbe05459e89557ddb9b09d292b6f6ba.pdf)  

## Citetation
```
@misc{xiao2026awesome_rubrics,
  author       = {},
  title        = {Awesome-Rubrics: A Curated Repository of Evaluation Rubrics},
  year         = {2026},
  url          = {https://github.com/Hongru0306/Awesome-Rubrics},
  note         = {GitHub repository, accessed March 23, 2026}
}
```
