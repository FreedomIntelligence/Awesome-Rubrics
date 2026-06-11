<h1 align="center">Awesome-Rubrics</h1>

<p align="center">
  <a href="./Rubric_Survey_Paper.pdf"><img src="https://img.shields.io/badge/Survey%20Paper-Paper-blue" alt="Survey Paper"></a>
  <a href="https://github.com/sindresorhus/awesome"><img src="https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg" alt="Awesome"></a>
  <a href="https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity"><img src="https://img.shields.io/badge/Maintained%3F-yes-green.svg" alt="Maintenance"></a>
  <a href="http://makeapullrequest.com"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat" alt="PRs Welcome"></a>
</p>

<p align="center">
  A curated reading list on <b>rubric-based evaluation, reward modeling, and post-training for large models</b>.
  <br>
  Rubrics turn expert judgment into structured criteria, auditable LLM judges, and trainable reward signals.
</p>

---


## News

- **[2026-06]** Our survey paper, *Structuring Human Objectives: A Survey of Rubrics for Evaluation, Alignment, and Agentic AI*, is now available: [PDF](./Rubric_Survey_Paper.pdf).

<p align="center">
  <img src="./utils/Taxonomy.jpg" alt="Taxonomy of rubric-centered supervision" width="95%">
</p>

---

Papers with publicly released code or project resources include an inline `[[Code](...)]` link. Entries without verified repositories omit that link.

> Contributions are welcome. If you find missing papers, inaccurate classifications, or newly released code, feel free to update this list.

## What are Rubrics?

In the context of LLM evaluation and alignment, a **rubric** is a structured set of criteria for judging open-ended model outputs. Instead of asking a human or LLM judge for one vague preference, rubrics decompose quality into explicit dimensions, scoring rules, and evidence requirements.

Rubrics make subjective judgment more inspectable:

- **What to judge**: relevance, factuality, completeness, safety, reasoning quality, style, or domain-specific standards.
- **How to judge**: score levels, checklists, pairwise criteria, evidence anchors, or weighted dimensions.
- **How to use the judgment**: evaluation reports, LLM-as-a-Judge protocols, reward models, preference tuning, policy optimization, and curriculum learning.

<p align="center">
  <img src="./utils/main.jpg" alt="Rubrics: from coarse to fine-grained reward signals" width="820">
</p>

<p align="center"><i>Figure 1. Rubrics convert coarse feedback into fine-grained, inspectable reward signals.</i></p>

| Feedback style | Typical signal | Best fit | Main limitation |
|---|---|---|---|
| **RLHF / model-based preference** | "Output A is better than output B." | Open-ended comparison | Coarse and hard to inspect |
| **RLVR / rule-based reward** | Format is correct, answer matches, reasoning token appears, list structure exists | Verifiable tasks | Too rigid for subjective or open-ended tasks |
| **Rubric-based feedback** | Relevance, completeness, clarity, safety, each scored separately | Open-ended evaluation and training | Requires careful design and calibration |

Rubrics are the middle layer: more structured than model-only preference, more flexible than hard rules.

## Why Rubrics Matter Now

> "In this new era, evaluation becomes more important than training."
>
> - Shunyu Yao, [*The Second Half* (2025)](https://ysymyth.github.io/The-Second-Half/)

As large models move from closed-form QA to open-ended reasoning, agents, multimodal generation, and professional domains, progress is increasingly bottlenecked by **evaluation and feedback design**. Training can optimize only what the system can measure, and many important tasks cannot be reduced to a single scalar reward.

| Rubrics help answer | Why it matters |
|---|---|
| **What counts as good behavior?** | They define explicit criteria, scoring boundaries, and failure modes. |
| **How can expert judgment scale?** | They convert tacit standards into reusable evaluation instructions and datasets. |
| **How can LLM-as-a-Judge become less opaque?** | Judges can be required to expose criteria, evidence, scores, and rationales. |
| **How does evaluation become training signal?** | Rubric-level feedback can supervise SFT, preference tuning, policy optimization, reward modeling, and curriculum learning. |

Rubrics therefore act as a bridge between **human standards** and **machine-optimizable signals**. They are not merely annotation templates; they are a control surface for evaluation, reward modeling, and post-training.


## Growing Research Momentum

<p align="center">
  <img src="./utils/tending.jpg" alt="Growing number of rubric-related papers" width="1080">
</p>

<p align="center"><i>Figure 2. The number of rubric-related papers has grown rapidly, suggesting increasing research attention to structured evaluation and reward design.</i></p>

The rising trend shows that rubric-based methods are becoming an increasingly important direction for large-model alignment, especially as evaluation, reward modeling, and post-training move toward more structured and auditable feedback.


## From Evaluation to Reward

Evaluation is no longer only a post-hoc metric. It is becoming part of the **infrastructure of AI systems**:

```text
🧑‍⚖️ Expert Standards → 📋 Rubrics → 📊 Evaluation Signals → 🎯 Rewards → 🔁 Training Dynamics
```

Rubrics are therefore not just for judging model outputs. They are a way to **automate parts of expert feedback**: experts define criteria, models apply them at scale, and failures reveal where the rubric or judge must be revised. In this sense, evaluation becomes an executable form of domain knowledge.

## A Minimal Rubric Example

For the query:

```text
How can cities encourage more people to use public transport?
```

a rubric does not directly ask "which answer is better?" It decomposes the judgment:

| Component | What the judge checks |
|---|---|
| **Relevance** | Does the answer address public transport adoption rather than unrelated urban issues? |
| **Clarity** | Is the answer easy to understand and well organized? |
| **Completeness** | Does it cover affordability, convenience, infrastructure, reliability, and incentives? |
| **Safety / fairness** | Does it avoid harmful, biased, or exclusionary suggestions? |

This makes the reward more interpretable, decomposable, and actionable.

## Rubric Generation Strategies

<p align="center">
  <img src="./utils/gen.jpg" alt="Rubric generation strategies" width="820">
</p>

<p align="center"><i>Figure 3. Rubric construction paradigms for large model alignment.</i></p>

| Strategy | Core idea | When it is useful |
|---|---|---|
| **Expert direct annotation** | Experts write criteria explicitly. | High-stakes domains and seed rubrics |
| **Induction from expert QA annotations** | Criteria are extracted from annotated examples. | Scaling expert knowledge beyond manual templates |
| **Distillation from teacher demonstrations** | Rubrics are derived from high-quality model outputs. | Bootstrapping scalable reward signals |

Together, these strategies show how rubric construction moves from manual specification toward data-driven induction and model-driven distillation.


## Repository Map

This repository is organized as a **conceptual map** of rubric-related research. We group papers by the role rubrics play in the large-model pipeline.

This organization helps show rubrics not only as evaluation tools, but also as structured interfaces connecting **expert standards**, **feedback data**, **reward signals**, **training objectives**, and **deployment-time assessment**.

| Section | Role in the repository |
|---|---|
| **Foundations** | Introduces what counts as a rubric, how rubric formats differ from preferences, rules, or scalar scores, and why structured criteria become useful in large-model settings. |
| **Data** | Covers how rubrics are collected, generated, refined, and organized into reusable supervision signals through human annotation, synthetic generation, expert labeling, and rubric datasets. |
| **Training** | Summarizes how rubric-level judgments can be transformed into SFT data, preference objectives, RL rewards, curriculum signals, and self-improvement loops. |
| **Evaluation** | Connects rubrics to LLM-as-a-judge protocols, benchmark design, calibration, reliability analysis, and robustness checks, where explicit and auditable criteria are especially important. |
| **Applications** | Shows how rubric-based methods extend beyond text QA to multimodal tasks, agent systems, and professional domains that require domain-specific standards. |

Overall, this structure follows the lifecycle of rubric-based large-model alignment:

**Define criteria → collect or generate rubric data → train with rubric signals → evaluate with structured judges → apply in domain-specific tasks**

> Rubrics provide a structured layer for connecting data, training, evaluation, and applications.


## Table of Contents

<details open>
<summary>Browse the reading list</summary>

- [Data](#data)
  - [Expert-Based Annotation](#expert-based-annotation)
    - [Expert Requirement](#expert-requirement)
    - [Expert Provider](#expert-provider)
  - [Model-Based Annotation](#model-based-annotation)
    - [Naive Generation Analysis](#naive-generation-analysis)
    - [Pairs-Grounded Generation](#pairs-grounded-generation)
    - [Iterative Refinement](#iterative-refinement)
  - [Human-AI Collaboration](#human-ai-collaboration)
- [Training](#training)
  - [Pre-training](#pre-training)
  - [Post-training](#post-training)
    - [Rubrics for Supervised FT](#rubrics-for-supervised-ft)
    - [Rubrics for Preference-Reward RL](#rubrics-for-preference-reward-rl)
    - [Rubrics for Direct-Reward RL](#rubrics-for-direct-reward-rl)
      - [Rubric Judgement Pattern](#rubric-judgement-pattern)
      - [Rubric Grader Analysis](#rubric-grader-analysis)
      - [Multi-Objective Optimization](#multi-objective-optimization)
      - [Credit Assignment](#credit-assignment)
      - [Agent Harness](#agent-harness)
    - [Rubrics for Advanced Training](#rubrics-for-advanced-training)
      - [Curriculum Learning](#curriculum-learning)
      - [Self-Evolving Learning](#self-evolving-learning)
      - [Hint-Based Learning](#hint-based-learning)
- [Inference](#inference)
  - [Inference-Time Rubric Supervision](#inference-time-rubric-supervision)
- [Risk](#risk)
  - [Rubric Reward Hacking](#rubric-reward-hacking)
- [Evaluation](#evaluation)
  - [Real-World Tasks](#real-world-tasks)
    - [Medical](#medical)
    - [Legal](#legal)
    - [Office Labor](#office-labor)
    - [Academic](#academic)
    - [Deep Research](#deep-research)
    - [Creative Generation](#creative-generation)
  - [General Capability Evaluation](#general-capability-evaluation)
    - [Agentic](#agentic)
    - [Reasoning](#reasoning)
    - [Alignment](#alignment)
- [Applications](#applications)
  - [Domain](#domain-applications)
    - [Medical](#medical)
    - [Writing and Retrieval](#writing-and-retrieval)
    - [DeepResearch](#deepresearch)
    - [Code](#code)
    - [General Agentic](#general-agentic)
  - [Multimodal](#multimodal-applications)
    - [Text + Vision](#text--vision)
    - [Text + Audio](#text--audio)
    - [Omni-modal](#omni-modal)

</details>

---

> Papers with publicly released code are marked with 🌟.

## Data

> This section collects work on how rubric criteria, checklists, and rubric-annotated data are authored, elicited, generated, refined, and validated before being used for evaluation or training.

### Expert-Based Annotation

> Expert-based annotation relies on domain specialists or expert-designed protocols when reliable rubrics require professional standards or task-specific expertise.

#### Expert Requirement

> These works study tasks where expert knowledge is necessary to define what counts as a correct, safe, complete, or high-quality answer.

##### 2026

- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.07244)] PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation [[Proj](https://presentbench.github.io/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Creative%20Generation&amp;color=A16A5B&amp;style=flat-square" alt="Creative Generation">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.16669)] PLAW BENCH: A Rubric-Based Benchmark for Evaluating LLMs in Real-World Legal Practice [[Code](https://github.com/SKYLENAGE-AI/PLawBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Legal&amp;color=8A6F8F&amp;style=flat-square" alt="Legal">

##### 2025

- 🌟 [[arXiv 2025.11](https://arxiv.org/abs/2511.11562)] PRBench: Large-Scale Expert Rubrics for Evaluating High-Stakes Professional Reasoning [[Proj](https://scale.com/research/prbench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">
- 🌟 [[ACL 26](https://arxiv.org/abs/2511.10507)] AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following [[Code](https://github.com/facebookresearch/AdvancedIF)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=VwNzKPqBxk)] ProfBench: Multi-Domain Rubrics requiring Professional Knowledge to Answer and Judge [[Code](https://github.com/NVlabs/ProfBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">
- 🌟 [[arXiv 2025.06](https://arxiv.org/abs/2506.01789)] Datasheets Aren't Enough: DataRubrics for Automated Quality Metrics and Accountability [[Proj](https://datarubrics.github.io/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement">
- 🌟 [[arXiv 2025.05](https://arxiv.org/abs/2505.08775)] HealthBench: Evaluating Large Language Models Towards Improved Human Health [[Proj](https://openai.com/index/healthbench/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">

#### Expert Provider

> These works release or organize expert-provided rubrics, checklists, or evaluation criteria as reusable assets for judging model outputs.

##### 2026

- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2604.02368)] XpertBench: Expert Level Tasks with Rubrics-Based Evaluation [[Proj](https://xpert.bytedance.com/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider"> <img src="https://img.shields.io/static/v1?label=&amp;message=Human-AI%20Collaboration&amp;color=5F8791&amp;style=flat-square" alt="Human-AI Collaboration">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.01562)] RubricBench: Aligning Model-Generated Rubrics with Human Standards [[Code](https://github.com/planepig/rubricbench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider"> <img src="https://img.shields.io/static/v1?label=&amp;message=Human-AI%20Collaboration&amp;color=5F8791&amp;style=flat-square" alt="Human-AI Collaboration"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">

##### 2025

- 🌟 [[arXiv 2025.12](https://arxiv.org/abs/2512.04921)] The AI Consumer Index (ACE) [[Proj](https://www.mercor.com/apex/ace-leaderboard/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=ErnvfmSX0P)] RESEARCH RUBRICS: A Benchmark of Prompts and Rubrics For Evaluating Deep Research Agents [[Proj](https://labs.scale.com/papers/researchrubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider">
- 🌟 [[arXiv 2025.09](https://arxiv.org/abs/2509.25721)] The AI Productivity Index: APEX-v1-extended [[Proj](https://www.mercor.com/apex/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=nJvgBolRcR)] ExpertLongBench: Benchmarking Language Models on Expert-Level Long-Form Generation Tasks with Structured Checklists [[Proj](https://huggingface.co/spaces/launch/ExpertLongBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider"> <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">

### Model-Based Annotation

> Model-based annotation uses LLMs or automated pipelines to construct rubric criteria at scale, reducing reliance on fully manual rubric authoring.

#### Naive Generation Analysis

> Naive generation methods ask models to produce criteria or checklists directly from the task, prompt, answer, or context, without grounding them in preference pairs or iterative human correction.

##### 2026

- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.23522)] Qworld: Question-Specific Evaluation Criteria for LLMs [[Proj](https://qworld.openscientist.ai)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Naive%20Generation%20Analysis&amp;color=4F6F73&amp;style=flat-square" alt="Naive Generation Analysis">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.20882)] RubricRAG: Towards Interpretable and Reliable LLM Evaluation via Domain Knowledge Retrieval for Rubric Generation [[Data](https://huggingface.co/datasets/kdhole/healthbench-rubric-responses)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Naive%20Generation%20Analysis&amp;color=4F6F73&amp;style=flat-square" alt="Naive Generation Analysis">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.07019)] AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge [[Code](https://github.com/ChicagoHAI/AutoChecklist)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Naive%20Generation%20Analysis&amp;color=4F6F73&amp;style=flat-square" alt="Naive Generation Analysis">

##### 2025

- 🌟 [[ACL 26](https://arxiv.org/abs/2510.07743)] OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment [[Model](https://huggingface.co/OpenRubrics/RubricRM-4B-Rubric)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Naive%20Generation%20Analysis&amp;color=4F6F73&amp;style=flat-square" alt="Naive Generation Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern">

#### Pairs-Grounded Generation

> Pairs-grounded methods infer criteria from preferences, comparisons, or contrastive response pairs, converting implicit relative judgments into explicit rubric dimensions.

##### 2026

- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.08035)] CDRRM: Contrast-Driven Rubric Generation for Reliable and Interpretable Reward Modeling [[Code](https://github.com/ldcan/CDRRM.git)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.03619)] Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation [[Model](https://huggingface.co/fdu-lcz/rubric_generator)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation"> <img src="https://img.shields.io/static/v1?label=&amp;message=DeepResearch&amp;color=4E6EAD&amp;style=flat-square" alt="DeepResearch">

##### 2025

- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.17314)] From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling [[Code](https://github.com/agentscope-ai/OpenJudge)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation">
- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.07284)] Online Rubrics Elicitation from Pairwise Comparisons [[Proj](https://scale.com/research/onlinerubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=c1bTcrDmt4)] Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains [[Data](https://huggingface.co/datasets/ScaleAI/RaR-Science)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation"> <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern">
- 🌟 [[arXiv 2025.06](https://arxiv.org/abs/2506.15651)] AutoRule: Reasoning Chain-of-Thought Extracted Rule-Based Rewards Improve Preference Learning [[Code](https://github.com/cxcscmu/AutoRule)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation">

##### 2024

- [[ACL Findings 2025](https://aclanthology.org/2025.findings-acl.114/)] CARMO: Dynamic Criteria Generation for Context Aware Reward Modelling <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation">

#### Iterative Refinement

> Iterative refinement methods repeatedly revise rubrics using feedback, disagreement, scoring errors, or self-reflection so that the criteria better match intended judgments.

##### 2026

- 🌟 [[ICLR 26](https://openreview.net/forum?id=vFcm5sOitq)] OptimSyn: Influence-Guided Rubrics Optimization for Synthetic Data Generation [[Code](https://github.com/FanZT6/OptimSyn)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Iterative%20Refinement&amp;color=5B8FA1&amp;style=flat-square" alt="Iterative Refinement">
- [[arXiv 2026.03](https://arxiv.org/abs/2603.00451)] Confusion-Aware Rubric Optimization for LLM-based Automated Grading <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Iterative%20Refinement&amp;color=5B8FA1&amp;style=flat-square" alt="Iterative Refinement">
- [[ICLR 26](https://openreview.net/forum?id=aA2PXFH2Cp)] Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Iterative%20Refinement&amp;color=5B8FA1&amp;style=flat-square" alt="Iterative Refinement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning">
- [[arXiv 2026.01](https://arxiv.org/abs/2601.18706)] Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Iterative%20Refinement&amp;color=5B8FA1&amp;style=flat-square" alt="Iterative Refinement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- 🌟 [[ACL 26](https://arxiv.org/abs/2601.08430)] RubricHub: A Comprehensive and Highly Discriminative Rubric Dataset via Automated Coarse-to-Fine Generation [[Code](https://github.com/teqkilla/RubricHub)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Iterative%20Refinement&amp;color=5B8FA1&amp;style=flat-square" alt="Iterative Refinement">

##### 2025

- 🌟 [[ICLR 26](https://openreview.net/forum?id=dBmjnRR1bC)] RLAC: Reinforcement Learning with Adversarial Critic for Free-Form Generation Tasks [[Proj](https://mianwu01.github.io/RLAC_website/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Iterative%20Refinement&amp;color=5B8FA1&amp;style=flat-square" alt="Iterative Refinement">

### Human-AI Collaboration

> Human-AI collaboration treats rubric construction as a joint process where humans guide, inspect, or correct model-generated criteria rather than fully delegating rubric design.

#### 2026

- 🌟 [[arXiv 2026.04](https://arxiv.org/abs/2604.02368)] XpertBench: Expert Level Tasks with Rubrics-Based Evaluation [[Proj](https://xpert.bytedance.com/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider"> <img src="https://img.shields.io/static/v1?label=&amp;message=Human-AI%20Collaboration&amp;color=5F8791&amp;style=flat-square" alt="Human-AI Collaboration">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.01562)] RubricBench: Aligning Model-Generated Rubrics with Human Standards [[Code](https://github.com/planepig/rubricbench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider"> <img src="https://img.shields.io/static/v1?label=&amp;message=Human-AI%20Collaboration&amp;color=5F8791&amp;style=flat-square" alt="Human-AI Collaboration"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.09653)] ClinAlign: Scaling Healthcare Alignment from Clinician Preference [[Code](https://github.com/AQ-MedAI/ClinAlign)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Human-AI%20Collaboration&amp;color=5F8791&amp;style=flat-square" alt="Human-AI Collaboration"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">

#### 2025

- 🌟 [[ICLR 25](https://proceedings.iclr.cc/paper_files/paper/2025/hash/771155abaae744e08576f1f3b4b7ac0d-Abstract-Conference.html)] WildBench: Benchmarking LLMs with Challenging Tasks from Real Users in the Wild [[Code](https://github.com/allenai/WildBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Human-AI%20Collaboration&amp;color=5F8791&amp;style=flat-square" alt="Human-AI Collaboration">

#### 2024

- 🌟 [[ICLR 24](https://openreview.net/forum?id=CYmF38ysDa)] FLASK: Fine-grained Language Model Evaluation based on Alignment Skill Sets [[Code](https://github.com/kaistAI/FLASK)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Human-AI%20Collaboration&amp;color=5F8791&amp;style=flat-square" alt="Human-AI Collaboration">


## Training

> This section covers methods that turn rubrics into training signals for models, reward models, evaluators, and agents.

#### Pre-training

> Pre-training work would use rubric-like supervision before task-specific alignment, preparing models for later rubric-guided evaluation or optimization.

- No retained papers after full-text justification review.

#### Post-training

> Post-training work applies rubrics after base-model training, using them for supervised fine-tuning, reward modeling, reinforcement learning, or self-improvement.

##### Rubrics for Supervised FT

> Rubrics can guide supervised fine-tuning by filtering examples, weighting samples, generating rationales, or teaching models to follow explicit criteria.

###### 2026
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.02986)] P-Check: Advancing Personalized Reward Models via Learning to Generate Dynamic Checklists [[Code](https://github.com/tommyEzreal/P-Check_)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Supervised%20Fine-Tuning&amp;color=9A7B5F&amp;style=flat-square" alt="Supervised Fine-Tuning">

###### 2025
- 🌟 [[ICLR 26](https://openreview.net/forum?id=ST0wOB1bdX)] mR3: Multilingual Rubric-Agnostic Reward Reasoning Models [[Code](https://github.com/rubricreward/mr3)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Supervised%20Fine-Tuning&amp;color=9A7B5F&amp;style=flat-square" alt="Supervised Fine-Tuning"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[arXiv 2025.05](https://arxiv.org/abs/2505.13388)] R3: Robust Rubric-Agnostic Reward Models [[Code](https://github.com/rubricreward/r3)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Supervised%20Fine-Tuning&amp;color=9A7B5F&amp;style=flat-square" alt="Supervised Fine-Tuning"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=1ZqJ6jj75q)] RM-R1: Reward Modeling as Reasoning [[Proj](https://rm-r1-uiuc.github.io/rmr1-site/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Supervised%20Fine-Tuning&amp;color=9A7B5F&amp;style=flat-square" alt="Supervised Fine-Tuning"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">

###### 2023
- 🌟 [[ICLR 24](https://proceedings.iclr.cc/paper_files/paper/2024/hash/803485352e61e3ebf41221e4776c9fd4-Abstract-Conference.html)] Prometheus: Inducing Fine-grained Evaluation Capability in Language Models [[Code](https://github.com/prometheus-eval/prometheus-eval)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Supervised%20Fine-Tuning&amp;color=9A7B5F&amp;style=flat-square" alt="Supervised Fine-Tuning">

##### Rubrics for Preference-Reward RL

> Preference-reward methods use rubrics or criteria to structure preference data and train reward models, rather than directly optimizing a hand-written rubric score.

###### 2026
- 🌟 [[arXiv 2026.05](https://arxiv.org/abs/2605.07396)] Rubric-based On-policy Distillation [[Code](https://github.com/Peregrine123/ROPD_official)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL">
- 🌟 [[arXiv 2026.04](https://arxiv.org/abs/2604.13618)] C2: Scalable Rubric-Augmented Reward Modeling from Binary Preferences [[Code](https://github.com/asahi-research/C2)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL">
- [[arXiv 2026.04](https://arxiv.org/abs/2604.13029)] Visual Preference Optimization with Rubric Rewards <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL"> <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Vision&amp;color=9A6F7F&amp;style=flat-square" alt="Text + Vision">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.21362)] AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation [[Code](https://github.com/alphadl/AdaRubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.14069)] Open Rubric System: Scaling Reinforcement Learning with Pairwise Adaptive Rubric [[Code](https://github.com/Qwen-Applications/OpenRS)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.01511)] Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training [[Model](https://huggingface.co/collections/OpenRubrics/rubricarm)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL"> <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">

###### 2025
- 🌟 [[ICML-W](https://openreview.net/forum?id=seA8en4ujl)] Configurable Preference Tuning with Rubric-Guided Synthetic Data [[Code](https://github.com/vicgalle/configurable-preference-tuning)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL">
- 🌟 [[NeurIPS 25](https://openreview.net/forum?id=RPRqKhjrr6)] Checklists Are Better Than Reward Models For Aligning Language Models [[Code](https://github.com/viswavi/RLCF)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL">

##### Rubrics for Direct-Reward RL

> Direct-reward RL directly optimizes policies using rubric scores, checklist outcomes, verifier judgments, or criterion-level feedback as rewards.

###### Rubric Judgement Pattern

> Rubric judgement pattern methods ask a judge, verifier, or rubric model to score outputs against explicit criteria and aggregate those judgments into rewards.

###### 2025
- 🌟 [[ICLR 26](https://openreview.net/forum?id=c1bTcrDmt4)] Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains [[Data](https://huggingface.co/datasets/ScaleAI/RaR-Science)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation"> <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern">
- 🌟 [[arXiv 2025.11](https://arxiv.org/abs/2511.19399)] DR Tulu: Reinforcement Learning with Evolving Rubrics for Deep Research [[Code](https://github.com/rlresearch/dr-tulu)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning"> <img src="https://img.shields.io/static/v1?label=&amp;message=DeepResearch&amp;color=4E6EAD&amp;style=flat-square" alt="DeepResearch">
- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.14660)] An Efficient Rubric-based Generative Verifier for Search-Augmented LLMs [[Code](https://github.com/linyue-ma/Search-Gen-V)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">
- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.07743)] OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment [[Model](https://huggingface.co/OpenRubrics/RubricRM-4B-Rubric)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Naive%20Generation%20Analysis&amp;color=4F6F73&amp;style=flat-square" alt="Naive Generation Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern">
- 🌟 [[arXiv 2025.08](https://arxiv.org/abs/2508.16949)] Breaking the Exploration Bottleneck: Rubric-Scaffolded Reinforcement Learning for General LLM Reasoning [[Code](https://github.com/IANNXANG/RuscaRL)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Hint-Based%20Learning&amp;color=B07955&amp;style=flat-square" alt="Hint-Based Learning">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=PTXi3Ef4sT)] Don't Pass@k: A Bayesian Framework for Large Language Model Evaluation [[Code](https://github.com/mohsenhariri/scorio)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern">
- 🌟 [[arXiv 2025.03](https://arxiv.org/abs/2503.05244)] WritingBench: A Comprehensive Benchmark for Generative Writing [[Code](https://github.com/X-PLUG/WritingBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Creative%20Generation&amp;color=A16A5B&amp;style=flat-square" alt="Creative Generation">

###### 2024
- 🌟 [[ACL 24](https://aclanthology.org/2024.acl-long.745/)] LLM-Rubric: A Multidimensional, Calibrated Approach to Automated Evaluation of Natural Language Texts [[Code](https://github.com/microsoft/LLM-Rubric)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Writing%20%26%20Retrieval&amp;color=9B6F8F&amp;style=flat-square" alt="Writing & Retrieval">

###### Rubric Grader Analysis

> Rubric grader analysis studies the reliability, calibration, robustness, and failure modes of rubric graders used as reward or evaluation signals.

###### 2026
- 🌟 [[arXiv 2026.05](https://arxiv.org/abs/2605.08354)] Auto-Rubric as Reward: From Implicit Preferences to Explicit Multimodal Generative Criteria [[Code](https://github.com/OpenEnvision/AutoRubric-as-Reward)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Vision&amp;color=9A6F7F&amp;style=flat-square" alt="Text + Vision">
- [[arXiv 2026.03](https://arxiv.org/abs/2603.15646)] Alternating Reinforcement Learning with Contextual Rubric Rewards <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization">
- [[arXiv 2026.03](https://arxiv.org/abs/2603.12246)] Examining Reasoning LLMs-as-Judges in Non-Verifiable LLM Post-Training <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">
- [[arXiv 2026.03](https://arxiv.org/abs/2603.11027)] Beyond the Illusion of Consensus: From Surface Heuristics to Knowledge-Grounded Evaluation in LLM-as-a-Judge <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">
- [[arXiv 2026.02](https://arxiv.org/abs/2602.20751)] SibylSense: Adaptive Rubric Learning via Memory Tuning and Adversarial Probing <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.01511)] Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training [[Model](https://huggingface.co/collections/OpenRubrics/rubricarm)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL"> <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.08654)] RULERS: Locked Rubrics and Evidence-Anchored Scoring for Robust LLM Evaluation [[Code](https://github.com/LabRAI/Rulers)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">

###### 2025
- 🌟 [[arXiv 2025.12](https://arxiv.org/abs/2512.23707)] Training AI Co-Scientists Using Rubric Rewards [[Data](https://huggingface.co/datasets/facebook/research-plan-gen)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">
- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.14660)] An Efficient Rubric-based Generative Verifier for Search-Augmented LLMs [[Code](https://github.com/linyue-ma/Search-Gen-V)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">
- 🌟 [[arXiv 2025.03](https://arxiv.org/abs/2503.23989)] Rubric Is All You Need: Improving LLM-Based Code Evaluation With Question-Specific Rubrics [[Code](https://github.com/NimaTorbati/PumaSubmit)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">
- [[ICLR 26](https://openreview.net/forum?id=DrhWTuhtYq)] QuRL: Rubrics As Judge For Open-Ended Question Answering <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">

###### 2024
- 🌟 [[arXiv 2024.10](https://arxiv.org/abs/2410.12784)] JudgeBench: A Benchmark for Evaluating LLM-based Judges [[Code](https://github.com/ScalerLab/JudgeBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">

###### 2023
- 🌟 [[arXiv 2023.06](https://arxiv.org/abs/2306.05685)] Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena [[Code](https://github.com/lm-sys/fastchat)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis">

###### Multi-Objective Optimization

> Multi-objective optimization treats rubric dimensions as separate reward components, balancing competing goals such as correctness, safety, helpfulness, and style.

###### 2026
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.26535)] PAPO: Stabilizing Rubric Integration Training via Decoupled Advantage Normalization [[Code](https://github.com/tanzelin430/PAPO)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization">
- [[arXiv 2026.03](https://arxiv.org/abs/2603.15646)] Alternating Reinforcement Learning with Contextual Rubric Rewards <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization">
- [[arXiv 2026.02](https://arxiv.org/abs/2602.11661)] Quark Medical Alignment: A Holistic Multi-Dimensional Alignment and Collaborative Optimization Paradigm <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.05242)] GDPO: Group reward-Decoupled Normalization Policy Optimization for Multi-reward RL Optimization [[Proj](https://nvlabs.github.io/GDPO/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization">

###### 2025
- 🌟 [[arXiv 2025.11](https://arxiv.org/abs/2511.16139)] Multidimensional Rubric-oriented Reward Model Learning via Geometric Projection Reference Constraints [[Model](https://huggingface.co/mingpinDZJ/Shanzhi-M1)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization">
- 🌟 [[arXiv 2025.08](https://arxiv.org/abs/2508.12790)] Reinforcement Learning with Rubric Anchors [[Model](https://huggingface.co/inclusionAI/Rubicon-Preview)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning">
- [[arXiv 2025.08](https://arxiv.org/abs/2508.07768)] Pareto Multi-Objective Alignment for Language Models <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization">

###### 2024
- 🌟 [[arXiv 2024.06](https://arxiv.org/abs/2406.12845)] Interpretable Preferences via Multi-Objective Reward Modeling and Mixture-of-Experts [[Model](https://huggingface.co/RLHFlow/ArmoRM-Llama3-8B-v0.1)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization">

###### Credit Assignment

> Credit assignment methods distribute rubric feedback from a final answer to intermediate steps, tokens, stages, or features so training receives denser supervision.

###### 2026
- 🌟 [[arXiv 2026.04](https://arxiv.org/abs/2604.02795)] Rubrics to Tokens: Bridging Response-level Rubrics and Token-level Rewards in Instruction Following Tasks [[Code](https://github.com/TURLEing/Rubrics-To-Tokens)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.03800)] A Rubric-Supervised Critic from Sparse Real-World Outcomes [[Code](https://github.com/OpenHands/critic-rubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.12268)] CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use [[Code](https://github.com/namezhenzhang/CM2-RLCR-Tool-Agent)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment"> <img src="https://img.shields.io/static/v1?label=&amp;message=General%20Agentic&amp;color=8B6F9F&amp;style=flat-square" alt="General Agentic">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.10067)] Features as Rewards: Scalable Supervision for Open-Ended Tasks via Interpretability [[Proj](https://www.goodfire.ai/research/rlfr)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.04649)] Outcome Accuracy is Not Enough: Aligning the Reasoning Process of Reward Models [[Code](https://github.com/QwenLM/RationaleRM)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment">
- [[arXiv 2026.02](https://arxiv.org/abs/2602.01791)] Grad2Reward: From Sparse Judgment to Dense Rewards for Improving Open-Ended LLM Reasoning <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.06487)] Technical Report Tongyi DeepResearch [[Code](https://github.com/Alibaba-NLP/qqr)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.06021)] Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards [[Code](https://github.com/THUDM/CaRR)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment"> <img src="https://img.shields.io/static/v1?label=&amp;message=DeepResearch&amp;color=4E6EAD&amp;style=flat-square" alt="DeepResearch">

###### 2025
- 🌟 [[arXiv 2025.12](https://arxiv.org/abs/2512.20491)] Step-DeepResearch Technical Report [[Code](https://github.com/stepfun-ai/StepDeepResearch)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment"> <img src="https://img.shields.io/static/v1?label=&amp;message=DeepResearch&amp;color=4E6EAD&amp;style=flat-square" alt="DeepResearch">
- 🌟 [[arXiv 2025.12](https://arxiv.org/abs/2512.20312)] TableGPT-R1: Advancing Tabular Reasoning Through Reinforcement Learning [[Model](https://huggingface.co/tablegpt/TableGPT-R1)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment">
- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.07774)] Curing Miracle Steps in LLM Mathematical Reasoning with Rubric Rewards [[Code](https://github.com/YouliangYuan/rrm-cure-miracle-steps)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment">
- [[arXiv 2025.06](https://arxiv.org/abs/2506.13351)] Direct Reasoning Optimization: Constrained RL with Token-Level Dense Reward and Rubric-Gated Constraints for Open-ended Tasks <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment">

###### Agent Harness

> Agent harness methods embed rubric-based judges, verifiers, or reward models inside long-horizon agent loops to guide planning, tool use, and process quality.

###### 2026
- [[arXiv 2026.04](https://arxiv.org/abs/2604.14820)] SWE-TRACE: Optimizing Long-Horizon SWE Agents Through Rubric Process Reward Models and Heuristic Test-Time Scaling <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agent%20Harness&amp;color=6B7280&amp;style=flat-square" alt="Agent Harness">
- 🌟 [[arXiv 2026.04](https://arxiv.org/abs/2604.06132)] Claw-Eval: Toward Trustworthy Evaluation of Autonomous Agents [[Proj](https://claw-eval.github.io/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agent%20Harness&amp;color=6B7280&amp;style=flat-square" alt="Agent Harness">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.21362)] AdaRubric: Task-Adaptive Rubrics for Reliable LLM Agent Evaluation and Reward Learning [[Code](https://github.com/alphadl/AdaRubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agent%20Harness&amp;color=6B7280&amp;style=flat-square" alt="Agent Harness"> <img src="https://img.shields.io/static/v1?label=&amp;message=General%20Agentic&amp;color=8B6F9F&amp;style=flat-square" alt="General Agentic">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.04171)] Agentic Rubrics as Contextual Verifiers for SWE Agents [[Proj](https://scale.com/research/agenticrubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agent%20Harness&amp;color=6B7280&amp;style=flat-square" alt="Agent Harness"> <img src="https://img.shields.io/static/v1?label=&amp;message=Code&amp;color=3B82A0&amp;style=flat-square" alt="Code">

###### 2024
- 🌟 [[COLM 24](https://openreview.net/forum?id=NPAQ6FKSmK)] Autonomous Evaluation and Refinement of Digital Agents [[Code](https://github.com/Berkeley-NLP/Agent-Eval-Refine)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agent%20Harness&amp;color=6B7280&amp;style=flat-square" alt="Agent Harness">

##### Rubrics for Advanced Training

> Advanced training methods make rubrics dynamic training instruments, using them as curricula, evolving objectives, or guidance signals rather than fixed scoring sheets.

###### Curriculum Learning

> Curriculum learning methods use rubric structure to order tasks, examples, or reward difficulty from easier criteria to harder ones.

###### 2026
- [[arXiv 2026.02](https://arxiv.org/abs/2602.21628)] RuCL: Stratified Rubric-Based Curriculum Learning for Multimodal Large Language Model Reasoning <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Curriculum%20Learning&amp;color=9A7682&amp;style=flat-square" alt="Curriculum Learning">
- [[arXiv 2026.02](https://arxiv.org/abs/2602.06795)] Generating Data-Driven Reasoning Rubrics for Domain-Adaptive Reward Modeling <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Curriculum%20Learning&amp;color=9A7682&amp;style=flat-square" alt="Curriculum Learning">

###### 2025
- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.15859)] InfiMed-ORBIT: Aligning LLMs on Open-Ended Complex Tasks via Rubric-Based Incremental Training [[Code](https://github.com/pidneuralode/ORBIT)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Curriculum%20Learning&amp;color=9A7682&amp;style=flat-square" alt="Curriculum Learning"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=hXNApWLBZG)] P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling [[Code](https://github.com/Tongyi-ConvAI/Qwen-Character/tree/main/Character-GenRM)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Curriculum%20Learning&amp;color=9A7682&amp;style=flat-square" alt="Curriculum Learning">

###### Self-Evolving Learning

> Self-evolving learning methods let rubrics change during training, using model failures, self-play, memory, or feedback to raise or adjust standards.

###### 2026
- [[arXiv 2026.02](https://arxiv.org/abs/2602.20751)] SibylSense: Adaptive Rubric Learning via Memory Tuning and Adversarial Probing <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.10885)] Reinforcing Chain-of-Thought Reasoning with Self-Evolving Rubrics [[Proj](https://alphalab-ustc.github.io/rlcer-alphalab/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning">
- [[arXiv 2026.02](https://arxiv.org/abs/2602.05125)] Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Iterative%20Refinement&amp;color=5B8FA1&amp;style=flat-square" alt="Iterative Refinement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning">

###### 2025
- 🌟 [[arXiv 2025.11](https://arxiv.org/abs/2511.19399)] DR Tulu: Reinforcement Learning with Evolving Rubrics for Deep Research [[Code](https://github.com/rlresearch/dr-tulu)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning"> <img src="https://img.shields.io/static/v1?label=&amp;message=DeepResearch&amp;color=4E6EAD&amp;style=flat-square" alt="DeepResearch">
- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.07284)] Online Rubrics Elicitation from Pairwise Comparisons [[Proj](https://scale.com/research/onlinerubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning">
- 🌟 [[arXiv 2025.08](https://arxiv.org/abs/2508.12790)] Reinforcement Learning with Rubric Anchors [[Model](https://huggingface.co/inclusionAI/Rubicon-Preview)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning">

###### Hint-Based Learning

> Hint-based learning uses rubrics as scaffolds, critiques, or guidance signals that point the learner toward missing criteria during optimization.

###### 2026
- [[arXiv 2026.05](https://arxiv.org/abs/2605.09269)] DeltaRubric: Generative Multimodal Reward Modeling via Joint Planning and Verification <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Hint-Based%20Learning&amp;color=B07955&amp;style=flat-square" alt="Hint-Based Learning">
- [[arXiv 2026.05](https://arxiv.org/abs/2605.07461)] Think-with-Rubrics: From External Evaluator to Internal Reasoning Guidance <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Hint-Based%20Learning&amp;color=B07955&amp;style=flat-square" alt="Hint-Based Learning">

###### 2025
- [[arXiv 2025.11](https://arxiv.org/abs/2511.12344)] Reward and Guidance through Rubrics: Promoting Exploration to Improve Multi-Domain Reasoning <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Hint-Based%20Learning&amp;color=B07955&amp;style=flat-square" alt="Hint-Based Learning">
- 🌟 [[arXiv 2025.08](https://arxiv.org/abs/2508.16949)] Breaking the Exploration Bottleneck: Rubric-Scaffolded Reinforcement Learning for General LLM Reasoning [[Code](https://github.com/IANNXANG/RuscaRL)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Hint-Based%20Learning&amp;color=B07955&amp;style=flat-square" alt="Hint-Based Learning">

## Inference

> This section covers rubric signals constructed or adapted at test time to guide judging, verification, refinement, or response selection without updating model weights.

### Inference-Time Rubric Supervision

> Inference-time rubric supervision generates or adapts criteria during deployment, using extra test-time computation to decompose, judge, and refine outputs when fixed references are unavailable.

#### 2025

- 🌟 [[arXiv 2025.09](https://arxiv.org/abs/2509.20357)] Language Models that Think, Chat Better [[Code](https://github.com/princeton-pli/RLMT)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Inference-Time%20Rubric%20Supervision&amp;color=4B728A&amp;style=flat-square" alt="Inference-Time Rubric Supervision">
- [[ICML 26](https://arxiv.org/abs/2509.14234)] Compute as Teacher: Turning Inference Compute Into Reference-Free Supervision <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Inference-Time%20Rubric%20Supervision&amp;color=4B728A&amp;style=flat-square" alt="Inference-Time Rubric Supervision">
- 🌟 [[arXiv 2025.04](https://arxiv.org/abs/2504.02495)] Inference-Time Scaling for Generalist Reward Modeling [[Model](https://huggingface.co/collections/BBQGOD/deepseek-grm)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Inference-Time%20Rubric%20Supervision&amp;color=4B728A&amp;style=flat-square" alt="Inference-Time Rubric Supervision">

## Risk

> This section focuses on reward-hacking failures that arise when models optimize against imperfect rubric rewards or rubric-based judges.

### Rubric Reward Hacking

> Rubric reward hacking work studies how models exploit loopholes, misspecified criteria, judge artifacts, or weak reward tails to obtain high rubric scores without genuinely better behavior.

#### 2026

- [[arXiv 2026.05](https://arxiv.org/abs/2605.12474)] Reward Hacking in Rubric-Based Reinforcement Learning <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Reward%20Hacking&amp;color=A24F5F&amp;style=flat-square" alt="Rubric Reward Hacking">
- [[arXiv 2026.04](https://arxiv.org/abs/2604.01375)] RIFT: A RubrIc Failure Mode Taxonomy and Automated Diagnostics <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Reward%20Hacking&amp;color=A24F5F&amp;style=flat-square" alt="Rubric Reward Hacking">
- [[arXiv 2026.03](https://arxiv.org/abs/2603.24586)] Comparing Developer and LLM Biases in Code Evaluation <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Reward%20Hacking&amp;color=A24F5F&amp;style=flat-square" alt="Rubric Reward Hacking">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.13576)] Rubrics as an Attack Surface: Stealthy Preference Drift in LLM Judges [[Code](https://github.com/ZDCSlab/Rubrics-as-an-Attack-Surface)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Reward%20Hacking&amp;color=A24F5F&amp;style=flat-square" alt="Rubric Reward Hacking">
- [[arXiv 2026.02](https://arxiv.org/abs/2602.02219)] Am I More Pointwise or Pairwise? Revealing Position Bias in Rubric-Based LLM-as-a-Judge <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Reward%20Hacking&amp;color=A24F5F&amp;style=flat-square" alt="Rubric Reward Hacking">

#### 2025

- [[arXiv 2025.06](https://arxiv.org/abs/2506.16507)] Robust Reward Modeling via Causal Rubrics <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Reward%20Hacking&amp;color=A24F5F&amp;style=flat-square" alt="Rubric Reward Hacking">

#### 2024

- [[NeurIPS 24](https://arxiv.org/abs/2411.01111)] Rule Based Rewards for Language Model Safety <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Reward%20Hacking&amp;color=A24F5F&amp;style=flat-square" alt="Rubric Reward Hacking">

## Evaluation

> Rubric-based evaluation work introduces benchmarks, datasets, or protocols that make open-ended model behavior comparable through explicit criteria and structured scoring.

### Real-World Tasks

> Real-world task benchmarks evaluate performance in concrete domains where rubric criteria encode professional, institutional, or task-specific standards.

#### Medical

> Medical benchmarks use rubrics to assess health-related accuracy, safety, reasoning, empathy, and usefulness under clinical or expert-informed standards.

##### 2026

- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.13691)] QuarkMedBench: A Real-World Scenario Driven Benchmark for Evaluating Large Language Models [[Code](https://github.com/Quark-Medical/QuarkMedBench_Technical_Report)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- [[arXiv 2026.03](https://arxiv.org/abs/2603.23519)] MedMT-Bench: Can LLMs Memorize and Understand Long Multi-Turn Conversations in Medical Scenarios? <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.10367)] LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation [[Code](https://github.com/ZhilingYan/LiveMedBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- [[arXiv 2026.01](https://arxiv.org/abs/2601.13235)] RubRIX: Rubric-Driven Risk Mitigation in Caregiver-AI Interactions <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- [[arXiv 2026.01](https://arxiv.org/abs/2601.03023)] MedDialogRubrics: A Comprehensive Benchmark and Evaluation Framework for Multi-turn Medical Consultations in Large Language Models <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">

##### 2025

- 🌟 [[arXiv 2025.05](https://arxiv.org/abs/2505.08775)] HealthBench: Evaluating Large Language Models Towards Improved Human Health [[Proj](https://openai.com/index/healthbench/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">

#### Legal

> Legal benchmarks use rubrics to evaluate legal reasoning, issue identification, evidence use, and procedural or substantive correctness.

##### 2026

- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.16669)] PLAW BENCH: A Rubric-Based Benchmark for Evaluating LLMs in Real-World Legal Practice [[Code](https://github.com/SKYLENAGE-AI/PLawBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Legal&amp;color=8A6F8F&amp;style=flat-square" alt="Legal">

##### 2025

- 🌟 [[arXiv 2025.11](https://arxiv.org/abs/2512.01020)] Evaluating Legal Reasoning Traces with Legal Issue Tree Rubrics [[Code](https://github.com/jinulee-v/LEGIT)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Legal&amp;color=8A6F8F&amp;style=flat-square" alt="Legal">

#### Office Labor

> Office labor benchmarks evaluate workplace tasks such as customer service, finance, hiring, productivity, and business workflows where outputs must satisfy operational criteria.

##### 2026

- [[arXiv 2026.03](https://arxiv.org/abs/2603.22744)] LH-Bench: Skill-Grounded Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.07980)] $OneMillion-Bench: How Far are Language Agents from Human Experts? [[Data](https://huggingface.co/datasets/humanlaya-data-lab/OneMillion-Bench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2604.02368)] Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation [[Proj](https://xpert.bytedance.com/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">

##### 2025

- [[arXiv 2025.11](https://arxiv.org/abs/2511.12306)] UpBench: A Dynamically Evolving Real-World Labor-Market Agentic Benchmark Framework Built for Human-Centric AI <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">
- 🌟 [[arXiv 2025.11](https://arxiv.org/abs/2511.11562)] PRBench: Large-Scale Expert Rubrics for Evaluating High-Stakes Professional Reasoning [[Proj](https://scale.com/research/prbench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">
- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.22143)] Benchmarking and Learning Real-World Customer Service Dialogue [[Proj](https://olamind-olabench.github.io/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">
- 🌟 [[ICLR 26](https://arxiv.org/abs/2510.18941)] ProfBench: Multi-Domain Rubrics requiring Professional Knowledge to Answer and Judge [[Code](https://github.com/NVlabs/ProfBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">
- [[arXiv 2025.10](https://arxiv.org/abs/2510.04374)] GDPval: Evaluating AI Model Performance on Real-World Economically Valuable Tasks [[Data](https://huggingface.co/datasets/openai/gdpval)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=nJvgBolRcR)] ExpertLongBench: Benchmarking Language Models on Expert-Level Long-Form Generation Tasks with Structured Checklists [[Proj](https://huggingface.co/spaces/launch/ExpertLongBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider"> <img src="https://img.shields.io/static/v1?label=&amp;message=Office%20Labor&amp;color=A07C58&amp;style=flat-square" alt="Office Labor">

#### Academic

> Academic benchmarks use rubrics to assess educational, scientific, or research tasks where outputs must satisfy discipline-specific correctness and presentation standards.

##### 2026

- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.27646)] PRBench: End-to-end Paper Reproduction in Physics Research [[Code](https://github.com/HET-AGI/PRBench-Eval-Handson)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Academic&amp;color=9A7F55&amp;style=flat-square" alt="Academic">
- [[arXiv 2026.01](https://arxiv.org/abs/2601.21165)] FrontierScience: Evaluating AI's Ability to Perform Expert-Level Scientific Tasks [[Data](https://huggingface.co/datasets/openai/frontierscience/tree/main)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Academic&amp;color=9A7F55&amp;style=flat-square" alt="Academic">

##### 2025

- [[arXiv 2025.12](https://arxiv.org/abs/2512.12220)] TechImage-Bench: Rubric-Based Evaluation for Technical Image Generation <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Academic&amp;color=9A7F55&amp;style=flat-square" alt="Academic">
- 🌟 [[arXiv 2025.04](https://arxiv.org/abs/2504.01848)] PaperBench: Evaluating AI's Ability to Replicate AI Research [[Code](https://github.com/openai/preparedness/tree/main/project/paperbench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Academic&amp;color=9A7F55&amp;style=flat-square" alt="Academic">

#### Deep Research

> Deep research benchmarks evaluate long-form research agents or reports, emphasizing evidence coverage, citation quality, logical support, completeness, and objectivity.

##### 2026

- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.28407)] MiroEval: Benchmarking Multimodal Deep Research Agents in Process and Outcome [[Proj](https://miroeval-ai.github.io/website/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Deep%20Research&amp;color=4C8FA3&amp;style=flat-square" alt="Deep Research">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.08536)] DeepResearch Bench II: Diagnosing Deep Research Agents via Rubrics from Expert Report [[Code](https://github.com/imlrz/DeepResearch-Bench-II)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Deep%20Research&amp;color=4C8FA3&amp;style=flat-square" alt="Deep Research">

##### 2025

- 🌟 [[arXiv 2025.12](https://arxiv.org/abs/2512.17776)] DEER: A Benchmark for Evaluating Deep Research Agents on Expert Report Generation [[Code](https://github.com/hanjanghoon/DEER)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Deep%20Research&amp;color=4C8FA3&amp;style=flat-square" alt="Deep Research">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=ErnvfmSX0P)] ResearchRubrics: A Benchmark of Prompts and Rubrics For Evaluating Deep Research Agents [[Proj](https://labs.scale.com/papers/researchrubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Deep%20Research&amp;color=4C8FA3&amp;style=flat-square" alt="Deep Research">
- 🌟 [[arXiv 2025.06](https://arxiv.org/abs/2506.11763)] DeepResearch Bench: A Comprehensive Benchmark for Deep Research Agents [[Code](https://github.com/Ayanami0730/deep_research_bench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Deep%20Research&amp;color=4C8FA3&amp;style=flat-square" alt="Deep Research">

#### Creative Generation

> Creative generation benchmarks use rubrics to judge open-ended artifacts such as writing, tables, images, or videos along multiple quality dimensions.

##### 2026

- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.07244)] PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation [[Proj](https://presentbench.github.io/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Creative%20Generation&amp;color=A16A5B&amp;style=flat-square" alt="Creative Generation">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.22155)] UEval: A Benchmark for Unified Multimodal Generation [[Proj](https://zlab-princeton.github.io/UEval/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Creative%20Generation&amp;color=A16A5B&amp;style=flat-square" alt="Creative Generation">

##### 2025

- 🌟 [[arXiv 2025.03](https://arxiv.org/abs/2503.05244)] WritingBench: A Comprehensive Benchmark for Generative Writing [[Code](https://github.com/X-PLUG/WritingBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Creative%20Generation&amp;color=A16A5B&amp;style=flat-square" alt="Creative Generation">

##### 2024

- 🌟 [[arXiv 2024.09](https://arxiv.org/abs/2409.16191)] HelloBench: Evaluating Long Text Generation Capabilities of Large Language Models [[Code](https://github.com/Quehry/HelloBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Creative%20Generation&amp;color=A16A5B&amp;style=flat-square" alt="Creative Generation">

### General Capability Evaluation

> General capability benchmarks test transferable abilities with rubric-based protocols, abstracting away from a single professional domain.

#### Agentic

> Agentic benchmarks evaluate planning, tool use, environment interaction, and long-horizon decision making with rubric-guided or process-aware assessment.

##### 2026

- [[arXiv 2026.03](https://arxiv.org/abs/2603.01357)] ASTRA-bench: Evaluating Tool-Use Agent Reasoning and Action Planning with Personal User Context <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agentic&amp;color=4B5563&amp;style=flat-square" alt="Agentic">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.11199)] When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification [[Code](https://github.com/jialeuuz/askbench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agentic&amp;color=4B5563&amp;style=flat-square" alt="Agentic">

##### 2025

- [[arXiv 2025.10](https://arxiv.org/abs/2510.04550)] TRAJECT-Bench: A Trajectory-Aware Benchmark for Evaluating Agentic Tool Use [[Data](https://huggingface.co/datasets/bigboss24/TRAJECT-Bench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agentic&amp;color=4B5563&amp;style=flat-square" alt="Agentic">
- 🌟 [[arXiv 2025.08](https://arxiv.org/abs/2508.14704)] MCP-Universe: Benchmarking Large Language Models with Real-World Model Context Protocol Servers [[Code](https://github.com/SalesforceAIResearch/MCP-Universe)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agentic&amp;color=4B5563&amp;style=flat-square" alt="Agentic">

##### 2024

- 🌟 [[NeurIPS 24](https://arxiv.org/abs/2401.13178)] AgentBoard: An Analytical Evaluation Board of Multi-turn LLM Agents [[Proj](https://hkust-nlp.github.io/agentboard/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agentic&amp;color=4B5563&amp;style=flat-square" alt="Agentic">

#### Reasoning

> Reasoning benchmarks use rubrics to assess reasoning quality when answers involve partial credit, social or moral concepts, explanations, or hard-to-verify intermediate logic.

##### 2025

- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.16380)] MoReBench: Evaluating Procedural and Pluralistic Moral Reasoning in Language Models, More than Outcomes [[Proj](https://morebench.github.io/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Reasoning&amp;color=6F5AA5&amp;style=flat-square" alt="Reasoning">

##### 2024

- 🌟 [[arXiv 2024.07](https://arxiv.org/abs/2407.08733)] Is Your Model Really A Good Math Reasoner? Evaluating Mathematical Reasoning with Checklist [[Code](https://github.com/PremiLab-Math/MathCheck)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Reasoning&amp;color=6F5AA5&amp;style=flat-square" alt="Reasoning">

#### Alignment

> Alignment benchmarks assess whether models or judges follow intended preferences, instructions, safety constraints, and consistency principles under explicit criteria.

##### 2026

- [[arXiv 2026.03](https://arxiv.org/abs/2603.25133)] RubricEval: A Rubric-Level Meta-Evaluation Benchmark for LLM Judges in Instruction Following <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.01562)] RubricBench: Aligning Model-Generated Rubrics with Human Standards [[Code](https://github.com/planepig/rubricbench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Provider&amp;color=7B6F86&amp;style=flat-square" alt="Expert Provider"> <img src="https://img.shields.io/static/v1?label=&amp;message=Human-AI%20Collaboration&amp;color=5F8791&amp;style=flat-square" alt="Human-AI Collaboration"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[LREC 26](https://arxiv.org/abs/2603.10303)] Is this Idea Novel? An Automated Benchmark for Judgment of Research Ideas [[Code](https://github.com/TimSchopf/RINoBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.08654)] From Rubrics to Reliable Scores: Evidence-Grounded Text Evaluation with LLM Judges [[Code](https://anonymous.4open.science/r/Rulers_0525-3328/README.md)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=ST0wOB1bdX)] mR3: Multilingual Rubric-Agnostic Reward Reasoning Models [[Code](https://github.com/rubricreward/mr3)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Supervised%20Fine-Tuning&amp;color=9A7B5F&amp;style=flat-square" alt="Supervised Fine-Tuning"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[ICLR 26](https://openreview.net/forum?id=1ZqJ6jj75q)] RM-R1: Reward Modeling as Reasoning [[Proj](https://rm-r1-uiuc.github.io/rmr1-site/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Supervised%20Fine-Tuning&amp;color=9A7B5F&amp;style=flat-square" alt="Supervised Fine-Tuning"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- [[ICLR 26](https://openreview.net/forum?id=QOWYX3Q2XS)] MENLO: From Preferences to Proficiency – Evaluating and Modeling Native-like Quality Across 47 Languages [[Data](https://huggingface.co/datasets/facebook/menlo)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">

##### 2025

- 🌟 [[arXiv 2025.11](https://arxiv.org/abs/2511.10507)] AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following [[Code](https://github.com/facebookresearch/AdvancedIF)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Expert%20Requirement&amp;color=5F8A75&amp;style=flat-square" alt="Expert Requirement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[NeurIPS 25](https://arxiv.org/abs/2503.07539)] XIFBench: Evaluating Large Language Models on Multilingual Instruction Following [[Code](https://github.com/zhenyuli801/XIFBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[arXiv 2025.01](https://arxiv.org/abs/2501.17399)] MultiChallenge: A Realistic Multi-Turn Conversation Evaluation Benchmark Challenging to Frontier LLMs [[Code](https://github.com/ekwinox117/multi-challenge)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[NeurIPS 25](https://arxiv.org/abs/2507.02833)] Generalizing Verifiable Instruction Following [[Code](https://github.com/allenai/IFBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[arXiv 2025.05](https://arxiv.org/abs/2505.13388)] R3: Robust Rubric-Agnostic Reward Models [[Code](https://github.com/rubricreward/r3)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Supervised%20Fine-Tuning&amp;color=9A7B5F&amp;style=flat-square" alt="Supervised Fine-Tuning"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
##### 2024

- 🌟 [[EMNLP 24](https://arxiv.org/abs/2501.15595)] SedarEval: Automated Evaluation using Self-Adaptive Rubrics [[Code](https://github.com/wwn1233/sedareval)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[arXiv 2024.10](https://arxiv.org/abs/2410.15553)] Multi-IF: Benchmarking LLMs on Multi-Turn and Multilingual Instructions Following [[Code](https://github.com/facebookresearch/Multi-IF)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[ICLR 25](https://arxiv.org/abs/2410.12784)] JudgeBench: A Benchmark for Evaluating LLM-based Judges [[Code](https://github.com/ScalerLab/JudgeBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[arXiv 2024.02](https://arxiv.org/abs/2402.10260)] A StrongREJECT for Empty Jailbreaks [[Proj](https://strong-reject.readthedocs.io/en/latest/)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
- 🌟 [[arXiv 2024.01](https://arxiv.org/abs/2401.03601)] InFoBench: Evaluating Instruction Following Ability in Large Language Models [[Code](https://github.com/qinyiwei/InfoBench)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Alignment&amp;color=9B6B6B&amp;style=flat-square" alt="Alignment">
## Applications

> Applications use rubrics as practical task interfaces: they guide generation, evaluation, training, or refinement in concrete systems rather than only proposing benchmarks.

### Domain

> Domain applications apply rubrics within specific task settings such as healthcare, writing, retrieval, deep research, code, and agent workflows.

#### Medical

> Medical applications use rubrics to align healthcare models with clinical reasoning, patient safety, expert preferences, and domain-specific response standards.

##### 2026

- 🌟 [[CVPR 26](https://arxiv.org/abs/2603.06366)] OralGPT-Plus: Learning to Use Visual Tools via Reinforcement Learning for Panoramic X-ray Analysis [[Code](https://github.com/isjinghao/OralGPT)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.09653)] ClinAlign: Scaling Healthcare Alignment from Clinician Preference [[Code](https://github.com/AQ-MedAI/ClinAlign)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Human-AI%20Collaboration&amp;color=5F8791&amp;style=flat-square" alt="Human-AI Collaboration"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- [[arXiv 2026.02](https://arxiv.org/abs/2602.11661)] Quark Medical Alignment: A Holistic Multi-Dimensional Alignment and Collaborative Optimization Paradigm <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Multi-Objective%20Optimization&amp;color=806F95&amp;style=flat-square" alt="Multi-Objective Optimization"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- [[arXiv 2026.01](https://arxiv.org/abs/2601.18706)] Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Iterative%20Refinement&amp;color=5B8FA1&amp;style=flat-square" alt="Iterative Refinement"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">

##### 2025

- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.15859)] InfiMed-ORBIT: Aligning LLMs on Open-Ended Complex Tasks via Rubric-Based Incremental Training [[Code](https://github.com/pidneuralode/ORBIT)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Curriculum%20Learning&amp;color=9A7682&amp;style=flat-square" alt="Curriculum Learning"> <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">
- 🌟 [[arXiv 2025.09](https://arxiv.org/abs/2509.02208)] Baichuan-M2: Scaling Medical Capability with Large Verifier System [[Code](https://github.com/baichuan-inc/Baichuan-M2-32B)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Medical&amp;color=4F9D8A&amp;style=flat-square" alt="Medical">

#### Writing and Retrieval

> Writing and retrieval applications use rubrics to guide text generation, revision, explanation, document retrieval, and automated assessment of written outputs.

##### 2025

- 🌟 [[arXiv 2025.09](https://arxiv.org/abs/2509.24869)] Retro*: Optimizing LLMs for Reasoning-Intensive Document Retrieval  [[Code](https://huggingface.co/collections/ljw13/retro-star)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Writing%20%26%20Retrieval&amp;color=9B6F8F&amp;style=flat-square" alt="Writing & Retrieval">
- [[arXiv 2025.08](https://arxiv.org/abs/2508.03990)] Are Today's LLMs Ready to Explain Well-Being Concepts? <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Writing%20%26%20Retrieval&amp;color=9B6F8F&amp;style=flat-square" alt="Writing & Retrieval">

##### 2024

- 🌟 [[ACL 24](https://aclanthology.org/2024.acl-long.745/)] LLM-Rubric: A Multidimensional, Calibrated Approach to Automated Evaluation of Natural Language Texts [[Code](https://github.com/microsoft/LLM-Rubric)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Writing%20%26%20Retrieval&amp;color=9B6F8F&amp;style=flat-square" alt="Writing & Retrieval">
- [[ICTIR 24](https://openreview.net/forum?id=b6TSaRWbvg)] Pencils Down! Automatic Rubric-based Evaluation of Retrieve/Generate Systems <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Writing%20%26%20Retrieval&amp;color=9B6F8F&amp;style=flat-square" alt="Writing & Retrieval">

#### DeepResearch

> DeepResearch applications use rubrics to supervise search, evidence chaining, report generation, and long-horizon research-agent optimization.

##### 2026

- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.03619)] Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation [[Model](https://huggingface.co/fdu-lcz/rubric_generator)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Pairs-Grounded%20Generation&amp;color=9A8A58&amp;style=flat-square" alt="Pairs-Grounded Generation"> <img src="https://img.shields.io/static/v1?label=&amp;message=DeepResearch&amp;color=4E6EAD&amp;style=flat-square" alt="DeepResearch">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.06021)] Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards [[Code](https://github.com/THUDM/CaRR)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment"> <img src="https://img.shields.io/static/v1?label=&amp;message=DeepResearch&amp;color=4E6EAD&amp;style=flat-square" alt="DeepResearch">

##### 2025

- 🌟 [[arXiv 2025.12](https://arxiv.org/abs/2512.20491)] Step-DeepResearch Technical Report [[Code](https://github.com/stepfun-ai/StepDeepResearch)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment"> <img src="https://img.shields.io/static/v1?label=&amp;message=DeepResearch&amp;color=4E6EAD&amp;style=flat-square" alt="DeepResearch">
- 🌟 [[arXiv 2025.11](https://arxiv.org/abs/2511.19399)] DR Tulu: Reinforcement Learning with Evolving Rubrics for Deep Research [[Code](https://github.com/rlresearch/dr-tulu)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Judgement%20Pattern&amp;color=6D7FA3&amp;style=flat-square" alt="Rubric Judgement Pattern"> <img src="https://img.shields.io/static/v1?label=&amp;message=Self-Evolving%20Learning&amp;color=5F6F89&amp;style=flat-square" alt="Self-Evolving Learning"> <img src="https://img.shields.io/static/v1?label=&amp;message=DeepResearch&amp;color=4E6EAD&amp;style=flat-square" alt="DeepResearch">

#### Code

> Code applications apply rubrics to software engineering agents, patch evaluation, code collaboration, and programming workflows.

##### 2026

- [[arXiv 2026.03](https://arxiv.org/abs/2603.02637)] StitchCUDA: An Automated Multi-Agents End-to-End GPU Programing Framework with Rubric-based Agentic Reinforcement Learning <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Code&amp;color=3B82A0&amp;style=flat-square" alt="Code">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.04171)] Agentic Rubrics as Contextual Verifiers for SWE Agents [[Proj](https://scale.com/research/agenticrubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agent%20Harness&amp;color=6B7280&amp;style=flat-square" alt="Agent Harness"> <img src="https://img.shields.io/static/v1?label=&amp;message=Code&amp;color=3B82A0&amp;style=flat-square" alt="Code">

#### General Agentic

> General agentic applications use rubrics to coordinate, evaluate, or train agents across tool use, simulated worlds, interviews, and other open-ended environments.

##### 2026

- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.21362)] AdaRubric: Task-Adaptive Rubrics for Reliable LLM Agent Evaluation and Reward Learning [[Code](https://github.com/alphadl/AdaRubrics)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Agent%20Harness&amp;color=6B7280&amp;style=flat-square" alt="Agent Harness"> <img src="https://img.shields.io/static/v1?label=&amp;message=General%20Agentic&amp;color=8B6F9F&amp;style=flat-square" alt="General Agentic">
- 🌟 [[arXiv 2026.02](https://arxiv.org/abs/2602.12268)] CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use [[Code](https://github.com/namezhenzhang/CM2-RLCR-Tool-Agent)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Credit%20Assignment&amp;color=64748B&amp;style=flat-square" alt="Credit Assignment"> <img src="https://img.shields.io/static/v1?label=&amp;message=General%20Agentic&amp;color=8B6F9F&amp;style=flat-square" alt="General Agentic">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.22511)] Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards [[Code](https://github.com/haruhi-sudo/SYNTHAGENT)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=General%20Agentic&amp;color=8B6F9F&amp;style=flat-square" alt="General Agentic">
- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2601.06487)] ArenaRL: Scaling RL for Open-Ended Agents via Tournament-based Relative Ranking [[Code](https://github.com/Alibaba-NLP/qqr)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=General%20Agentic&amp;color=8B6F9F&amp;style=flat-square" alt="General Agentic">
- [[arXiv 2026.01](https://arxiv.org/abs/2601.03555)] SCRIBE: Structured Mid-Level Supervision for Tool-Using Language Models <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=General%20Agentic&amp;color=8B6F9F&amp;style=flat-square" alt="General Agentic">

##### 2025

- [[arXiv 2025.12](https://arxiv.org/abs/2512.06196)] ARCANE: A Multi-Agent Framework for Interpretable and Configurable Alignment <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=General%20Agentic&amp;color=8B6F9F&amp;style=flat-square" alt="General Agentic">

### Multimodal

> Multimodal applications extend rubric supervision beyond text, using criteria to assess or train systems that combine language with vision, speech, or omni-modal signals.

#### Text + Vision

> Text-and-vision applications use rubrics for image or video generation, captioning, visual reasoning, and visual reward modeling.

##### 2026

- 🌟 [[arXiv 2026.05](https://arxiv.org/abs/2605.08354)] Auto-Rubric as Reward: From Implicit Preferences to Explicit Multimodal Generative Criteria [[Code](https://github.com/OpenEnvision/AutoRubric-as-Reward)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Rubric%20Grader%20Analysis&amp;color=8A7A5F&amp;style=flat-square" alt="Rubric Grader Analysis"> <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Vision&amp;color=9A6F7F&amp;style=flat-square" alt="Text + Vision">
- [[arXiv 2026.04](https://arxiv.org/abs/2604.13029)] Visual Preference Optimization with Rubric Rewards <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Preference-Reward%20RL&amp;color=7F6B9B&amp;style=flat-square" alt="Preference-Reward RL"> <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Vision&amp;color=9A6F7F&amp;style=flat-square" alt="Text + Vision">
- 🌟 [[arXiv 2026.03](https://arxiv.org/abs/2603.16600)] Rationale Matters: Learning Transferable Rubrics via Proxy-Guided Critique for VLM Reward Models [[Code](https://github.com/Qwen-Applications/Proxy-GRM)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Vision&amp;color=9A6F7F&amp;style=flat-square" alt="Text + Vision">
- [[arXiv 2026.03](https://arxiv.org/abs/2603.09160)] RubiCap: Rubric-Guided Reinforcement Learning for Dense Image Captioning <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Vision&amp;color=9A6F7F&amp;style=flat-square" alt="Text + Vision">

##### 2025

- [[arXiv 2025.11](https://arxiv.org/abs/2511.20651)] RubricRL: Simple Generalizable Rewards for Text-to-Image Generation <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Vision&amp;color=9A6F7F&amp;style=flat-square" alt="Text + Vision">
- 🌟 [[arXiv 2025.10](https://arxiv.org/abs/2510.14738)] AutoRubric: Rubric-Based Generative Rewards for Faithful Multimodal Reasoning [[Code](https://github.com/Jill0001/AutoRubric-R1V)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Vision&amp;color=9A6F7F&amp;style=flat-square" alt="Text + Vision">

#### Text + Audio

> Text-and-audio applications use rubrics to evaluate or fine-tune speech-language systems across multiple raters, aspects, and quality dimensions.

##### 2026

- [[arXiv 2026.03](https://arxiv.org/abs/2603.16889)] Rubric-Guided Fine-tuning of SpeechLLMs for Multi-Aspect, Multi-Rater L2 Reading-Speech Assessment <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Audio&amp;color=6B8F8F&amp;style=flat-square" alt="Text + Audio">

##### 2025

- 🌟 [[ACL 26](https://arxiv.org/abs/2510.14664)] SpeechLLM-as-Judges: Towards General and Interpretable Speech Quality Evaluation [[Code](https://github.com/NKU-HLT/SpeechLLM-as-Judges)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Text%20%2B%20Audio&amp;color=6B8F8F&amp;style=flat-square" alt="Text + Audio">

#### Omni-modal

> Omni-modal applications use rubric-grounded preference or reward modeling across multiple modalities within a unified training or evaluation framework.

##### 2026

- 🌟 [[arXiv 2026.01](https://arxiv.org/abs/2602.00846)] Omni-RRM: Advancing Omni Reward Modeling via Automatic Rubric-Grounded Preference Synthesis [[Code](https://anonymous.4open.science/r/Omni-RRM-CC08)] <br>
  <img src="https://img.shields.io/static/v1?label=&amp;message=Omni-modal&amp;color=5E548E&amp;style=flat-square" alt="Omni-modal">





## LICENSE
This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Contact
If you have any questions or suggestions, please feel free to contact [Hongru Xiao](mailto:hongru_xiao@tongji.edu.cn).



