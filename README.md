# Awesome-Rubric [![Survey Paper](https://img.shields.io/badge/%F0%9F%93%84%20Survey%20Paper-Coming%20soon-blue)](#) [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity) [![PR's Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](http://makeapullrequest.com)

**Overview.** This repository provides a curated reading list for **rubric-based learning, reward data, modeling, and evaluation of large models**. It emphasizes how explicit criteria are used to build data, guide post-training, design reward signals, and evaluate open-ended model behavior.

Papers with publicly released code or project resources appear in the `Source` column. Entries without verified repositories use `-` in that column. All paper tables use the same `18/64/18` column layout for steadier GitHub rendering.

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

### Basics/Definitions
> Rubrics define structured evaluation dimensions, scoring rules, and judgment boundaries for open-ended model outputs. This section covers work that clarifies what counts as a rubric and how rubrics function as judges or reward criteria.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.05125">arXiv 2026.02</a></td>
      <td width="64%">Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=DrhWTuhtYq">ICLR</a></td>
      <td width="64%">QuRL: Rubrics As Judge For Open-Ended Question Answering</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=c1bTcrDmt4">ICLR</a></td>
      <td width="64%">Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=oP99JQiDYp">ICLR</a></td>
      <td width="64%">Robust Reward Modeling via Causal Rubrics</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td width="64%">Auto-Rubric: Learning From Implicit Weights to Explicit Rubrics for Reward Modeling</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td width="64%">From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

### Basics/Format

> This section focuses on how rubrics are expressed, including dimensions, levels, weights, and scoring templates. It is useful for understanding the representational form that makes rubric-based supervision reusable and controllable.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.07019">arXiv 2026.03</a></td>
      <td width="64%">AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=c1bTcrDmt4">ICLR</a></td>
      <td width="64%">Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td width="64%">From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

### Basics/Traditional Domain Usage

- No retained papers after full-text justification review.

### Why Introduce Large Models

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=pBjy4ek2QV">ICLR</a></td>
      <td width="64%">Chasing the Tail: Effective Rubric-based Reward Modeling for Large Language Model Post-Training</td>
      <td width="18%"><a href="https://github.com/Jun-Kai-Zhang/rubrics">Code</a></td>
    </tr>
  </tbody>
</table>

## Rubrics in the Era of Large Models

### Data

#### Synthetic Data

> Synthetic data uses generated tasks, labels, critiques, or rubric annotations to expand supervision beyond limited human labeling. In Rubric RL, it is especially useful when rubric-style feedback can be programmatically produced at scale.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.09653">arXiv 2026.02</a></td>
      <td width="64%">ClinAlign: Scaling Healthcare Alignment from Clinician Preference</td>
      <td width="18%"><a href="https://github.com/AQ-MedAI/ClinAlign">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.22511">arXiv 2026.01</a></td>
      <td width="64%">Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards</td>
      <td width="18%"><a href="https://github.com/haruhi-sudo/SYNTHAGENT">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=vFcm5sOitq">ICLR</a></td>
      <td width="64%">OptimSyn: Influence-Guided Rubrics Optimization for Synthetic Data Generation</td>
      <td width="18%"><a href="https://github.com/FanZT6/OptimSyn">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.07743">arXiv 2025.10</a></td>
      <td width="64%">OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment</td>
      <td width="18%"><a href="https://huggingface.co/datasets/OpenRubrics/OpenRubrics">Code</a></td>
    </tr>
  </tbody>
</table>

#### Real Data

> Real data refers to rubric signals grounded in human preferences, authentic interactions, or expert annotations. These sources are important when alignment targets depend on nuanced human standards that are hard to synthesize fully.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2604.02368">arXiv 2026.04</a></td>
      <td width="64%">Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation</td>
      <td width="18%"><a href="https://github.com/randomtutu/Xpertbench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.07244">arXiv 2026.03</a></td>
      <td width="64%">PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation</td>
      <td width="18%"><a href="https://github.com/PresentBench/PresentBench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.27646">arXiv 2026.03</a></td>
      <td width="64%">PRBench: End-to-end Paper Reproduction in Physics Research</td>
      <td width="18%"><a href="https://github.com/HET-AGI/PRBench-Eval-Handson">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.18706">arXiv 2026.01</a></td>
      <td width="64%">Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=QOWYX3Q2XS">ICLR</a></td>
      <td width="64%">MENLO: From Preferences to Proficiency - Evaluating and Modeling Native-like Quality Across 47 Languages</td>
      <td width="18%"><a href="https://huggingface.co/datasets/facebook/menlo">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.22143">arXiv 2025.10</a></td>
      <td width="64%">Benchmarking and Learning Real-World Customer Service Dialogue</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2505.08775">arXiv 2025.05</a></td>
      <td width="64%">HealthBench: Evaluating Large Language Models Towards Improved Human Health</td>
      <td width="18%"><a href="https://github.com/openai/simple-evals">Code</a></td>
    </tr>
  </tbody>
</table>

### Training

#### Pre-training

- No retained papers after full-text justification review.

#### Post-training

##### Post-training-SFT

> Rubrics can be used in supervised fine-tuning for filtering data, weighting samples, or imposing structured response preferences. This makes SFT more aligned with multi-dimensional quality targets instead of flat imitation alone.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=hXNApWLBZG">ICLR</a></td>
      <td width="64%">P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2508.03990">arXiv 2025.08</a></td>
      <td width="64%">Are Today's LLMs Ready to Explain Well-Being Concepts?</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

##### Post-training-OPD&DPO

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.21362">arXiv 2026.03</a></td>
      <td width="64%">AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.07743">arXiv 2025.10</a></td>
      <td width="64%">OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2508.03990">arXiv 2025.08</a></td>
      <td width="64%">Are Today's LLMs Ready to Explain Well-Being Concepts?</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2509.22638">arXiv 2025.09</a></td>
      <td width="64%">Language Models Can Learn from Verbal Feedback Without Scalar Rewards</td>
      <td width="18%"><a href="https://github.com/sail-sg/feedback-conditional-policy">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=seA8en4ujl">ICML-W</a></td>
      <td width="64%">Configurable Preference Tuning with Rubric-Guided Synthetic Data</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

##### Post-training-RL Algorithm Optimization

> This section covers preference optimization methods that incorporate fine-grained rubric signals rather than only pairwise global preferences. Rubrics help make preference learning more controllable, interpretable, and task-adaptive.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.05242">arXiv 2026.01</a></td>
      <td width="64%">GDPO: Group reward-Decoupled Normalization Policy Optimization for Multi-reward RL Optimization</td>
      <td width="18%"><a href="https://github.com/NVlabs/GDPO">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.15646">arXiv 2026.03</a></td>
      <td width="64%">Alternating Reinforcement Learning with Contextual Rubric Rewards</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.20046">arXiv 2026.03</a></td>
      <td width="64%">Experience is the Best Teacher: Motivating Effective Exploration in Reinforcement Learning for LLMs</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.26535">arXiv 2026.03</a></td>
      <td width="64%">PAPO: Stabilizing Rubric Integration Training via Decoupled Advantage Normalization</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.06021">arXiv 2026.01</a></td>
      <td width="64%">Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards</td>
      <td width="18%"><a href="https://github.com/THUDM/CaRR">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.15160">arXiv 2026.01</a></td>
      <td width="64%">Knowledge Graphs are Implicit Reward Models: Path-Derived Signals Enable Compositional Reasoning</td>
      <td width="18%"><a href="https://github.com/yuvalkansal/kg_si_rl">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.01511">arXiv 2026.02</a></td>
      <td width="64%">Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.07594">arXiv 2026.02</a></td>
      <td width="64%">Learning to Self-Verify Makes Language Models Better Reasoners</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.08321">arXiv 2026.02</a></td>
      <td width="64%">Improving Data and Reward Design for Scientific Reasoning in Large Language Models</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.11199">arXiv 2026.02</a></td>
      <td width="64%">When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification</td>
      <td width="18%"><a href="https://github.com/jialeuuz/askbench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.12268">arXiv 2026.02</a></td>
      <td width="64%">CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.14069">arXiv 2026.02</a></td>
      <td width="64%">Open Rubric System: Scaling Reinforcement Learning with Pairwise Adaptive Rubric</td>
      <td width="18%"><a href="https://github.com/Qwen-Applications/OpenRS">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.03197">arXiv 2026.03</a></td>
      <td width="64%">Specificity-aware reinforcement learning for fine-grained open-world classification</td>
      <td width="18%"><a href="https://github.com/s-angheben/SpeciaRL">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.15434">arXiv 2026.03</a></td>
      <td width="64%">Listening to the Echo: User-Reaction Aware Policy Optimization via Scalar-Verbal Hybrid Reinforcement Learning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2604.02795">arXiv 2026.04</a></td>
      <td width="64%">Rubrics to Tokens: Bridging Response-level Rubrics and Token-level Rewards in Instruction Following Tasks</td>
      <td width="18%"><a href="https://github.com/TURLEing/Rubrics-To-Tokens">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2508.07768">arXiv 2025.08</a></td>
      <td width="64%">Pareto Multi-Objective Alignment for Language Models</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2506.08123">arXiv 2025.06</a></td>
      <td width="64%">QA-LIGN: Aligning LLMs through Constitutionally Decomposed QA</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2506.13351">arXiv 2025.06</a></td>
      <td width="64%">Direct Reasoning Optimization: Constrained RL with Token-Level Dense Reward and Rubric-Gated Constraints for Open-ended Tasks</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2507.17746">arXiv 2025.07</a></td>
      <td width="64%">Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2508.12790">arXiv 2025.08</a></td>
      <td width="64%">Reinforcement Learning with Rubric Anchors</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2508.16949">arXiv 2025.08</a></td>
      <td width="64%">Breaking the Exploration Bottleneck: Rubric-Scaffolded Reinforcement Learning for General LLM Reasoning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2509.22611">arXiv 2025.09</a></td>
      <td width="64%">Quantile Advantage Estimation: Stabilizing RLVR for LLM Reasoning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.11184">arXiv 2025.10</a></td>
      <td width="64%">Reinforcement Learning for Tool-Integrated Interleaved Thinking towards Cross-Domain Generalization</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.14738">arXiv 2025.10</a></td>
      <td width="64%">AutoRubric-R1V: Rubric-Based Generative Reward for Vision-Language Reasoning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.15859">arXiv 2025.10</a></td>
      <td width="64%">InfiMed-ORBIT: Aligning LLMs on Open-Ended Complex Tasks via Rubric-Based Incremental Training</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2511.10507">arXiv 2025.11</a></td>
      <td width="64%">AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2511.12344">arXiv 2025.11</a></td>
      <td width="64%">Reward and Guidance through Rubrics: Promoting Exploration to Improve Multi-Domain Reasoning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2512.20312">arXiv 2025.12</a></td>
      <td width="64%">TableGPT-R1: Advancing Tabular Reasoning Through Reinforcement Learning</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

##### Post-training-Reward Signal Optimization

> This section centers on designing better rubric-based rewards, critics, and judges after initial model training. It includes work on reward shaping, judge calibration, rubric generation, and converting high-level criteria into usable learning signals.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.08430">arXiv 2026.01</a></td>
      <td width="64%">RubricHub: A Comprehensive and Highly Discriminative Rubric Dataset via Automated Coarse-to-Fine Generation</td>
      <td width="18%"><a href="https://github.com/teqkilla/RubricHub">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.01511">arXiv 2026.02</a></td>
      <td width="64%">Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.14069">arXiv 2026.02</a></td>
      <td width="64%">Open Rubric System: Scaling Reinforcement Learning with Pairwise Adaptive Rubric</td>
      <td width="18%"><a href="https://github.com/Qwen-Applications/OpenRS">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.08035">arXiv 2026.03</a></td>
      <td width="64%">CDRRM: Contrast-Driven Rubric Generation for Reliable and Interpretable Reward Modeling</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2604.02795">arXiv 2026.04</a></td>
      <td width="64%">Rubrics to Tokens: Bridging Response-level Rubrics and Token-level Rewards in Instruction Following Tasks</td>
      <td width="18%"><a href="https://github.com/TURLEing/Rubrics-To-Tokens">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.02986">arXiv 2026.01</a></td>
      <td width="64%">P-Check: Advancing Personalized Reward Models via Learning to Generate Dynamic Checklists</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.07149">arXiv 2026.01</a></td>
      <td width="64%">Rewarding Creativity: A Human-Aligned Generative Reward Model for Reinforcement Learning in Storytelling</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.11374">arXiv 2026.01</a></td>
      <td width="64%">Reward Modeling for Scientific Writing Evaluation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.00846">arXiv 2026.02</a></td>
      <td width="64%">OMNI-RRM: Advancing Omni Reward Model</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.01791">arXiv 2026.02</a></td>
      <td width="64%">Grad2Reward: From Sparse Judgment to Dense Rewards for Improving Open-Ended LLM Reasoning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.03619">arXiv 2026.02</a></td>
      <td width="64%">Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.05125">arXiv 2026.02</a></td>
      <td width="64%">Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.10067">arXiv 2026.02</a></td>
      <td width="64%">Features as Rewards: Scalable Supervision for Open-Ended Tasks via Interpretability</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.20751">arXiv 2026.02</a></td>
      <td width="64%">SibylSense: Adaptive Rubric Learning via Memory Tuning and Adversarial Probing</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.01562">arXiv 2026.03</a></td>
      <td width="64%">RubricBench: Aligning Model-Generated Rubrics with Human Standards</td>
      <td width="18%"><a href="https://github.com/planepig/rubricbench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.07019">arXiv 2026.03</a></td>
      <td width="64%">AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.20882">arXiv 2026.03</a></td>
      <td width="64%">RubricRAG: Towards Interpretable and Reliable LLM Evaluation via Domain Knowledge Retrieval for Rubric Generation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=dBmjnRR1bC">ICLR</a></td>
      <td width="64%">Reinforcement Learning from Dynamic Critic Feedback for Free-Form Generations</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2506.15651">arXiv 2025.06</a></td>
      <td width="64%">AutoRule: Reasoning Chain-of-Thought Extracted Rule-Based Rewards Improve Preference Learning</td>
      <td width="18%"><a href="https://github.com/cxcscmu/AutoRule">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2508.12790">arXiv 2025.08</a></td>
      <td width="64%">Reinforcement Learning with Rubric Anchors</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.07743">arXiv 2025.10</a></td>
      <td width="64%">OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2505.13388">arXiv 2025.05</a></td>
      <td width="64%">R3: Robust Rubric-Agnostic Reward Models</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td width="64%">From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=RPRqKhjrr6">NeurIPS</a></td>
      <td width="64%">Checklists Are Better Than Reward Models For Aligning Language Models</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

##### Post-training-Curriculum Learning

> Curriculum learning studies how rubric dimensions or difficulty levels can stage training over time. It is relevant when structured feedback is used not only to score outputs but also to organize learning progression.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.21628">arXiv 2026.02</a></td>
      <td width="64%">RuCL: Stratified Rubric-Based Curriculum Learning for Multimodal Large Language Model Reasoning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=hXNApWLBZG">ICLR</a></td>
      <td width="64%">P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling</td>
      <td width="18%"><a href="https://github.com/Tongyi-ConvAI/Qwen-Character/tree/main/Character-GenRM">Code</a></td>
    </tr>
  </tbody>
</table>

##### Post-training-Self-evolution

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.10885">arXiv 2026.02</a></td>
      <td width="64%">Reinforcing Chain-of-Thought Reasoning with Self-Evolving Rubrics</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

### Evaluation

#### Evaluation Methods

> Evaluation methods focus on how rubrics are used to judge outputs reliably and consistently across tasks. This includes LLM-as-a-judge settings, rubric-aware reward reasoning, and methods that improve interpretability of evaluation.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.08035">arXiv 2026.03</a></td>
      <td width="64%">CDRRM: Contrast-Driven Rubric Generation for Reliable and Interpretable Reward Modeling</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.20882">arXiv 2026.03</a></td>
      <td width="64%">RubricRAG: Towards Interpretable and Reliable LLM Evaluation via Domain Knowledge Retrieval for Rubric Generation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.21362">arXiv 2026.03</a></td>
      <td width="64%">AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.08654">arXiv 2026.01</a></td>
      <td width="64%">RULERS: Locked Rubrics and Evidence-Anchored Scoring for Robust LLM Evaluation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.05125">arXiv 2026.02</a></td>
      <td width="64%">Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.10367">arXiv 2026.02</a></td>
      <td width="64%">LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.13576">arXiv 2026.02</a></td>
      <td width="64%">Rubrics as an Attack Surface: Stealthy Preference Drift in LLM Judges</td>
      <td width="18%"><a href="https://github.com/ZDCSlab/Rubrics-as-an-Attack-Surface">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.01562">arXiv 2026.03</a></td>
      <td width="64%">RubricBench: Aligning Model-Generated Rubrics with Human Standards</td>
      <td width="18%"><a href="https://github.com/planepig/rubricbench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.07019">arXiv 2026.03</a></td>
      <td width="64%">AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.11027">arXiv 2026.03</a></td>
      <td width="64%">Beyond the Illusion of Consensus: From Surface Heuristics to Knowledge-Grounded Evaluation in LLM-as-a-Judge</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.12246">arXiv 2026.03</a></td>
      <td width="64%">Examining Reasoning LLMs-as-Judges in Non-Verifiable LLM Post-Training</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.25133">arXiv 2026.03</a></td>
      <td width="64%">RUBRIC EVAL: A Rubric-Level Meta-Evaluation Benchmark for LLM Judges in Instruction Following</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=ST0wOB1bdX">ICLR</a></td>
      <td width="64%">mR3: Multilingual Rubric-Agnostic Reward Reasoning Models</td>
      <td width="18%"><a href="https://github.com/rubricreward/mr3">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=PTXi3Ef4sT">ICLR</a></td>
      <td width="64%">Don't Pass@$k$: A Bayesian Framework for Large Language Model Evaluation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=0WGl8PNMSA">ICLR</a></td>
      <td width="64%">Retro: Optimizing LLMs for Reasoning-Intensive Document Retrieval</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=1ZqJ6jj75q">ICLR</a></td>
      <td width="64%">RM-R1: Reward Modeling as Reasoning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=QOWYX3Q2XS">ICLR</a></td>
      <td width="64%">MENLO: From Preferences to Proficiency - Evaluating and Modeling Native-like Quality Across 47 Languages</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2505.13388">arXiv 2025.05</a></td>
      <td width="64%">R3: Robust Rubric-Agnostic Reward Models</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.12712">arXiv 2025.10</a></td>
      <td width="64%">Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td width="64%">From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### Evaluation Benchmarks

> Benchmark work provides datasets and tasks where rubric-based evaluation can be compared, stress-tested, and standardized. These resources are important for measuring whether rubric-trained or rubric-judged systems generalize across realistic scenarios.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.07980">arXiv 2026.03</a></td>
      <td width="64%">$OneMillion-Bench: How Far are Language Agents from Human Experts?</td>
      <td width="18%"><a href="https://github.com/humanlaya/OneMillion-Bench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.10303">arXiv 2026.03</a></td>
      <td width="64%">Is this Idea Novel? An Automated Benchmark for Judgment of Research Ideas</td>
      <td width="18%"><a href="https://github.com/TimSchopf/RINoBench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.22744">arXiv 2026.03</a></td>
      <td width="64%">Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.28407">arXiv 2026.03</a></td>
      <td width="64%">MiroEval: Benchmarking Multimodal Deep Research Agents in Process and Outcome</td>
      <td width="18%"><a href="https://github.com/MiroMindAI/MiroEval">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2604.02368">arXiv 2026.04</a></td>
      <td width="64%">Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation</td>
      <td width="18%"><a href="https://github.com/randomtutu/Xpertbench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.14569">arXiv 2026.01</a></td>
      <td width="64%">SOCIAL CAPTION: Evaluating Social Understanding in Multimodal Models</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.16669">arXiv 2026.01</a></td>
      <td width="64%">PL AW BENCH: A Rubric-Based Benchmark for Evaluating LLMs in Real-World Legal Practice</td>
      <td width="18%"><a href="https://github.com/SKYLENAGE-AI/PLawBench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.21165">arXiv 2026.01</a></td>
      <td width="64%">Frontier Science: Evaluating AI's Ability to Perform Expert-Level Scientific Tasks</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.22155">arXiv 2026.01</a></td>
      <td width="64%">UEval: A Benchmark for Unified Multimodal Generation</td>
      <td width="18%"><a href="https://github.com/zlab-princeton/UEval">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.10367">arXiv 2026.02</a></td>
      <td width="64%">LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation</td>
      <td width="18%"><a href="https://github.com/ZhilingYan/LiveMedBench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.11199">arXiv 2026.02</a></td>
      <td width="64%">When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification</td>
      <td width="18%"><a href="https://github.com/jialeuuz/askbench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.01562">arXiv 2026.03</a></td>
      <td width="64%">RubricBench: Aligning Model-Generated Rubrics with Human Standards</td>
      <td width="18%"><a href="https://github.com/planepig/rubricbench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=7pQv7qitFV">ICLR</a></td>
      <td width="64%">MicroVerse: A Preliminary Exploration Toward a Micro-World Simulation</td>
      <td width="18%"><a href="https://github.com/FreedomIntelligence/MicroVerse">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=VwNzKPqBxk">ICLR</a></td>
      <td width="64%">ProfBench: Multi-Domain Rubrics requiring Professional Knowledge to Answer and Judge</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=nJvgBolRcR">ICLR</a></td>
      <td width="64%">ExpertLongBench: Benchmarking Language Models on Expert-Level Long-Form Generation Tasks with Structured Checklists</td>
      <td width="18%"><a href="https://huggingface.co/datasets/launch/ExpertLongBench">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2507.02833">arXiv 2025.07</a></td>
      <td width="64%">Generalizing Verifiable Instruction Following</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2511.10507">arXiv 2025.11</a></td>
      <td width="64%">AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2505.08775">arXiv 2025.05</a></td>
      <td width="64%">HealthBench: Evaluating Large Language Models Towards Improved Human Health</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.04374">arXiv 2025.10</a></td>
      <td width="64%">GDPval: Evaluating AI Model Performance on Real-World Economically Valuable Tasks</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.16380">arXiv 2025.10</a></td>
      <td width="64%">MoreBench: Evaluating Procedural and Pluralistic Reasoning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2511.07685">arXiv 2025.11</a></td>
      <td width="64%">RESEARCH RUBRICS: A Benchmark of Prompts and Rubrics For Evaluating Deep Research Agents</td>
      <td width="18%"><a href="https://github.com/scaleapi/researchrubrics">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2512.01020">arXiv 2025.12</a></td>
      <td width="64%">Evaluating Legal Reasoning Traces with Legal Issue Tree Rubrics</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

## Practical Application of Rubrics

> Applications grouped by modality and domain, highlighting where rubrics help capture quality, safety, and task completion.

### By Modality

#### Modality-Text

> This section covers rubric use in text generation, dialogue, and reasoning-heavy language tasks. The emphasis is on how structured criteria guide evaluation or training for open-ended textual outputs.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.07149">arXiv 2026.01</a></td>
      <td width="64%">Rewarding Creativity: A Human-Aligned Generative Reward Model for Reinforcement Learning in Storytelling</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.15434">arXiv 2026.03</a></td>
      <td width="64%">Listening to the Echo: User-Reaction Aware Policy Optimization via Scalar-Verbal Hybrid Reinforcement Learning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=ugZKZ8vufv">ICLR</a></td>
      <td width="64%">The CoT Encyclopedia: Analyzing, Predicting, and Controlling how a Reasoning Model will Think</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2508.03990">arXiv 2025.08</a></td>
      <td width="64%">Are Today's LLMs Ready to Explain Well-Being Concepts?</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2509.22638">arXiv 2025.09</a></td>
      <td width="64%">Language Models Can Learn from Verbal Feedback Without Scalar Rewards</td>
      <td width="18%"><a href="https://github.com/sail-sg/feedback-conditional-policy">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.22143">arXiv 2025.10</a></td>
      <td width="64%">Benchmarking and Learning Real-World Customer Service Dialogue</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2512.01020">arXiv 2025.12</a></td>
      <td width="64%">Evaluating Legal Reasoning Traces with Legal Issue Tree Rubrics</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### Modality-Visual

> Visual rubric work extends structured judging and reward design to images, videos, and vision-language tasks. It is useful when model quality depends on multiple perceptual and semantic dimensions rather than a single scalar objective.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.09160">arXiv 2026.03</a></td>
      <td width="64%">RubiCap: Rubric-Guided Reinforcement Learning for Dense Image Captioning</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.16600">arXiv 2026.03</a></td>
      <td width="64%">Rationale Matters: Learning Transferable Rubrics via Proxy-Guided Critique for VLM Reward Models</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.14569">arXiv 2026.01</a></td>
      <td width="64%">SOCIAL CAPTION: Evaluating Social Understanding in Multimodal Models</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.05659">arXiv 2026.03</a></td>
      <td width="64%">When Rubrics Fail: Error Enumeration as Reward in Reference-Free RL Post-Training for Virtual Try-On</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=7pQv7qitFV">ICLR</a></td>
      <td width="64%">MicroVerse: A Preliminary Exploration Toward a Micro-World Simulation</td>
      <td width="18%"><a href="https://github.com/FreedomIntelligence/MicroVerse">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2509.22647">arXiv 2025.09</a></td>
      <td width="64%">CAP RL: S TIMULATING DENSE IMAGE CAPTION CAPA-</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.12712">arXiv 2025.10</a></td>
      <td width="64%">Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2511.20651">arXiv 2025.11</a></td>
      <td width="64%">RubricRL: Simple Generalizable Rewards for Text-to-Image Generation</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### Modality-Sound

- No retained papers after full-text justification review.

### By Domain

#### Domain-Medical

> Medical applications use rubrics to capture expert standards, safety expectations, and multi-step clinical reasoning quality. This is important because medical evaluation often cannot be reduced to single-answer correctness.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.09653">arXiv 2026.02</a></td>
      <td width="64%">ClinAlign: Scaling Healthcare Alignment from Clinician Preference</td>
      <td width="18%"><a href="https://github.com/AQ-MedAI/ClinAlign">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.13691">arXiv 2026.03</a></td>
      <td width="64%">QuarkMedBench: A Real-World Scenario Driven Benchmark for Evaluating Large Language Models</td>
      <td width="18%"><a href="https://github.com/Quark-Medical/QuarkMedBench_Technical_Report">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.23519">arXiv 2026.03</a></td>
      <td width="64%">MedMT-Bench: Can LLMs Memorize and Understand Long Multi-Turn Conversations in Medical Scenarios?</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2604.00024">arXiv 2026.04</a></td>
      <td width="64%">WHBench: A Women's Health Benchmark for Evaluating Frontier LLMs with Expert-in-the-Loop Validation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.13235">arXiv 2026.01</a></td>
      <td width="64%">RubRIX: Rubric-Driven Risk Mitigation in Caregiver-AI Interactions</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.18706">arXiv 2026.01</a></td>
      <td width="64%">Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.10367">arXiv 2026.02</a></td>
      <td width="64%">LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.11661">arXiv 2026.02</a></td>
      <td width="64%">Quark Medical Alignment: A Holistic Multi-Dimensional Alignment and Collaborative Optimization Paradigm</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2509.02208">arXiv 2025.09</a></td>
      <td width="64%">Baichuan-M2: Scaling Medical Capability with Large Verifier System</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2505.08775">arXiv 2025.05</a></td>
      <td width="64%">HealthBench: Evaluating Large Language Models Towards Improved Human Health</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.15859">arXiv 2025.10</a></td>
      <td width="64%">InfiMed-ORBIT: Aligning LLMs on Open-Ended Complex Tasks via Rubric-Based Incremental Training</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### Domain-Code

> Code-domain rubric work studies structured evaluation for coding, debugging, and software-agent behavior.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.04171">arXiv 2026.01</a></td>
      <td width="64%">Agentic Rubrics as Contextual Verifiers for SWE Agents</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

#### Domain-Agent

> Agent settings require rubrics to evaluate long-horizon behavior, tool use, planning, and subjective task completion. This section highlights work where structured criteria are central to assessing or training interactive agents.

#### 2026

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.06487">arXiv 2026.01</a></td>
      <td width="64%">Technical Report Tongyi DeepResearch</td>
      <td width="18%"><a href="https://github.com/Alibaba-NLP/qqr">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.06021">arXiv 2026.01</a></td>
      <td width="64%">Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards</td>
      <td width="18%"><a href="https://github.com/THUDM/CaRR">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2601.22511">arXiv 2026.01</a></td>
      <td width="64%">Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards</td>
      <td width="18%"><a href="https://github.com/haruhi-sudo/SYNTHAGENT">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.07244">arXiv 2026.03</a></td>
      <td width="64%">PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation</td>
      <td width="18%"><a href="https://github.com/PresentBench/PresentBench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.21362">arXiv 2026.03</a></td>
      <td width="64%">AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation</td>
      <td width="18%"><a href="https://github.com/alphadl/AdaRubrics">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.22744">arXiv 2026.03</a></td>
      <td width="64%">Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2603.27646">arXiv 2026.03</a></td>
      <td width="64%">PRBench: End-to-end Paper Reproduction in Physics Research</td>
      <td width="18%"><a href="https://github.com/HET-AGI/PRBench-Eval-Handson">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.03619">arXiv 2026.02</a></td>
      <td width="64%">Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.11199">arXiv 2026.02</a></td>
      <td width="64%">When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification</td>
      <td width="18%"><a href="https://github.com/jialeuuz/askbench">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2602.12268">arXiv 2026.02</a></td>
      <td width="64%">CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use</td>
      <td width="18%"><a href="https://github.com/namezhenzhang/CM2-RLCR-Tool-Agent">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2604.02368">arXiv 2026.04</a></td>
      <td width="64%">Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation</td>
      <td width="18%"><a href="https://github.com/randomtutu/Xpertbench">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <thead>
    <tr>
      <th width="18%" align="left">Volume</th>
      <th width="64%" align="left">Title</th>
      <th width="18%" align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.11184">arXiv 2025.10</a></td>
      <td width="64%">Reinforcement Learning for Tool-Integrated Interleaved Thinking towards Cross-Domain Generalization</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2510.12712">arXiv 2025.10</a></td>
      <td width="64%">Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2512.06196">arXiv 2025.12</a></td>
      <td width="64%">ARCANE: A Multi-Agent Framework for Interpretable and Configurable Alignment</td>
      <td width="18%">-</td>
    </tr>
    <tr>
      <td width="18%"><a href="https://arxiv.org/abs/2512.20491">arXiv 2025.12</a></td>
      <td width="64%">Step-DeepResearch Technical Report</td>
      <td width="18%"><a href="https://github.com/stepfun-ai/StepDeepResearch">Code</a></td>
    </tr>
    <tr>
      <td width="18%"><a href="https://openreview.net/forum?id=be76fus1ou">NeurIPS-W</a></td>
      <td width="64%">Towards Real-World Evaluation of Agentic Work in Freelance Marketplaces</td>
      <td width="18%">-</td>
    </tr>
  </tbody>
</table>

## LICENSE
This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Contact
If you have any questions or suggestions, please feel free to contact [Hongru Xiao](mailto:hongru_xiao@tongji.edu.cn).
