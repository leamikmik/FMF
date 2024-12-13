```table-of-contents
title: # Kazalo
style: nestedOrderedList
```

---
# Definicija
$$M_{i\times j}=\left[\begin{matrix} m_{11} & \dots & m_{1j}  \\ \vdots & & \vdots \\ m_{i1} & \dots & m_{ij} \end{matrix}\right] \in \Bbb R^{i\times j}$$
- Matrika je **pravokotna tabela števil.**
- *[[Vektorji v R|Vektorji]] so matrike z enim stolpcem*  ($\Bbb R^{m\times1}$)
- Matrikam z $i=j$ rečemo [[#kvadratne matrike|kvadratne matrike]]
- Označimo jih z velikimi tiskanimi črkami.
- Matriki polni ničel rečemo ničelna matrika
- Če ima matrika $A$ **inverz** ($A*A^{-1}=I$) ji rečemo da je <u>obrnljiva</u>
---
# Operacije na matrikah
- **Seštevanje/Odštevanje** -> $A\pm B=\left[\begin{matrix} a_{11}\pm b_{11} & \dots & a_{1j}\pm b_{1j}  \\ \vdots & & \vdots \\ a_{i1}\pm b_{i1} & \dots & a_{ij}\pm b_{ij} \end{matrix}\right];\ A,B \in \Bbb R^{i\times j}$
- **Množenje z skalarjem** -> $\alpha*A=\left[\begin{matrix} \alpha*a_{11} & \dots & \alpha*a_{1j}  \\ \vdots & & \vdots \\ \alpha*a_{i1} & \dots & \alpha*a_{ij} \end{matrix}\right] \in \Bbb R^{i\times j};\ \alpha\in\Bbb R$
- **[[#Množenje matrik]]**
- [[#Transponiranje]]
## Množenje matrik
$$A\in\Bbb R^{m\times n};\ B\in\Bbb R^{n\times r};\ C=A*B \in\Bbb R^{m\times r}$$
- Število stolpcev prve matrike je enako številu vrstic druge matrice
- $c_{ij}=a_{i1}b_{1j}+\dots+a_{in}b_{nj}$ -> $1\le i\le m;\ 1\le j\le r$
- **$(i,j)$-ti element produkta matrik je skalarni produkt $i$-te vrstice $A$ in $j$-tega stolpca $B$**
## Transponiranje
- $A\in\Bbb R^{m\times n};\ B\in\Bbb  R^{n\times m}$
- Transporirana matrika je $B$, kjer velja da $b_{ij}=a_{ji}$ (*rotacija*)
- Označimo z $A^{T}$
- Če $A^T=A$ rečemo da je $A$ **simetrična** matrika
## Lastnosti operacij
### Seštevanje
1. $(A+B)+C=A+(B+C)$ -> Asociativnost
2. $A+0=A$
3. $A+(-A)=0$
4. $A+B=B+A$ -> Komutativnost
### Množenje
1. $A*B\ne B*A$
2. $(\alpha+\beta)A=\alpha A+\beta A$
3. $\alpha(A+B)=\alpha A+\alpha B$
4. $(\alpha \beta)A=\alpha(\beta A)$
5. $1*A=A$
6. $(A*B)*C=A*(B*C)$
7. $(AB)^{-1}=B^{-1}A^{-1}$
### Transponiranje
1. $(A^{T})^{T}=A$
2. $(A+B)^{T}=A^{T}+B^{T}$
3. $(\alpha A)^{T}=\alpha*A^{T}$
4. $(A*B)^{T}=B^{T}*A^{T}$
---
# Kvadratne matrike
$$A\in\Bbb R^{n\times n}$$
1. **skalarna matrika** => $\left[\begin{matrix} \alpha & 0 & \dots & 0  \\ 0 & \alpha & \ddots & \vdots \\ \vdots & \ddots & \ddots & 0 \\ 0 & \dots & 0 & \alpha \end{matrix}\right]$
2. **diagonalna matrika** => $\left[\begin{matrix} d_{1} & & \huge 0 \\ & \ddots &  \\ \huge 0 & & d_{n} \end{matrix}\right]$
3. **zgornje**-trikotna mat. => $\left[\begin{matrix} a_{11} & \dots & a_{1n} \\ & \ddots & \vdots \\ \huge 0 & & a_{nn} \end{matrix}\right]$
4. **spodnje**-trikotna mat. => $\left[\begin{matrix} a_{11} & & \huge 0 \\ \vdots & \ddots &  \\ a_{n1} & \dots & a_{nn} \end{matrix}\right]$
5. **Identiteta** => $I=\left[\begin{matrix}1&&\huge 0 \\ &\ddots& \\ \huge 0&&1\end{matrix}\right]$
- *Vsota in produkt zgornjih in spodnjih trikotnih mat. je tudi zgornja oz. spodnjo trikotna mat.*
---
# Vrstična kanonična forma 
$$A\in\Bbb R^{n\times m}$$
- Označimo kot $VKF(A)$
- **Pivot** -> prvi neničelni el. v vsaki vrstici
- **Rang** -> št. pivotov v dani matrici
## Elementarne transformacije
1. $E_{i,j}(\alpha)$ **Prištej skalarni večkratnik vrstice**:
	- $v'_{1}=v_{1}+2*v_{2}=[v_{11}+2*v_{21}\ \dots \ v_{1n}+2*v_{2n}]$
	- *Vsak člen posebej*
	- $\left[\begin{matrix} 1 & \alpha_{ji} & \huge 0 \\ & \ddots &  \\ \huge 0 & & 1 \end{matrix}\right]$
	- $E_{i,j}(\alpha)^{-1}=E_{i,j}(-\alpha)$
1. $F_i(\alpha)$ **Dano vrstico pomnoži z nenič. skalarjem**:
	- $v'=\alpha*v=[v_{1}*\alpha\ \dots\ v_{n}*\alpha]$
	- $\left[\begin{matrix}1 & & \huge 0\\ & \alpha_{ii}& \\ \huge 0 & & 1 \end{matrix}\right]$
	- $F_{i}(\alpha)^{-1}=F_{i}(\frac{1}{\alpha})$
1. $P_{i,j}$ **Zamenjaj 2 vrstici**:
	- $v_{x}\leftrightarrow v_{y}$
	- $\left[\begin{matrix} 1 & 1_{ij} & \huge 0 \\ & \ddots & 1_{ji} \\ \huge 0 & & 1 \end{matrix}\right]$
	- $P_{i,j}^{-1}=P_{i,j}$
## Pravila
- *prvi neničelni el. v vsaki vrsti je $1$ (t.j. imenovan **pivot**)*
- *prvi neničelni el. v naslednji vrstici je bolj "desno" od prejšnjega*
- *v stolpcu kjer se nahaja pivot, je le ta edini nenič. el.*
- *vse čisto ničelne vrstice se nahajajo na dnu*
## Preobrazba
1. Začni $i=j=1$
	- Če $a_{ij}=0$:
		- Če $a_{kj}=0$ za vsak $k>i$, povečaj $j$ za $1$
		- Če obstaja $k>i$, da je $a_{kj}\ne 0$, potem zamenjaj $i$-to in $k$-to vrstico
	- Če $a_{ij}\ne0$ 
		- Potem $k$-ti vrstici prištej primeren večkratnik $i$-te vrstice (tako da bo el. na mestu $a_{kj}=0$ za vse $k=i+1;\ k\le m$)
	- Nato povečaj $i$ in $j$ za $1$, dokler ne pade iz matrike ($i>n$ ali $j>m$)
2. Vrstice pomnoži z skalarji, da bodo vsi pivoti $1$
3. Pridelaj še $0$ nad pivoti s prištevanjem večkratnika pivotne vrstice
## Primer
$$A=\left[\begin{matrix}1&0&-2&1&0\\0&-1&-3&1&3\\-2&-1&1&-1&3\\0&3&9&0&-12\end{matrix}\right]$$
$$VKF(A)=\left[\begin{matrix} 1&0&-2&0&-1\\0&1&3&0&-4\\0&0&0&1&-1\\0&0&0&0&0 \end{matrix}\right]$$
$$rang(A)=3$$
---
