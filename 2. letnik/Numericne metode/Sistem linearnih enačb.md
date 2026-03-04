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
## Obcustljivost sistemov linearnih enacb
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
# Sistem lin enacb s posebno obliko
- tridiagonalne matrike
- pasovne matrike
- kompleksne
- razprsene
- simetricne pozitivno definitne
## simetricne pozitivno definitne
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
