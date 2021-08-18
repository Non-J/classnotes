# Calculus 2: Infinite Series

## Sequences and Series

A sequence $a(n)$ is a function that takes $n\in\Z^+$. Its associated series is $s(n)=\sum_{i=1}^{i=n}{a(i)}$. Observe that series is a subtype of sequence.

- Arithmetric Sequence is a sequence whose terms increase/decrease by a constant.
- Geometric Sequence is a sequence whose terms increase/decase by a constant multiple.

A sequence "converges" if $lim_{n\to\infty}a(n)$ exists, otherwise the sequence "diverges".

## Sequeeze Theorem

If $a(n)\leq b(n)\leq c(n)$ and $lim_{n\to\infty}a(n)=lim_{n\to\infty}c(n)=L$, then $lim_{n\to\infty}b(n)=L$.

If $\sum_n{a(n)}, \sum_n{c(n)}$ converges and $a(n)\leq b(n)\leq c(n)$ for arbitrarily large $n$ then $\sum_n{b(n)}$ also converges.

Tip: Try to apply Sequeeze Theorem to absolute functions.

## Convergence Tests

| Name             | Test                                                                                                                                                                                                         | Condition                                                                  |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------- |
| p-series         | $\sum{1/n^p}$                                                                                                                                                                                                | Converges if $p>1$, diverges otherwise.                                    |
| Geometric Series | $\sum{c\cdot r^n}$                                                                                                                                                                                           | Converges if $\|r\| <1$, diverges otherwise.                               |
| Divergence       | $\lim_{n\to\infty}{a_n}\neq0 \implies \sum{a}$ diverges                                                                                                                                                      |                                                                            |
| Integral         | $\int_{1}^{\infty}{f(x)dx} \iff \sum{a}$                                                                                                                                                                     | $f(n)=a_n$ for $n\in\N$<br />$f$ is continuous, positive, and decreasing.  |
| Comparison       | $\sum{b_n}$ converges $\implies\sum{a_n}$ converges<br />$\sum{a_n}$ diverges $\implies\sum{b_n}$ diverges                                                                                                   | $a_n\le b_n$ after sufficiently large $n$, and terms are positive.         |
| Limit Comparison | $\lim_{n\to\infty}{a_n/b_n}$<br />$>0\implies\sum{a_n}\leftrightarrow\sum{b_n}$<br />$=0\implies\sum{b_n}$converges $\to\sum{a_n}$ converges<br />$=\infty\implies\sum{b_n}$ diverges $\to\sum{a_n}$diverges | $a_n$ and $b_n$ are positive.                                              |
| Ratio            | $\lim_{n\to\infty}{\|{a_{n+1}}/{a_n}\|}$<br />$<1\implies\sum{a_n}$ converges<br />$>1\implies\sum{a_n}$ diverges<br />$=1\implies$ inconclusive                                                             | Result implies [absolute convergence](#absolute-convergence).              |
| Root             | $\lim_{n\to\infty}{\sqrt[n]{\|a_n\|}}$<br />$<1\implies\sum{a_n}$ converges<br />$>1\implies\sum{a_n}$ diverges<br />$=1\implies$ inconclusive                                                               | Result implies [absolute convergence](#absolute-convergence).              |
| Alternative      | $\lim_{n\to\infty}f(n)=0\implies a_n$ converges                                                                                                                                                              | $a_n=(-1)^{n}f(n)$<br />$f(n)$ is positive,  and decreasing for $n\in\Z^+$ |

#### Absolute and Conditional Convergent

$\sum{a_n}$ conditionally converges if $\sum{|a_n|}$ diverges but $\sum{a_n}$ converges.

<a name="absolute-convergence"></a>

$\sum{a_n}$ absolutely converges if $\sum{|a_n|}$ converges.

$\sum{a_n}$ absolutely converges $\implies \sum{a_n}$ and $\sum{|a_n|}$ both converges.

## Power Series and Taylor Series

A power series $f(x)=\sum_{n=0}^\infty{c_n(x-x_0)^n}$ will **converges only** for $|x-x_0|<R$[^ p1] for some value $R$ (possibly $0$ or $\infty$)

A power series is *continuous, differentiable, and integratable[^ p2]* on the interval $(x_0-R, x_0+R)$

A Taylor series is expression of a function in the form of power series, where $c_n=\frac{(d/dx)^n(f)(x_0)}{\operatorname{factorial}(n)}$

[^ p1]: Be careful of the convergence at endpoint (i.e, $x=x_0\pm R$)
[^ p2]: Radius of convergence is unchanged for differentiation and integration

### Maclaurin Series References Tables

Maclaurin Series are Taylor series where $x_0=0$

| Function     | Series (Term)                                           | Interval of Convergence |
| ------------ | ------------------------------------------------------- | ----------------------- |
| $1/({1-x})$  | $x^n$                                                   | $\|x\|<1$               |
| $e^x$        | $x^n/\operatorname{factorial}(n)$                       | $\R$                    |
| $\sin(x)$    | $(-1)^n\frac{x^{2n+1}}{\operatorname{factorial}(2n+1)}$ | $\R$                    |
| $\cos(x)$    | $(-1)^n\frac{x^{2n}}{\operatorname{factorial}(2n)}$     | $\R$                    |
| $\arctan(x)$ | $(-1)^n\frac{x^{2n+1}}{2n+1}$                           | $\|x\|<1$               |
| $\ln(1+x)$   | $(-1)^{n+1}x^n/n$                                       | $\|x\|<1$ and 1         |
| $(x+1)^k$    | $\binom{k}{n}x^n$                                       | $\|x\|<1$               |

