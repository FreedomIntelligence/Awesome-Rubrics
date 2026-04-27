# Awesome-Rubric [![Survey Paper](https://img.shields.io/badge/??%20Survey%20Paper-Coming%20soon-blue)](#) [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity) [![PR's Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](http://makeapullrequest.com)

**Overview.** This repository provides a curated reading list for **rubric-based learning, reward data, modeling, and evaluation of large models**. It emphasizes how explicit criteria are used to build data, guide post-training, design reward signals, and evaluate open-ended model behavior.

Papers with publicly released code or project resources appear in a fixed-width `Source` column. Entries without verified repositories use `-` in that column.

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

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.05125">arXiv 2026.02</a></td>
      <td>Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=DrhWTuhtYq">ICLR</a></td>
      <td>QuRL: Rubrics As Judge For Open-Ended Question Answering</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=c1bTcrDmt4">ICLR</a></td>
      <td>Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=oP99JQiDYp">ICLR</a></td>
      <td>Robust Reward Modeling via Causal Rubrics</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td>Auto-Rubric: Learning From Implicit Weights to Explicit Rubrics for Reward Modeling</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td>From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

### Basics/Format

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.07019">arXiv 2026.03</a></td>
      <td>AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=c1bTcrDmt4">ICLR</a></td>
      <td>Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td>From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

### Basics/Traditional Domain Usage

- No retained papers after full-text justification review.

### Basics/Why Introduce Large Models

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://openreview.net/forum?id=pBjy4ek2QV">ICLR</a></td>
      <td>Chasing the Tail: Effective Rubric-based Reward Modeling for Large Language Model Post-Training</td>
      <td><a href="https://github.com/Jun-Kai-Zhang/rubrics">Code</a></td>
    </tr>
  </tbody>
</table>

## Rubrics in the Era of Large Models

### Data

#### Synthetic Data

#### 2026

<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.09653">arXiv 2026.02</a></td>
      <td>ClinAlign: Scaling Healthcare Alignment from Clinician Preference</td>
      <td><a href="https://github.com/AQ-MedAI/ClinAlign">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.22511">arXiv 2026.01</a></td>
      <td>Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards</td>
      <td><a href="https://github.com/haruhi-sudo/SYNTHAGENT">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=vFcm5sOitq">ICLR</a></td>
      <td>OptimSyn: Influence-Guided Rubrics Optimization for Synthetic Data Generation</td>
      <td><a href="https://github.com/FanZT6/OptimSyn">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.07743">arXiv 2025.10</a></td>
      <td>OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment</td>
      <td><a href="https://huggingface.co/datasets/OpenRubrics/OpenRubrics">Code</a></td>
    </tr>
  </tbody>
</table>


#### Real Data

#### 2026

<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2604.02368">arXiv 2026.04</a></td>
      <td>Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation</td>
      <td><a href="https://github.com/randomtutu/Xpertbench">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.07244">arXiv 2026.03</a></td>
      <td>PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation</td>
      <td><a href="https://github.com/PresentBench/PresentBench">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.27646">arXiv 2026.03</a></td>
      <td>PRBench: End-to-end Paper Reproduction in Physics Research</td>
      <td><a href="https://github.com/HET-AGI/PRBench-Eval-Handson">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.18706">arXiv 2026.01</a></td>
      <td>Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=QOWYX3Q2XS">ICLR</a></td>
      <td>MENLO: From Preferences to Proficiency �C Evaluating and Modeling Native-like Quality Across 47 Languages</td>
      <td><a href="https://huggingface.co/datasets/facebook/menlo">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.22143">arXiv 2025.10</a></td>
      <td>Benchmarking and Learning Real-World Customer Service Dialogue</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2505.08775">arXiv 2025.05</a></td>
      <td>HealthBench: Evaluating Large Language Models Towards Improved Human Health</td>
      <td><a href="https://github.com/openai/simple-evals">Code</a></td>
    </tr>
  </tbody>
</table>

### Training

#### Pre-training

- No retained papers after full-text justification review.

#### Post-training

##### Post-training-SFT

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://openreview.net/forum?id=hXNApWLBZG">ICLR</a></td>
      <td>P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2508.03990">arXiv 2025.08</a></td>
      <td>Are Today��s LLMs Ready to Explain Well-Being Concepts?</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

##### Post-training-OPD&DPO

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.21362">arXiv 2026.03</a></td>
      <td>AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.07743">arXiv 2025.10</a></td>
      <td>OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2508.03990">arXiv 2025.08</a></td>
      <td>Are Today��s LLMs Ready to Explain Well-Being Concepts?</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2509.22638">arXiv 2025.09</a></td>
      <td>Language Models Can Learn from Verbal Feedback Without Scalar Rewards</td>
      <td><a href="https://github.com/sail-sg/feedback-conditional-policy">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=seA8en4ujl">ICML-W</a></td>
      <td>Configurable Preference Tuning with Rubric-Guided Synthetic Data</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

##### Post-training-RL Algorithm Optimization

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.05242">arXiv 2026.01</a></td>
      <td>GDPO: Group reward-Decoupled Normalization Policy Optimization for Multi-reward RL Optimization</td>
      <td><a href="https://github.com/NVlabs/GDPO">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.15646">arXiv 2026.03</a></td>
      <td>Alternating Reinforcement Learning with Contextual Rubric Rewards</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.20046">arXiv 2026.03</a></td>
      <td>Experience is the Best Teacher: Motivating Effective Exploration in Reinforcement Learning for LLMs</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.26535">arXiv 2026.03</a></td>
      <td>PAPO: Stabilizing Rubric Integration Training via Decoupled Advantage Normalization</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.06021">arXiv 2026.01</a></td>
      <td>Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards</td>
      <td><a href="https://github.com/THUDM/CaRR">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.15160">arXiv 2026.01</a></td>
      <td>Knowledge Graphs are Implicit Reward Models: Path-Derived Signals Enable Compositional Reasoning</td>
      <td><a href="https://github.com/yuvalkansal/kg_si_rl">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.01511">arXiv 2026.02</a></td>
      <td>Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.07594">arXiv 2026.02</a></td>
      <td>Learning to Self-Verify Makes Language Models Better Reasoners</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.08321">arXiv 2026.02</a></td>
      <td>Improving Data and Reward Design for Scientific Reasoning in Large Language Models</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.11199">arXiv 2026.02</a></td>
      <td>When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification</td>
      <td><a href="https://github.com/jialeuuz/askbench">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.12268">arXiv 2026.02</a></td>
      <td>CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.14069">arXiv 2026.02</a></td>
      <td>Open Rubric System: Scaling Reinforcement Learning with Pairwise Adaptive Rubric</td>
      <td><a href="https://github.com/Qwen-Applications/OpenRS">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.03197">arXiv 2026.03</a></td>
      <td>Specificity-aware reinforcement learning for fine-grained open-world classification</td>
      <td><a href="https://github.com/s-angheben/SpeciaRL">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.15434">arXiv 2026.03</a></td>
      <td>Listening to the Echo: User-Reaction Aware Policy Optimization via Scalar-Verbal Hybrid Reinforcement Learning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2604.02795">arXiv 2026.04</a></td>
      <td>Rubrics to Tokens: Bridging Response-level Rubrics and Token-level Rewards in Instruction Following Tasks</td>
      <td><a href="https://github.com/TURLEing/Rubrics-To-Tokens">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2508.07768">arXiv 2025.08</a></td>
      <td>Pareto Multi-Objective Alignment for Language Models</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2506.08123">arXiv 2025.06</a></td>
      <td>QA-LIGN: Aligning LLMs through Constitutionally Decomposed QA</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2506.13351">arXiv 2025.06</a></td>
      <td>Direct Reasoning Optimization: Constrained RL with Token-Level Dense Reward and Rubric-Gated Constraints for Open-ended Tasks</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2507.17746">arXiv 2025.07</a></td>
      <td>Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2508.12790">arXiv 2025.08</a></td>
      <td>Reinforcement Learning with Rubric Anchors</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2508.16949">arXiv 2025.08</a></td>
      <td>Breaking the Exploration Bottleneck: Rubric-Scaffolded Reinforcement Learning for General LLM Reasoning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2509.22611">arXiv 2025.09</a></td>
      <td>Quantile Advantage Estimation: Stabilizing RLVR for LLM Reasoning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.11184">arXiv 2025.10</a></td>
      <td>Reinforcement Learning for Tool-Integrated Interleaved Thinking towards Cross-Domain Generalization</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.14738">arXiv 2025.10</a></td>
      <td>AutoRubric-R1V: Rubric-Based Generative Reward for Vision-Language Reasoning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.15859">arXiv 2025.10</a></td>
      <td>InfiMed-ORBIT: Aligning LLMs on Open-Ended Complex Tasks via Rubric-Based Incremental Training</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2511.10507">arXiv 2025.11</a></td>
      <td>AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2511.12344">arXiv 2025.11</a></td>
      <td>Reward and Guidance through Rubrics: Promoting Exploration to Improve Multi-Domain Reasoning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2512.20312">arXiv 2025.12</a></td>
      <td>TableGPT-R1: Advancing Tabular Reasoning Through Reinforcement Learning</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

##### Post-training-Reward Signal Optimization

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.08430">arXiv 2026.01</a></td>
      <td>RubricHub: A Comprehensive and Highly Discriminative Rubric Dataset via Automated Coarse-to-Fine Generation</td>
      <td><a href="https://github.com/teqkilla/RubricHub">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.01511">arXiv 2026.02</a></td>
      <td>Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.14069">arXiv 2026.02</a></td>
      <td>Open Rubric System: Scaling Reinforcement Learning with Pairwise Adaptive Rubric</td>
      <td><a href="https://github.com/Qwen-Applications/OpenRS">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.08035">arXiv 2026.03</a></td>
      <td>CDRRM: Contrast-Driven Rubric Generation for Reliable and Interpretable Reward Modeling</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2604.02795">arXiv 2026.04</a></td>
      <td>Rubrics to Tokens: Bridging Response-level Rubrics and Token-level Rewards in Instruction Following Tasks</td>
      <td><a href="https://github.com/TURLEing/Rubrics-To-Tokens">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.02986">arXiv 2026.01</a></td>
      <td>P-Check: Advancing Personalized Reward Models via Learning to Generate Dynamic Checklists</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.07149">arXiv 2026.01</a></td>
      <td>Rewarding Creativity: A Human-Aligned Generative Reward Model for Reinforcement Learning in Storytelling</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.11374">arXiv 2026.01</a></td>
      <td>Reward Modeling for Scientific Writing Evaluation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.00846">arXiv 2026.02</a></td>
      <td>OMNI-RRM: Advancing Omni Reward Model</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.01791">arXiv 2026.02</a></td>
      <td>Grad2Reward: From Sparse Judgment to Dense Rewards for Improving Open-Ended LLM Reasoning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.03619">arXiv 2026.02</a></td>
      <td>Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.05125">arXiv 2026.02</a></td>
      <td>Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.10067">arXiv 2026.02</a></td>
      <td>Features as Rewards: Scalable Supervision for Open-Ended Tasks via Interpretability</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.20751">arXiv 2026.02</a></td>
      <td>SibylSense: Adaptive Rubric Learning via Memory Tuning and Adversarial Probing</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.01562">arXiv 2026.03</a></td>
      <td>RubricBench: Aligning Model-Generated Rubrics with Human Standards</td>
      <td><a href="https://github.com/planepig/rubricbench">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.07019">arXiv 2026.03</a></td>
      <td>AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.20882">arXiv 2026.03</a></td>
      <td>RubricRAG: Towards Interpretable and Reliable LLM Evaluation via Domain Knowledge Retrieval for Rubric Generation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=dBmjnRR1bC">ICLR</a></td>
      <td>Reinforcement Learning from Dynamic Critic Feedback for Free-Form Generations</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2506.15651">arXiv 2025.06</a></td>
      <td>AutoRule: Reasoning Chain-of-Thought Extracted Rule-Based Rewards Improve Preference Learning</td>
      <td><a href="https://github.com/cxcscmu/AutoRule">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2508.12790">arXiv 2025.08</a></td>
      <td>Reinforcement Learning with Rubric Anchors</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.07743">arXiv 2025.10</a></td>
      <td>OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2505.13388">arXiv 2025.05</a></td>
      <td>R3: Robust Rubric-Agnostic Reward Models</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td>From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=RPRqKhjrr6">NeurIPS</a></td>
      <td>Checklists Are Better Than Reward Models For Aligning Language Models</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

##### Post-training-Curriculum Learning

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.21628">arXiv 2026.02</a></td>
      <td>RuCL: Stratified Rubric-Based Curriculum Learning for Multimodal Large Language Model Reasoning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=hXNApWLBZG">ICLR</a></td>
      <td>P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

##### Post-training-Self-evolution

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.10885">arXiv 2026.02</a></td>
      <td>Reinforcing Chain-of-Thought Reasoning with Self-Evolving Rubrics</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

### Evaluation

#### Evaluation Methods

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.08035">arXiv 2026.03</a></td>
      <td>CDRRM: Contrast-Driven Rubric Generation for Reliable and Interpretable Reward Modeling</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.20882">arXiv 2026.03</a></td>
      <td>RubricRAG: Towards Interpretable and Reliable LLM Evaluation via Domain Knowledge Retrieval for Rubric Generation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.21362">arXiv 2026.03</a></td>
      <td>AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.08654">arXiv 2026.01</a></td>
      <td>RULERS: Locked Rubrics and Evidence-Anchored Scoring for Robust LLM Evaluation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.05125">arXiv 2026.02</a></td>
      <td>Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.10367">arXiv 2026.02</a></td>
      <td>LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.13576">arXiv 2026.02</a></td>
      <td>Rubrics as an Attack Surface: Stealthy Preference Drift in LLM Judges</td>
      <td><a href="https://github.com/ZDCSlab/Rubrics-as-an-Attack-Surface">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.01562">arXiv 2026.03</a></td>
      <td>RubricBench: Aligning Model-Generated Rubrics with Human Standards</td>
      <td><a href="https://github.com/planepig/rubricbench">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.07019">arXiv 2026.03</a></td>
      <td>AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.11027">arXiv 2026.03</a></td>
      <td>Beyond the Illusion of Consensus: From Surface Heuristics to Knowledge-Grounded Evaluation in LLM-as-a-Judge</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.12246">arXiv 2026.03</a></td>
      <td>Examining Reasoning LLMs-as-Judges in Non-Verifiable LLM Post-Training</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.25133">arXiv 2026.03</a></td>
      <td>RUBRIC EVAL: A Rubric-Level Meta-Evaluation Benchmark for LLM Judges in Instruction Following</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=ST0wOB1bdX">ICLR</a></td>
      <td>mR3: Multilingual Rubric-Agnostic Reward Reasoning Models</td>
      <td><a href="https://github.com/rubricreward/mr3">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=PTXi3Ef4sT">ICLR</a></td>
      <td>Don��t Pass@$k$: A Bayesian Framework for Large Language Model Evaluation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=0WGl8PNMSA">ICLR</a></td>
      <td>Retro: Optimizing LLMs for Reasoning-Intensive Document Retrieval</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=1ZqJ6jj75q">ICLR</a></td>
      <td>RM-R1: Reward Modeling as Reasoning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=QOWYX3Q2XS">ICLR</a></td>
      <td>MENLO: From Preferences to Proficiency �C Evaluating and Modeling Native-like Quality Across 47 Languages</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2505.13388">arXiv 2025.05</a></td>
      <td>R3: Robust Rubric-Agnostic Reward Models</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.12712">arXiv 2025.10</a></td>
      <td>Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.17314">arXiv 2025.10</a></td>
      <td>From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### Evaluation Benchmarks

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.07980">arXiv 2026.03</a></td>
      <td>$OneMillion-Bench: How Far are Language Agents from Human Experts?</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.10303">arXiv 2026.03</a></td>
      <td>Is this Idea Novel? An Automated Benchmark for Judgment of Research Ideas</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.22744">arXiv 2026.03</a></td>
      <td>Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.28407">arXiv 2026.03</a></td>
      <td>MiroEval: Benchmarking Multimodal Deep Research Agents in Process and Outcome</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2604.02368">arXiv 2026.04</a></td>
      <td>Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.14569">arXiv 2026.01</a></td>
      <td>SOCIAL CAPTION: Evaluating Social Understanding in Multimodal Models</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.16669">arXiv 2026.01</a></td>
      <td>PL AW BENCH: A Rubric-Based Benchmark for Evaluating LLMs in Real-World Legal Practice</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.21165">arXiv 2026.01</a></td>
      <td>Frontier Science: Evaluating AI's Ability to Perform Expert-Level Scientific Tasks</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.22155">arXiv 2026.01</a></td>
      <td>UEval: A Benchmark for Unified Multimodal Generation</td>
      <td><a href="https://github.com/zlab-princeton/UEval">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.10367">arXiv 2026.02</a></td>
      <td>LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.11199">arXiv 2026.02</a></td>
      <td>When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification</td>
      <td><a href="https://github.com/jialeuuz/askbench">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.01562">arXiv 2026.03</a></td>
      <td>RubricBench: Aligning Model-Generated Rubrics with Human Standards</td>
      <td><a href="https://github.com/planepig/rubricbench">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=7pQv7qitFV">ICLR</a></td>
      <td>MicroVerse: A Preliminary Exploration Toward a Micro-World Simulation</td>
      <td><a href="https://github.com/FreedomIntelligence/MicroVerse">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=VwNzKPqBxk">ICLR</a></td>
      <td>ProfBench: Multi-Domain Rubrics requiring Professional Knowledge to Answer and Judge</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=nJvgBolRcR">ICLR</a></td>
      <td>ExpertLongBench: Benchmarking Language Models on Expert-Level Long-Form Generation Tasks with Structured Checklists</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2507.02833">arXiv 2025.07</a></td>
      <td>Generalizing Verifiable Instruction Following</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2511.10507">arXiv 2025.11</a></td>
      <td>AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2505.08775">arXiv 2025.05</a></td>
      <td>HealthBench: Evaluating Large Language Models Towards Improved Human Health</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.04374">arXiv 2025.10</a></td>
      <td>GDPval: Evaluating AI Model Performance on Real-World Economically Valuable Tasks</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.16380">arXiv 2025.10</a></td>
      <td>MoreBench: Evaluating Procedural and Pluralistic Reasoning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2511.07685">arXiv 2025.11</a></td>
      <td>RESEARCH RUBRICS: A Benchmark of Prompts and Rubrics For Evaluating Deep Research Agents</td>
      <td><a href="https://github.com/scaleapi/researchrubrics">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2512.01020">arXiv 2025.12</a></td>
      <td>Evaluating Legal Reasoning Traces with Legal Issue Tree Rubrics</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

## Practical Application of Rubrics

Applications grouped by modality and domain, highlighting where rubrics help capture quality, safety, and task completion.

### By Modality

#### Modality-Text

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.07149">arXiv 2026.01</a></td>
      <td>Rewarding Creativity: A Human-Aligned Generative Reward Model for Reinforcement Learning in Storytelling</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.15434">arXiv 2026.03</a></td>
      <td>Listening to the Echo: User-Reaction Aware Policy Optimization via Scalar-Verbal Hybrid Reinforcement Learning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=ugZKZ8vufv">ICLR</a></td>
      <td>The CoT Encyclopedia: Analyzing, Predicting, and Controlling how a Reasoning Model will Think</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2508.03990">arXiv 2025.08</a></td>
      <td>Are Today��s LLMs Ready to Explain Well-Being Concepts?</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2509.22638">arXiv 2025.09</a></td>
      <td>Language Models Can Learn from Verbal Feedback Without Scalar Rewards</td>
      <td><a href="https://github.com/sail-sg/feedback-conditional-policy">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.22143">arXiv 2025.10</a></td>
      <td>Benchmarking and Learning Real-World Customer Service Dialogue</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2512.01020">arXiv 2025.12</a></td>
      <td>Evaluating Legal Reasoning Traces with Legal Issue Tree Rubrics</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### Modality-Visual

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.09160">arXiv 2026.03</a></td>
      <td>RubiCap: Rubric-Guided Reinforcement Learning for Dense Image Captioning</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.16600">arXiv 2026.03</a></td>
      <td>Rationale Matters: Learning Transferable Rubrics via Proxy-Guided Critique for VLM Reward Models</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.14569">arXiv 2026.01</a></td>
      <td>SOCIAL CAPTION: Evaluating Social Understanding in Multimodal Models</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.05659">arXiv 2026.03</a></td>
      <td>When Rubrics Fail: Error Enumeration as Reward in Reference-Free RL Post-Training for Virtual Try-On</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=7pQv7qitFV">ICLR</a></td>
      <td>MicroVerse: A Preliminary Exploration Toward a Micro-World Simulation</td>
      <td><a href="https://github.com/FreedomIntelligence/MicroVerse">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2509.22647">arXiv 2025.09</a></td>
      <td>CAP RL: S TIMULATING DENSE IMAGE CAPTION CAPA-</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.12712">arXiv 2025.10</a></td>
      <td>Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2511.20651">arXiv 2025.11</a></td>
      <td>RubricRL: Simple Generalizable Rewards for Text-to-Image Generation</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### Modality-Sound

- No retained papers after full-text justification review.

### By Domain

#### Domain-Medical

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.09653">arXiv 2026.02</a></td>
      <td>ClinAlign: Scaling Healthcare Alignment from Clinician Preference</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.13691">arXiv 2026.03</a></td>
      <td>QuarkMedBench: A Real-World Scenario Driven Benchmark for Evaluating Large Language Models</td>
      <td><a href="https://github.com/Quark-Medical/QuarkMedBench_Technical_Report">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.23519">arXiv 2026.03</a></td>
      <td>MedMT-Bench: Can LLMs Memorize and Understand Long Multi-Turn Conversations in Medical Scenarios?</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2604.00024">arXiv 2026.04</a></td>
      <td>WHBench: A Women��s Health Benchmark for Evaluating Frontier LLMs with Expert-in-the-Loop Validation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.13235">arXiv 2026.01</a></td>
      <td>RubRIX: Rubric-Driven Risk Mitigation in Caregiver-AI Interactions</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.18706">arXiv 2026.01</a></td>
      <td>Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.10367">arXiv 2026.02</a></td>
      <td>LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.11661">arXiv 2026.02</a></td>
      <td>Quark Medical Alignment: A Holistic Multi-Dimensional Alignment and Collaborative Optimization Paradigm</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2509.02208">arXiv 2025.09</a></td>
      <td>Baichuan-M2: Scaling Medical Capability with Large Verifier System</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2505.08775">arXiv 2025.05</a></td>
      <td>HealthBench: Evaluating Large Language Models Towards Improved Human Health</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.15859">arXiv 2025.10</a></td>
      <td>InfiMed-ORBIT: Aligning LLMs on Open-Ended Complex Tasks via Rubric-Based Incremental Training</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### Domain-Code

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.04171">arXiv 2026.01</a></td>
      <td>Agentic Rubrics as Contextual Verifiers for SWE Agents</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

#### Domain-Agent

#### 2026
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.22511">arXiv 2026.01</a></td>
      <td>Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards</td>
      <td><a href="https://github.com/haruhi-sudo/SYNTHAGENT">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.07244">arXiv 2026.03</a></td>
      <td>PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation</td>
      <td><a href="https://github.com/PresentBench/PresentBench">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.21362">arXiv 2026.03</a></td>
      <td>AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation</td>
      <td><a href="https://github.com/alphadl/AdaRubrics">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.22744">arXiv 2026.03</a></td>
      <td>Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2603.27646">arXiv 2026.03</a></td>
      <td>PRBench: End-to-end Paper Reproduction in Physics Research</td>
      <td><a href="https://github.com/HET-AGI/PRBench-Eval-Handson">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.06021">arXiv 2026.01</a></td>
      <td>Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards</td>
      <td><a href="https://github.com/THUDM/CaRR">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2601.06487">arXiv 2026.01</a></td>
      <td>Technical Report Tongyi DeepResearch</td>
      <td><a href="https://github.com/Alibaba-NLP/qqr">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.03619">arXiv 2026.02</a></td>
      <td>Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.11199">arXiv 2026.02</a></td>
      <td>When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification</td>
      <td><a href="https://github.com/jialeuuz/askbench">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2602.12268">arXiv 2026.02</a></td>
      <td>CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use</td>
      <td><a href="https://github.com/namezhenzhang/CM2-RLCR-Tool-Agent">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2604.02368">arXiv 2026.04</a></td>
      <td>Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation</td>
      <td><a href="https://github.com/randomtutu/Xpertbench">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025
<table width="100%">
  <colgroup>
    <col width="18%">
    <col width="64%">
    <col width="18%">
  </colgroup>
  <thead>
    <tr>
      <th align="left">Volume</th>
      <th align="left">Title</th>
      <th align="left">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.11184">arXiv 2025.10</a></td>
      <td>Reinforcement Learning for Tool-Integrated Interleaved Thinking towards Cross-Domain Generalization</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2510.12712">arXiv 2025.10</a></td>
      <td>Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2512.06196">arXiv 2025.12</a></td>
      <td>ARCANE: A Multi-Agent Framework for Interpretable and Configurable Alignment</td>
      <td>-</td>
    </tr>
    <tr>
      <td><a href="https://arxiv.org/abs/2512.20491">arXiv 2025.12</a></td>
      <td>Step-DeepResearch Technical Report</td>
      <td><a href="https://github.com/stepfun-ai/StepDeepResearch">Code</a></td>
    </tr>
    <tr>
      <td><a href="https://openreview.net/forum?id=be76fus1ou">NeurIPS-W</a></td>
      <td>Towards Real-World Evaluation of Agentic Work in Freelance Marketplaces</td>
      <td>-</td>
    </tr>
  </tbody>
</table>

## LICENSE
This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Contact
If you have any questions or suggestions, please feel free to contact [Hongru Xiao](mailto:hongru_xiao@tongji.edu.cn).`.


