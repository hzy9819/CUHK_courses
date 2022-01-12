# Homework 5

#### Problem 1

##### (a)

​	$f(x) = - x^TAx = -\sum_{i,j} x_iA_{ij}x_j$

​	the first-order optimality conditions:

​		$\nabla f(x) + w_1\nabla g_1(x) + w_2 \nabla g_2(x) = \textbf{0} \Rightarrow -2Ax - 2w_1x + w_2v_1 = \textbf{0}, w_i \ge 0$

​	By the **Handout 7-2 Theorem 3**, we convert Problem (1) to $min  f(x) = -x^TAx$ and it's easy to verify that $f(x)$ is continuously differentiable in $R^n$. Consider $\nabla g_1(x) = -2x, \nabla g_2(x) = v_1$ is independent because not $\exist k, s.t. -2x \equiv kv_1$。

##### (b)

​	 Consider the result in (a), let it $\cdot v_1^T$ at left and right, the we get:

​		$-2Axv_1^T - 2w_1xv_1^T + w_2v_1v_1^T = \textbf{0} = w_2 ||v_1||^2_2 $

​	which indicate that $w_2 = 0$, thus we have $Ax = w_1x$, which means the optimal result must be eigenvector, so we have:

​	$f(x) = -x^TAx = \lambda ||x||^2_2 = \lambda$

​	which is equal to some eigenvalue.

​	However, due to $v_1^Tx = 0$, thus $x \neq v_1$, so the optimal value can only be the second largest eigenvalue of A. Thus, $\lambda_2$ is the second largest eigenvalue of A and $v_2$ is an eigenvector associated with $\lambda_2$

#### Problem 2

$1^o: \Rightarrow$

​	Because $x^*$ is an optimal solution and $f(x)$ is continuous differentiable convex function. Thus,  $\forall x \in C, f(x) \ge f(x^*), \text{and } \nabla f(x^*) (x - x^*) \ge 0$

​	By **Handouts 2 Theorem3** , we have $x^* = \Pi_C(x^* - \nabla f(x^*)) $

$\Leftrightarrow x^* \in C \text{ and } (x - x^*)(x^* - \nabla f(x^*) - x^*) = -(x - x^*)\nabla f(x^*) \le 0, \forall x \in C$

​	Thus, $x^* = \Pi_C(x^* - \nabla f(x^*)) $

$2^o: \Leftarrow$

​	Because $x^* = \Pi_C(x^* - \nabla f(x^*)) $, we have $\nabla f(x^*)(x - x^*) \ge 0$, and  $f(x)$ is continuous differentiable convex function. Thus, $f(x) \ge f(x^*) + \nabla f(x^*)(x - x^*) \ge f(x^*), \forall x \in C$。

​	Thus, $x^*$ is an optimal solution.

#### Problem 3

​	We can convert this problem to:
$$
\begin{array}{cl} \min & z \\
	\text{subject to}	& g_1(x) - z \le 0 \\
					& g_2(x) - z \le 0 \\
					& ... \\
					& g_m(x) - z \le 0
\end{array}
$$
$1^o: \Rightarrow$

​	Because $x^*$ is an optimal solution, by **KKT condition** and Slater condition, we have:

​	$\sum_{j=1}^m u^*_j \nabla g_j(x^*) = \textbf{0}, u^* \ge \textbf{0}$

​	and

​	$u^*_j (g_j(x^*) - z^*) = 0, \text{for } j = 1,...m$

​	Thus, for $g_j(x^*) < max\{g_1(x^*),...,g_m(x^*)\}, u^*_j = 0$

​	Besides, $g_j(x^*) = max\{g_1(x^*),...,g_m(x^*)\}$ must exists, so that $u^* \ne \textbf{0}$ exists and can scale it to satisfy $\sum_{j=1}^m u^*_j = 1$

$2^o:\Leftarrow$

​	For given $x^*$, there exist a vector $u^* \in R^m, s.t.$

​	$\sum_{j=1}^m u^*_j \nabla g_j(x^*) = \textbf{0}, u^* \ge \textbf{0}, \sum_{j=1}^m u^*_j = 1$

​	$u^*_j = 0$, if $g_j(x^*) < max\{g_1(x^*),...,g_m(x^*)\}$

​	$z^* =  max\{g_1(x^*),...,g_m(x^*)\}$

​	let $I = \{j | g_j(x^*) = max\{g_1(x^*),...,g_m(x^*)\}\}$,

 1.    $\forall i \in I, \nabla g_i(x^*) = \textbf{0}$:

       $\forall x \in R^n, z = max\{g_i(x)\}_{i=1...m} \ge max\{g_i(x)\}_I$

       $g_i$ is convex function, thus $\forall i \in I, g_i(x) \ge g_i(x^*)$ 

       thus,  $z^* \le z, \forall x$

 2.    $\exist i, \nabla g_i(x^*) \ne \textbf{0}$:

       because $g_i$ is convex function, thus

       $\forall x \in R^n, \exist i \in I, \nabla g_i(x^*)(x - x^*) \ge 0 \Rightarrow g_i(x) \ge g_i(x^*)$

       $z = max\{g_i(x)\}_{i=1...m} \ge max\{g_i(x)\}_I \ge z^*$ 

       

       In summary, $x^*$ is an optimal solution if and only if the condition above it true.

#### Problem 4

##### 	(a)

​		$x^TAx = A \cdot xx^T, x^2_i = 1 \Leftrightarrow x^TE_ix = 1 = E_i \cdot xx^T$, where $E_i$  is matrix $e_{ii} = 1$ and other is 0.

​	let $X = xx^T$, the semidefinite relaxation of Problem (3) is 
$$
\begin{array}{cl}
inf & A \cdot X \\
\text{subject to} & E_i \cdot X = 1 & \text{for } i = 1,...,n & (P)\\
& X \ge \textbf{0}
\end{array}
$$


##### 	(b)

​		dual of (P):
$$
\begin{array}{cl}
sup & e^Ty \\ 
\text{subject to} & \left[ \begin{array}{cc} y_1 & 0 & 0, ...,0\\ 0 & y_2 & 0,...,0 \\ & ... & \\ 0 & ... & y_n \end{array} \right] + S = A & (D) \\
& y \in R^n, S \in S^n_+
\end{array}
$$
​	It is easy to solve (D) that $e^Ty = tr(A)$ with $y_i = A_{ii}$, if (D) is solvable, which means $A_{ij} \ge 0, i \ne j$

​	At this condition, (P) has solution $A \cdot X = tr(A) = e^Ty$ with $X = E$。

​	Besides, if exist $A_{ij} < 0, i \ne j$, then $v^*_p = -\infty$ and (D) cannot be solved.

​	So, the duality gap is zero.

##### (c)

​	$\theta(w) = inf_{x \in R^n} \{x^TAx + \sum_{i=1}^nw_i(1-x^2)\} = e^Tw + inf_{x \in R^n} x^T(A-Diag(w))x$

​	consider, if exist $A_{ij} < 0, i\ne j$, then $inf_{x \in R^n} x^T(A-Diag(w))x = (A - Diag(w)) \cdot (xx^T)$ must be $-\infty$ and $\theta(w) = -\infty$

​	So the maximum target holds $A - Diag(w) \in S^n_+$ when $\theta(w) > -\infty$

​	Besides, when $A - Diag(w) \in S^n_+, inf_{x \in R^n} x^T(A-Diag(w))x = 0$, so $\theta(w) = e^Tw$

​	So we can equivalent Problem(4) to:
$$
\begin{array}{cl}
sup & e^Tw \\ 
\text{subject to} & Diag(w) + S = A  \\
& w \in R^n, S \in S^n_+
\end{array}
$$
which is same as (D) in (b)



#### Problem 5

##### (a)

​	Let $f(x) = x_1^2 + 4x_2^2 + 16x_3^2$

​	It is easy to verify that $f(x)$ is a continuous function on $R^3$

​	let $x_1 = x_2 = x_3 = 1, f(x) = 21$, so $inf f(x) \le 21, x_1x_2x_3=1$, so we can let $B = \{x|x_1^2, x_2^2, x^2_3 \le 21\}$ as an add condition which will not effect the origin problem.

​	So that $\{x|x_1^2+x_2^2+x_3^2=1\} \cup B$ is a compact and f is continuous, $inf f$ must exists

##### (b)

​	By **KKT condition**：

​	$\nabla f(x) + w\nabla g(x) = (2x_1, 8x_2, 32x_3) + w(x_2x_3, x_1x_3, x_1x_2) = \textbf{0}$

​	there is only one constrain $g(x)$ so it's must be independent, so the KKT condition is necessary

##### (c)

$$
\begin{array}{cl}
2x_1 + wx_2x_3 = 0 \\
8x_2 + wx_1x_3 = 0 \\
32x_3 + wx_1x_2 = 0 \\
x_1x_2x_3 = 1
\end{array}
$$

we can get $x = (2, 1, 1/2)$ with $w = -8$ as the optimal solution set

#### Problem 6

The KKT condition of Problem (6):

​	$\nabla tr(AX) + v \nabla tr((X - X_0)^2) = \textbf{0}, v \ge 0 \quad (1)$

with the complementary slackness:

​	$v( tr((X - X_0)^2) - r^2) = 0 \quad(2)$

we can solve equation (1) $\Leftrightarrow X = X_0 + \frac{A}{2v}$ so the $X_0 + \frac{A}{2v} \in S_+$ or the optimal may not exist

combine (1) and (2) :

​	$tr((X_0 - \frac{A}{2v} - X_0)^2) = \frac{tr(A^2)}{4v^2} \le r^2$

​	$\Rightarrow v \ge \frac{\sqrt{tr(A^2)}}{2r}$

​	$tr(AX) = tr(AX_0) + \frac{tr(A^2)}{2v}$

we can find that there is a optimal solution when $v =  \frac{\sqrt{tr(A^2)}}{2r}$ with $X^* = X_0 - \frac{rA}{\sqrt{tr(A^2)}}$

