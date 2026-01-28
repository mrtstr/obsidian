### perference training
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
