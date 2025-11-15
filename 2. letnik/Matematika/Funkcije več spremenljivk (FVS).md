```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Evklidski prostor $\Bbb R^{n}$
- Sestavljen je iz urejenih n-teric realnih števil
	- $x=(x_{1},x_{2},\dots,x_{n});\forall i\in\{1,2,...,n\}; x_{i}\in \Bbb R$
- Operacije:
	- Seštevanje/odštevanje -> $x\pm y=(x_{1}\pm y_{1},x_{2}\pm y_{2},\dots,x_{n}\pm y_{n})$
	- Množenje s skalarjem -> $\alpha x=(\alpha x_{1},\alpha x_{2},\dots,\alpha x_{n})$
- S operacijami postane prostor vektorski; za bazo vzamemo **STD**
	- Standardni skalarni produkt -> $\left<x,y\right>=x_{1}y_{1}+x_{2}y_{2}+\dots+x_{n}y_{n}$
	- Standardna norma -> $\|x\|=\sqrt{\left<x,x\right>}$
- **Razdalja** -> $d(x,y)=\|x-y\|$
	- $d(x,x)=0$
	- $d(x,y)=d(y,x)$
	- $d(x,y)\le d(x,z)+d(z,y)$
- **Krogla** -> $K(a,r)=\{x\in\Bbb R^{n}; d(a,x)<r\}$
	- $a\in\Bbb R^{n}, r>0$
	- $K(a,r)$ rečemo **odprta** krogla s središčem $a$ in polmerom $r$
	- $\overline{K(a,r)}=\{x\in\Bbb R^{n}; d(a,x)\le r\}$ je pa **zaprta** krogla
- **Odprtost množice** -> $A\subset \Bbb R^{n}$
	- $a\in A$ je *notranja točka* => $\exists r>0;K(a,r)\subset A$
		- Množico označimo z $\text{int}(A)$
	- $a\in \Bbb R^{n}\backslash A$ je *zunanja točka* => $\exists r>0;K(a,r)\subset \Bbb R^{n}\backslash A$
		- Množico označimo z $\text{ext}(A)$
	- $a\in\Bbb R^{n}$ je *robna točka* => $\forall r>0; K(a,r)\cap A\ne\emptyset$ in $K(a,r)\cap \Bbb R^{n}\backslash A\ne\emptyset$
		- Množico označimo z $\delta A$
	- $A$ je odprta če so vse njene točke notranje
		1. $\emptyset$ in $\Bbb R^{n}$ sta odprti
		2. Presek <u>končno</u> mnogo odprtih množic je odprta množica
		3. Poljubna unija odprtih množic je odprta množica
	- $A$ je zaprta če vsebuje vse svoje robne točke
	- $A$ je omejena če $\exists R>0; \|a\|<R;\forall a\in A$
	- Odprta množica $A$ je povezana, če obstajata disjunktni odprti množici $B,C\subset\Bbb R^{n}$ da velja $A=B\cup C$
## Zaporedja in kompaktnost
$$\{a^{(k)}\}^{\infty}_{k=1}\subset\Bbb R^{n}$$
- Točka $a\in\Bbb R^{n}$ je **stekališče** zaporedja če $\forall\epsilon>0$ obstaja neskončno indeksov $k$, za katere velja $d(a,a^{(k)})<\epsilon$
- Točka $a\in\Bbb R^{n}$ je **limita** če $\forall\epsilon>0,\exists N_{0}>0$ tako da $\forall k>N_{0}$ velja $d(a,a^{(k)})<\epsilon$
	- $\lim_{k\to\infty}a^{(k)}=a\iff\lim_{k\to\infty}a^{(k)}_{j}=a_{j}$ -> Zaporedje konvergira natanko tedaj, ko konvergira vsaka komponenta zaporedja
---
# Zvezne preslikave iz $\Bbb R^{n}$ v $\Bbb R^{m}$
$$D\subset \Bbb R^{n};\ f:D\to\Bbb R^{m}$$
- Preslikava $f$ je **zvezna** v $a\in D$ če $\forall\epsilon>0,\exists\delta>0$ da je $d(f(x),f(a))<\epsilon$ kjer je $x\in D,d(x,a)<\delta$
	- Preslikava zvezna na $D$, če je zvezna v vsaki točki $D$
	- V točki $(a,b)\in\Bbb R^{2}$ -> $\lim_{r\to0}|f(a+r\cos\phi,b+r\sin\phi)-f(a,b)|=0$ 
- Preslikava *enakomerno* zvezna če $\forall\epsilon>0,\exists\delta>0$ da je $\|f(x)-f(\bar x)\|<\epsilon$ za $\forall x,\bar x\in D$, kjer $\|x-\bar x\|<\delta$
- **Operacije pri katerih se ohrani zveznost** ($f,g:D\to\Bbb R^{m}$ kjer sta $f,g$ zvezni v $a\in D$):
	- $f+g$
	- $f-g$
	- $f*g$
	- $\frac{f}{g};g(a)\ne0$
- $f:K\to\Bbb R$ zvezna in $K\subset\Bbb R^{n}$ kompaktna -> $f$ bo na $K$ dosegel svoj minimum in maximum
## Vektorske funkcije
$$D\subset\Bbb R,f:D\to\Bbb R^{m}$$
- $f(t)=(f_{1}(t),f_{2}(t),\dots,f_{n}(t))$
- Funkcija je zvezna $\iff$ so zvezne vse koordinate funkcije 
- Limita (vektor) v točki $a$ -> $\lim_{t\to a}f(t)=A$
	- Vrednost limite je limita vseh koordinatnih funkcij -> $\lim_{t\to a}f_{k}(t)=A_{k};k\in\{1,\dots,n\}$
	- Če je funkcija zvezna v točki $a$ je enaka vrednosti v $a$ -> $\lim_{t\to a}f(t)=f(a)$
---
# Odvod
- Odvod vektorske funkcije ($D\subset\Bbb R,f:D\to\Bbb R^{n},f=(f_{1},\dots,f_{n})$):
	- Odvedljiva če vse funkcije ($\forall f_{i}:D\to\Bbb R^{n}$) odvedljive v $a\in D$
	- $f'(a)=(f_{1}'(a),\dots,f_{n}'(a))$
	- Diferenciabilnost skoraj enaka kot za $f:\Bbb R\to\Bbb R$
## Parcialni odvodi in diferenciabilnost
$$D\subset\Bbb R^{n},f:D\to\Bbb R^{m},a\in\text{int}(D),h\in\Bbb R^{n}>\vec0$$
- **Parcialni odvod funkcije** $f$ po $x_{i}$ v točki $a$:
	- $\frac{df}{dx_{i}}(a)=\lim_{h\to0} \frac{f(a_{1},\dots,a_{i}+h,\dots,a_{n})-f(a)}{h}$
	- oz. <u>odvod po koordinati</u>
- Parcialni odvod lahko razvijemo v **višje rede**:
	- Če ima vsaka točka $f$ definirane parcialne odvode
	- Potem $\frac{d}{dx_{k}}\left(\frac{df}{dx_{j}}\right);j,k\in\{1,\dots,n\}$ ali $\frac{d^{2}f}{dx_{k}dx_{j}}$
	- oz. odvajamo odvod ponovno
	- Če sta dva parcialna odvoda zvezna v neki točki in je njun razviti parcialni odvod tudi zvezen => $\frac{d^{2}f}{dx_{k}dx_{j}}(a)=\frac{d^{2}f}{dx_{j}dx_{k}}(a)$
- **Diferencial** $L:\Bbb R^{n}\to\Bbb R^{m}$ => $f(a+h)=f(a)+L(a)h+o(h)$
	- kjer $\lim_{h\to0} \frac{\|o(h)\|}{\|h\|}=0$, potem rečemo, da je $f$ *diferenciabilna* v točki $a$
		- potem je tudi zvezna in parcialno odvedljiva v $a$
	- $L(a)=(Df)(a)=\left[\begin{matrix} \frac{df_{1}}{dx_{1}}(a) & \dots & \frac{df_{1}}{dx_{n}}(a) \\ \vdots & \ddots & \vdots \\ \frac{df_{m}}{dx_{1}}(a) & \dots & \frac{df_{m}}{dx_{n}}(a) \end{matrix}\right]$
		- imenujemo tudi **Jacobijeva matrika**
- **Verižno pravilo**
	- Naj bo $f:D\to\Bbb R^{m}$ in $g:\bar D\to\mathbb{R}^{k}$ kjer $D\subset\Bbb R^{n}$ in $\bar D\subset\Bbb R^{m}$, naj bo $a\in\text{int}(D)$ in $f(a)\in\text{int}(\bar D)$. Naj bo $f$ diferenciabilen v $a$ in $g$ v $f(a)$
	- Potem je $g\circ f$ diferenciabilen v $a$ in $D(g\circ f)(a)=Dg(f(a))*Df(a)$
- **Tangentni prostor na nivojnice:**
	- Naj bo $f:\Bbb R^{n}\to\Bbb R$ enkrat zvezno odvedljiva in $c\in Z_{f}\subset\Bbb R$.
	- **Nivojnica** -> $N_{c}=\{x\in\Bbb R^{n};f(x)=c\}$
		- imamo $a\in N_{c}$
	- Tangentni prostor na nivojnico v $a$ je definiran kot
		- $T_{a}N_{c}=\{v\in\Bbb R^{n};<\nabla f(a),v>=0\}$
		- tj. $v$ je v $T_{a}N_{c}$ natanko tedaj, ko je smerni odvod $f$ v smeri $v$ enak 0
## Smerni odvod in gradient FVS
- Imamo $n\in\Bbb R^{n}$ enotski vektor, FVS $f$ in $a\in\text{int}(D)$
- Če obstaja $\frac{df}{dn}(a)=\lim_{h\to0} \frac{f(a+hn)-f(a)}{h}$ temu rečemo **smerni odvod** v točki $a$ in smeri $n$
	- Parcialni odvodi so smerni odvodi v smeri koordinate odvajanja
- **Gradient** -> $\nabla f(a)=( \frac{df}{dx_{1}}(a),\dots, \frac{df}{dx_{n}}(a))$
	- $n=\nabla f(a)$ kaže v smer največjega naraščanja
	- $\frac{df}{dn}(a)=\left< \nabla f(a),n\right>$
