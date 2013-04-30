---
layout: post
title: Spin-orbit coupled Hamiltonian
---

For applications in many parts of condensed matter physics and cold atoms physics, we use what is known as the spin-orbit coupled Hamiltonian. This Hamiltoninan is so-named because it couples momentum $$\mathbf{p}$$
to the spin $$\mathbf{S}=\frac12\sigma$$.

$$ H = \frac{p^2}{2m} + \alpha (\boldsymbol{\sigma} \times \mathbf{p})\cdot \hat{\mathbf{z}} + \Delta \sigma_z. $$

In this post, we go through the calculation of the energy spectrum and eigenvectors. 

First of all, instead of the normal method of finding eigenvectors, we note that we can rewrite this Hamiltonian in the form

$$ H = \frac{p^2}{2m} + \mathbf{b}(p) \cdot \boldsymbol{\sigma} $$

where $$\mathbf{b}(p) = (\alpha p_y, -\alpha p_x, \Delta)$$. Now, $$\mathbf{b}(p)$$ represents a point on the Bloch sphere, and so we expect the eigenvectors to be parallel and anti-parallel to this vector. The energies in this case are very straight forward and amount to the positive and negative of $$\lvert\mathbf{b}(p)\rvert$$:

$$ \epsilon_\pm(p) = \frac{p^2}{2m} \pm \sqrt{ \alpha^2 p^2 + \Delta^2}. $$

With these eigenvalues, it is a straight forward exercise in linear algebra to find the eigenvectors. After a bit of algebra, the eigenvectors of $$H$$ in terms of the eigenvectors of $$\sigma_z$$ ( $$\sigma_z\left\lvert\uparrow\right\rangle = \left\lvert\uparrow\right\rangle$$ and $$\sigma_z\left\lvert\uparrow\right\rangle = -\left\lvert\uparrow\right\rangle$$ ) are

$$\left\lvert\pm\right\rangle = \frac1{\sqrt2}\left[\sqrt{1 \pm \frac{\delta}{\sqrt{1+\delta^2}}}\left\lvert\uparrow\right\rangle + e^{-i\phi} \sqrt{1 \mp \frac{\delta}{\sqrt{1+\delta^2}}}\left\lvert\downarrow\right\rangle \right]$$

where we have defined $$\delta = \Delta/\alpha p$$ and $$\phi$$ by $$p_y+ip_x = p e^{i\phi}$$. Note what happens when $$p_{x,y} \rightarrow -p_{x,y}$$ the occupations stay the same. However, if we just look at one energy, $$\epsilon_-(p)$$ the ground state energy, we see that the state we get when $$p_{x,y} \rightarrow -p_{x,y}$$ is almost orthogonal to the original state. 

[This post will be updated later with figures.]