---
layout: post
title: Quenching the low-energy Haldane model
published: false
---

If we think about current response in a free-fermion system, certain models with time-reversal symmetry breaking should experience some sort of Hall current: When a voltage is applied, there is a perpendicular current that occurs.

This is classically known as the [Hall effect][1], and quantum mechanically it can lead to a [quantized Hall conductance][2]. Leaving aside issues of disoder, we will focus on the free case here.

A model which shows an "anomalous" Hall effect (i.e. a Hall effect without an applied magnetic field) is what we will refer to as the Haldane model, 

$$ H = v_{\mathrm F} \mathbf p \cdot \sigma + \Delta \sigma_z. $$

Strictly speaking this is only half of the (low-energy) Haldane model, but we will focus on it due to its relevance in other cases like the surface of topological insulators.

We will write the eigenstates of this system in terms of their place on the Bloch sphere

$$ \left\lvert \psi_0 \right\rangle = \cos \tfrac\theta2 \left\lvert \uparrow \right\rangle - e^{i \phi} \sin\tfrac\theta 2\left\lvert \downarrow \right\rangle $$

where

$$ \begin{align} \cos \theta & = - \frac{\Delta}{\sqrt{\Delta^2 + (v_{\mathrm F} p)^2}}, &   p_x + i p_y & = e^{i\phi} p.
\end{align}$$

If we start out in this state, we now want to find the conductivity response in time. To accomplish this, we use the Kubo formula from the time-dependent perturbation theory using the current operator $$j_\mu = -e v_{\mathrm F} \sigma_\mu$$

$$\begin{align}
  \sigma_{xy}(t_2,t_1) = -i e^2 v_{\mathrm F}^2 \int_{t_1}^{t_2}dt\, \langle[\sigma_{x}(t_2), \sigma_y(t)] \rangle.
\end{align}$$

where $$\langle \cdots \rangle$$ is the expectation value over a state or set of (occupied) states. 

    

[1]: https://en.wikipedia.org/wiki/Hall_effect
[2]: https://en.wikipedia.org/wiki/Quantum_Hall_effect#Integer_quantum_Hall_effect_.E2.80.93_Landau_levels