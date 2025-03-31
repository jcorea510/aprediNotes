A lot of models has similar properties enclosed in a family of probabilistic models, known as Exponential Family. 

## Exponential family
$$p(x|\eta)=\frac{1}{Z(\eta)}\exp\left(\sum_{k=1}^{K}\eta_{k}u_{k}(x)\right)m(x)=\frac{1}{Z(\eta)}\exp\left(\eta^{T}u(x)\right)m(x)$$
Given an x discrete or continuous value vector; natural parameters eta; sufficient statistic u, with each uk being a function of x; m(x) the base measure; and Z(eta) a partition function.
$$z(\eta)=\int \exp(\eta^{T}u(x))m(x)$$
And the unnormalized distribution is given by:
$$\tilde{p}(x|\eta)=\exp(\eta^{T}u(x))m(x)$$
It is said that the distributions functions belonging to the exponential family are those that *energy function* is linear in the natural parameters. 
$$\ln(\tilde{p}(x|\eta))=\eta^{T}u(x)+\ln(m(x))$$
### Bernoulli Distribution
For a binary rv x in {0, 1}, and u=Pr\[x=1\]
$$Bern(x|\mu)=\mu^{x}(1-\mu)^{1-x}$$
Since the sufficient statistic u(x)=x, and the measure function is m(x)=1, the map between u and eta is:
$$\eta=\ln(\frac{\mu}{1-\mu})$$
The inverse is know as *logistic sigmoid function*
$$\mu=\sigma(\eta)=\frac{1}{1+e^{-\eta}}$$
### Normal Distribution
$$\mathcal{N}(x|v,\sigma^2)=\frac{1}{\sqrt{2\pi\sigma^2}}\exp(-\frac{(x-\mu)^{2}}{2\sigma²})$$
It is in the exponential family by:
$$\eta=v$$
$$u(x)=x$$
$$m(x)=\frac{1}{\sqrt{2\pi}}\exp(-\frac{x^{2}}{2})$$
$$a(\eta)=\frac{\eta²}{2}$$
### Other distributions.
Poison, Gamma, Dirichlet, Multinomial, Beta, etc.

## Next topic.
[[Generalized linear models]]

