---
layout: post
title: Optical reflection off of a 2D sheet
published: false
---

One type of popular experiment used to probe some material properties is optical experiments. The idea is simple: Put up a piece of material, send in light with some polarization and see how it is reflected and how it is transmitted. You can ask: How does the polarization change? How much gets transmitted? And these questions can lead to some profound insights into the nature of a material.

For instance, by probing the optical Kerr effect, a fancy name for just seeing how the angle of a reflected wave changes, one can determine if a material is time-reversal invariant (in short: hosts some internal magnetization). Similar data is found by looking at the transmitted wave (the Faraday effect).

In this post, I will derive some simple relations for how a 2D sheet with some optical linear response reflects and transmitts light incident on it. A good reference for some of the gory details of the general case is found in [this paper by Tse and MacDonald][1].

For the material, we will assume it is at $$z=0$$ and has a current response $$\mathbf{J} = \sigma \mathbf{E} \delta(z)$$ where

$$\sigma = \begin{pmatrix} \sigma_{xx} & \sigma_{xy} \\ \sigma_{yx} & \sigma_{yy} \end{pmatrix}$$

is the conductivity matrix solely in the xy-plane ($$\sigma_{zz} = 0$$). The place to begin for these calculations is at Maxwell equations. Using Gaussian units and setting $$c=1$$ for simplicity, we use the fact that there is no charge build-up to write

$$ 
\begin{align} 
\nabla \cdot \mathbf{E} & = 0 & \nabla \times \mathbf{B} - \partial_t \mathbf{E} & = 4 \pi \mathbf{J} \\
\nabla \cdot \mathbf{B} & = 0 & \nabla \times \mathbf{E} + \partial_t \mathbf{B} & = 0
\end{align}
$$

First, the free space solutions (when $$\mathbf J = 0$$) have $$\mathbf E = \mathbf E_0 e^{i \mathbf k \cdot \mathbf x - i \omega t}$$ with $$\omega = \lvert \mathbf k\rvert$$. By $$\nabla \cdot \mathbf E=0$$ we have $$\mathbf E_0 \cdot \mathbf k = 0$$ and by $$\nabla \times \mathbf{E} + \partial_t \mathbf{B} = 0$$, we have $$\mathbf B = \tfrac{\mathbf k}\omega \times \mathbf{E_0} e^{i \mathbf k \cdot \mathbf x - i \omega t}$$. This will be true for reflected and transmitted waves as well.

Now assume that we have a wave incident on the plate coming from $$z=-\infty$$, so $$\mathbf k$$ has $$k_z>0$$, then the electric field can be broken up into the incident wave $$\mathbf E_0$$ and reflected wave $$\mathbf{E}_r$$ with $$\mathbf k' = (k_x,k_y,-k_z)$$ as

$$ \mathbf E = \mathbf E_0 e^{i \mathbf k \cdot \mathbf x - i \omega t} + \mathbf{E}_r e^{i \mathbf k' \cdot \mathbf x - i \omega t}, \quad z < 0.$$

And the transmitted wave will have wave vector $$\mathbf k'' = \mathbf k$$ by virtue of the fact that $$k_x, k_y$$ and $$\omega$$ must be the same by the Maxwell equations (enforced by orthogonality of the functions $$e^{i\mathbf k \cdot x - i \omega t}$$ across the $$z=0$$ boundary and knowledge that there is only an incident wave coming from $$z=-\infty$$, ruling out a $$k_z''<0$$ situation). This situation is a special case, and will _not_ be the case for a bulk material with any kind of electromagnetic response! In those cases, the dispersion could not be $$\omega = \lvert \mathbf k \rvert$$.

Thus for the case of a vacuum for $$z>0$$, we have

$$ \mathbf E = \mathbf E_t e^{i \mathbf k \cdot \mathbf x - i \omega t} , \quad z>0. $$

Now, we need to satisfy Maxwell's equations across the boundary. $$\nabla \cdot \mathbf{E} = 0$$ and $$\nabla \times \mathbf{E} + \partial_t \mathbf{B} = 0$$ imply that both the normal and tangential part of $$\mathbf{E}$$ (respectively) are continuous across the boundary so we have

$$ \mathbf{E}_0 + \mathbf{E}_r - \mathbf{E}_t = 0. $$

The more interesting equation comes from $$\nabla \times \mathbf{B} - \partial_t \mathbf{E}  = 4 \pi \mathbf{J}$$. If we draw a contour (INSERT FIG) and integrate the above about that contour, we get

$$ \mathbf{e}_1 \cdot( \mathbf{B}_2 - \mathbf{B}_1 ) = 4 \pi \mathbf{e}_2 \cdot \sigma \mathbf{E}_t.$$

If we insert how $$\mathbf{B}$$ is related to $$\mathbf{E}$$ we get

$$ \mathbf{e}_1 \cdot( \mathbf{k} \times \mathbf{E}_t -  \mathbf{k} \times \mathbf{E}_0 -  \mathbf{k}' \times \mathbf{E}_r) = 4 \pi \omega (\hat{\mathbf{z}} \times \mathbf{e}_1) \cdot \sigma \mathbf{E}_t$$

where I have also used $$\mathbf{e}_2 = \mathbf{z} \times \mathbf{e}_1$$. We can further use the cyclic nature of the triple product (i.e. $$\mathbf{A} \cdot (\mathbf{B} \times \mathbf{C}) = \mathbf{C} \cdot (\mathbf{A} \times \mathbf{B}) $$), and the fact that $$\mathbf{e}_1$$ can be either $$\mathbf{x}$$ or $$\mathbf{y}$$.

$$\hat{\mathbf{z}}\times (\mathbf{k} \times \mathbf{E}_t -  \mathbf{k} \times \mathbf{E}_0 -  \mathbf{k}' \times \mathbf{E}_r) = 4 \pi \omega \sigma \mathbf{E}_t$$

At this point, we need to pick polarizations

[1]: http://dx.doi.org/10.1103/PhysRevB.84.205327