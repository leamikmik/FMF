```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Temperatura
- **Fizikalna količina** => $T\ [K]=T\ [°C]+273$
- V *Celzijevi temperaturni lestvici* definiramo (pri $p\approx 1\text{bar}$):
	- mešanica vode in ledu (led topi/voda zmrzuje), ima temperaturo $0°C$
	- mešanica vode in pare (voda vre), ima temperaturo $100\text{°C}$
- 0. zakon TD => Telesom v toplotnem stiku se po dovolj dolgem času **temperature izenačijo**
- $T=0K$ je nedosegljivo
## Plinska enačba
- **Idealen plin** => Zanemarimo privlačne sile med molekulami
- **<u>Plinska enačba</u>** -> $\frac{p_{1}V_{1}}{T_{1}}= \frac{p_{2}V_{2}}{T_{2}}=\text{konst.}$ ali $pV= \frac{m}{M}RT$ ali $p=nk_{B}T$
	- $p_{1},V_{1},T_{1}$ podatki na začetku
	- $p_{2},V_{2},T_{2}$ podatki na koncu
	- Pri poljubni spremembi *idealnega plina* se $\frac{pV}{T}$ **ne** spremeni
- **Avogadrov zakon:**
	- Avogadrovo število $N_{A}=6*10^{26}$
	- $1\text{kmol}=N_{A}$ atomov ali molekul te snovi
	- **Kilomolska masa $M$** je masa enega kilomola te snovi
	- Za idealne pline (pri $p=1\text{bar}$ in $T=273K$) => $1\text{kmol}$ poljubnega plina zavzame prostornino $V=22.4m^{3}$
## Linearno in prostorninsko raztezanje
1. $V=V(T)$ prostornina odvisna od temp.
	- $\Delta V=\beta V\Delta T$ => $\beta= \frac{1}{V} \frac{\Delta V}{\Delta T};\ [K^{-1}]$
	- $\beta$ => koef. prostorninskega temp. raztezanja ($\beta\approx3\alpha$)
		- za idealne pline $\beta= \frac{1}{T}$
2. $l=l(T)$ dolžina odvisna od temp
	- $\Delta l=\alpha l\Delta T$ => $\alpha= \frac{1}{l}\frac{\Delta l}{\Delta T};\ [K^{-1}]$
	- $\alpha$ -> koeficient lin. temp. raztezanja (odvisen od materiala (ponavadi okoli $10^{-5}K^{-1}$))

---
# Zakoni termodinamike
## Energijski zakon
- spomnimo se izreka o $W_{meh}$ ($A''$ [[Mehanika#Delo, moč in energija|tu]])
- Zakon -> $Q+A''=\Delta W_{k}+\Delta W_{p}+\Delta W_{pr}+\Delta W_{n}$
- $\Delta W_{n}$ => sprememba notranje en.
	- Energija, ki jo ima telo zaradi stanja, v kakršnem se nahaja
## Entropijski zakon
- $Q$ samo od sebe vedno teče iz toplejšega na hladnejše telo

---
# Toplota
$$Q\ [J]$$
- **delež en. ki, pri stiku dveh teles brez dela preide iz enega na drugo telo.**
- $\Delta T>0\Rightarrow Q>0$ (toploto dovedemo)
- $\Delta T<0\Rightarrow Q<0$ (toploto odvedemo)
1. **Specifična toplota pri $p=$ konstanten**
	- $T_{1}\to T_{2};\ Q$ za $\Delta T$
	- $c_{p}\ [\frac{J}{kgK}]$ -> specifična toplota pri $p=$ konst.
	- $Q=mc_{p}\Delta T$
2. **Specifična toplota pri $V=$ konst.**
	- $c_{v}\ [=c_{p}]$ -> specifična toplota pri $V=$ konst.
	- $Q=mc_{v}\Delta T$
	- kapljevine in trdne snovi $c_{p}\approx c_{v}$
3. **Talilna toplota**
	- $T_{t}$ -> temperaturna tališča (temp. pri kateri snov preide iz trdne faze v tekočo)
	- $q_{t} [\frac{J}{kg}]$ => talilna toplota snovi 
	- $Q=q_{t}m$ -> toplota potrebna za taljenje
		- Če hočemo tekočino strditi je $Q=-q_{t}m$
4. **Izparilna toplota**
	- $T_{v}$ -> temperatura vrelišča
	- $q_{i} [\frac{J}{kg}]$ => izparilna toplota snovi 
	- $Q=q_{i}m$ -> toplota potrebna za izparevanje
		- Če hočemo tekočino kondenzirati je $Q=-q_{i}m$
5. **Sežigna toplota**
	-  Gorenje => spajanje s kisikom
	- $q_{s} [\frac{J}{kg}]$ => sežinga toplota snovi 
	- $Q=-q_{s}m$ -> Toplota ki je sprosti, ko zgori snov
		- $|Q|$ => Energijska vrednost snovi (npr. živila)
		- $1\text{cal}=4.2J$

---
# Prevajanje toplote
- Planarna geometrija (plane) prehod toplote skozi snov
- **Toplotni tok** $P= \frac{Q}{t};\ [ \frac{J}{s}=W]$ -> količina toplote, ki preide skozi snov na enoto časa
- $P=\lambda S \frac{\Delta T}{l}=hS\Delta T$
	- $\lambda$ -> toplotna prehodnost $[\frac{W}{mK}]$
---
# Notranja energija
- Idealni plini: $\Delta W_{n}=\Delta W_{n}(\Delta T)=mc_{V}\Delta T$
- Trde snovi in kapljevine: $\Delta W_{n}\approx mc_{p}\Delta T$
---
# Toplotni stroj
- Osnovne ideje: $Q_{dov}\Rightarrow A_{odv}$
- Izkoristek -> $\eta:= \frac{|A_{odv}|}{Q_{dov}}$
	- Idealni stroj -> $\eta_{max}=1- \frac{T_{odv}}{T_{dov}}$
	- $0\le\eta\le\eta_{max}\lt1$