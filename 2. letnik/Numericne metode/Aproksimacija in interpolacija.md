```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Aproksimacija
- Aproksimiramo neko zvezno funkcijo $f$ na $[a,b]$ s preprostejšo funkcijo $g$ (ponavadi polinom)
- Kakovost gledamo z $\|f-g\|$
- Če za polinom $p$ obstaja $n+2$ takih točk, da za razliko $r=f-p$ velja, da v teh točkah $|r|$ doseže maksimum, pri čemer predznak $|r|$ z zaporednim indeksom alternira, potem je $p$ najboljša aproksimacija
## Metoda najmanjših kvadratov
- Vhodni podatki so $f$ in interval $[a,b]$ oz. $n$ točk (potem $f(x_{i})=y_{i}$) in bazni prostor velikosti $k$. Izhod je funkcija $p$
1. Nastavimo $p(x)=a_{0}\phi_{0}(x)+\dots+a_{k}\phi_{k}(x)$ kjer so $\phi$ bazni vektorji
2. Izberemo skalarni produkt glede na funkcijo
	- $f$ zvezna -> $\left<f,g\right>=\int^{b}_{a}f(x)g(x)$
	- $f$ diskretna -> $\left<f,g\right>=\sum\limits_{i=1}^{n}f(x_{i})g(x_{i})$
3. Rešimo Gramov sistem
	- $\left[\begin{matrix}\left<\phi_{0},\phi_{0}\right> & \dots & \left<\phi_{0},\phi_{k}\right> \\ \vdots & &\vdots \\ \left<\phi_{0},\phi_{k}\right> & \dots & \left<\phi_{k},\phi_{k}\right>\end{matrix}\right]\left[\begin{matrix}\alpha_{0} \\ \vdots \\ \alpha_{k}\end{matrix}\right]=\left[\begin{matrix}\left<f,\phi_{0}\right> \\ \vdots \\ \left<f,\phi_{k}\right>\end{matrix}\right]$
## Remesova metoda
- Vhodni podatki so $f$, interval $[a,b]$, stopnja $n$ in toleranca $\epsilon$. Izhod je pa polinom stopnje kvečjem $n$
```
izberemo delilne točke x_0<x_1<...<x_{n+1} na [a,b]
for k=0:n+1
	določi p ki reši lin sistem f(x_i) - p(x_i) = r*(-1)^i za vsak i
	y = lokalni max od |f-p| na [a,b]
	if |f(y) - p(y)| - |r| < \epsilon:
		return p
	end
	if x_k <= y <= x_{k+1}:
		if sign( f(x_k)-p(x_k) ) == sign( f(y)-p(y) ):
			x_k = y
		else:
			x_{k+1} = y
	elif a <= y <= x_0:
		if sign( f(x_0)-p(x_0) ) == sign( f(y)-p(y) ):
			x_0 = y
		else:
			x_{n+1} = y
	elif x_{n+1} <= y <= b:
		if sign( f(x_{n+1})-p(x_{n+1}) ) == sign( f(y)-p(y) ):
			x_{n+1} = y
		else:
			x_0 = y
	end
	po potrebi uredimo delilne točke po velikosti
end
```
---
# Interpolacija
- Iščemo neko *interpolacijsko funkcijo* $g$ (spet ponavadi polinom), ki se v $n+1$ točkah ujema s funkcijo $f$ ter lahko za približek vrednosti $f$ uzamemo vrednost $g$. Skoraj nikoli ne iščemo enačbe polinoma in zadošča samo izračunati vrednost polinoma v neki točki.
- **Legrangeev interpolacijski polinom**
	- $L_{i,n}(x)=\prod\limits^{n}_{k=0;\ k\ne i}\frac{x-x_{k}}{x_{i}-x_{k}}$
	- $p(x)=\sum\limits^{n}_{k=0}f(x_{k})L_{k,n}(x)$
## Nevilleova shema
- Vhod $n+1$ točk $x_{0},\dots,x_{n}$ in iskan $x$. Izhod je vrednost $f(x)$
- $I_{i,i+1,\dots,i+k}(x)=\frac{I_{i,i+1,\dots,i+k-1}(x)(x-x_{i+k})-I_{i+1,i+2,\dots,i+k}(x)(x-x_{i})}{x_{i}-x_{i+k}}$ -> Vrednost v $x$ polinoma ki se v točkah $x_{i},\dots,x_{i+k}$ ujema z $f$
	- $I_{i}(x)=x_{i}$
- Zapišemo v trikotni shemi
![[Pasted image 20260516181053.png]] 
## Deljene diference
- Deljena diferenca $f[x_{0},\dots,x_{k}]$ je vodilni koeficient interpolacijskega polinoma stopnje $k$, ki se ujema s funkcijo $f$ v $k$ različnih točkah $x_{0},\dots,x_{k}$
	- Je simetrična funkcija argumentov
- $P_{n}(x)=f[x_{0}]+f[x_{0},x_{1}](x-x_{0})+\dots+f[x_{0},\dots,x_{n}](x-x_{0})\dots(x-x_{n-1})$ -> polinom, ki se ujema s $f$ v točkah $x_{0},\dots,x_{n}$
	- Rečemo tudi **Newtnov interpolacijski polinom**
- $f[x_{0},\dots,x_{k}]=\begin{cases} \frac{f^{(k)}(x_{0})}{k!}  & x_{0}=x_{1}=\dots=x_{k} \\ \frac{f[x_{1},\dots,x_{k}]-f[x_{0},\dots,x_{k-1}]}{x_{k}-x_{0}} & \text{sicer} \end{cases}$
- Lahko spet zapišemo v trikotni shemi
	- Za polinom lahko vzamemo potem koeficiente po diagonali
- $f(x)-P_{n}(x)=\frac{f^{(n+1)}(\zeta)}{(n+1)!}(x-x_{0})\dots(x-x_{n})$
	- $\min(x,x_{0},\dots,x_{n})\le\zeta\le\max(x,x_{0},\dots,x_{n})$
## Končne diference
- Če so točke ekvidistantne, torej $x_{i}=x_{0}+i*h$ (enakomerno razmaknjene med druga drugo) lahko formule poenostavimo
- $\Delta^{m}_{h}f(x)=\begin{cases}f(x) & m=0 \\ \Delta^{m-1}_{h}f(x+h)-\Delta^{m-1}_{h}f(x) & m>0\end{cases}$
	- $\Delta^{m}y_{k}=\begin{cases}y_{k} & m=0 \\ \Delta^{m-1}y_{k+1}-\Delta^{m-1}y_{k} & m>0\end{cases}$
- Interpolacijski polinom v $x$ -> $I_{n}(x)=\sum\limits_{k=0}^{n}{s\choose k}\Delta^{k}_{h}f(x_{0})$
	- $s= \frac{x-x_{0}}{h}$
	- ${s\choose k}= \frac{s(s-1)(s-2)\dots(s-k+1)}{k!}$