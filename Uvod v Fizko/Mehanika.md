```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Kinematika
- Opisovanje gibanja
- Omejitve:
	1. premo gibanje
	2. točkasta telesa
1. Položaj telesa $x$
2. Hitrost telesa $x=x(t)$ 
	- graf $x(t)$ v odvisnosti $t$; $T(t, x)$
	- $v(t_{1}):=k(T_{1}):=\frac{dx}{dt}t_{1}$
	- $[v]=\frac{m}{s}$
	- $1\frac{m}{s}=3.6 \frac{km}{h}$
3. Pospešek $[a]= \frac{m}{s^{2}}$ 
## Primeri
1. $x(t)=x_{0}+v_{0}*t$; $x_{0},v_{0}$ konstanti
	- $[x_{0}]=m$; $[v_{0}]=\frac{m}{s}$
	- $x(t=0)=x_{0}$
	- $v(t_{1})=x'(t_{1})=...=v_{0}$
2. $x(t)=x_{0}+v_{0}t+ \frac{a_{0}t^{2}}{2}$
	- $[x_{0}]=m$; $[v_{0}]=\frac{m}{s}$; $[a_{0}]=\frac{m}{s^{2}}$
	- $v(t)=x'(t)=...=v_{0}+a_{0}t$
	- $v(t_{1})\ne v(t_{2})$ => Gibanje ni enakomerno
3. Navpicni met vseh vrst
	- v blizini zemljinega povrsja ($g\approx 9.88 \frac{m}{s^{2}}$)
	- $a_{0}=-g$ (ce zanemarimo zracni upor)
	- $v_{0}=0$ => prosti pad
	- $v_{0}>0$ => met navzgor
	- $v_{0}<0$ => met navzdol

---
# Delo, moč in energija
- Delo => $A:=Fs;\ [J=Nm]$
- Moč => $P:=\frac{dA}{dt};\ [\frac{J}{s}=W]$
- Energije:
	- Kineticna -> $W_{k}:=\frac{mv^{2}}{2};\ [J]$
		- Izrek -> $A=\Delta W_{k}=W_{k}'-W_{k}$
	- Potiencalna -> $W_{p}:=mg_{0}y;\ [J]$
	- Proznostna -> $W_{pr}:=\frac{1}{2}ky^{2};\ [J]$
- Konzervativne sile:
	- Teza -> $F_{g};\ A_{g}=-(mg_{0}y'-mg_{0}y)= -\Delta W_{p}$
	- Vzmet -> $F_{v};\ A_{v}=-(\frac{ky'^{2}}{2}-\frac{ky^{2}}{2})=-\Delta W_{pr}$
- Delo sil, razen kozervativnih => $A'':=A-A_{g}-A_{v}=\Delta W_{k}+\Delta W_{p}+\Delta W_{pr}$

---
# Sunek sile in gibalna količina
1D
$F$ so konstantne
- $F, t$ => sunek sile $:=Ft;\ [Ns]$ (predznak je smer!)
- $m,v$ => gibalna kolicina $G:=mv;\ [Ns]$ (predznak spet smer)
	- Izrek: $Ft=\Delta G$
- Ce imamo vec teles =>
	- $G=G_{1}+G_{2}$
	- $F_{1\to2}, F_{2\to1}$ -> Notranje sile
	- $F_{1,z}, F_{2,z}$ -> zunanje sile
		- $F_{1}=F_{1,z}+F_{2\to1}$
		- $F_{1,z}+F_{2,z}=F_{z}$
	- Izrek => $F_{z}t=\Delta G$
		- Posebni primer ($F_{z}t=0$) -> $\Delta G=0$ 
---
# Navor in vrtenje
Navor => $M$
- $M=J_{1}\alpha;\ J_{1}=mr^{2}$
- $M=J^{*}\alpha$
	- $J^{*}=\frac{1}{2}mr^{2}$ => Homogen valj
	- $J^{*}=\frac{2}{5}mr^{2}$ => Homogena krogla
	- $J^{*}=mr^{2}$ => Votli valj
- $M=0\Leftrightarrow\alpha=0\Leftrightarrow\omega=\omega_{0}=\text{koef}$
- $W_{k}$ tockastega telesa, ki krozi:
	- $W_{k}=\frac{1}{2}mv^{2}=\frac{1}{2}m(r\omega)^{2}=\frac{1}{2}J_{1}w^{2}=W_{rot}$ 
	- $W_{rot}=\frac{1}{2}J^{*}\omega^{2}$ => Rot energija *nekega* telesa, ki se vrti
- Izrek -> Poljubno gibanje razseznega dolgega telesa lahko razstavimo na translacijo krozisca in na rotacijo okrog teziscne osi.
	- $W_{k}=W^{*}_{k}+W_{rot}$
		- $W^{*}_{k}=\frac{1}{2}mv^{*^{2}}$
		- $W_{rot}=\frac{1}{2}J^{*}\omega^{2}$
## Kotaljenje
- $v^{*}\Leftrightarrow\omega$
- Telo se kotali ko ne drsi  => $v^{*}=r\omega$
- Tocke v stiku z podlago mirujejo; prijemalisce sile podlage miruje
	- $v_{p}=0\Rightarrow P_{p}=F_{p}v_{p}=0\Rightarrow P_{p}=\frac{A_{p}}{t}=0\Rightarrow A_{p}=0$
- $W_{k}=\frac{x}{20}mv^{*^{2}}$ 
	- $x=15$ => Homogen valj
	- $x=14$ => Homogena krogla
	- $x=20$ => Votli valj
---
# Mehanika tekočin
- Tekocina -> so snovi ki jih pretakamo
1. Gostota => $\rho=\frac{m}{V};\ [\frac{kg}{m^{3}}]$
2. Tlak (sile glede na prijemalsice) => $p\ [\frac{N}{m^{2}}=Pa;\ 1\ bar=10^{5}Pa]$
	1. Tockasto
	2. Ploskovno (ploscina ploskve $S$) => $p:=\frac{F}{S}$ 
	3. Prostorsko
3. Stisljivost => $\chi:=- \frac{\Delta V}{V*\Delta p};\ [Pa^{-1}]$
	- $p\rightarrow p'=p+\Delta p$ => $V\rightarrow V'=V-\Delta V$
	- $-\frac{\Delta V}{V}$ sorazmeren $\Delta p$ => $-\frac{\Delta V}{v}=\chi\Delta p$
- Tekocina: plini in kapljevine
	1. Plini: 
		- $\rho\approx1 \frac{kg}{m^{3}}$ (pri tlaku $1\ bar$ in pri sobni temp.)
		- $\chi=10^{-5}Pa^{-1}=1\ bar^{-1}$ (pri tlaku $1\ bar$)
		- Ne tvorijo gladine, kapelj
	2. Kapljevine:
		- $\rho\approx10^{3} \frac{kg}{m^{3}}$
		- $\chi\approx10^{-10}Pa^{-1}=10^{5}bar^{-1}$
		- Tvorijo kaplje in gladino