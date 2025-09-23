```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Algebraične strukture
- $M$ --> Množica
- $\circ$ --> binarna operacija na M
	- $\circ: M\times M\rightarrow M$
	- $a,b\in M\Rightarrow a\circ b\in M$
- $(M,\circ)$ --> oznaka za množico $M$ z operacijo $\circ$:
	1. $\forall a,b,c\in M \Rightarrow (a\circ b)\circ c= a\circ(b\circ c)$ => Operacija $\circ$ je <u>asociativna</u>
	2. $\exists e\in M; \forall a\in M\Rightarrow a\circ e=e\circ a=a$ => Element $e$ je <u>enota</u>
	3. $\exists e;\forall a\in M; \exists a^{-1}\in M \Rightarrow a\circ a^{-1}=a^{-1}\circ a=e$ => $a^{-1}$ je <u>inverz</u>
	4. $\forall a,b\in M \Rightarrow a\circ b=b\circ a$ => Operacija $\circ$ je <u>komutativna</u>
- Ena operacija $(M, \circ)$:
	- **Polgrupa** -> $\circ$ v $(M,\circ)$ je <u>asociativen</u>
	- **Monoid** -> *polgrupa* in obstaja <u>enota</u>
	- **Grupa** -> *monoid* in za $\forall a\in M$ obstaja <u>inverz</u> $a^{-1}$
	- **Abelova grupa** -> *grupa* in $\circ$ je <u>komutativen</u>
	- **Podgrupa** -> $N\subseteq M$ in $(N,\circ)$ je grupa, je $N$ <u>podgrupa</u> v $M$
		- $\forall a,b\in N\Rightarrow a\circ b^{-1}\in N$
- Dve operaciji $(M, +, *)$:
	- **Kolobar** =>
		1. $(M,+)$ je <u>Abelova grupa</u>
		2. $(M, *)$ je <u>polgrupa</u>
		3. <u>Distributivnost</u> => $(a+b)*c= a*c+b*c$
	- **Kolobar z enico** => Če $(M, *)$ je <u>monoid</u>
	- **Komutativen kolobar** => Če $(M, *)$ je <u>komutativna polgrupa</u>
	- **Obseg** => Če $(M/\{0\}, *)$ je <u>grupa</u> (*vsi el. razen $0$ so obrnljivi*)
	- **Polje** => Če obseg in komutativno
## Primeri
- $(\Bbb Z, +, *)$ -> Komutativen kolobar z enico
- $(\Bbb C, +, *)$ -> Polje
- $(\Bbb R^{n\times n}, +, *)$ -> Kolobar z enico
- $(\Bbb Z_{n}, +, *)$ -> Če je $n$ praštevilo, je kolobar polje.  ($\Bbb Z_{n}$ so cela števila po modolu $n$)
- $(\Bbb R[x],+,*)$ -> Komutativen kolobar z enico (polinomi)
	- $\Bbb R_{n}[x]$ => polinomi z stopnjo do $n$

---
# Vektorski prostor
- $V$ množica, $F$ polje
- Denimo da imamo operacije:
	- $+: V\times V\rightarrow V$
	- $*: F\times V\rightarrow V$
- Da bo $(V, +, *)$ <u>vektorski prostor</u> velja: ($\alpha,\beta\in F;\ v,w\in V$)
	1. $(V, +)$ je *Abelova grupa*
	2. $(\alpha+\beta)*v=\alpha*v+\beta*v$
	3. $\alpha(v+w)=\alpha*v+\alpha*w$
	4. $\alpha*(\beta*v)=(\alpha*\beta)*v$
	5. $1*v=v$
- Tako rečemo elementom iz $V$ **vektorji**, operaciji $+$ **seštevanje vektorjev** in operaciji $*$ **množenje vektorja z skalarjem**
	- $\Bbb R^{n}$ je vektorski prostor nad $\Bbb R$
	- $\Bbb R^{n\times n}$ je vektorski prostor nad $\Bbb R$
- V vsakem vek. prostoru $V$ velja $0*v=0; \forall v\in V$
## Vektorski podprostor
- $U\subseteq V$ => $U$ je <u>vektorski podprostor</u> prostora $V$
	- $\alpha*u+\beta*v\in U$ za $\forall \alpha,\beta\in F$ in $\forall u,v\in U$
- **Linearna kombinacija** vektorjev $u$ in $v$
- Če je $U$ [[Premice in ravnine#Ravnine|ravnina]] je v.p. če vsebuje točko $T(0,0,0)$
- <u>Presek vektorskih</u> => $U_{1}\cap U_{2}\cap\dots\cap U_{n} \subseteq V$
	- Pogojih vseh podprostorov so v veljavi
- **Seštevanje** -> $U_{1}+U_{2}\subseteq V$ => $\dim(U_{1}+U_{2})=\dim(U_{1})+\dim(U_{2})-\dim(U_{1}\cap U_{2})$
- *Direktna vsota* -> $U_{1}\oplus U_{2}$ => Kadar je $U_{1}\cap U_{2}=\{0\}$
## Linearna kombinacija
$\alpha_{1}v_{1}+\alpha_{2}v_{2}+\dots+\alpha_{n}v_{n}$
- $v_{1},v_{2},\dots,v_{n}\in V$
- $\alpha_{1},\alpha_{2},\dots,\alpha_{n}\in F$
- Množici vseh lin. kombinacij <u>linearna ogrinjača</u>
	- Oznaka: $Lin(v_{1},v_{2},\dots,v_{n})$
	- Je najmanjši **vektorski prostor** ki vsebuje podane vektorje
- Če je lin. kombinacija enaka $0$ so vektorji **linearno neodvisni**
## Baza vektorskega prostora
$V$ ($\{v_{1},v_{2},\dots,v_{n}\}$) če:
1. Vektorji so linearno <u>neodvisni</u>
2. Vsak vektor iz $V$ lahko zapišemo kot lin. kombinacijo $v_{1},v_{2},\dots$
- <u>Standardna baza</u> $\{e_{1},e_{2},\dots,e_{n}\}$:
	1. $\Bbb R^{n}$ => $e_{i}=\left[\begin{matrix} 0 \\ \vdots \\ 1 \\ \vdots \\ 0 \end{matrix}\right]$ (1 na $i$-tem členu)
	2. $\Bbb R_{n}[x]$ => $\{ 1,x,x^{2},\dots,x_{n} \}$
- *Razvoj po bazi enolično določen*
	- Razvoj je enak seštevku baznih vektorjev, pomnoženih z primernimi skalarji $u_{j}=\sum\limits^{m}_{i=1}\alpha_{ij}v_{i}$
- **Dimenzija** v.p. je enaka <u>moči baze</u> $V$ -> $\dim(V)$
	1. $\dim(\Bbb R^{n})=n$
	2. $\dim(\Bbb R_{n}[x])=n+1$
	3. $\dim(\Bbb R^{m\times n})=m*n$
	- *Dve različni bazi za enak prostor imata enako moč*
	- Kriteriji baze lahko znižajo velikost baze (vsaka formula avg. 1)
- <u>Preverjanje lin. neodvisnosti</u> => $\sum\limits^{m}_{i=1}\alpha_{i}v_{i}=0$
	- Bazni vektorji so lin. neodvisno samo **ko so vsi $\alpha_{i}=0$**
## Prehod v baze
$$B\to S\to C$$
- $B, C$ *podani bazi*; $S$ *standardna baza*
- $v_{c}=P_{BC}*v_{b}$
- $P_{BC}$ => **prehodna matrika iz $B$ v $C$ bazo**
	- $P_{BC}=P_{CB}^{-1}$
	- $P_{BC}=P_{CS}^{-1}*P_{BS}$
- $P_{BS}$ => <u>matrika iz </u>$B$<u> v standardno bazo je enaka matriki elementov </u>$B$<u> baze</u>