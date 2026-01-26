```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Definicija
- **Lokalno zaprta** množica $\chi$ -> $\forall x\in\chi; \exists r>0$ da je $\chi\cap \bar K$ zaprta množica v $\Bbb R^{n}$
	- Vsaka zaprta ali odprta množica (ali presek odprte in zaprte množice) je tudi lokalno zaprta
- **Zveznost** -> Naj bo $I=[a,b]$ in $\chi\subset\Bbb R^{n}$ lokalno zaprta množica. Naj bo $f:I\times\chi\to\Bbb R$ zvezna. 
	- $G:\chi\times I\times I\to\Bbb R$ definirana in $G(x,u,w)=\int^{w}_{u}f(t,x)dt$ zvezna
	- $F(x)=\int_{I}f(t,x)dt$ zvezna
- **Odvajanje** -> Naj bo $J\subset\Bbb R$ odprt interval in $f:[a,b]\times J\to\Bbb R$ zvezna. Naj $\forall (t,x)\in[a,b]\times J$ obstaja $\frac{df}{dx}(t,x)$ in je zvezna. 
	- $\frac{d}{dx}\int^{b}_{a}f(t,x)dt=\int^{b}_{a} \frac{d}{dx}f(t,x)dt$.
		- $\frac{dF}{dx_{j}}(x)=\int^{b}_{a} \frac{df}{dx_{j}}(t,x)dt$
	- $\frac{d}{dx}  \int^{\beta(x)}_{\alpha(x)}f(t,x)dt=f[\beta(x),x]\beta'(x)-f[\alpha(x),x]\alpha'(x)+\int^{\beta(x)}_{\alpha(a)} \frac{d}{dx}f(t,x)dt$
- **Integracija** -> Naj bo $f$ zvezna na $[a,b]\times[c,d]$ in $F(x)=\int^{b}_{a}f(t,x)dt$
	- $\int^{d}_{c}F(x)dx=\int^{b}_{a}(\int^{d}_{c}f(t,x)dx)dt$

---
# Posplošeni integral
$$\int^\infty_{a}f(t,x)dt$$
- integral konvergira enakomerno na $[c,d]$ če $\forall\epsilon>0; \exists \bar b>a$ tako da $\forall b>\bar b$ velja $|\int^{\infty}_{\bar b}f(x,t)dt|<\epsilon; \forall x\in[c,d]$
- Naj bo $f$ zvezen na $[c,d]\times[a,\infty]$ in integral $F=\int^{\infty}_{a}f(x,t)dt$ konvergira enakomerno. 
	- Potem je $F$ zvezna na $[c,d]$
	- $\int^{d}_{c}(\int^{\infty}_{a}f(x,t)dt)dx=\int^{\infty}_{a}(\int^{b}_{a}f(x,t)dx)dt$
- $F'(x)=\int^{\infty}_{a} \frac{df}{dx}(x,t)dt$ če $\frac{df}{dx}(x,t)$ zvezna in lahko omejimo $|\frac{df}{dx}|$ z konstanto. Potem $F(x)=\int F'(x)dx$
- Če je pol v $b$ med $a$ in $\infty$ -> $\int_{a}^{\infty}f(x,t)dt=\int^{b}_{a}g(x,t)dt + \int^{\infty}_{b}g(x,t)dt$ 
	- Naredimo $g$ zvezen v $b$

---
# Eulerjeva $\Gamma$-funkcija
$$\Gamma(x)=\int_{0}^{\infty}t^{x-1}e^{-t}dt;\ \forall x>0$$
- "Posplošitev" $n!$
- Nekaj znanih:
	- $\Gamma(1)=1$
	- $\Gamma(x+1)=x\Gamma(x)$
	- $\Gamma(\frac{1}{2})=\sqrt{\pi}$

---
# Eulerjeva $B$-funkcija
$$B(x,y)=\int_{0}^{1}t^{x-1}(1-t)^{y-1}dt=\int_{0}^{\infty} \frac{s^{x-1}}{(1+s)^{x+y}}ds$$
- $B(x,y)=B(y,x)$