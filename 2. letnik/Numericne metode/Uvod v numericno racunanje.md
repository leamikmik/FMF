```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Uvod
- Numerična mat. -> Analiza in razvoj algoritmov za resevanje mat. problemov
- Iščemo rešitev v numerični obliki (npr. namesto $\pi$ iščemo $3.14159...$)
- **Numerična metoda** -> postopek, kjer iz vhodnih numeričnih podatkov z končnim številom elementarnih operacij izračunamo približek za rezultat problema
- Kdaj uporabimo:
	- ko ne poznamo drugih metod
	- ko so bolj udobne in manj zapletene od analitičnih
- Glavne zahteve za dobro metodo:
	- Zanesljivost in robustnost
	- Natančnost
	- Ekonomičnost
- Napake:
	- $x$ je točna vrednost, $\bar x$ pa približek
	- **Absolutna napaka** $d_{a}=\bar x - x$ => $\bar x = x+d_{a}$
	- **Relativna napaka** $d_{r}=\frac{\bar x - x}{x}; x\ne0$ => $\bar x=x(1+d_{r})$
---
# Predstavitev števil v računalniku
**oz. plavajoča vejica**
- Omejeno število mest za zapis nekega števila -> **Končna aritmetika**
- Števila so predstavljena v obliki => $x=\pm m*b^{e}$ 
	- Množico zapišemo kot $P(b,t,L,U)$
	- $x$ je število
	- $b$ je baza
	- $t$ je dolžina mantise
	- $e$ je eksponenta ($L\le e\le U$)
	- $m=0.c_{1}...c_{t}$ je mantisa
		- $c_{1},c_{2},...,c_{t}\in\{0,1,...,b-1\}$
	- Enolično zapišemo tako, da $c_{1}\ne0$ (imenujemo **normalizirana števila**)
- Decimalni del v binarnem izracunamo z $st * 2: -1/-0$
	- Tj. ce pomnozimo z $2$ in je st vecje od 1 damo 1
	- Koncno stevilo ima lahko periodo
	- Npr. $12.3$ v $P(2,5,-4,6)$ -> $1100.0100\overline{1100}$
		- **Normalizirana** -> $0.11000100\overline{1100} * 2^{4}$
		- Ni mogoce tocen zapis -> Priblizek $0.11001*2^{4}$
- Prostor med zapisljivimi stevili je $b^{e-t}$ 
- Zaokrozimo glede na $c_{t+1}$:
	- Ce je manjše od $\frac{b}{2}$ zaokrožimo navzdol,
	- Ce je pa večje pa zaokrožimo navzgor (prištejemo $b^{-t}$)
	- Zapišemo približek od $x$ kot $fl(x)=\bar x$
	- Relativna napaka -> $\frac{|fl(x)-x|}{|x|}$
		- **Osnovna zaokrožitvena napaka** (OZN) => $u=\frac{1}{2}b^{1-t}$ 
		- Izrek: Če leži $x$ znotraj intervala predstavljivih števil, potem je $\frac{|fl(x)-x|}{|x|}\le \frac{u}{1+u}<u$. Dokaz:
			- $x=\pm(y+z)*b^{e}$ kjer $y=0.c_{1}c_{2}\dots c_{t}$ in $z=0.0\dots0c_{t+1}c_{t+2}\dots$
			- $\bar x=\pm y*b^{e}$
			- $\frac{|fl(x)-x|}{|x|}=\frac{z}{z+y}\le\frac{\frac{1}{2}b^{1-t}}{1+\frac{1}{2}b^{1-t}}= \frac{u}{1+u}$
		- $fl(x)=x(1+\delta);|\delta|\le u$
## IEEE Standard/format števil
- Števila so zapisana v enojni (32 bit) ali dvojni (64 bit) natančnosti
- **Enojni** (1 bit predznak $s$, 8 bitov eksponenta $1\le e\le254$ , 23 bitov mantisa $c$)
	- Formula -> $x=(-1)^{s}(0.1c_{2}c_{3}\dots c_{24})*2^{e-126}$
	- Zapis "posebnih stevil" dobimo z $e=0$ in $e=255$
		- $e=0:$
			- $c_{2}\dots c_{24}=0$ <=> $x=0$
		- $e=255:$
			- $c_{2}\dots c_{24}=0$ <=> $x=(-1)^{s}\infty$
			- vsaj en $c\ne0$ <=> $x=\text{NaN}$
	- tj. $P(2,24,-125, 128)$
	- Napaka $u=2^{-24}\approx6*10^{-8}$
	- Obseg predstavljivih stevil je okoli $10^{-38}$ do $10^{38}$
- **Dvojni** (1 bit predznak $s$, 11 bit eksponent $1\le e\le2046$, 52 bit mantisa $c$)
	- Formula -> $x=(-1)^{s}0.1c_{2}\dots c_{53}*2^{e-1022}$
	- tj. $P(2,53,-1021,1024)$
	- Napaka $u=2^{-53}\approx 10^{-16}$
	- Obseg predstavljivih stevil je okoli $10^{-308}$ do $10^{308}$
- Zagotavlja, da za vse osnovne racunske operacije velja:
	- $fl(x\circ y)=(x\circ y)(1+\delta);|\delta|\le u$
---
# Napake pri numericnem racunanju
- **Celotna napaka** => $D=y-\bar y= D_{n}+D_{m}+D_{z}$
- Poznamo 3 vrste napak:
	1. *Neodstranljiva napaka* -> Napaka vhodnih podatkov
	2. *Napaka metode* -> pojavi, ko npr. neskončne procese nadomestimo z končnimi 
	3. *Zaokrožitvene napake aritmetike* -> Pri vsaki računski operaciji se pojavi zaokrožitvena napaka. Končna napaka je odvisna od vrstnega reda in načina računanja
## Neodstranljiva napaka $D_{n}$
- Pojavi zaradi nenatančnosti začetnih podatkov (nenatančna meritev, aproksimacije nepredstavljivih števil, ...)
- Namesto $x$ računamo s $\bar x$, kar pomeni, če v nadaljevanju ne pride do novih napak, namesto $y=f(x)$ imamo $\bar y=f(\bar x)$
- Tedaj $D_{n}=y-\bar y$
- Če je funkcija $f$ odvedljiva v $x$:
	- $|D_{n}|\approx|f'(x)||x-\bar x|$
## Napaka metode $D_{m}$
- Pogosto ni možno s končno mnogo osnovnimi operacijami izračunati vrednost $f$. Zato aproksimiramo z funkcijo $g$
- Do napake pride tudi zato, ker nadomestimo neskončen proces s končnim
- Namesto $f$ računamo vrednost $g$. Torej $\bar y=f(\bar x)$ in $\tilde y=g(\bar x)$
- Tedaj $D_{m}=\bar y - \tilde y$
- Primer je Taylorjeva vrsta
## Zaokrožitvena napaka $D_{z}$
- Pri dejanskem računanju $\tilde y=g(\bar x)$ se pri vsaki operaciji pojavi zaokrožitvena napaka, zato v resnici računamo $\hat y$
- Vrednost $\hat y$ je odvisna od vrstnega reda operacij in načina izračuna $g(\bar x)$
- $D_{z}=\tilde y- \hat y$
- Ne velja nujno $\hat y=fl(\tilde y)$ zato ker se zaokrožuje že pri vmesnih korakih
---
# Občutljivost problem in stabilnost metode
- Analiziramo za koliko se spremeni rezultat, če malo zmotimo (perturbiramo) začetne podatke
	- Malo spremembe -> *neobčutljiv* (dobro pogojen)
	- Veliko spremembe -> *občutljiv* (slabo pogojen)
- Znan primer: **Wilkinsonov zgled**
	- $p(x)=(x-1)(x-2)\dots(x-20)$
	- Ima ničle $1,2,3,\dots,20$
	- Če zmotimo koeficient pri $x^{19}$ dobimo $g(x)=p(x)-2^{-23}x^{19}$
	- Nove ničle so:
		- $x_{9}=8.91752$
		- $x_{10,11}=10.0953\pm0.6431i$
		- $\dots$
---
# Direktna in obratna stabilnost
- Pojem stabilnost se navezuje na numerično metodo.
- Ločimo direktno in obratno stabilnost, glavno orodje za preverjanje je pa *analiza zaokrožitvenih napak*
- Recimo da namesto $f(x)=y$ dobimo $fl(x)=\bar y$
- *Direktna napaka* -> absolutna ali relativna napaka med $y$ in $\bar y$
	- Če je direktna napaka majhna -> Proces direktno stabilen
	- Napaka velika -> Proces direktno nestabilen
- *Obratna napaka* -> absolutna ali relativna napaka med $x$ in $\bar x$
	- Za koliko je treba zmotiti $x$ v $\bar x$ da dobimo $f(\bar x)=fl(x)=\bar y$
	- Če je za vsak $x$ obratna napaka majhna, je proces obratno stabilen
---
# Analiza zaokrožitvenih napak
- Vsaka operacija ima neko napako $1+\delta;|\delta|\le u$
- Če napake množimo (npr. $d=\frac{a+b}{c}$ in $fl(d)=\frac{(a+b)(1+\delta_{1})}{c}(1+\delta_{2})$) lahko zapišemo v obliki $\frac{a+b}{c}(1+\gamma)$ in $|\gamma|\le2u$ oz $nu$ pri $n$ operacijah
	- Če npr. $|\delta_{1}|\le3u$ in $|\delta_{2}|\le2u$ potem $|\gamma|\le5u$ (napake se seštevajo)
- Obratno stabilnost pogledamo z zamikom vnešenih podatkov. Npr. na prejšnjem primeru:
	- $\frac{\bar a+\bar b}{\bar c}=\frac{a+b}{c}(1+\gamma)$ in iščemo $\bar a, \bar b, \bar c$
	- $\bar c=c$, $\bar a=a(1+\gamma)$ in $\bar b=b(1+\gamma)$
	- Zato ker je $\gamma$ majhna je obratno stabilen
- Direktno stabilnost pogledamo pa z absolutno oz. relativno napako:
	- najprej $fl(d)-d= \frac{a+b}{c}\gamma$
	- potem $fl(d)-d\le2u( \frac{a+b}{c})$
	- na koncu pa $|\frac{fl(d)-d}{d}|\le| \frac{2u(\frac{a+b}{c})}{\frac{a+b}{c}} |=2u$
	- Torej ta primer tudi direktno stabilen
- Velik problem je odštevanje skoraj enakih števil, saj pride do velike izgube natančnosti
## Računanje vrednosti polinoma preko Hornerjevega algoritma
- $p(x)=a_{n}x^{n}+a_{n-1}x^{n-1}+\dots+a_{0}$
- Naj bo $x$ dano predstavljivo st.
	- $p\dots$ točna vrednost $p(x)$
	- $\bar p\dots$ numerično izračunana vrednost
- $|\frac{\bar p-p}{p}|\le2n u \frac{\sum\limits^{n}_{i=0}|a_{i}||x|^{i}}{|\sum\limits^{n}_{i=0}a_{i}x^{i}|}$ => Ni direktno stabilen
## Glej skripto str. 18-22
[[Uvod v numerične metode (matematika).pdf]]

---
# Poučni primeri
## Rekurzivno integriranje
$$I_{n}=\int_{0}^{1}x^{n}e^{x-1}dx$$
- Z pomočjo per partesa spremenimo integral v rekurzivno obliko, tako da so vsi $n$-ji v novem integralu $n-1$. 
	- $I_{n}=x^{n}e^{x-1}\mid_{0}^{1}-n\int_{0}^{1}x^{n-1}e^{x-1}dx=1-nI_{n-1}$
- Da naredimo postopek bol stabilen izpostavimo $I_{n-1}$.
	- $I_{n-1}= \frac{1-I_{n}}{n}$
- Sedaj vzamemo aproksimacijo za velik $n$ je enak $0$.