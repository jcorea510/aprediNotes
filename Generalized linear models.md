Since there is a various probability distribution functions that belongs to Exponential Family. If our problem has the next characteristics:
1. y|x;theta ~ Exponential Family (eta)
2. Given x; our task is to predict E\[T(y)\|x] and with frecuency T(y)=y, so that h_theta(x)=E\[y|x\]
3. As design criteria is taken the parameter eta=theta^{T}x
The is a set of cases that allow us to generalized all models as linear models.

## Ordinary Minimum Squares (OLS)
It is solve by Normal distributions. It takes a continuous variable y so that:
$$y|x;\theta\backsim\mathcal{N}(\mu,\sigma^{2})$$
$$h_{\theta}(x)=E[y|x;\theta]=\mu=\theta^{T}x$$
## Logistic regression (LR)
It is used in binary classification y in {0,1}. It is solved with Bernoulli distribution as:
$$y|x;\theta\backsim Ber(\phi)$$
$$E[y|x;\theta]=p(y=1|x;\theta)=\phi$$
$$h_{\theta}(x)=\phi=\frac{1}{1+e^{-\theta^{T}x}}$$
## Softmax
It considerate a multinomial distribution y in {1,2,...k} with k classes. If there are parameters phi=(phi1,phi2,...phik) so that p(y=i)=phii. To set softmax as part of exponential family it is taken unit vectors T(i) in R^{k-1}
$$T(1)=\left[\matrix{1\\0\\.\\.\\.\\0}\right];T(2)=\left[\matrix{0\\1\\.\\.\\.\\0}\right];...;T(k-1)=\left[\matrix{0\\0\\.\\.\\.\\1}\right];T(k)=\left[\matrix{0\\0\\.\\.\\.\\0}\right]$$
And indicative function 1{a}=1 if true and 1{a}=0 if false. Assuming a response know as softmax regression:
$$p(y=i|x;\Theta)=\phi=\frac{e^{\theta_{i}^{T}x}}{\sum_{j=1}^{k}e^{\theta_{j}^{T}x}}$$
The hypothesis is given then:
$$h_{\Theta}(x)=\left[\matrix{\phi_{1}\\\phi_{2}\\.\\.\\.\\\phi_{k-1}}\right]$$
The minimization can be solved by maximum log-likelihood, which is maximized by ascend gradient. Which yield to:
$$\nabla_{\Theta}l(\Theta)=\sum_{i=1}^{m}x^{(i)}(\tilde{y}^{(i)}-\tilde{h}_{\Theta}(x^{(i)}))^{T}$$
$$\Theta^{(t+1)}=\Theta^{(t)}-\alpha\nabla_{\Theta}l(\Theta)$$
It may be vectorized as:
$$\Theta^{t+1}=\Theta^{t}-\alpha X^{T}(H_{\Theta}-Y)$$


