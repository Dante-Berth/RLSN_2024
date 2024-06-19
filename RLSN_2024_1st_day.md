# RLSN
## Introduction ( From Stochastic Networks to Reinforcement Learning)
It is composed applied probability MCMC, stasticical learning, Operation research, MDPs, Optimisation, Complex networks , Queueing, Scheduking, Algorithms design.
Stochastic networks are not stochastic neural networks. Stochastic networks can be queues, many operationnal problems and more.
# Day 1
## Learning and Control in Countable State Spaces (presented by R. Srikant UIUC) 
Stochastic Network such as queueing.
Chess, go and other games can be large enven if it is finite-state spaces (limited) while it exists uncountable state space but structured problmes such as $$x_{k+1} = Ax_{k}+Bu_{k}+w_{k}$$ where A, B are learnt by a neural network for instance. It exists problems behind it such as countable state spaces ( limited structure positivity, easy stabilizability, how can we exploit it ?).\\

For the last problem, we want to stabilize thanks to exploit the problem structure. The example taken is a matrix of queues which can be seen as a problem of datacenters where packets arrive to each queue according to some arrival process. You need to control permutation matrices, find a sequence of such matrices to minimize average delay. Another problem is also scheduling 5G network. It is also a problem allocated package. Ride Hailing customers and cars control matches, control prices, control payments, the goal is to maximize revenue minus weighted delay (taxi company).Scheduling jobs on server / processes how to accelerate according a graph of jobs to complete. The goal is to allocate tasks to minimize mean job delay.
### For countable state spaces.
$$s_{k+1}=f(s_{k},a_{k},w_{k})\\
    - s_{k}\in mathbb{Z} (vector of queues)
    - a_{k} action 
    - w_{k} random process   
$$

Policy evaluation
$$
J_{pi} +Q_{s,a} = c(s) + \mathbb{E}[Q(s',\pi(s')|s,a)]
$$
Policy Improvement (NPG)
$$
\pi_{k+1}(a|s) proporionnalte \pi_{k}(a|s) exp(-\eta\widehat{Q_{\pi_{k}}(s,a)})
$$
NN cannot perfectly find Q.
In theory for NPG update, we have a convergence for $J_{\pi}$ in $$O(\sqrt(T\widehat{Q_{max}}))$$ but $\widehat{Q_{max}}$ can be infinite.
For queuing $Q_{\pi_{k}}(s,a)$ is quadractic according to the size of the queue.\\
Regret is $$\sum_{k=1}^{T}(J_{\pi_{k}}-J_{\pi^{*}})
To conclude, for a given problem with the right assumptions you can derive a good algorithm which obeys to convergence. For optimiality, you need a large neural network to have a good approximation of Q function.

### The biais of constant step size in reinforcement learning
$$\theta_{n+1} = \theta_{n} + \alpha(f(\theta_{n},Y_{n})+M_{n+1})$$
$$\alpha$$ is step_size (constant or decreasing), while $$f$$ is gradient of the function, $$Y_{n}$$ is markov chaine and $$M_{n+1}$$ is noise.\\
What is the behavior of $\theta_{n}$ given n towards $\inf$
$\theta_{n}$ can be seen as an ODE. A good approximation is to do the average of $\theta_{n}$ but we want to understand the biais $ \mathbb{E}[\theta_{n}]-\phi_{n}$
\\
$$\theta_{n+1} = \theta_{n} + \alpha(f(\theta_{n},Y_{n})+M_{n+1})\\
\phi_{n+1} = \phi_{n}+\alpha \widehat{f}(\phi_{n})
$$

### Natural policy gradient for Queues
countably infinite queues, Does NPG converge to the globally optimal policy for queueing MDP if so how fast ? We care about averagfe cost and countablye infinite state space.
Uniform Lyapunov Stability  

### Average reward ($\gamma = 1$)
Seems difficult

# Day 2
## Finite-time High Probability Bounds for Polyak-Ruppert Averaged Iterates of <u>Linear</u> Stochastic Approximation

$$f(\theta^{*}) = 0$$ but you do not have $f$ called oracle,$F(\theta;Z_{n})$ but $\mathbb{E}[F(\theta;Z_{n})] =  f(\theta)$
$$\theata_{n+1} = \theta_{n} + \alpha_{n}F(\theta_{n};Z_{n})$$ called stochastic approximation
I understood nothing

# Day 3
## Learning-Augmented Algorithms for MDPs



