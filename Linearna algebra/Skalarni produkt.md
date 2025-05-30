```table-of-contents
title: # Kazalo
style: nestedOrderedList
```

---
# Definicija
$$\left<\ ,\ \right>:V\times V\to\Bbb C;\ V\subseteq\Bbb C$$
- je skalarni produkt če **veljajo [[#Lastnosti skalarnega produkta|prve 3 lastnosti]]**
- [[Vektorji v R#Norma|Norma]] => $\| a\|=\sqrt{\left< a,  b\right>}$
- *Vektorja sta pravokotna (**ortagonalna**) če* $\left< a, b\right>=0$
	- $a$ in $b- \frac{< a, b>}{< a, a>} a$ sta pravokotna
- Lahko zapisemo $\left< a,  b\right>= a^{T}*S* b$
	- $S^{T}=S$, $S$ je strogo pozitivno definirana. (*Determinante glavnih minorjev strogo pozitivni*)
	- $S=\left[\begin{matrix} \left< v_{1},  v_{1}\right> & \dots & \left< v_{1},  v_{n}\right> \\ \vdots & \ddots & \vdots \\ \left< v_{n},  v_{1}\right> & \dots & \left< v_{n},  v_{n}\right> \end{matrix}\right]$, kjer je $\{ v_{1}, v_2,\dots v_{n}\}$ baza za $V$
## Osnovna definicija
$$\left< a,  b\right>=\sum\limits_{i=1}^{n}a_{i}b_{i}=a_{1}*b_{1}+a_{2}*b_{2}+\dots+a_{n}*b_{n}$$

---
# Lastnosti skalarnega produkta
1. $\left<\alpha* a+\beta* b, c\right>=\alpha\left< a, c\right>+\beta\left< b,  c\right>$ -> Linearnost v prvem faktorju
2. $\left< a, b\right>=\overline{\left< b, a\right>}$ -> Simetričnost (v $\Bbb C$ je [[1. Števila#Konjugacija|konjugirano]])
3. $\left< a,  a\right>=\| a\|^2\ge0$ -> Pozitivna definitnost
	- $\left< a,  a\right>=0\iff  a=0$
4. $|\left< a, b\right>|\le\| a\|*\| b\|$ -> **Cauchy-schwartz izrek**
5. $\left< a, b\right>=\| a\|*\| b\|*\cos{\gamma}$
6. $\| a+ b\|^{2}=\| a\|^{2}+\| b\|^{2}$ -> **Pitagorov izrek**
	- Samo če sta vektorja pravokotna
## Ortogonalnost
$$S^{\perp}=\{ a\in V;\ \left< a,  b\right>=0;\ \forall b\in S\}$$
- Ortogonalna baza
- $S^{\perp}$ je [[Vektorski prostori#Vektorski podprostor|vektorski podprostor]] v $V$
	- $S^{\perp}$ rečemo "*$S$ ortagonalno*"
- Če tudi $\| a_{i}\|=1$ je baza **ortonomirana** (*ON*)
- *V vsakem neničelnem vektorskem prostoru obstaja ortonomirana baza.*
- *Vsaka ortogonalna množica je linearno neodvisna.*
- **Postopek Gramm-Schmidotve ortogonalizacije**:
	1. $\{ v_{1}, v_2,\dots v_{n}\}$ -> Baza
	2. $w_{1}= v_{1}$
	3. $w_{2}= v_{2}- \frac{< v_{2},  w_{1}>}{< w_{1}, w_{1}>} w_{1}$
	4. ...
	5. $w_{k}= v_{k}-\sum\limits^{k-1}_{i=1} \frac{< v_{k},  w_{i}>}{< w_{i},  w_{i}>}w_{i}$
	6. $\{ w_{1}, w_2,\dots w_{n}\}$ -> <u>Ortogonalna</u> baza
	7. $e_{i}= \frac{ w_{i}}{\| w_{i}\|} \to  \{ e_{1}, e_2,\dots e_{n}\}$ -> <u>Ortonomirana</u> baza
- Matrika za projekcijo na podprostor $U\subseteq\Bbb R^{n}$ => $Q*Q^{T};\ Q=[ e_{1}, e_2,\dots e_{n}]$
- Vsak $x\in V$ lahko razvijemo z *ON*-bazo v.p. $V$ => $x=\sum\limits^{n}_{i=1}\left< x,  e_{i}\right> e_{i}$
- Pravokotna projekcija vek. na podp. -> $\text{proj}_{U}(x)=\left< x,  e_{1}\right>e_{1}+\dots+\left< x,  e_{i}\right>e_{i}$
	- Aproksimacija $x$ v podp. $U$
- Lastni vek. **simetričnih ali hermitskih** matrik so (pri različnih last. vrednosih) ortagonalni.
	- Za take matriko obstaja ON-baza iz lastnih vektorjev
	- Matrika je v tej bazi diagonalna ($A=PDP^{T}$)
	- Če ima lastna vrednost več vektorjov, ju ortogonaliziramo z Gramm-Schmid.

---
# Linearni funkcionali
$$\varphi: V\to\Bbb C$$
- Linearna preslikava *iz vektorskega prostora* v $\Bbb C$ (oz. $\Bbb R$)
- **Rieszov izrek o lin. funkc.**
	- Naj ima $V$ skal. produkt in $\varphi: V\to\Bbb C$. Potem obstaja natanko **en** $v\in V$, ki izpolni $\varphi(x)=\left< x,  v\right>;\ \forall x\in V$
	- $v=\sum\limits^{n}_{i=1}\overline{\varphi( e_{i})} e_{i}$ za neko ON-bazo $\{ e_{1}, e_2,\dots e_{n}\}$

---
# Adjungirana preslikava
$$U\to V\to\Bbb C;\ u\to Au\to\left<Au,v\right>$$
- $U, V$ vektorska prostora z skal. produktom
- $A:U\to V$; $\varphi:U\to\Bbb C;\varphi(u)=\left<Au,v\right>$
- Preslikavo $A^{*}:V\to U$ imenujemo **adjungirana preslikava** preslikave $A$
	- $\varphi(u)=\left<Au,v\right>=\left<u,A^{*}v\right>$
- $A^{*}$ je linearna preslikava (*aditivnost in homogenost*)
- Če imamo ON-bazi $B,C$ za $U,V$:
	- $A_{BC}=\left[\begin{matrix} \left<A b_{1},  c_{1}\right> & \dots & \left<A b_{n},  c_{1}\right> \\ \vdots & \ddots & \vdots \\ \left< Ab_{1},  c_{n}\right> & \dots & \left< Ab_{n},  c_{n}\right> \end{matrix}\right]$
	- $A^{*}_{CB}=\left[\begin{matrix} \left<A^{*} c_{1},  b_{1}\right> & \dots & \left<A^{*} c_{n},  b_{1}\right> \\ \vdots & \ddots & \vdots \\ \left< A^{*}c_{1},  b_{n}\right> & \dots & \left< A^{*}c_{n},  b_{n}\right> \end{matrix}\right]$
	- $(i,j)$-ti el. v $A_{BC}$ je enak **konjugirano** $(j,i)$-temu el. v $A^{*}_{CB}$
- $A^{*}_{i,j}=\overline{A^{T}_{i,j}}$ (Matrika $A^{*}$ v ON-bazi je enaka transponirani in po elementih konjugirani matriki $A$)
1. **Sebiadjungirana** matrika -> $A=A^{*}$
2. **Normalna** matrika -> $A*A^{*}=A^{*}*A 
3. **Unitarna** matrika -> $AA^{*}=A^{*}A=I$
	- Če $AA^{T}=I$ je $A$ ortogonalna
	- Za te matrike obstaja ON-baza iz last. vektorjev, vse lastne vrednosti pa so absolutno enake $1$
4. **Pozitivno definitne** matrike ->$A=A^{*}$ in $\left<Au,u\right>>0;\ \forall u\ne0$
	- Simetrična oz. hermitska matrika je pozitivno definitna natanko, ko so vse lastne vrednosti pozitivne
## Lastnosti
1. $(A+B)^{*}=A^{*}+B^{*}$
2. $(\alpha A)^{*}=\bar\alpha A^{*}$
3. $(AB)^{*}=B^{*}A^{*}$
4. $(A^{*})^{*}=A$
5. Če je $A$ obrnljvia => $(A^{*})^{-1}=(A^{-1})^{*}$
6. $\ker(A^{*})=(\text{im }A)^{\perp}$ in $\text{im}(A^{*})=(\ker A)^{\perp}$
	- Posledica -> $U=\ker(A)\oplus\text{im}(A^{*})$ in $V=\text{im}(A)\oplus\ker(A^{*})$
7. $\alpha$ je lastna vrednost od $A$, natanko ko je $\bar\alpha$ lastna vrednost $A^{*}$