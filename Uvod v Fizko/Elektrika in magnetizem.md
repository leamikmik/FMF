```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Električni tok
1. **Toplotni učinek**:
	- Žica se segreje in podaljša
	- Nitka v žarnici se segreje toliko da žari
2. **Magnetni učinek**:
	- Med dvema vzporednima žicama, po katerih teče tok, se pojavi sila 
		- Odbojna, če tokova vzporedna
		- Privlačna, če sta nasprotna
	- Magnetna igla, ki ponavadi kaže v smeri server/jug se v bližini žice z tokom orientira pravokotno na žico
3. **Kemijski učinek**:
	- Pod vplivom el. toka potekajo nekatere kemijske reakcije (npr. elektroliza)
## Jakost el. toka
- $I\ [A]$ -> tok, z enoto amper. Definirajmo amper:
	- Dva zelo dolga vzporedna ravna vodnika, na razdalji 1m
	- Po njima teče enak tok ($I_{1}=I_{2}=I$)
	- **Če je sila 1. vodnika na 1m 2. vodnika $2*10^{-7}N$** => $I=1A$
## Smer el. toka
- Tok je lahko enakomeren ali izmeničen
- Smer toka sovpada s smerjo desnega vijaka, ki ga vrtimo v smeri kroženja
## Električni naboj
$$e=It;\ [As]$$

---
# El. delo, el. moč in el. napetost
- El. delo => $A_{el}=U*e$
- El. moč => $P_{el}=\frac{A_{el}}{t}=UI$ (enakomerni konstani tok)
## Ohmov zakon in el. upornost
- $R=\frac{U}{I};\ [\Omega]$ => Upornost -> Ohmov zakon
- Zaporedna vezava upornikov => $R=R_{1}+R_{2}$
- Vzporedna vezava upornikov => $\frac{1}{R_{n}}=\frac{1}{R_{1}}+\frac{1}{R_{2}}$
- $R=\zeta\frac{l}{S}$
	- $\zeta$ -> specifična upornost \[$\Omega m$]
	- $\Delta\zeta=\alpha_{\zeta}\zeta\Delta T$ -> Odvisnost od temp. ($\alpha_{\zeta};\ [K^{-1}]$ temp. koef. spec. upornosti)
## El. moč, ki jo troši porabnik
$$P_{R_{1}}=I_{1}^{2}R_{1}$$
## Upornik v tokokrogu z izmeničnim tokom
- $U=U_{0}\sin(\omega t);\ \omega=2\pi\nu$
	- $U_{ef}=\frac{U_{0}}{\sqrt2}$ -> efektivna napetost
	- $U_{0}$ -> Amplituda (max)
- $I=I_{0}\sin(\omega t);\ \omega=2\pi\nu$
	- $I_{ef}=\frac{I_{0}}{\sqrt2}$ -> efektivni tok
	- $I_{0}$ -> Amplituda (max)
- $P=U_{0}I_{0}\sin^{2}(\omega t);\ \omega=2\pi\nu$
	- $\bar P_{el}=\frac{P_{0}}{2}=U_{ef}I_{ef}$
---
# El. polje
## Kondenzator
$$C=\frac{e}{U}$$
-  *Kondenzator je elektrotehniški element, ki lahko shranjuje energijo v obliki električnega polja.*
- $C$ -> kapaciteta \[$F$]
- Ploščati kondenzator:
	- $U = \frac{e}{S\varepsilon_{0}}d$
	- $C = \varepsilon\varepsilon_{0}\frac{S}{d}$
		- Če ni snovi med ploščama je $\varepsilon$ enak 1
- Energija kondenzatorja -> $W_{c}=\frac{1}{2} \frac{e^{2}}{C}$
	- $W_{c_{12}}=\frac{1}{2} C(E_{2}l)^{2}$ -> Končna jakost el. polja
	- Za ploščati kond $W_{c}=\frac{1}{2}\varepsilon\varepsilon_{0}UE_{2}^{2}$

![[Kondenzator 2023-11-09 15.03.35.excalidraw]]
## El. sila
$$F_{el}=eE$$
- Delec med ploščama kondenzatorja
	- Odvisno od naboja ga vleče v eno smer
	- Ko pride do ene stene, spremeni naboj in gre nazaj
## Jakost el. polja
$$E=\frac{F_{el}}{q}= \frac{e}{4\pi\varepsilon_{0}r^{2}}=Pt;\ [\frac{V}{m}]$$
- $F_{el}=\frac{e_{1}e_{2}}{4\pi\varepsilon_{0}r^{2}}$ -> Sila med dvema nabojema (**Columbov zakon**)
- Med ploščama kond. -> $E=\frac{U}{l}$
	- Smer -> Od $+$ proti $-$
- $W_{E}=\frac{1}{2}\varepsilon\varepsilon_{0}UE_{2}^{2}$ => energija el. polja
---
# Magnetno polje
- $B\ [T]$ -> **Gostota mag. polja** z enoto tesla
	- $F_{m}=evB\sin\phi;\ \phi\angle v,B$
- $W_{B}=\frac{1}{2} \frac{B^{2}}{\mu\mu_{0}}U$ => energija mag. polja 
- Po vodniku z tokom:
	- Vpliv magnetne sile na naboje v žici
	- $F_{m}=IlB\sin\phi;\ \phi\angle l(I),B$
- V okolici vodnika s tokom:
	- $B=\mu_{0}\frac{I}{2\pi r}$
	- $r$ je razdalja med gledano točko in vodnikom
	- $\mu_{0}$ je konstanta mag. polja
- $\frac{1}{\sqrt{\mu_{0}\varepsilon_{0}}}=c_{0}$ (hitrost svetlobe v vakumu)
- $B$ v tuljavi
	- $B=\mu_{0}\frac{IN}{l}$
- **Magnetni pretok** $\phi_{B}=BS\cos\phi;\ [Vs]$
- Induktivnost tuljave:
	- Magnetni pretok skozi 1 navoj (površine $S_{1}$)
		- $\phi_{B,1}=\frac{\mu_{0}NIS_{1}}{l}$
	- Mag. pretok skozi vseh N:
		- $\phi_{B}=\frac{\mu_{0}N^{2}IS_{1}}{l}$
	- **Induktivnost tuljave** $L=\frac{\mu\mu_{0}N^{2}S_{1}}{l};\ [H]$ enota henry
---
# Indukcija
- $U_{i}$ je inducirana napetost