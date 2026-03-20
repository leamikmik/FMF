```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Uvod
- Želimo rešiti več enačb z obliko $f_{i}(x_{1},x_{2},\dots,x_{n})=0; \forall i\in\{1,\dots,n\}$ 
	- Krajše $F(x)=0$ kjer $F:\Bbb R^{n}\to\Bbb R^{n}$
- Če $n=1$ potem lahko iz grafa določimo začetni približek
	- Enako za $n=2$, samo iščemo presek, kar je ena funkcija
- Drugače pa bolj zapleteno
	- redukcija na manjši sistem
	- aproksimacija z linearnim modelom
	- uporaba variacijskih metod
	- metoda zveznega nadaljevanja
---
# Jacobijeva iteracija
- [[Funkcije več spremenljivk (FVS)#Parcialni odvodi in diferenciabilnost|Jacobijeva matrika]]
- Sistem zapišemo v obliki $x=G(x);\ G:\Bbb R^{n}\to\Bbb R^{n}$
	- $x^{(r+1)}=G(x^{(r)})$
- Pretvorimo funkcije v $F$ tako, da je v vsaki izpostavljen en izmed elementov $x\in\Bbb R^{n}$
- Če obstaja $\Omega\subset\Bbb R^{n}$ da
	1. $x\in\Omega\Rightarrow G(x)\in\Omega$
	2. $x\in\Omega\Rightarrow \rho(JG(x))\le q< 1$
		- $\rho$ spektralni radij matrike (aboslutno največja lastna vrednost)
	- Potem $G(x)=x$ na $\Omega$ natanko eno rešitev $\alpha$
	- $\forall x^{(0)}\in\Omega$ konvergira k $\alpha$
- Red konvergence odvisen od Jacobijeve matrike
	- Če $JG(\alpha)=0$ dobimo vsaj kvadratično konvergenco
- Ker za vsako lastno vrednost velja $|\lambda|\le\|A\|$ je zadostni pogoj za konvergenco $\|JG(x)\|<1$
- Če obstaja $\Omega\subset\Bbb R^{n}$ da
	1. $x\in\Omega\Rightarrow G(x)\in\Omega$
	2. $\|JG(x)\|_{\infty}\le m<1$
	- Velja ocena $\|x^{(r)}-\alpha\|_{\infty}\le \frac{m^{r}}{1-m}\|x^{(1)}-x^{(0)}\|_{\infty}$
---
# Newtonova metoda
$$JF(x^{(r)})\Delta x^{(r)}=-F(x^{(r)});\ x^{(r+1)}=x^{(r)}+\Delta x^{(r)}$$
- oz. $x^{(r+1)}=x^{(r)}-JF(x^{(r)})^{-1}F(x^{(r)})$
	- Ni praktično iskati inverza
- [[Nelinearne enačbe#Tangentna metoda (newtnova metoda)]]
- **Kantorovičev** izrek, denimo $\exists a,b,c \Rightarrow h=abc< \frac{1}{2}$ in velja:
	1. $F$ v $x^{(0)}$ odvedljiva in $\|JF^{-1}(x^{(0)})\|_{\infty}\le a$
	2. $b=\|x^{(1)}-x^{(0)}\|_{\infty}$
	3. V okolici $K_{\infty}(x^{(0)},2b)=\{x:\|x-x^{(0)}\|_{\infty}\le 2b\}$ je funkcija $f_{i}$ dvakrat zvezno odvedljiva in
		- $\sum\limits_{k=1}^{n}\left| \frac{d^{2}f_{i}(x)}{dx_{j}dx_{k}} \right|\le \frac{c}{n}$
	- Potem ima $F(x)=0$ v $K_{\infty}(x^{(0)},2b)$ natanko eno rešitev h kateri konvergira zap. $\{x^{(r)}\}$ in velja
		- $\|x^{(r)}-\alpha\|_{\infty}\le \frac{(2h)^{2^{r}-1}}{2^{r-1}}$
---
# Kvazi-Newtonove metode
- Pri velikem $n$ imamo z Newtnovo metodo veliko dela ($O(n^{3})$ operacij)
- Računamo *približek* za popravek, zato rečemo temu *netočna* Newt. metoda
	- Kombinacija Newtnove metode in poljubne iterativne metode
- **Broydenova** metoda
	- Naj bo $B_{r}$ približek za $JF(x^{(r)})$
	- $B_{r+1}=B_{r}+ \frac{F(x^{(r)})(\Delta x^{(r)})^{T}}{(\Delta x^{(r)})^{T}\Delta x^{(r)}}$
	- oz. $B_{r+1}(x^{(r+1)}-x^{(r)})=F(x^{(r+1)}-F(x^{(r)}))$
- Na začetku vzememo čim boljšo aproks. za $JF(x^{(0)})$
---
# Variacijske metode
- Iščemo ekstrem dvakrat zvezno odvedljive funkcije $G:\Bbb R^{n}\to\Bbb R$
- $\nabla G(x)=0$ ([[Funkcije več spremenljivk (FVS)#Smerni odvod in gradient FVS|gradient]])
- Če je $x$ stacionarna točka, potem o vrsti in obstoju ekstrema določa **Hessejeva** matrika
	- $HG(x)=\left[ \begin{matrix} \frac{d^{2}G(x)}{dx^{2}_{1}} & \dots & \frac{d^{2}G(x)}{dx_{1}dx_{n}} \\ \vdots & & \vdots \\ \frac{d^{2}G(x)}{dx_{1}dx_{n}} & \dots & \frac{d^{2}G(x)}{dx_{n}^{2}} \end{matrix} \right]$
	- pozitivno definitna => lokalni minimum
	- negativno definitna => lokalni maksimum
	- semidefinitna => odločajo višji odvodi
	- nedefinitna => ni ekstrema
- Torej iskanje ekstrema FVS lahko prevedemo na reševanja nelinearnih enačb
	- Gre tudi obratno
	- $G(x)=\sum\limits_{i=1}^{n}f_{i}^{2}(x)$ ima **globalni minimum** v ničlah $F$
## Metode za iskanje minimuma gladke FVS
- Naj $x^{(r)}$ tekoči približek
- Izberemo smer $v_{r}\in\Bbb R^{n}$ in iščemo $x^{(r+1)}=x^{(r)}+\lambda_{r}v_{r}$ da je $G(x^{(r+1)})<G(x^{(r)})$
- Problem je kako izbrati smer $v_{r}$ in določimo premik $\lambda_{r}$
- Možnosti za smer:
	1. *splošna metoda spusta* => poljubna smer, le da ni pravokotna na $\nabla G(x^{(r)})$
	2. *metoda najhitrejšega spusta* oz. *gradientna metoda* => smer $v_{r}=-\nabla G(x^{(r)})$. Moramo poznati parcialne odvode $G$
	3. *metoda koordinatnega spusta* => za smeri po vrsti ciklično izbiramo koordinatne smeri
- Določanje premika:
	- $g_{r}(\lambda):=G(x^{(r)}+\lambda v_{r})$
		- $g_{r}(\lambda_{r})<g_{r}(0)$
	1. *metoda največjega spusta* => kjer $g$ doseže minimum. Rešujemo nelinearno enačbo $g_{r}'(\lambda_{r})=0$ oz. poljubno metodo za računanje min. funkcije
	2. *metoda tangentnega spusta* => vzamemo presečišče tangente $y=g_{r}(\lambda)$ v točki $\lambda=0$ z osjo $x$ 
		- oz. $\lambda_{r}=- \frac{g_{r}(0)}{g_{r}'(0)}$ če $g_{r}(\lambda_{r})\ge g(0)$ potem razpolavljamo $\lambda$ dokler ne dobimo manjše vrednosti 
	3. *metoda paraboličnega spusta* => najprej s tangentno metodo določimo $\alpha$, potem skozi točke $(0,g_{r}(0))$, $(\alpha/2,g_{r}(\alpha/2))$ in $(\alpha,g_{r}(\alpha))$ potegnemo parabolo in za $\lambda_{r}$ vzamemo točko, kjer parabola doseže minimum
	4. *metoda diskretnega spusta* => Izberemo $h_{r}$. Če $g(h_{r})<g(0)$ potem se premikamo naprej s korakom $h_{r}$, in za $\lambda_{r}$ vzamemo $kh_{r}$, kjer je prvič $g((k+1)h_{r})\ge g(kh_{r})$. Sicer $h_{r}$ razpolavljamo toliko časa, da je $g(h_{r})<g(0)$ in za $\lambda_{r}$ vzamemo $h_{r}$
- Če iščemo min. nenegativne funkcije imamo zagotovljeno konvergenco ne glede na začetni približek, saj dobimo $\{x^{(r)}\}$ za katere velja $G(x^{(r+1)})<G(x^{(r)})$
	- Linearen red konvegnece
- Tako dobimo nek lokalni min., ni pa gotovo, da bomo našli globalni minimum. Ponavadi uporabimo kombinacijo variacijske in Newtnove metode