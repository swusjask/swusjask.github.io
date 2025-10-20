---
layout: single
title: My IMC 2024 Solution
date: 2024-10-05
categories:
- Mathematics
- IMC
tags:
- IMC 2024
- math competition
- solutions
- team selection
math: true
---

In this blog, I will share my solutions during competition. While some of my solutions differ from the official ones, others follow the same ideas but are presented in different ways.

You can find the official solutions for Day 1 and Day 2 at the following links:
- [IMC 2024 Day 1 Solutions](https://www.imc-math.org.uk/imc2024/imc2024-day1-solutions.pdf){: target="_blank"}
- [IMC 2024 Day 2 Solutions](https://www.imc-math.org.uk/imc2024/imc2024-day2-solutions.pdf){: target="_blank"}

## IMC 2024

### Problem 1 [10 / 10]

Determine all pairs $(a,b) \in \mathbb{C} \times \mathbb{C}$ satisfying

$$ |a| = |b| = 1 \quad \text{and} \quad a + b + a\overline{b}\in \mathbb{R} $$

#### Solution

Notice that for $ \|z\| = 1 $, we have property that $\overline{z} = {1 \over z}$. Because $a + b + a\overline{b} \in \mathbb{R}$, we have

$$
\begin{align*}

a + b + a\overline{b} &= \overline{(a + b + a\overline{b})} \\

a + b + a\overline{b} &= \overline{a} + \overline{b} + \overline{a}b \\

a + b + {a \over b} &= {1 \over a} + {1 \over b} + {b \over a} \\

{ab + b^2 + a \over b} &= {b + a + b^2 \over ab} \\

a^2b + ab^2 + a^2 &= b + a + b^2 \quad \quad b \neq 0 \\

a^2 - b^2 - a - b + a^2b + ab^2 &= 0 \\
(a+b)(a-b) - (a+b) + ab(a+b) &= 0 \\
(a+b)(a-b-1+ab) &= 0 \\
(a+b)(a-1)(b+1) &= 0 \\

\end{align*}
$$

Thus, from the factorization, we conclude: $ a + b = 0$, $a = 1$, or $b = -1$. We will now check these solutions:

- If $a + b = 0$, then $a = -b$. Substituting this into $a + b + a\overline{b}$ gives $a - a - {a \over a} = -1 \in \mathbb{R}$. So $$\{ (z, -z) \mid \| z \| = 1, z \in \mathbb{C} \}$$ is a solution.
- If $a = 1$. Substituting this into $a + b + a\overline{b}$ gives $1 + b + \overline{b}$. But $\overline{(1 + b + \overline{b})} = 1 + \overline{b} + b = 1 + b + \overline{b}$. So $1 + b + \overline{b} \in \mathbb{R}$. So $$\{ (1, z) \mid \| z \| = 1, z \in \mathbb{C} \}$$ is a solution.
- If $b = -1$. Substituting this into $a + b + a\overline{b}$ gives $a - 1 - a = -1 \in \mathbb{R}$. So $$\{ (z, -1) \mid \| z \| = 1, z \in \mathbb{C} \}$$ is a solution.

Thus, all pairs $(a,b)$ satisfying the conditions are the set of

$$ \{ (z, -z) \mid \| z \| = 1, z \in \mathbb{C} \} \cup \{ (1, z) \mid \| z \| = 1, z \in \mathbb{C} \} \cup \{ (z, -1) \mid \| z \| = 1, z \in \mathbb{C} \} $$


### Problem 3 [7 / 10]

For which positive integers $n$ does there exist an $n \times n$ matrix $A$ whose entries are all in $$\{ -1, 1 \}$$ such that $A^2$ is the matrix of all ones?

#### Solution

We claim that for $n$ not complete square is not possible. Let $J_n$ be the $n \times n$ matrix of all ones. Then, we have

$$ A^4 = (A^2)^2 = J_n^2 = nJ_n = nA^2 \Longrightarrow A^4 - nA^2 = 0 $$

The minimal polynomial of $A^2$ divides $x^2 - nx = x(x - n)$. Therefore, the eigenvalues of $A^2$ are either $0$ or $n$. Consequently, the eigenvalues of $A$ must be either $0$, $\sqrt{n}$, or $-\sqrt{n}$.

Denote $E_\lambda (M)$ as the eigenspace of $M$ corresponding to the eigenvalue $\lambda$. It also clear that because all row vectors of $A^2$ are the same, hence $\operatorname{rank} (A^2) = 1$. So by the rank-nullity theorem, we have

$$ \dim E_0(A^2) = \dim \operatorname{null}(A^2) = n-1 $$

As a result, $\dim E_n(A^2)$ must be $1$. 

Let $b = (1, 1, \ldots, 1)$ be the vector of all ones. For $v \in \operatorname{span}(b)$, we have $v = \alpha b$ for some scalar $\alpha$. Then, $A^2v = \alpha J_n b = \alpha n b = nv$. So $v \in E_n(A^2)$. Hence $\operatorname{span}(b) \subseteq E_n(A^2)$. As a result $E_n(A^2) = \operatorname{span}(b)$ given the fact that $\dim E_n(A^2) = 1$ .

Suppose all the eigenvalues of $A$ are $0$. This would imply that $A$ is nilpotent (i.e., $A^k = 0$ for some integer $k$), which in turn means $A^2$ is also nilpotent. But since $A^2 = J_n$ is not nilpotent, contradiction. Thus, there must be at least one eigenvalue of $A$ that is not $0$. Without loss of generality (WLOG), let us assume this eigenvalue is $\sqrt{n}$.

Now, we claim that $E_\sqrt{n}(A) = E_n(A^2)$. To see this, let $v \in E_\sqrt{n}(A)$. Then, $Av = \sqrt{n}v$. So

$$ A^2v = A(\sqrt{n}v) = \sqrt{n}Av = n v $$

Thus, $v \in E_n(A^2)$ and $E_\sqrt{n}(A) \subseteq E_n(A^2)$. Consequently, $\dim E_\sqrt{n}(A) \leq 1$. But dimension of eigenspace is at least $1$, so $\dim E_\sqrt{n}(A) = 1$ and we have $E_\sqrt{n}(A) = E_n(A^2) = \operatorname{span}(b)$.

We are ready to prove the main claim that it is indeed not possible for $n$ not complete square. Because $b$ in $E_\sqrt{n}(A)$, we have 

$$Ab = \sqrt{n}b$$

Notice that all element in $Ab$ is rational number. But all element in $\sqrt{n}b$ is irrational number. This is a contradiction. Therefore, $n$ must be a complete square.

#### Additional Notes

Indeed my solution is not complete. The rest of the solution is to show that for $n$ complete square, there exists a matrix $A$ such that $A^2 = J_n$. That is we must have the construction of $A$. But, at that time, I was not able to find the construction. You can read the construction in the official solution. Also, if you notice that actually my solution compared to official one is more complicated xD, but I think it is still worth to share.

### Problem 6 [10 / 10]

Prove that for any function $f: \mathbb{Q} \to \mathbb{Z}$, there exist $a,b,c \in \mathbb{Q}$ such that $a < b < c$, $f(b) \geq f(a)$, and $f(b) \geq f(c)$.

#### Solution

Assume by contradiction that there exists a function $f: \mathbb{Q} \to \mathbb{Z}$ such that for all $a,b,c \in \mathbb{Q}$ with $a < b < c$, we have $f(b) < f(a)$ or $f(b) < f(c)$. We will show that this leads to a contradiction.

Let $I(x,y) = [x,y] \cap \mathbb{Q}$ for $x,y \in \mathbb{Q}$. We will show that there exist $x$ and $y$ such that $f$ in $I(x,y)$ is strictly monotone. Let us fix some $x,y \in \mathbb{Q}$. We will consider two case.

1. Case 1: There not exist $v < w, \quad \forall v,w \in I(x,y)$ such that $f(v) < f(w)$
   
   $\forall a,b,c \in I(x,y)$, with $a < b < c$, we have $f(b) < f(a)$. Since it cannot be $f(b) < f(c)$. So $I(x,y)$ is strictly monotone decreasing.
   
2. Case 2: There exist $v < w, \quad \forall v,w \in I(x,y)$ such that $f(v) < f(w)$
   
   $\forall a \in I(x,y)$ with $a > w$, we have $f(w) < f(a)$. Since $f(w) > f(v)$. By similar argument, $\forall b \in I(x,y)$ with $b > a$ we have $f(b) > f(a)$. As a result, $\forall a,b \in I(w,y)$ with $a < b$, we have $f(a) < f(b)$. So $I(w,y)$ is strictly monotone increasing.
  
In both cases, we have shown that there exist $x$ and $y$ such that $I(x,y)$ is strictly monotone. Now, we will show that this leads to a contradiction. Let $x$ and $y$ be such that $f$ in $I(x,y)$ is strictly monotone. Also let $$m = \min \{f(x), f(y) \}$$ and $$M = \max \{f(x), f(y) \}$$    So, for  $z \in I(x,y)$, we have $m < f(z) < M$. Notice that element in $I(x,y)$ is countably infinite, but integer between $m$ and $M$ is finite. Then there exist two element in $I(x,y)$ that map to the same integer. This is a contradiction. Therefore, our assumption is wrong. So, there must exist $a,b,c \in \mathbb{Q}$ such that $a < b < c$, $f(b) \geq f(a)$, and $f(b) \geq f(c)$ for any $f: \mathbb{Q} \to \mathbb{Z}$.

### Problem 7 [9 / 10]

Let $n$ be a positive integer. Suppose that $A$ and $B$ are invertible $n \times n$ matrices with complex entries such that $A + B = I$ and

$$(A^2 + B^2)(A^4 + B^4) = A^5 + B^5$$

Find all possible values of $\det (AB)$ for the given $n$

#### Solution

First, we will find $\sigma(A)$, spectrum of matrix $A$, which is the set of all eigenvalues A. We have $B = I - A$. Substituting this into the equation, we have

$$
\begin{align*}

(A^2 + (I - A)^2)(A^4 + (I - A)^4) &= A^5 + (I - A)^5 \\

(A^2 + I^2 - 2A + A^2)(A^4 + I^4 - 4A + 6A^2 - 4A^3 + A^4) &= A^5 + I^5 - 5A + 10A^2 - 10A^3 + 5A^4 - A^5 \\

(2A^2 - 2A + I)(2A^4 - 4A^3 + 6A^2 - 4A + I) &= 5A^4 - 10A^3 + 10A^2 -5A + I \\

4A^6 - 12A^5 + 22A^4 - 24A^3 + 16A^2 - 6A + I &= 5A^4 - 10A^3 + 10A^2 -5A + I \\

4A^6 - 12A^5 + 17A^4 - 14A^3 + 6A^2 - A &= 0 \\

A(A-I)(2A-I)^2\left(A - ({1 \over 2} + {i\sqrt{3} \over 2})I\right)\left(A - ({1 \over 2} - {i\sqrt{3} \over 2})I\right) &= 0

\end{align*}
$$

Hence, minimal polynomial of $A$ will divide $x(x-1)(2x-1)^2(x - ({1 \over 2} + {i\sqrt{3} \over 2}))(x - ({1 \over 2} - {i\sqrt{3} \over 2}))$. So, possible spectrum is $$\sigma(A) = \{0, 1, {1 \over 2},{1 \over 2} + {i\sqrt{3} \over 2}, {1 \over 2} - {i\sqrt{3} \over 2} \}$$.

Since $A$ is invertible, then $0$ is not an eigenvalue of $A$. Also since $B$ are invertible with $B = I - A$. It means $1$ also cannot be eigenvalue of $A$ since it lead to $0$ is eigenvalue of $B$. As a result, the correct spectrum of $A$ is $$\{ {1 \over 2}, {1 \over 2} + {i\sqrt{3} \over 2}, {1 \over 2} - {i\sqrt{3} \over 2} \}$$.

Now, we have $AB = A(I-A) = A - A^2$. And because

$${1 \over 2} - {1 \over 2}^2 = {1 \over 4}$$

$${1 \over 2} + {i\sqrt{3} \over 2} - \left({1 \over 2} + {i\sqrt{3} \over 2}\right)^2 = 1$$

$${1 \over 2} - {i\sqrt{3} \over 2} - \left({1 \over 2} - {i\sqrt{3} \over 2}\right)^2 = 1$$

So, $$\sigma(AB) = \{ {1 \over 4}, 1 \}$$. Because determinant is product of all eigenvalues. The possible values of $\det(AB)$ considering multiplicity of eigenvalue is $\displaystyle {1 \over 4}^k$ for $0 \leq k \leq n$.

We now show that these values are possible. Let

$$A = \operatorname{diag}\left( \underbrace{ {1 \over 2}, \ldots, {1 \over 2} }_{k}, \underbrace{ {1 \over 2} - {i\sqrt{3} \over 2}, \ldots, {1 \over 2} - {i\sqrt{3} \over 2} }_{n-k} \right) $$

$$B = \operatorname{diag}\left( \underbrace{ {1 \over 2}, \ldots, {1 \over 2} }_{k}, \underbrace{ {1 \over 2} + {i\sqrt{3} \over 2}, \ldots, {1 \over 2} + {i\sqrt{3} \over 2} }_{n-k} \right) $$

We also can check that $A$ and $B$ are invertible that satisfy $A + B = I$ and $(A^2 + B^2)(A^4 + B^4) = A^5 + B^5$. Also .


$$AB = \operatorname{diag}\left( \underbrace{ {1 \over 4}, \ldots, {1 \over 4} }_{k}, \underbrace{ 1, \ldots, 1 }_{n-k} \right)$$

and $\det(AB) = \displaystyle {1 \over 4}^k$.

#### Additional Notes

Compared to the official solution, my solution is little complicated but follow the same idea. Instead directly calculate spectrum of $AB$ which is more easier, I calculate spectrum of $A$ first. Also the reason I don't get full score is because I state that my construction is clearly valid without showing the calculation.

## Team Selection

Actually, the team selection test there is only one time (kinda weird though 🗿). But luckily I manage to do well in this test so I can pass. This time, before begin into to my solution. I will write all problem first.

1. Given a set $X$ that contain $n \geq 2$ element. Let $A_1, A_2, \ldots, A_{101}$ is subset of $X$ such that union for any $50$ subset $A_j$ always have more than $\displaystyle {50n \over 51}$ element. Prove that there exist $3$ subset $A_i, A_j, A_k$ such that every two set is mutually exclusive.
2. Let $f$ is polynomial with integer coefficient that is symmetric in $100$ variables and homogeneous of degree $d$. Prove that if $d$ is not multiple of $100$, then $101$ will divide $f(1,2,\ldots,100)$.
      -  Polynomial $f$ is symmetric if for any permutation $x_{i_1}, x_{i_2}, \ldots, x_{i_{100}}$ of $x_1, x_2, \ldots, x_{100}$, we have $f(x_1, x_2, \ldots, x_{100}) = f(x_{i_1}, x_{i_2}, \ldots, x_{i_{100}})$.
      -  Polynomial $f$ is homogeneous of degree $d$ if for any integer $c$ satisfy $f(cx_1, cx_2, \ldots, cx_{100}) = c^d f(x_1, x_2, \ldots, x_{100})$.
      
3. Let $P(x) = a_0 + a_1x + a_2x^2 + \cdots + a_nx^n$ be polynomial of degree $n \geq 1$ with real coefficients. If
   
   $${a_0 \over 1} + {a_1 \over 2} + {a_2 \over 3} + \cdots + {a_n \over n+1} = 0,$$

   then show that $P(x)$ has a real root in the interval $(0,1)$.
4. Let $\Omega \subset \mathbb{C}$ be a domain and $f: \Omega \to \mathbb{C}$ be a holomorphic function such that $f'(z) \neq 0$ for all $z \in \Omega$. Prove that

   $$\{ \operatorname{Re}(f(z)) + \operatorname{Im}(f(z)) \mid z \in \Omega \} $$

   is an open subset of $\mathbb{R}$
5. Pair of square real matrix $X$ and $Y$ is 'good' if both matrix is invertible and satisfy $YX = XYXY$.
   1. Prove that if $A$ and $B$ is good with size $n \times n$, $\|\operatorname{trace}(AB)\| \leq n$.
   2.  For any pair of good matrix $C$ and $D$ with size $2 \times 2$, determine all possible value of $\operatorname{trace}(CD)$. Explain your answer.

Here is my solution that I write during the test (of course I not answer all of problems).

### Solution 2
First, we will see all element inside $f$ in $\mathbb{Z}_{101}$. Also because $101$ is prime, the multiplicative group $$\mathbb{Z}_{101}^{*}$$ is cyclic. So, there exist primitive root $$g \in \mathbb{Z}_{101}^*$$ such that $$\mathbb{Z}_{101}^* = \left\langle g \right\rangle$$. It also well-known that mapping $x \mapsto gx $ is bijection. Indeed, for any group $G$ and $g \in G$, the mapping $x \mapsto gx$ is bijection. The proof is simple, for one-to-one is if $gx = gy$. Then $x = y$. For onto is for any $x \in G$, then $g^{-1}x \in G$ and $g(g^{-1}x) = x$. So, the mapping is onto. Hence the mapping is bijection.

Notice that

$$
\begin{align*}

f(g * 1, g*2, \ldots, g * 100) &= g^df(1, 2, \ldots, 100) \qquad \text{(homogeneous)} \\

f(\sigma(1), \sigma(2), \ldots, \sigma(100)) &= g^df(1, 2, \ldots, 100) \qquad (\text{for some }\sigma \in S_{100} \text{ because } x \mapsto gx \text{ is bijective}) \\

f(1, 2, \ldots, 100) &= g^df(1, 2, \ldots, 100) \qquad (\text{symmetric}) \\

f(1, 2, \ldots, 100)(g^d - 1) &= 0 \\

\Longrightarrow 101 &\mid f(1, 2, \ldots, 100)(g^d - 1)

\end{align*}
$$

Also, because $g$ is primitive root we have 

$$101 \mid g^d - 1 \Longleftrightarrow g^d \equiv 1 \pmod{101} \Longleftrightarrow 100 \mid d$$

But, given that $d$ is not multiple of $100$ we have $101 \nmid g^d - 1$. As a result, $101 \mid f(1, 2, \ldots, 100)$.

### Solution 3

Because polynomial function is integrable. Let $Q(x) = \displaystyle \int_0^x P(t) \, dt = a_0x + {a_1 \over 2}x^2 + \cdots + {a_n \over n+1}$. Then, we have

$$
\begin{align*}

Q(0) &= 0 \\
Q(1) &= {a_0 \over 1} + {a_1 \over 2} + \cdots + {a_n \over n+1} = 0

\end{align*}
$$

By mean-value theorem, $\exists c \in (0,1)$ such that 

$$
\begin{align*}

Q'(c) &= {Q(1) - Q(0) \over 1 - 0} = 0 \\
P(c) &= {0 - 0 \over 1} \\
P(c) &= 0
   
\end{align*}
$$

### Solution 5

#### Incomplete [during test]
1. This solution only hold if we assume all eigenvalues of $AB$ is real (which is not hold in general). Because $A$ and $B$ is good, we have

$$
\begin{align*}

BA &= ABAB \\
\operatorname{trace}(BA) &= \operatorname{trace}(ABAB) \\
\operatorname{trace}(AB) &= \operatorname{trace}((AB)^2) \tag{1} \label{eq:trace} \\

\end{align*}
$$

Let $\lambda_i$ is eigenvalue of $AB$ for $i = 1,2,\cdots,n$. We also have $\lambda_i^2$ is eigenvalue of $(AB)^2$. So, from \eqref{eq:trace}, we have

$$ \sum_{i=1}^n \lambda_i =  \sum_{i=1}^n \lambda_i^2$$

Because $\lambda_i \neq 0$, QM-AM inequality holds and we have 

$$
\begin{align*}

{|\operatorname{trace}(AB)| \over n} = {\left|\displaystyle \sum_{i=1}^n \lambda_i \right| \over n} \overset{ \text{(triangle Inequality)}}{\leq} {\displaystyle \sum_{i=1}^n |\lambda_i| \over n} &\overset{ \text{(QM-AM Inequality)}}{\leq} \sqrt{\displaystyle \sum_{i=1}^n \lambda_i^2 \over n} \\

\Longrightarrow {\left|\displaystyle \sum_{i=1}^n \lambda_i \right|^2 \over n^2} &\leq {\displaystyle \sum_{i=1}^n \lambda_i^2 \over n} \\

\left|\displaystyle \sum_{i=1}^n \lambda_i \right|^2 &\leq n\left( \displaystyle \sum_{i=1}^n \lambda_i^2 \right) \\

\left|\displaystyle \sum_{i=1}^n \lambda_i \right|^2 &\leq n\left( \displaystyle \sum_{i=1}^n \lambda_i \right) \\

\left|\displaystyle \sum_{i=1}^n \lambda_i \right| &\leq n \\

\Longrightarrow |\operatorname{trace}(AB)| &\leq n

\end{align*}
$$

#### Complete [after test]

1. Notice that

   $$BA = ABAB = A(BABA)A^{-1} = A(BA)^2A^{-1}$$

   Which means that $BA$ and $(BA)^2$ are similar. Let $\lambda \in \sigma(BA)$ be eigenvalue of $BA$. Then, $\lambda^2$ is eigenvalue of $(BA)^2$ that also means eigenvalue of $BA$. Hence $\lambda^2 \in \sigma(BA)$. Because $\sigma(BA)$ is finite, continuing this argument we will get $\lambda^{2^k} = \lambda$ for some non-negative $k$. Taking the modulus we get

   $$
   \begin{align*}
   
   |\lambda|^{2^k} &= |\lambda| \\

   |\lambda|^{2^k - 1} &= 1 \qquad \text{(because } |\lambda| \neq 0 \text{ by invertibility)} \\
   
   \Longrightarrow |\lambda| &= 1

   \end{align*}
   $$

   So, now we get (counting multiplicity)

   $$
   |\operatorname{trace}(AB)| = |\operatorname{trace}(BA)| = \left|\displaystyle \sum_{\lambda \in \sigma(BA)} \lambda \right| \overset{ \text{(triangle Inequality)}}{\leq} \displaystyle \sum_{\lambda \in \sigma(BA)} |\lambda| = n
   $$
2. Calculate $\operatorname{trace}(CD)$ is equivalent with calculate $\operatorname{trace}(DC)$. So we will only consider $\operatorname{trace}(DC)$. Let $\lambda_1$ and $\lambda_2$ be eigenvalues of $DC$. By argument before, we must have either of this two case

   - $\lambda_1^2 = \lambda_1$ and $\lambda_2^2 = \lambda_2$.

      Which means $\lambda_1 = \lambda_2 = 1$ (Since it cannot be $0$). As a result, $\operatorname{trace}(DC) = 1 + 1 = 2$. This case is possible given by $C = D = I$.

   - $\lambda_1^2 = \lambda_2$ and $\lambda_2^2 = \lambda_1$.

      Which means $\lambda_1^4 = \lambda_1 \Longrightarrow \lambda_1^3 = 1$. Then, $\lambda_1$ is 3rd root of unity. By similar argument $\lambda_2$ is also 3rd root of unity. If either one is $1$, then we get back to the first case. So assume not and we have $(\lambda_1, \lambda_2) = (e^{2\pi i \over 3}, e^{4\pi i \over 3})$ up to permutation. Which mean $\operatorname{trace}(DC) = e^{2\pi i \over 3} + e^{4\pi i \over 3} = -1$. This case is possible given by
      
      $$C = \begin{bmatrix} 0 & 1 \\ 1 & 0 \end{bmatrix} \quad D = \begin{bmatrix} \sin ({2\pi \over 3}) & \cos ({2\pi \over 3}) \\ \cos ({2\pi \over 3}) & -\sin ({2\pi \over 3}) \end{bmatrix}$$

   So all possible value of $\operatorname{trace}(CD)$ is $2$ and $-1$.


Actually, one of problem is broken though. The detail is left as exercise to the reader.
