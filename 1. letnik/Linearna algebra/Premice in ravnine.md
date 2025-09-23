```table-of-contents
title: # Kazalo
style: nestedOrderedList
```

---
# Premice in ravnine v $\Bbb R^{3}$
## Premice
$$p: \left[\begin{array} {}x_{0}\\y_{0}\\z_{0} \end{array}\right]+t\left[\begin{array}{}s_{1}\\ s_{2}\\ s_{3}\end{array}\right];\ t\in\Bbb R$$
- *Točka ki leži na premici* -> $T(x_{0},y_{0},z_{0})$
- *Smerni [[Vektorji v R|vektor]]* -> $\vec s$
- **Drugačen zapis:**
	- $\frac{x-x_{0}}{s_{1}}=\frac{y-y_{0}}{s_{2}}=\frac{z-z_{0}}{s_{3}}$
	- $x=x_{0}+s_{1}*t;\ y=y_{0}+s_{2}*t;\ z=z_{0}+s_{3}*t$
## Ravnine
$$ax+by+cz=d$$
- Točka v ravnini -> $T(x,y,z)$
- **Norma ravnine** (vektor pravokoten na ravnino) -> $\vec n=\left[\begin{array}{}a\\ b\\ c\end{array}\right]$
	- $\vec n=\vec a\times\vec b;\ \vec a,\vec b\subset\Pi$
- $d=\left<\vec{0T},\vec n\right>$

---
# Razdalje med objekti v $\Bbb R^3$ 
## Med dvema točkama
$$d=\|\vec{AB}\|=\sqrt{\left<\vec{AB},\vec{AB}\right>}$$
## Med točko in premico
$$d=\frac{\|\vec s\times\vec{AT}\|}{\|\vec s\|}$$
## Med dvema premicama
$$d=\frac{|[\vec s_{1},\vec s_{2},\vec{T_{1}T_{2}}]|}{\|\vec s_{1}\times\vec s_{2}\|}$$
- Če sta premici vzporedni je $\vec s_{1}\times\vec s_{2}=\vec 0$. Tako zračunamo razdaljo poljubne točke ene premice na drugo.
## Med točko in ravnino
$$d=\frac{\left|\left<\vec{AT}, \vec n\right>\right|}{\|\vec n\|}$$
## Med premico in ravnino
$$x=\left<\vec s, \vec n\right>$$
1. $x\not=0$ -> Premica seka ravnino, razdalja je $0$
2. $x=0$ -> Premica je vzporedna z ravnino, zračunamo z točko na premici
## Med dvema ravninama
$$x=\vec n_{1}\times\vec n_{2}$$
1. $x\not=0$ -> Ravnini se sekata, razdalja je 0
2. $x=0$ -> Razdalja med točko prve ravnine in druge ravnino