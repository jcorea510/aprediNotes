## Introduction
It's the set of learning algorithms in which data training set has values and labels. Label indicates the spectated result to be obtained if the model learned correctly. 

In **Supervised learning** we aim to learn a predictive distribution p(t|x), for the label t given a co-variate variable x. When the label t is discrete the used algorithms are classified as [[Clasification]] algorithms,  when t is continuous It is say to be a [[Regression]] problem.

So that in **Unsupervised learning** we aim to discover how to learn properties of the mechanism that generate the data of interest.

In **Reinforced learning** the task consist in learning through optimal inferring based in a punishment or reward system as a result of actions.

In **Pasive learning** the algorithm just receive all data; while **Active learning** algorithms can affect the choice on the basis of prior observations.
Meanwhile, **offline learning** operates over a batch of training data, and **online learning** operates in a streaming fashion.

## Mathematical approach

The outlined learning task assumes that x and t are related for a function t=f(x) with properties as smoothness for unobserved domain points x. If not it is impossible to solve, as given by the *no free launch theorem*. The set of assumptions is called *bias*. In the learning process it is necessary to minimize a *generalization loss*.

### Inference
It is define a non negative loss function.
$$l_{q}(t-\hat{t})=|t-\hat{t}|^{q}$$
The the generalization loss is just the espected value of the loss function.
$$\hat{L_{p}}=E_(x,t)\backsim pxt[l(t,\hat{t}(x))]$$
The solution to the problem is given by the optimal solution (derivative equal to cero).
$$\hat{t}^{*}(x)=argmin(E_{t\backsim p_{t|x}}[l(t,\hat{t})|x])$$
## Frequentist approach
Asumes a independent identical distributed (i.i.d) data points (x,t) in D for a distribution p(x,t). Since the p(x,t) is unknown is not possible to solve optima solutions of generalization loss.

It can be solved by either finding pD(t|x) first and then finding p(x,t) by inference. <br>
The other way is via *Empirical Risk Minimization (ERM)*. It aim to find a minimal estimation of generalization loss as:
$$L_{D}(\hat{t(x)})=\frac{1}{N}\sum_{n=1}^{N}l(t_{n},\hat{t}(x_{n}))$$

This point to the next fundamental distinction.<br>
**Discriminative probabilistic model**: Learn directly the posterior p(t|x).<br>
**Generative probabilistic model**: Learn p(x,t) and posterior compute p(t|x).<br>
## Next topic
Follow [[Regression]]

