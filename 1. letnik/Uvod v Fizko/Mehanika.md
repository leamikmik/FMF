```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Kinematika
$$x(t)=x_{0}+v_{0}t+ \frac{a_{0}t^{2}}{2}$$
- Opisovanje gibanja
- Omejitve:
	1. premo gibanje
	2. točkasta telesa
1. Položaj telesa $x$
2. Hitrost telesa $v=\frac{x}{t}$ 
	- graf $x(t)$ v odvisnosti $t$; $T(t, x)$
	- $v(t_{1})=\lim_{\Delta t\to0} \frac{x(t_{1}+\Delta t)-x(t_{1})}{\Delta t} =x'(t_{1});\ [\frac{m}{s}]$
	- $1\frac{m}{s}=3.6 \frac{km}{h}$
3. Pospešek $[a]= \frac{m}{s^{2}}$
	- $a(t_{1})=x''(t_{1})=v'(t_{1})$
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
	- Koncna hitrost v odv. od visine => $v_{k}=\sqrt{v_{0}^{2}+2gh}$

---
# Dinamika
- *Kvalitativno* -> $F$ (sila) => količina ki opisuje vpliv oklice na telo
- *Kvantitativno* (**Newtonovi zakoni**):
	1. $F=0\Leftrightarrow a=0$ -> Telo **miruje** ali pa se giblje **premo enakomerno**
		- $G=mv$
	2. $F=m*a$ -> **Pospešek je sorazmeren** s skupno silo na telo in ima smer sile; sorazmerni koef. je masa telesa
		- $J=\Delta G$
	3. $F_{2\to1}=-F_{1\to2}$ -> Če **prvo telo vpliva na drugega** z neko silo, potem **drugo vpliva na prvega** z nasprotno-enako silo
		- $\sum G=\sum G_{0}$
## Sila teže
$$F_{g}=-mg$$
## Sila podlage
$$F_{p}=-F_{g}=mg$$
- Nasprotna silam navzdol, če ne, telo nebi bilo v skladu z 1. Newt zakonom (predpostavljamo da telo ne pada)
![[Pasted image 20250421155338.png]]
## Sila trenja
$$|F_{tr}|=k_{tr}|F_{p}|$$
- $k_{tr}$ je koef. trenja (odvisen od podlage in stične ploskve)
- Smer $F_{tr}$ je nasprotna smeri hitrosti $v$ telesa
- $F_{tr}$ **zavira** premikanje telesa
![[Pasted image 20250421155643.png]]
## Sila lepenja
$$|F_{l}|=|F_{r}|;\ |F_{l}|^{max}=k_{l}|F_{p}|$$
- $k_{l}\gtrsim k_{tr}$ 
- Telo **miruje**
![[Pasted image 20250421160104.png]]
## Sila vzmeti
$$F_{v}=-ky$$
- **Hookov zakon**
- $y$ raztezek, $k\ [\frac{N}{m}]$  koef. vzmeti
- Če vzmet niha je $y=y_{0}\sin(2\pi\nu t)$
	- Čas nihanja $t_{0}=2\pi\sqrt{\frac{m}{k}}$
	- $my''=-ky$
---
# Delo, moč in energija
- Delo => $A:=Fs;\ [J=Nm]$
- Moč => $P:=\frac{A}{t}=A';\ [\frac{J}{s}=W]$
	- Pri konstanti hitrosti -> $P=F*v$
- Energije:
	- Kinetična -> $W_{k}:=\frac{mv^{2}}{2};\ [J]$
		- **Izrek** -> $A=\Delta W_{k}=W_{k}'-W_{k}$
	- Potiencalna -> $W_{p}:=mg_{0}y;\ [J]$
	- Proznostna -> $W_{pr}:=\frac{1}{2}ky^{2};\ [J]$
- Konzervativne sile:
	- Teza -> $F_{g};\ A_{g}=-(mg_{0}y'-mg_{0}y)= -\Delta W_{p}$
	- Vzmet -> $F_{v};\ A_{v}=-(\frac{ky'^{2}}{2}-\frac{ky^{2}}{2})=-\Delta W_{pr}$
- Delo sil, razen kozervativnih (**izrek o mehanski energiji**) => $A'':=A-A_{g}-A_{v}=\Delta W_{k}+\Delta W_{p}+\Delta W_{pr}$

---
# Sunek sile in gibalna količina
$F$ so konstantne
- $F, t$ => sunek sile $J:=Ft;\ [Ns]$ (predznak je smer!)
- $m,v$ => gibalna kolicina $G:=mv;\ [Ns]$ (predznak spet smer)
	- **Izrek** => $Ft=\Delta G$
- Ce imamo vec teles =>
	- $G=G_{1}+G_{2}$
	- $F_{1\to2}, F_{2\to1}$ -> Notranje sile
	- $F_{1,z}, F_{2,z}$ -> zunanje sile
		- $F_{1}=F_{1,z}+F_{2\to1}$
		- $F_{1,z}+F_{2,z}=F_{z}$
	- **Izrek o gibalni količini sistema 2 teles** => $F_{z}t=\Delta G$
		- Posebni primer ($F_{z}t=0$) -> $\Delta G=0$ 
## Trki
- Skupni sunek zunanjih sil je $0$
- $G=G' \Rightarrow m_{1}v_{1}=m_{1}v_{1}'+m_{2}v_{2}'$
1. **Popolnoma neprožni**:
	- $v'=v_{1} \frac{m_{1}}{m_{1}+m_{2}}$
	- Telesa ob trku sprimeta -> $v'=v_{1}'=v_{2}'$
	- Skupna kinetična energije se <u>ne</u> ohranja, gibalna pa se ohranja
2. **Popolnoma prožni**:
	- $v_{1}'=v_{1} \frac{m_{2}-m_{1}}{m_{2}+m_{1}};\ v_{2}'=v_{1} \frac{2m_{1}}{m_{1}+m_{2}}$
	- Kineticna en. se ohrani
---
# Kroženje in vrtenje
- Kot -> $\phi=\frac{l}{r}; [/]\ rd$
	- razmerje med krožnim lokom in polmerom krožnice
- Kotna hitrost -> $\omega=\phi';\ [s^{-1}]$
	- $v=\omega r$
- Kotni pospešek -> $\alpha=\phi'';\ [s^{-2}]$
	- $a=r\alpha$ => $rF=mr^{2}\alpha$
- Vztrajnostni moment -> $J_{1}=mr^{2}\ [kgm^{2}]$
- Navor -> $M=J_{1}\alpha=rF;\ J_{1}=mr^{2}$
- $M=J^{*}\alpha$
	- $J^{*}=\frac{1}{2}mr^{2}$ => **Homogen valj**
	- $J^{*}=\frac{2}{5}mr^{2}$ => **Homogena krogla**
	- $J^{*}=mr^{2}$ => **Votli valj**
- $M=0\Leftrightarrow\alpha=0\Leftrightarrow\omega=\omega_{0}=\text{koef}$ (enakomerno vrtenje)
- $W_{k}$ tockastega telesa, ki krozi:
	- $W_{k}=\frac{1}{2}mv^{2}=\frac{1}{2}m(r\omega)^{2}=\frac{1}{2}J_{1}w^{2}$ 
	- $W_{rot}=\frac{1}{2}J^{*}\omega^{2}$ => Rot energija *nekega* telesa, ki se vrti
- I**zrek** -> Poljubno gibanje razseznega togega telesa lahko razstavimo na translacijo težišča in na rotacijo okrog teziscne osi.
	- $W_{k}=W^{*}_{k}+W_{rot}$
		- $W^{*}_{k}=\frac{1}{2}mv^{*^{2}}$ ($v^{*}$ hitrost težišča) 
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
## Hidrostatika
- Tekocina pri miru
- Tekocina -> so snovi ki jih pretakamo
1. Gostota => $\rho=\frac{m}{V};\ [\frac{kg}{m^{3}}]$
2. Tlak (sile glede na prijemalsice) => $p\ [\frac{N}{m^{2}}=Pa;\ 1\ bar=10^{5}Pa]$
	1. Tockasto
	2. Ploskovno (ploscina ploskve $S$) => $p:=\frac{F}{S}$ 
	3. Prostorsko
3. Stisljivost => $\chi:=- \frac{\Delta V}{V*\Delta p};\ [Pa^{-1}]$
	- $p\rightarrow p'=p+\Delta p$ => $V\rightarrow V'=V-\Delta V$
	- $-\frac{\Delta V}{V}$ sorazmeren $\Delta p$ => $-\frac{\Delta V}{V}=\chi\Delta p$
- Tekocina: plini in kapljevine
	1. Plini: 
		- $\rho\approx1 \frac{kg}{m^{3}}$ (pri tlaku $1\ bar$ in pri sobni temp.)
		- $\chi=10^{-5}Pa^{-1}=1\ bar^{-1}$ (pri tlaku $1\ bar$)
		- Ne tvorijo gladine, kapelj
	2. Kapljevine:
		- $\rho\approx10^{3} \frac{kg}{m^{3}}$
		- $\chi\approx10^{-10}Pa^{-1}=10^{5}bar^{-1}$
		- Tvorijo kaplje in gladino
- Hidrostatski tlak
	- $p(h)=p_{0}+\rho g_{0}h$ -> Tlak na globini
- Sila vzgona (**Arhimedovo načelo**) $F_{vzg}$
	- Telo (v celoti potopljeno v tekocini $\rho_{t}$ ($V_{izp}=V$)) => $m$, $V$, $\rho$
	- $V_{izp}=V$
	- $F_{g}=-mg_{0}$
	- $F_{vzg}=-F_{g,izp}=m_{izp}g_{0}$
		- $m_{izp}=V_{izp}\rho_{t}$
	- $F=F_{g}+F_{vzg}=-(m-m_{izp})g_{0}=-(\rho V-\rho_{t}V_{izp})g_{0}$
		- Telo komplet potopljeno => $F=-(\rho-\rho_{t})Vg_{0}$
	1. $\rho>\rho_{t}$ => $F<0$ (telo potopi)
	2. $\rho=\rho_{t}$ => $F=0$ (telo lebdi)
	3. $\rho<\rho_{t}$ => $F>0$ (telo plava)
		- $V_{izp}<V$
		- potoljen del -> $\frac{V_{izp}}{V}=\frac{\rho}{\rho_{t}}$
## Hidrodinamika
- Tekocina premika
- **Viskoznost** -> $F_{vis}=\eta \frac{v}{z}S$
- Viskoznostni koef. (odvisna od tekocine) $\eta$
- **Kvadratni zakon upor**:
	- $F_{u}=- \frac{1}{2}C_{u}\rho_{t}S_{\perp}v^{2}$
	- Vrednosti $C_{u}$ za oblike:
		- Krogla => $C_{u}=0.4$
		- Na pol prerezana votla krogla => $C_{u}=1.3$
		- Ravna deska => $C_{u}=1.1$
		- Kaplja => $C_{u}=0.04$
		- Avtomobil => $C_{u}\approx0.3-0.5$