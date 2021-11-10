# Homework 3

#### Problem 1

##### (a)

By the definition of the subdifferential:

$\begin{aligned} \partial \mathbb{I}_{C}(x) &= \{s\in \mathbb{R^n}: \mathbb{I}_{C}(y) - \mathbb{I}_{C}(x) \ge s^T(y-x), \forall y \in C\}  \\ &= \{s\in \mathbb{R^n}: s^T(y-x) \le 0, \forall y \in C\} \end{aligned}$

##### (b)

By the result in (a), $\partial \mathbb{I}_{R^n_+}(x) = \{s\in \mathbb{R^n}: s^T(y-x) \le 0, \forall y \in \mathbb{R}^n_+\}$

First, let us show that $\partial \mathbb{I}_{R^n_+}(x) \sube \left\{s \in \mathbb{R}^{n}: s \leq \mathbf{0}, x^{T} s=0\right\}$

​	let $I_k = \{0,0,...,1,0,...\} \in \mathbb{R}^n$ who have 1 at k-th dim and other dims are 0

​	$\therefore \forall I_k, x + I_k \ge 0$ and $s^T(x + I_k - x) = s^T I_k = s_kI_k\le 0$

​	$\therefore s \le \mathbf{0}$

​	assume $s^Tx \ne 0$

​	$\therefore s^Tx > 0$, when let $y = 0$

​	let $y = 2x \ge \mathbf{0}, s^T(y-x) = s^Tx > 0$

​	By contradiction, $s^Tx = 0$

Second, let us show that $\partial \mathbb{I}_{R^n_+}(x) \supseteq \left\{s \in \mathbb{R}^{n}: s \leq \mathbf{0}, x^{T} s=0\right\}$

​	$\because s \le \mathbf{0}, x^Ts = 0$

​	$\therefore s^T(y - x) = s^Ty \le 0, \forall y \ge \mathbf{0}$

In conclusion, $\partial \mathbb{I}_{R^n_+}(x) = \left\{s \in \mathbb{R}^{n}: s \leq \mathbf{0}, x^{T} s=0\right\}$

#### Problem 2

##### (a)

​	By the property of $||\cdot||_2$ 

​	$\forall p_1, p_2 \in \mathbb{R}^2, \alpha \in [0,1],$

​	$\begin{aligned}  ||\alpha p_1 + (1-\alpha)p_2||_2 &\le \alpha||p_1||_2 + (1-\alpha)||p_2||_2 \\ &\le max(||p_1||_2, ||p_2||_2) \end{aligned}$ （equal iff $\alpha = 0$ or $1$)

​	assume $||p_1||_2 \le ||p_2||_2$:

​		① $||p_2||_2 < 1$:

​			$f(\alpha p_1 + (1-\alpha)p_2) \le \alpha f(p_1) + (1-\alpha) f(p_2) = 0$

​		② $||p_1||_2 < 1, ||p_2||_2 = 1$:

​			$f(\alpha p_1 + (1-\alpha)p_2) \le \alpha f(p_1) + (1-\alpha) f(p_2) = (1-\alpha) f(p_2)$ (equal iff $\alpha = 0$ or $1$)

​		③ $||p_1||_2 = ||p_2||_2 = 1$ :

​			$f(\alpha p_1 + (1-\alpha)p_2) \le \alpha f(p_1) + (1-\alpha) f(p_2) $ (equal iff $\alpha = 0$ or $1$)

​		④ $||p_2||_2 > 1$:

​			$f(p_2) = +\infty$

​			$f(\alpha p_1 + (1-\alpha)p_2) \le \alpha f(p_1) + (1-\alpha) f(p_2) $ (equal iff $\alpha = 0$ or $1$)

​		In conclusion, $f$ is convex.

##### (b)

​	let $f(1, 0) = 1$ and $f(x_1, x_2) = 0, ||(x_1, x_2)||_2 = 1, (x_1, x_2) \neq (1, 0)$

​	It's obviously that, $(1, 0, 1) \in epi(f)$ and is **isolated**

​	so $epi(f)$ is not closed.

#### Problem 3

​	$\forall x_1, x_2 \in \mathbb{R}, \alpha \in [0,1]$,

​	assume $x_1 \le x_2$:

​	① $x_1, x_2 < -1$

​		$\begin{aligned} f(\alpha p_1 + (1-\alpha) p_2) &= \frac{\alpha^2 x_1^2}{2} + \alpha (1 - \alpha) x_1 x_2 + \frac{(1-\alpha)^2 x_2^2}{2} - |\alpha p_1 + (1-\alpha) p_2)| \\ &= \frac{\alpha^2 x_1^2}{2} + \alpha (1 - \alpha) x_1 x_2 + \frac{(1-\alpha)^2 x_2^2}{2} + \alpha p_1 + (1-\alpha) p_2) \\ &\le \frac{\alpha x_1^2}{2} + \frac{(1-\alpha) x_2^2}{2} + \alpha p_1 + (1-\alpha) p_2) \\ &= \alpha f(x_1) + (1-\alpha) f(x_2) \end{aligned}$

​	② $x_1 < -1, |x_2| \le 1$

​		1' $\alpha p_1 + (1-\alpha) p_2 < -1$:

​			$\begin{aligned} f(\alpha p_1 + (1-\alpha) p_2)  &\le \frac{\alpha x_1^2}{2} + \frac{(1-\alpha) x_2^2}{2} - |\alpha p_1 + (1-\alpha) p_2)| \\ &\le \frac{\alpha x_1^2}{2} + \frac{(1-\alpha)}{8} - |\alpha p_1| \\ &= \alpha f(x_1) + (1-\alpha) f(x_2) \end{aligned}$			

​		2' $\alpha p_1 + (1-\alpha) p_2 \ge -1$:

​			$f(\alpha p_1 + (1-\alpha) p_2) = \frac{1}{2}$ and $f(p_1), f(p_2) \ge \frac{1}{2}$

​			$\therefore f(\alpha p_1 + (1-\alpha) p_2) \le \alpha f(x_1) + (1-\alpha) f(x_2)$

​	③ $x_1 < -1, x_2 > 1$			

​		1' $|\alpha p_1 + (1-\alpha) p_2| > 1$

​			same as ①

​		2‘ $|\alpha p_1 + (1-\alpha) p_2| \le 1$

​			same as ②-2’

​	④ $|x_1|, |x_2| \le 1$

​			same as ②-2'

​	⑤ $|x_1| \le 1, x_2 > 1$

​			same as ②

​	⑥ $x_1, x_2 > 1$

​			same as ①

#### Problem 4

​	Yes.

​	By the problem, we have constraints $\forall i = 1, ..., n, x_i \ge 0$  or $x \le 0$ which corresponding to $n$ vectors $\{a_i\}_{i=1}^n$

​	let $I_k = \{0,0,...,1,0,...\} \in \mathbb{R}^n$ who have 1 at k-th dim and other dims are 0

​	$a_i = I_k$ if $x_i \ge 0$ and $a_i = -I_k$ if $x_i \le 0$

​	It's obvious that $\{a_i\}_{i=1}^n$ is linearly independent and $\{a_i\}_{i=1}^n \sube P$

​	By *Handout 3, Theorem 2(3)*, we get that $P$ has at least one vertex

#### Problem 5

##### 	(a)

​		① assume both have solution:

​			$\exist x \in R^n, y \in R^m, s.t.$

​			$\mathbf{0} \le (y^TA)x = y^T(Ax) \le \mathbf{0} \Rightarrow y = \mathbf{0}$

​			Contradiction that $y \ne \mathbf{0}$

​		② exactly one system has a solution：

​			$Ax < \mathbf{0} \Leftrightarrow Ax \le e$

​			which equivalent to $\widetilde Az = e, z\ge \mathbf{0}$, where $\widetilde A = [A, I], z = (x, s)$

​			By Farkas' lemma, if the system $\widetilde Az = e, z \ge \mathbf{0}$ has no solution, then there exists a $y \in \mathbb{R}^m s.t. \widetilde A^Ty \le \mathbf{0}$ and $e^Ty > 0$.

​			From the definition of $\widetilde A$, we see that $A^Ty \ge \mathbf{0}, y \ge \mathbf{0}$

​			Moreover, since $e^Ty > 0$, we conclude that $y \neq 0$.

​			Thus ($I$) has solution ($II$) has no solution

##### (b)

​		① assume both have solution:

​			$\exist x \in R^n, y \in R^m, s.t.$

​			$\mathbf{0} = (y^TA)x = y^T(Ax) > \mathbf{0}$	

​			Contradiction

​		② exactly one system has a solution：

​			$\because Ax \ge 0, Ax \neq 0$ is equivalent to $Ax \ge 0, b^TAx = 1, b > \mathbf{0}$

​			let $\widetilde A = \left(\begin{array}{ccc}A & -A & -I \\ b^{T} A & -b^{T} A & 0\end{array}\right)$, $z = (x^+, x^-, s)$

​			($I$) can be written as $\widetilde Az = e = \left(\begin{array}{l}\mathbf{0} \\ \mathbf{1}\end{array}\right), z \ge 0$

​			By Farkas' lemma, if the system $\widetilde Az = e, z \ge \mathbf{0}$ has no solution, then there exists a $y \in \mathbb{R}^m s.t. \widetilde A^T(y', \alpha) \le \mathbf{0}$ and $e^T(y',\alpha) > 0$.

​			Let $y = y' + \alpha \cdot b, y' \ge0, \alpha > \mathbf{0}, b > \mathbf{0}$

​			so we can get $A^Ty = 0, y > \mathbf{0}$

​			Thus ($I$) has solution ($II$) has no solution

