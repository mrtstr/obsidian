## Two-stage training paradigm

Out of the box, a pretrained [[LLM]] mostly **continues text patterns**.  
To turn it into a useful assistant (e.g. a chatbot), training is done in **two stages**:

### Stage 1: Pretraining
- Train on very large, general text-based datasets (web, books, code, etc.).
- Objective:
  - **Base model with broad language capabilities**
  - Learns patterns of grammar, discourse, reasoning, and factual associations.
- Extremely compute-intensive and expensive.

### Stage 2: Post-training / Alignment

- Turn the base model into a **model aligned with human intentions**  
  (helpful, instruction-following, and safer to deploy).
- **much cheaper** than pre-training 

#### Step 1: Supervised Fine-Tuning (SFT / instruction tuning) 
- continue training the pretrained model with the **same next-token prediction loss**, but now on **high-quality instruction–response pairs** instead of raw web text.
- training data is **written by humans** with quality over quantity approach
- Example: Input: “Summarize this text: …” → Target: a clean, human-written summary.
##### limitations
- no negative feedback for unsafe or wrong answers
- only trained on high quality and correct questions (no for example conflicting instructions)
- hallucinations is not prevented

#### Step 2: alignment on preference 
- **general challenge**: often there is no single correct answer and human preference depends on values 
- general approach: **collect human preference** and then t**rain the model to produce responses that humans prefer**
##### collecting human preference
- collecting **human absolute preference** (e.g. scale 0 to 10) is very unreliable, but **relative preference is much more consistent**
1) generate a **promt dataset**$\{X^{(1)},...., X^{(n)}\}$
2) generate multiple responses for each promt $\left\{Y^{(1)}_{(1)},..., Y^{(1)}_{(k)}, Y^{(2)}_{(1)...}\right\}$
3) lat humans rate the response answer combination relative to each other (either in pairs $(X, Y^+, Y^-)$ or as a total order for each promt)

##### training the model for preference
- $\pi_\theta$ is the [[LLM]] after the SFT step (request/response level and not token level) that is optimized

$$
\pi_\theta(Y | X) = \mathbb{P}_\theta(Y| X)
$$

- two approaches but currently only DPO is used because its simpler with comparable results
1) Reinforcement Learning from Human Feedback (RLHF) with Proximal Policy Optimization (PPO) 
2) Direct Preference Optimization (DPO)

###### Reinforcement Learning from Human Feedback
- first minimize the $\ell_\mathrm{RM}$ [[loss function]] to train a reward model $r_\vartheta(X, Y)$ to rate responses such that $r_\vartheta(X, Y^+) > r_\vartheta(X, Y^-)$

$$
\ell_\mathrm{RM} = -\log \sigma\left(r_\vartheta(X, Y^+)-r_\vartheta(X, Y^-)\right)
$$

- in a second step, train the actual model $\pi_\theta$ with the reward model as trainer
- the component $\beta\mathrm{KL}(\pi_\theta || \pi_{SFT})$ is to make sure that the model doesn't deviate too much from the original model $\pi_{SFT}$ (after pre-training and SFT)
$$
\max_\theta \mathbb{E}_{Y\sim\pi_\theta(. | X)}\left[r_\vartheta(X, Y) - \beta\mathrm{KL}(\pi_\theta || \pi_{SFT})\right]
$$

###### Direct Preference Optimization
- minimize $\ell_\mathrm{DPO}$ such that $\pi_\theta(Y^+ | X) > \pi_\theta(Y^- | X)$

$$
\ell_\mathrm{DPO} = -\log \sigma\left(\beta[\log \pi_\theta(Y^+ | X) - \log \pi_\theta(Y^- | X)]\right)
$$

# anki

START
Basic
what is alignment training on preference?
- how does it fit in the two-stage training paradigm?
- what comes before and after?
- two methods with loss functions. Which of them is currently used?
Back: 
## Two-stage training paradigm

Out of the box, a pretrained [[LLM]] mostly **continues text patterns**.  
To turn it into a useful assistant (e.g. a chatbot), training is done in **two stages**:

### Stage 1: Pretraining
- Train on very large, general text-based datasets (web, books, code, etc.).
- Objective:
  - **Base model with broad language capabilities**
  - Learns patterns of grammar, discourse, reasoning, and factual associations.
- Extremely compute-intensive and expensive.

### Stage 2: Post-training / Alignment

- Turn the base model into a **model aligned with human intentions**  
  (helpful, instruction-following, and safer to deploy).
- **much cheaper** than pre-training 

#### Step 1: Supervised Fine-Tuning (SFT / instruction tuning) 
- continue training the pretrained model with the **same next-token prediction loss**, but now on **high-quality instruction–response pairs** instead of raw web text.
- training data is **written by humans** with quality over quantity approach
- Example: Input: “Summarize this text: …” → Target: a clean, human-written summary.
##### limitations
- no negative feedback for unsafe or wrong answers
- only trained on high quality and correct questions (no for example conflicting instructions)
- hallucinations is not prevented

#### Step 2: alignment on preference 
- **general challenge**: often there is no single correct answer and human preference depends on values 
- general approach: **collect human preference** and then t**rain the model to produce responses that humans prefer**
##### collecting human preference
- collecting **human absolute preference** (e.g. scale 0 to 10) is very unreliable, but **relative preference is much more consistent**
1) generate a **promt dataset**$\{X^{(1)},...., X^{(n)}\}$
2) generate multiple responses for each promt $\left\{Y^{(1)}_{(1)},..., Y^{(1)}_{(k)}, Y^{(2)}_{(1)...}\right\}$
3) lat humans rate the response answer combination relative to each other (either in pairs $(X, Y^+, Y^-)$ or as a total order for each promt)

##### training the model for preference
- $\pi_\theta$ is the [[LLM]] after the SFT step (request/response level and not token level) that is optimized

$$
\pi_\theta(Y | X) = \mathbb{P}_\theta(Y| X)
$$

- two approaches but currently only DPO is used because its simpler with comparable results
1) Reinforcement Learning from Human Feedback (RLHF) with Proximal Policy Optimization (PPO) 
2) Direct Preference Optimization (DPO)

###### Reinforcement Learning from Human Feedback
- first minimize the $\ell_\mathrm{RM}$ [[loss function]] to train a reward model $r_\vartheta(X, Y)$ to rate responses such that $r_\vartheta(X, Y^+) > r_\vartheta(X, Y^-)$

$$
\ell_\mathrm{RM} = -\log \sigma\left(r_\vartheta(X, Y^+)-r_\vartheta(X, Y^-)\right)
$$

- in a second step, train the actual model $\pi_\theta$ with the reward model as trainer
- the component $\beta\mathrm{KL}(\pi_\theta || \pi_{SFT})$ is to make sure that the model doesn't deviate too much from the original model $\pi_{SFT}$ (after pre-training and SFT)
$$
\max_\theta \mathbb{E}_{Y\sim\pi_\theta(. | X)}\left[r_\vartheta(X, Y) - \beta\mathrm{KL}(\pi_\theta || \pi_{SFT})\right]
$$

###### Direct Preference Optimization
- minimize $\ell_\mathrm{DPO}$ such that $\pi_\theta(Y^+ | X) > \pi_\theta(Y^- | X)$

$$
\ell_\mathrm{DPO} = -\log \sigma\left(\beta[\log \pi_\theta(Y^+ | X) - \log \pi_\theta(Y^- | X)]\right)
$$



Tags: ml WS2526
<!--ID: 1764591468175-->
END


START
Basic
what is SFT?
- how does it fit in the two-stage training paradigm?
- what comes before and after?
- what are its limitations?
Back: 
## Two-stage training paradigm

Out of the box, a pretrained [[LLM]] mostly **continues text patterns**.  
To turn it into a useful assistant (e.g. a chatbot), training is done in **two stages**:

### Stage 1: Pretraining
- Train on very large, general text-based datasets (web, books, code, etc.).
- Objective:
  - **Base model with broad language capabilities**
  - Learns patterns of grammar, discourse, reasoning, and factual associations.
- Extremely compute-intensive and expensive.

### Stage 2: Post-training / Alignment

- Turn the base model into a **model aligned with human intentions**  
  (helpful, instruction-following, and safer to deploy).
- **much cheaper** than pre-training 

#### Step 1: Supervised Fine-Tuning (SFT / instruction tuning) 
- continue training the pretrained model with the **same next-token prediction loss**, but now on **high-quality instruction–response pairs** instead of raw web text.
- training data is **written by humans** with quality over quantity approach
- Example: Input: “Summarize this text: …” → Target: a clean, human-written summary.
##### limitations
- no negative feedback for unsafe or wrong answers
- only trained on high quality and correct questions (no for example conflicting instructions)
- hallucinations is not prevented

#### Step 2: alignment on preference 
- **general challenge**: often there is no single correct answer and human preference depends on values 
- general approach: **collect human preference** and then t**rain the model to produce responses that humans prefer**
##### collecting human preference
- collecting **human absolute preference** (e.g. scale 0 to 10) is very unreliable, but **relative preference is much more consistent**
1) generate a **promt dataset**$\{X^{(1)},...., X^{(n)}\}$
2) generate multiple responses for each promt $\left\{Y^{(1)}_{(1)},..., Y^{(1)}_{(k)}, Y^{(2)}_{(1)...}\right\}$
3) lat humans rate the response answer combination relative to each other (either in pairs $(X, Y^+, Y^-)$ or as a total order for each promt)

##### training the model for preference
- $\pi_\theta$ is the [[LLM]] after the SFT step (request/response level and not token level) that is optimized

$$
\pi_\theta(Y | X) = \mathbb{P}_\theta(Y| X)
$$

- two approaches but currently only DPO is used because its simpler with comparable results
1) Reinforcement Learning from Human Feedback (RLHF) with Proximal Policy Optimization (PPO) 
2) Direct Preference Optimization (DPO)

###### Reinforcement Learning from Human Feedback
- first minimize the $\ell_\mathrm{RM}$ [[loss function]] to train a reward model $r_\vartheta(X, Y)$ to rate responses such that $r_\vartheta(X, Y^+) > r_\vartheta(X, Y^-)$

$$
\ell_\mathrm{RM} = -\log \sigma\left(r_\vartheta(X, Y^+)-r_\vartheta(X, Y^-)\right)
$$

- in a second step, train the actual model $\pi_\theta$ with the reward model as trainer
- the component $\beta\mathrm{KL}(\pi_\theta || \pi_{SFT})$ is to make sure that the model doesn't deviate too much from the original model $\pi_{SFT}$ (after pre-training and SFT)
$$
\max_\theta \mathbb{E}_{Y\sim\pi_\theta(. | X)}\left[r_\vartheta(X, Y) - \beta\mathrm{KL}(\pi_\theta || \pi_{SFT})\right]
$$

###### Direct Preference Optimization
- minimize $\ell_\mathrm{DPO}$ such that $\pi_\theta(Y^+ | X) > \pi_\theta(Y^- | X)$

$$
\ell_\mathrm{DPO} = -\log \sigma\left(\beta[\log \pi_\theta(Y^+ | X) - \log \pi_\theta(Y^- | X)]\right)
$$



Tags: ml WS2526
<!--ID: 1764591468178-->
END



START
Basic
explain the **two stage training paradigm** for LLMs and why its necessary
Back: 
## Two-stage training paradigm

Out of the box, a pretrained [[LLM]] mostly **continues text patterns**.  
To turn it into a useful assistant (e.g. a chatbot), training is done in **two stages**:

### Stage 1: Pretraining
- Train on very large, general text-based datasets (web, books, code, etc.).
- Objective:
  - **Base model with broad language capabilities**
  - Learns patterns of grammar, discourse, reasoning, and factual associations.
- Extremely compute-intensive and expensive.

### Stage 2: Post-training / Alignment

- Turn the base model into a **model aligned with human intentions**  
  (helpful, instruction-following, and safer to deploy).
- **much cheaper** than pre-training 

#### Step 1: Supervised Fine-Tuning (SFT / instruction tuning) 
- continue training the pretrained model with the **same next-token prediction loss**, but now on **high-quality instruction–response pairs** instead of raw web text.
- training data is **written by humans** with quality over quantity approach
- Example: Input: “Summarize this text: …” → Target: a clean, human-written summary.
##### limitations
- no negative feedback for unsafe or wrong answers
- only trained on high quality and correct questions (no for example conflicting instructions)
- hallucinations is not prevented

#### Step 2: alignment on preference 
- **general challenge**: often there is no single correct answer and human preference depends on values 
- general approach: **collect human preference** and then t**rain the model to produce responses that humans prefer**
##### collecting human preference
- collecting **human absolute preference** (e.g. scale 0 to 10) is very unreliable, but **relative preference is much more consistent**
1) generate a **promt dataset**$\{X^{(1)},...., X^{(n)}\}$
2) generate multiple responses for each promt $\left\{Y^{(1)}_{(1)},..., Y^{(1)}_{(k)}, Y^{(2)}_{(1)...}\right\}$
3) lat humans rate the response answer combination relative to each other (either in pairs $(X, Y^+, Y^-)$ or as a total order for each promt)

##### training the model for preference
- $\pi_\theta$ is the [[LLM]] after the SFT step (request/response level and not token level) that is optimized

$$
\pi_\theta(Y | X) = \mathbb{P}_\theta(Y| X)
$$

- two approaches but currently only DPO is used because its simpler with comparable results
1) Reinforcement Learning from Human Feedback (RLHF) with Proximal Policy Optimization (PPO) 
2) Direct Preference Optimization (DPO)

###### Reinforcement Learning from Human Feedback
- first minimize the $\ell_\mathrm{RM}$ [[loss function]] to train a reward model $r_\vartheta(X, Y)$ to rate responses such that $r_\vartheta(X, Y^+) > r_\vartheta(X, Y^-)$

$$
\ell_\mathrm{RM} = -\log \sigma\left(r_\vartheta(X, Y^+)-r_\vartheta(X, Y^-)\right)
$$

- in a second step, train the actual model $\pi_\theta$ with the reward model as trainer
- the component $\beta\mathrm{KL}(\pi_\theta || \pi_{SFT})$ is to make sure that the model doesn't deviate too much from the original model $\pi_{SFT}$ (after pre-training and SFT)
$$
\max_\theta \mathbb{E}_{Y\sim\pi_\theta(. | X)}\left[r_\vartheta(X, Y) - \beta\mathrm{KL}(\pi_\theta || \pi_{SFT})\right]
$$

###### Direct Preference Optimization
- minimize $\ell_\mathrm{DPO}$ such that $\pi_\theta(Y^+ | X) > \pi_\theta(Y^- | X)$

$$
\ell_\mathrm{DPO} = -\log \sigma\left(\beta[\log \pi_\theta(Y^+ | X) - \log \pi_\theta(Y^- | X)]\right)
$$


_____________

### in context learning
- ability of LLMs to **learn tasks from examples provided in the prompt** without updating the weight
- emerges naturally from large-scale training on the next-token prediction objective because the model was trained on billions of fragments containing:
	• examples → solution
	• question → answer
	• pattern → continuation
#### algorithmic ICL
- algorithm-like behaviors: copying, sorting, repeating patterns, matching prefixes
- example: prompt: **A B C ... A B ?** → prediction: **C**
#### semantic ICL
- The model leverages its latent world knowledge and aligns it with the examples inside the prompt
	→ deduces what the user wants based on patterns in the examples
- example: 
	- prompt: **cat → German: Katze, English: dog → German: ?**  
	- prediction: **Hund**

#### limitations
- no reliable instruction following and very sensitive to formatting
- no guarantees of correctness, safety, preference alignment, consistency
	→ model may ignore instructions


Tags: ml WS2526
<!--ID: 1764257200499-->
END
