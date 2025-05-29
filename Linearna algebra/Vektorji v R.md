```table-of-contents
title: # Kazalo
style: nestedOrderedList
```

---
# Definicija
$\mathbb{R}^{n}=\left\{(x_{1}, x_{2},..., x_{n});\ x_{1}, x_{2},... x_{n} \in \mathbb R \land n\in \mathbb N\right\}$
- Točka v $\mathbb R^n$ ima $n$ koordinat
- *Vektor je usmerjena daljica ki je neodvisna od vzporednih premikov (tj. natanko določena s svojo smerjo in dolžino)*
- Če imata vektorja enako smer in dolžino rečemo da sta enaka
- Vsak vektor lahko premaknemo tako, da se začne v točki $0$ ($\vec{AB}=\vec{0B}-\vec{0A}$)
- Torej lahko vsak vektor podamo le z njegovo **končno točko**
- Oznaka: $\vec v, \vec x, \vec{AB}$
- Če je napisana samo 1 točka, se začne vektor v 0 ($\vec v=\left[  \begin{array} {c}a_1 \\a_2 \\\vdots \\a_n\end{array}\right]$)
- <u>Linearna kombinacija</u> -> $\alpha_{1}\vec a_{1}+\dots+\alpha_{n}\vec a_{n}$
	- Opredelimo vektor kot kombinacija drugih
	- **Linearna neodvistnost** -> Vektorji so neodvisni če ni mogoče vektor zapisati z drugim
- **Kot med vektorji**:
	- $\cos{\gamma}=\frac{\left<\vec v,\vec u\right>}{\|\vec v\|*\|\vec u\|}$
	- $\sin\gamma=\frac{\|\vec x\times\vec y\|}{\|\vec x\|*\|\vec y\|}$
	- $\cos \gamma=\frac{\left[\vec x,\vec y,\vec z\right]}{\|\vec x\times\vec y\|*\|\vec z\|}$

---
# Operacije na vektrojih
- **Seštevanje/Odštevanje** -> $\vec v\pm\vec w=\left[\begin{array} {}v_{1}\pm w_{1} \\ v_{2}\pm w_{2} \\ \vdots \\ v_{n}\pm w_{n} \end{array}\right]$
- **Množenje s skalarjem** (konstanta) -> $\alpha*\vec v=\left[\begin{array} {}\alpha*v_{1} \\ \alpha*v_{2} \\ \vdots \\ \alpha*v_{n} \end{array}\right]$
- [[#Norma]] (dolžina) vektorja -> $\|\vec v\|=\sqrt{v_{1}^{2}+v_{2}^{2}+\dots+v_{n}^{2}}$   
- [[Skalarni produkt]] vektorjev -> $\left<\vec v, \vec w\right>=v_1*w_1+...+v_n*w_n$
- [[#Vektorski produkt]] vektorjev -> $\vec v \times\vec w= \left[\begin{array} {}v_{2}w_{3}-v_{3}w_{2} \\ v_{3}w_{1}-v_{1}w_{3}  \\ v_{1}w_{2}-v_{2}w_{1} \end{array}\right]$
- [[#Mešani produkt]] ->$\left[\vec x,\vec y,\vec z\right]=\left<\vec x\times\vec y,\vec z\right>$
## Lastnosti operacij 
$$\vec a, \vec b, \vec c \in \mathbb R^{n};\ \alpha, \beta \in \mathbb R$$
1. $(\vec a+\vec b)+\vec c=\vec a +(\vec b+\vec c)$ -> Asociativnost sešt. 
2. $\vec a+\vec 0=\vec a$ -> $\vec 0$ je enota za sešt. 
3. $\vec a+(-\vec a)=\vec 0$ -> inverz za sešt. 
4. $\vec a+\vec b=\vec b+\vec a$ -> komutativnost sešt. 
5. $\alpha*(\vec a+\vec b)=\alpha*\vec a+\alpha*\vec b$
6. $(\alpha+\beta)*\vec a=\alpha*\vec a+\beta*\vec a$
7. $(\alpha*\beta)*\vec a=\alpha*(\beta*\vec a)$
8. $1*\vec a=\vec a$

---
# Norma 
$$\|\vec v\|=\sqrt{v_{1}^{2}+v_{2}^{2}+\dots+v_{n}^{2}}$$
- Dobimo dolžino vektorja
- $\vec u$ je **enotski** vektor, če je $\|\vec u\|=1$
## Lastnosti norme
1. $\|\alpha*\vec u\|=|\alpha|*\|\vec u\|$ -> absolutna homogenost 
2. $\|\vec u\|\ge 0$ -> pozitivna definiranost
	- $\|\vec u\|= 0\iff\vec u=\vec0$
3. $\|\vec u+\vec v\|\le\|\vec u\|+\|\vec v\|$ -> trikotniška neenakost

---
# Pravokotna projekcija
![[Vektorji v R 2024-10-10 11.52.13.excalidraw]]
$$\text{proj}_{\vec u}(\vec v)=\frac{<\vec u,\vec v>}{{\|\vec u\|}^{2}}*\vec u$$
- $\cos \gamma=\frac{\|proj_{\vec u}(\vec v)\|}{\vec v}$
- Pravokotna projekcija vektorja $\vec v$ na vektor $\vec u$

---
# Vektorski produkt
$$\vec v \times\vec w= \left[\begin{array} {}v_{2}w_{3}-v_{3}w_{2} \\ v_{3}w_{1}-v_{1}w_{3}  \\ v_{1}w_{2}-v_{2}w_{1} \end{array}\right]\in\Bbb R^3$$
- Delamo samo v $\Bbb R^{3}$
- Lažje zapomniti kot [[Determinante|determinanto]] $\vec z=\vec v \times\vec w=\left|\begin{matrix} \text z_{1}&\text z_{2}&\text z_{3} \\ v_{1}&v_{2}&v_{3} \\ w_{1}&w_{2}&w_{3} \end{matrix}\right|$
- Vrstni red operacij je **pomemben** -> $\vec v\times\vec w\not=\vec w\times\vec v$
- Produkt je nov vektor, ki je <u>pravokoten</u> na $\vec v$ in $\vec w$
- **Ploščina paralelograma** -> $\|\vec x\times\vec y\|=\|\vec x\|*\|\vec y\|*\sin\phi$
## Lastnosti vektorskih produktov
1. $(\vec x+\vec y)\times\vec z=\vec x\times\vec z+\vec y\times\vec z$
2. $(\alpha\vec x)\times\vec y=\alpha(\vec x\times\vec y)=\vec x\times(\alpha\vec y)$
3. $\vec x\times\vec y=-\vec y\times\vec x$
4. $(\alpha\vec x+\beta\vec y)\times\vec z=\alpha\vec x\times\vec z+\beta\vec y\times\vec z$
5. $\vec x\times(\alpha\vec y+\beta\vec z)=\alpha\vec x\times\vec y+\beta\vec x\times\vec z$
6. $\vec x\times\vec x=\vec x\times\vec 0=\vec 0$
7. $(\vec x\times\vec y)\times\vec z=\left<\vec x,\vec z\right>*\vec y-\left<\vec y,\vec z\right>$ -> Dvojni vektorski produkt

---
# Mešani produkt
$$\left[\vec x,\vec y,\vec z\right]=\left<\vec x\times\vec y,\vec z\right>=\left|\begin{matrix} z_{1}&z_{2}&z_{3} \\ x_{1}&x_{2}&x_{3} \\ y_{1}&y_{2}&y_{3} \end{matrix}\right|$$
- Vrstni red vektorjev ni pomemben ($[\vec x,\vec y,\vec z]=[\vec z, \vec x, \vec y]$)
- Mešani produkt je **volumen paralelepipeda** (paralelogram kvader)
- $\left[\vec x,\vec y,\vec z\right]=\|\vec x\times\vec y\|*\|\vec z\|*\cos \gamma$ -> Kot med vektorji

---