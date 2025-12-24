
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
	- $\frac{\|\delta x\|}{\|x\|}\le \frac{\kappa(A)}{1-\kappa(A) \frac{\|\delta A\|}{\|A\|} }(\frac{\|\delta A\|}{\|A\|}+\frac{\|\delta b\|}{\|b\|})\approx \kappa(A)*2\epsilon$
	- $\kappa(A)=\|A\|*\|A^{-1}\|$ -> Pogojenostno stevilo matrike 
		- ce je stevilo veliko lahko kljub majhnim relativnim napakam s podatki dobimo visoko relativno napako resitve
		- matrikam ki imajo veliko pogojenostno stevilo recemo OBCUTLJIVE

- direktna stabilnost ...
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
- ```
  for j=1:n
	  v_jj = sqrt(a_jj - sum_k=1^j-1(v_jk^2) )
	  for i=j+1:n
		  v_ij = 1/v_jj (a_ij - sum_k=1^j-1(v_jk * v_ik) )
	  end
end
  ```