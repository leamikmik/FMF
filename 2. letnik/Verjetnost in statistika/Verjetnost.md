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
- **Pravila računanja:**
	- *Idempotentnost* -> $A+A=A,AA=A$
	- *Komutativnost* -> $A+B=B+A,AB=BA$
	- *Asociativnost* -> $(A+B)+C=A+(B+C),(AB)C=A(BC)$
	- *Distributivnost* -> $(A+B)C=AC+BC,AB+C=(A+C)(B+C)$
	- *De Morganov zakon* -> $\overline{(A+B)}=\bar A \bar B,\overline{(AB)}=\bar A+\bar B$
- Neprazna družina dogodkov (podmnožic) $D$ v $G$ je **$\sigma$-algebra** če
	- $A\in D\Rightarrow \bar A\in D$ (če imamo nek dogodek obstaja njegovo nasprotje)
	- $\{A_{i}\}\subset\forall i=1,2,...\Rightarrow\sum\limits^{\infty}_{i=1}A_{i}\in D$ (če imamo več različnih dogodkov, obstaja tak dogodek, kjer se zgodi vsaj en od teh dogodkov)
## Definicija verjetnosti in lastnosti
- $D$ poljubna $\sigma$-algebra v $G$, **verjetnost** na $G$ je preslikava $P:D\to\Bbb R$:
	- $P(A)\ge0$
	- $P(G)=1$
	- $P(A_{1}+A_{2}+\dots)=P(A_{1})+P(A_{2})+\dots$ (če so $A_{i}$ paroma nezdružljivi)
- Zgornjim lastnostim rečemo *aksiomi Kolmogorova*. Iz njih izhajajo še naslednje lastnosti:
	1. $P(N)=0$
	2. $A\subset B\Rightarrow P(A)\le P(B)$
	3. $P(\bar A)=1-P(A)$
	4. $P(A+B)=P(A)+P(B)-P(AB)$ (Vsota poljubnih dogodkov)
		- $P(A+B+C)=P(A)+P(B)+P(C)-P(AB)-P(AC)-P(BC)+P(ABC)$
		- Odštejemo presek, ker se drugače nektere verjetnosti podvojijo
	5. *Za monotona zaporedja dogodkov (vsak sledeči dogodek vsebuje vse prejšnje/naslednje) velja zveznost preslikave $P$*:
		- $A_{1}\subset A_{2}\subset\dots\Rightarrow P(A_{1}+A_{2}+\dots)=\lim_{n\to\infty}P(A_{n})$
		- $A_{1}\supset A_{2}\supset\dots\Rightarrow P(A_{1}A_{2}\dots)=\lim_{n\to\infty}P(A_{n})$
- **Verjetnostni prostor** je trojica $(G,D,P)$ kjer je $G$ dana neprazna množica, $D$ $\sigma$-algebra podmnožic v $G$ in $P:D\to\Bbb R$ verjetnostna preslikava. Sedaj imenujemo elemente v $G$ <u>izide</u>, elemente v $D$ pa <u>dogodke</u>
---
# Pogojna verjetnost
- Verjetnost dogodka $A$ pri fiksiranem dogodku $B$  -> $P(A|B)= \frac{P(AB)}{P(A)}$
- **Več fazni poskusi**
	- $H_{1},H_{2},\dots$ paroma nezdružljivi dogodki (v prvi fazi)
	- **Popolna verjetnost** -> $P(A)=P(H_{1})P(A|H_{1})+P(H_{2})P(A|H_{2})+\dots$
	- **Bayesova formula**:
		- Vemo, da se je zgodil dogodek $A$, zanima nas verjetnost da se je v prvi fazi zgodil dogodek $H_{k}$
		- $P(H_{k}|A)=\frac{ P(H_{k})P(A|H_{k})}{P(A)}$
- **Neodvisni dogodki** => $P(AB)=P(A)P(B)$
	- Če dogodka ne vplivata en na drugega.
---
# Zaporedje neodvisnih poskusov
- Dva poskusa sta neodvisna, kadar rezultati enega poskusa ne vplivajo na verjetnost dogodkov v drugem.
- Iščemo verjetnost da se dogodek $A$ v $n$ ponovitvah poskusa zgodi $k$ krat
	- oz. $P_{n}(k)$
	- možnih kombinacij je $n\choose k$
	- $P(A)=p;P(\bar A)=q=1-p$
- **Bernoullijeva formula**: $P_{n}(k)={n\choose k} p^{k}q^{n-k}$
- Aproksimacije formule za $P_{n}(k)$:
	- $p$ blizu 0 -> $P_{n}(k)\approx \frac{(np)^{k}e^{-np}}{k!}$
	- $p$ blizu 1/2 -> $P_{n}(k)\approx \frac{1}{\sqrt{2\pi npq}}e^{- \frac{(k-np)^{2}}{2npq}}$
	- da se zgodi vsaj $k_{1}$ in manj od $k_{2}$ krat -> $P_{n}(k_{1},k_{2})\approx \Phi( \frac{k_{2}-np}{\sqrt{npq}} )-\Phi( \frac{k_{1}-np}{\sqrt{npq}} )$
		- **Funkcija napake** ->$\Phi(x)= \frac{1}{\sqrt{2\pi}}\int^{x}_{0}e^{-\frac{1}{2}t^{2}} dt$
---
