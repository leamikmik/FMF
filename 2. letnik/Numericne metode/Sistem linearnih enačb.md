```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Uvod
- Rešujemo sistem več linearnih enačb
- Zapišemo kot $Ax=b$ 
	- $A^{H}=\overline{A^{T}}$
- [[Matrike]]
---
# Norme
- Enaka pravila kot normalna [[Vektorji v R#Norma|norma]].
## Vektorske norme:
- $\|x\|_{1}=\sum\limits^{n}_{i=1}|x_{1}|$ -> 1-norma
- $\|x\|_{2}=\left(\sum\limits^{n}_{i=1}|x_{i}|^{2}\right)^{1/2}$ -> 2-norma oz. *evklidska norma*
- $\|x\|_{\infty}=\max_{i=1,\dots,n}|x_{i}|$ -> $\infty$-norma
- Vse so oblike Holderjeve $p$-norme => $\|x\|_{p}=(\sum^{n}_{i=1}|x_{i}|^{p})^{1/p}$
	- Holderjeva neenakost -> $|x^{H}y|\le\|x\|_{p}\|y\|_{q}$ kjer $\frac{1}{p} + \frac{1}{q}=1$\
- Ocene:
	- $\|x\|_{2}\le\|x\|_{1}\le\sqrt{n}\|x\|_{2}$
	- $\|x\|_{\infty}\le\|x\|_{2}\le\sqrt{n}\|x\|_{\infty}$
	- $\|x\|_{\infty}\le\|x\|_{1}\le n\|x\|_{\infty}$
## Matrična norma:
- Ima še lastnost $\|AB\|\le\|A\|*\|B\|$ -> submultiplikativnost
- Operatorska norma => $\|A\|=\max \frac{\|Ax\|}{\|x\|}$
- Singularna vrednost => $\sigma_{i}=+\sqrt{\lambda_{i}}$
	- $\sigma_{1}\ge\sigma_{2}\ge\dots\ge\sigma_{n}\ge0$
- $\|A\|_{1}=\max_{j=1,\dots,n}\left(\sum^{n}_{i=1}|a_{ij}|\right)$
- $\|A\|_{2}=\sigma_{1}(A)=\max_{i=1,\dots,n}\sqrt{\lambda_{i}(A^{H}A)}$ -> spektralna norma
	- Največja singularna vrednost (pozitivni kvadratni koreni lastnih vrednosti matrike $B=A^{H}A$)
	- $\|A\|_{2}=\|UA\|_{2}=\|AU\|_{2}$
- $\|A\|_{\infty}=\max_{i=1,\dots,n}\left(\sum^{n}_{j=1}|a_{ij}|\right)$
	- $\|A\|_{F}=\|UA\|_{F}=\|AU\|_{F}$
- $\|A\|_{F}=\left(\sum^{n}_{i,j=1}|a_{ij}|^{2}\right)^{1/2}$ -> Forbeniusova norma
- $\|I\|=1$ in $\|I\|_{F}=\sqrt{n}$
- Normo $\|A\|_{2}$ je zelo težko izračunati, zato uporabimo ocene:
	- $\frac{1}{\sqrt{n}}\|A\|_{F}\le\|A\|_{2}\le\|A\|_{F}$
	- $\frac{1}{\sqrt{n}}\|A\|_{1}\le\|A\|_{2}\le\sqrt{n}\|A\|_{1}$
	- $\frac{1}{\sqrt{n}}\|A\|_{\infty}\le\|A\|_{2}\le\sqrt{n}\|A\|_{\infty}$
	- $\|A\|_{2}\le\sqrt{\|A\|_{1}\|A\|_{\infty}}$
- $|\lambda|\le \|A\|;\ \forall\lambda(A)$
---
# Občutljivost linearnih sistemov
- Zanima nas, kako je rešitev sistema občutljiva na spremembe matrike $A$ in $b$
- $\|(I-X)^{-1}\|\le  \frac{1}{1-\|X\|}$
	- Če $\|X\|<1$ v matrični normi, v kateri je $\|I\|=1$
- $\kappa(A)=\|A\|*\|A^{-1}\|$ -> občutljivost oz. pogojenostno število matrike 
	- Če je število veliko lahko kljub majhnim relativnim napakam s podatki dobimo visoko relativno napako rešitve
	- $1\le\kappa(A)$ => Enakost le če unitarna matrika pomnožena z neničelnim skalarjem
	- $\kappa_{2}= \frac{\sigma_{1}(A)}{\sigma_{n}(A)}$
- $A$ nesigularna in $\delta A$ motnja da $\|A^{-1}\|*\|\delta A\|<1$
	- $\frac{\|\delta x\|}{\|x\|}\le \frac{\kappa(A)}{1-\kappa(A) \frac{\|\delta A\|}{\|A\|} }(\frac{\|\delta A\|}{\|A\|}+\frac{\|\delta b\|}{\|b\|})$
	- $\min\left\{\frac{\|\sigma A\|_{2}}{\|A\|_{2}}; \det(A+\sigma A)=0\right\}= \frac{1}{\kappa_{2}(A)}$
- Direktna stabilnost => $\frac{\|x-\bar x\|}{\|x\|}\le \kappa(A)* \frac{\| A\bar x - b \|}{\|b\|}$
---
# Elementarne eliminacije
- Imamo $x\in\Bbb R^{n}$ kjer $x_{k}\ne0$. Iščemo nesigularno matriko $L_{k}$ da $L_{k}*x=\left[\begin{matrix} x_{1} \\ \vdots \\ x_{k} \\ 0 \\ \vdots \\ 0 \end{matrix}\right]$, ki je rečemo *elementarna eliminacija*
	- Torej matriko ki uniči elemente vektorja po $k$ indeksu
- Lahko zapišemo kot $L_{k}=I-l_{k}e_{k}^{T}$ kjer $l_{k}=\left[\begin{matrix} \vdots \\ 0 \\ \frac{x_{k+1}}{x_{k}} \\ \vdots \\ \frac{x_{n}}{x_{k}} \end{matrix}\right]$, $e_{k}$ pa bazni vektor (vse $0$ razen $k$-tega indeksa, ki je $1$)
	- $L^{-1}_{k}=I+l_{k}e^{T}_{k}$
	- Produkt matrik $L^{-1}_{1}L^{-1}_{2}\dots L^{-1}_{n-1}=I+l_{1}e_{1}^{T}+l_{2}e_{2}^{T}+\dots+l_{n-1}e_{n-1}^{T}$
---
# LU razcep
$$PA=LU$$
- $P$ permutacijska matrika ($P=I$ na začetku, če menjamo vrstice $A$, jih tudi zamenjamo v $P$)
	- Obstaja razcep brez $P$ če so vse vodilne podmatrike nesingularne
		- Razcep ni enoličen
	- Samo zamenjava vrstic -> *delno pivotiranje*
		- vsi el. $L$ po absoluti $\le 1$
		- matrika mora biti nesingularna
	- Zamenjava tudi stolpcev -> *kompletno pivotiranje*
- $L$ spodnje trikotna matrika z enicami po diagonali
	- $L=L^{-1}_{1}\dots L^{-1}_{n-1}$
	- $A^{(i)}=L_{i}A^{(i-1)}$ (če $a_{ii}\ne0$) 
- $U$ zgornje trikotna matrika
	- $U=L^{-1}A=A^{(n-1)}$
- Tudi imenujemo **Gaussov razcep**
- Sistem $Ax=b$ rešimo:
	1. $PA=LU$
	2. $Ly=Pb=:b'$ -> [[#Prema substitucija]]
	3. $Ux=y$ -> [[#Obratna substitucija]]
## Algoritmi
### Razcep brez pivotiranja
- (vnos $A$, izhod $A$ z poddiagonalo enako $L-I$, zgornji trikotnik pa $U$)
- Zahtevnost algoritma je $\frac{2}{3}n^{3}+O(n^{2})$
- Po človeško:
	1. $i=1$
	2. Delimo vse elemente $i$-te vrstice pod pivotom z pivotom vrstice in to damo v matriko $L$ 
	3. Vzamemo podmatriko pod $i$-to vrstico in stolpcem
	4. Vsakemu el. te matrike odštejemo zmnožek elementa trenutne vrstice in trenutnega stolpca
	5. Ponovimo $n-1$ krat
```
for j=1:n-1
	for i=j+1:n
		a_ij = a_ij/a_jj
		for k=j+1:n
			a_ik = a_ik - a_ij * a_jk
		end
	end
end
```
### Razcep z delnim pivotiranjem
- (enak vnos in izhod kot brez, plus $P$)
- Ko zamenjamo vrstici v $A$ moramo tudi v $P$
- Enaka zahtevnost
- Enak kot prejšnji postopek, dodatno pa za vsak stolpec $j$ zamenjamo trenutno vrstico (v matriki $A$ in $P$) z vrstico največje absolutne vrednosti v stolpcu
```
for j=1:n-1
	max_{j<=p<=n} |a_pj|
	zamenjaj vrstici p in j (v A in P)
	for i=j+1:n
		a_ij = a_ij/a_jj
		for k=j+1:n
			a_ik = a_ik - a_ij * a_jk
		end
	end
end
```
### Razcep s kompletnim pivotiranjem 
$$PAQ=LU$$
- Gledamo največjo absolutno vrednost v celi matriki in v $P$ zamenjamo vrstico v $Q$ pa stolpec
- Število operacij je enako, primerjav pa je $O(n^{3})$ 
- Postopek:
	1. $PAQ=LU$
	2. $Ly=Pb=:b'$
	3. $Ux'=y$
	4. $x=Qx'$
### Prema substitucija
- $Ly=b'$
- $l_{i1}y_{1}+\dots+l_{i,i-1}y_{i-1}+y_{i};\ i=1,\dots,n$
- Število operacij -> $\sum^{n}_{i=1}(1+2(i-1))=n^{2}$
```
for i=1:n
	y_i = b'_i - sum[j=1,i-1](l_ij * y_j)
end
```
### Obratna substitucija
- $Ux=y$
- $u_{ii}x_{i}+u_{i,i+1}x_{i+1}+\dots+u_{in}x_{n}=y_{i};\ i=1,\dots,n$
- Število operacij -> $\sum^{n}_{i=1}(2+2(i-1))=n^{2}+n$
```
for i=n:1
	x_i = ( y_i - sum[j=i+1,n](u_ij * x_j) ) / u_ii 
end
```
---
# Analiza zaokrožitvenih napak $LU$
- Recimo da imamo rešitev sistema $Ax=b$ z $LU$ razcepom in dobimo $\bar x$. Analiza obratne stabilnosti potem iščemo $\delta A$ da $(A+\delta A)\bar x=b$.
- Predpostavimo:
	- Pri oceni ne pride do prekoračitve oz. podkoračitve
	- Uporabili $LU$ razcep brez pivotiranja
	- $|A|$ pomeni $|a_{ij}|$
	- $A\le B$ pomeni $a_{ij}\le b_{ij}$
- Sistem $LU$ rešujemo v treh korakih. Za vsak korak ocenimo obratno napako:
	- $Ly=b$ => $(L+\delta L)\bar y=b$ kjer $|\delta L|\le nu|L|$
		- $Ux=y$ => $(U+\delta U)\bar x=y$ kjer $|\delta U|\le nu|U|$
		- Reševanje trikotnega sistema je vedno obratno stabilno
	- $A=LU+E$ kjer $|E|\le nu|L|*|U|$
		- Sam $LU$ razcep ni nujno obratno stabilen
	- $Ax=b$ => $(A+\delta A)\bar x=b$ kjer $|\delta A|\le 3nu|L|*|U|$
		- oz. $\|\delta A\|_{\infty}\le 3nu\|L\|_{\infty}*\|U\|_{\infty}$
- Reševanje $LU$ razcepa brez pivotiranja **ni obratno stabilno**, razen če ima matrika kakšno posebno lastnost (npr. diagonalna dominantnost po stolpcih, simetrična pozitivna definitnost)
- Pri **delnem in kompletnem pivotiranju**:
	- $|l_{ij}|\le1$ -> $\|L\|_{\infty}\le n$
	- **pivotna rast** => $g:= \frac{\max|u_{ij}|}{\max|a_{ij}|}$
		- delno pivotiranje -> $g\le2^{n-1}$
		- kompletno pivotiranje -> $g\le n^{\frac{1}{2}+ \frac{\ln n}{4}}$
	- $\|U\|_{\infty}\le ng\|A\|_{\infty}$
	- $\|\delta A\|_{\infty}\le 3gn^{3}u\|A\|_{\infty}$
	- Pričakujemo majhno obratno napako če pivotna rast majhna
	- Kompletno pivotiranje v praksi boljše od delnega, a je več primerjanj
---
# Ostanki
- Recimo da rešimo sistem $Ax=b$, koliko je sedaj rešitev $\bar x$ natančna?
- Izračunamo lahko **ostanek** $r=b-A\bar x$ in gledamo njegovo normo
	- *Relativni ostanek* -> $\frac{\|r\|}{\|A\|*\|\bar x\|}\le \frac{\|\delta A\|}{\|A\|}$
- $\frac{\|\bar x-x\|}{\|x\|}\le \kappa(A) \frac{\|r\|}{\|A\|*\|\bar x\|}$
- **Hagnerjeva cenilka**
	- Če poznamo faktorja $L$ in $U$, potem cenilka v času $O(n^{2})$ vrne spodnjo mejo $\|A^{-1}\|_{\infty}$ ki ne odstopa od točne vrednosti za več kot faktor 10
- $\frac{\|\bar x-x\|}{\|x\|}\le \frac{\|A^{-1}\|*\|r\|}{\|\bar x\|}$ -> Ker zgornja bolj pesimistična
	- Boljše je $\frac{\|\bar x-x\|_{\infty}}{\|x\|_{\infty}}\le \frac{\||A^{-1}|*|r|\|_{\infty}}{\|\bar x\|_{\infty}}$
	- Namesto $\||A^{-1}*r|\|_{\infty}$ lahko uporabimo $\|A^{-1}R\|_{\infty}$ kjer $R$ ničelna matrika z elementi $r$ po diagonali
---
# Sistemi s posebno obliko
- Lahko prišparamo na operacijah in pomnilniku
## Simetrične matrike
- Pol manj prostora in operacij
- Za zdaj rečimo še da je pozitivno definitna
	- **simetrično pozitivna definitna** => SPD
- Velja:
	1. Vsaka vodilna podmatrika SPD matrike je SPD
	2. Če je $A$ SPD, potem se izvede $LU$ razcep brez pivotiranja in diagonala od $U$ je strogo pozitivna
	3. $A$ je SPD natanko, ko obstaja nesignularna spodnje-trikotna matrika $V$ s pozitivnimi elementi na diagonali, da je $A=VV^{T}$
- $A=VV^{T}$ imenuje **razcep Choleskega**, $V$ pa **faktor Choleskega**
	- $a_{jk}=\sum\limits_{i=1}^{k}v_{ji}v_{ki}$
	- Algoritem razcepa porabi $\frac{1}{3}n^{3}+O(n^{2})$ operacij
	- Najcenejša metoda za ugotavljenja ali je matrika SPD. Če ni se v spodnjem algoritmu pod kvadratnim korenom pojavi negativna vrednost
	- ``` matlab
	for k=1:n
		v_kk = (a_kk - sum[i=1, k-1](v_ki ^ 2))^0.5
		for j=k+1:n
			v_jk = (a_jk - sum[i=1, k-1](v_ji * v_ki)) / v_kk
		end
	end
	```
	- $\|\delta A\|_{\infty}\le 3n^{2}u\|A\|_{\infty}$ -> obratno stabilna
	- Cenejše in stabilnejše od $LU$ razcepa
- Če pa matrika ni definitna ne moremo uporabiti Choleskega
- Za nedefinitno obstaja $PAP^{T}=LDL^{T}$
	- $D$ bločno diagonalna z bloki $1\times 1$ in $2\times 2$
	- Obstaja več algoritmov:
		- Bunch-Kaufmannov
		- Bunch-Parlettov
		- Aasenova metoda
	- Potrebujejo $\frac{1}{3}n^{3}+O(n^{2})$
## Tridiagonalne matrike


15.12

- pri delnem pivotiranju pred eleminicaijo v j-tem stolpcu primerjamo elemente v tem stoplcu od diagonalnega navzdol in zamenjamo j-to vrstico s tisto vrstico, ki vsebuje po absolutni vrednosti najvecji element. Menjave belezimo v permutacijksi matriki. Razcep ki dobimo je oblike
- $P*A=L*U$
- ce je matrika obrnljia potem je pivot na vsakem koraku razlicen od 0
	- razcep ni enolicen
- postopek:
	1. nastavimo permutacijsko matriko $P=I$
	2. pogledamo po absoluti najvecji el v 1. stolpcu
	3. ce 1. el ni najvecji, zamenjamo vrstice (tudi v $P$)
	4. potem delimo vse elemente stolpca, ki niso prvi, z pivotom
	5. potem vzamemo podmatriko brez trenutnega stolpca in vrstice (oz vseh visjih)
	6. vsakemu elementu te matrike odstejemo zmnozek elementa trenutne vrstice in trenutnega stolpca
	7. postopek ponavljamo n-1 krat
	8. potem je $L=I+\text{elementi koncne matrike pod diagonalo}$ in $U=\text{vsi elementi koncne matrike nad vkljucno diagonalo}$
- Kako do resitve $Ax=b$?
	- $PAx=Pb$
	- $LUx=Pb$
	1. Resimo $Ly=Pb$
		- Dobimo $y$ -> preme substitucije
	2. Resimo $Ux=y$
		- Dobimo $x$ -> obratne substitucije
- Pri delnem pivotiranju so vsi elementi matrike $L$ po abs vrednosti $\le 1$
Obcustljivost sistemov linearnih enacb
- kako se spremeni resitev $x$ sistema enacb $Ax=b$ ce malo spremenimo vhodne podatke
	- $\bar A = A+\delta A$ in $\bar b=b+\delta b$
	- $\frac{\|\delta A\|}{\|A\|}\le \epsilon$ in $\frac{\|\delta b\|}{\|b\|}\le \epsilon$
		- normi sta vsklajeni
	- zanima nas ocena $(A+\delta A)\bar x=b+\delta b$
		- $\bar x = x+ \delta x$ in $\frac{\|\delta x\|}{\|x\|}\le\ ?$
	- $\frac{\|\delta x\|}{\|x\|}\le \frac{\kappa(A)}{1-\kappa(A) \frac{\|\delta A\|}{\|A\|} }(\frac{\|\delta A\|}{\|A\|}+\frac{\|\delta b\|}{\|b\|})$
	- $\kappa(A)=\|A\|*\|A^{-1}\|$ -> Pogojenostno stevilo matrike 
		- ce je stevilo veliko lahko kljub majhnim relativnim napakam s podatki dobimo visoko relativno napako resitve
		- matrikam ki imajo veliko pogojenostno stevilo recemo OBCUTLJIVE

- direktna stabilnost 
	- $\frac{\|x-\bar x\|}{\|x\|}\le \kappa(A)* \frac{\| A\bar x - b \|}{\|b\|}$
 Sistem lin enacb s posebno obliko
- tridiagonalne matrike
- pasovne matrike
- kompleksne
- razprsene
- simetricne pozitivno definitne
simetricne pozitivno definitne
- Matrika A je s.p.d ce velja $A=A^{T}$ in $x^{T}Ax>0$ za $\forall x\ne\vec 0$
	- ali pa lastne vrednosti strogo vec od 0
- lastnosti 
	- naj bo $C$ obrnljiva mat. Potem je $A$ spd $\iff$ $C^{T}AC$ spd
	- vse vodilne podmatrike (podmatrika k vsebuje prvi clen) spd $A$ so tudi spd 
	- naj bo $A$ spd potem tudi $A([i_{1}i_{2}\dots i_{k}],[i_{1}i_{2}\dots i_{k}])$ spd (lahko poljubno vzamemo vrstice in stolpce. ni nujno da zaporedno)
	- naj bo $A$ spd potem so vsi diagonalni elementi $>0$ in maximum je na diagonali
	- ce je $A$ spd potem $LU$ razcep brez pivotiranja, tj $A=LU$ in vsi diagonalni el matrike $U$ so $>0$
- matrika $A$ je spd iff ko obstaja razcep CHOLESKEGA to je razcep oblike $A=V*V^{T}$ kjer je $V$ spodnje trikotna matrika z pozitivnimi diagonalnimi el
- algoritm - razcept choleskega (vhod $A$ izhod $V$)
```
	for j=1:n
	  v_jj = sqrt(a_jj - sum_k=1^j-1(v_jk^2) )
	  for i=j+1:n
		  v_ij = 1/v_jj (a_ij - sum_k=1^j-1(v_jk * v_ik) )
	  end
	end
```

---
23.2.
Algoritem (gran-schmidtov postpek)
```
for i=1:n
	q^(0)_i = a_i
end
for i=1:n
	r_ii = ||q^(i-1)_i||_2
	q_i = 1/r_ii q^(i-1)_i
	for j=i+1:n
		r_ij = q^T_i * a_j
		q^(i)_j = q^(i-1)_j - r_ij * q_i
	end
end
```
Vrstica 8. taka kot je, recemo Klasicni GSP (CGS)
Al pa (`r_ij = q^T_i * q^(i-1)_j`) Modificiran GSP (MGS)
CGS in MGS nam data enak eksakten rezultat, pri numericnem je pa MGS bolj stabilen.

Kako z pomocjo $QR$ razcepa do resitve $Ax=b$ po MNK?
- $A=QR$
- $A^{T}Ax=A^{T}b$
- $(QR)^{T}QRx=(QR)^{T}b$
- $R^{T}Q^{T}QRx=R^{T}Q^{T}b$
- $Rx=Q^{T}b$
