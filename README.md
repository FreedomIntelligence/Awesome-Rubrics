# Awesome-Rubrics [![Survey Paper](https://img.shields.io/badge/%F0%9F%93%84%20Survey%20Paper-Coming%20soon-blue)](#) [![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome) [![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity) [![PR's Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat)](http://makeapullrequest.com)

**Overview.** This repository provides a curated reading list for **rubric-based learning, reward data, modeling, and evaluation of large models**. It emphasizes how explicit criteria are used to build data, guide post-training, design reward signals, and evaluate open-ended model behavior.

Papers with publicly released code or project resources appear in the `Source` column. Entries without verified repositories use `-` in that column. 

> Contributions are welcome. If you find missing papers, inaccurate classifications, or newly released code, feel free to update this list.

<!-- ![rubric overview](imgs/rubric_readme.png) -->

## Table of Contents

- [📚 Basics](#basics)
  - [Definitions](#definitions)
  - [Format](#format)
  - [Traditional Domain Usage](#traditional-domain-usage)
  - [Why Introduce Large Models](#why-introduce-large-models)
- [🚀 Rubrics in the Era of Large Models](#rubrics-in-the-era-of-large-models)
  - [Data](#data)
    - [Synthetic Data](#synthetic-data)
    - [Real Data](#real-data)
  - [Training](#training)
    - [Pre-training](#pre-training)
    - [Post-training](#post-training)
      - [Post-training-SFT](#post-training-sft)
      - [Post-training-OPD and DPO](#post-training-opddpo)
      - [Post-training-RL Algorithm Optimization](#post-training-rl-algorithm-optimization)
      - [Post-training-Reward Signal Optimization](#post-training-reward-signal-optimization)
      - [Post-training-Curriculum Learning](#post-training-curriculum-learning)
      - [Post-training-Self-evolution](#post-training-self-evolution)
  - [Evaluation](#evaluation)
    - [Evaluation Methods](#evaluation-methods)
      - [Model-based](#model-based)
      - [Statistical-based](#statistical-based)
    - [Evaluation Benchmarks](#evaluation-benchmarks)
- [📊 Practical Application of Rubrics](#practical-application-of-rubrics)
  - [By Modality](#by-modality)
    - [Modality-Text](#modality-text)
    - [Modality-Visual](#modality-visual)
    - [Modality-Sound](#modality-sound)
  - [By Domain](#by-domain)
    - [Domain-Medical](#domain-medical)
    - [Domain-Code](#domain-code)
    - [Domain-Agent](#domain-agent)

## Basics

### Definitions
> Rubrics define structured evaluation dimensions, scoring rules, and judgment boundaries for open-ended model outputs. This section covers work that clarifies what counts as a rubric and how rubrics function as judges or reward criteria.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.05125">Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.17314">From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/agentscope-ai/OpenJudge">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=c1bTcrDmt4">Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/collections/ScaleAI/rar">Data</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=DrhWTuhtYq">QuRL: Rubrics As Judge For Open-Ended Question Answering</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=oP99JQiDYp">Robust Reward Modeling via Causal Rubrics</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

### Format

> This section focuses on how rubrics are expressed, including dimensions, levels, weights, and scoring templates. It is useful for understanding the representational form that makes rubric-based supervision reusable and controllable.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.07019">AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.17314">From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/agentscope-ai/OpenJudge">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=c1bTcrDmt4">Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

### Traditional Domain Usage

- No suitable papers were found after the full-text justification review.

### Why Introduce Large Models

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=pBjy4ek2QV">Chasing the Tail: Effective Rubric-based Reward Modeling for Large Language Model Post-Training</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/Jun-Kai-Zhang/rubrics">Code</a></td>
    </tr>
  </tbody>
</table>

## Rubrics in the Era of Large Models

### Data

#### Synthetic Data

> Synthetic data uses generated tasks, labels, critiques, or rubric annotations to expand supervision beyond limited human labeling. In Rubric RL, it is especially useful when rubric-style feedback can be programmatically produced at scale.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.09653">ClinAlign: Scaling Healthcare Alignment from Clinician Preference</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/AQ-MedAI/ClinAlign">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.08430">RubricHub: A Comprehensive and Highly Discriminative Rubric Dataset via Automated Coarse-to-Fine Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/teqkilla/RubricHub">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.07743">OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/datasets/OpenRubrics/OpenRubrics">Data</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=vFcm5sOitq">OptimSyn: Influence-Guided Rubrics Optimization for Synthetic Data Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/FanZT6/OptimSyn">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=c1bTcrDmt4">Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/collections/ScaleAI/rar">Data</a></td>
    </tr>
  </tbody>
</table>

#### Real Data

> Real data refers to rubric signals grounded in human preferences, authentic interactions, or expert annotations. These sources are important when alignment targets depend on nuanced human standards that are hard to synthesize fully.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.04</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2604.02368">Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/randomtutu/Xpertbench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.07244">PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/PresentBench/PresentBench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.27646">PRBench: End-to-end Paper Reproduction in Physics Research</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/HET-AGI/PRBench-Eval-Handson">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.18706">Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.22143">Benchmarking and Learning Real-World Customer Service Dialogue</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.05</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2505.08775">HealthBench: Evaluating Large Language Models Towards Improved Human Health</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/openai/simple-evals">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=QOWYX3Q2XS">MENLO: From Preferences to Proficiency - Evaluating and Modeling Native-like Quality Across 47 Languages</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/datasets/facebook/menlo">Code</a></td>
    </tr>
  </tbody>
</table>

### Training

#### Pre-training

- No suitable papers were found after the full-text justification review.

#### Post-training

##### Post-training-SFT

> Rubrics can be used in supervised fine-tuning for filtering data, weighting samples, or imposing structured response preferences. This makes SFT more aligned with multi-dimensional quality targets instead of flat imitation alone.

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=hXNApWLBZG">P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

##### Post-training-OPD&DPO

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.21362">AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/alphadl/AdaRubrics">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.07743">OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/OpenRubrics/models">Model</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.08</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2508.03990">Are Today's LLMs Ready to Explain Well-Being Concepts?</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICML-W</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=seA8en4ujl">Configurable Preference Tuning with Rubric-Guided Synthetic Data</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/vicgalle/configurable-preference-tuning">Code</a></td>
    </tr>
  </tbody>
</table>

##### Post-training-RL Algorithm Optimization

> This section covers preference optimization methods that incorporate fine-grained rubric signals rather than only pairwise global preferences. Rubrics help make preference learning more controllable, interpretable, and task-adaptive.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.04</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2604.02795">Rubrics to Tokens: Bridging Response-level Rubrics and Token-level Rewards in Instruction Following Tasks</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/TURLEing/Rubrics-To-Tokens">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.15434">Listening to the Echo: User-Reaction Aware Policy Optimization via Scalar-Verbal Hybrid Reinforcement Learning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.15646">Alternating Reinforcement Learning with Contextual Rubric Rewards</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.20046">Experience is the Best Teacher: Motivating Effective Exploration in Reinforcement Learning for LLMs</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/sikelifei/HeRL">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.26535">PAPO: Stabilizing Rubric Integration Training via Decoupled Advantage Normalization</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/tanzelin430/PAPO">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.01511">Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/collections/OpenRubrics/rubricarm">Model</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.07594">Learning to Self-Verify Makes Language Models Better Reasoners</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.12268">CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/namezhenzhang/CM2-RLCR-Tool-Agent">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.14069">Open Rubric System: Scaling Reinforcement Learning with Pairwise Adaptive Rubric</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/Qwen-Applications/OpenRS">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.06021">Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/THUDM/CaRR">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.05242">GDPO: Group reward-Decoupled Normalization Policy Optimization for Multi-reward RL Optimization</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://nvlabs.github.io/GDPO/">Proj</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.08</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2508.07768">Pareto Multi-Objective Alignment for Language Models</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.06</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2506.13351">Direct Reasoning Optimization: Constrained RL with Token-Level Dense Reward and Rubric-Gated Constraints for Open-ended Tasks</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.08</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2508.16949">Breaking the Exploration Bottleneck: Rubric-Scaffolded Reinforcement Learning for General LLM Reasoning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/IANNXANG/RuscaRL">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2509.22611">Quantile Advantage Estimation: Stabilizing RLVR for LLM Reasoning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.11184">Reinforcement Learning for Tool-Integrated Interleaved Thinking towards Cross-Domain Generalization</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.11</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2511.12344">Reward and Guidance through Rubrics: Promoting Exploration to Improve Multi-Domain Reasoning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

##### Post-training-Reward Signal Optimization

> This section centers on designing better rubric-based rewards, critics, and judges after initial model training. It includes work on reward shaping, judge calibration, rubric generation, and converting high-level criteria into usable learning signals.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.04</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2604.02795">Rubrics to Tokens: Bridging Response-level Rubrics and Token-level Rewards in Instruction Following Tasks</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/TURLEing/Rubrics-To-Tokens">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.08035">CDRRM: Contrast-Driven Rubric Generation for Reliable and Interpretable Reward Modeling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/ldcan/CDRRM">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.01562">RubricBench: Aligning Model-Generated Rubrics with Human Standards</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/planepig/rubricbench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.07019">AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/ChicagoHAI/AutoChecklist">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.20882">RubricRAG: Towards Interpretable and Reliable LLM Evaluation via Domain Knowledge Retrieval for Rubric Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.01511">Alternating Reinforcement Learning for Rubric-Based Reward Modeling in Non-Verifiable LLM Post-Training</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/collections/OpenRubrics/rubricarm">Model</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.14069">Open Rubric System: Scaling Reinforcement Learning with Pairwise Adaptive Rubric</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/Qwen-Applications/OpenRS">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.00846">OMNI-RRM: Advancing Omni Reward Model</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://anonymous.4open.science/r/Omni-RRM-CC08/readme.md">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.01791">Grad2Reward: From Sparse Judgment to Dense Rewards for Improving Open-Ended LLM Reasoning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.03619">Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.05125">Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.10067">Features as Rewards: Scalable Supervision for Open-Ended Tasks via Interpretability</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.20751">SibylSense: Adaptive Rubric Learning via Memory Tuning and Adversarial Probing</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.08430">RubricHub: A Comprehensive and Highly Discriminative Rubric Dataset via Automated Coarse-to-Fine Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/teqkilla/RubricHub">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.11374">Reward Modeling for Scientific Writing Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/UKPLab/acl2026-expert-rm">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.02986">P-Check: Advancing Personalized Reward Models via Learning to Generate Dynamic Checklists</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/tommyEzreal/P-Check_">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.07149">Rewarding Creativity: A Human-Aligned Generative Reward Model for Reinforcement Learning in Storytelling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.12</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2512.20312">TableGPT-R1: Advancing Tabular Reasoning Through Reinforcement Learning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/tablegpt/TableGPT-R1">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.11</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2511.10507">AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/facebookresearch/AdvancedIF">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.17314">From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/agentscope-ai/OpenJudge">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.07743">OpenRubrics: Towards Scalable Synthetic Rubric Generation for Reward Modeling and LLM Alignment</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/OpenRubrics/datasets">Data</a> / <a href="https://huggingface.co/OpenRubrics/models">Model</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=dBmjnRR1bC">RLAC: Reinforcement Learning with Adversarial Critic for Free-Form Generation Tasks</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://mianwu01.github.io/RLAC_website/">Proj</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.08</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2508.12790">Reinforcement Learning with Rubric Anchors</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.06</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2506.15651">AutoRule: Reasoning Chain-of-Thought Extracted Rule-Based Rewards Improve Preference Learning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/cxcscmu/AutoRule">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">NeurIPS 25</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=RPRqKhjrr6">Checklists Are Better Than Reward Models For Aligning Language Models</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/viswavi/RLCF">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.05</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2505.13388">R3: Robust Rubric-Agnostic Reward Models</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/rubricreward/r3">Code</a></td>
    </tr>
  </tbody>
</table>

##### Post-training-Curriculum Learning

> Curriculum learning studies how rubric dimensions or difficulty levels can stage training over time. It is relevant when structured feedback is used not only to score outputs but also to organize learning progression.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.21628">RuCL: Stratified Rubric-Based Curriculum Learning for Multimodal Large Language Model Reasoning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=hXNApWLBZG">P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/Tongyi-ConvAI/Qwen-Character/tree/main/Character-GenRM">Code</a></td>
    </tr>
  </tbody>
</table>

##### Post-training-Self-evolution

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.10885">Reinforcing Chain-of-Thought Reasoning with Self-Evolving Rubrics</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://alphalab-ustc.github.io/rlcer-alphalab/">Code</a></td>
    </tr>
  </tbody>
</table>

### Evaluation

#### Evaluation Methods

> Evaluation methods focus on how rubrics are used to judge outputs reliably and consistently across tasks. This includes LLM-as-a-judge settings, rubric-aware reward reasoning, and methods that improve interpretability of evaluation.

#### Model-based

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.20882">RubricRAG: Towards Interpretable and Reliable LLM Evaluation via Domain Knowledge Retrieval for Rubric Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/datasets/kdhole/healthbench-rubric-responses">Data</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.11027">Beyond the Illusion of Consensus: From Surface Heuristics to Knowledge-Grounded Evaluation in LLM-as-a-Judge</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.08035">CDRRM: Contrast-Driven Rubric Generation for Reliable and Interpretable Reward Modeling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/ldcan/CDRRM.git">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.07019">AutoChecklist: Composable Pipelines for Checklist Generation and Scoring with LLM-as-a-Judge</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/ChicagoHAI/AutoChecklist">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.12246">Examining Reasoning LLMs-as-Judges in Non-Verifiable LLM Post-Training</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.21362">AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/alphadl/AdaRubrics">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.05125">Rethinking Rubric Generation for Improving LLM Judge and Reward Modeling for Open-ended Tasks</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.13576">Rubrics as an Attack Surface: Stealthy Preference Drift in LLM Judges</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/ZDCSlab/Rubrics-as-an-Attack-Surface">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.08654">RULERS: Locked Rubrics and Evidence-Anchored Scoring for Robust LLM Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/LabRAI/Rulers.git">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=ST0wOB1bdX">mR3: Multilingual Rubric-Agnostic Reward Reasoning Models</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/rubricreward/mr3">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=1ZqJ6jj75q">RM-R1: Reward Modeling as Reasoning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://rm-r1-uiuc.github.io/rmr1-site/">Proj</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=QOWYX3Q2XS">MENLO: From Preferences to Proficiency - Evaluating and Modeling Native-like Quality Across 47 Languages</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/datasets/facebook/menlo">Data</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=0WGl8PNMSA">Retro: Optimizing LLMs for Reasoning-Intensive Document Retrieval</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/VectorSpaceLab/agentic-search/tree/main/Retro-star">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.17314">From Implicit Weights to Explicit Rubrics: A Training-Free Framework for Reward Modeling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/agentscope-ai/OpenJudge">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.05</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2505.13388">R3: Robust Rubric-Agnostic Reward Models</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/rubricreward/r3">Code</a></td>
    </tr>
  </tbody>
</table>

#### Statistical-based

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=PTXi3Ef4sT">Don't Pass@k: A Bayesian Framework for Large Language Model Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/mohsenhariri/scorio">Code</a></td>
    </tr>
  </tbody>
</table>

#### Evaluation Benchmarks

> Benchmark work provides datasets and tasks where rubric-based evaluation can be compared, stress-tested, and standardized. These resources are important for measuring whether rubric-trained or rubric-judged systems generalize across realistic scenarios.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.01562">RubricBench: Aligning Model-Generated Rubrics with Human Standards</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/planepig/rubricbench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.10303">Is this Idea Novel? An Automated Benchmark for Judgment of Research Ideas</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/TimSchopf/RINoBench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.22744">Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.28407">MiroEval: Benchmarking Multimodal Deep Research Agents in Process and Outcome</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://miroeval-ai.github.io/website/">Proj</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2604.02368">Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://xpert.bytedance.com/">Proj</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.07980">$OneMillion-Bench: How Far are Language Agents from Human Experts?</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.10367">LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/ZhilingYan/LiveMedBench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.11199">When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.16669">PLAW BENCH : A Rubric-Based Benchmark for Evaluating LLMs in Real-World Legal Practice</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/SKYLENAGE-AI/PLawBench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.21165">FRONTIER SCIENCE : E VALUATING AI’ S ABILITY TO PERFORM EXPERT -LEVEL SCIENTIFIC TASKS</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/datasets/openai/frontierscience/tree/main">Data</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.22155">UEval: A Benchmark for Unified Multimodal Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://zlab-princeton.github.io/UEval/">Proj</a></td>
    </tr>
  </tbody>
</table>

##### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.11</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2511.07685">RESEARCH RUBRICS : A Benchmark of Prompts and Rubrics For Evaluating Deep Research Agents</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://scale.com/research/researchrubrics">Proj</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.11</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2512.01020">Evaluating Legal Reasoning Traces with Legal Issue Tree Rubrics</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.11</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2511.10507">AdvancedIF: Rubric-Based Benchmarking and Reinforcement Learning for Advancing LLM Instruction Following</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/facebookresearch/AdvancedIF">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.04374">GDPVAL : EVALUATING AI MODEL PERFORMANCE ON REAL-WORLD ECONOMICALLY VALUABLE TASKS</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/datasets/openai/gdpval">Data</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.16380">MOREBENCH : EVALUATING PROCEDURAL AND PLoReBench: Evaluating Procedural and Pluralistic Moral Reasoning in Language Models, More than Outcomes</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://morebench.github.io/">Proj</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.18941">ProfBench: Multi-Domain Rubrics requiring Professional Knowledge to Answer and Judge</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/NVlabs/ProfBench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=nJvgBolRcR">ExpertLongBench: Benchmarking Language Models on Expert-Level Long-Form Generation Tasks with Structured Checklists</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://huggingface.co/spaces/launch/ExpertLongBench">Proj</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.07</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2507.02833">Generalizing Verifiable Instruction Following</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/allenai/IFBench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.05</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2505.08775">HealthBench: Evaluating Large Language Models Towards Improved Human Health</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/openai/simple-evals">Code</a></td>
    </tr>
  </tbody>
</table>

## Practical Application of Rubrics

> Applications grouped by modality and domain, highlighting where rubrics help capture quality, safety, and task completion.

### By Modality

#### Modality-Text

> This section covers rubric use in text generation, dialogue, and reasoning-heavy language tasks. The emphasis is on how structured criteria guide evaluation or training for open-ended textual outputs.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.11199">When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/jialeuuz/askbench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.07149">Rewarding Creativity: A Human-Aligned Generative Reward Model for Reinforcement Learning in Storytelling</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.12</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2512.01020">Evaluating Legal Reasoning Traces with Legal Issue Tree Rubrics</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.22143">Benchmarking and Learning Real-World Customer Service Dialogue</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.08</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2508.03990">Are Today's LLMs Ready to Explain Well-Being Concepts?</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=DrhWTuhtYq">QuRL: Rubrics As Judge For Open-Ended Question Answering</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=ugZKZ8vufv">The CoT Encyclopedia: Analyzing, Predicting, and Controlling how a Reasoning Model will Think</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/LGAI-Research/CoT-Encyclopedia">Code</a></td>
    </tr>
  </tbody>
</table>

#### Modality-Visual

> Visual rubric work extends structured judging and reward design to images, videos, and vision-language tasks. It is useful when model quality depends on multiple perceptual and semantic dimensions rather than a single scalar objective.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.09160">RubiCap: Rubric-Guided Reinforcement Learning for Dense Image Captioning</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.16600">Rationale Matters: Learning Transferable Rubrics via Proxy-Guided Critique for VLM Reward Models</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/Qwen-Applications/Proxy-GRM">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.05659">When Rubrics Fail: Error Enumeration as Reward in Reference-Free RL Post-Training for Virtual Try-On</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.14569">SOCIAL CAPTION: Evaluating Social Understanding in Multimodal Models</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.11</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2511.20651">RubricRL: Simple Generalizable Rewards for Text-to-Image Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.12712">Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://labs.scale.com/leaderboard/vtb">Proj</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">ICLR 26</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=7pQv7qitFV">MicroVerse: A Preliminary Exploration Toward a Micro-World Simulation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/FreedomIntelligence/MicroVerse">Code</a></td>
    </tr>
  </tbody>
</table>

#### Modality-Sound

- No suitable papers were found after the full-text justification review.

### By Domain

#### Domain-Medical

> Medical applications use rubrics to capture expert standards, safety expectations, and multi-step clinical reasoning quality. This is important because medical evaluation often cannot be reduced to single-answer correctness.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.13691">QuarkMedBench: A Real-World Scenario Driven Benchmark for Evaluating Large Language Models</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/Quark-Medical/QuarkMedBench_Technical_Report">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.23519">MedMT-Bench: Can LLMs Memorize and Understand Long Multi-Turn Conversations in Medical Scenarios?</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.09653">ClinAlign: Scaling Healthcare Alignment from Clinician Preference</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/AQ-MedAI/ClinAlign">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.10367">LiveMedBench: A Contamination-Free Medical Benchmark for LLMs with Automated Rubric Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.11661">Quark Medical Alignment: A Holistic Multi-Dimensional Alignment and Collaborative Optimization Paradigm</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.13235">RubRIX: Rubric-Driven Risk Mitigation in Caregiver-AI Interactions</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.18706">Health-SCORE: Towards Scalable Rubrics for Improving Health-LLMs</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.15859">InfiMed-ORBIT: Aligning LLMs on Open-Ended Complex Tasks via Rubric-Based Incremental Training</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/pidneuralode/ORBIT">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.09</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2509.02208">Baichuan-M2: Scaling Medical Capability with Large Verifier System</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.05</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2505.08775">HealthBench: Evaluating Large Language Models Towards Improved Human Health</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/openai/simple-evals">Code</a></td>
    </tr>
  </tbody>
</table>

#### Domain-Code

> Code-domain rubric work studies structured evaluation for coding, debugging, and software-agent behavior.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.04171">Agentic Rubrics as Contextual Verifiers for SWE Agents</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

#### Domain-Agent

> Agent settings require rubrics to evaluate long-horizon behavior, tool use, planning, and subjective task completion. This section highlights work where structured criteria are central to assessing or training interactive agents.

#### 2026

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.04</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2604.02368">Xpertbench: Expert Level Tasks with Rubrics-Based Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/randomtutu/Xpertbench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.07244">PresentBench: A Fine-Grained Rubric-Based Benchmark for Slide Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/PresentBench/PresentBench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.21362">AdaRubric: Task-Adaptive Rubrics for LLM Agent Evaluation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/alphadl/AdaRubrics">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.22744">Beyond Binary Correctness: Scaling Evaluation of Long-Horizon Agents on Subjective Enterprise Tasks</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.03</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2603.27646">PRBench: End-to-end Paper Reproduction in Physics Research</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/HET-AGI/PRBench-Eval-Handson">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.03619">Learning Query-Specific Rubrics from Human Preferences for DeepResearch Report Generation</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.11199">When and What to Ask: AskBench and Rubric-Guided RLVR for LLM Clarification</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/jialeuuz/askbench">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.02</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2602.12268">CM2: Reinforcement Learning with Checklist Rewards for Multi-Turn and Multi-Step Agentic Tool Use</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/namezhenzhang/CM2-RLCR-Tool-Agent">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.06487">Technical Report Tongyi DeepResearch</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/Alibaba-NLP/qqr">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.06021">Chaining the Evidence: Robust Reinforcement Learning for Deep Search Agents with Citation-Aware Rubric Rewards</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/THUDM/CaRR">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2026.01</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2601.22511">Mock Worlds, Real Skills: Building Small Agentic Language Models with Synthetic Tasks, Simulated Environments, and Rubric-Based Rewards</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/haruhi-sudo/SYNTHAGENT">Code</a></td>
    </tr>
  </tbody>
</table>

#### 2025

<table width="100%" style="width: 100%; table-layout: fixed;">
  <colgroup>
    <col width="16%" style="width: 16%;">
    <col width="14%" style="width: 14%;">
    <col width="52%" style="width: 52%;">
    <col width="18%" style="width: 18%;">
  </colgroup>
  <thead>
    <tr>
      <th width="16%" align="left" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Date</th>
      <th width="14%" align="left" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Volume</th>
      <th width="52%" align="left" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Title</th>
      <th width="18%" align="left" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">Source</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.12</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2512.06196">ARCANE: A Multi-Agent Framework for Interpretable and Configurable Alignment</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.12</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2512.20491">Step-DeepResearch Technical Report</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://github.com/stepfun-ai/StepDeepResearch">Code</a></td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.11184">Reinforcement Learning for Tool-Integrated Interleaved Thinking towards Cross-Domain Generalization</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">2025.10</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">arXiv</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://arxiv.org/abs/2510.12712">Beyond Seeing: Evaluating Multimodal LLMs on Tool-Enabled Image Perception</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
    <tr>
      <td width="16%" style="width: 16%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
      <td width="14%" style="width: 14%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">NeurIPS 25-W</td>
      <td width="52%" style="width: 52%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;"><a href="https://openreview.net/forum?id=be76fus1ou">Towards Real-World Evaluation of Agentic Work in Freelance Marketplaces</a></td>
      <td width="18%" style="width: 18%; vertical-align: top; overflow-wrap: anywhere; word-break: break-word;">-</td>
    </tr>
  </tbody>
</table>

## LICENSE
This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.

## Contact
If you have any questions or suggestions, please feel free to contact [Hongru Xiao](mailto:hongru_xiao@tongji.edu.cn).
