# Maximum Density of an Integer Set Containing No n, 2n, 3n Simultaneously

## Problem

Let \(A\subseteq \mathbb N\) be a set of positive integers such that there is no \(n\in\mathbb N\) for which all three of

$$
n,\qquad 2n,\qquad 3n
$$

belong to \(A\).

We prove that the maximum possible asymptotic density of \(A\) is

$$
\boxed{\frac34}.
$$

The proof has two parts:

1. a construction of density \(3/4\);
2. an upper bound of \(3/4\).

---

# 1. Lower bound: a construction of density \(3/4\)

For a positive integer \(n\), let \(v_3(n)\) denote the exponent of \(3\) in the prime factorization of \(n\).

Define

$$
A_0=\{n\ge1:\ v_3(n)\text{ is even}\}.
$$

We first verify that \(A_0\) is admissible.

Suppose \(n\in A_0\). Then \(v_3(n)\) is even. Since multiplication by \(2\) does not change the exponent of \(3\),

$$
v_3(2n)=v_3(n)
$$

is also even.

On the other hand,

$$
v_3(3n)=v_3(n)+1
$$

is odd.

Therefore \(n\) and \(2n\) may both belong to \(A_0\), but \(3n\notin A_0\). Hence \(A_0\) never contains all of \(n,2n,3n\).

Now compute its density.

The density of integers with \(v_3(n)=b\) is

$$
\frac{2}{3^{b+1}},
$$

because such integers are divisible by \(3^b\) but not by \(3^{b+1}\).

Therefore

$$
d(A_0)
=
\sum_{\substack{b\ge0\\b\text{ even}}}
\frac{2}{3^{b+1}}.
$$

Writing \(b=2k\),

$$
d(A_0)
=
\frac23\sum_{k=0}^{\infty}\frac1{9^k}
=
\frac23\cdot\frac{1}{1-\frac19}
=
\frac23\cdot\frac98
=
\frac34.
$$

Thus

$$
\boxed{\sup d(A)\ge\frac34}.
$$

---

# 2. Upper bound

We now prove that no admissible set can have density greater than \(3/4\).

The argument is most naturally expressed using logarithmic density.

For a set \(B\subseteq\mathbb N\), define its logarithmic density, when the limit exists, by

$$
\delta_{\log}(B)
=
\lim_{N\to\infty}
\frac{1}{\log N}
\sum_{\substack{n\le N\\n\in B}}
\frac1n.
$$

A standard summation-by-parts argument shows that if \(B\) has an asymptotic density \(d(B)\), then

$$
\delta_{\log}(B)=d(B).
$$

Consequently, it is enough to prove

$$
\overline{\delta}_{\log}(A)\le\frac34
$$

for every admissible \(A\).

---

# 3. Decomposition into the \(2\)- and \(3\)-adic grid

Every positive integer has a unique representation

$$
n=2^a3^bq,
$$

where

$$
a,b\ge0,
\qquad
\gcd(q,6)=1.
$$

For \(a,b\ge0\), define

$$
X_{a,b}(q)
=
\mathbf 1_A(2^a3^bq),
$$

where \(q\) ranges over positive integers coprime to \(6\).

The admissibility condition says that for every such \(q\),

$$
X_{a,b}(q)\,
X_{a+1,b}(q)\,
X_{a,b+1}(q)=0.
$$

In words, for every lattice point \((a,b)\), we cannot simultaneously select

$$
(a,b),\qquad(a+1,b),\qquad(a,b+1).
$$

---

# 4. Passing to normalized logarithmic averages

Let

$$
Q=\{q\ge1:\gcd(q,6)=1\}.
$$

Set

$$
H_Q(N)
=
\sum_{\substack{q\le N\\q\in Q}}\frac1q.
$$

By the standard harmonic-density calculation,

$$
H_Q(N)=\frac13\log N+O(1).
$$

Choose a sequence \(N_j\to\infty\) along which the upper logarithmic density of \(A\) is attained.

By a diagonal subsequence argument, we may assume that for every fixed \(a,b\),

$$
x_{a,b}
=
\lim_{j\to\infty}
\frac{1}{H_Q(N_j)}
\sum_{\substack{q\le N_j\\q\in Q}}
\frac{X_{a,b}(q)}q
$$

exists.

Thus

$$
0\le x_{a,b}\le1.
$$

For each fixed \(b\), define

$$
c_b
=
\sum_{a=0}^{\infty}2^{-a}x_{a,b}.
$$

Since

$$
0\le x_{a,b}\le1,
$$

the series converges and

$$
0\le c_b\le2.
$$

The upper logarithmic density of \(A\) along the chosen sequence is

$$
\delta_{\log}(A)
=
\frac13
\sum_{b=0}^{\infty}3^{-b}c_b.
$$

Indeed, the contribution of the class

$$
n=2^a3^bq,\qquad (q,6)=1
$$

is weighted by

$$
\frac{1}{2^a3^b}
$$

and the normalized harmonic mass of \(Q\) contributes the factor \(1/3\).

The interchange of the limit and the infinite sums is justified by the geometric tails

$$
\sum_{a>A}2^{-a}\to0,
\qquad
\sum_{b>B}3^{-b}\to0.
$$

---

# 5. The one-dimensional potential inequality

Fix \(b\).

For a fixed \(q\in Q\), write

$$
x_a=X_{a,b}(q)\in\{0,1\}.
$$

Define

$$
h(0)=\frac23,
\qquad
h(1)=\frac43.
$$

For every \(u,v\in\{0,1\}\), we have

$$
u\left(1-\frac13v\right)
\le
h(u)-\frac12h(v).
$$

This is checked directly in the four cases:

$$
(u,v)=(0,0):
\qquad
0\le\frac13;
$$

$$
(u,v)=(0,1):
\qquad
0\le0;
$$

$$
(u,v)=(1,0):
\qquad
1\le1;
$$

$$
(u,v)=(1,1):
\qquad
\frac23\le\frac23.
$$

Therefore, multiplying by \(2^{-a}\) and summing over \(a\ge0\),

$$
\sum_{a\ge0}
2^{-a}x_a
\left(1-\frac13x_{a+1}\right)
\le
\sum_{a\ge0}
2^{-a}
\left(
h(x_a)-\frac12h(x_{a+1})
\right).
$$

The right-hand side telescopes:

$$
\sum_{a=0}^{N}
2^{-a}
\left(
h(x_a)-\frac12h(x_{a+1})
\right)
=
h(x_0)-2^{-(N+1)}h(x_{N+1}).
$$

Since \(h(x)\le4/3\),

$$
\sum_{a\ge0}
2^{-a}
x_a
\left(1-\frac13x_{a+1}\right)
\le
\frac43.
$$

Define

$$
W_b(q)
=
\sum_{a\ge0}
2^{-a}
X_{a,b}(q)X_{a+1,b}(q).
$$

Then

$$
\sum_{a\ge0}2^{-a}X_{a,b}(q)
-\frac13W_b(q)
\le
\frac43.
$$

Averaging over \(q\) and passing to the chosen limit gives

$$
c_b-\frac13W_b\le\frac43,
$$

where

$$
W_b
=
\lim_{j\to\infty}
\frac1{H_Q(N_j)}
\sum_{\substack{q\le N_j\\q\in Q}}
\frac{W_b(q)}q.
$$

Hence

$$
c_b
\le
\frac43+\frac13W_b.
$$

---

# 6. The forbidden third point

If

$$
X_{a,b}(q)=X_{a+1,b}(q)=1,
$$

then admissibility forces

$$
X_{a,b+1}(q)=0.
$$

Therefore, pointwise in \(q\),

$$
X_{a,b+1}(q)
\le
1-X_{a,b}(q)X_{a+1,b}(q).
$$

Multiply by \(2^{-a}\) and sum over \(a\):

$$
\sum_{a\ge0}
2^{-a}X_{a,b+1}(q)
\le
\sum_{a\ge0}2^{-a}
-
\sum_{a\ge0}
2^{-a}X_{a,b}(q)X_{a+1,b}(q).
$$

Since

$$
\sum_{a\ge0}2^{-a}=2,
$$

we obtain

$$
c_{b+1}\le2-W_b.
$$

Equivalently,

$$
W_b\le2-c_{b+1}.
$$

Substituting this into the previous inequality,

$$
c_b
\le
\frac43+\frac13(2-c_{b+1}),
$$

so

$$
\boxed{
c_b+\frac13c_{b+1}\le2.
}
$$

This inequality holds for every \(b\ge0\).

---

# 7. Summing the column inequalities

Multiply

$$
c_b+\frac13c_{b+1}\le2
$$

by \(3^{-b}\), and sum only over even \(b\):

$$
\sum_{\substack{b\ge0\\b\text{ even}}}
3^{-b}c_b
+
\sum_{\substack{b\ge0\\b\text{ even}}}
3^{-(b+1)}c_{b+1}
\le
2
\sum_{\substack{b\ge0\\b\text{ even}}}
3^{-b}.
$$

The first sum contains all even \(b\), while the second contains all odd \(b\). Hence the left-hand side is exactly

$$
\sum_{b\ge0}3^{-b}c_b.
$$

On the right,

$$
2
\sum_{k=0}^{\infty}3^{-2k}
=
2\sum_{k=0}^{\infty}\frac1{9^k}
=
2\cdot\frac98
=
\frac94.
$$

Therefore

$$
\sum_{b\ge0}3^{-b}c_b
\le
\frac94.
$$

Consequently,

$$
\delta_{\log}(A)
=
\frac13
\sum_{b\ge0}3^{-b}c_b
\le
\frac13\cdot\frac94
=
\frac34.
$$

Thus every admissible set satisfies

$$
\boxed{
\overline{\delta}_{\log}(A)\le\frac34.
}
$$

In particular, every admissible set having an asymptotic density satisfies

$$
\boxed{
d(A)\le\frac34.
}
$$

---

# 8. Equality

The construction

$$
A_0=\{n:v_3(n)\text{ is even}\}
$$

has asymptotic density

$$
\frac34
$$

and contains no triple \(n,2n,3n\).

Together with the upper bound,

$$
d(A)\le\frac34,
$$

we conclude that the maximum possible asymptotic density is

$$
\boxed{\frac34}.
$$

---

# Conclusion

The extremal density is

$$
\boxed{\frac34}.
$$

An extremal construction is

$$
\boxed{
A_0=\{n\ge1:v_3(n)\equiv0\pmod2\}.
}
$$

The upper bound follows from the potential-function inequality

$$
u\left(1-\frac13v\right)
\le
h(u)-\frac12h(v),
\qquad
h(0)=\frac23,\quad h(1)=\frac43,
$$

which yields the column recurrence

$$
\boxed{
c_b+\frac13c_{b+1}\le2.
}
$$

Summing this recurrence over even \(b\) gives

$$
\sum_{b\ge0}3^{-b}c_b\le\frac94,
$$

and hence

$$
\boxed{d(A)\le\frac34}.
$$

Since the explicit construction attains \(3/4\), the bound is sharp.
