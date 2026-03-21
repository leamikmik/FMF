```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Uvod
- Potrebujemo vsaj 4 točke (oz. $y,b\in\Bbb R^{m};\ m>4$)
- Iščemo $p(y):=x_{1}+x_{2}y_{i}+x_{3}y_{i}^{2}+x_{4}y_{i}^{3}=b_{i}$
	- Oz. $Ax=b$ kjer $A=\left[\begin{matrix}1 & y_{1} & y_{1}^{2} & y_{1}^{3} \\ \vdots & \vdots & \vdots & \vdots \\ 1 & y_{m} & y_{m}^{2} & y_{m}^{3}\end{matrix}\right]$ in $x=\left[\begin{matrix}x_{1} \\ x_{2} \\ x_{3} \\ x_{4}\end{matrix}\right]$
		- $\text{rang}(A)=n$
	- Imamo več enačb kot neznanko torej je *predoločen sistem*
- $x$ je *rešitev po metodi najmanjših kvadratov*
- Ne splača delati sistema, torej vzamemo tak $x$, da $\|Ax-b\|_{2}$ čim manjše
	- oz. $\sum\limits_{i=1}^{m}(p(y_{i})-b_{i})^{2}$ minimalno
---
# Normalni sistemi
$$\min\|Ax-b\|_{2};\ A\in\Bbb R^{m\times n}, b\in\Bbb R^{m},x\in\Bbb R^{n}$$
- $m\ge n$
- Ubistvu iščemo vektor $Ax$ iz podp. $\text{im}(A)$
	- Rešitev => prav. projekcija $b$ na $\text{im}(A)$
- oz. $A^{T}Ax=A^{T}b$ => **normalni sistem**
- Ker je $A^{T}A$ pozitivno definitna lahko uporabimo [[2. letnik/Numericne metode/Sistem linearnih enačb#Simetrične matrike|razcep Choleskega]]
	- $n^{2}m+ \frac{1}{3}n^{3}+O(n^{2})$ operacij
- Najpreprostejši način reševanja, ni pa najstabilnejši.
	- Če stolpci $A$ niso dovolj linearno neodvisni, lahko uporabimo boljšo bazo za $\text{im}(A)$
---
# QR razcep
- $A\in\Bbb R^{m\times n}, m\ge n$ in $\text{rang}(A)=n$
- razcep => $A=QR$ kjer $Q\in\Bbb R^{m\times n}$ pravokotna matrika z ortobnomiranimi stolpci in $R\in\Bbb R^{n\times n}$ zgornje trikotna matrika s pozitivnimi diagonalnimi el.
	- Enoličen razcep
- Potem je naš sistem $Rx=Q^{T}b$
- Lahko uporabimo [[#Algoritem|Gram-Schimotovo]] ortogonalizacijo stolpcev matrike $A$
	- *Klasična GS metoda* => CGS
	- *Modificirana GS metoda* => MGS
		- Računamo $\bar Q\bar R$ razcep razširjene matrike $[\begin{matrix}A & b\end{matrix}]$
			- $\bar Q = [\begin{matrix}Q & q_{n+1}\end{matrix}]$
			- $\bar R=\left[\begin{matrix}R & z \\  & \rho\end{matrix} \right];\ z\in\Bbb R^{n}$
		- Nato rešujemo $Q(Rx-z)-\rho q_{n+1}$, ki ima minimum pri $Rx=z$
	- MGS stabilnejši od CGS
	- Število operacij je $2mn^{2}$
## Razširjeni $QR$ razcep
$$A=\bar Q\bar R$$
- $\bar Q\in\Bbb R^{m\times m}$ ortogonalna, $\bar R\in\Bbb R^{m\times n}$ zgornja trapezna matrika
- Prvih $n$ stolpcev $\bar Q=Q$ in $\bar R=\left[\begin{matrix}R \\ 0\end{matrix}\right]$ 
- **Tudi razširjeni $QR$ razcep bomo ponavadi imenovali kar $QR$ razcep**
## Algoritem
- vhod $A$ izhod $QR$
- **Gran-Schimitov algoritem**
```
for k=1:n
	q_k = a_k
	for i=1:k-1
		r_ik = q_i^T * a_k (CGS) oz. q_i^T * q_k (MGS)
		q_k = q_k - r_ik * q_i
	end
	r_kk = ||q_k||_2
	q_k = q_k / r_kk
end
```
---
# Givensove rotacije
- Vektor $x\in\Bbb R^{n}$ sučemo za kot $\varphi$ v negativni smeri, če ga množimo z ortagonalno matriko $R^{T}=\left[\begin{matrix}c & s \\ -s & c\end{matrix}\right]$
- **Beri pazljivo, saj je matrika včasih transponirana** (zamenjata se samo $s$ in $-s$)
	- $c:=\cos\varphi$
	- $s:=\sin\varphi$
- $R_{ik}$ je sestavljen:
	- $r_{jj}=1;\ j\ne i,k$
	- $r_{jj}=c;\ j=i,k$
	- $r_{ki}=-r_{ik}=s$
- Če pomnožimo matriko $A\in\Bbb R^{m\times n}$ z $R_{ik}^{T}$ se spremenita samo $i$-ta in $k$-ta vrstica
	- Če hočemo uničiti $a_{ki}$ potem za $R_{ik}^{T}$ nastavimo:
		- $r=\sqrt{a^{2}_{ii}+a^{2}_{ki}}$
		- $c= \frac{a_{ii}}{r}$
		- $s= \frac{a_{ki}}{r}$
	- Če $A$ uničimo vse poddiagonalne elemente dobimo matriko $\bar R\left[\begin{matrix}R \\ 0\end{matrix}\right]$
	- Za $Q$ pa dobimo produkt $\bar Q=R_{12}R_{13}\dots R_{nm}$ (vseh rotacij ki smo uporabili za $\bar R$), kjer je $Q$ enak prvih $n$ stolpcev
	- S tem sistemom lahko dobimo $QR$ razcep
- Če uporabimo ta sistem za reševanje $Ax=b$ ne potrebujemo $Q$ iz $QR$ razcepa
	- Samo v vsakem koraku $b$ pomnožimo z $R_{ik}^{T}$
	- Na koncu dobimo $\bar Q^{T}b$ in vzamemo prvih $n$ elementov tj. $Rx=\bar Q^{T}x(1:n)$
	- Potrebno $3mn^{2}-n^{3}$ operacij
## Algoritem
- Vhod $A$, izhod $\bar R$ in po želji $\bar Q$ in $\bar Q^{T}b$
```
Q = I_m (če iščemo \bar Q)
for j = 1:n
	for k = j+1:m
		r = \sqrt{a_jj^2 + a_kj^2}
		if r > 0:
			c = a_jj / r
			s = a_kj / r
			A([j k], j:n) = R^T A([j k], j:n)
			b([j k]) = R^T b([j k]) (če iščemo \bar Q^T * b)
			Q(1:m, [j k]) = Q(1:m, [j k]) R^T (če iščemo \bar Q)
	end
end
```
- Izračun $\bar Q$ vzame dodatnih $6m^{2}n-3mn^{2}$ operacij
- Sistem lin. enačb velikosti $n\times n$ lahko rešimo z $2n^{3}+O(n^{2})$ operacijami oz. dodatnih $3n^{3}+O(n^{2})$ če še iščemo $\bar Q$
---
# Householderjeva zrcaljenja
$$P=I- \frac{2ww^{T}}{w^{T}w}$$
- kjer je $w\in\Bbb R^{n}$ neničelni vektor 
- $P$ predstavlja zrcaljenje preko hiperravnine, ki je ortogonalna na vektor $w$
	- $P=P^{T}$ in $P^{2}=I$ (oz. simetrična in ortogonalna)
- $\forall x\in\Bbb R^{n}$ lahko predstavimo z $x=\alpha w+u;\ u\perp w$
	- oz. preslikavo $Px=-\alpha w+u$
- Zrcalimo z $Px=x- \frac{1}{m}(x^{T}w)w$ 
	- $m= \frac{1}{2}w^{T}w$
	- Dela tudi za matrike
	- Ne rabimo računati $P$ iščemo samo $w$
	- $\|Px\|_{2}=\|x\|_{2}$
- Za nas je dobra preslikava, ki vektor $x$ preslika v $\left[\begin{matrix}\pm\|x\|_{2} \\ 0\end{matrix}\right]$
	- $w= x+\text{sign}(x_{1})\|x\|_{2}e_{1}$
		- $\text{sign}(0)=1$ (signatura od nič drugače definirana kot v MATLAB)
	- $m=\|x\|_{2}(\|x\|_{2}+|x_{1}|)$
	- Za izračun $Px$ potrebno $4n+O(1)$ operacij
		- Za $w$ in $m$ pa $2n+O(1)$
	- Z tem lahko izračunamo $\bar R$ iz razširjenega $QR$ razcepa
- Za $Ax=b$ potrebno $2mn^{2}- \frac{2}{3}n^{3}$ operacij
- Za polno matriko je Householderjevo zrcaljenje učinkovitejšo od Givensovih rotacij
- $n\times n$ sistem uzame $\frac{4}{3}n^{3}$ operacij
## Algoritem
- Vhod $A\in\Bbb R^{m\times n}$, izhod $\bar R$ in po potrebi $\bar Q$ in $\bar Q^{T}b$
```
Q = I_m 
for i = 1:n
	določi w_i v R^{m-i+1}, ki prezrcali A(i:m, i) v \pm k*e_1
	A(i:m, i:n) = P_i * A(i:m, i:n)
	b(i:m) = P_i * b(i:m)  (če rešujemo Ax = b)
	Q(i:m, 1:n) = P_i * Q(i:m, 1:n)  (če iščemo \bar Q)
end
Q = Q^T
```
- Za $\bar Q$ potrebnih ekstra $4m^{2}n-2mn^{2}$