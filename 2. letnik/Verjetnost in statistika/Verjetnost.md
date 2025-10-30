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
## Pravila računanja
- *Idempotentnost* -> $A+A=A,AA=A$
- *Komutativnost* -> $A+B=B+A,AB=BA$
- *Asociativnost* -> $(A+B)+C=A+(B+C),(AB)C=A(BC)$
- *Distributivnost* -> $(A+B)C=AC+BC,AB+C=(A+C)(B+C)$
- *De Morganov zakon* -> $\overline{(A+B)}=\bar A \bar B,\overline{(AB)}=\bar A+\bar B$