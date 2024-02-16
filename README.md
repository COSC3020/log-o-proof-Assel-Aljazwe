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
Defining Big O: Big O notation $O(f(n))$ defines an upper bound of $f(n)$, meaning $f(n) ≤ c * g(n)$ for some constant $c > 0$ and a sufficiently large $n$, n ≥ n<sub>0</sub>
Proving O(log<sub>2</sub>n) = O(log<sub>5</sub>n): <br />
Recalling Change of Base Formula: log<sub>b</sub>a = $\frac{log_c a}{log<sub>c</sub>b}$ where a > 0, b > 1, c > 1 <br />
Applying Change of Base Formula: log<sub>5</sub>n = $\frac{log<sub>2</sub>n}{log<sub>2</sub>5}$ <br />
Setting Constants: Let k = log<sub>2</sub>5, which is a constant because both 2 and 5 are constants <br />
Equivalent expression for log<sub>5</sub>n: log<sub>5</sub>n = $\frac{1}{k}$ log<sub>2</sub>n  $\frac{1}{k}$ is a constant multiplier. <br />
Using Big O Defintion: By definition, for f(n) = log<sub>2</sub>n to be in O(log<sub>5</sub>n), there must exist constants c > 0 and n<sub>0</sub> > 0 such that 0 ≤ log<sub>2</sub>n ≤ c * log<sub>5</sub>n for all n ≥ n<sub>0</sub> <br />
Substituting log<sub>5</sub>n with its relation: 0 ≤ log<sub>2</sub>n ≤ c * $\frac{1}{k}$ log<sub>2</sub>n <br />
Choose c = k: Ensuring the inequality holds as: 0 ≤ log<sub>2</sub>n ≤ k * $\frac{1}{k}$ log<sub>2</sub>n = log<sub>2</sub>n <br />
