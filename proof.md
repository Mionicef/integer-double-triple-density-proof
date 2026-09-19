# Maximum Density of an Integer Set Containing No $n, 2n, 3n$ Simultaneously

## Theorem

Let $A\subseteq\mathbb N$ be a set of positive integers such that there is no $n\in\mathbb N$ with $n\in A$, $2n\in A$ and $3n\in A$ all at once. If $A$ has an asymptotic (natural) density $d(A)$, then

$$
d(A)\le \frac34 .
$$

Moreover, the value $3/4$ is attained by

$$
A_0=\lbrace n\in\mathbb N : v_3(n)\text{ is even}\rbrace ,
$$

where $v_3(n)$ denotes the exponent of $3$ in the prime factorization of $n$. Hence the maximum density is

$$
\boxed{\dfrac34}.
$$

The upper bound is proved for sets whose natural density exists (the argument also works for the lower density; see Section 6).

---

## 1. Lower bound: a construction of density $3/4$

Let

$$
A_0=\lbrace n\in\mathbb N : v_3(n)\text{ is even}\rbrace .
$$

### $A_0$ is admissible

For every $n$,

$$
v_3(2n)=v_3(n),\qquad v_3(3n)=v_3(n)+1 .
$$

So $n$ and $2n$ have the same parity of $v_3$, while $3n$ has the opposite parity. Hence $n,2n,3n$ can never all lie in $A_0$.

### Density of $A_0$

Let $S_b=\lbrace n : v_3(n)=b\rbrace=\lbrace 3^b m : 3\nmid m\rbrace$. Its density is

$$
\frac1{3^b}\left(1-\frac13\right)=\frac{2}{3^{b+1}} .
$$

For $B\ge 0$ let $T_B=\lbrace n : v_3(n)>B\rbrace$. This is exactly the set of multiples of $3^{B+1}$, so its density is $3^{-(B+1)}$. Writing $A_0(x)=\operatorname{card}\lbrace  n\le x : n\in A_0\rbrace$, we get

$$
\left| A_0(x)-\operatorname{card}\lbrace  n\le x : v_3(n)\in\lbrace 0,2,4,\dots\rbrace,\ v_3(n)\le B\rbrace\right|\le \frac{x}{3^{B+1}} .
$$

The finite union on the right has density $\sum_{b\le B,\ b\text{ even}} \frac{2}{3^{b+1}}$. So the upper and lower densities of $A_0$ differ from this finite sum by at most $3^{-(B+1)}$. Letting $B\to\infty$:

$$
d(A_0)=\sum_{k\ge0}\frac{2}{3^{2k+1}}=\frac23\sum_{k\ge0}\frac1{9^k}=\frac23\cdot\frac{1}{1-\frac19}=\frac23\cdot\frac98=\frac34 .
$$

Therefore the maximum density is at least $3/4$.

---

## 2. Decomposition into $2$-adic and $3$-adic coordinates

Every positive integer has a unique representation

$$
n=2^a3^b q,\qquad a,b\ge 0,\quad (q,6)=1 .
$$

Let $Q=\lbrace q\ge 1 : (q,6)=1\rbrace$. For $a,b\ge 0$ and $q\in Q$ define

$$
X_{a,b}(q)=\mathbf 1_A\left(2^a3^bq\right)\in\lbrace 0,1\rbrace .
$$

For fixed $q$, the numbers $2^a3^bq$ form a grid indexed by $(a,b)$, called the **fiber** of $q$. The number $n=2^a3^bq$ sits at $(a,b)$, its double $2n$ at $(a+1,b)$, and its triple $3n$ at $(a,b+1)$. So $A$ is admissible if and only if, for all $a,b\ge0$ and $q\in Q$,

$$
X_{a,b}(q)X_{a+1,b}(q)X_{a,b+1}(q)=0. \qquad (\star)
$$

The proof has two steps:

1. On every fiber, the weighted sum $\sum_{a,b} X_{a,b}(q)/(2^a3^b)$ is at most $9/4$. The total weight of a full fiber is $\sum_{a,b}2^{-a}3^{-b}=2\cdot\frac32=3$, so an admissible set fills at most $\frac{9/4}{3}=\frac34$ of it.
2. Summing over $q\in Q$ with harmonic weights $1/q$ gives $\sum_{n\le N,\ n\in A}\frac1n\le\frac34\log N+O(1)$.

---

## 3. The weighted bound on one fiber

Fix $q\in Q$ and write $x_{a,b}=X_{a,b}(q)\in\lbrace0,1\rbrace$. For each $b\ge0$ define

$$
c_b=\sum_{a\ge0}2^{-a}x_{a,b},\qquad W_b=\sum_{a\ge0}2^{-a}x_{a,b}x_{a+1,b}.
$$

Clearly $0\le c_b\le 2$ and $W_b\ge 0$.

### Lemma 1

For every $b\ge0$,

$$
c_{b+1}\le 2-W_b .
$$

**Proof.** By $(\star)$, $x_{a,b+1}\le 1-x_{a,b}x_{a+1,b}$. Multiply by $2^{-a}$ and sum over $a\ge0$:

$$
c_{b+1}\le\sum_{a\ge0}2^{-a}-\sum_{a\ge0}2^{-a}x_{a,b}x_{a+1,b}=2-W_b. \qquad\blacksquare
$$

### Lemma 2

For every $b\ge0$,

$$
c_b-\frac13W_b\le\frac43 .
$$

**Proof.** Define $h(0)=\frac23$ and $h(1)=\frac43$. For all $u,v\in\lbrace0,1\rbrace$,

$$
u\left(1-\frac13v\right)\le h(u)-\frac12h(v). \qquad (1)
$$

This is checked in the four cases:

| $(u,v)$ | $u(1-v/3)$ | $h(u)-h(v)/2$ |
|:---:|:---:|:---:|
| $(0,0)$ | $0$ | $\frac13$ |
| $(0,1)$ | $0$ | $0$ |
| $(1,0)$ | $1$ | $1$ |
| $(1,1)$ | $\frac23$ | $\frac23$ |

Fix $b$ and write $X_a=x_{a,b}$. Taking $u=X_a$, $v=X_{a+1}$ in (1) and multiplying by $2^{-a}$:

$$
2^{-a}X_a\left(1-\frac13X_{a+1}\right)\le 2^{-a}h(X_a)-2^{-(a+1)}h(X_{a+1}).
$$

Summing over $a=0,\dots,K$, the right-hand side telescopes:

$$
\sum_{a=0}^{K}2^{-a}\left(X_a-\frac13X_aX_{a+1}\right)\le h(X_0)-2^{-(K+1)}h(X_{K+1})\le\frac43 .
$$

Letting $K\to\infty$ (both series converge) gives $c_b-\frac13W_b\le\frac43$. $\blacksquare$

### Lemma 3

For every $b\ge0$,

$$
c_b+\frac13c_{b+1}\le 2 .
$$

**Proof.** Lemma 2 gives $W_b\ge 3c_b-4$. Combining with Lemma 1,

$$
c_{b+1}\le 2-W_b\le 2-(3c_b-4)=6-3c_b ,
$$

that is, $3c_b+c_{b+1}\le 6$, or $c_b+\frac13c_{b+1}\le2$. $\blacksquare$

### Proposition 4 (weighted bound on every fiber)

For every $q\in Q$,

$$
\sum_{a,b\ge0}\frac{x_{a,b}}{2^a3^b}\le\frac94 .
$$

**Proof.** All terms are nonnegative, so

$$
\sum_{a,b\ge0}\frac{x_{a,b}}{2^a3^b}=\sum_{b\ge0}\frac{c_b}{3^b}.
$$

Group the terms $b=2k$ and $b=2k+1$. By Lemma 3,

$$
\frac{c_{2k}}{3^{2k}}+\frac{c_{2k+1}}{3^{2k+1}}=\frac1{9^k}\left(c_{2k}+\frac13c_{2k+1}\right)\le\frac{2}{9^k}.
$$

Summing over $k\ge0$:

$$
\sum_{b\ge0}\frac{c_b}{3^b}\le 2\sum_{k\ge0}\frac1{9^k}=2\cdot\frac98=\frac94. \qquad\blacksquare
$$

**Sharpness.** For $A_0$ we have $x_{a,b}=1$ if $b$ is even and $0$ if $b$ is odd. Then $c_b=2,0,2,0,\dots$, Lemma 3 is an equality for even $b$, and $\sum_b c_b3^{-b}=\frac94$. So the fiber bound cannot be improved.

---

## 4. Harmonic sum over $Q$

Let

$$
H_Q(N)=\sum_{q\le N,\ q\in Q}\frac1q .
$$

### Lemma 5

$$
H_Q(N)=\frac13\log N+O(1).
$$

**Proof.** By inclusion-exclusion over the divisors of $6$,

$$
H_Q(N)=H(N)-\frac12H\left(\left\lfloor \tfrac N2\right\rfloor\right)-\frac13H\left(\left\lfloor \tfrac N3\right\rfloor\right)+\frac16H\left(\left\lfloor \tfrac N6\right\rfloor\right),
$$

where $H(M)=\sum_{m\le M}\frac1m=\log M+O(1)$. Therefore

$$
H_Q(N)=\left(1-\frac12-\frac13+\frac16\right)\log N+O(1)=\frac13\log N+O(1). \qquad\blacksquare
$$

---

## 5. Global logarithmic upper bound

Let $A$ be admissible and set

$$
D_N=\sum_{n\le N,\ n\in A}\frac1n .
$$

Using $n=2^a3^bq$ with $q\in Q$,

$$
D_N=\sum_{q\le N,\ q\in Q}\frac1q\sum_{a,b\ge0,\ 2^a3^bq\le N}\frac{X_{a,b}(q)}{2^a3^b}.
$$

All terms are nonnegative, so we may drop the restriction $2^a3^bq\le N$ in the inner sum, and then apply Proposition 4:

$$
D_N\le\sum_{q\le N,\ q\in Q}\frac1q\cdot\frac94=\frac94H_Q(N)=\frac94\left(\frac13\log N+O(1)\right).
$$

Hence, for every $N\ge 1$,

$$
D_N\le\frac34\log N+O(1),
$$

where the $O(1)$ is an absolute constant, independent of $A$.

---

## 6. From logarithmic sums to natural density

Let $A(t)=\operatorname{card}\lbrace  n\le t : n\in A\rbrace$. By Abel summation,

$$
D_N=\frac{A(N)}{N}+\int_1^N\frac{A(t)}{t^2}\ dt .
$$

**Case 1: the density exists.** Suppose $d(A)=\lim_{t\to\infty}A(t)/t$ exists. Then $A(N)/N\to d(A)$ and $\int_1^N A(t)t^{-2}\ dt=d(A)\log N+o(\log N)$, so

$$
D_N=d(A)\log N+o(\log N).
$$

Comparing with $D_N\le\frac34\log N+O(1)$ and dividing by $\log N$ gives $d(A)\le\frac34$.

**Case 2: lower density.** Let $\underline d(A)=\liminf A(t)/t$. For any $\varepsilon>0$ there is $T$ with $A(t)\ge(\underline d(A)-\varepsilon)t$ for $t\ge T$. Then $D_N\ge(\underline d(A)-\varepsilon)\log N-C_\varepsilon$, and the same comparison gives $\underline d(A)\le\frac34$.

---

## 7. Conclusion

- Section 1: $A_0=\lbrace n : v_3(n)\text{ is even}\rbrace$ is admissible and $d(A_0)=\frac34$.
- Sections 2 to 6: every admissible $A$ with a natural density (or just a lower density) satisfies $d(A)\le\frac34$.

Therefore the maximum possible density of an integer set containing no number together with both its double and its triple is

$$
\boxed{\dfrac34}.
$$

---

## Remark

The proof controls the (upper) logarithmic density, so it covers every admissible set whose natural density exists, and also lower densities. It does not by itself cover the *upper natural density* of a set whose natural density fails to exist; that question would need a separate argument.
