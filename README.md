[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/fbkbKZ5N)
# Asymptotic Equivalences

In the lectures, we said that logarithms with different bases don't affect the
asymptotic complexity of an algorithm. Prove that $O(\log_{2} n)$ is the same as
$O(\log_{5} n)$. Use the mathematical definition of $O$ -- do a formal proof,
not just the intuition.

I have started with the formal definition of $O$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$T(n) \in O(f(n)) \iff \exists c, n_0: T(n) \leq c \cdot f(n) \forall n \geq n_0$

## Proof:
**Defining Big O**: Big O notation $O(f(n))$ defines an upper bound of $f(n)$, meaning $f(n) ≤ c * g(n)$ for some constant $c > 0$ and a sufficiently large $n$, n ≥ n<sub>0</sub> <br />
### Proving O(log<sub>2</sub>n) = O(log<sub>5</sub>n): <br />

**Recalling Change of Base Formula for Logarithms**: $$\log_b a = \frac{\log_c a}{\log_c b}$$ where \(a > 0\), \(b > 1\), and \(c > 1\). <br />

**Applying Change of Base Formula to Relate $(\log_{2} n)$ and $(\log_{5} n)$**:

$$\log_5 n = \frac{\log_2 n}{\log_2 5}$$

**Setting Constants**: Let k = log<sub>2</sub>5, which is a constant because both 2 and 5 are constants <br />

**Equivalent expression for (log<sub>5</sub>n)**:

$$\log_5 n = \frac{1}{k} \(log_2 n)$$

where $\frac{1}{k}$ is a constant multiplier.

**Using Big O Defintion to Conclude Asymptotic Equivalence**: Given that $(\log_{5} n)$ is a constant multiple of $(\log_{2} n)$ , according to the definition of Big O Notation, if two functions $f(n)$ and $g(n)$ satisfy $f(n) ≤ c * g(n)$ for some constant $c > 0$ and all sufficiently large $n$, then $f(n)$ ∈ $O(g(n))$.

**Demonstrating Constant Factors Do Not Matter using Big O Definition**:

Lets theoretically consider f(n) = $(\log_{5} n)$ and g(n) = $(\log_{2} n)$. According to the Big O Definition, we're looking for a constant C such that $f(n) ≤ C * g(n)$ for sufficiently large $n$

Given the change of base formula, $\log_5 n = \frac{\log_2 n}{\log_2 5}$, we can identify k = ${\log_2 5}$ as a constant factor. This transformation shows that $(\log_{5} n)$ can be bounded by $(\log_{2} n)$ when multiplied by any constant C ≥ $\frac{1}{k}$. Thus showing that the specific value of C (in this case $\frac{1}{k}$) does not impact the classification of $\log_5 n$ in terms of Big O notation because any constant factor satisfying C ≥ $\frac{1}{k}$ can be used to meet the Big O criteria.

By choosing C = $\frac{1}{k}$ (or any C ≥ $\frac{1}{k}$) and any n<sub>0</sub> > 1, we prove that $(\log_{5} n)$ grows no faster than a constant multiple of $(\log_{2} n)$. Therefore, confirming $(\log_{5} n)$ ∈ $O(\log_{2} n)$, and demonstrating that the constants (including the log bases) do not change/have no impact on the growth rate comparison between $(\log_{5} n)$ and $(\log_{2} n)$. The constant in this case only serves to scale functions for comparison. Moreover, this proves the bases of these logarithms, also treated as constants, have no impact on the asymptotic classification.

$*$ **Reciprocal from $(\log_{2} n)$ to $(\log_{5} n)$**: Similarly, multiplying both sides of the equation by k, we get $(\log_{2} n)$ = $k * (\log_{5} n)$. Here, the roles of $(\log_{2} n)$ and $(\log_{5} n)$ are reversed, demonstrating that $(\log_{2} n)$ can similarly be bounded by $(\log_{5} n)$ multiplied by a constant (in this case, k or even any constant C' > k), further reinforcing the idea that the choice of the constant (whether k or 1/k) is irrelevant for asymptotic classification. So, similarly $(\log_{2} n)$ ∈ $O(\log_{5} n)$

The analysis above demonstrates through direct application of the Big O definition and the logarithm change of base formula, that constant factors like k and 1/k do not affect the asymptotic classification of functions. By showing that $(\log_{5} n)$ can be expressed as a constant multiple of $(\log_{2} n)$ and vice versa, and that any constant greater than the initial constants k or 1/k satisfy the Big O criteria, we confirm that $O(\log_{2} n)$ = $O(\log_{5} n)$. Hence concluding that the constants, including the bases of logarithms, while being different constants don't impact how we classify their growth with Big O notation, reinforcing the idea that constants don't really matter in Big O. Moreover, as these functions grow, the impact of the constant multipliers (including those that represent logarithmic bases) become negligible compared to the function's log n growth rates.

