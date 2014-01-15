---
layout: post
title: Conductance with single particle Quantum Mechanics
published: false
---

In this post, I explore how to derive conductance in a material where there are no interactions and each particle (or quasi-particle) can be described by a single particle Hamiltonian.

In order to do this, we assume that our Hamiltonian has the simplified form

$$ H_0 = T(\mathbf{p}) + U(\mathbf{x}), $$

where $$T(\mathbf{p})$$ is the kinetic energy, a function of the momentum operator $$\mathbf{p}$$, and $$U(\mathbf{x})$$ is any potential, a function of the position operator $$\mathbf{x}$$.
In order to derive the current, we need to first define what the single-particle current is. Well, assume each particle described by the above Hamiltonian has $$-e$$ charge, so that we can say

$$\hat{\mathbf{j}}(t) = -e \dot {\mathbf{x}}(t)$$

is the single particle current operator. This is all in Heisenberg picture, so the operators are evolving instead of the states themselves. In this case, it's just easier to think of how the current is changing instead of how the state is changing and what that means for the current.

Using this, we can use Hamilton's equations of motion to obtain how everything depends on the Hamiltonian. For completeness, we can observe this by noting

$$ \begin{align} \dot x_i^0(t) & = \frac{d}{dt} [e^{i H_0 t} x_i e^{-i H_0 t}] \\
   & = i e^{i H_0 t} [H_0,x_i] e^{-i H_0 t} \\
   & = i e^{i H_0 t} [ T(\mathbf{p}),x_i] e^{-i H_0 t} \\
   & = e^{i H_0 t} \partial_i T(\mathbf{p}) e^{-i H_0 t} = \partial_i T(\mathbf{p}(t)),
   \end{align}
$$

where $$\partial_i T(p)$$ is the derivative of $$T$$ with respect to $$p_i$$.
Thus, the current operator is just

$$
\hat{\mathbf{j}_0}(t) = -e \nabla_{\mathbf{p}} T(\mathbf{p}(t)).
$$

But this does not introduce any electric or magnetic field. To fix that we insert a purely electric field in the form of a $$\mathbf A(t) = \mathbf A(\omega) e^{-i\omega t}$$, so that $$\mathbf E(t) = i \omega \mathbf A(\omega) e^{-i \omega t}$$. Then, the Hamiltonian, after minimal coupling, becomes

$$
H(t) = T(\mathbf p - e \mathbf A(t)) + U(\mathbf x).
$$

For linear response, we can expand $$T$$ since $$A(t)$$  commutes with everything as a $$c$$-number. Then, our Hamiltonian is

$$
H(t) = T(p) + U(x) - e \mathbf A(t) \cdot \nabla_{\mathbf p} T(\mathbf p).
$$

(For the case of $$T(p)$$ linear, this is the only term and it's exact.)

Thus, the term added to our Hamiltonian is $$\mathbf A(t) \cdot \hat{\mathbf j}_0$$ (no time-dependence on the current operator). In order to see how the current operator changes with the inclusion of this term, we need to use the fact that the unitary evolution that satisfies $$i\partial_t U(t) = H(t) U(t)$$, approximately looks like

$$U(t,0) = e^{-i H_0 t} \left(1 - i \int_0^t dt' \mathbf A(t') \cdot \hat{\mathbf j}_0(t')\right).$$

Now, instead of starting things at 0, we start things at $$-\infty$$, and use $$U_0(t,-\infty)$$ to represent the unitary evolution under $$H_0$$.
Then, we can look again at

$$ \begin{align}  j_i(t) & = -e\frac{d}{dt}\left[U^\dagger(t,-\infty) x_i U(t,\infty)\right] \\
 & = -e i U^\dagger(t,-\infty) [H(t), x_i] U(t,-\infty) \\
 & \sim \left(1 + i \int_{-\infty}^t dt' \mathbf A(t') \cdot \hat{\mathbf j}_0(t') \right) j_i^0(t) \left(1 - i \int_{-\infty}^t dt' \mathbf A(t') \cdot \hat{\mathbf j}_0(t') \right)\\  & \quad - e U_0^\dagger(t,-\infty)[\mathbf A(t) \cdot \mathbf{\hat j}_0, x_i] U_0(t,-\infty) \\
  & \sim j_i^0(t) - i \int_{-\infty}^t dt' [j_i^0(t),j_k^0(t')] A_k(t') -  i e^2 \partial_i \partial_k T(\mathbf p(t)) A_k(t). 
\end{align} $$

Now, in order to turn this into a many-body current, we need to sum over all the occupied states with some distribution $$f(\epsilon_n)$$ where $$\epsilon_n$$ is the energy of eigenstate $$n$$. Then, the current is

$$ J_i(t) = \int_{-\infty}^\infty dt' K_{ik}(t-t') A_k(t') $$

where $$K_{ik}(t-t') = -i \sum_n f(\epsilon_n)\langle n \lvert  \{ [j^0_i(t),j_k^0(t')] \theta(t-t') +e^2 \partial_i\partial_k T(\mathbf p(t)) \delta(t-t') \} \rvert n \rangle$$ assuming that current without an applied field is zero.

For now, let us drop the term that's a second derivative in the Kinetic energy -- i.e., assume the Kinetic energy is first order in $$\mathbf p$$. Then, in between the pair of current operators, we insert a complete set of states, and we can write

$$\langle n \lvert j_i^0(t) \rvert m \rangle \langle m \lvert j_k^0(t') \rvert n \rangle = e^{i (\epsilon_n -\epsilon_m)t - i (\epsilon_n-\epsilon_m )t'} \langle n \lvert j_i^0 \rvert m \rangle \langle m \lvert j_k^0 \rvert n \rangle. $$

We additionally need to take into account the form of $$A_k(t')$$, so the relevant integral becomes

$$ \int_{-\infty}^t e^{-i(\omega + \epsilon_n - \epsilon_m + i \delta) t'} dt' = \frac{e^{-i(\omega + \epsilon_n - \epsilon_m)t}}{-i(\omega + \epsilon_n - \epsilon_m + i \delta)}, $$

where $$\delta>0$$ is a small number introduced for convergence (takes care of distributional issues). 
Thus, we can write the current as

$$
J_i(t) = \sum_{n,m} \frac{f(\epsilon_n) - f(\epsilon_m)}{\omega + \epsilon_n - \epsilon_m + i \delta} j^0_{i,nm} j^0_{k,mn} A_k(\omega) e^{-i \omega t},
$$

and from that we deduce that

$$
\sigma_{ik}(\omega) = \frac1{i(\omega+i\delta)} \sum_{n,m} \frac{f(\epsilon_n) - f(\epsilon_m)}{\omega + \epsilon_n - \epsilon_m + i \delta} j^0_{i,nm} j^0_{k,mn} .
$$

The $$\omega + i \delta$$ that divides this quantity comes from changing $$ A(\omega) \rightarrow E(\omega)$$.
Additionally, the $$i \delta$$ comes from the same place the other $$i\delta$$ comes from.

Now, there is clearly a singularity in this expression at zero frequency, so we'd like to isolate out this singularity. To do so, we return to the time domain

$$
\sigma_{ik}(t) = \int d\omega \, \sigma_{ik}(\omega) e^{-i \omega t}.
$$

Doing so produces the expression

$$
\begin{multline}
\sigma_{ik}(t) = \theta(t)\left[ 2\pi \sum_{n\neq m} \frac{f(\epsilon_n) - f(\epsilon_m)}{\epsilon_n - \epsilon_m } j^0_{i,nm} j^0_{k,mn}  \right. \\ \left. - 2 \pi \sum_{n\neq m} \frac{f(\epsilon_n) - f(\epsilon_m)}{\epsilon_n - \epsilon_m } j^0_{i,nm} j^0_{k,mn} e^{i(\epsilon_n - \epsilon_m) t} \right]
\end{multline}
$$

Note that the use of $\omega \rightarrow \omega + i \delta$ has enforced casuality.

We can now go back a step to write our conductivity in terms of a part singular at $$\omega = 0$$ and a part that's regular:

$$
\sigma_{ik}(\omega) = \sigma_{ik,\mathrm{sing}}(\omega) + \sigma_{ik,\mathrm{reg}}(\omega)
$$

where

$$
\sigma_{ik,\mathrm{sing}} =  \frac{1}{i(\omega+i\delta)} \sum_{n\neq m} \frac{f(\epsilon_n) - f(\epsilon_m)}{\epsilon_n - \epsilon_m } j^0_{i,nm} j^0_{k,mn} ,
$$

and

$$
\sigma_{ik,\mathrm{reg}}(\omega) = i \sum_{n\neq m} \frac1{\epsilon_n-\epsilon_m}\frac{f(\epsilon_n) - f(\epsilon_m)}{\omega + \epsilon_n - \epsilon_m + i \delta} j^0_{i,nm} j^0_{k,mn}.
$$