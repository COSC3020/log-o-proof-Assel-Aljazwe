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


# Proving that $O(\log_2 n)$ is the same as $O(\log_5 n)$ using the formal definition of Big O notation.

## Formal Definition of Big O Notation

For two functions $f(n)$ and $g(n)$,

$$
f(n) \in O(g(n)) \Leftrightarrow \exists c > 0, n_0 > 0 : 0 \leq f(n) \leq c \cdot g(n), \forall n \geq n_0
$$

Our goal is to show that $\log_2(n) \in O(\log_5(n))$ and vice versa.

## Proof:

We can utilize the change of base formula for logarithms:

$$
\log_a(b) = \frac{\log_c(b)}{\log_c(a)}
$$

for any positive $a, b, c$, where $a \neq 1$, $b \neq 1$, and $c \neq 1$.

### Proving $\log_2(n) \in O(\log_5(n))$

By applying the change of base formula, we express $\log_2(n)$ in terms of $\log_5(n)$:

$$
\log_2(n) = \frac{\log_5(n)}{\log_5(2)}
$$

**Assumption for Contradiction:** Suppose $\log_2(n) \notin O(\log_5(n))$.

This would mean that there exists no values of $c > 0$ and $n_0 > 0$, to satisfy the following:

$$
0 \leq \left(\frac{\log_5(n)}{\log_5(2)}\right) \leq c \cdot \log_5(n), \forall n \geq n_0
$$

**Contradiction:** However, by setting $c = \frac{1}{\log_5(2)}$, a constant greater than 0, and choosing any $n_0 > 1$, the inequality is satisfied. This contradicts the assumption.

### Proving $\log_5(n) \in O(\log_2(n))$

Similarly, we apply the change of base formula to express $\log_5(n)$ in terms of $\log_2(n)$:

$$
\log_5(n) = \frac{\log_2(n)}{\log_2(5)}
$$

**Assumption for Contradiction:** Assume $\log_5(n) \notin O(\log_2(n))$.

This implies that there exist no values of $c > 0$ and $n_0 > 0$ that can satisfy:

$$
0 \leq \left(\frac{\log_2(n)}{\log_2(5)}\right) \leq c \cdot \log_2(n), \forall n \geq n_0
$$

**Contradiction:** Selecting $c = \frac{1}{\log_2(5)}$ and any $n_0 > 1$ shows that the inequality can always be satisfied, which contradicts the initial assumption.

## Conclusion

The assumptions for contradiction in both cases were proven wrong, therefore confirming asymptotic equivalence between $\log_2(n)$ and $\log_5(n)$. Thus generalizing the argument, showing that for any $n$ greater than a specified $n_0$, the logarithmic functions with bases 2 and 5 are asymptotically equivalent within Big O notation.
