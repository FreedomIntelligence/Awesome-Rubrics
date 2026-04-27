# Awesome-Rubric [![Survey Paper](https://img.shields.io/badge/%F0%9F%93%84%20Survey%20Paper-Coming%20soon-blue)](#) [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity) [![PR's Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](http://makeapullrequest.com)

**Overview.** This repository provides a curated reading list for **rubric-based learning, reward data, modeling, and evaluation of large models**. It emphasizes how explicit criteria are used to build data, guide post-training, design reward signals, and evaluate open-ended model behavior.

Papers with publicly released code or project resources include an inline `[[Code](...)]` link. Entries without verified repositories omit that link.

> Contributions are welcome. If you find missing papers, inaccurate classifications, or newly released code, feel free to update this list.

<!-- ![rubric overview](imgs/rubric_readme.png) -->

## Table of Contents

- [Basics](#basics)
  - [Definitions](#basicsdefinitions)
  - [Format](#basicsformat)
  - [Traditional Domain Usage](#basicstraditional-domain-usage)
  - [Why Introduce Large Models](#basicswhy-introduce-large-models)
- [Rubrics in the Era of Large Models](#rubrics-in-the-era-of-large-models)
  - [Data](#data)
    - [Synthetic Data](#synthetic-data)
    - [Real Data](#real-data)
  - [Training](#training)
    - [Pre-training](#pre-training)
    - [Post-training](#post-training)
      - [Post-training-SFT](#post-training-sft)
      - [Post-training-OPD&DPO](#post-training-opddpo)
      - [Post-training-RL Algorithm Optimization](#post-training-rl-algorithm-optimization)
      - [Post-training-Reward Signal Optimization](#post-training-reward-signal-optimization)
      - [Post-training-Curriculum Learning](#post-training-curriculum-learning)
      - [Post-training-Self-evolution](#post-training-self-evolution)
  - [Evaluation](#evaluation)
    - [Evaluation Methods](#evaluation-methods)
    - [Evaluation Benchmarks](#evaluation-benchmarks)
- [Practical Application of Rubrics](#practical-application-of-rubrics)
  - [By Modality](#by-modality)
    - [Modality-Text](#modality-text)
    - [Modality-Visual](#modality-visual)
    - [Modality-Sound](#modality-sound)
  - [By Domain](#by-domain)
    - [Domain-Medical](#domain-medical)
    - [Domain-Code](#domain-code)
    - [Domain-Agent](#domain-agent)

## Basics

This part introduces what rubrics are, how they are represented, and why structured criteria become useful once model outputs move beyond single-answer correctness.

### Basics/Definitions

Rubrics define structured evaluation dimensions, scoring rules, and judgment boundaries for open-ended model outputs. This section covers work that clarifies what counts as a rubric and how rubrics function as judges or reward criteria.

#### 2026
- [[arXiv 2026.02](https://arxiv.org/abs/2602.05125)] Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks
- [[ICLR](https://openreview.net/forum?id=DrhWTuhtYq)] QuRL: Rubrics As Judge For Open-Ended Question Answering
- [[ICLR](https://openreview.net/forum?id=c1bTcrDmt4)] Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains
- [[ICLR](https://openreview.net/forum?id=oP99JQiDYp)] Robust Reward Modeling via Causal Rubrics

#### 2025
- [[arXiv 2025.10](https://arxiv.org/abs/2510.17314)] Auto-Rubric: Learning From Implicit Weights to Explicit Rubrics for Reward Modeling
- [[arXiv 2025.10](https://arxiv.org/abs/2510.17314)] From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling

### Basics/Format

This section focuses on how rubrics are expressed, including dimensions, levels, weights, and scoring templates. It is useful for understanding the representational form that makes rubric-based supervision reusable and controllable.


#### 2026
- [[arXiv 2026.03](https://arxiv.org/abs/2603.07019)] AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge
- [[ICLR](https://openreview.net/forum?id=c1bTcrDmt4)] Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains

#### 2025
- [[arXiv 2025.10](https://arxiv.org/abs/2510.17314)] From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling

### Basics/Traditional Domain Usage

- No retained papers after full-text justification review.

### Why Introduce Large Models

#### 2026
- [[ICLR](https://openreview.net/forum?id=pBjy4ek2QV)] Chasing the Tail: Effective Rubric-based Reward Modeling for Large Language Model Post-Training [[Code](https://github.com/Jun-Kai-Zhang/rubrics)]

## Rubrics in the Era of Large Models

### Data

#### Synthetic Data

Synthetic data uses generated tasks, labels, critiques, or rubric annotations to expand supervision beyond limited human labeling. In Rubric RL, it is especially useful when rubric-style feedback can be programmatically produced at scale.

#### 2026

- [[arXiv 2026.02](https://arxiv.org/abs/2602.09653)] ClinAlign: Scaling Healthcare Alignment from Clinician Preference [[Code](https://github.com/AQ-MedAI/ClinAlign)]
- [[arXiv 2026.01](https://arxiv.org/abs/2601.22511)] Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards [[Code](https://github.com/haruhi-sudo/SYNTHAGENT)]
- [[ICLR](https://openreview.net/forum?id=vFcm5sOitq)] OptimSyn: Influence-Guided Rubrics Optimization for Synthetic Data Generation [[Code](https://github.com/FanZT6/OptimSyn)]

#### 2025
- [[arXiv 2025.10](https://arxiv.org/abs/2510.07743)] OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment [[Code](https://huggingface.co/datasets/OpenRubrics/OpenRubrics)]


#### Real Data

Real data refers to rubric signals grounded in human preferences, authentic interactions, or expert annotations. These sources are important when alignment targets depend on nuanced human standards that are hard to synthesize fully.

#### 2026

- [[arXiv 2026.04](https://arxiv.org/abs/2604.02368)] Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation [[Code](https://github.com/randomtutu/Xpertbench)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.07244)] PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation [[Code](https://github.com/PresentBench/PresentBench)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.27646)] PRBench: End-to-end Paper Reproduction in Physics Research [[Code](https://github.com/HET-AGI/PRBench-Eval-Handson)]
- [[arXiv 2026.01](https://arxiv.org/abs/2601.18706)] Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs
- [[ICLR](https://openreview.net/forum?id=QOWYX3Q2XS)] MENLO: From Preferences to Proficiency �C Evaluating and Modeling Native-like Quality Across 47 Languages [[Code](https://huggingface.co/datasets/facebook/menlo)]

#### 2025

- [[arXiv 2025.10](https://arxiv.org/abs/2510.22143)] Benchmarking and Learning Real-World Customer Service Dialogue
- [[arXiv 2025.05](https://arxiv.org/abs/2505.08775)] HealthBench: Evaluating Large Language Models Towards Improved Human Health [[Code](https://github.com/openai/simple-evals)]

### Training

#### Pre-training

- No retained papers after full-text justification review.

#### Post-training

##### Post-training-SFT

Rubrics can be used in supervised fine-tuning for filtering data, weighting samples, or imposing structured response preferences. This makes SFT more aligned with multi-dimensional quality targets instead of flat imitation alone.

#### 2026
- [[ICLR](https://openreview.net/forum?id=hXNApWLBZG)] P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling

#### 2025
- [[arXiv 2025.08](https://arxiv.org/abs/2508.03990)] Are Today's LLMs Ready to Explain Well-Being Concepts?

##### Post-training-OPD&DPO

#### 2026
- [[arXiv 2026.03](https://arxiv.org/abs/2603.21362)] AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation

#### 2025
- [[arXiv 2025.10](https://arxiv.org/abs/2510.07743)] OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment
- [[arXiv 2025.08](https://arxiv.org/abs/2508.03990)] Are Today's LLMs Ready to Explain Well-Being Concepts?
- [[arXiv 2025.09](https://arxiv.org/abs/2509.22638)] Language Models Can Learn from Verbal Feedback Without Scalar Rewards [[Code](https://github.com/sail-sg/feedback-conditional-policy)]
- [[ICML-W](https://openreview.net/forum?id=seA8en4ujl)] Configurable Preference Tuning with Rubric-Guided Synthetic Data

##### Post-training-RL Algorithm Optimization

This section covers preference optimization methods that incorporate fine-grained rubric signals rather than only pairwise global preferences. Rubrics help make preference learning more controllable, interpretable, and task-adaptive.

#### 2026
- [[arXiv 2026.01](https://arxiv.org/abs/2601.05242)] GDPO: Group reward-Decoupled Normalization Policy Optimization for Multi-reward RL Optimization [[Code](https://github.com/NVlabs/GDPO)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.15646)] Alternating Reinforcement Learning with Contextual Rubric Rewards
- [[arXiv 2026.03](https://arxiv.org/abs/2603.20046)] Experience is the Best Teacher: Motivating Effective Exploration in Reinforcement Learning for LLMs
- [[arXiv 2026.03](https://arxiv.org/abs/2603.26535)] PAPO: Stabilizing Rubric Integration Training via Decoupled Advantage Normalization
- [[arXiv 2026.01](https://arxiv.org/abs/2601.06021)] Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards [[Code](https://github.com/THUDM/CaRR)]
- [[arXiv 2026.01](https://arxiv.org/abs/2601.15160)] Knowledge Graphs are Implicit Reward Models: Path-Derived Signals Enable Compositional Reasoning [[Code](https://github.com/yuvalkansal/kg_si_rl)]
- [[arXiv 2026.02](https://arxiv.org/abs/2602.01511)] Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training
- [[arXiv 2026.02](https://arxiv.org/abs/2602.07594)] Learning to Self-Verify Makes Language Models Better Reasoners
- [[arXiv 2026.02](https://arxiv.org/abs/2602.08321)] Improving Data and Reward Design for Scientific Reasoning in Large Language Models
- [[arXiv 2026.02](https://arxiv.org/abs/2602.11199)] When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification [[Code](https://github.com/jialeuuz/askbench)]
- [[arXiv 2026.02](https://arxiv.org/abs/2602.12268)] CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use
- [[arXiv 2026.02](https://arxiv.org/abs/2602.14069)] Open Rubric System: Scaling Reinforcement Learning with Pairwise Adaptive Rubric [[Code](https://github.com/Qwen-Applications/OpenRS)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.03197)] Specificity-aware reinforcement learning for fine-grained open-world classification [[Code](https://github.com/s-angheben/SpeciaRL)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.15434)] Listening to the Echo: User-Reaction Aware Policy Optimization via Scalar-Verbal Hybrid Reinforcement Learning
- [[arXiv 2026.04](https://arxiv.org/abs/2604.02795)] Rubrics to Tokens: Bridging Response-level Rubrics and Token-level Rewards in Instruction Following Tasks [[Code](https://github.com/TURLEing/Rubrics-To-Tokens)]

#### 2025
- [[arXiv 2025.08](https://arxiv.org/abs/2508.07768)] Pareto Multi-Objective Alignment for Language Models
- [[arXiv 2025.06](https://arxiv.org/abs/2506.08123)] QA-LIGN: Aligning LLMs through Constitutionally Decomposed QA
- [[arXiv 2025.06](https://arxiv.org/abs/2506.13351)] Direct Reasoning Optimization: Constrained RL with Token-Level Dense Reward and Rubric-Gated Constraints for Open-ended Tasks
- [[arXiv 2025.07](https://arxiv.org/abs/2507.17746)] Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains
- [[arXiv 2025.08](https://arxiv.org/abs/2508.12790)] Reinforcement Learning with Rubric Anchors
- [[arXiv 2025.08](https://arxiv.org/abs/2508.16949)] Breaking the Exploration Bottleneck: Rubric-Scaffolded Reinforcement Learning for General LLM Reasoning
- [[arXiv 2025.09](https://arxiv.org/abs/2509.22611)] Quantile Advantage Estimation: Stabilizing RLVR for LLM Reasoning
- [[arXiv 2025.10](https://arxiv.org/abs/2510.11184)] Reinforcement Learning for Tool-Integrated Interleaved Thinking towards Cross-Domain Generalization
- [[arXiv 2025.10](https://arxiv.org/abs/2510.14738)] AutoRubric-R1V: Rubric-Based Generative Reward for Vision-Language Reasoning
- [[arXiv 2025.10](https://arxiv.org/abs/2510.15859)] InfiMed-ORBIT: Aligning LLMs on Open-Ended Complex Tasks via Rubric-Based Incremental Training
- [[arXiv 2025.11](https://arxiv.org/abs/2511.10507)] AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following
- [[arXiv 2025.11](https://arxiv.org/abs/2511.12344)] Reward and Guidance through Rubrics: Promoting Exploration to Improve Multi-Domain Reasoning
- [[arXiv 2025.12](https://arxiv.org/abs/2512.20312)] TableGPT-R1: Advancing Tabular Reasoning Through Reinforcement Learning

##### Post-training-Reward Signal Optimization

This section centers on designing better rubric-based rewards, critics, and judges after initial model training. It includes work on reward shaping, judge calibration, rubric generation, and converting high-level criteria into usable learning signals.

#### 2026
- [[arXiv 2026.01](https://arxiv.org/abs/2601.08430)] RubricHub: A Comprehensive and Highly Discriminative Rubric Dataset via Automated Coarse-to-Fine Generation [[Code](https://github.com/teqkilla/RubricHub)]
- [[arXiv 2026.02](https://arxiv.org/abs/2602.01511)] Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training
- [[arXiv 2026.02](https://arxiv.org/abs/2602.14069)] Open Rubric System: Scaling Reinforcement Learning with Pairwise Adaptive Rubric [[Code](https://github.com/Qwen-Applications/OpenRS)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.08035)] CDRRM: Contrast-Driven Rubric Generation for Reliable and Interpretable Reward Modeling
- [[arXiv 2026.04](https://arxiv.org/abs/2604.02795)] Rubrics to Tokens: Bridging Response-level Rubrics and Token-level Rewards in Instruction Following Tasks [[Code](https://github.com/TURLEing/Rubrics-To-Tokens)]
- [[arXiv 2026.01](https://arxiv.org/abs/2601.02986)] P-Check: Advancing Personalized Reward Models via Learning to Generate Dynamic Checklists
- [[arXiv 2026.01](https://arxiv.org/abs/2601.07149)] Rewarding Creativity: A Human-Aligned Generative Reward Model for Reinforcement Learning in Storytelling
- [[arXiv 2026.01](https://arxiv.org/abs/2601.11374)] Reward Modeling for Scientific Writing Evaluation
- [[arXiv 2026.02](https://arxiv.org/abs/2602.00846)] OMNI-RRM: Advancing Omni Reward Model
- [[arXiv 2026.02](https://arxiv.org/abs/2602.01791)] Grad2Reward: From Sparse Judgment to Dense Rewards for Improving Open-Ended LLM Reasoning
- [[arXiv 2026.02](https://arxiv.org/abs/2602.03619)] Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation
- [[arXiv 2026.02](https://arxiv.org/abs/2602.05125)] Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks
- [[arXiv 2026.02](https://arxiv.org/abs/2602.10067)] Features as Rewards: Scalable Supervision for Open-Ended Tasks via Interpretability
- [[arXiv 2026.02](https://arxiv.org/abs/2602.20751)] SibylSense: Adaptive Rubric Learning via Memory Tuning and Adversarial Probing
- [[arXiv 2026.03](https://arxiv.org/abs/2603.01562)] RubricBench: Aligning Model-Generated Rubrics with Human Standards [[Code](https://github.com/planepig/rubricbench)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.07019)] AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge
- [[arXiv 2026.03](https://arxiv.org/abs/2603.20882)] RubricRAG: Towards Interpretable and Reliable LLM Evaluation via Domain Knowledge Retrieval for Rubric Generation
- [[ICLR](https://openreview.net/forum?id=dBmjnRR1bC)] Reinforcement Learning from Dynamic Critic Feedback for Free-Form Generations

#### 2025
- [[arXiv 2025.06](https://arxiv.org/abs/2506.15651)] AutoRule: Reasoning Chain-of-Thought Extracted Rule-Based Rewards Improve Preference Learning [[Code](https://github.com/cxcscmu/AutoRule)]
- [[arXiv 2025.08](https://arxiv.org/abs/2508.12790)] Reinforcement Learning with Rubric Anchors
- [[arXiv 2025.10](https://arxiv.org/abs/2510.07743)] OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment
- [[arXiv 2025.05](https://arxiv.org/abs/2505.13388)] R3: Robust Rubric-Agnostic Reward Models
- [[arXiv 2025.10](https://arxiv.org/abs/2510.17314)] From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling
- [[NeurIPS](https://openreview.net/forum?id=RPRqKhjrr6)] Checklists Are Better Than Reward Models For Aligning Language Models

##### Post-training-Curriculum Learning

Curriculum learning studies how rubric dimensions or difficulty levels can stage training over time. It is relevant when structured feedback is used not only to score outputs but also to organize learning progression.

#### 2026
- [[arXiv 2026.02](https://arxiv.org/abs/2602.21628)] RuCL: Stratified Rubric-Based Curriculum Learning for Multimodal Large Language Model Reasoning
- [[ICLR](https://openreview.net/forum?id=hXNApWLBZG)] P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling [[Code](https://github.com/Tongyi-ConvAI/Qwen-Character/tree/main/Character-GenRM)]

##### Post-training-Self-evolution

#### 2026
- [[arXiv 2026.02](https://arxiv.org/abs/2602.10885)] Reinforcing Chain-of-Thought Reasoning with Self-Evolving Rubrics

### Evaluation

#### Evaluation Methods

Evaluation methods focus on how rubrics are used to judge outputs reliably and consistently across tasks. This includes LLM-as-a-judge settings, rubric-aware reward reasoning, and methods that improve interpretability of evaluation.

#### 2026
- [[arXiv 2026.03](https://arxiv.org/abs/2603.08035)] CDRRM: Contrast-Driven Rubric Generation for Reliable and Interpretable Reward Modeling
- [[arXiv 2026.03](https://arxiv.org/abs/2603.20882)] RubricRAG: Towards Interpretable and Reliable LLM Evaluation via Domain Knowledge Retrieval for Rubric Generation
- [[arXiv 2026.03](https://arxiv.org/abs/2603.21362)] AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation
- [[arXiv 2026.01](https://arxiv.org/abs/2601.08654)] RULERS: Locked Rubrics and Evidence-Anchored Scoring for Robust LLM Evaluation
- [[arXiv 2026.02](https://arxiv.org/abs/2602.05125)] Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks
- [[arXiv 2026.02](https://arxiv.org/abs/2602.10367)] LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation
- [[arXiv 2026.02](https://arxiv.org/abs/2602.13576)] Rubrics as an Attack Surface: Stealthy Preference Drift in LLM Judges [[Code](https://github.com/ZDCSlab/Rubrics-as-an-Attack-Surface)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.01562)] RubricBench: Aligning Model-Generated Rubrics with Human Standards [[Code](https://github.com/planepig/rubricbench)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.07019)] AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge
- [[arXiv 2026.03](https://arxiv.org/abs/2603.11027)] Beyond the Illusion of Consensus: From Surface Heuristics to Knowledge-Grounded Evaluation in LLM-as-a-Judge
- [[arXiv 2026.03](https://arxiv.org/abs/2603.12246)] Examining Reasoning LLMs-as-Judges in Non-Verifiable LLM Post-Training
- [[arXiv 2026.03](https://arxiv.org/abs/2603.25133)] RUBRIC EVAL: A Rubric-Level Meta-Evaluation Benchmark for LLM Judges in Instruction Following
- [[ICLR](https://openreview.net/forum?id=ST0wOB1bdX)] mR3: Multilingual Rubric-Agnostic Reward Reasoning Models [[Code](https://github.com/rubricreward/mr3)]
- [[ICLR](https://openreview.net/forum?id=PTXi3Ef4sT)] Don't Pass@$k$: A Bayesian Framework for Large Language Model Evaluation
- [[ICLR](https://openreview.net/forum?id=0WGl8PNMSA)] Retro: Optimizing LLMs for Reasoning-Intensive Document Retrieval
- [[ICLR](https://openreview.net/forum?id=1ZqJ6jj75q)] RM-R1: Reward Modeling as Reasoning
- [[ICLR](https://openreview.net/forum?id=QOWYX3Q2XS)] MENLO: From Preferences to Proficiency - Evaluating and Modeling Native-like Quality Across 47 Languages

#### 2025
- [[arXiv 2025.05](https://arxiv.org/abs/2505.13388)] R3: Robust Rubric-Agnostic Reward Models
- [[arXiv 2025.10](https://arxiv.org/abs/2510.12712)] Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception
- [[arXiv 2025.10](https://arxiv.org/abs/2510.17314)] From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling

#### Evaluation Benchmarks

Benchmark work provides datasets and tasks where rubric-based evaluation can be compared, stress-tested, and standardized. These resources are important for measuring whether rubric-trained or rubric-judged systems generalize across realistic scenarios.

#### 2026
- [[arXiv 2026.03](https://arxiv.org/abs/2603.07980)] $OneMillion-Bench: How Far are Language Agents from Human Experts? [[Code](https://github.com/humanlaya/OneMillion-Bench)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.10303)] Is this Idea Novel? An Automated Benchmark for Judgment of Research Ideas [[Code](https://github.com/TimSchopf/RINoBench)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.22744)] Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks
- [[arXiv 2026.03](https://arxiv.org/abs/2603.28407)] MiroEval: Benchmarking Multimodal Deep Research Agents in Process and Outcome [[Code](https://github.com/MiroMindAI/MiroEval)]
- [[arXiv 2026.04](https://arxiv.org/abs/2604.02368)] Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation [[Code](https://github.com/randomtutu/Xpertbench)]
- [[arXiv 2026.01](https://arxiv.org/abs/2601.14569)] SOCIAL CAPTION: Evaluating Social Understanding in Multimodal Models
- [[arXiv 2026.01](https://arxiv.org/abs/2601.16669)] PL AW BENCH: A Rubric-Based Benchmark for Evaluating LLMs in Real-World Legal Practice [[Code](https://github.com/SKYLENAGE-AI/PLawBench)] 
- [[arXiv 2026.01](https://arxiv.org/abs/2601.21165)] Frontier Science: Evaluating AI's Ability to Perform Expert-Level Scientific Tasks
- [[arXiv 2026.01](https://arxiv.org/abs/2601.22155)] UEval: A Benchmark for Unified Multimodal Generation [[Code](https://github.com/zlab-princeton/UEval)]
- [[arXiv 2026.02](https://arxiv.org/abs/2602.10367)] LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation [[Code](https://github.com/ZhilingYan/LiveMedBench)]
- [[arXiv 2026.02](https://arxiv.org/abs/2602.11199)] When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification [[Code](https://github.com/jialeuuz/askbench)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.01562)] RubricBench: Aligning Model-Generated Rubrics with Human Standards [[Code](https://github.com/planepig/rubricbench)]
- [[ICLR](https://openreview.net/forum?id=7pQv7qitFV)] MicroVerse: A Preliminary Exploration Toward a Micro-World Simulation [[Code](https://github.com/FreedomIntelligence/MicroVerse)]
- [[ICLR](https://openreview.net/forum?id=VwNzKPqBxk)] ProfBench: Multi-Domain Rubrics requiring Professional Knowledge to Answer and Judge
- [[ICLR](https://openreview.net/forum?id=nJvgBolRcR)] ExpertLongBench: Benchmarking Language Models on Expert-Level Long-Form Generation Tasks with Structured Checklists [[Code](https://huggingface.co/datasets/launch/ExpertLongBench)]

#### 2025
- [[arXiv 2025.07](https://arxiv.org/abs/2507.02833)] Generalizing Verifiable Instruction Following
- [[arXiv 2025.11](https://arxiv.org/abs/2511.10507)] AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following
- [[arXiv 2025.05](https://arxiv.org/abs/2505.08775)] HealthBench: Evaluating Large Language Models Towards Improved Human Health
- [[arXiv 2025.10](https://arxiv.org/abs/2510.04374)] GDPval: Evaluating AI Model Performance on Real-World Economically Valuable Tasks
- [[arXiv 2025.10](https://arxiv.org/abs/2510.16380)] MoreBench: Evaluating Procedural and Pluralistic Reasoning
- [[arXiv 2025.11](https://arxiv.org/abs/2511.07685)] RESEARCH RUBRICS: A Benchmark of Prompts and Rubrics For Evaluating Deep Research Agents [[Code](https://github.com/scaleapi/researchrubrics)]
- [[arXiv 2025.12](https://arxiv.org/abs/2512.01020)] Evaluating Legal Reasoning Traces with Legal Issue Tree Rubrics

## Practical Application of Rubrics

Applications grouped by modality and domain, highlighting where rubrics help capture quality, safety, and task completion.

### By Modality

#### Modality-Text

This section covers rubric use in text generation, dialogue, and reasoning-heavy language tasks. The emphasis is on how structured criteria guide evaluation or training for open-ended textual outputs.

#### 2026
- [[arXiv 2026.01](https://arxiv.org/abs/2601.07149)] Rewarding Creativity: A Human-Aligned Generative Reward Model for Reinforcement Learning in Storytelling
- [[arXiv 2026.03](https://arxiv.org/abs/2603.15434)] Listening to the Echo: User-Reaction Aware Policy Optimization via Scalar-Verbal Hybrid Reinforcement Learning
- [[ICLR](https://openreview.net/forum?id=ugZKZ8vufv)] The CoT Encyclopedia: Analyzing, Predicting, and Controlling how a Reasoning Model will Think

#### 2025
- [[arXiv 2025.08](https://arxiv.org/abs/2508.03990)] Are Today��s LLMs Ready to Explain Well-Being Concepts?
- [[arXiv 2025.09](https://arxiv.org/abs/2509.22638)] Language Models Can Learn from Verbal Feedback Without Scalar Rewards [[Code](https://github.com/sail-sg/feedback-conditional-policy)]
- [[arXiv 2025.10](https://arxiv.org/abs/2510.22143)] Benchmarking and Learning Real-World Customer Service Dialogue
- [[arXiv 2025.12](https://arxiv.org/abs/2512.01020)] Evaluating Legal Reasoning Traces with Legal Issue Tree Rubrics

#### Modality-Visual

Visual rubric work extends structured judging and reward design to images, videos, and vision-language tasks. It is useful when model quality depends on multiple perceptual and semantic dimensions rather than a single scalar objective.

#### 2026
- [[arXiv 2026.03](https://arxiv.org/abs/2603.09160)] RubiCap: Rubric-Guided Reinforcement Learning for Dense Image Captioning
- [[arXiv 2026.03](https://arxiv.org/abs/2603.16600)] Rationale Matters: Learning Transferable Rubrics via Proxy-Guided Critique for VLM Reward Models
- [[arXiv 2026.01](https://arxiv.org/abs/2601.14569)] SOCIAL CAPTION: Evaluating Social Understanding in Multimodal Models
- [[arXiv 2026.03](https://arxiv.org/abs/2603.05659)] When Rubrics Fail: Error Enumeration as Reward in Reference-Free RL Post-Training for Virtual Try-On
- [[ICLR](https://openreview.net/forum?id=7pQv7qitFV)] MicroVerse: A Preliminary Exploration Toward a Micro-World Simulation [[Code](https://github.com/FreedomIntelligence/MicroVerse)]

#### 2025
- [[arXiv 2025.09](https://arxiv.org/abs/2509.22647)] CAP RL: S TIMULATING DENSE IMAGE CAPTION CAPA-
- [[arXiv 2025.10](https://arxiv.org/abs/2510.12712)] Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception
- [[arXiv 2025.11](https://arxiv.org/abs/2511.20651)] RubricRL: Simple Generalizable Rewards for Text-to-Image Generation

#### Modality-Sound

- No retained papers after full-text justification review.

### By Domain

#### Domain-Medical

Medical applications use rubrics to capture expert standards, safety expectations, and multi-step clinical reasoning quality. This is important because medical evaluation often cannot be reduced to single-answer correctness.

#### 2026
- [[arXiv 2026.02](https://arxiv.org/abs/2602.09653)] ClinAlign: Scaling Healthcare Alignment from Clinician Preference [[Code](https://github.com/AQ-MedAI/ClinAlign)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.13691)] QuarkMedBench: A Real-World Scenario Driven Benchmark for Evaluating Large Language Models [[Code](https://github.com/Quark-Medical/QuarkMedBench_Technical_Report)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.23519)] MedMT-Bench: Can LLMs Memorize and Understand Long Multi-Turn Conversations in Medical Scenarios?
- [[arXiv 2026.04](https://arxiv.org/abs/2604.00024)] WHBench: A Women��s Health Benchmark for Evaluating Frontier LLMs with Expert-in-the-Loop Validation
- [[arXiv 2026.01](https://arxiv.org/abs/2601.13235)] RubRIX: Rubric-Driven Risk Mitigation in Caregiver-AI Interactions
- [[arXiv 2026.01](https://arxiv.org/abs/2601.18706)] Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs
- [[arXiv 2026.02](https://arxiv.org/abs/2602.10367)] LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation
- [[arXiv 2026.02](https://arxiv.org/abs/2602.11661)] Quark Medical Alignment: A Holistic Multi-Dimensional Alignment and Collaborative Optimization Paradigm

#### 2025
- [[arXiv 2025.09](https://arxiv.org/abs/2509.02208)] Baichuan-M2: Scaling Medical Capability with Large Verifier System
- [[arXiv 2025.05](https://arxiv.org/abs/2505.08775)] HealthBench: Evaluating Large Language Models Towards Improved Human Health
- [[arXiv 2025.10](https://arxiv.org/abs/2510.15859)] InfiMed-ORBIT: Aligning LLMs on Open-Ended Complex Tasks via Rubric-Based Incremental Training

#### Domain-Code

Code-domain rubric work studies structured evaluation for coding, debugging, and software-agent behavior.

#### 2026
- [[arXiv 2026.01](https://arxiv.org/abs/2601.04171)] Agentic Rubrics as Contextual Verifiers for SWE Agents

#### Domain-Agent

Agent settings require rubrics to evaluate long-horizon behavior, tool use, planning, and subjective task completion. This section highlights work where structured criteria are central to assessing or training interactive agents.

#### 2026
- [[arXiv 2026.01](https://arxiv.org/abs/2601.06487)] Technical Report Tongyi DeepResearch [[Code](https://github.com/Alibaba-NLP/qqr)]
- [[arXiv 2026.01](https://arxiv.org/abs/2601.06021)] Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards [[Code](https://github.com/THUDM/CaRR)]
- [[arXiv 2026.01](https://arxiv.org/abs/2601.22511)] Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards [[Code](https://github.com/haruhi-sudo/SYNTHAGENT)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.07244)] PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation [[Code](https://github.com/PresentBench/PresentBench)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.21362)] AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation [[Code](https://github.com/alphadl/AdaRubrics)]
- [[arXiv 2026.03](https://arxiv.org/abs/2603.22744)] Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks
- [[arXiv 2026.03](https://arxiv.org/abs/2603.27646)] PRBench: End-to-end Paper Reproduction in Physics Research [[Code](https://github.com/HET-AGI/PRBench-Eval-Handson)]
- [[arXiv 2026.02](https://arxiv.org/abs/2602.03619)] Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation
- [[arXiv 2026.02](https://arxiv.org/abs/2602.11199)] When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification [[Code](https://github.com/jialeuuz/askbench)]
- [[arXiv 2026.02](https://arxiv.org/abs/2602.12268)] CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use [[Code](https://github.com/namezhenzhang/CM2-RLCR-Tool-Agent)]
- [[arXiv 2026.04](https://arxiv.org/abs/2604.02368)] Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation [[Code](https://github.com/randomtutu/Xpertbench)]

#### 2025
- [[arXiv 2025.10](https://arxiv.org/abs/2510.11184)] Reinforcement Learning for Tool-Integrated Interleaved Thinking towards Cross-Domain Generalization
- [[arXiv 2025.10](https://arxiv.org/abs/2510.12712)] Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception
- [[arXiv 2025.12](https://arxiv.org/abs/2512.06196)] ARCANE: A Multi-Agent Framework for Interpretable and Configurable Alignment
- [[arXiv 2025.12](https://arxiv.org/abs/2512.20491)] Step-DeepResearch Technical Report [[Code](https://github.com/stepfun-ai/StepDeepResearch)]
- [[NeurIPS-W](https://openreview.net/forum?id=be76fus1ou)] Towards Real-World Evaluation of Agentic Work in Freelance Marketplaces

## LICENSE
This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Contact
If you have any questions or suggestions, please feel free to contact [Hongru Xiao](mailto:hongru_xiao@tongji.edu.cn).


