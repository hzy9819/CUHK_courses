<<<<<<< HEAD
# Homework 2

=======
# SEEM 5580 Homework 2

##### 2.11 

<font face = "Times New Roman">**Problem**: Cars pass a certain street location according to a Poission process with rate $\lambda$. A person wanting to cross the street at that location waits until she can see that no cars will come by in the next $T$ time units. Find the expected time that the person waits before starting to cross (Note, for instance, that if no cars will be passing in the first $T$ time units then the waiting time is 0)</font>

**Solve**:  

​	let $W = E(waiting$ $time)$

​	From **proposition 2.2.1**, we get that event $X_i$ is independent identically distributed exponential random variables having mean $\frac{1}{\lambda}$

​	Thus, we can get the equation:
$$
\begin{align}
W &= \int_0^{T}(W + x)Pr\{X_i = x\}dx \\
&= \int_0^T(W + x)\lambda e^{-\lambda x}dx \\
&= W + \frac{1}{\lambda}-e^{-\lambda T}(T + W + \frac{1}{\lambda}) \\

W &= \frac{e^{\lambda T - 1}}{\lambda} - T
\end{align}
$$
So we get the expected waiting time $W = \frac{e^{\lambda T - 1}}{\lambda} - T$







##### 2.30

<font face = "Times New Roman">**Problem:** Let $T_1, T_2, ...$ denote the interarrival times of events of a nonhomogeneous Poisson process having intensity function $\lambda(t)$</font>

​	<font face = "Times New Roman">**(a)** Are the $T_i$ independent?</font>

​	<font face = "Times New Roman">**(b)** Are the $T_i$ identically distributed?</font>

​	<font face = "Times New Roman">**(c)** Find the distribution of $T_1$</font>

​	<font face = "Times New Roman">**(d)** Find the distribution of $T_2$</font>

**Solve**:

​	**(a)**

​		No, we can calculate $T_2$'s conditional distribution:
$$
\begin{align}
Pr\{T_2 > t | X_1 = s\} &= \lim_{s' \to s} Pr\{N(s+t) - N(s) = 0, N(s') = 0, N(s) - N(s') = 1 | N(s) = 1\} \\
&=Pr\{N(s+t) - N(s) = 0\} \\
&=e^{m(s) - m(t+s)}
\end{align}
$$


​		we can find this distribution is depends on $s$, thus $T_1, T_2$ is not independent and $T_i$ not independent.

​		**(b)**

​			No, with the result of (a), we find that $T_2$ depends on $T_1$

​		**(c)**

​			$Pr\{T_1 > t\} = Pr\{N(t) = 0\} = e^{m(0) - m(t)} = e^{-m(t)}$

​			$F_{X_1}(t) = Pr\{T_1 \le t\} = 1 - e^{-m(t)}$

​			thus, $f_{X_1}(t) = \lim_{t' \to t} \frac{Pr\{T_1 > t'\} - Pr\{T_1 > t\}}{t' - t} = \lambda(t)e^{-m(t)}$

​		**(d)**

​			combine the result in (a) and (c), we get
$$
\begin{align}
Pr\{T_2 > t\} &= \int_0^\infty Pr(T_2 > t | T_1 = s)f_{X_1}(s)ds \\
&= \int_0^\infty e^{m(s) - m(t+s)} \lambda(s)e^{-m(s)}ds \\
&= \int_0^\infty \lambda(s) e^{- m(t+s)}ds \\

F_{X_2}(t) &= Pr\{T_2 \le t\} \\
&= 1 - \int_0^\infty \lambda(s) e^{- m(t+s)}ds
\end{align}
$$
