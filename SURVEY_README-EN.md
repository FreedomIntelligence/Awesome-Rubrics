# Awesome-Rubrics

> Definition: Rubric-based Reinforcement Learning (Rubric RL) uses structured evaluation criteria (rubrics) as reward signals to train and align LLMs and AI agents. Rubrics span from verifiable rules (RLVR) to LLM-generated multi-dimensional scoring.


---

## Table of Contents

- [Basics](#basics)
  - [Basics/Definitions](#basicsdefinitions)
  - [Basics/Format](#basicsformat)
  - [Basics/Traditional Domain Usage](#basicstraditional-domain-usage)
  - [Basics/Why Introduce Large Models](#basicswhy-introduce-large-models)
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

---

## Basics

### Basics/Definitions

> *Definitions, boundaries, and core components of Rubrics as evaluation/reward criteria for LLMs.*

1. **QuRL: Rubrics As Judge For Open-Ended Question Answering**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=DrhWTuhtYq) · [PDF](https://openreview.net/attachment?id=DrhWTuhtYq&name=pdf)

2. **Incentivizing LLMs to Self-Verify Their Answers**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=MBDWO29Qq6) · [PDF](https://openreview.net/pdf/ea6649a9cfb1c181a137632923e930e4e14e6ad3.pdf)

3. **Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=c1bTcrDmt4) · [PDF](https://openreview.net/attachment?id=c1bTcrDmt4&name=pdf)

4. **Robust Reward Modeling via Causal Rubrics**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=oP99JQiDYp) · [PDF](https://openreview.net/attachment?id=oP99JQiDYp&name=pdf)

5. **Reinforcement Learning from Dynamic Critic Feedback for Free-Form Generations**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=dBmjnRR1bC) · [PDF](https://openreview.net/attachment?id=dBmjnRR1bC&name=pdf)


### Basics/Format

> *Rubric dimensions, scoring levels, and structured expression format of rubrics.*

1. **Cat-PO: Cross-modal Adaptive Token-rewards for Preference Optimization in Truthful Multimodal LLMs**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=iIbe6qDN0A) · [PDF](https://openreview.net/attachment?id=iIbe6qDN0A&name=pdf)


### Basics/Traditional Domain Usage

> *Historical practices of Rubrics in educational assessment, NLP, or IR before LLMs.*

*No highly relevant papers identified for this section.*

### Basics/Why Introduce Large Models

> *Why structured Rubrics/verifiable rewards are necessary in the LLM era.*

1. **Hybrid Reinforcement: when reward is sparse, better to be dense**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=0CajQNVKyB) · [PDF](https://openreview.net/attachment?id=0CajQNVKyB&name=pdf)

2. **Your Models Have Thought Enough: Training Large Reasoning Models to Stop Overthinking**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=2u5ZRzDyS0) · [PDF](https://openreview.net/attachment?id=2u5ZRzDyS0&name=pdf)

3. **Chasing the Tail: Effective Rubric-based Reward Modeling for Large Language Model Post-Training**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=pBjy4ek2QV) · [PDF](https://openreview.net/attachment?id=pBjy4ek2QV&name=pdf)

4. **RLBFF: Binary Flexible Feedback to bridge between Human Feedback & Verifiable Rewards**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=P3R3S6S5Km) · [PDF](https://openreview.net/attachment?id=P3R3S6S5Km&name=pdf)


## Rubrics in the Era of Large Models

### Data

#### Synthetic Data

> *Synthetic data generated with rubric-style structured feedback for LLM training.*

1. **OptimSyn: Influence-Guided Rubrics Optimization for Synthetic Data Generation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=vFcm5sOitq) · [PDF](https://openreview.net/attachment?id=vFcm5sOitq&name=pdf)

2. **Spinning Straw into Gold: Relabeling LLM Agent Trajectories in Hindsight for Successful Demonstrations**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=QNfmqMSR7r) · [PDF](https://openreview.net/attachment?id=QNfmqMSR7r&name=pdf)


#### Real Data

> *Rubric signals from human preferences, real interactions, or authentic human annotations.*

1. **Learning Ordinal Probabilistic Reward from Preferences**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0Vf5trUAVF) · [PDF](https://openreview.net/attachment?id=0Vf5trUAVF&name=pdf)

2. **DeepMath-103K: A Large-Scale, Challenging, Decontaminated, and Verifiable Mathematical Dataset for Advancing Reasoning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=kHB5Te5IWm) · [PDF](https://openreview.net/attachment?id=kHB5Te5IWm&name=pdf)

3. **Pre-Trained Policy Discriminators are General Reward Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=efwbxMJ5M6) · [PDF](https://openreview.net/pdf/94d9ceac23b8b3dabf4a91f2f547f7ff2d1f293a.pdf)


### Training

#### Pre-training

> *Rubric/structured criteria injected or used during the pre-training stage.*

*No highly relevant papers identified for this section.*

#### Post-training

##### Post-training-SFT

> *Rubric constraints, filtering, and reweighting applied in Supervised Fine-Tuning.*

1. **Multi-Feature Quantized Self-Attention for Fair Large Language Models**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=0UvgQxsi7S) · [PDF](https://openreview.net/attachment?id=0UvgQxsi7S&name=pdf)

2. **ContextIF: Enhancing Instruction-Following through Context Reward**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=IuscGSmfEf) · [PDF](https://openreview.net/attachment?id=IuscGSmfEf&name=pdf)

3. **P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=hXNApWLBZG) · [PDF](https://openreview.net/attachment?id=hXNApWLBZG&name=pdf)


##### Post-training-OPD&DPO

> *Fine-grained rubric signals introduced in DPO or preference optimization.*

1. **ActiveDPO: Active Direct Preference Optimization for Sample-Efficient Alignment**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=RD4XgyVyGh) · [PDF](https://openreview.net/attachment?id=RD4XgyVyGh&name=pdf)

2. **Rectifying Shortcut Behaviors in Preference-based Reward Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=m51t6RKfGH) · [PDF](https://openreview.net/pdf/68f64407c11f7fe9069c3e63b8c90bfbf679caa6.pdf)

3. **PALC: Preference Alignment via Logit Calibration**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=0cmuYj3WeG) · [PDF](https://openreview.net/attachment?id=0cmuYj3WeG&name=pdf)

4. **Offline Preference-Based Value Optimization**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=9cUdn8GKId) · [PDF](https://openreview.net/attachment?id=9cUdn8GKId&name=pdf)

5. **Capturing Individual Human Preferences with Reward Features**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=TgCkj4uEPl) · [PDF](https://openreview.net/pdf/556cfcd15c657ecd28cbd21afadcd2e31ec0a60c.pdf)

6. **Quantile Reward Policy Optimization: Alignment with Pointwise Regression and Exact Partition Functions**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=TS128AgTRw) · [PDF](https://openreview.net/pdf/2b158b043e79c9b894e23da28c8170a07013f88f.pdf)


##### Post-training-RL Algorithm Optimization

> *Optimization of PPO/GRPO algorithms under rubric/verifiable rewards.*

1. **Repurposing Synthetic Data for Fine-grained Search Agent Supervision**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=CByVWPpb8T) · [PDF](https://openreview.net/attachment?id=CByVWPpb8T&name=pdf)

2. **DRPO: Efficient Reasoning via Decoupled Reward Policy Optimization**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=GP5RHZnEsw) · [PDF](https://openreview.net/attachment?id=GP5RHZnEsw&name=pdf)

3. **BLEUBERI: BLEU is a surprisingly effective reward for instruction following**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=bEYzeItoOH) · [PDF](https://openreview.net/pdf/62e5a2c7ddd32238b72c8305a544a7429632dfa2.pdf)

4. **KTAE: A Model-Free Algorithm to Key-Tokens Advantage Estimation in Mathematical Reasoning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=yqQVRNdmKJ) · [PDF](https://openreview.net/pdf/c7361c0485c7a932526ce8e922fcf62f985013b3.pdf)

5. **MARTI: A Framework for Multi-Agent LLM Systems Reinforced Training and Inference**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=E7jZqo0A50) · [PDF](https://openreview.net/attachment?id=E7jZqo0A50&name=pdf)

6. **Group Verification-based Policy Optimization for Interactive Coding Agents**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=RY47Tq0VsV) · [PDF](https://openreview.net/attachment?id=RY47Tq0VsV&name=pdf)

7. **Self-Aligned Reward: Towards Effective and Efficient Reasoners**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=89Pje8STvm) · [PDF](https://openreview.net/attachment?id=89Pje8STvm&name=pdf)

8. **ShorterBetter: Guiding Reasoning Models to Find Optimal Inference Length for Efficient Reasoning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=MJvwM5dBZM) · [PDF](https://openreview.net/pdf/bde69f28fc3bc8b96d74cd959ffd7e961aa0e70e.pdf)

9. **A Simple "Motivation" Can Enhance Reinforcement Finetuning of Large Reasoning Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=3owSlsYDQf) · [PDF](https://openreview.net/attachment?id=3owSlsYDQf&name=pdf)


##### Post-training-Reward Signal Optimization (GDPO)

> *Reward modeling, judge calibration, and reward shaping using rubrics for LLMs.*

1. **Hybrid Reinforcement: when reward is sparse, better to be dense**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=0CajQNVKyB) · [PDF](https://openreview.net/attachment?id=0CajQNVKyB&name=pdf)

2. **SophiaVL-R1: Reinforcing MLLMs Reasoning with Thinking Reward**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0tzvmjMcXC) · [PDF](https://openreview.net/attachment?id=0tzvmjMcXC&name=pdf)

3. **TraPO: A Semi-Supervised Reinforcement Learning Framework for Boosting LLM Reasoning**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=3K1y4KbWAx) · [PDF](https://openreview.net/attachment?id=3K1y4KbWAx&name=pdf)

4. **R1-Reward: Training Multimodal Reward Model Through Stable Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=4Ewgw9M2xE) · [PDF](https://openreview.net/attachment?id=4Ewgw9M2xE&name=pdf)

5. **ARM-FM: Automated Reward Machines via Foundation Models for Compositional Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=OBpQdCWLfd) · [PDF](https://openreview.net/attachment?id=OBpQdCWLfd&name=pdf)

6. **Text2Grad: Reinforcement Learning from Natural Language Feedback**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=SIE9fNq8lk) · [PDF](https://openreview.net/attachment?id=SIE9fNq8lk&name=pdf)

7. **Checklists Are Better Than Reward Models For Aligning Language Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=RPRqKhjrr6) · [PDF](https://openreview.net/pdf/490597cf8f353f8b01b8474e2f98c045eba8f5f4.pdf)

8. **Rewarding Doubt: A Reinforcement Learning Approach to Calibrated Confidence Expression of Large Language Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=yResLmrVO1) · [PDF](https://openreview.net/attachment?id=yResLmrVO1&name=pdf)


##### Post-training-Curriculum Learning

> *Curriculum learning staged by difficulty/dimension with rubric rewards.*

1. **SophiaVL-R1: Reinforcing MLLMs Reasoning with Thinking Reward**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0tzvmjMcXC) · [PDF](https://openreview.net/attachment?id=0tzvmjMcXC&name=pdf)

2. **Teaching Language Models to Evolve with Users: Dynamic Profile Modeling for Personalized Alignment**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=1V3Toke6XP) · [PDF](https://openreview.net/pdf/3c6a0c8b1dfec67e80825018ffe4d2f29cda83dc.pdf)

3. **Smarter Not Harder: Generative Process Evaluation with Intrinsic-Signal Driving and Ability‑Adaptive Reward Shaping**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=LZZENDlZt9) · [PDF](https://openreview.net/attachment?id=LZZENDlZt9&name=pdf)


##### Post-training-Self-evolution

> *Self-reflection, self-rewarding, and self-training loops in LLMs.*

1. **Vision-SR1: Self-Rewarding Vision-Language Model via Reasoning Decomposition and Multi-Reward Policy Optimization**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=C1M4ETatgM) · [PDF](https://openreview.net/attachment?id=C1M4ETatgM&name=pdf)

2. **Critique-RL: Training Language Models For Critiquing Through Two-Stage Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=SsUjdSVdUl) · [PDF](https://openreview.net/attachment?id=SsUjdSVdUl&name=pdf)

3. **Consistently Simulating Human Personas with Multi-Turn Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=A0T3piHiis) · [PDF](https://openreview.net/pdf/109c600393cc962e64028e8425eca62778f40ee9.pdf)

4. **Incentivizing LLMs to Self-Verify Their Answers**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=MBDWO29Qq6) · [PDF](https://openreview.net/pdf/ea6649a9cfb1c181a137632923e930e4e14e6ad3.pdf)


### Evaluation

#### Evaluation Methods

> *Rubric-based evaluation methods, LLM-judge reliability and consistency analysis.*

1. **Incentivizing Agentic Reasoning in LLM Judges via Tool-Integrated Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=AXNRILww9c) · [PDF](https://openreview.net/attachment?id=AXNRILww9c&name=pdf)

2. **mR3: Multilingual Rubric-Agnostic Reward Reasoning Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ST0wOB1bdX) · [PDF](https://openreview.net/attachment?id=ST0wOB1bdX&name=pdf)

3. **J1: Incentivizing Thinking in LLM-as-a-Judge via Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=dnJEHl6DI1) · [PDF](https://openreview.net/attachment?id=dnJEHl6DI1&name=pdf)

4. **Don’t Pass@$k$: A Bayesian Framework for Large Language Model Evaluation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=PTXi3Ef4sT) · [PDF](https://openreview.net/attachment?id=PTXi3Ef4sT&name=pdf)

5. **Ask a Strong LLM Judge when Your Reward Model is Uncertain**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=SkdhLeuq8P) · [PDF](https://openreview.net/pdf/32cbf67ca0e677b3f3fb9f298ed389d0875b2739.pdf)

6. **Reverse Engineering Human Preferences with Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=heY0zzGvYm) · [PDF](https://openreview.net/pdf/92f4508273884ba1413de3f4dd3ec020b732f559.pdf)

7. **Translate Policy to Language: Flow Matching Generated Rewards for LLM Explanations**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=zmZsWCGzUV) · [PDF](https://openreview.net/attachment?id=zmZsWCGzUV&name=pdf)

8. **Retro*: Optimizing LLMs for Reasoning-Intensive Document Retrieval**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0WGl8PNMSA) · [PDF](https://openreview.net/attachment?id=0WGl8PNMSA&name=pdf)

9. **RM-R1: Reward Modeling as Reasoning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=1ZqJ6jj75q) · [PDF](https://openreview.net/attachment?id=1ZqJ6jj75q&name=pdf)

10. **MENLO: From Preferences to Proficiency – Evaluating and Modeling Native-like Quality Across 47 Languages**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=QOWYX3Q2XS) · [PDF](https://openreview.net/attachment?id=QOWYX3Q2XS&name=pdf)


#### Evaluation Benchmarks

> *Benchmarks and datasets specifically for rubric-trained or rubric-evaluated LLMs.*

1. **MicroVerse: A Preliminary Exploration Toward a Micro-World Simulation**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=7pQv7qitFV) · [PDF](https://openreview.net/attachment?id=7pQv7qitFV&name=pdf)

2. **ProfBench: Multi-Domain Rubrics requiring Professional Knowledge to Answer and Judge**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=VwNzKPqBxk) · [PDF](https://openreview.net/attachment?id=VwNzKPqBxk&name=pdf)

3. **ExpertLongBench: Benchmarking Language Models on Expert-Level Long-Form Generation Tasks with Structured Checklists**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=nJvgBolRcR) · [PDF](https://openreview.net/attachment?id=nJvgBolRcR&name=pdf)

4. **StoryAlign: Evaluating and Training Reward Models for Story Generation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=a3JmkJtTDV) · [PDF](https://openreview.net/attachment?id=a3JmkJtTDV&name=pdf)

5. **VerifyBench: Benchmarking Reference-based Reward Systems for Large Language Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=JfsjGmuFxz) · [PDF](https://openreview.net/attachment?id=JfsjGmuFxz&name=pdf)


## Practical Application of Rubrics

### By Modality

#### Modality-Text

> *Rubric RL practices in text reasoning, dialogue, and generation tasks.*

1. **Aligning Deep Implicit Preferences by Learning to Reason Defensively**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ZA7i5Otjqd) · [PDF](https://openreview.net/attachment?id=ZA7i5Otjqd&name=pdf)

2. **The CoT Encyclopedia: Analyzing, Predicting, and Controlling how a Reasoning Model will Think**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ugZKZ8vufv) · [PDF](https://openreview.net/attachment?id=ugZKZ8vufv&name=pdf)

3. **RLVER: Reinforcement Learning with Verifiable Emotion Rewards for Empathetic Agents**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=P7wBg0vPTh) · [PDF](https://openreview.net/attachment?id=P7wBg0vPTh&name=pdf)


#### Modality-Visual

> *Rubric RL practices in visual/VLM/image/video tasks.*

1. **Towards Faithful Reasoning in Remote Sensing: A Perceptually-Grounded GeoSpatial Chain-of-Thought for Vision-Language Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=lJ7zecny2e) · [PDF](https://openreview.net/attachment?id=lJ7zecny2e&name=pdf)

2. **Unveiling Chain of Step Reasoning for Vision-Language Models with Fine-grained Rewards**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=D8nHwexHNv) · [PDF](https://openreview.net/pdf/9393d795825dc403a5224e23b11e26237b1bf5ed.pdf)

3. **Time-R1: Post-Training Large Vision Language Model for Temporal Video Grounding**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=gJ05Gm5VxQ) · [PDF](https://openreview.net/pdf/fd77e738ed9ddbaf6dd0fdfd97b99cdf186b552d.pdf)

4. **Perception-R1: Pioneering Perception Policy with Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=BeXcXrXetA) · [PDF](https://openreview.net/pdf/295cac79046d44e50b6d8b20590b41e011777405.pdf)

5. **Generative RLHF-V: Learning Principles from Multi-modal Human Preference**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=Evz0xPema0) · [PDF](https://openreview.net/pdf/86833030567663e2260d22821b68dd2db0c7c3cc.pdf)

6. **VLM-R³: Region Recognition, Reasoning, and Refinement for Enhanced Multimodal Chain-of-Thought**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ERGIrG9GBR) · [PDF](https://openreview.net/pdf/5e7d2aa638471c63b356d40e8943dbfd513adca1.pdf)

7. **Unlocking Multimodal Mathematical Reasoning via Process Reward Model**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=96I8PGPALv) · [PDF](https://openreview.net/pdf/9bc76b4ee1cdbe244a893c162b08d3ed55059de4.pdf)

8. **Fact-R1: Towards Explainable Video Misinformation Detection with Deep Reasoning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=EeyvDitalf) · [PDF](https://openreview.net/pdf/57d8d99f86e1cce535d963ef6bb4073464914b94.pdf)


#### Modality-Sound

> *Rubric RL practices in speech/audio tasks.*

1. **TTS Can Speak in Any Style with Any Voice**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=F7GmbfyVg9) · [PDF](https://openreview.net/attachment?id=F7GmbfyVg9&name=pdf)

2. **SpeechJudge: Towards Human-Level Judgment for Speech Naturalness**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=I9ED9VWZq6) · [PDF](https://openreview.net/attachment?id=I9ED9VWZq6&name=pdf)


### By Domain

#### Domain-Medical

> *Rubric RL training and evaluation in medical scenarios.*

1. **ATPO: ADAPTIVE TREE POLICY OPTIMIZATION FOR MULTI-TURN MEDICAL DIALOGUE**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=2bv3B8B9bl) · [PDF](https://openreview.net/attachment?id=2bv3B8B9bl&name=pdf)

2. **Doctor-R1: Mastering Clinical Inquiry with Experiential Agentic Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=vQGHTyL0Jw) · [PDF](https://openreview.net/attachment?id=vQGHTyL0Jw&name=pdf)

3. **MedAgentGym: A Scalable Agentic Training Environment for Code-Centric Reasoning in Biomedical Data Science**  
   *ICLR*  [OpenReview](https://openreview.net/forum?id=jHDZEUgS4r) · [PDF](https://openreview.net/attachment?id=jHDZEUgS4r&name=pdf)


#### Domain-Code

> *Rubric RL training and evaluation in code generation/debugging.*

1. **Process-Verified Reinforcement Learning for Theorem Proving via Lean**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=P00k4DFaXF) · [PDF](https://openreview.net/attachment?id=P00k4DFaXF&name=pdf)

2. **Critique-Coder: Enhancing Coder Models by Critique Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=tsuxIeLUsz) · [PDF](https://openreview.net/attachment?id=tsuxIeLUsz&name=pdf)

3. **QiMeng-CodeV-R1: Reasoning-Enhanced Verilog Generation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ly5DnRIgCZ) · [PDF](https://openreview.net/pdf/09c10d014999eae477f919d98b0b392a60db1ab1.pdf)

4. **Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=80L235oVBe) · [PDF](https://openreview.net/pdf/b354babdd37a4bbb9a67f01f12802970609d5429.pdf)

5. **SWE-RL: Advancing LLM Reasoning via Reinforcement Learning on Open Software Evolution**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ULblO61XZ0) · [PDF](https://openreview.net/pdf/ddd60c79265a4298a0592f27ac7d58b00b035132.pdf)

6. **Co-Evolving LLM Coder and Unit Tester via Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=wPdBe9zxNr) · [PDF](https://openreview.net/pdf/f11013ca9dbe05459e89557ddb9b09d292b6f6ba.pdf)


#### Domain-Agent

> *Rubric RL training and evaluation in Web/Tool/multi-agent systems.*

1. **Reasoning as an Adaptive Defense for Safety**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=2NLHoWE0eS) · [PDF](https://openreview.net/pdf/c036ebd40ea82ab94b9badc0028faf7e94456ca1.pdf)

2. **AlphaAlign: Incentivizing Safety Alignment with Extremely Simplified Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=2XNb1JUKW3) · [PDF](https://openreview.net/attachment?id=2XNb1JUKW3&name=pdf)

3. **WebArbiter: A Generative Reasoning Process Reward Model for Web Agents**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=canA6Ef0RP) · [PDF](https://openreview.net/attachment?id=canA6Ef0RP&name=pdf)

4. **HiPRAG: Hierarchical Process Rewards for Efficient Agentic Retrieval Augmented Generation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=Gt4v9WBPzm) · [PDF](https://openreview.net/attachment?id=Gt4v9WBPzm&name=pdf)

5. **Empowering LLM Tool Invocation with Tool-call Reward Model**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=LnBEASInVr) · [PDF](https://openreview.net/attachment?id=LnBEASInVr&name=pdf)

6. **Process vs. Outcome Reward: Which is Better for Agentic RAG Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=h3LlJ6Bh4S) · [PDF](https://openreview.net/pdf/863197fcba5eb83767ace1f59ea8fa5f81958eb6.pdf)

7. **ToolRL: Reward is All Tool Learning Needs**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=eOLdGbXT6t) · [PDF](https://openreview.net/pdf/097ae4a34c2eb2b82b2bb8fccc279fb0e3585304.pdf)

8. **UI-Genie: A Self-Improving Approach for Iteratively Boosting MLLM-based Mobile GUI Agents**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=3uUmJzSSOW) · [PDF](https://openreview.net/pdf/60b0d40a43feb74b9a8bfe6c1d7e28e83974f25c.pdf)

9. **Search and Refine During Think: Facilitating Knowledge Refinement for Improved Retrieval-Augmented Reasoning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=rBlWKIUQey) · [PDF](https://openreview.net/pdf/55cb62683b4084a45b97fd43ed7c483dbae3acc3.pdf)

