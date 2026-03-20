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
- Lahko uporabimo **Gram-Schimotovo** ortogonalizacijo stolpcev matrike $A$
	- *Klasična GS metoda* => CGS
	- *Modificirana GS metoda* => MGS
		- Računamo $\bar Q\bar R$ razcep razširjene matrike $[\begin{matrix}A & b\end{matrix}]$
			- $\bar Q = [\begin{matrix}Q & q_{n+1}\end{matrix}]$
			- $\bar R=\left[\begin{matrix}R & z \\  & \rho\end{matrix} \right];\ z\in\Bbb R^{n}$
		- Nato rešujemo $Q(Rx-z)-\rho q_{n+1}$, ki ima minimum pri $Rx=z$
	- MGS stabilnejši od CGS
	- ```
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
	- Število operacij je $2mn^{2}$
- Poznamo še *razširjeni $QR$ razcep* => $A=\bar Q\bar R$
	- $\bar Q\in\Bbb R^{m\times m}$ ortogonalna, $\bar R\in\Bbb R^{m\times n}$ zgornja trapezna matrika
	- Prvih $n$ stolpcev $\bar Q=Q$ in $\bar R=\left[\begin{matrix}R \\ 0\end{matrix}\right]$ 
	- **Tudi razširjeni $QR$ razcep bomo ponavadi imenovali kar $QR$ razcep**
---
# Givensove rotacije
- 

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
