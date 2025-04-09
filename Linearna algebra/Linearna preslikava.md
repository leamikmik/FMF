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
2. **Slika** preslikave ($Z_{f}$) => $\text{im}(A)=\{y\in V; \exists x\in U \Rightarrow y=A(x)\}\le V$
	- A je *surjektivna* => $\text{im}(A)=V$
- *Jedro* in *sliko* dobimo z [[Sistem linearnih enačb#Gaussova eliminacija|gaussom]] mat. $A$:
	- $\ker$ -> rešitev gaussa
	- $\text{im}$ -> vrstice matrike kjer so pivoti
3. $\dim(U)=\dim(\ker(A))+\dim(\text{im}(A))$
4. $\text{rang}(A)=\dim(\text{im}(A))$ 
	- **Rang** lin. preslikave je enak rangu njene matrike. Vrednost je ista neglede na bazo
---
# Lastne vrednosti in vektorji
$$A\in\Bbb C^{n\times n};\ Ax=\lambda x;\ (A-\lambda I)x=0$$
- $\lambda\in\Bbb C$ => **lastna vrednost** matrike $A$, če $\exists x\ne0;\ Ax=\lambda x$
	- $A-\lambda I$ => ni obrnljiva
	- $\det(A-\lambda I)=0$
	- Če $A\in\Bbb R^{n\times n}; Ax=\lambda x \Leftrightarrow A\bar x=\bar\lambda\bar x$ ([[1. Števila#Kompleksna števila#Konjugacija|Konjugacija]])
- $x\in\Bbb C^{n}$ => **lastni vektor** matrike $A$, pri last. vrednosti $\lambda$
	- $x\in\ker(A-\lambda I)$ => **lastni podprostor** pri last. vrednosti $\lambda$ (vsebuje vse last. vektorje pri last. vrednosti $\lambda$ in $\vec 0$)
	- Lastni vektorji *niso enolični*, torej ponavadi iščemo bazo od $\ker(A-\lambda I)$
- $p_{A}(x)=\det(A-xI)$ => **karakteristični polinom** (stopnje $n$)
	- <u>Ničle</u> polinoma so *last. vrednosti*
	- Podobni matriki imata ista polinoma (torej iste *last. vrednosti*)
		- NE velja obratno
	- $(-1)^{n}\lambda^{n}+(-1)^{n-1}\text{sled}(A)\lambda^{n-1}+\dots+\det(A)$
	- ***Cayley-Hamilton izrek*** => $p_{A}(A)=0$
	- $m_{A}(p)$ je <u>minimalni</u> polinom, če je vodilni koef. $1$ in je med vsemi poli. ki **uničijo matriko** najmanjše stopnje
		- $m_{A}(p)\mid p_{A}(x);p_{A,v}(x)\mid m_{A}(p)$
		- Min. polinom in karak. polinom imata iste ničle (lahko različna večkratnost)
- $p_{A,v}(x)=x^{k}-\alpha_{k-1}x^{k-1}+\dots+\alpha_{0}$ => **matrični polinom**
	- <u>Minimalni polinom za vektor</u> $0\ne v\in\Bbb C^{n}$ glede na mat. $A$
	- Sistem rešitev -> $\left[v\shortmid Av \shortmid A^{2}v\shortmid\dots\shortmid A^{k}v\right]$ ($k$ dokler so lin neodvisni)
	- $p_{A,v}(A)*v=0$
	- Če $(A-\alpha I)u=0\Rightarrow p_{A,u}(x)=x-\alpha$
	- $p_{A}(x)\mid p_{A,v}(x)$
- $C(p)=\left[\begin{matrix}0 && \huge 0 & -a_{0} \\ 1 & \ddots &&-a_{1} \\ &\ddots &0&\vdots \\ \huge 0&&1&-a_{k-1}\end{matrix}\right]\in\Bbb C^{k\times k}$ => **pridružena matrika polinoma**
	- $p(x)=x^{k}-\alpha_{k-1}x^{k-1}+\dots+\alpha_{0};\ k\in\Bbb N$
		- $p(x)=x-\alpha\Rightarrow C(p)=[-\alpha]$
	- $p_{C(p})(x)=\det(C(p)-xI)=(-1)^{k}p(x)$
- $a(\lambda)$ => **algebraična večkratnost** (stopnja ničle)
- $g(\lambda)=\dim(\ker(A-\lambda I))$ => **geometrična večkratnost** (velikost podprostora)
	- Pove nam koliko lin. neodvisnih last. vekt. lahko najdemo pri $\lambda$
	- $g(\lambda)=n-\text{rang}(A-\lambda I)$
## Diagonalizacija
$$A_{B}=\left[\begin{matrix} \lambda_{1} & & \huge 0 \\ & \ddots &  \\ \huge 0 & & \lambda_{n} \end{matrix}\right]=B^{-1}AB$$
- $A$ se da diagonalizirati če obstaja baza $B$ sestavljena iz last. vekt.
	- Če ima mat. $A$ $n$ različnih last. vrednosti, se da diagonalizirati
	- Če $g(\lambda)=a(\lambda);\ \forall\lambda$
- Če se ne da diagonalizirati, lahko naredimo *zgornje-trikotno*, pri tem so na diagonali lastne vrednosti.
	- Vrstni red lastnih vrednosti je poljuben (**Schurov izrek**)
---