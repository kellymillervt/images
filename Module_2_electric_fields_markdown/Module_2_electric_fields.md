---
title: "Module 2: Electric Fields"
source_pdf: "module 2_electric fields.pdf"
image_base_url: "https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images"
---

<!--
IMAGES:
This lesson expects the images to live at:

https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/<filename>

If you move the images, update `image_base_url` above accordingly.
-->

# Chapter 5: Electric Charges and Fields (continued)

## 5.4 Electric Field

### Learning Objectives
By the end of this section, you will be able to:
- Explain the purpose of the electric field concept
- Describe the properties of the electric field
- Calculate the field of a collection of source charges of either sign

As we showed in the preceding section, the net electric force on a test charge is the vector sum of all the electric forces acting on it from the various *source* charges. But what if we use a different test charge (different magnitude and/or sign), or we want to know the force on many different test charges at the same location? Recomputing forces each time is inefficient.

Instead, we define a quantity that depends **only** on the source charges (not on the test charge): the **electric field**.

### Defining a field

Suppose we have $N$ source charges $q_i$ located at position vectors $\mathbf{r}_i$. We want the net force on a test charge $Q$ located at position $\mathbf{r}$.

For each source charge, define the displacement vector from $q_i$ to $Q$:
$$
\mathbf{R}_i = \mathbf{r} - \mathbf{r}_i, \qquad R_i = |\mathbf{R}_i|, \qquad \hat{\mathbf{R}}_i = \frac{\mathbf{R}_i}{R_i}.
$$

The force on $Q$ due to $q_i$ is
$$
\mathbf{F}_i
= \frac{1}{4\pi\varepsilon_0}\,\frac{Q\,q_i}{R_i^2}\,\hat{\mathbf{R}}_i.
$$

By superposition, the net force is
$$
\mathbf{F}_\text{net}
= \sum_{i=1}^N \mathbf{F}_i
= \frac{1}{4\pi\varepsilon_0} \sum_{i=1}^N \frac{Q\,q_i}{R_i^2}\,\hat{\mathbf{R}}_i.
\tag{5.3}
$$

Factor out $Q$:
$$
\mathbf{F}_\text{net} = Q\,\mathbf{E}(\mathbf{r}),
$$
which motivates the definition of the **electric field**:
$$
\boxed{
\mathbf{E}(\mathbf{r})
= \frac{1}{4\pi\varepsilon_0} \sum_{i=1}^N \frac{q_i}{R_i^2}\,\hat{\mathbf{R}}_i
}
\tag{5.4}
$$

Equivalently, using $\hat{\mathbf{R}}_i = \mathbf{R}_i/R_i$, we can write
$$
\mathbf{E}(\mathbf{r})
= \frac{1}{4\pi\varepsilon_0} \sum_{i=1}^N q_i\,\frac{\mathbf{r}-\mathbf{r}_i}{|\mathbf{r}-\mathbf{r}_i|^3}.
$$

**FIGURE 5.18** Each source charge produces its own electric field at point $P$; the net field is their vector sum (superposition).  
![FIGURE 5.18]( https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/p02_img01_20.jpg )

### Example 5.3: The Electric Field of a Helium Nucleus

A helium nucleus has charge $q = +2e$ and an electron is at distance $r = 26.5\times 10^{-12}\,\text{m}$. The field magnitude is
$$
E = \frac{1}{4\pi\varepsilon_0}\,\frac{|q|}{r^2}
= k\,\frac{2e}{r^2}.
$$
Using $k=8.988\times 10^9\,\text{N·m}^2/\text{C}^2$ and $e=1.602\times 10^{-19}\,\text{C}$ gives
$$
E \approx 4.10\times 10^{12}\,\text{N/C},
$$
directed radially **away** from the positive nucleus.

### Example 5.4: Electric Field Above Two Charges

Two charges are separated by distance $d$ on the $x$-axis, with a field point located at height $z$ above the midpoint (on the $z$-axis).

Let $r = \sqrt{z^2 + (d/2)^2}$ be the distance from either charge to the field point.

#### (a) Two equal charges: $+q$ and $+q$

The horizontal ($x$) components cancel by symmetry; the vertical components add:
$$
E_z = 2\left( \frac{1}{4\pi\varepsilon_0}\frac{q}{r^2}\right)\cos\theta
= 2\left( \frac{1}{4\pi\varepsilon_0}\frac{q}{r^2}\right)\frac{z}{r}.
$$
So,
$$
\boxed{
\mathbf{E}(z)
= \frac{1}{4\pi\varepsilon_0}\,\frac{2qz}{\left(z^2+(d/2)^2\right)^{3/2}}\,\hat{\mathbf{k}}
}
\tag{5.5}
$$

#### (b) Two equal and opposite charges: $+q$ and $-q$

Now the vertical components cancel, while the horizontal components add:
$$
\boxed{
\mathbf{E}(z)
= \frac{1}{4\pi\varepsilon_0}\,\frac{qd}{\left(z^2+(d/2)^2\right)^{3/2}}\,\hat{\mathbf{i}}
}
\tag{5.6}
$$

For $z \gg d$, we can approximate $\left(z^2+(d/2)^2\right)^{3/2}\approx z^3$, giving the far-field dipole scaling:
$$
\boxed{
\mathbf{E}(z) \approx \frac{1}{4\pi\varepsilon_0}\,\frac{qd}{z^3}\,\hat{\mathbf{i}}
}
\tag{5.7}
$$

---

## 5.5 Calculating Electric Fields of Charge Distributions

### Learning Objectives
By the end of this section, you will be able to:
- Explain what a continuous source charge distribution is and how it is related to discrete source charges
- Describe line, surface, and volume charge densities
- Calculate the field of a continuous source charge distribution

When many charges are very closely spaced, it is convenient to treat charge as a continuous distribution.

### Charge density
- **Line charge density:** $\lambda = \dfrac{dq}{dl}$  (C/m)
- **Surface charge density:** $\sigma = \dfrac{dq}{dA}$ (C/m$^2$)
- **Volume charge density:** $\rho = \dfrac{dq}{dV}$ (C/m$^3$)

### From sums to integrals
For a discrete set of charges:
$$
\mathbf{E}(\mathbf{r}) = \frac{1}{4\pi\varepsilon_0}\sum_i \frac{q_i}{r_i^2}\,\hat{\mathbf{r}}_i.
\tag{5.8}
$$

For continuous distributions, replace $q_i \to dq$ and the sum by an integral:

**Line charge:**
$$
\mathbf{E}(\mathbf{r})=\frac{1}{4\pi\varepsilon_0}\int_\text{line} \frac{\lambda\,dl}{r^2}\,\hat{\mathbf{r}}.
\tag{5.9}
$$

**Surface charge:**
$$
\mathbf{E}(\mathbf{r})=\frac{1}{4\pi\varepsilon_0}\int_\text{surface} \frac{\sigma\,dA}{r^2}\,\hat{\mathbf{r}}.
\tag{5.10}
$$

**Volume charge:**
$$
\mathbf{E}(\mathbf{r})=\frac{1}{4\pi\varepsilon_0}\int_\text{volume} \frac{\rho\,dV}{r^2}\,\hat{\mathbf{r}}.
\tag{5.11}
$$

### Example 5.5: Field on the Axis of a Finite Line Segment

A uniformly charged line segment of length $L$ lies along the $x$-axis from $-L/2$ to $+L/2$ with line density $\lambda$. Find the field at point $P$ a distance $z$ above the midpoint (on the $z$-axis).

By symmetry, horizontal components cancel and only $E_z$ remains:
$$
dE_z = \frac{1}{4\pi\varepsilon_0}\frac{\lambda\,dx}{r^2}\cos\theta
= \frac{1}{4\pi\varepsilon_0}\frac{\lambda\,dx}{(x^2+z^2)}\frac{z}{\sqrt{x^2+z^2}}
= \frac{1}{4\pi\varepsilon_0}\,\lambda z\,\frac{dx}{(x^2+z^2)^{3/2}}.
$$

Integrating from $-L/2$ to $+L/2$:
$$
\boxed{
\mathbf{E}(z)=\frac{1}{4\pi\varepsilon_0}\,\frac{\lambda L}{z\sqrt{z^2+(L/2)^2}}\,\hat{\mathbf{k}}
}
\tag{5.12}
$$

### Example 5.6: Field of an Infinite Line of Charge

Let the line be infinite with density $\lambda$. At perpendicular distance $z$ from the line:
$$
\boxed{
E(z)=\frac{1}{2\pi\varepsilon_0}\,\frac{\lambda}{z}
}
\tag{5.13}
$$
The field points radially away from the line if $\lambda>0$ (toward it if $\lambda<0$).

### Example 5.7: Field on the Axis of a Charged Ring

For a ring of radius $R$ with total charge $q$ (uniformly distributed), the field on the symmetry axis at height $z$ is
$$
\mathbf{E}(z)=\frac{1}{4\pi\varepsilon_0}\,\frac{qz}{(z^2+R^2)^{3/2}}\,\hat{\mathbf{k}}.
$$

### Example 5.8: Field on the Axis of a Uniformly Charged Disk

For a disk of radius $R$ with uniform surface charge density $\sigma$, the field on the axis a distance $z$ from the center is
$$
\boxed{
\mathbf{E}(z)=\frac{\sigma}{2\varepsilon_0}\left(1-\frac{z}{\sqrt{z^2+R^2}}\right)\hat{\mathbf{k}}
}
\tag{5.14}
$$

### Field of an Infinite Plane of Charge

Taking the limit $R\to\infty$ of the disk gives the field magnitude above an infinite sheet:
$$
\boxed{
E=\frac{\sigma}{2\varepsilon_0}
}
\tag{5.15}
$$
The direction is perpendicular to the plane (away from the plane for $\sigma>0$).

### Example 5.9: Two Infinite Parallel Sheets

Two infinite sheets carry equal and opposite surface charge densities $+\sigma$ and $-\sigma$. The fields cancel **outside** and add **between** the sheets:
$$
E_\text{between}=\frac{\sigma}{\varepsilon_0}.
$$

---

## 5.6 Electric Field Lines

### Learning Objectives
By the end of this section, you will be able to:
- Explain the purpose of an electric field diagram
- Describe the relationship between field lines and forces
- Construct diagrams of simple charge distributions

Electric field lines are a visualization tool:
- Field lines point in the direction a positive test charge would accelerate.
- The density of lines indicates relative field magnitude.
- Lines begin on positive charge and end on negative charge (or at infinity).
- Lines never cross.

**FIGURE 5.27** Electric field lines for various charge configurations.  
![FIGURE 5.27]( https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/p16_img01_113.jpg )

**FIGURE 5.28** Field lines for two equal charges (repulsion).  
![FIGURE 5.28]( https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/p17_img01_120.jpg )

**FIGURE 5.29** Field lines for two opposite charges (dipole-like).  
![FIGURE 5.29]( https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/p17_img02_121.jpg )

**FIGURE 5.30** Field lines for a charged conducting sphere.  
![FIGURE 5.30]( https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/p18_img01_128.jpg )

**FIGURE 5.31** Field lines for a charged parallel-plate setup.  
![FIGURE 5.31]( https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/p19_img01_136.jpg )

---

## 5.7 Electric Dipoles

### Learning Objectives
By the end of this section, you will be able to:
- Define the electric dipole moment
- Calculate the torque on an electric dipole in an electric field
- Describe the behavior of dipoles in uniform and nonuniform fields

An **electric dipole** consists of two equal and opposite charges $+q$ and $-q$ separated by vector displacement $\mathbf{d}$ (from $-q$ to $+q$).

### Dipole moment
The **dipole moment** is
$$
\boxed{\mathbf{p} = q\,\mathbf{d}}
\tag{5.16}
$$
It points from the negative charge toward the positive charge.

**FIGURE 5.32** Definition of the dipole moment vector.  
![FIGURE 5.32]( https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/p20_img01_145.jpg )

### Torque in a uniform electric field
In a uniform external field $\mathbf{E}$, the net force on an ideal dipole is zero, but the dipole generally experiences a **torque** that tends to align $\mathbf{p}$ with $\mathbf{E}$:
$$
\boxed{\boldsymbol{\tau} = \mathbf{p}\times \mathbf{E}}
\tag{5.17}
$$

**FIGURE 5.33** A dipole in a uniform electric field experiences a torque.  
![FIGURE 5.33]( https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/p21_img01_151.jpg )

### Far-field dipole scaling (connection to Eq. 5.7)

In the geometry of Eq. (5.7), the far-field dipole strength can be written in terms of $\mathbf{p}$:
$$
\mathbf{E}(z) \approx \frac{1}{4\pi\varepsilon_0}\,\frac{p}{z^3}\,\hat{\mathbf{i}}.
$$

**FIGURE 5.34** Dipole in a nonuniform field (net force can appear if $\mathbf{E}$ changes in space).  
![FIGURE 5.34]( https://raw.githubusercontent.com/kellymillervt/images/main/Module_2_electric_fields_markdown/images/p21_img02_152.jpg )
