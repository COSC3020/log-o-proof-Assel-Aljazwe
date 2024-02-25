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

### Proving O(log<sub>2</sub>n) = O(log<sub>5</sub>n): <br />

### Formal Definition of Big O Notation
The definition of Big O notation is as follows:
$$f(n) \in O(g(n)) \iff \exists c > 0, n_0 > 0 : 0 \leq f(n) \leq c \cdot g(n), \forall n \geq n_0$$

### Change of Base Formula
The change of base formula for logarithms is important for this proof:
$$\log_{a} n = \frac{\log_{b} n}{\log_{b} a}$$

### Proof Method
To show that $\log_{2} n$ and $\log_{5} n$ are equivalent in terms of Big O notation, we'll find constants $c$ and $n_0$ that satisfy the formal definition of Big O notation.

### Application of Change of Base Formula
Converting $\log_{2} n$ to base 5 using the change of base formula gives us:
$$\log_{2} n = \frac{\log_{5} n}{\log_{5} 2}$$

Representing $\frac{1}{\log_{5} 2}$ as $k$, where $k$ is a constant because $\log_{5} 2 > 0$. This allows us to express $\log_{2} n$ as a multiple of $\log_{5} n$:
$$\log_{2} n = k \cdot \log_{5} n$$

### Establishing Equivalence
Given the relationship between $\log_{2} n$ and $\log_{5} n$, we see that for any choice of $n_0 > 1$, there exists a constant $c = k$ such that:
$$\log_{2} n \leq c \cdot \log_{5} n, \forall n \geq n_0$$

### Conclusion
Since we can express $\log_{2} n$ as a constant multiple of $\log_{5} n$, and this relationship holds for all $n \geq n_0$, we can conclude that:
$$O(\log_{2} n) = O(\log_{5} n)$$

This proves that logarithms with different bases are equivalent in Big O notation, showing that the base of the logarithm does not affect the asymptotic complexity class.

