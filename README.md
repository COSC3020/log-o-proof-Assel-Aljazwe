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

# Proof of Asymptotic Equivalence

## Formal Definition of Big O Notation

Big O notation formally defines that $f(n) \in O(g(n))$ if and only if there exist constants $c > 0$ and $n_0 > 0$ such that $0 \leq f(n) \leq c \cdot g(n)$ for all $n \geq n_0$.

## Change of Base Formula

The change of base formula for logarithms states: 
$$\log_{a} n = \frac{\log_{b} n}{\log_{b} a}$$

## Proof for $\log_{2} n$ and $\log_{5} n$ Being Asymptotically Equivalent

Using the change of base formula, we can express $\log_{2} n$ in terms of $\log_{5} n$:

$$\log_{2} n = \frac{\log_{5} n}{\log_{5} 2}$$

Let $k = \frac{1}{\log_{5} 2}$, which is a constant because $\log_{5} 2$ is a positive real number. Thus, we can write:

$$\log_{2} n = k \cdot \log_{5} n$$

To satisfy the formal definition of Big O notation, we need to show that for $f(n) = \log_{2} n$ and $g(n) = \log_{5} n$, there exists a constant $c$ such that $f(n) \leq c \cdot g(n)$ for all $n \geq n_0$.

Since $k$ is a constant, we can choose $c = k$ and $n_0 = 1$, therefore satisfying:

$$\log_{2} n \leq c \cdot \log_{5} n, \forall n \geq n_0$$

This establishes that $\log_{2} n \in O(\log_{5} n)$

### Reverse Direction:

Given that $\log_{2} n = k \cdot \log_{5} n$ with $k = \frac{1}{\log_{5} 2}$, we reverse the process to express $\log_{5} n$ in terms of $\log_{2} n$.

Using the change of base formula again, we have:
$$\log_{5} n = \frac{\log_{2} n}{\log_{2} 5}$$

Let $k' = \frac{1}{\log_{2} 5}$, which is also a constant. Therefore:
$$\log_{5} n = k' \cdot \log_{2} n$$

To satisfy the Big O notation definition for $f(n) = \log_{5} n$ and $g(n) = \log_{2} n$, there must exist a constant $c'$ such that:
$$f(n) \leq c' \cdot g(n) \quad \text{for all} \quad n \geq n_0'$$

Since $k'$ is a constant, we can choose $c' = k'$ and $n_0' = 1$, ensuring:
$$\log_{5} n \leq c' \cdot \log_{2} n, \quad \forall n \geq n_0'$$

This proves that $\log_{5} n \in O(\log_{2} n)$, thus showing the two logarithmic functions are asymptotically equivalent

