# Homework 2（draft）

#### Problem 1

##### (a) 

$\because A,B \in S^n_+ $

$\therefore \exist U \in R^{k \times n}, k = rank(B), B = U^{T}U$ 

$\therefore tr(AB) = tr(AU^TU) = tr(UAU^T) \ge 0$ with assumption $tr(AB) = tr(BA)$

let us proof $tr(AB) = tr(BA), \forall A, B \in S^n$：

​	let $A = (a_{ij})_{n \times n}, B = (b_{ij})_{n \times n}$

​	$tr(AB) = \sum_{i = 1}^{n} \sum_{j = 1}^n a_{ij} b_{ji}$

​	$tr(BA) = \sum_{i = 1}^{n} \sum_{j = 1}^n b_{ij} a_{ji}$

​	we can rearrange the equation above and get $tr(AB) = tr(BA)$

##### (b)

First we proof $\mathcal{S}_{+}^{n}\subseteq\bigcap_{A \in \mathcal{S}_{+}^{n}}\left\{X \in \mathcal{S}^{n}: A \bullet X \geq 0\right\}$

​	$\because$  the result in (a), we have $\mathcal{S}_{+}^{n} \subseteq\left\{X \in \mathcal{S}^{n}: A \bullet X \geq 0\right\}$ 

​	$\therefore \bigcap_{A \in \mathcal{S}_{+}^{n}}\left\{X \in \mathcal{S}^{n}: A \bullet X \geq 0\right\} \supseteq \bigcap_{A \in \mathcal{S}_{+}^{n}} S_+^n = S_+^n$

then we proof  $\mathcal{S}_{+}^{n}\supseteq\bigcap_{A \in \mathcal{S}_{+}^{n}}\left\{X \in \mathcal{S}^{n}: A \bullet X \geq 0\right\}$

​	we only have to proof : $\forall X \notin S_+^n, \exist A \in S_+^n, s.t. A \bullet X < 0$

​	$\because X \notin S_+^n$

​	$\therefore \exist \mu \in R^n, s.t. \mu^TX\mu < 0$

​	let $A = \mu\mu^T$ , we can get $tr(AX) = tr(\mu\mu^TX) = tr(\mu^TX\mu) < 0$

note that $A = \mu\mu^T$ because $\forall z \in R^n, z^TAz = z^T\mu\mu^Tz = (\sum z_iu_i)^2 >= 0$

​	$\therefore \forall X \notin S_+^n, X \notin \bigcap_{A \in \mathcal{S}_{+}^{n}}\left\{X \in \mathcal{S}^{n}: A \bullet X \geq 0\right\}$

​	$\therefore \mathcal{S}_{+}^{n}\supseteq\bigcap_{A \in \mathcal{S}_{+}^{n}}\left\{X \in \mathcal{S}^{n}: A \bullet X \geq 0\right\}$

In summary, $\mathcal{S}_{+}^{n} = \bigcap_{A \in \mathcal{S}_{+}^{n}}\left\{X \in \mathcal{S}^{n}: A \bullet X \geq 0\right\}$



#### Problem 2

##### (a) 

​	First let us proof $f$  possesses Property C $\Leftrightarrow$ $L_t = \{x \in \mathbb{R}^n:f(x) \le t\}$ is compact for any $t \in \mathbb{R}$

​		**① proof of** $\Rightarrow$:

​			first let us show $L_t$ is bounded, which means $\forall x \in L_t, \exist T \in \mathbb{R}, s.t. ||x||_2 < T$

​			Proof by contradiction: 

​					assume $L_t$ is not bounded, so there exists a sequence $\{x^k\}_{k \ge 0} \subseteq L_t, ||x^k||_2 \to +\infty$

​					$\because f$ possesses Property C

​					$\therefore f(x^k) \to +\infty$

​					However, with the limitation of $f(x) \le t$,  we can find $\{x^k\}_{k \ge 0} \subsetneq L_t$ 

​					Contradicting the assumption, thus $L_t$ is bounded

​			then let us show $L_t$ is close, which means $\forall \{x^k\}_{k \ge 0} \subseteq L_t, \{x^k\} \to x, x \in L_t$

​			$\because f$ is a continuous function

​			$\therefore \{f(x^k)\} \to f(x)$ 

​			$\because \{x^k\}_{k \ge 0} \subseteq L_t$

​			$\therefore \forall x^i \in \{x^k\}, f(x^i) \le t$

​			$\therefore \{f(x^k)\} \to f(x) \le t$

​			$\therefore x \in L_t, L_t$ is close

​			In summary, $L_t$ is compact

​		**② proof of** $\Leftarrow$:

​			Proof by contradiction:

​					assume $f$  not possesses Property C, which means $\exist \{x^k\}_{k \ge 0} \subseteq \mathbb{R}, ||x^k||_2 \to +\infty, f(x^k) \le T, T \in \mathbb{R}$

​					let $t > T$, then $\{x^k\}_{k \ge 0} \subseteq L_t$. However $||x^k||_2 \to +\infty$, thus $L_t$ is not bounded.

​					Contradicting the assumption, thus $f$  possesses Property C

​		In summary,  $f$  possesses Property C $\Leftrightarrow$ $L_t = \{x \in \mathbb{R}^n:f(x) \le t\}$ is compact for any $t \in \mathbb{R}$

​	Then let us proof $f$ is continuous and possesses Property C, $\inf _{x \in \mathbb{R}^n} f(x)$ always has an optimal solution.

​				$\inf _{x \in \mathbb{R}^n} f(x)$ always has an optimal solution, which means we can find a $x_0 \in \mathbb{R}^n s.t. \forall x \in R^n, f(x) \ge f(x_0)$

​				$\because f$ is continuous and possesses Property C, thus we can find a infimum $c$, which is the max $c_i$ satisfy $f(x) \ge c_i$

​				then we only need to show that exist $x_0 \in \mathbb{R}^n, s.t. f(x_0) = c$

​				let $t = c + 1$ , $L_t$ is compact and $c$ is also infimum of $L_t$

​				with the definition of infimum and continuous, $\exist \{x^k\}_{k \ge 0} \subseteq L_t, \{f(x^k)\} \to c, \{x^k\} \to x_0$

​				$\because L_t$ is compact

​				$\therefore x_0 \in L_t \subseteq R^n$

​				Thus we can always find an optimal solution $x_0$

##### (b)

​		No.

​		assume $f(0) < +\infty$, let $A = 0^{m \times n}$, thus $\forall x \in \mathbb{R}^n, g(x) \equiv f(0) < \infty, g$ not possesses Property C.



#### Problem 3

##### (a)

​	$\forall x, y \in K^{\circ}, \alpha, \beta \in R^+$, let $z = \alpha x + \beta y$

​	$\forall u \in K, z^T u = (\alpha x + \beta y)^T x = \alpha x^T u + \beta y^T u \le 0$

​	$\therefore z \in K^{\circ}, K^{\circ}$ is a convex cone

**(b)**

​	



​				

​					

​			



