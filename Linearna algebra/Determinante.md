```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Permutacije
- Na množici števil $\{1, 2,\dots, n\}$ je vsaka bijektivna preslikava iz te množice samo vase
- **Oznake**: $\pi,\sigma,\dots$
- *Zapis*:
	1. $\pi=\left(\begin{matrix} 1&2&3&\dots&n \\ \pi(1)&\pi(2)&\pi(3)&\dots&\pi(n) \end{matrix}\right)$
		- "$n$ postane preslikava $n$"
	2. $\pi=(i_{1}i_{2}\dots i_{k})(j_{1}j_{2}\dots j_{l})$
		- $i_{1}\rightarrow i_{2}\dots i_{k}\rightarrow i_{1}$
		- $j_{1}\rightarrow j_{2}\dots j_{l}\rightarrow j_{1}$
		- **Cikel** => $(i_{1}i_{2}\dots i_{k})$
- Permutacijo vedno lahko zapišemo kot produkt <u>disjunktnih ciklov</u>
- **Transpozicija** je cikel *dolžine* $2$
- $S_{n}$ -> Množica vseh permutacij na množici $\{1, 2,\dots, n\}$
	- $|S_{n}|=n!$ -> število kombinacij permutacij
- **Index** => $ind(\pi)$
	- Je <u>število inverzij</u> permutacije
	- **Inverzija** => Koliko preslikanih števil desno od gledanega elementa je manjših od elementa
- **Signatura**/predznak => $sgn(\pi)=(-1)^{ind(\pi)}$
	- Če je signatura $1$ je permutacija **soda**
- Če v spodnji vrstici permutacije <u>zamenjamo</u> dve števili, se signatura spremeni -> $sgn(\tilde\pi)=-sgn(\pi)$
- **Inverzna permutacija** => $\pi^{-1}$
	- $ind(\pi^{-1})=ind(\pi)$