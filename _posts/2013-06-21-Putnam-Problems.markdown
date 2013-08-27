---
layout: post
title: Three Putnam Math Problems
published: false
---

Sometimes doing some hard but in principle solvable problems can be a good break from more cutting edge research where you don't even know if a solution can be found. In this spirit, I offer you three relatively random problems from the [Putnam exam](http://math.scu.edu/putnam/)[^1]. 

1.  [A3, 1999] Consider the power series expansion

    $$ \begin{align} \label{eq:1} \frac1{1-2x-x^2} = \sum_{n=0}^\infty a_n x^n \end{align}$$

    Prove that, for each integer $$n\geq0$$, there is an integer $$m$$ such that

    $$ \begin{align} \label{eq:2} a_n^2 + a_{n+1}^2 = a_m. \end{align} $$

2.  [A6, 1999] The sequence $$(a_n)_{n\geq 1}$$ is defined by $$a_1=1$$, $$a_2=2$$, $$a_3=24$$, and, for $$n\geq 4$$,

    $$ \begin{align} \label{eq:3} a_n = \frac{6 a_{n-1}^2 a_{n-3} - 8 a_{n-1} a_{n-2}^2}{a_{n-2} a_{n-3}}. \end{align} $$

    Show that, for all $$n$$, $$a_n$$ is an integer multiple of $$n$$.

3.  [B5, 1998] Let $$N$$ be the positive integer with 1998 decimal digits, all of them 1; that is,

    $$ \begin{align} \label{eq:4} N = \underbrace{1111\cdots11}_\text{1998 digits}. \end{align}$$

    Find the thousandth digit after the decimal point of $$\sqrt N$$.

If you want to try these for yourself, give it a shot. In my opinion 1 is the easiest and 2 is the hardest. The solutions are below.

### Solutions

#### 1.

The power series expansion in Eq. \\eqref{eq:1} for this problem represents a classic generating function for the sequence given by $$a_n$$. There are many ways to solve for the $$a_n$$, but one fast way is to note that

$$
\begin{align*}
  \frac1{1-2x-x^2} & = -\frac1{(x-a_+)(x-a_-)} \\ & = \frac1{a_+ -a_-} \left[ \frac1{a_+ - x} - \frac1{a_- - x} \right] \\ & = \frac1{a_+ -a_-} \sum_{n=0}^\infty \frac{a_-^{n+1} - a_+^{n+1}}{(a_+a_-)^{n+1}} x^n
\end{align*}
$$

The polynomial can be solved and we get

$$
  a_\pm = -1 \pm \sqrt{2}.
$$

Then the appropriate numbers can be calculated: $$a_+ a_- = -1$$ and $$a_+ - a_- = 2 \sqrt 2$$, and we have

$$
\begin{align}
  a_n = \frac1{2\sqrt 2} [(1+ \sqrt 2)^{n+1} - (1 - \sqrt 2)^{n+1}]. \label{eq:ansprob1}
\end{align}
$$

With the recurrence relation found, we can square plug it into the appropriate formula. First, we find the square

$$
  a_n^2 = \frac18 [(1 + \sqrt 2)^{2n+2} - 2 (-1)^{n+1} + (1- \sqrt 2)^{2n+2}],
$$

so that if we use $$(1 \pm \sqrt 2)^{-1} = -1 \pm \sqrt 2 $$ to aid in simplification,	

$$
\begin{align*}
  a_n^2 + a_{n+1}^2 & = \frac1{2\sqrt 2} [(1 + \sqrt 2)^{2n+3}  - (1- \sqrt 2)^{2n+3}] \\
   & = a_{2n+2}.
\end{align*}
$$

Thus, $$m = 2n+2$$ and we've solved the problem.

#### 2.

This problem uses sequences as well. To solve it, we first notice that things simplify greatly if we consider $$b_{n} = \frac{a_{n}}{a_{n-1}} $$, in which case the non-linear equation changes to 

$$ b_n = 6 b_{n-1} - 8 b_{n-2}. $$

This equation is much simpler to evaluate and we can do that with the ansatz, $$ b_n = x^n$$. Upon doing that, we get the quadratic equation

$$ x^2 - 6 x + 8 = 0. $$

The solutions of which are $$ x_1 = 4$$ and $$x_2 = 2$$. Thus, the general solution has the form $$ b_n = c_1 4^{n-2} + c_2 2^{n-2}$$. To figure out what the coefficients are, we can find from the initial conditions, $$b_2 = 2$$ and $$b_3 = 12$$, and we have $$2 = c_1 + c_2$$ and $$ 12 = 4 c_1 + 2 c_2$$. From this point, we have that $$ c_1 = 4 $$ and $$ c_2 = -2$$. Thus, 

$$ b_n = 4^{n-1} - 2^{n-1} = 2^{n-1}(2^n - 1).$$

Now, $$a_n = \prod_{j=1}^n b_j$$ as can be checked by induction. Thus,

$$ a_n = \prod_{j=1}^n 2^{j-1} (2^j -1) = 2^{n(n-1)/2} \prod_{j=1}^n (2^j -1 ).$$

Now, does $$n$$ divide this? Well, we can write any integer in the form $$ n = 2^k m$$ where $$k$$ is an integer and $$m$$ is an odd integer. We know that $$k < n$$ so the prefactor $$2^{n(n-1)/2}$$ takes care of the $$ 2^k $$ term, and the initial question becomes whether or not $$m\leq n$$ divides $$\prod_{j=1}^n (2^j -1 )$$.

For this question, consider $$[ 2^j \mod m ]$$ for $$j = 1, \ldots , m$$. Because $$ m $$ is odd, $$ 2^j \neq 0 \mod m $$ and there must be at least one repeat. Our goal is to show that there is a $$j$$ such that $$ 0 < j \leq m $$ and $$ 2^j \mod m \equiv 1$$.

To prove this, we want 
to show that if $$ 2^{j_1} \equiv 2^{j_2} \mod m $$, then $$ 2^{j_1-1} \equiv 2^{j_2-1} \mod m $$. Assume for contradiction $$ 2^{j_1-1} \not\equiv 2^{j_2-1} \mod m $$, then for $$0\leq q_{1,2} < m$$, and integers $$p_{1,2}$$ we have $$ 2^{j_1-1} = q_1 + p_1 m $$ and $$ 2^{j_2 -1 } = q_2 + p_2 m $$. Then if we multiply by $$2$$, we obtain $$ 2^{j_1} = 2 q_1 + 2 p_1 m $$ and $$ 2^{j_2 } = 2q_2 + 2p_2 m $$. Thus, in order to get modular equivalence, we need $$2 q_1 = 2 q_2 + e m $$ for some integer $$ e$$. However, $$ 0 \leq 2 q_{1,2} < 2m$$ implies that $$ e = \pm 1$$. But then $$ m = 2|q_1 - q_2|$$ implies that $$m$$ is an even integer, a contradiction. Thus, we have proven that if $$ 2^{j_1} \equiv 2^{j_2} \mod m $$, then $$ 2^{j_1-1} \equiv 2^{j_2-1} \mod m $$.

Now, we know there must be a $$j_1 < j_2 \leq m$$ such that $$ 2^{j_1} \equiv 2^{j_2} \mod m $$. Further, the chain $$\{ 1 , 2, 4, \ldots, 2^{j_1} \} $$ must be equivalent to the chain $$\{ 2^{j_2-j_1}, \ldots 2^{j_2}\}$$ considered $\mod m$. This is guaranteed by the above statement. (Assume a difference and it immediately contradicts the statement, "If $$ 2^{j_1} \equiv 2^{j_2} \mod m $$, then $$ 2^{j_1-1} \equiv 2^{j_2-1} \mod m $$".) Thus, we have that there is an $$r \leq m$$ such that $$2^r = 1$$ ($$r = j_2 - j_1$$), and thus $$2^r - 1 \equiv 0 \mod m$$.

Therefore, since $$m\leq n$$, we can say $$m$$ divides one of the odd integers $$2^r - 1$$ with $$ r \leq n$$, and thus we have proven that $$ n$$ divides $$a_n$$.

[^1]: Problems and solutions are in [The William Lowell Putnam Mathematical Competition 1985-2000: Problems, Solutions, and Commentary](http://www.amazon.com/William-Lowell-Mathematical-Competition-1985-2000/dp/088385807X).