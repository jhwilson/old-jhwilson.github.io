---
layout: post
title: Subtleties in linear response theory
published: false
---

In linear response theory, we consider some small perturbation to a Hamiltonian and consider on the response of some observable to that perturbation. In the case considered here, the perturbation is an electric field, and the response is current. The linear response that characterizes these quantities is called the conductance.

There's a problem though, an electric field _accelerates_ a charge. Consider a classical electron for the time being, then

$$ m \ddot x(t) = - e \mathbf{E}. \label{eq:Newton}$$

Or in terms of current $$j(t) = -e \dot x(t)$$, $$ \frac{d j}{dt} = \frac{e^2}{m} \mathbf{E} $$. From here we can quickly and naively go to frequency space to find $$ j(\omega) = i \frac{e^2/m}{\omega} \mathbf{E}(\omega) $$. Then one might remember that another way to define $$\mathbf{E}$$ is in terms of a vector potential that is purely time-dependent, so $$\mathbf{E}(\omega) = i \omega \mathbf A(\omega)$$. Now, if we just plug this into our linear response for the current, we get

$$ j(\omega) = - \frac{ e^2}{m} \mathbf A(\omega). \label{eq:jA} $$

All is well and good, right? Well, not quite. In electromagnetism, the constant part of $$\mathbf A(t)$$ corresponds to the $$\omega = 0$$ term of $$A(\omega)$$. This represents what is known as a "pure gauge". These gauges are _physically equivalent_ to the null field $$\mathbf A(\omega=0) = 0$$. Thus, whatever linear response is represented above at $$\omega = 0$$ must be unphysical, right? 

Wrong.

Before explainging why this is wrong, let's give some further context to this linear response theory. The term $$- e^2/m$$ is actually the single particle term of what is known as the "diamagnetic" response to the conductivity when you add in more electrons (usually distributed in a Fermi distribution). This term persists in quantum mechanics, and no other terms appear to cancel it in the simplest case of $$ H = \frac{p^2}{2m} $$. In fact, while the math becomes more cumbersome, the solution we shall illustate below holds perfectly well for even the multi-electron system.

Now, at this point you may have guessed that there's something strange going on at $$\omega = 0$$ due to the fact that the electric field _accelerates_ the particle and doesn't just have a velocity response. At the $$\omega = 0$$ point, the _physical_ field $$E(\omega)$$ seems to necessarily be equal to zero in the gauge we have prescribed unless $$A(\omega) \sim 1/\omega $$ for small $$\omega$$. This would lead to a divergent $$j(\omega)$$, restoring our faith that the system is accelerating out of control.

But what about when $$\mathbf{A}(\omega=0) = \mathbf{A}_0$$? It seems like then we have a true velocity response to an unphysical object. The solution is subtle: At some point in the quick derivation we made an assumption that implied $$\mathbf A(t) \rightarrow 0 $$ at $$ t \rightarrow -\infty$$. This implies that if $$\mathbf A(t) = \mathbf A_0$$ at any finite time, there had to be some time in between where $$d\mathbf A/ dt \neq 0$$. Thus, during that "ramp up" time, an electric field was on and it accelerated the charge to a specific velocity resulting in the current $$j(\omega) = - \frac{ e^2}{m} \mathbf A(\omega)$$.

The assumption is subtle, but the result is rather simple. For now, just assume that $$\mathbf A(-\infty) = 0 $$ and at some $$t_0$$, $$\mathbf A(t_0) = \mathbf A_0$$, then we can integrate Eq. (\ref{eq:Newton}) to obtain the velocity:

$$ m \dot x (t_0) =  e \int_{-\infty}^{t_0} \frac{d \mathbf A}{d t} d t = e \mathbf A_0. $$

Or, in other words, $$\mathbf j(t_0) = -\frac{e^2}{m} \mathbf A_0$$, the same as before! This is how a constant $$\mathbf A_0$$ can be physical: When it represents the change from a different constant vector potential.

Now, to isolate the assumption, let us run through what they were

1. $$\frac{d j}{d t} = \frac{e^2}{m} E(t)$$.
2. Take the Fourier transform: $$ j(\omega) = i \frac{e^2/m}{\omega} E(\omega)$$.
3. Insert vector potential with $$E = -\frac{d}{dt} A$$ and _assume the Fourier transform exists_ for $$A$$: $$j(\omega) = - \frac{e^2}m A(\omega)$$.
4. Undo the Fourier transform: $$j(t) = - \frac{e^2}{m} A(t)$$.

Now, let us get the last equation (in #4 above) by a simpler route.

1. $$\frac{d j}{dt} = \frac{e^2}{m} E(t)$$.
2. Use $$E = - \frac{d}{dt} A$$ and integrate the above expression from $$-\infty$$ to $$t$$: $$j(t) - j(-\infty) = -\frac{e^2}{m} ( A(t) - A(-\infty))$$.

Two perfectly legitimate calculations resulting in different results. Firstly, this highlights that the first procedure does actually assume $$A(-\infty) = 0$$. Secondly, the only assumptions that could have given $$j(-\infty) = 0$$ (an assumption we probably wanted anyway) and $$A(-\infty) = 0$$ are that they could be given in terms of Fourier transforms. In order for a function to have a Fourier transform it needs to be _absolutely integrable_---i.e. $$ \int_{-\infty}^\infty \lvert A(t) \rvert dt < \infty$$. Given $$A(t)$$ as a continuous, piece-wise differentiable function, we need $$A(t) \rightarrow 0 $$ for $$t \rightarrow \pm \infty$$. This imposes our gauge, and since we are not interested in future times let alone $$ t \rightarrow +\infty$$, we can artificially modify the function as we see fit to accomodate that. But how the function began at $$-\infty$$ is important, and we must impose that. Hence, we have chosen, at least partially, a gauge.

We are left with a dilemma then about pure plain waves $$ A(t) = A(\omega) e^{-i \omega t}$$. How do those function?

Technically, they are outside of the bounds of the Fourier analysis and we can see that simply by the fact that if we tried to do the above procedure, we couldn't have a well defined answer as $$t \rightarrow -\infty$$ (too oscillatory). However, we can approximate the plain wave in terms of an absolutely integrable function $$ A_\delta(t) = A(\omega) e^{-i (\omega + i \delta) t}$$ for any $$\delta >0$$, and everything works. This shows us explicitly that $$t = - \infty$$ does have $$ A_\delta \rightarrow 0$$ for all $$\delta>0$$. And this is the origin of the well known substitution $$\omega \rightarrow \omega + i\delta$$.
