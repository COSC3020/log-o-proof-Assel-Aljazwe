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


## Proof By Contradiction:

### 1\. Proving $\\log\_2(n) \\in O(\\log\_5(n))$

**Assumption for Contradiction:**

Suppose $\\log\_2(n) \\notin O(\\log\_5(n))$. This means that for every $c > 0$ and every $n\_0 > 0$, there exists some $n \\geq n\_0$ such that:

$\log\_2(n) > c \\cdot \\log\_5(n)$

**Using Change of Base Formula:**

$\log\_2(n) = \\frac{\\log\_5(n)}{\\log\_5(2)}$​

**Deriving Contradiction:**

Choosing $c = \\frac{1}{\\log\_5(2)}$. It follows that for all $n \\geq 1$:

$\log\_2(n) = c \\cdot \\log\_5(n)$

This contradicts the assumption, thus proving $\\log\_2(n) \\in O(\\log\_5(n))$.

### 2\. Proving $\\log\_5(n) \\in O(\\log\_2(n))$

**Assumption for Contradiction:**

Assume $\\log\_5(n) \\notin O(\\log\_2(n))$. This implies that for every $c > 0$ and every $n\_0 > 0$, there exists some $n \\geq n\_0$ such that:

$\log\_5(n) > c \\cdot \\log\_2(n)$

**Using Change of Base Formula:**

$\log\_5(n) = \\frac{\\log\_2(n)}{\\log\_2(5)}$

**Deriving Contradiction:**

Choosing $c = \\frac{1}{\\log\_2(5)}$. It follows that for all $n \\geq 1$:

$\log\_5(n) = c \\cdot \\log\_2(n)$

This contradicts the assumption, proving that $\\log\_5(n) \\in O(\\log\_2(n))$.

# Useful Resources:

Logarithm change of base rule intro https://www.khanacademy.org/math/algebra2/x2ec2f6f830c9fb89:logs/x2ec2f6f830c9fb89:change-of-base/a/logarithm-change-of-base-rule-intro

Time complexity of an algorithm: Is it important to state the base of the logarithm? https://cs.stackexchange.com/questions/109607/time-complexity-of-an-algorithm-is-it-important-to-state-the-base-of-the-logari

Relationship between logarithms with different bases in Time Complexity Analysis https://www.linkedin.com/pulse/relationship-between-logarithms-different-bases-time-analysis-baloch

Omitting bases in Logs -> Big O https://math.stackexchange.com/questions/37377/omitting-bases-in-logs-big-o

ChatGPT https://chatgpt.com/




