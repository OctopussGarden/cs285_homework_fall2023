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

### 2. Code
Show in codes
### 3. Behavioral Cloning
**Outputs**
- `Ant-v4`
  ```shell
  Eval_StdReturn : 0.0
  Eval_MaxReturn : 453.48095703125
  Eval_MinReturn : 453.48095703125
  Eval_AverageEpLen : 1000.0
  Train_AverageReturn : 4681.891673935816
  Train_StdReturn : 30.70862278765526
  Train_MaxReturn : 4712.600296723471
  Train_MinReturn : 4651.18305114816
  Train_AverageEpLen : 1000.0
  Training Loss : 3.739296880667098e-05
  Train_EnvstepsSoFar : 0
  TimeSinceStart : 1.4117987155914307
  Initial_DataCollection_AverageReturn : 4681.891673935816
  ```
- `HalfCheetah`
  ```shell
  Eval_StdReturn : 0.0
  Eval_MaxReturn : 1598.0390625
  Eval_MinReturn : 1598.0390625
  Eval_AverageEpLen : 1000.0
  Train_AverageReturn : 4034.7999834965067
  Train_StdReturn : 32.8677631311341
  Train_MaxReturn : 4067.6677466276406
  Train_MinReturn : 4001.9322203653724
  Train_AverageEpLen : 1000.0
  Training Loss : 7.291514066309901e-06
  Train_EnvstepsSoFar : 0
  TimeSinceStart : 1.2278029918670654
  Initial_DataCollection_AverageReturn : 4034.7999834965067
  ```
- `Hopper`
  ```shell
  Eval_StdReturn : 0.0
  Eval_MaxReturn : 1362.51611328125
  Eval_MinReturn : 1362.51611328125
  Eval_AverageEpLen : 1000.0
  Train_AverageReturn : 3717.5129936182307
  Train_StdReturn : 0.3530361779417035
  Train_MaxReturn : 3717.8660297961724
  Train_MinReturn : 3717.159957440289
  Train_AverageEpLen : 1000.0
  Training Loss : 6.329021562123671e-05
  Train_EnvstepsSoFar : 0
  TimeSinceStart : 1.332962989807129
  Initial_DataCollection_AverageReturn : 3717.5129936182307
  ```
- `Walker2d`
  ```shell
  Eval_StdReturn : 0.0
  Eval_MaxReturn : 897.5069580078125
  Eval_MinReturn : 897.5069580078125
  Eval_AverageEpLen : 1000.0
  Train_AverageReturn : 5383.310325177668
  Train_StdReturn : 54.15251563871789
  Train_MaxReturn : 5437.462840816386
  Train_MinReturn : 5329.1578095389505
  Train_AverageEpLen : 1000.0
  Training Loss : 0.00044358352897688746
  Train_EnvstepsSoFar : 0
  TimeSinceStart : 1.322859525680542
  Initial_DataCollection_AverageReturn : 5383.310325177668
  ```