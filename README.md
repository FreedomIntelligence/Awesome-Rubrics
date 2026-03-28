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

The papers in this section explore the use of rubrics as evaluative and reward criteria for enhancing large language models (LLMs), focusing on how Rigorous Rubric Feedback (RRF) and Causal Rubrics can guide model improvements in domains with implicit evaluation standards. QuRL and "Rubrics as Rewards" demonstrate the efficacy of Reinforcement Learning from Verifiable Rewards (RLVR) in tasks with clear correctness signals, like math and coding, but highlight difficulties when extending to open-ended, real-world tasks. "Incentivizing LLMs to Self-Verify" and "Robust Reward Modeling via Causal Rubrics" address the risk of reward hacking and the challenge of ensuring robust evaluation in complex reasoning tasks. A significant open problem remains the high cost and complexity of applying diverse rubrics across varied and implicit task evaluations, as noted in "Reinforcement Learning from Dynamic Critic Feedback for Free-Form Generations."

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

The Cat-PO paper exemplifies recent advances in managing semantic coherence in Multi-modal Large Language Models (MLLMs) by leveraging cross-modal adaptive token-rewards for preference optimization. This approach addresses the challenge of hallucinations in MLLMs, which generate semantically inconsistent textual contents across varied modalities. A key technique involves cross-modal token-reward systems, aiming to enhance alignment between different input and output modalities. Despite these innovations, ensuring consistent semantic fidelity in complex, multi-modal contexts remains an open challenge in the field.

1. **Cat-PO: Cross-modal Adaptive Token-rewards for Preference Optimization in Truthful Multimodal LLMs**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=iIbe6qDN0A) · [PDF](https://openreview.net/attachment?id=iIbe6qDN0A&name=pdf)


### Basics/Traditional Domain Usage

> *Historical practices of Rubrics in educational assessment, NLP, or IR before LLMs.*

*No highly relevant papers identified for this section.*

### Basics/Why Introduce Large Models

> *Why structured Rubrics/verifiable rewards are necessary in the LLM era.*

The incorporation of structured rubrics and verifiable rewards in post-training processes is increasingly vital to address the challenges associated with large language models (LLMs), including reward sparsity and computational inefficiencies. Papers such as "Hybrid Reinforcement" emphasize deterministic checkers for more reliable feedback, while "Your Models Have Thought Enough" introduces methods to limit computational overhead in reasoning by curbing overthinking. "Chasing the Tail" highlights the problem of reward hacking with reinforcement fine-tuning (RFT) and proposes effective rubric-based reward strategies to ensure higher output quality. Lastly, "RLBFF" explores the integration of binary flexible feedback to bridge human and verifiable reward avenues, posing the need for efficient feedback mechanisms in LLM post-training.

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

In the realm of synthetic data generation for LLM training, recent research showcases innovative methods like OptimSyn, which uses influence-guided rubric optimization to improve the quality of synthetic data and enhance subsequent model performance. Additionally, the challenge of partial observability and delayed feedback in LLM agent supervision is tackled by Spinning Straw into Gold, which introduces a relabeling technique for LLM agent trajectories, refining them to provide successful demonstrations. These studies emphasize overcoming the bottleneck of supervision availability and maximizing LLM training efficacy, addressing existing challenges in scalability and data sufficiency.

1. **OptimSyn: Influence-Guided Rubrics Optimization for Synthetic Data Generation**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=vFcm5sOitq) · [PDF](https://openreview.net/attachment?id=vFcm5sOitq&name=pdf)

2. **Spinning Straw into Gold: Relabeling LLM Agent Trajectories in Hindsight for Successful Demonstrations**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=QNfmqMSR7r) · [PDF](https://openreview.net/attachment?id=QNfmqMSR7r&name=pdf)


#### Real Data

> *Rubric signals from human preferences, real interactions, or authentic human annotations.*

This section investigates the integration of human-derived signals into reward models to enhance the alignment of large language models with authentic human values, emphasizing ordinal probabilistic reward frameworks from preferences. Featured methods include policy discriminators as general reward models and large-scale data utilization such as the DeepMath-103K dataset to advance logical reasoning. Key challenges addressed across these papers include developing sufficiently complex training datasets for reasoning and overcoming limitations of current reward formulations that may not fully capture intricate human interactions and annotations.

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

This section surveys SFT-stage techniques that explicitly incorporate rubric-like constraints via data selection, reweighting, and context shaping. Multi-Feature Quantized Self-Attention (MFQSA) modifies attention computation during SFT using quantized sensitive-attribute features to debias internal representations and reduce fairness gaps. ContextIF augments SFT with a learned context reward that scores and selects instruction–context pairs, effectively reweighting training data toward examples that elicit better instruction following and generalization to novel tasks. P-GenRM introduces a personalized generative reward model with test-time user-based scaling, enabling user-specific preference conditioning during alignment; open challenges include obtaining reliable fine-grained signals (fairness labels, context rewards, and personal preferences) and maintaining robustness and generalization under such highly targeted supervision.

1. **Multi-Feature Quantized Self-Attention for Fair Large Language Models**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0UvgQxsi7S) · [PDF](https://openreview.net/attachment?id=0UvgQxsi7S&name=pdf)

2. **ContextIF: Enhancing Instruction-Following through Context Reward**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=IuscGSmfEf) · [PDF](https://openreview.net/attachment?id=IuscGSmfEf&name=pdf)

3. **P-GenRM: Personalized Generative Reward Model with Test-time User-based Scaling**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=hXNApWLBZG) · [PDF](https://openreview.net/attachment?id=hXNApWLBZG&name=pdf)


##### Post-training-OPD&DPO

> *Fine-grained rubric signals introduced in DPO or preference optimization.*

This section examines recent advancements in fine-grained rubric signals for DPO and preference optimization, focusing on techniques that enhance LLM alignment with human preferences. Key approaches include ActiveDPO, which emphasizes sample-efficient direct preference optimization, and PALC, which uses logit calibration for preference alignment. Challenges identified across these studies include the computational demands of aligning models and the difficulty of accounting for individual human preferences, as noted in "Capturing Individual Human Preferences with Reward Features." Open problems persist in optimizing offline learning strategies as explored in "Offline Preference-Based Value Optimization."

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

This section surveys recent advances in the optimization of PPO and GRPO algorithms through various verifiable reward mechanisms, focusing on fine-tuning large language models (LLMs) for enhanced reasoning and search capabilities. Techniques such as DRPO and Group Verification-based Policy Optimization are central to improving model efficiency and reasoning capabilities by using decoupled reward optimizations and group techniques, respectively. However, open challenges persist, such as the costly requirement for large-scale human-labeled data as noted in BLEUBERI and the need for enhanced inference efficiency addressed in frameworks like MARTI and strategies like ShorterBetter. Additionally, approaches like KTAE and Self-Aligned Reward explore rule-based and self-aligned optimizations, which highlight the ongoing effort to balance effective model training with operational efficiency.

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

In the domain of post-training reward signal optimization for large language models (LLMs), the surveyed papers address critical issues through diverse methodologies like Hybrid Reinforcement, SophiaVL-R1, and TraPO, which focus on densifying sparse feedback to enhance reasoning capabilities. Techniques such as ARM-FM and Text2Grad innovate by utilizing automated reward mechanisms and natural language feedback to refine the reward shaping process. Challenges highlighted include the complexity of specifying accurate reward functions and calibrating judged feedback, as discussed in works like Checklists Are Better Than Reward Models and Rewarding Doubt. These studies underscore the difficulty of aligning rewards with nuanced tasks while maintaining model robustness and interpretability.

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

This section explores post-training curriculum learning approaches that leverage reinforcement learning to enhance reasoning in multimodal large language models (MLLMs) and large reasoning models (LRMs). SophiaVL-R1 employs rule-based reinforcement learning with thinking rewards to improve reasoning abilities, while "Smarter Not Harder" introduces ability-adaptive reward shaping to address the challenges of sparse feedback in conventional RL methods. "Teaching Language Models to Evolve with Users" investigates personalized alignment through dynamic profile modeling to facilitate effective user-centric dialogues. A key challenge remains in refining the granularity of reward mechanisms to ensure efficient model training across varying difficulty dimensions.

1. **SophiaVL-R1: Reinforcing MLLMs Reasoning with Thinking Reward**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=0tzvmjMcXC) · [PDF](https://openreview.net/attachment?id=0tzvmjMcXC&name=pdf)

2. **Teaching Language Models to Evolve with Users: Dynamic Profile Modeling for Personalized Alignment**  
   *NeurIPS 2025*  [OpenReview](https://openreview.net/forum?id=1V3Toke6XP) · [PDF](https://openreview.net/pdf/3c6a0c8b1dfec67e80825018ffe4d2f29cda83dc.pdf)

3. **Smarter Not Harder: Generative Process Evaluation with Intrinsic-Signal Driving and Ability‑Adaptive Reward Shaping**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=LZZENDlZt9) · [PDF](https://openreview.net/attachment?id=LZZENDlZt9&name=pdf)


##### Post-training-Self-evolution

> *Self-reflection, self-rewarding, and self-training loops in LLMs.*

This section explores post-training self-evolution techniques in language models, focusing on self-reflection, self-rewarding, and self-training loops. Vision-SR1 tackles visual hallucinations in Vision-Language Models with reasoning decomposition and multi-reward policy optimization. Critique-RL employs a two-stage reinforcement learning framework for critiquing outputs to enhance model feedback mechanisms. Additionally, the challenge of consistent persona simulation in interactive applications is addressed with multi-turn reinforcement in human-like contexts, while another approach incentivizes LLMs to self-verify their answers, highlighting the ongoing quest for reliable self-assessment and enhancement in complex reasoning tasks.

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

The papers in this section explore advanced rubric-based evaluation methods for Large Language Models (LLM) judges, focusing on techniques like reinforcement learning to enhance reasoning (Incentivizing Agentic Reasoning in LLM Judges via Tool-Integrated Reinforcement Learning and J1) and multilingual evaluation challenges (mR3). Bayesian frameworks (Don’t Pass@$k$) and reward modeling approaches (RM-R1) are highlighted to address the instability and scalability issues inherent in LLM evaluation. Despite these innovations, challenges remain in achieving language proficiency across diverse languages (MENLO) and ensuring stable, reliable evaluation under constrained computational scenarios.

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

Evaluation benchmarks for rubric-trained LLMs encompass diverse domains and tasks, as demonstrated across five papers. ProfBench emphasizes rubric-based assessments in professional tasks, while ExpertLongBench tackles long-form generation using structured checklists, highlighting accuracy and expert-level skill requirements. StoryAlign and VerifyBench focus on reward model training, with StoryAlign refining narrative cohesion and VerifyBench integrating reference-based systems for enhanced reasoning. A central challenge remains ensuring evaluation metrics effectively capture nuanced model performance across micrometaphysical simulations, professional judgment, and expert content generation.

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

The Modality-Text section examines innovative approaches in Rubric RL practices, focusing on reasoning, dialogue, and generation tasks in Large Language Models (LLMs). Key themes include personalized alignment for defensively reasoning models, such as in "Aligning Deep Implicit Preferences," which addresses challenges in inferring user preferences and intentions. Techniques like CoT (chain-of-thought) strategies, as explored in "The CoT Encyclopedia," aim to better understand and predict reasoning patterns in LLMs, though the comprehensive analysis of these strategies remains limited. Additionally, "RLVER" highlights the significant gap in emotional intelligence, advocating for reinforcement learning using verifiable emotion rewards to enhance empathetic interaction capabilities. These papers collectively tackle ongoing challenges in balancing cognitive and emotional intelligence in language models, alongside improving alignment and reasoning inference mechanisms.

1. **Aligning Deep Implicit Preferences by Learning to Reason Defensively**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ZA7i5Otjqd) · [PDF](https://openreview.net/attachment?id=ZA7i5Otjqd&name=pdf)

2. **The CoT Encyclopedia: Analyzing, Predicting, and Controlling how a Reasoning Model will Think**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=ugZKZ8vufv) · [PDF](https://openreview.net/attachment?id=ugZKZ8vufv&name=pdf)

3. **RLVER: Reinforcement Learning with Verifiable Emotion Rewards for Empathetic Agents**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=P7wBg0vPTh) · [PDF](https://openreview.net/attachment?id=P7wBg0vPTh&name=pdf)


#### Modality-Visual

> *Rubric RL practices in visual/VLM/image/video tasks.*

Within the realm of visual modalities for Rubric RL applications, the surveyed papers collectively address the enhancement of reasoning capabilities in vision-language models (VLMs) and multi-modal large language models (MLLMs). Key techniques such as Chain-of-Thought reasoning, exemplified in "Towards Faithful Reasoning in Remote Sensing," are adapted to manage nuanced tasks in remote sensing, while Time-R1 and Perception-R1 investigate post-training frameworks to improve perception and temporal video grounding. Despite these advances, challenges remain in accurately aligning model outputs with human preferences and effectively integrating reasoning processes for complex spatial-temporal tasks, as evidenced by efforts in Generative RLHF-V and VLM-R³. The ongoing struggle to achieve dynamic and reliable reasoning through multimodal approaches continues to be a pivotal challenge.

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

Within the realm of Rubric RL practices for speech and audio tasks, this section details advancements like FlexiVoice, which innovatively combines flexible style control and zero-shot voice cloning, utilizing natural-language instruction for TTS synthesis. Meanwhile, SpeechJudge addresses the alignment of large generative models with human feedback in assessing speech naturalness, highlighting the absence of large-scale human preference datasets as a critical obstacle. These studies emphasize the need for enhanced human-model interaction and evaluation frameworks to surmount these impediments and improve the realism and adaptability of speech synthesis systems.

1. **TTS Can Speak in Any Style with Any Voice**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=F7GmbfyVg9) · [PDF](https://openreview.net/attachment?id=F7GmbfyVg9&name=pdf)

2. **SpeechJudge: Towards Human-Level Judgment for Speech Naturalness**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=I9ED9VWZq6) · [PDF](https://openreview.net/attachment?id=I9ED9VWZq6&name=pdf)


### By Domain

#### Domain-Medical

> *Rubric RL training and evaluation in medical scenarios.*

In the medical domain of rubric RL training and evaluation, the papers explore enhancements in conversational agents and coding-based reasoning for clinical scenarios. ATPO introduces Adaptive Tree Policy Optimization for effectively navigating multi-turn medical dialogues to address incomplete information during diagnosis. Doctor-R1 leverages experiential agentic RL to refine clinical inquiry skills, focusing on precise medical decision-making and empathetic consultation abilities. MedAgentGym presents a scalable training environment promoting code-centric reasoning within biomedical data science, spotlighting the challenge of integrating LLMs with complex heterogeneous data. These efforts underscore ongoing challenges in optimizing dialogue strategies and improving the contextual understanding of language models in diverse medical interactions.

1. **ATPO: ADAPTIVE TREE POLICY OPTIMIZATION FOR MULTI-TURN MEDICAL DIALOGUE**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=2bv3B8B9bl) · [PDF](https://openreview.net/attachment?id=2bv3B8B9bl&name=pdf)

2. **Doctor-R1: Mastering Clinical Inquiry with Experiential Agentic Reinforcement Learning**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=vQGHTyL0Jw) · [PDF](https://openreview.net/attachment?id=vQGHTyL0Jw&name=pdf)

3. **MedAgentGym: A Scalable Agentic Training Environment for Code-Centric Reasoning in Biomedical Data Science**  
   *ICLR 2026*  [OpenReview](https://openreview.net/forum?id=jHDZEUgS4r) · [PDF](https://openreview.net/attachment?id=jHDZEUgS4r&name=pdf)


#### Domain-Code

> *Rubric RL training and evaluation in code generation/debugging.*

This section of the survey delves into the training and evaluation of Rubric RL methods in code generation and debugging, emphasizing Reinforcement Learning with Verifiable Rewards (RLVR). Representative techniques include the Process-Verified RL approach for theorem proving via Lean and the Critique-Coder method that integrates critique-based reinforcement for coder models. Main challenges identified involve the complexity of optimization modeling, such as in the Solver-Informed RL work, and the need for enhanced reasoning capabilities in LLMs, explored in QiMeng-CodeV-R1 and SWE-RL research. Open problems remain in achieving consistent performance across diverse tasks and languages.

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

The Domain-Agent section explores advanced techniques in Rubric RL for training and evaluating agents within web, tool, and multi-agent systems. Highlighted methods such as AlphaAlign and WebArbiter demonstrate the implementation of adaptive reasoning and incentive-based safety alignment to address vulnerabilities in large language models (LLMs) across domains like math, code, and web tasks. Key challenges include developing efficient agentic retrieval-augmented generation, as seen in HiPRAG, and integrating external tools to overcome LLM limitations without compromising system security. While approaches such as ToolRL and UI-Genie strive to enhance agent-generalization capabilities, ongoing research focuses on refining reward models to balance process versus outcome-oriented learning.

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

