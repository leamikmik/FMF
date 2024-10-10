$\mathbb{R}^n={(x1, x2,..., xn);x1, x2,... xn \in \mathbb R; n\in \mathbb N}$
- Točka v $\mathbb R^n$ ima $n$ koordinat
- Vektor je usmerjena daljica ki je neodvisna od vzporednih premikov (tj. natako dolocena s svojo smerjo in dolzino)
- Ce imata vektorja enako smer in dolzino recemo da sta enaka
- Vsak vektor lahko premaknemo tako, da se začne v točki 0 ($\vec{AB}=\vec{0B}-\vec{0A}$)
- Torej lahko vsak vektor podamo le z njegovo končno točko
- Oznaka: $\vec v, \vec x, \vec{AB}$
- Če je napisana samo 1 točka, se začne vektor v 0 ($\vec v=\left[  \begin{array} {c}a_1 \\a_2 \\\vdots \\a_n\end{array}\right]$)
- $\|\vec v\|=\sqrt{v_{1}^{2}+v_{2}^{2}+\dots+v_{n}^{2}}$ -> dolžina (norma) vektorja  
# Operacije na vektrojih
- Seštevanje/Odštevanje -> Vsota je vektor ki se začne v začetni točki prvega, konca pa v končni točki drugega, ob pogoju da se drugi začne v končni točki prvega (vzporedne koordinate sestevamo) 
- Množenje s skalarjem(konstanta) -> "raztegne" vektor za vrednost skalarja, če je negativen se obrne smer, če je 0 pa postane ničelni vektor(začetna in končna točka iste $\vec 0$). Pomnožimo komponente z skalarjem
- Skalarni produkt vektorjev pomnožimo in seštejemo komponente vektorjev da dobimo skalar -> $<\vec v, \vec w>=v_1*w_1+...+v_n*w_n$
    - $<\vec v, \vec v>=\|\vec v\|^2$
### Lastnosti operacij 
$$\vec a, \vec b, \vec c \in \mathbb R^n;\alpha, \beta \in \mathbb R$$
1. $(\vec a+\vec b)+\vec c=\vec a +(\vec b+\vec c)$ -> Asociativnost sešt. 
2. $\vec a+\vec 0=\vec a$ -> $\vec 0$ je enota za sešt. 
3. $\vec a+(-\vec a)=\vec 0$ -> inverz za sešt. 
4. $\vec a+\vec b=\vec b+\vec a$ -> komutativnost sešt. 
5. $\alpha*(\vec a+\vec b)=\alpha*\vec a+\alpha*\vec b$
6. $(\alpha+\beta)*\vec a=\alpha*\vec a+\beta*\vec a$
7. $(\alpha*\beta)*\vec a=\alpha*(\beta*\vec a)$
8. $1*\vec a=\vec a$
# Skalarni produkt 
$$<\vec v, \vec u>=v_{1}*u_{1}+v_{2}*u_{2}+\dots+v_{n}*u_{n}$$
- $\cos\gamma=\frac{<\vec v, \vec u>}{\|\vec u\|*\|\vec v\|}$
- Dva vektorja sta pravokotna če je njun skalarni produkt enak $0$
## Lastnosti skalarnega produkta
1. $<\alpha*\vec u+\beta*\vec v,\vec w>=\alpha<\vec u,\vec w>+\beta<\vec v, \vec w>$
2. $<\vec u,\vec v>=<\vec v,\vec u>$ -> Simetričnost
3. $<\vec u, \vec u>\ge0$ => $\vec u=\vec 0$
4. $|<\vec u,\vec v>|\le\|\vec u\|*\|\vec v\|$ -> Cauchy-schwartz izrek
## Lastnosti norme
1. $\|\alpha*\vec u\|=|\alpha|*\|\vec u\|$ -> absolutna homogenost 
2. $\|\vec u\|\ge 0$ => $\vec u=\vec0$ -> pozitivna definiranost
3. $\|\vec u+\vec v\|\le\|\vec u\|+\|\vec v\|$ -> trikotniška neenakost
$\vec u$ je **enotski** vektor, če je $\|\vec u\|=1$

# Pravokotna projekcija
![[Vektorji v R 2024-10-10 11.52.13.excalidraw]]
$$proj_{\vec u}(\vec v)=\frac{<\vec u,\vec v>}{<\vec u,\vec u>}*\vec u$$
- $\cos \gamma=\frac{\|proj_{\vec u}(\vec v)\|}{\vec v}$
- Pravokotna projekcija vektorja $\vec v$ na vektor $\vec u$

# Vektorski produkt vektorjev
$$\vec v \times\vec w= \left[\begin{array} {}v_{2}w_{3}-v_{3}w_{2} \\ v_{3}w_{1}-v_{1}w_{3}  \\ v_{1}w_{2}-v_{2}w_{1} \end{array}\right]\in\Bbb R^3$$
- Delamo samo v $\Bbb R^{3}$
- Vrstni red operacij je pomemben -> $\vec v\times\vec w\not=\vec w\times\vec v$
- Produkt je linearen
## Lastnosti vektorskih produktov
1. $(\vec x+\vec y)\times\vec z=\vec x\times\vec z+\vec y\times\vec z$
2. $(\alpha\vec x)\times\vec y=\alpha(\vec x\times\vec y)=\vec x\times(\alpha\vec y)$
3. $\vec x\times\vec y=-\vec y\times\vec x$
4. $(\alpha\vec x+\beta\vec y)\times\vec z=\alpha\vec x\times\vec z+\beta\vec y\times\vec z$
5. $\vec x\times(\alpha\vec y+\beta\vec z)=\alpha\vec x\times\vec y=\beta\vec x\times\vec z$
6. $\vec x\times\vec x=\vec x\times\vec 0=\vec 0$
7. $(\vec x\times\vec y)\times\vec z=<\vec x,\vec z>*\vec y-<\vec y,\vec z>$ -> Dvojni vektorski produkt