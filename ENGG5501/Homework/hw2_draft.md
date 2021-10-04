# Homework 2（draft）

#### Problem 1

##### (a) 

$\because A,B \in S^n_+ $

$\therefore \exist U \in R^{k \times n}, k = rank(B), B = U^{T}U$ 

$\therefore tr(AB) = tr(AU^TU) = tr(UAU^T) \ge 0$ with assumption $tr(AB) = tr(BA)$



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



