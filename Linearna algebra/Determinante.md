```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Permutacije
- Na množici števil $\{1, 2,\dots, n\}$ je vsaka bijektivna preslikava iz te množice samo vase
- **Oznake**: $\Pi,\sigma,\dots$
- *Zapis*:
	1. $\Pi=\left(\begin{matrix} 1&2&3&\dots&n \\ \Pi(1)&\Pi(2)&\Pi(3)&\dots&\Pi(n) \end{matrix}\right)$
		- "$n$ postane preslikava $n$"
	2. $\Pi=(i_{1}i_{2}\dots i_{k})(j_{1}j_{2}\dots j_{l})$
		- $i_{1}\rightarrow i_{2}\dots i_{k}\rightarrow i_{1}$
		- $j_{1}\rightarrow j_{2}\dots j_{l}\rightarrow j_{1}$
		- **Cikel** => $(i_{1}i_{2}\dots i_{k})$
- Permutacijo vedno lahko zapišemo kot produkt <u>disjunktnih ciklov</u>
- **Transpozicija** je cikel *dolžine* $2$
- $S_{n}$ -> Množica vseh permutacij na množici $\{1, 2,\dots, n\}$
	- $|S_{n}|=n!$ -> število kombinacij permutacij
- **Index** => $ind(\Pi)$
	- Je <u>število inverzij</u> permutacije
	- **Inverzija** => Koliko preslikanih števil desno od gledanega elementa je manjših od elementa
- **Signatura**/predznak => $sgn(\Pi)=(-1)^{ind(\Pi)}$
	- Če je signatura $1$ je permutacija **soda**
- Če v spodnji vrstici permutacije <u>zamenjamo</u> dve števili, se signatura spremeni -> $sgn(\tilde\Pi)=-sgn(\Pi)$
- **Inverzna permutacija** => $\Pi^{-1}$
	- $ind(\Pi^{-1})=ind(\Pi)$
---
# Determinanta
$$\det(A)=\sum_{\Pi\in S_{n}}sgn(\Pi)*a_{1\Pi(1)}*\dots a_{n\Pi(n)}\in\Bbb R$$
- *V vsaki vrstici in v vsakem stolpcu vzamemo 1 element*
- $A\in\Bbb R^{n\times n}$
- **Označimo tudi** => $\det(A)=\left| \begin{matrix} a_{11}&\dots &a_{1n}\\\vdots&\ddots&\vdots \\ a_{n1}&\dots&a_{nn} \end{matrix} \right|$
- Determinanta **trikotne** matrike je <u>produkt</u> diagonalnih členov
## Razvoj
### n = 2
![[Pasted image 20241127131352.png]]
### n = 3
![[Pasted image 20241127131325.png]]
### n > 3
- **Minor** $m_{ij}$ -> Je determinanta matrike, v kateri <u>izbrišemo</u> $i$-to vrstico in $j$-ti stolpec
- **Kofaktor**  => $k_{ij}=(-1)^{i+j}*m_{ij}$

- $1\le i ,j\le n$
1. **Razvoj po $i$-ti vrstici**:
	- $\det(A)=\sum_{r=1}^{n}a_{ir}*k_{ir}$
2. **Razvoj po $j$-tem stolpcu**:
	- $\det(A)=\sum_{r=1}^{n}a_{rj}*k_{rj}$
- Razvijamo do $3\times 3$ matrike, potem z [[#n = 3|tem]]

## Lastnosti
1. $\det(A)=\det(A^{T})$
2. Če pomnožimo <u>vrstico/stolpec</u> s skalarjem, se determinanta pomnoži z enakim skalarjem
3. $\det(\alpha A)=\alpha^{n}\det(A);\ A\in\Bbb R^{n\times n}$
4. Če je vrstica/stolpec vsota dveh vektorjev, je tudi determinanta vsota dveh determinant, vsakič z ustreznim vektorjem
5. $\tilde A=A: v_{i}\leftrightarrow v_{j}\lor s_{i}\leftrightarrow s_{j};\ \det(\tilde A)=-\det(A)$
6. $v_{i}=v_{j}\lor s_{i}=s_{j};\ \det(A)=0$
7. Prištevanje vrstic/stolpcev determinante ne spremeni