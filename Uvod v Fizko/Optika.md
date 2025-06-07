```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Valovna optika
- Svetloba = EM valovanje
- $\lambda\ [m]$ -> valovna dolžina
	- $\nu= \frac{c_{0}}{\lambda}$ -> frekvenca glede na val. dolžino in svetlobno hitrost
	- vidna svetloba: $400nm\lesssim\lambda\lesssim800nm$
- $c_{0}\approx3*10^{8} \frac{m}{s}$ -> svetlobna hitrost
- Elektromagnetno valovanje se razlikuje od mehanskega, ker se lahko širi skozi prazen prostor
## Lom svetlobe
$$c=\frac{c_{0}}{n};\ n\ge1$$
- $n\ [/]$ -> lomni količnik
	- Zrak => $\sim 1$; voda => $1.33$ (za vidno svetlobo)
- $\alpha$ -> vpadni kot (med žarkom in pravokotnico na snov)
	![[Pasted image 20250607123518.png]]
	- $\alpha'=\alpha$ -> odbojni kot (**odbojni zakon**)
	- $\beta$ -> kot med prepuščenimi žarki in pravokotnico
		- $\sin\beta=\sin\alpha \frac{n_{1}}{n_{2}}$ (**lomni zakon**)

---
# Fotometrija
## Svetlobni tok
- **Okvir** porvšine ($S$), *pravokoten* na smer valovanja
- $P=\frac{W}{t};\ [W]$ -> energijski tok svetlobe
	- $W$ => energija svetlobe, ki v časi pretoči skozi okvir
- $j=\frac{P}{S};\ [\frac{W}{m^{2}}]$ -> jakost svetlobnega toka
## Odbojnost (albedo)
- $j$ -> jakost, ki pada pravokotno na površino snovi
- $a=\frac{j_{a}}{j};\ [/]$ => odbojnost
	- $j_{a}$ -> tok po odboju
	- $0\le a\le 1$
		- $a=0$ -> črno telo (ni odboja)
		- $a=1$ -> belo telo (totalen odboj)
	- $a=a(\lambda)$ => barve
## Meritev svetlobnega toka
- Merimo na črnem telesu ($a\approx 0$), ki je izoliran od okolice
	- $S$ ploskev na katero *pravokotno* padajo žarki
	- Absorbira $\Delta T$ temp.
- $P= \frac{mc_{p}\Delta T}{(1-a)t}$
	- Ker je $\perp$ vpad => $j=\frac{mc_{p}\Delta T}{(1-a)tS}$
	- Velja samo, če telo ne oddaja toplote in so njegove sevalne izgube zanemarljive
## Občutena jakost toka
- $j_{o}$ -> kako močna se zdi svetloba (povprečje ankentiranih prostovoljcev)
- $j_{o}=\eta j;\ [\frac{lm}{m^{2}}]$; $\eta=\eta(\lambda)$ -> občutljivost
## Osvetljenost
$$j'=j\cos\alpha$$
- $\alpha$ -> vladni kot svetlobe (glede na $\perp$)
## Svetlobna moč svetila
-  $P^{*};\ [W]$ => celoten energijski tok, ki ga v obliki EM valovanja oddaja svetilo
	- $P^{*}<<P$
- Npr. svetilo sveti *enakomerno na vse strani* => $j=\frac{P^{*}}{4\pi r^{2}}$
- $j^{*}$ => (površinska) gostota svetlobne moči
	- **Stefanov zakon** -> $j^{*}=(1-a)\sigma T^{4}$ ($\sigma$ je konstanta)
	- Če vsi deli površine svetijo enako močno => $j^{*}=\frac{P^{*}}{S_{sv}}$
- **Wienov zakon** => $\lambda_{vrh}=\frac{k_{w}}{T}$ 
	- $k_{w}\approx2.9*10^{-3}mK$
	- Za toplejše telo, bo valovna dolžina, pri kateri bo oddalo večino svojega sevanja, manjša.

---
# Geometrijska optika
## Preslikave
- Žarki so ravne črte, lomljene na enem ali nekaj mestih
- Vsaka točka predmeta seva žarke na vse strani
- Pot žarkov se zlomi npr. zaradi zrcal ali leč
## Krogelna zrcala
 1. Konkavno krogelno zrcalo
	 - $R$ -> krivinski radij zrcala
	 - $f=\frac{R}{2}$ -> gorišče
	 - $a, b$ -> razdalja predmeta od zrcala in razdalja preslikave od zrcala
	 - $y, y'$ -> višina predmeta in višina slike
		 - $y'>0$ -> pokončna slika
		 - $y'<0$ -> slika obrnjena
	- $\frac{1}{a}+ \frac{1}{b}= \frac{1}{f}$ -> **Enačba kokavnega zrcala**
	- $\frac{y'}{y}= \frac{f}{f-a}=- \frac{b}{a}$
2. Konveksno krogelno zrcalo
	- Preslikava je utvara
	- $\frac{1}{a}+ \frac{1}{b}= - \frac{1}{f}$
	- $\frac{y'}{y}= \frac{f}{a+f}$
3. Bikonveksna leča
	- zbiralna leča
	- $\frac{1}{a}+ \frac{1}{b}= \frac{1}{f}$
	- $\frac{y'}{y}= \frac{f}{f-a}$
	- $b>0$ => slika realna; $b<0$ => slika navidezna
4. Bikonkavna leča
	- razpršilna leča
	- $\frac{1}{a}+ \frac{1}{b}= - \frac{1}{f}$
	- $\frac{y'}{y}= \frac{f}{a+f}$
	- $b<0$ -> slika navidezna
## Linearna povečava
- za realne slike
- $N_{1}=| \frac{y'}{y} |= \frac{f}{a-f}$ (konkavna zrcala in zbiralne leče)
## Človeško oko
- $b_{0}$ je fiksen
- $f= \frac{ab_{0}}{a+b_{0}}$
- V možganih se slika obrne
- Če $b \ne b_{0}$ (slika ni ostra):
	- daljnovidnost -> $b=b_{0}$ samo za oddaljene predmete
	- kratkovidnost -> $b=b_{0}$ samo za bližnje predmete
## Optične naprave
- $\alpha$ -> zorni kot
	- $\tan \alpha= \frac{y}{a}$
- Včasih $\alpha$ premajhen, da bi videli podrobnosti
	1. $y\to 0$ -> premajhen predmet
	2. $a\to\infty$ -> preveč oddaljen predmet
	- $\tan\alpha\simeq\alpha\to0$
- Optična naprava **poveča zorni kot** -> $N_{2}= \frac{\tan\alpha'}{\tan\alpha}$
1. Lupa
	- Zbiralna leča, ki jo postavimo med predmet in oko
	- Predmet <u>na goriščni razdalji</u> pred lupo ($a=f$)
	- $N_{2}=\frac{a_{0}}{f}$
2. Mikroskop => $N_{2}= \frac{a_{0}l}{f_{1}f_{2}}$
3. Daljnogled => $N_{2}=\frac{f_{1}}{f_{2}}$
