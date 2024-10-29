```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Definicija
$$M_{i\times j}=\left[\begin{matrix} m_{11} & \dots & m_{1j}  \\ \vdots & & \vdots \\ m_{i1} & \dots & m_{ij} \end{matrix}\right] \in \Bbb R^{i\times j}$$
- Matrika je **pravokotna tabela števil.**
- *[[Vektorji v R|Vektorji]] so matrike z enim stolpcem*  ($\Bbb R^{m\times1}$)
- Matrikam z $i=j$ rečemo *kvadratne matrike*
- Označimo jih z velikimi tiskanimi črkami.
- Matriki polni ničel rečemo ničelna matrika
---
# Operacije na matrikah
- **Seštevanje/Odštevanje** -> $A\pm B=\left[\begin{matrix} a_{11}\pm b_{11} & \dots & a_{1j}\pm b_{1j}  \\ \vdots & & \vdots \\ a_{i1}\pm b_{i1} & \dots & a_{ij}\pm b_{ij} \end{matrix}\right];\ A,B \in \Bbb R^{i\times j}$
- **Množenje z skalarjem** -> $A=\left[\begin{matrix} \alpha*a_{11} & \dots & \alpha*a_{1j}  \\ \vdots & & \vdots \\ \alpha*a_{i1} & \dots & \alpha*a_{ij} \end{matrix}\right] \in \Bbb R^{i\times j};\ \alpha\in\Bbb R$
- **[[#Množenje matrik]]**
## Množenje matrik
- $A\in\Bbb R^{m\times n};\ B\in\Bbb R^{n\times r};\ C=A*B \in\Bbb R^{m\times r}$
	- Število stolpcev prve matrike je enako številu vrstic druge matrice
- $c_{ij}=a_{i1}b_{1j}+\dots+a_{in}b_{nj}$ -> $1\le i\le m;\ 1\le j\le r$
- **$(i,j)$-ti element produkta matrik $A,\ B$ je skalarni produkt $i$-te vrstice $A$ in $j$-tega stolpca $B$**
## Lastnosti operacij
1. $(A+B)+C=A+(B+C)$ -> Asociativnost
2. $A+0=A$
3. $A+(-A)=0$
4. $A+B=B+A$ -> Komutativnost
5. $(\alpha+\beta)A=\alpha A+\beta A$
6. $\alpha(A+B)=\alpha A+\alpha B$
7. $(\alpha \beta)A=\alpha(\beta A)$
8. $1*A=A$
9. $(A*B)C=A(B*C)$
