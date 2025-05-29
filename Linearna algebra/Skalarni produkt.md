```table-of-contents
title: # Kazalo
style: nestedOrderedList
```

---
# Definicija
$$\left<\ ,\ \right>:V\times V\to\Bbb C;\ V\subseteq\Bbb C$$
- je skalarni produkt če **veljajo [[#Lastnosti skalarnega produkta|prve 3 lastnosti]]**
- [[Vektorji v R#Norma|Norma]] => $\|\vec a\|=\sqrt{\left<\vec a, \vec b\right>}$
- *Vektorja sta pravokotna (**ortagonalna**) če* $\left<\vec a,\vec b\right>=0$
	- $\vec a$ in $\vec b- \frac{<\vec a,\vec b>}{<\vec a,\vec a>}\vec a$ sta pravokotna
- Lahko zapisemo $\left<\vec a, \vec b\right>=\vec a^{T}*S*\vec b$
	- $S^{T}=S$, $S$ je strogo pozitivno definirana. (*Determinante glavnih minorjev strogo pozitivni*)
	- $S=\left[\begin{matrix} \left<\vec v_{1}, \vec v_{1}\right> & \dots & \left<\vec v_{1}, \vec v_{n}\right> \\ \vdots & \ddots & \vdots \\ \left<\vec v_{n}, \vec v_{1}\right> & \dots & \left<\vec v_{n}, \vec v_{n}\right> \end{matrix}\right]$, kjer je $\{\vec v_{1},\vec v_2,\dots\vec v_{n}\}$ baza za $V$
## Osnovna definicija
$$\left<\vec a, \vec b\right>=\sum\limits_{i=1}^{n}a_{i}b_{i}=a_{1}*b_{1}+a_{2}*b_{2}+\dots+a_{n}*b_{n}$$

---
# Lastnosti skalarnega produkta
1. $\left<\alpha*\vec a+\beta*\vec b,\vec c\right>=\alpha\left<\vec a,\vec c\right>+\beta\left<\vec b, \vec c\right>$ -> Linearnost v prvem faktorju
2. $\left<\vec a,\vec b\right>=\overline{\left<\vec b,\vec a\right>}$ -> Simetričnost (v $\Bbb C$ je [[1. Števila#Konjugacija|konjugirano]])
3. $\left<\vec a, \vec a\right>=\|\vec a\|^2\ge0$ -> Pozitivna definitnost
	- $\left<\vec a, \vec a\right>=0\iff \vec a=0$
4. $|\left<\vec a,\vec b\right>|\le\|\vec a\|*\|\vec b\|$ -> **Cauchy-schwartz izrek**
5. $\left<\vec a,\vec b\right>=\|\vec a\|*\|\vec b\|*\cos{\gamma}$
6. $\|\vec a+\vec b\|^{2}=\|\vec a\|^{2}+\|\vec b\|^{2}$ -> **Pitagorov izrek**
	- Samo če sta vektorja pravokotna
## Ortogonalnost
$$S^{\perp}=\{\vec a\in V;\ \left<\vec a, \vec b\right>=0;\ \forall b\in S\}$$
- Ortogonalna baza
- $S^{\perp}$ je [[Vektorski prostori#Vektorski podprostor|vektorski podprostor]] v $V$
	- $S^{\perp}$ rečemo "*$S$ ortagonalno*"
- Če tudi $\|\vec a_{i}\|=1$ je baza **ortonomirana** (*ON*)
- *V vsakem neničelnem vektorskem prostoru obstaja ortonomirana baza.*
- *Vsaka ortogonalna množica je linearno neodvisna.*
- **Postopek Gramm-Schmidotve ortogonalizacije**:
	1. $\{\vec v_{1},\vec v_2,\dots\vec v_{n}\}$ -> Baza
	2. $\vec w_{1}=\vec v_{1}$
	3. ...
	4. $\vec w_{k}=\vec v_{k}-\sum\limits^{k-1}_{i=1} \frac{<\vec v_{k}, \vec w_{i}>}{<\vec w_{i}, \vec w_{i}>}w_{i}$
	5. $\{\vec w_{1},\vec w_2,\dots\vec w_{n}\}$ -> <u>Ortogonalna</u> baza
	6. $\vec e_{i}= \frac{\vec w_{i}}{\|\vec w_{i}\|} \to  \{\vec e_{1},\vec e_2,\dots\vec e_{n}\}$ -> <u>Ortonomirana</u> baza
- Matrika za projekcijo na podprostor $U\subseteq\Bbb R^{n}$ => $Q*Q^{T};\ Q=[\vec e_{1},\vec e_2,\dots\vec e_{n}]$
- Vsak $x\in V$ lahko razvijemo z *ON*-bazo v.p. $V$ => $\vec x=\sum\limits^{n}_{i=1}\left<\vec x, \vec e_{i}\right>\vec e_{i}$
- Pravokotna projekcija vek. na podp. -> $\text{proj}_{U}(x)=\left< x, \vec e_{1}\right>e_{1}+\dots+\left< x, \vec e_{i}\right>e_{i}$
	- Aproksimacija $x$ v podp. $U$

---
# Linearni funkcionali
$$\varphi: V\to\Bbb C$$
- Linearna preslikava *iz vektorskega prostora* v $\Bbb C$ (oz. $\Bbb R$)
- **Rieszov izrek o lin. funkc.**
	- Naj ima $V$ skal. produkt in $\varphi: V\to\Bbb C$. Potem obstaja natanko **en** $v\in V$, ki izpolni $\varphi(x)=\left<\vec x, \vec v\right>;\ \forall x\in V$
	- $\vec v=\sum\limits^{n}_{i=1}\overline{\varphi(\vec e_{i})}\vec e_{i}$ za neko ON-bazo $\{\vec e_{1},\vec e_2,\dots\vec e_{n}\}$

---
# Adjungirana preslikava
$$$$
- 