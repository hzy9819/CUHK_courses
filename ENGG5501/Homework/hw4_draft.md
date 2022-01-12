# Homework 4

#### Problem 1

##### (a)

standard form of (2):

$\begin{array}{ll}\operatorname{minimize} & (\textbf{0},e)^{T}\left(x_{1},..., x_{n}, y_{1},..., y_{m}\right) \\ \text { subject to } & {\left[\begin{array}{c|c}A & I  \end{array}\right]\left[\begin{array}{c}x \\ y\end{array}\right]=b} \\ & (x, y) \geq \mathbf{0} .\end{array}$

dual of (2):

$\operatorname{maximize} \quad b^{T}s$
$\text{subject to} & \left[\begin{array}{c}A \\ \hline I  \end{array}\right]s \leq\left[\begin{array}{l}\textbf{0} \\ e\end{array}\right] .$

##### (b)

By the limitation of $(x,y) \ge \textbf{0}$, there exist $n+m$ linearly independent vectors. So (2) has at least one vertex, then either the optimal values is $-\infty$, or there exists a vertex that is optimal via **Handout-3 Theorem 3 & 4**.

Besides, because $e, y \ge \textbf{0}$, so $e^Ty \ge \textbf{0}$ which means the optimal values is impossible $-\infty$, so (2) always has an optimal solution.

##### (c)

proof of $\Rightarrow$:

​	Because (1) has solution so there $\exists  \bar{x}$ satisfy (1). Then $(x, y) = (\bar{x}, \textbf{0})$ is a feasible solution in (2) with value is zero.

​	Besides, $e^Ty \ge 0$, so that is a optimal solution.

proof of $\Leftarrow$:

​	Because (2) has the optimal value is zero, denote one optimal solution as $(\bar{x}, \bar{y})$, we have $e^T\bar{y} = 0$ and $\bar{y} \ge \textbf{0}$ which can refer that $\bar{y} = \textbf{0}$.

​	So we can find $A\bar{x} + I\bar{y} = b \Rightarrow A\bar x = b - I\bar y = b$ and $\bar x \ge \textbf{0}$

​	Hence $\bar x$ is a solution of (1)

In summary, system (1) has a solution $\Leftrightarrow$ opt value of (2) is 0.

#### Problem 2

We can construct dual LP as follow:

$\begin{aligned} v_{p}^{*}=& \text { minimize } \quad -e^{T} x \\ & \text { subject to } \quad P^T x=x \\ & x \geq \mathbf{0} \end{aligned}$

and dual:

$\begin{aligned} v_{d}^{*}=& \text { maximize } \quad 0^{T} y \\ & \text { subject to } \quad (P-I) y \leq -e \end{aligned}$

because  $P$ is a stochastic matrix with $P_{ij} \ge 0$ and $Pe=e$, so we have $0 \le P_{ij} \le 1, \sum_{j=1}^nP_{ij} = 1$. 

We only need to show that $(P-I)y \le -e$ is infeasible, i.e. $\forall y , \exists y_i, s.t. \sum_{j=1}^nP_{ij}y_j > y_i - 1$

Assume $\exist y, s.t (P-I)y \le -e$,  let $min(y_i) = y_0$.

we have $\forall i, (1 - P_{ii})y_i \ge \sum_{j \ne i} P_{ij}y_j + 1$ and $P_{ii} \ne 1$（$P_{ii} = 1$, then $0 \ge 1$）

$\Rightarrow y_i \ge \frac{\sum_{j \ne i}P_{ij}+1}{1-P_{ii}} \ge \frac{(1-P_{ii})y_0 + 1}{1-P_{ii}} = y_0 + \frac{1}{1-P_{ii}} > y_0$

but the inequality is not true when $y_i = y_0$, so $(P-I)y \le -e$ is infeasible.

Hence, due to LP duality theory, primal problem is infeasible or unbounded. 

And $x = \textbf{0}$ is one solution of primal problem, so primal problem is unbounded, which means $P^Tx = x, x \ge 0, x \ne \textbf{0}$ is solvable.

#### Problem 3

##### (a)

​	Because $p, q > 1$, $||x||_p$ is continuous and convex on $R^n$

 *    non-empty and closed under addition:

      ​	$\textbf{0} \in C_p \ne \emptyset$, $\forall (t_u, u),(t_v, v) \in C_p, ||u + v||_p \le ||u||_p + ||v||_p \le t_u + t_v \Rightarrow (t_u + t_v, u+v) \in C_p$

 *    cone:

      ​	$\forall (t, u) \in C_p, \alpha > 0, ||\alpha u||_p = \alpha ||u||_p \le \alpha t \Rightarrow (\alpha t, \alpha u) \in C_p$

 *    pointed:

      ​	let $(t, u), (-t, -u) \in C_p$, we have $t = 0$ because $||x||_p \ge 0$, thus $u = 0$

 *    closed:

      ​	We only need to show that, for all **limit point** of $C_p$ in $C_p$. By definition, for any limit point $(t, u)$ and correspond sequence $\{(t_i, u_i) \in C_p\}, lim \ (t_i, u_i) = (t, u)$, consider function $f(t, x) = ||x||_p - t$ is continuous and $f(t, x) \le 0, (t, x) \in C_p$, thus $f(t, u) = lim \ f(t_i, u_i) \le 0$ which indicate that $(t, u) \in C_p$.

In summary, $C_p$ is a closed pointed cone.

##### (b)

​	$C_p^* = \{(t', x') \in R \times R^n: t*t'+ x \bullet x' \ge 0, \forall (t,x) \in C_p\}$ 

$1^o: C_p^* \supseteq C_q:$

​	$\forall (t_p, x_p) \in C_p, (t_q, x_q) \in C_q, ||x_p||_p \le t_p, ||x_q||_q \le t_q$

​	By Holder’s inequality: $||fg||_1 \le ||f||_p||g||_q$

​	Thus $t_p * t_q + x_p \bullet x_q \ge ||x_p||_p||x_q||_q - ||x_px_q||_1 \ge 0, (t_q, x_q) \in C_p^*$

​	which indicate that $C_p^* \supseteq C_q$

$2^o: C_p^* \subseteq C_q:$

​	$\forall (t', x') \in C_p^*, t*t'+ x \bullet x' \ge 0, \forall (t, x) \in C_p$

​	let $x = -x', t = ||x'||_p$, thus we have $x'\bullet x' = ||x' x'||_1 = ||x'||_p||x'||_q$

​	$\Rightarrow ||x'||_p * t' - x' \bull x' = ||x'||_p*t' - ||x'||_p||x'||_q \ge 0$

​	$\Rightarrow ||x'||_q \le t'$

​	$\Rightarrow (t', x') \in C_q$

​	thus $C_p^* \subseteq C_q$

In summary, $C_p^* = C_q$

##### (c)

​	$int(C_p) = \{(t, x) \in R \times R^n:t\ge0, ||x||_p < t\}$

proof:

​	$1^o: bound(C_p) = C_p \setminus int(C_p) \supseteq int(C_p) \setminus \{(t, x) \in R \times R^n:t\ge0, ||x||_p < t\} $

​		$\Rightarrow int(C_p) \subseteq \{(t, x) \in R \times R^n:t\ge0, ||x||_p < t\}$ :

​		$\forall (t, x) \in \{||x||_p=t\}, \exist r \in R^+, (t-r, x) \in B((t, x), r), (t-r, x) \notin C_p$

​		therefore, $C_p \setminus int(C_p) \supseteq \{(t, x) \in R \times R^n:t\ge0, ||x||_p = t\}$ 

​	$2^o: int(C_p) \supseteq \{(t, x) \in R \times R^n:t\ge0, ||x||_p < t\}$

​		By definition, $\forall (||x||_p+r, x) \in \{(t, x) \in R \times R^n:t\ge0, ||x||_p < t\}, r \in R^+, \exist B((||x||_p+r, x), r'), r' = r * sin \theta, $ where $cos \theta = \frac{v_1\bull v_2}{||v_1||||v_2||}, v_1 = (1, 0, ..., 0), v_2 = det (t, ||x||_p)$

​		It's easy to verify that $r' < dis(||x||_p + r, bound(C_p))$, so $int(C_p) \supseteq \{(t, x) \in R \times R^n:t\ge0, ||x||_p < t\}$

In summary, $int(C_p) = \{(t, x) \in R \times R^n:t\ge0, ||x||_p < t\}$

#### Problem 4

##### (a)

​	let $y \in R^{n_j+1}, y = A^{j}\left[\begin{array}{l} x \\ u \end{array}\right]-b^{j},$

​	$y \in Q^{n_j+1} \Leftrightarrow ||y_{2\sim n_j+1}||_2 \le y_1$

​	We need to construct $A_j, b_j, s.t.z = y_{2 \sim n_j+1}, ||z||_2 \le y_1 \Leftrightarrow x^TQx = x^TQ^{1/2}Q^{1/2}x\le t \Leftrightarrow ||Q^{1/2}x||^2_2 \le t \Leftrightarrow ||Q^{1/2}x||_2 \le \sqrt t$	

​	which indicate that $z = Q^{1/2}x, y_1 = \sqrt t$（for $t < 0$, let $y_1 = -1$）

​	Then we let $A^j = \left[ \begin{array}{ccc} 1 & \textbf{0} & -1\\ \textbf{0} & Q^{1/2} & \textbf{0}\end{array}\right], \mu = (t - \sqrt t), b = \textbf{0} \Rightarrow y = A^{j}\left[\begin{array}{l} x \\ \mu \end{array}\right]-b^{j} = \left[\begin{array}{c} \sqrt t \\ Q^{1/2}x\end{array}\right]$

​	Thus $X$ is SOC-representable.

##### (b)

​	let $\pi \ge 0, \sqrt{x_1x_2} \ge \pi \ge t$, it easy to show that $\pi$ exist and $t \le \sqrt{x_1x_2} \Leftrightarrow \pi^2 \le x_1x_2 = \frac{1}{4}((x_1 + x_2)^2 - (x_1 - x_2)^2)$

​	$\Leftrightarrow ||(\pi, \frac{1}{2}(x_1-x_2)||_2 \le \frac{1}{2}(x_1+x_2)$ which indicate that then final vector $v = (\frac{1}{2}(x_1 + x_2), \frac{1}{2}(x_1 - x_2), \pi)^T \in Q^3$

​	The we let $A^j = \left[ \begin{array}{ccc} 0 & \frac{1}{2}& \frac{1}{2} & 0 \\ 0 & \frac{1}{2} &-\frac{1}{2} & 0 \\ 0 & 0 & 0 & 1\end{array} \right], \mu = (\pi), b^j = \textbf{0} \Rightarrow v = A^{j}\left[\begin{array}{l} x \\ \mu \end{array}\right]-b^{j} = \left[\begin{array}{c} \frac{1}{2}(x_1 + x_2) \\ \frac{1}{2}(x_1 - x_2) \\ \pi\end{array}\right]$

​	Thus $X$ is SOC-representable.

​	

#### Problem 5

##### (a)

​	$\forall p = u + v \in K^*_1 + K^*_2, u \in K^*_1, v \in K^*_2, \forall x \in K_1 \cap K_2, p \bullet x = (u + v) \bull x = u \bull x + v \bull x \ge 0$

​	Hence, $p \in (K_1 + K_2)^*, K_1^*+K_2^* \subseteq (K_1\cap+ K_2)^*$

##### (b)

​	$1^o: K_1^* + K_2^*$ is a cone:

​		$\forall p = u + v \in K^*_1 + K^*_2, u \in K^*_1, v \in K^*_2, \forall \alpha > 0, \alpha p = \alpha u + \alpha v, \alpha u \in K_1^*, \alpha v \in K_2^*$

​		Hence, $\alpha p \in K_1^* + K_2^*, K^*_1 + K^*_2$ is a cone

​	$2^o: K_1^* + K_2^*$ is convex:

​		$\forall p_1, p_2 \in K_1^* + K_2^*, p_1 = u_1 + v_1, p_2 = u_2 + v_2, u_1,u_2 \in K_1^*, v_1, v_2 \in K^*_2, \forall \alpha \in (0, 1),$

​		$ \alpha p_1 + (1-\alpha)p_2 = (\alpha u_1 + (1-\alpha)u_2) + (\alpha v_1 + (1-\alpha)v_2) = u + v$, where $u \in K^*_1, v \in K^*_2$ because they are convex

​		Hence, $\alpha p_1 + (1-\alpha)p_2 \in K^*_1 + K^*_2$ which indicates $K^*_1 + K^*_2$ is convex

​	In summary, $K^*_1 + K^*_2$ is a convex cone

##### (c)

​	By the definition of close, we need to show that $\forall p = u + v \in K^*_1 + K^*_2, \exist \{p_i = u_i + v_i\} \in K^*_1 + K^*_2, \{p_i\} \rightarrow p$

​	Because, $\exist x \in int(K_1) \cap int(K_2)$, thus for any given $t, S_t = \{w \in K_1^*: ||w||_2 = t\}$ is compact and $inf_{S_t} \left<x, w \right> > 0$ and same as $K_2$

​	which indicate that $\{\left<x, u_i\right>\}, \{\left<x, v_i\right>\}$ is also bounded and $\{u_i\}, \{v_i\}$ is bounded.

​	Hence, $\{u_i\}, \{v_i\}$ must exist some convergent subsequences let them converge on $u, v$ and belong to $K_1^*, K_2^*$ with the closeness, thus  $K^*_1 + K^*_2$ is closed.

##### (d)

​	Proof by contradiction:

​		Assume $(K_1 \cap K_2)^* \subsetneq K_1^* + K_2^*$ which means there exist $x \in (K_1 \cap K_2)^*, x \notin  K_1^* + K_2^*$. Thus exist a vector $b$, let $b^Tw \le 0 < b^Tx, \forall w \in K_1^* + K_2^*$

​		Because $0 \in K_1^*, K_2^*$, thus $b^Tw \le 0, \forall K_1^* \cup K_2^*$

​		However, $x \in (K_1 \cap K_2)^*$ which means $\forall w \in K_1 \cap K_2, x^Tw \ge 0$ thus $x \in K_1^* \cup K_2^*$ which means $b^Tx \le 0$, and it is a contradiction

​	Therefore, $(K_1 \cap K_2)^* \subseteq K_1^* + K_2^*$

​		

​		