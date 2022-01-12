**moment generating function**: $\psi(t) =E\left[e^{t X}\right] =\int e^{i X} d F(x)$

<img src="C:\Users\ROG\AppData\Roaming\Typora\typora-user-images\image-20211018202131018.png" alt="image-20211018202131018" style="zoom:40%;" />

**Conditional Expectation**: $P\{X=x \mid Y=y\}=\frac{P\{X=x, Y=y\}}{P\{Y=y\}}$

**Exponential Distribution:**
$$
f(x)= \begin{cases}\lambda e^{-\lambda x} & x \geq 0 \\ 0 & x<0\end{cases}\\
F(x)=\int_{-\infty}^{x} f(y) d y= \begin{cases}1-e^{-\lambda x} & x \geq 0 \\ 0 & x<0\end{cases}\\
E\left[e^{\prime X}\right]=\int_{0}^{\infty} e^{i x} \lambda e^{-\lambda x} d x=\frac{\lambda}{\lambda-t}\\
E[X]=1 / \lambda, \quad \operatorname{Var}(X)=1 / \lambda^{2}
$$
<img src="C:\Users\ROG\AppData\Roaming\Typora\typora-user-images\image-20211018202818563.png" alt="image-20211018202818563" style="zoom:40%;" />

<img src="C:\Users\ROG\AppData\Roaming\Typora\typora-user-images\image-20211018202902684.png" alt="image-20211018202902684" style="zoom:40%;" />

<img src="C:\Users\ROG\AppData\Roaming\Typora\typora-user-images\image-20211018203034186.png" alt="image-20211018203034186" style="zoom:40%;" />

**Poisson Process**:

​	$P\{N(t+s)-N(s)=n\}=e^{-\lambda t} \frac{(\lambda t)^{n}}{n !}, \quad n=0,1$

​	$P\left\{X_{1}>t\right\}=P\{N(t)=0\}=e^{-\lambda t}$

​	$S_{n}=\sum_{i=1}^{n} X_{t}, \quad n \geq 1, f(t)=\lambda e^{-\lambda^{\prime}} \frac{(\lambda t)^{n-1}}{(n-1)^{\prime}}, \quad t \geq 0$

**Nonhomogeneous Poisson Process**:

​	$m(t)=\int_{0}^{t} \lambda(s) d s$

​	$P\{N(t+s)-N(t)=n\}
=\exp \{-(m(t+s)-m(t))\}[m(t+s)-m(t)]^{n} / n^{\prime}, n \geq 0$

**Compound Poisson Process**:

​	$W=\sum_{i=1}^{N} X_{t},E[W] =\lambda E[X] \operatorname{Var}(W) =\lambda E\left[X^{2}\right]$

​	$E[W h(W)]=\lambda E[X h(W+X)]$

**Conditional Poisson Process**:

​	$P\{\Lambda \leq x \mid N(t)=n\}=\frac{\int_{0}^{x} e^{-\lambda t}(\lambda t)^{n} d G(\lambda)}{\int_{0}^{\infty} e^{-\lambda t}(\lambda t)^{n} d G(\lambda)}$

**Markov Chain**:

​	$P_{i j}^{n+m}=\sum_{k=0}^{\infty} P_{i k}^{n} P_{k j}^{m}$

​	$i \leftrightarrow j:$ same class, *irreducible*: only one class

​	*aperiodic*: $d(i) = 1$

​	$f_{i j}^{n}=P\left\{X_{n}=j, X_{k} \neq j, k=1,..., n-1 \mid X_{0}=i\right\}, f_{ij}=\sum_{n=1}^{\infty} f_{i j}^{n}$

​	*recurrent*: $f_{jj} = 1 \Leftrightarrow \sum_{n=1}^{\infty} P_{jj}^{n}=\infty$   *transient*: otherwise

​	$\mu_{j j}= \begin{cases}\infty & \text { if } j \text { is transient } \\ \sum_{n=1}^{\infty} n f_{j j}^{n} & \text { if } j \text { is recurrent. }\end{cases}$

​	$\pi_{j}=\lim _{n \rightarrow \infty} P_{jj}^{n d(\jmath)}$

​	*positive recurrent*: $\mu_{jj} < \infty \Leftrightarrow \pi_j > 0$

​	*null recurrent*: $\mu_{jj} = \infty \Leftrightarrow \pi_j = 0$

​	class property: $d(i) = d(j)$, *Positive(null) recurrent*

​	*stationary*: $P_{j}=\sum_{i=0}^{\infty} P_{i} P_{i j}, \quad j \geq 0$

​	*ergodic*: irreducible aperiodic Markov chain, all states ate positive recurrent: $\pi_{j}=\lim _{n \rightarrow \infty} P_{ij}^{n}>0$

​	$\pi_{j}=\sum_{i} \pi_{i}P_{i j}\\ \sum_{j} \pi_{j}=1$