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

$*$ From $(\log_{5} n)$ to $(\log_{2} n)$: Given the relationship $\log_5 n = \frac{1}{k} \(log_2 n)$, its clear that for any n, $(\log_{5} n)$ grows at the same rate as $(\log_{2} n)$, differing only by the constant factor $\frac{1}{k}$. This means $(\log_{5} n)$ ∈ $O(\log_{2} n)$

$*$ From $(\log_{2} n)$ to $(\log_{5} n)$: Similarly, multiplying both sides of the equation by k, we get $(\log_{2} n)$ = $k * (\log_{5} n)$. Here, $(\log_{2} n)$ is within a constant factor k of $(\log_{5} n)$, which shows $(\log_{2} n)$ ∈ $O(\log_{5} n)$

The proofs above demonstrate that $(\log_{2} n)$ and $(\log_{5} n)$ are within constant factors of each other. So we can arrive to the conclusion by the definition of Big O notation that O(log<sub>2</sub>n) = O(log<sub>5</sub>n). This is also due to the fact that the base of the logarithm has no affect on how it is categorized in terms of asymptotic complexity. Therefore, the growth rates of $(\log_{2} n)$ and $(\log_{5} n)$ are considered equivalent in Big O Notation. <br />

