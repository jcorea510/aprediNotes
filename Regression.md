## Introduction
The are linear and non linear regression. Based in discriminative probabilistic model p(t|x,theta), suppose the next follow set of definitions.<br>
**Hypothesis class**: It refers to the supposed possible set of functions that the labels follows. It is inferred as a training model for the developer.<br>
**Capacity**: It is given by the order M of the hypothesis class. It's the number of the degress of freedom in the model. High capacity has the ability to better describe the training set but reduce the generalization.<br>
**Model parameters**: Identify the specific model within the hypothesis class. It is given by *biases* and *weights*.<br> 

The function may be given by:
$$y=\underline{W}h(\underline{x},\underline{\theta})$$
## Maximum likelihood criterion.
It aim to find the set of parameters \theta under which the training set D has the maximum probability of being observed.
$$p(t_{D}|x_{D},w,\beta)=\prod_{n=1}^{N}p(t_{n}|x_{n},w,\beta)$$
Or the Log-likelihood (LL) function. Assuming normal distribution.
$$ln(p(t_{D}|x_{D},w,\beta))=-\frac{\beta}{2}\sum_{n=1}^{N}(\mu(x_{n},w)-t_{n})^2+\frac{N}{2}ln(\frac{B}{2\pi})$$
By solving the minimization problem of the negative LL (NLL) the solution for better parameters can be solved.
$$min_{\beta,w}-\frac{1}{N}\sum_{n=1}^{N}ln[p(t_{n}|x_{n},w,\beta)]$$
## Objective function.
Assuming normal distribution. The objective funtion may be expressed as:
$$J(\underline{\theta})=\frac{1}{2}\sum_{i=1}^{N}w^{i}(h_{\underline{\theta}}(\underline{x}^{(i)})-\underline{y})^{2}$$
Which yield to the closed solution (normal equation), when possible by the hypothesis. 
$$\underline{\theta}=(\underline{X}^{T}W\underline{X})^{-1}\underline{X}^{T}W\underline{y}$$
## Gradient descend
### Pure gradient descent
It consist if finding the optimal solution throught iterations and and evaluation. It may be found using
the gradient of the objective function and a rule of actualization of parameters.
$$\theta^{(t+1)}:=\theta^{t}-\alpha\nabla J(\theta^{t})$$
**Stochastic gradient descend**: From the training set it is choose just one data to calculate the gradient each time. <br>
**Batch gradient descend**:It does a partition of the training set D and use a random sub training set each iteration to estimate new parameters. <br>
**Mini batches**: It's a mix between Stochastic gradient descend and Batch gradient descend <br>
**Overfitting**: It happens when the order of hypothesis is to high so that it represents well the training data, but fails to predicts new data.

**Underfitting**: It is when the order of hypothesis is low so that it fails to represent the training data set and new data.

### Momentum gradient descend
The update rule is split in two steps. At first it is considered the speed of gradient descend, and then update the parameters. The idea behind momentum, is to filter noise added for random points selection in Stochastic gradient descend, through a momentum that contain information about previous evaluated points so that the total descend tries to point to the minimum, even when new evaluation point doesn't. This is done with a digital filter.
$$v^{(t)}=\beta v^{(t-1)}+(1-\beta)\nabla_{\theta}J(\theta^{(t)})$$
$$\theta^{(t+1)}=\theta^{(t)}-\alpha v^{t}$$
### RMSprop (Root Mean Square propagation)
This takes the square of gradient. So that it add more value to small gradient but stable, and slow with high gradient and inconsistent value.  It reduce noise in data. It adapts parameter to each data. It follow a two step update rule too.
$$s^{(t)}=\beta_{2}s^{(t-1)}+(1-\beta_{2})[\nabla_{\theta}J(\theta^{(t)})]^{2}$$
$$\theta^{(t+1)}=\theta^{(t)}-\alpha diag(\sqrt{s^{(t)}+\epsilon})^{-1}\nabla_{\theta}J(\theta^{(t)})$$
### Adam (Adaptive momentum optimization)
Adam is a mixture between RMSprop and momentum. It follow a three step update rule, that filter unwanted high gradient descend and noise in data through momentum.
$$v^{(t)}=\beta v^{(t-1)}+(1-\beta)\nabla_{\theta}J(\theta^{(t)})$$
$$s^{(t)}=\beta_{2}s^{(t-1)}+(1-\beta_{2})[\nabla_{\theta}J(\theta^{(t)})]^{2}$$
$$\theta^{(t+1)}=\theta^{(t)}-\alpha diag(\sqrt{s^{(t)}+\epsilon})^{-1}v^{(t)}$$

## Next topic
[[Probabilistic models]]

