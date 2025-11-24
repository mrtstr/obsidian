### learning rate scheduling
- large models are extremely sensitive to the learning rate
- a learning rate scheduling ensures
	- stable early training
	- fast convergence
	- avoid divergence / loss spikes
- there are two stages **warm-up phase** and the **decay phase**

#### warm-up phase
- start slow and linear increase util the maximum learning rate $\eta_\mathrm{max}$ is reached after $T_\mathrm{warmup}$ steps
- prevents unstable gradients when weights are still random
$$
\eta(t) = \eta_\mathrm{max} \cdot \frac{1}{T_\mathrm{warmup}}
$$

#### decay phase
- after warm-up, LR gradually decreases for **smooth convergence** and **reduced loss oscillations** using cosine decay

$$
\eta(t) = \eta_\mathrm{min} + \frac{1}{2} (\eta_\mathrm{max} - \eta_\mathrm{min}) \cdot \left(1+\cos\left(\pi\frac{t-T_\mathrm{warmup}}{T_\mathrm{total} -T_\mathrm{warmup}}\right)\right)
$$

![[Pasted image 20251124144429.png]]

# ----------------

![[nn adam optimizer#adam optimizer]]


# anki

START
Basic
[[nn learning rate scheduling]]
- why is it important for LLM training?
- two phases with goal and equation

Back: 
### learning rate scheduling
- large models are extremely sensitive to the learning rate
- a learning rate scheduling ensures
	- stable early training
	- fast convergence
	- avoid divergence / loss spikes
- there are two stages **warm-up phase** and the **decay phase**

#### warm-up phase
- start slow and linear increase util the maximum learning rate $\eta_\mathrm{max}$ is reached after $T_\mathrm{warmup}$ steps
- prevents unstable gradients when weights are still random
$$
\eta(t) = \eta_\mathrm{max} \cdot \frac{1}{T_\mathrm{warmup}}
$$

#### decay phase
- after warm-up, LR gradually decreases for **smooth convergence** and **reduced loss oscillations** using cosine decay

$$
\eta(t) = \eta_\mathrm{min} + \frac{1}{2} (\eta_\mathrm{max} - \eta_\mathrm{min}) \cdot \left(1+\cos\left(\pi\frac{t-T_\mathrm{warmup}}{T_\mathrm{total} -T_\mathrm{warmup}}\right)\right)
$$

![[Pasted image 20251124145547.png]]

Tags: ml WS2526
<!--ID: 1763995026501-->
END
