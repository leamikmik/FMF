```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Definicija
$$A: U\to V$$
- $U, V$ => [[Vektorski prostori|vektorska prostora]]
- Lin preslikava če: $(x,y\in U; \alpha,\beta\in F)$
	1. $A(x+y)=A(x)+A(y)$ => **Aditivnost**
	2. $A(\alpha x)=\alpha A(x)$ => **Homogenost**
	- **Najlažje preveriti** -> $A(\alpha x+\beta y)=\alpha A(x)+\beta A(y)$
- Sledi pravilom [[2. Matematična analiza#Uvodna preslikava|osnove preslikave]]
- **Posebne preslikave**:
	1. Ničelna => $0:U\to V;\ 0(x)=0$
		- $\ker(0)=U$
		- $\text{im}(0)=\{0\}$
	2. Identična => $I:U\to U;\ I(x)=x$
		- $\ker(I)=\{0\}$
		- $\text{im}(I)=U$
## Matrika
- Preslikavo se lahko zapiše kot $\Bbb R^{m\times n}$ [[Matrike|matriko]] z katero <u>levo množimo</u> argument => $A(x)=A*x$
- ***i-ti stolpec mat $A$ je koeficient razvoja $A(u_{i})$ po bazi $V$***
- Matrika je odvisna od izbire baze
- $A_{B_{1}C_{1}}=P_{C_{2}C_{1}}*A_{B_{2}C_{2}}*P_{B_{1}C_{1}};\ B_{1,2}\ \text{baza}\ V, C_{1,2}\ \text{baza}\ U$
- Matriki sta si **podobni** ($A\sim B$) če $A=PBP^{-1}$ (ista preslikava, druga baza)
## Lastnosti
1. **Jedro** preslikave => $\ker(A) = \{x\in U;A(x)=0\} \le U$ 
	- A je *injektivna* => $\ker(A)=\{0\}$
2. **Slika** preslikave => $\text{im}(A)=\{y\in V; \exists x\in U \Rightarrow y=A(x)\}\le V$
	- A je *surjektivna* => $\text{im}(A)=V$
- *Jedro* in *sliko* dobimo z [[Sistem linearnih enačb#Gaussova eliminacija|gaussom]] mat. $A$:
	- $\text{im}$ -> vrstice matrike kjer so pivoti
	- $\ker$ -> rešitev gaussa
3. $\dim(U)=\dim(\ker(A))+\dim(\text{im}(A))$
4. $\text{rang}(A)=\dim(\text{im}(A))$ 
	- **Rang** lin. preslikave je enak rangu njene matrike. Vrednost je ista neglede na bazo
---
# Lastne vrednosti in vektorji
