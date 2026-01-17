> Ce fichier contiendra des formules diverses, si je ressens le besoin de les numériser.

# Opérations vectorielles
> Le produit scalaire( $.$) et vectoriel ($\wedge$) sont considérés comme acquis.

> On rappele que l'**angle solide** (angle 3d, stéradians) s'écrit $\Omega$.

<u>En base cartésienne:</u>

- Distributivité vectorielle:

$$
\vec{u}\wedge(\vec v\wedge \vec{w})=(\vec{u}\cdot \vec{w})\vec{v}-(\vec{u}\cdot\vec{v})\vec{w}
$$

- Nabla: 

$$
\vec \nabla=
\begin{pmatrix}
    \frac{\partial}{\partial x}\\
    \frac{\partial}{\partial y}\\
    \frac{\partial}{\partial z}
\end{pmatrix}
$$

- **Gradient:** $\displaystyle \overrightarrow{grad}(u)=\vec{\nabla}u=\frac{\partial u}{\partial x}\vec{u_x}+\frac{\partial u}{\partial y}\vec{u_y}+\frac{\partial u}{\partial z}\vec{u_z}$

- **Divergence:** $\displaystyle div(\vec{a})=\vec{\nabla}\cdot \vec{a}=\frac{\partial a_x}{\partial x}+\frac{\partial a_y}{\partial y}+\frac{\partial a_z}{\partial z}$

- **Rotationnel:** 

$$ \overrightarrow{rot}(\vec{a})=\vec{\nabla}\wedge\vec{a}=
\begin{pmatrix}
    \partial y a_z-\partial za_y\\
    \partial za_x-\partial xa_z\\
    \partial xa_y-\partial ya_x
\end{pmatrix}
$$

- **Laplacien:** $\displaystyle \Delta u=\vec{\nabla}\cdot \vec{\nabla}u= \frac{\partial^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}+\frac{\partial^2 u}{\partial z^2}$ *Seul applicable sur un scalaire ou vecteur*

<u>Propriétés d'association:</u>

$$
div(\overrightarrow{grad}(u))=\vec{\nabla}\cdot \vec{\nabla} u=\Delta u
$$
$$
\overrightarrow{rot}(\overrightarrow{grad}(u))=\vec{0}
$$
$$
div(\overrightarrow{rot}(a))=0
$$
$$
\overrightarrow{rot}\cdot \overrightarrow{rot}(a)=\overrightarrow{grad}(div(\vec{a}))-\Delta \vec{a}
$$