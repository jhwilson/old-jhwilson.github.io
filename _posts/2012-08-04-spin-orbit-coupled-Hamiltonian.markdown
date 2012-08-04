---
layout: post
title: Spin-orbit coupled Hamiltonian
---

For applications in many parts of condensed matter physics and cold atoms physics, we use what is known as the spin-orbit coupled Hamiltonian. This Hamiltoninan is so-named because it couples momentum <span>\(\mathbf{p}\)</span>
to the spin <span>\(\mathbf{S}=\frac12\sigma\)</span>

<div>
\[ H = \frac{p^2}{2m} + \alpha (\boldsymbol{\sigma} \times \mathbf{p})\cdot \hat{\mathbf{z}} + \Delta \sigma_z. \]
</div>

In this post, we go through the calculation of the energy spectrum and eigenvectors. 

First of all, instead of the normal method of finding eigenvectors, we note that we can rewrite this Hamiltonian in the form

<div>
\[ H = \frac{p^2}{2m} + \mathbf{b}(p) \cdot \boldsymbol{\sigma} \]
</div>

where <span>\(\mathbf{b}(p) = (\alpha p_y, -\alpha p_x, \Delta)\)</span>. Now, <span>\(\mathbf{b}(p)\)</span> represents a point on the Bloch sphere, and so we expect the eigenvectors to be parallel and anti-parallel to this vector. The energies in this case are very straight forward and amount to the positive and negative of <span>\(|\mathbf{b}(p)|\)</span>:

<div>
\[ \epsilon_\pm(p) = \frac{p^2}{2m} \pm \sqrt{ \alpha^2 p^2 + \Delta^2}. \]
</div>

With these eigenvalues, it is a straight forward exercise in linear algebra to find the eigenvectors. After a bit of algebra, the eigenvectors of <span>\(H\)</span> in terms of the eigenvectors of <span>\(\sigma_z\)</span> (<span>\(\sigma_z\left|\uparrow\right\rangle = \left|\uparrow\right\rangle\)</span> and <span>\(\sigma_z\left|\uparrow\right\rangle = -\left|\uparrow\right\rangle\)</span>) are

<div>
\[\left|\pm\right\rangle = \frac1{\sqrt2}\left[\sqrt{1 \pm \frac{\delta}{\sqrt{1+\delta^2}}}\left|\uparrow\right\rangle + e^{-i\phi} \sqrt{1 \mp \frac{\delta}{\sqrt{1+\delta^2}}}\left|\downarrow\right\rangle \right]\]
</div>

where we have defined <span>\(\delta = \Delta/\alpha p\)</span> and <span>\(\phi\)</span> by <span>\(p_y+ip_x = p e^{i\phi})</span>. Note what happens when <span>\(p_{x,y} \rightarrow -p_{x,y}\)</span> the occupations stay the same. However, if we just look at one energy, <span>\(\epsilon_-(p)\)</span> the ground state energy, we see that the state we get when <span>\(p_{x,y} \rightarrow -p_{x,y}\)</span> is almost orthogonal to the original state. 

[This post will be updated later with figures.]