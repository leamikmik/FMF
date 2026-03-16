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
