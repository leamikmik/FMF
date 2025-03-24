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