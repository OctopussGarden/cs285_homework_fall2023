[TOC]

## Hw1-solution

### 1. Analysis

$$
\mathbb{E}_{p_{\pi^*}(s)} \pi_\theta \left( a \neq \pi^*(s) \mid s \right) = \frac{1}{T} \sum_{t=1}^{T} \mathbb{E}_{p_{\pi^*}(s_t)} \pi_\theta \left( a_t \neq \pi^*(s_t) \mid s_t \right) \leq \epsilon
$$

#### 1.1 Show that $\sum_{s_t} \left| p_{\pi_\theta}(s_t) - p_{\pi^*}(s_t) \right| \leq 2T\epsilon$

> ==Solution:==
>
> For $\pi_{\theta} \left( a_t \neq \pi^*(s_t) \mid s_t \right) \leq \epsilon$, for every $s_t \in {\rm supp}(p_{\pi^{\star}})$
>
> i.e. we have
> $$
> p_{\pi_\theta}(s_t) = (1 - \epsilon_{s_t})^t p_{\pi^*}(s_t) + (1 - (1-\epsilon_{s_t})^t)p_{\rm mistake}(s_t)
> $$
> and the identity (for $\epsilon \in [0,1]$) 
> $$
> (1-\epsilon)^T \geq 1-T\epsilon
> $$
> plus, **the worst case variation divergence is 2**, then
> $$
> \begin{aligned}
> \sum_{s_t} \left| p_{\pi_\theta}(s_t) - p_{\pi^*}(s_t) \right| &= \sum_{s_t} \left|(1 - (1-\epsilon)^t) (p_{\rm mistake}(s_t) - p_{\pi^*}(s_t)) \right| \\
> &\leq 2 (1 - (1-\epsilon)^T)\\
> &\leq 2T\epsilon
> \end{aligned}
> $$

#### 1.2

We have
$$
J(\pi) = \sum_{t=1}^{T} \mathbb{E}_{p_\pi(s_t)} r(s_t)
$$
Then, 
$$
\begin{aligned}
J(\pi^*) - J(\pi_\theta) &= \sum_{t=1}^{T} \mathbb{E}_{p_{\pi^*}(s_t)} r(s_t) - \mathbb{E}_{p_{\pi_\theta}(s_t)} r(s_t) \\
&= \sum_{t=1}^{T} \sum_{s_t} \left(p_{\pi^*}(s_t) - p_{\pi_{\theta}}(s_t) \right) r(s_t) \\
&\le 2T\epsilon \sum_{t=1}^{T} r(s_t)\\
\end{aligned}
$$


- a)  Where $\left|r(s_t) \leq R_{\rm max} \right|$ and $r(s_t) = 0, \text{for all } t \lt T$,  
  $$
  \sum_{t=1}^{T} r(s_t) = r(s_T) \le R_{\max}
  $$
  ​	$J(\pi^*) - J(\pi_\theta) = \mathcal{O}(T\epsilon)$

- b) While for random reward, $\sum_{t=1}^{T} r(s_t)$ is in $\mathcal{O}(T)$, so 

  ​	$J(\pi^*) - J(\pi_\theta) = \mathcal{O}(T^{2} \epsilon)$

