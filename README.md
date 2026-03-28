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

This section of the evolving Rubric RL survey explores the foundational definitions, boundaries, and core components that underpin the use of rubrics as evaluation and reward criteria within the context of Reinforcement Learning (RL) frameworks applied to Large Language Models (LLMs). It emphasizes understanding how explicit and implicit rubrics guide model behavior in generating outputs that meet specific task requirements. Key research dimensions include the development of verifiable reward structures, the challenges of reward alignment and hacking, and the dynamic adaptation of evaluation criteria to accommodate diverse and complex reasoning tasks. As the field evolves, these foundational elements serve as pivotal guides in ensuring robust and reliable improvement of LLMs through RL methodologies.

1. **QuRL: Rubrics As Judge For Open-Ended Question Answering**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=DrhWTuhtYq) · [PDF](https://openreview.net/attachment?id=DrhWTuhtYq&name=pdf)

2. **Incentivizing LLMs to Self-Verify Their Answers**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=MBDWO29Qq6) · [PDF](https://openreview.net/pdf/ea6649a9cfb1c181a137632923e930e4e14e6ad3.pdf)

3. **Rubrics as Rewards: Reinforcement Learning Beyond Verifiable Domains**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=c1bTcrDmt4) · [PDF](https://openreview.net/attachment?id=c1bTcrDmt4&name=pdf)

4. **Robust Reward Modeling via Causal Rubrics**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=oP99JQiDYp) · [PDF](https://openreview.net/attachment?id=oP99JQiDYp&name=pdf)

5. **Reinforcement Learning from Dynamic Critic Feedback for Free-Form Generations**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=dBmjnRR1bC) · [PDF](https://openreview.net/attachment?id=dBmjnRR1bC&name=pdf)


### Basics/Format

> *Rubric dimensions, scoring levels, and structured expression format of rubrics.*

The "Basics/Format" section encompasses the foundational elements of rubrics within Rubric RL, focusing on their setup, scoring methodologies, and structural organization. This section is significant as it provides the framework necessary for evaluating and interpreting models' performance, thereby influencing the accuracy and reliability of results within Rubric RL studies. Key research dimensions include the categorization of scoring levels, the design of rubric dimensions to capture diverse model outputs, and the exploration of structured expression formats to effectively communicate evaluation criteria. This evolving framework ensures that new insights can be seamlessly integrated, advancing the rubric's adaptability and comprehensiveness in assessing multi-modal generative tasks.

1. **Cat-PO: Cross-modal Adaptive Token-rewards for Preference Optimization in Truthful Multimodal LLMs**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=iIbe6qDN0A) · [PDF](https://openreview.net/attachment?id=iIbe6qDN0A&name=pdf)


### Basics/Traditional Domain Usage

> *Historical practices of Rubrics in educational assessment, NLP, or IR before LLMs.*

*No highly relevant papers identified for this section.*

### Basics/Why Introduce Large Models

> *Why structured Rubrics/verifiable rewards are necessary in the LLM era.*

This section explores the fundamental necessity of implementing structured rubrics and verifiable rewards in the context of large language models (LLMs). In the LLM era, the ability to reliably assess and enhance model reasoning and performance is critical, as models increasingly handle complex tasks where subjective evaluations might lead to inconsistent outcomes. Key research directions here include the development of deterministic evaluation methods to ensure consistency, mitigating reward over-optimization to prevent exploitative model behavior, and refining reinforcement learning frameworks to incorporate verifiable rewards for robust model training and assessment. This topic plays a pivotal role in Rubric RL by ensuring the outputs of large models remain reliable and aligned with intended goals.

1. **Hybrid Reinforcement: when reward is sparse, better to be dense**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0CajQNVKyB) · [PDF](https://openreview.net/attachment?id=0CajQNVKyB&name=pdf)

2. **Your Models Have Thought Enough: Training Large Reasoning Models to Stop Overthinking**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=2u5ZRzDyS0) · [PDF](https://openreview.net/attachment?id=2u5ZRzDyS0&name=pdf)

3. **Chasing the Tail: Effective Rubric-based Reward Modeling for Large Language Model Post-Training**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=pBjy4ek2QV) · [PDF](https://openreview.net/attachment?id=pBjy4ek2QV&name=pdf)

4. **RLBFF: Binary Flexible Feedback to bridge between Human Feedback & Verifiable Rewards**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=P3R3S6S5Km) · [PDF](https://openreview.net/attachment?id=P3R3S6S5Km&name=pdf)


## Rubrics in the Era of Large Models

### Data

#### Synthetic Data

> *Synthetic data generated with rubric-style structured feedback for LLM training.*

The "Synthetic Data" section focuses on the generation and utilization of artificial datasets designed with structured feedback to enhance the training of large language models (LLMs) in Rubric-Reinforcement Learning (RL) environments. Conceptually, this encompasses methodologies for creating data that enable LLMs to perform effectively in scenarios where traditional supervised data acquisition is limited or infeasible. This area is significant within Rubric RL as it addresses key challenges in long-horizon and partially observable settings, where feedback from synthetic data can guide models towards improved decision-making capabilities. Key research dimensions include techniques for generating high-quality synthetic data, methods for integrating rubric-style feedback effectively, and strategies for evaluating the impact of synthetic data on model performance across various tasks.

1. **OptimSyn: Influence-Guided Rubrics Optimization for Synthetic Data Generation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=vFcm5sOitq) · [PDF](https://openreview.net/attachment?id=vFcm5sOitq&name=pdf)

2. **Spinning Straw into Gold: Relabeling LLM Agent Trajectories in Hindsight for Successful Demonstrations**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=QNfmqMSR7r) · [PDF](https://openreview.net/attachment?id=QNfmqMSR7r&name=pdf)


#### Real Data

> *Rubric signals from human preferences, real interactions, or authentic human annotations.*

The "Real Data" section encompasses studies that utilize human-derived signals, encompassing preferences, interactions, and annotations, to inform and enhance reinforcement learning (RL) models. This scope is integral to Rubric RL as it seeks to bridge the gap between artificial intelligence systems and human values, ensuring that models align with real human intentions and complex reasoning capabilities. Key research dimensions within this scope include the development of reward models for human-centric alignment, exploration of generative approaches, and the formulation of policy discriminators to quantify differences in behavior. This section reflects the ongoing evolution in leveraging authentic human data to refine and advance RL methodologies.

1. **Learning Ordinal Probabilistic Reward from Preferences**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0Vf5trUAVF) · [PDF](https://openreview.net/attachment?id=0Vf5trUAVF&name=pdf)

2. **DeepMath-103K: A Large-Scale, Challenging, Decontaminated, and Verifiable Mathematical Dataset for Advancing Reasoning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=kHB5Te5IWm) · [PDF](https://openreview.net/attachment?id=kHB5Te5IWm&name=pdf)

3. **Pre-Trained Policy Discriminators are General Reward Models**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=efwbxMJ5M6) · [PDF](https://openreview.net/pdf/94d9ceac23b8b3dabf4a91f2f547f7ff2d1f293a.pdf)


### Training

#### Pre-training

> *Rubric/structured criteria injected or used during the pre-training stage.*

*No highly relevant papers identified for this section.*

#### Post-training

##### Post-training-SFT

> *Rubric constraints, filtering, and reweighting applied in Supervised Fine-Tuning.*

The Post-training-SFT section delves into the methodologies and strategies employed in applying constraints, filtering, and reweighting during supervised fine-tuning (SFT) of large language models (LLMs). This process is integral to Rubric RL as it addresses the correction and mitigation of inherent biases in LLMs, thereby enhancing fairness and alignment with instructional tasks. Within this scope, research investigates the balance between improving model robustness and ensuring ethical considerations such as bias reduction, along with exploring personalized alignment to individual user preferences. As the field advances, insights into these sub-directions will continue to refine and evolve the application of SFT in fostering fair and adaptable AI systems.

1. **Multi-Feature Quantized Self-Attention for Fair Large Language Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0UvgQxsi7S) · [PDF](https://openreview.net/attachment?id=0UvgQxsi7S&name=pdf)

2. **ContextIF: Enhancing Instruction-Following through Context Reward**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=IuscGSmfEf) · [PDF](https://openreview.net/attachment?id=IuscGSmfEf&name=pdf)

3. **P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=hXNApWLBZG) · [PDF](https://openreview.net/attachment?id=hXNApWLBZG&name=pdf)


##### Post-training-OPD&DPO

> *Fine-grained rubric signals introduced in DPO or preference optimization.*

The Post-training-OPD&DPO section focuses on the integration of human preferences into post-training optimizations of reinforcement learning models, primarily through preference-based methods and data-driven optimization approaches. This area is significant within Rubric RL as it enhances the alignment of large language models with human expectations, improving their practical applicability and performance in diverse environments. Key research dimensions include the development of fine-grained reward signals, leveraging offline preference data, and optimizing models with reduced computational costs. As research evolves, this section continues to explore novel strategies to efficiently incorporate human feedback into model refinement processes.

1. **ActiveDPO: Active Direct Preference Optimization for Sample-Efficient Alignment**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=RD4XgyVyGh) · [PDF](https://openreview.net/attachment?id=RD4XgyVyGh&name=pdf)

2. **Rectifying Shortcut Behaviors in Preference-based Reward Learning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=m51t6RKfGH) · [PDF](https://openreview.net/pdf/68f64407c11f7fe9069c3e63b8c90bfbf679caa6.pdf)

3. **PALC: Preference Alignment via Logit Calibration**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0cmuYj3WeG) · [PDF](https://openreview.net/attachment?id=0cmuYj3WeG&name=pdf)

4. **Offline Preference-Based Value Optimization**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=9cUdn8GKId) · [PDF](https://openreview.net/attachment?id=9cUdn8GKId&name=pdf)

5. **Capturing Individual Human Preferences with Reward Features**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=TgCkj4uEPl) · [PDF](https://openreview.net/pdf/556cfcd15c657ecd28cbd21afadcd2e31ec0a60c.pdf)

6. **Quantile Reward Policy Optimization: Alignment with Pointwise Regression and Exact Partition Functions**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=TS128AgTRw) · [PDF](https://openreview.net/pdf/2b158b043e79c9b894e23da28c8170a07013f88f.pdf)


##### Post-training-RL Algorithm Optimization

> *Optimization of PPO/GRPO algorithms under rubric/verifiable rewards.*

The "Post-training-RL Algorithm Optimization" section focuses on the enhancement and fine-tuning of reinforcement learning algorithms, specifically Proximal Policy Optimization (PPO) and Group Relative Policy Optimization (GRPO), utilizing verifiable and structured reward systems. This area is crucial within Rubric RL as it advances the alignment of reinforcement learning models with human preferences and knowledge, driving improved performance in complex reasoning tasks. Key research dimensions in this section include the integration of rule-based and entity-centric rewards, scalability of training processes, and the refinement of reward models to reduce dependency on extensive human-labeled data. The research continuously evolves to refine algorithmic strategies that elevate the reasoning capabilities of large models across diverse problem domains.

1. **Repurposing Synthetic Data for Fine-grained Search Agent Supervision**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=CByVWPpb8T) · [PDF](https://openreview.net/attachment?id=CByVWPpb8T&name=pdf)

2. **DRPO: Efficient Reasoning via Decoupled Reward Policy Optimization**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=GP5RHZnEsw) · [PDF](https://openreview.net/attachment?id=GP5RHZnEsw&name=pdf)

3. **BLEUBERI: BLEU is a surprisingly effective reward for instruction following**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=bEYzeItoOH) · [PDF](https://openreview.net/pdf/62e5a2c7ddd32238b72c8305a544a7429632dfa2.pdf)

4. **KTAE: A Model-Free Algorithm to Key-Tokens Advantage Estimation in Mathematical Reasoning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=yqQVRNdmKJ) · [PDF](https://openreview.net/pdf/c7361c0485c7a932526ce8e922fcf62f985013b3.pdf)

5. **MARTI: A Framework for Multi-Agent LLM Systems Reinforced Training and Inference**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=E7jZqo0A50) · [PDF](https://openreview.net/attachment?id=E7jZqo0A50&name=pdf)

6. **Group Verification-based Policy Optimization for Interactive Coding Agents**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=RY47Tq0VsV) · [PDF](https://openreview.net/attachment?id=RY47Tq0VsV&name=pdf)

7. **Self-Aligned Reward: Towards Effective and Efficient Reasoners**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=89Pje8STvm) · [PDF](https://openreview.net/attachment?id=89Pje8STvm&name=pdf)

8. **ShorterBetter: Guiding Reasoning Models to Find Optimal Inference Length for Efficient Reasoning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=MJvwM5dBZM) · [PDF](https://openreview.net/pdf/bde69f28fc3bc8b96d74cd959ffd7e961aa0e70e.pdf)

9. **A Simple "Motivation" Can Enhance Reinforcement Finetuning of Large Reasoning Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=3owSlsYDQf) · [PDF](https://openreview.net/attachment?id=3owSlsYDQf&name=pdf)


##### Post-training-Reward Signal Optimization

> *Reward modeling, judge calibration, and reward shaping using rubrics for LLMs.*

The Post-training-Reward Signal Optimization section focuses on the strategies and methodologies employed to refine reward signals for large language models (LLMs) after initial training phases, specifically incorporating reward modeling, judge calibration, and reward shaping mechanisms. This section underscores the importance of these optimizations in enhancing LLMs' reasoning capabilities and alignment with human values and instructions, thereby fostering more reliable and accurate language models. Key research dimensions within this scope include the development of verifiable reward systems, exploration of multimodal reward models, and integration of fine-grained reward specifications to improve learning efficacy and output quality. As the field evolves, this section continuously explores new methods to optimize reward structures, ensuring LLMs are both effective and trustworthy in diverse applications.

1. **Hybrid Reinforcement: when reward is sparse, better to be dense**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0CajQNVKyB) · [PDF](https://openreview.net/attachment?id=0CajQNVKyB&name=pdf)

2. **SophiaVL-R1: Reinforcing MLLMs Reasoning with Thinking Reward**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0tzvmjMcXC) · [PDF](https://openreview.net/attachment?id=0tzvmjMcXC&name=pdf)

3. **TraPO: A Semi-Supervised Reinforcement Learning Framework for Boosting LLM Reasoning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=3K1y4KbWAx) · [PDF](https://openreview.net/attachment?id=3K1y4KbWAx&name=pdf)

4. **R1-Reward: Training Multimodal Reward Model Through Stable Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=4Ewgw9M2xE) · [PDF](https://openreview.net/attachment?id=4Ewgw9M2xE&name=pdf)

5. **ARM-FM: Automated Reward Machines via Foundation Models for Compositional Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=OBpQdCWLfd) · [PDF](https://openreview.net/attachment?id=OBpQdCWLfd&name=pdf)

6. **Text2Grad: Reinforcement Learning from Natural Language Feedback**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=SIE9fNq8lk) · [PDF](https://openreview.net/attachment?id=SIE9fNq8lk&name=pdf)

7. **Checklists Are Better Than Reward Models For Aligning Language Models**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=RPRqKhjrr6) · [PDF](https://openreview.net/pdf/490597cf8f353f8b01b8474e2f98c045eba8f5f4.pdf)

8. **Rewarding Doubt: A Reinforcement Learning Approach to Calibrated Confidence Expression of Large Language Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=yResLmrVO1) · [PDF](https://openreview.net/attachment?id=yResLmrVO1&name=pdf)


##### Post-training-Curriculum Learning

> *Curriculum learning staged by difficulty/dimension with rubric rewards.*

This section on Post-training-Curriculum Learning explores the methodologies and frameworks for systematically enhancing large language models by staging their learning processes according to difficulty or specific dimensions, with the aim of reinforcing skill development progressively. Within the broader scope of Rubric Reinforcement Learning (RL), this topic is essential for refining model performance through structured and adaptive training schemes that align with desired outcomes. Key research dimensions include adaptable curriculum design, difficulty ranking mechanisms, and reward systems that evaluate model progression and incentivize desirable behaviors. This section serves as a foundational area in Rubric RL to optimize model learning efficiency and effectiveness.

1. **SophiaVL-R1: Reinforcing MLLMs Reasoning with Thinking Reward**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0tzvmjMcXC) · [PDF](https://openreview.net/attachment?id=0tzvmjMcXC&name=pdf)

2. **Teaching Language Models to Evolve with Users: Dynamic Profile Modeling for Personalized Alignment**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=1V3Toke6XP) · [PDF](https://openreview.net/pdf/3c6a0c8b1dfec67e80825018ffe4d2f29cda83dc.pdf)

3. **Smarter Not Harder: Generative Process Evaluation with Intrinsic-Signal Driving and Ability‑Adaptive Reward Shaping**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=LZZENDlZt9) · [PDF](https://openreview.net/attachment?id=LZZENDlZt9&name=pdf)


##### Post-training-Self-evolution

> *Self-reflection, self-rewarding, and self-training loops in LLMs.*

This section covers methods where models improve themselves after initial training through self-reflection, self-generated feedback, and autonomous training loops. Within Rubric RL, these approaches are central to reducing reliance on external supervision, enabling models to internally evaluate, critique, and refine their own behaviors and reward signals over time. Key research dimensions include techniques for stable self-rewarding and self-critique, mechanisms for iterative refinement of policies and prompts, and safeguards against error amplification, mode collapse, and hallucination. The section also encompasses work on multi-step self-improvement curricula, role-play or self-play based learning, and frameworks for integrating self-evolution with human or environment-in-the-loop oversight.

1. **Vision-SR1: Self-Rewarding Vision-Language Model via Reasoning Decomposition and Multi-Reward Policy Optimization**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=C1M4ETatgM) · [PDF](https://openreview.net/attachment?id=C1M4ETatgM&name=pdf)

2. **Critique-RL: Training Language Models For Critiquing Through Two-Stage Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=SsUjdSVdUl) · [PDF](https://openreview.net/attachment?id=SsUjdSVdUl&name=pdf)

3. **Consistently Simulating Human Personas with Multi-Turn Reinforcement Learning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=A0T3piHiis) · [PDF](https://openreview.net/pdf/109c600393cc962e64028e8425eca62778f40ee9.pdf)

4. **Incentivizing LLMs to Self-Verify Their Answers**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=MBDWO29Qq6) · [PDF](https://openreview.net/pdf/ea6649a9cfb1c181a137632923e930e4e14e6ad3.pdf)


### Evaluation

#### Evaluation Methods

> *Rubric-based evaluation methods, LLM-judge reliability and consistency analysis.*

Evaluation Methods within Rubric RL focuses on the systematic analysis of rubric-based methods used to assess response quality, particularly the reliability and consistency of Large Language Model (LLM) judges. This topic is significant as it explores the roles these models play in automating evaluation processes, reducing reliance on human judgment and contributing to scalable solutions in AI frameworks. Key research dimensions include the effectiveness and robustness of LLM judges in diverse evaluation scenarios, their alignment with human preferences, and the integration of reinforcement learning approaches with human feedback mechanisms to refine model behavior.

1. **Incentivizing Agentic Reasoning in LLM Judges via Tool-Integrated Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=AXNRILww9c) · [PDF](https://openreview.net/attachment?id=AXNRILww9c&name=pdf)

2. **mR3: Multilingual Rubric-Agnostic Reward Reasoning Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ST0wOB1bdX) · [PDF](https://openreview.net/attachment?id=ST0wOB1bdX&name=pdf)

3. **J1: Incentivizing Thinking in LLM-as-a-Judge via Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=dnJEHl6DI1) · [PDF](https://openreview.net/attachment?id=dnJEHl6DI1&name=pdf)

4. **Don’t Pass@$k$: A Bayesian Framework for Large Language Model Evaluation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=PTXi3Ef4sT) · [PDF](https://openreview.net/attachment?id=PTXi3Ef4sT&name=pdf)

5. **Ask a Strong LLM Judge when Your Reward Model is Uncertain**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=SkdhLeuq8P) · [PDF](https://openreview.net/pdf/32cbf67ca0e677b3f3fb9f298ed389d0875b2739.pdf)

6. **Reverse Engineering Human Preferences with Reinforcement Learning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=heY0zzGvYm) · [PDF](https://openreview.net/pdf/92f4508273884ba1413de3f4dd3ec020b732f559.pdf)

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

Evaluation Benchmarks in Rubric RL serve as a collection of standardized metrics and datasets specifically designed to assess the capabilities and limitations of rubric-trained or rubric-evaluated large language models (LLMs). This section is crucial, as it grounds research efforts in objective, repeatable performance measurements that facilitate the reliable comparison and validation of model outputs. Within this scope, key research dimensions include the development of novel benchmark tasks that reflect real-world expert workflows, the adaptation of existing datasets to rubric-specific evaluation criteria, and the exploration of interdisciplinary metrics that capture the nuances of language and reasoning abilities intrinsic to these models. By continuously expanding, this section aims to provide comprehensive tools for understanding and advancing the effectiveness of rubric-based LLM evaluations.

1. **MicroVerse: A Preliminary Exploration Toward a Micro-World Simulation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=7pQv7qitFV) · [PDF](https://openreview.net/attachment?id=7pQv7qitFV&name=pdf)

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

The Modality-Text section covers the exploration and advancement of text-based interactions within Rubric RL frameworks, encompassing reasoning, dialogue, and generation tasks facilitated by large language models (LLMs). This area is significant as it delves into how textual data can be leveraged to enhance personalized and adaptive interactions, crucial for improving user-centric experiences in AI. Key research dimensions include the development of reasoning strategies like chain-of-thought processes, personalization approaches to align AI responses with user intent, and the integration of both cognitive and emotional dimensions in language model outputs. These converging directions aim to refine AI's ability to understand, generate, and engage in nuanced human-like communication.

1. **Aligning Deep Implicit Preferences by Learning to Reason Defensively**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ZA7i5Otjqd) · [PDF](https://openreview.net/attachment?id=ZA7i5Otjqd&name=pdf)

2. **The CoT Encyclopedia: Analyzing, Predicting, and Controlling how a Reasoning Model will Think**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ugZKZ8vufv) · [PDF](https://openreview.net/attachment?id=ugZKZ8vufv&name=pdf)

3. **RLVER: Reinforcement Learning with Verifiable Emotion Rewards for Empathetic Agents**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=P7wBg0vPTh) · [PDF](https://openreview.net/attachment?id=P7wBg0vPTh&name=pdf)


#### Modality-Visual

> *Rubric RL practices in visual/VLM/image/video tasks.*

The Modality-Visual section in Rubric RL focuses on research related to vision-language models (VLMs), image, and video analysis within reinforcement learning frameworks. This area explores how visual data can be integrated with language understanding to enhance model decision-making capabilities, enabling more effective multimodal processing and reasoning. It encompasses key research directions such as the advancement of temporal video grounding, the improvement of reasoning in vision-language tasks, and the adaptation of rule-based reinforcement learning to multimodal model training. These efforts are crucial in addressing the complexities of aligning visual perception with language-driven objectives, a pivotal challenge in developing comprehensive AI systems.

1. **Towards Faithful Reasoning in Remote Sensing: A Perceptually-Grounded GeoSpatial Chain-of-Thought for Vision-Language Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=lJ7zecny2e) · [PDF](https://openreview.net/attachment?id=lJ7zecny2e&name=pdf)

2. **Unveiling Chain of Step Reasoning for Vision-Language Models with Fine-grained Rewards**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=D8nHwexHNv) · [PDF](https://openreview.net/pdf/9393d795825dc403a5224e23b11e26237b1bf5ed.pdf)

3. **Time-R1: Post-Training Large Vision Language Model for Temporal Video Grounding**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=gJ05Gm5VxQ) · [PDF](https://openreview.net/pdf/fd77e738ed9ddbaf6dd0fdfd97b99cdf186b552d.pdf)

4. **Perception-R1: Pioneering Perception Policy with Reinforcement Learning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=BeXcXrXetA) · [PDF](https://openreview.net/pdf/295cac79046d44e50b6d8b20590b41e011777405.pdf)

5. **Generative RLHF-V: Learning Principles from Multi-modal Human Preference**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=Evz0xPema0) · [PDF](https://openreview.net/pdf/86833030567663e2260d22821b68dd2db0c7c3cc.pdf)

6. **VLM-R³: Region Recognition, Reasoning, and Refinement for Enhanced Multimodal Chain-of-Thought**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=ERGIrG9GBR) · [PDF](https://openreview.net/pdf/5e7d2aa638471c63b356d40e8943dbfd513adca1.pdf)

7. **Unlocking Multimodal Mathematical Reasoning via Process Reward Model**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=96I8PGPALv) · [PDF](https://openreview.net/pdf/9bc76b4ee1cdbe244a893c162b08d3ed55059de4.pdf)

8. **Fact-R1: Towards Explainable Video Misinformation Detection with Deep Reasoning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=EeyvDitalf) · [PDF](https://openreview.net/pdf/57d8d99f86e1cce535d963ef6bb4073464914b94.pdf)


#### Modality-Sound

> *Rubric RL practices in speech/audio tasks.*

The Modality-Sound section within Rubric RL focuses on the exploration and advancement of reinforcement learning (RL) techniques applied to speech and audio processing tasks. This area is significant as it addresses the challenge of enhancing generative audio models to align with human preferences, thus improving the quality and user satisfaction of speech-related applications. Key research dimensions in this scope include style control in speech synthesis, effective voice cloning techniques, and the incorporation of human feedback to guide model training and refinement. As this section evolves, it will continue to encompass studies that push the boundaries of RL applications in audio technologies, leveraging advancements to achieve more natural and contextually appropriate auditory outputs.

1. **TTS Can Speak in Any Style with Any Voice**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=F7GmbfyVg9) · [PDF](https://openreview.net/attachment?id=F7GmbfyVg9&name=pdf)

2. **SpeechJudge: Towards Human-Level Judgment for Speech Naturalness**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=I9ED9VWZq6) · [PDF](https://openreview.net/attachment?id=I9ED9VWZq6&name=pdf)


### By Domain

#### Domain-Medical

> *Rubric RL training and evaluation in medical scenarios.*

The Domain-Medical section encompasses research focused on the application and refinement of Rubric RL (Reinforcement Learning) in medical scenarios, particularly in enhancing diagnostic accuracy and decision-making capabilities. This topic holds significant importance in Rubric RL as it deals with complex, real-world environments where effective decision-making can substantially impact patient outcomes. Key research dimensions within this scope include the development of RL frameworks for multi-turn medical dialogue systems, the integration of RL for simulating and training medical reasoning models, and the exploration of scalable environments that mimic realistic biomedical challenges. This section remains integral to advancing the understanding and performance of RL systems in dynamic and high-stakes medical settings.

1. **ATPO: ADAPTIVE TREE POLICY OPTIMIZATION FOR MULTI-TURN MEDICAL DIALOGUE**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=2bv3B8B9bl) · [PDF](https://openreview.net/attachment?id=2bv3B8B9bl&name=pdf)

2. **Doctor-R1: Mastering Clinical Inquiry with Experiential Agentic Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=vQGHTyL0Jw) · [PDF](https://openreview.net/attachment?id=vQGHTyL0Jw&name=pdf)

3. **MedAgentGym: A Scalable Agentic Training Environment for Code-Centric Reasoning in Biomedical Data Science**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=jHDZEUgS4r) · [PDF](https://openreview.net/attachment?id=jHDZEUgS4r&name=pdf)


#### Domain-Code

> *Rubric RL training and evaluation in code generation/debugging.*

The Domain-Code section within the Rubric RL survey encompasses conceptual frameworks and methodologies that integrate reinforcement learning with code generation and debugging tasks. This domain is significant because it advances the application of reinforcement learning principles to develop autonomous systems capable of reasoning, optimizing, and generating code with greater efficiency and accuracy. Key research dimensions in this scope include the exploration of verifiable reward mechanisms, optimization algorithms, and the utilization of symbolic and formal verification methods to enhance the robustness and reliability of code produced by large language models. Additionally, this section remains adaptable to include ongoing developments in leveraging reinforcement learning to improve code-dependent decision-making processes across various industries.

1. **Process-Verified Reinforcement Learning for Theorem Proving via Lean**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=P00k4DFaXF) · [PDF](https://openreview.net/attachment?id=P00k4DFaXF&name=pdf)

2. **Critique-Coder: Enhancing Coder Models by Critique Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=tsuxIeLUsz) · [PDF](https://openreview.net/attachment?id=tsuxIeLUsz&name=pdf)

3. **QiMeng-CodeV-R1: Reasoning-Enhanced Verilog Generation**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=ly5DnRIgCZ) · [PDF](https://openreview.net/pdf/09c10d014999eae477f919d98b0b392a60db1ab1.pdf)

4. **Solver-Informed RL: Grounding Large Language Models for Authentic Optimization Modeling**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=80L235oVBe) · [PDF](https://openreview.net/pdf/b354babdd37a4bbb9a67f01f12802970609d5429.pdf)

5. **SWE-RL: Advancing LLM Reasoning via Reinforcement Learning on Open Software Evolution**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=ULblO61XZ0) · [PDF](https://openreview.net/pdf/ddd60c79265a4298a0592f27ac7d58b00b035132.pdf)

6. **Co-Evolving LLM Coder and Unit Tester via Reinforcement Learning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=wPdBe9zxNr) · [PDF](https://openreview.net/pdf/f11013ca9dbe05459e89557ddb9b09d292b6f6ba.pdf)


#### Domain-Agent

> *Rubric RL training and evaluation in Web/Tool/multi-agent systems.*

The Domain-Agent section of the Rubric RL survey encompasses the exploration and evaluation of Rubric RL methodologies within web, tool, and multi-agent systems. This domain is crucial for understanding how adaptive reasoning and strategic resource allocation at test time can enhance agents' performance across complex environments that involve long decision-making horizons and dynamic interactions. Key research dimensions within this scope include agent coordination, robust task execution under multi-step processes, integration of external information, and the enhancement of reasoning mechanisms to ensure safe, efficient, and goal-oriented outcomes. As these systems evolve, the section seeks to continually identify emerging challenges and methodologies that improve agents' ability to act autonomously and adaptively in diverse operational contexts.

1. **Reasoning as an Adaptive Defense for Safety**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=2NLHoWE0eS) · [PDF](https://openreview.net/pdf/c036ebd40ea82ab94b9badc0028faf7e94456ca1.pdf)

2. **AlphaAlign: Incentivizing Safety Alignment with Extremely Simplified Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=2XNb1JUKW3) · [PDF](https://openreview.net/attachment?id=2XNb1JUKW3&name=pdf)

3. **WebArbiter: A Generative Reasoning Process Reward Model for Web Agents**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=canA6Ef0RP) · [PDF](https://openreview.net/attachment?id=canA6Ef0RP&name=pdf)

4. **HiPRAG: Hierarchical Process Rewards for Efficient Agentic Retrieval Augmented Generation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=Gt4v9WBPzm) · [PDF](https://openreview.net/attachment?id=Gt4v9WBPzm&name=pdf)

5. **Empowering LLM Tool Invocation with Tool-call Reward Model**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=LnBEASInVr) · [PDF](https://openreview.net/attachment?id=LnBEASInVr&name=pdf)

6. **Process vs. Outcome Reward: Which is Better for Agentic RAG Reinforcement Learning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=h3LlJ6Bh4S) · [PDF](https://openreview.net/pdf/863197fcba5eb83767ace1f59ea8fa5f81958eb6.pdf)

7. **ToolRL: Reward is All Tool Learning Needs**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=eOLdGbXT6t) · [PDF](https://openreview.net/pdf/097ae4a34c2eb2b82b2bb8fccc279fb0e3585304.pdf)

8. **UI-Genie: A Self-Improving Approach for Iteratively Boosting MLLM-based Mobile GUI Agents**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=3uUmJzSSOW) · [PDF](https://openreview.net/pdf/60b0d40a43feb74b9a8bfe6c1d7e28e83974f25c.pdf)

9. **Search and Refine During Think: Facilitating Knowledge Refinement for Improved Retrieval-Augmented Reasoning**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=rBlWKIUQey) · [PDF](https://openreview.net/pdf/55cb62683b4084a45b97fd43ed7c483dbae3acc3.pdf)

