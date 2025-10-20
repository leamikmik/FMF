- Numericna mat. -> Analiza in razvoj algoritmov za resevanje mat. poblemov
- Iscemo resitev v numericni obliki (npr. namesto $\pi$ iscemo $3.14159...$)
- **Numericna metoda** -> postopek, kjer iz vhodnih num. podatkov z koncnim stevilom elementarnih operacij izracunamo priblizek za rezultat problema
- Kdaj uporabimo:
	- ko ne poznamo drugih metod
	- ko so bolj udobne in manj zapletene od analiticnih
- Glavne zahteve za dobro metodo:
	- Zanesljivost in robustnost
	- Natancnost
	- Ekonomicnost
- Napake:
	- $x$ je tocna vrednost, $\bar x$ pa priblizek
	- **Absolutna napaka** $d_{a}=\bar x - x$ => $\bar x = x+d_{a}$
	- **Relativna napaka** $d_{r}=\frac{\bar x - x}{x}; x\ne0$ => $\bar x=x(1+d_{r})$
# Predstavitev števil v računalniku
**oz. plavajoča vejica**
- Omejeno stevilo mest za zapis nekega števila -> **Koncna aritmetika**
- Stevila so predstavljena v obliki => $x=\pm0.c_{1}c_{2}c_{3}...c_{t}*b^{e}$ 
	- Mnozico zapisemo kot $P(b,t,L,U)$
	- $x$ je stevilo
	- $b$ je baza
	- $e$ je exponenta ($L\le e\le U$)
	- $0.c_{1}...c_{t}$ je mantisa
		- $c_{1},c_{2},...,c_{t}\in\{0,1,...,b-1\}$
	- Enolicno zapisemo tako, da $c_{1}\ne0$ (recemo **normalizirana stevila**)
- Decimalni del v binarnem izracunamo z $st * 2: -1/-0$
	- Tj. ce pomnozimo z $2$ in je st vecje od 1 damo 1
	- Koncno stevilo ima lahko periodo
	- Npr. $12.3$ v $P(2,5,-4,6)$ -> $1100.0100\overline{1100}$
		- **Normalizirana** -> $0.11000100\overline{1100} * 2^{4}$
		- Ni mogoce tocen zapis -> Priblizek $0.11001*2^{4}$
- Prostor med zapisljivimi stevili je $b^{e-t}$ 
- Zaokrozimo glede na $c_{t+1}$:
	- Ce je manjse od $\frac{b}{2}$ zaokrozimo navzdol,
	- Ce je pa vecje pa zaokrozimo navzgor (pristejemo $b^{-t}$)
	- Zapisemo priblizek od $x$ kot $fl(x)=\bar x$
	- Relativna napaka -> $\frac{|\bar x -x|}{|x|}$
		- $x=\pm(y+z)*b^{e}$ kjer $y=0.c_{1}c_{2}\dots c_{t}$ in $z=0.0\dots0c_{t+1}c_{t+2}\dots$
		- $\bar x=\pm y*b^{e}$
		- Relativna napak  je potem $\frac{z}{z+y}\le\frac{\frac{1}{2}b^{1-t}}{1+\frac{1}{2}b^{1-t}}$
		- $u=\frac{1}{2}b^{1-t}$ (**osnovka zaokrozitvena napaka** ali **OZN**) tj. napaka $\frac{u}{u+1}$
		- Izrek: Ce lezi $x$ znotraj intervala predstavljivih stevil, potem je $\frac{|fl(x)-x|}{|x|}\le \frac{u}{1+u}<u$
			- Posledica $fl(x)=x(1+\delta),\ |\delta|\le u$
## IEEE Standard/format stevil
- Stevila so zapisana v enojni (32 bit) ali dvojni (64 bit) natancnosti
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
# Napake pri numericnem racunanju
- Poznamo 3 vrste napak:
	1. Neodstranljiva napaka -> Napaka vhodnih podatkov
	2. Napaka metode -> pojavi, ko npr. neskoncne procese nadomestimo z koncnimi 
	3. Naokrozitvene napake aritmetike -> Pri vsaki racunski operaciji se pojavi zaokrozitvena napaka. Koncna napaka je odvisna od vrstnega reda in nacina racunanja
## Neodstranljiva napaka
- Zanima nas, kako se spremeni rezultat, ce malo spremenimo vhodne podatke
- Primer je neobcutljiv, ce je sprememba majhna (v primerjavi z OZN), sicer je primer obcutljiv
- Wilkinsonov zgled:
	- $p(x)=(x-1)(x-2)\dots(x-20)$
	- Spremenimo koeficient pri $x^{19}$ -> $q(x)=p(x)-2^{-23}x^{19}$
	- Nicle sse zelo spremenijo. Dobimo celo komplekse nicle
## Analiza zaokrozitvenih napak aritmetike
- Recimo da racunamo vrednost $y=f(x)$ (recimo da je $f$ eksakten)
- Numericno izracunamo $\bar y$ -> $f$ je numericen
- Direktna napaka: $|\bar y - y|$ (absolutna) ali $\frac{|\bar y - y|}{|y|}$ (relativna)
- Ce je direktna napaka majhna (v primerjavi z OZN) je algoritem **direktno stabilen**, sicer je **direktno nestabilen**
	- Naj bo $\bar x$ tak, da velja $\bar y=f(\bar x); x=f(y);\bar y=fl(x)$
	- Obratna napaka $\frac{|\bar x-x|}{|x|}$
	- direktna napaka $\frac{|\bar y - y|}{|y|}$
- ce je obratna napak majhna, potem je algoritem **obratno stabilen**, sicer je **obratno nestabilen**
- Ce je algoritem obratno stabilen, je numaricno izracunana resitev tocna resitev "malo" spremenjenih vhodnih podatkov