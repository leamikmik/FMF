```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Neformalni uvod
- Poskus (eksperiment) -> dogodek ($A$)
- Poskus ponovimo n-krat in je $h_{n}(A)$ število dogodkov $A$
	- Relativna frekvenca -> $f_{n}(A):= \frac{h_{n}(A)}{n}\in [0,1]$
	- Zaporedje konvergira
	- Naj bo $p=\lim_{n\to\infty}f_{n}(A)$
	- Statistična definicija verjetnosti -> $P(A):=p$
- Klasična def. verjetnosti $P(A):=\frac{\text{st vgodnih izidov}}{\text{st vseh izidov}}$
	- **Pri pogoju da so vsi izidi enako možni**
- Ce je vseh izvidov neskončno, s pomagamo z geometrijsko definicijo verjetnosti (liki v $\Bbb R^{n}$)
--- 
# Aksiomatična definicija
1. **Način dogodkov**: $A\subset B$ (Vedno ko se zgodi $A$ se zgodi tudi $B$)
2. **Enakost dogodkov**: $A=B\iff A\subset B\vee B\subset A$ (Enakih dogodkov ne ločimo)
	- Gotovi dogodki => $G$
	- Nemogoči dogodki => $N$
3. **Vsota dogodkov**: $A+B$ (Zgodi se vsaj eden dogodek)
4. **Produkt dogodkov**: $AB$ (Oba dogodka se zgodita hkrati)
5. **Nezdružljiva dogodka**: $AB=N$
	- Dogodki $A_{1},\dots,A_{n}$ so paroma nezdružjivi če velja $A_{i}A_{j}=N;i\ne j$
6. **Nasprotna dogodka**: $AB=N$ in $A+B=G$ tedaj je $B=\bar A$ in $\bar A$ imenujemo nasprotje dogodka $A$
	- $\bar{\bar A}=A,\bar N=G,\bar G=N$
7. **Popoln sistem**: $E_{1}+\dots+E_{n}=G,E_{i}E_{j}=N\ (i\ne j)$
- Dogodke lahko obravnavamo kot množice:
	- Vsota => unija
	- Produkt => presek
	- Nasprotni dogodek => komplement
	- Gotov dogodek => univerzalna množica
	- Nemogoč dogodek => prazna množica
- **Pravila računanja:**
	- *Idempotentnost* -> $A+A=A,AA=A$
	- *Komutativnost* -> $A+B=B+A,AB=BA$
	- *Asociativnost* -> $(A+B)+C=A+(B+C),(AB)C=A(BC)$
	- *Distributivnost* -> $(A+B)C=AC+BC,AB+C=(A+C)(B+C)$
	- *De Morganov zakon* -> $\overline{(A+B)}=\bar A \bar B,\overline{(AB)}=\bar A+\bar B$
- Neprazna družina dogodkov (podmnožic) $D$ v $G$ je **$\sigma$-algebra** če
	- $A\in D\Rightarrow \bar A\in D$ (če imamo nek dogodek obstaja njegovo nasprotje)
	- $\{A_{i}\}\subset\forall i=1,2,...\Rightarrow\sum\limits^{\infty}_{i=1}A_{i}\in D$ (če imamo več različnih dogodkov, obstaja tak dogodek, kjer se zgodi vsaj en od teh dogodkov)
## Definicija verjetnosti in lastnosti
- $D$ poljubna $\sigma$-algebra v $G$, **verjetnost** na $G$ je preslikava $P:D\to\Bbb R$:
	- $P(A)\ge0$
	- $P(G)=1$
	- $P(A_{1}+A_{2}+\dots)=P(A_{1})+P(A_{2})+\dots$ (če so $A_{i}$ paroma nezdružljivi)
- Zgornjim lastnostim rečemo *aksiomi Kolmogorova*. Iz njih izhajajo še naslednje lastnosti:
	1. $P(N)=0$
	2. $A\subset B\Rightarrow P(A)\le P(B)$
	3. $P(\bar A)=1-P(A)$
	4. $P(A+B)=P(A)+P(B)-P(AB)$ (Vsota poljubnih dogodkov)
		- $P(A+B+C)=P(A)+P(B)+P(C)-P(AB)-P(AC)-P(BC)+P(ABC)$
		- Odštejemo presek, ker se drugače nektere verjetnosti podvojijo
	5. *Za monotona zaporedja dogodkov (vsak sledeči dogodek vsebuje vse prejšnje/naslednje) velja zveznost preslikave $P$*:
		- $A_{1}\subset A_{2}\subset\dots\Rightarrow P(A_{1}+A_{2}+\dots)=\lim_{n\to\infty}P(A_{n})$
		- $A_{1}\supset A_{2}\supset\dots\Rightarrow P(A_{1}A_{2}\dots)=\lim_{n\to\infty}P(A_{n})$
- **Verjetnostni prostor** je trojica $(G,D,P)$ kjer je $G$ dana neprazna množica, $D$ $\sigma$-algebra podmnožic v $G$ in $P:D\to\Bbb R$ verjetnostna preslikava. Sedaj imenujemo elemente v $G$ <u>izide</u>, elemente v $D$ pa <u>dogodke</u>
---
# Pogojna verjetnost
- Verjetnost dogodka $A$ pri fiksiranem dogodku $B$  -> $P(A|B)= \frac{P(AB)}{P(B)}$
- **Več fazni poskusi**
	- $H_{1},H_{2},\dots$ paroma nezdružljivi dogodki (v prvi fazi)
	- **Popolna verjetnost** -> $P(A)=P(H_{1})P(A|H_{1})+P(H_{2})P(A|H_{2})+\dots$
	- **Bayesova formula**:
		- Vemo, da se je zgodil dogodek $A$, zanima nas verjetnost da se je v prvi fazi zgodil dogodek $H_{k}$
		- $P(H_{k}|A)=\frac{ P(H_{k})P(A|H_{k})}{P(A)}$
- **Neodvisni dogodki** => $P(AB)=P(A)P(B)$
	- Če dogodka ne vplivata en na drugega.
---
# Zaporedje neodvisnih poskusov
- Dva poskusa sta neodvisna, kadar rezultati enega poskusa ne vplivajo na verjetnost dogodkov v drugem.
- Iščemo verjetnost da se dogodek $A$ v $n$ ponovitvah poskusa zgodi $k$ krat
	- oz. $P_{n}(k)$
	- možnih kombinacij je ${n\choose k}=\frac{n!}{(n-k)!*k!}$
	- $P(A)=p;P(\bar A)=q=1-p$
- **Bernoullijeva formula**: $P_{n}(k)={n\choose k} p^{k}q^{n-k}$
- Aproksimacije formule za $P_{n}(k)$:
	- $p$ blizu 0 -> $P_{n}(k)\approx \frac{(np)^{k}}{k!}e^{-np}$
	- $p$ blizu 1/2 -> $P_{n}(k)\approx \frac{1}{\sqrt{2\pi npq}}e^{- \frac{(k-np)^{2}}{2npq}}$
	- da se zgodi vsaj $k_{1}$ in manj od $k_{2}$ krat -> $P_{n}(k_{1},k_{2})\approx \Phi(\mu_{2} )-\Phi( \mu_{1})$
		- $\mu_{i}=\frac{k_{i}-np}{\sqrt{npq}}$
		- vsaj $k$ => $P_{n}(k,n)\approx \frac{1}{2}-\Phi(\mu)$
		- do $k$ => $P_{n}(0,k)\approx \frac{1}{2}+\Phi(\mu)$
		- **Funkcija napake** ->$\Phi(x)= \frac{1}{\sqrt{2\pi}}\int^{x}_{0}e^{-\frac{1}{2}t^{2}} dt$
---
# Slučajne spremenljivke
 - Pri poskusu dostikrat določimo neko številsko količino, ki jo lahko merimo. Katero vrednost zavzame je odvisno od slučaja, zato ji bomo rekli slučajna spremenljivka. Zanima nas tudi, s kakšno verjetnostjo zavzame spremenljivka določeno vrednost.
	 - Npr. pri metu kocke, je slučajna spremenljivka vrednost meta (med 1 in 6) in verjetnost vsake vrednosti je 1/6.
- Ločimo vrednosti spremenljivke:
	- *diskretna* -> števne vrednosti ($1,2,3,\text{cifra},\text{grb},\dots$)
	- *zvezna* -> ne-števne vrednosti ($[0,1],\text{razdalja},\dots$)
- **Definicija**: 
	- Na prostoru $(G,D,P)$ je funkcija $X:G\to\Bbb R$
	- Da za vsak $y,z\in\Bbb R$ je $(y\circ X\circ z)=\{e\in G;y\circ X(e)\circ z\}$ dogodek v $D$
		- Kjer $\circ$ lahko $<,>,=,\le,\ge$ (glej nižje za formule)
	- Imamo še $F(x)=P(y\circ X\circ z)$ ki se imenuje **porazdelitvena funkcija** slučajne spremenljivke $X$
- Lastnosti porazdelitvene funkcije:
	1. Funkcija je definirana na vsej realni oni in velja $0\ge F(x)\ge 1;\forall x\in\Bbb R$
	2. Funkcija je naraščajoča -> $x_{1}<x_{2}\Rightarrow F(x_{1})\le F(x_{2})$
	3. $\lim_{x\to-\infty}F(x)=0$ in $\lim_{x\to\infty}F(x)=1$
	4. Funkcija levo zvezna -> $F(x)=F(x-)$
- **Izračun verjetnosti preprostih dogodkov**:
	1. $P(X\ge x)=1-F(x)$
	2. $P(X\le x)=F(x+)$
	3. $P(X=x)=F(x+)-F(x)$
	4. $P(X>x)=1-F(x+)$
	5. $P(x_{1}\le X<x_{2})=F(x_{2})-F(x_{1})$
	6. $P(x_{1}<X\le x_{2})=F(x_{2}+)-F(x_{1}+)$
	7. $P(x_{1}\le X\le x_{2})=F(x_{2}+)-F(x_{1})$
	8. $P(x_{1}<X<x_{2})=F(x_{2})-F(x_{1}+)$
## Diskretno razporejene slučajne spremenljivke
- Slučajna spremenljivka $X$ je *diskretna*, če je njena zaloga vrednosti končna ali števna množica.
- Predstavimo s shemo:
	- $X:\left(\begin{matrix}x_{1} & x_{2} & x_{3} & \dots \\ p_{1} & p_{2} & p_{3} & \dots\end{matrix}\right)$
	- $x_{k}$ -> možne vrednosti
	- $p_{k}$ -> verjetnost vsake vrednosti
		- $\sum\limits_{k}p_{k}=1$
- Porazdelitvena funkcija je odsekoma konstantna
### Pomembnejše diskretne porazdelitve
1. **Enakomerna diskretna porazdelitev** na $n$ točkah:
	- $X:\left(\begin{matrix}x_{1} & x_{2} & \dots & x_{n} \\ 1/n & 1/n & \dots & 1/n\end{matrix}\right)$
	- npr. met kocke
2. **Binomska porazdelitev** -> $\text{Bin}(n,p)$
	- $n$ je št. neodvisnih ponovitev poskusa
	- $X:\left(\begin{matrix}0 &1 & 2 & \dots \\ p_{1} & p_{2} & p_{3} & \dots\end{matrix}\right)$
	- $p_{k}={n\choose k}p^{k}(1-p)^{n-k}$
3. **Poissonova porazdelitev** -> $\text{Poi}(\lambda); \lambda>0$
	- $X:\left(\begin{matrix}x_{1} & x_{2} & x_{3} & \dots \\ p_{1} & p_{2} & p_{3} & \dots\end{matrix}\right)$
	- $p_{k}=\lambda^{k} \frac{e^{-\lambda}}{k!}$
4. **Pascalova porazdelitev** -> $\text{Pas}(m,p)$
	- Porazdeljeno število ponovitev poskusa, da se dogodek zgodi $m$-krat
	- Zaloga vrednosti je $\{m,m+1,m+2,\dots\}$
	- $p_{k}={k-1\choose m-1}p^{m}(1-p)^{k-m}$
	- Če je $m=1$ rečemo temu *geometrijska porazdelitev* $\text{Geo}(p)$
		- $p_{k}=p(1-p)^{k-1}$
5. **Hipergeometrijska porazdelitev** -> $\text{Hip}(n;M,N)$
	- Uporabimo, da je med $n$ izbranimi kroglami natanko $k$ belih, če je v posodi $M$ belih in $N-M$ črnih 
	- $p_{k}= {M\choose k} {N-M\choose n-k}/{N\choose n}$
	- $k\le n\le \min{M,N-M}$
## Zvezno porazdeljene slučajne spremenljivke
- $X$ je *zvezno porazdeljena*, če obstaja nenegativna integrabilna funk. $p_{X}$ imenovana **gostota verjetnosti**
	- $F_{X}(x)=P(X\le x)=\int^{x}_{-\infty}p_{X}(t)dt$ za $\forall x\in\Bbb R$
	- Oz verjetnost $X$-a do vključno $x$ je ploščina grafa od $-\infty$ do $x$
### Pomembnejše zvezne porazdelitve
1. **Enakomerna porazdelitev** na $[a,b]$
	- $p_{X}(x)=\begin{cases} \frac{1}{b-a} & x\in[a,b]  \\ 0 & x\notin[a,b] \end{cases}$
	- $F_{X}(x)=\begin{cases}0 & x\le a \\ \frac{x-a}{b-a} & a<x<b \\ 1 & b\le x\end{cases}$
2. **Normalna / Gaussova porazdelitev** -> $N(\mu,\delta)$
	- $\mu\in\Bbb R,\delta>0$
	- $p_{X}(x)= \frac{1}{\delta\sqrt{2\pi}}e^{-\frac{1}{2}( \frac{x-\mu}{\delta} )^{2}}$
	- $F_{N(\mu,\delta)}= \frac{1}{2}+\Phi( \frac{x-\mu}{\delta})$
	- <u>Standardizirana normalna gostota</u> => $N(0,1)$
3. **Eksponentna porazdelitev**
	- $\lambda>0$
	- $p(x)=\begin{cases}\lambda e^{-\lambda x} & x\ge0 \\ 0 & x<0\end{cases}$
	- $F(x)=\begin{cases}1-e^{-\lambda x} & x\ge0 \\0 & x<0\end{cases}$
4. **Cauchyjeva porazdelitev**
	- $p(x)=\frac{1}{\pi(1+x^{2})}$
	- $F(x)=\frac{1}{\pi}\arctan(x)+\frac{1}{2}$