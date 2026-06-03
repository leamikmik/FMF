```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Uvod
- Delimo na:
	1. Opisno statistiko (zbiranje, opisovanje podatkov, ...)
	2. Analitično statistiko (uporaba podatkov pri sklepanju)
- **Populacija** -> Množica el. pri katerih lahko opazujemo ali merimo neko merljivo količino
	- oz. neka neprazna množica $G$, na kateri je def. merljiva količina, merljiva funkcija $X$
	- $X$ imamo za [[Verjetnost#Slučajne spremenljivke|slučajno spremenljivko]], na ver. prostoru $G$
- **Vzorec**:
	1. Vzorec mora biti izbran nepristransko
	2. Vzorec mora biti dovolj velik
	- Dobremu vzorcu rečemo da je *reprezentativen*
	- Slučajnemu vektorju $(X_{1},X_{2},...,X_{n})$ rečemo vzorec
		- $X_{i}$ je zaporedna meritev, $n$ pa velikost vzorca
		- Vrednosti iz ene meritve zapišemo $(x_{1},\dots,x_{n})$ in rečemo realizacija vzorca
	- Da se predpostaviti da so vse spremenljivke enako porazdeljene in so med seboj neodvisne. Potem temu rečemo *enostaven slučajni vzorec*
- **Osnovni izrek statistike** -> Večkrat ko izvedemo meritve bolj se frekvenca bliža verjetnosti dogodka
---
# Opisovanje podatkov in računanje vzorčnih količin
- Zapis podatkov:
	1. **Neurejeno** -> Samo naštejemo vrednosti v poljubnem vrstnem redu z vsemi ponavljanji
	2. **Frekvenčna tabela** -> Podamo le različne vrednosti in njihove frekvence. Št. različnih vrednosti označimo z $r$
	3. **Grupirane v razrede** -> Enako kot frekvenčna tabela, le da podatke razdelimo na razrede in frekvence razredov. Vsi razredi so enako veliki. $x_{i}$ je sredina razreda
	4. **Grafično** -> Graf, histogram, frekvenčni kolač, ...
- Karakteristike populacije:
	-  Redko delamo meritve na celi populaciji, zato iščemo ocene v vzorcu (*vzorčne ocene ali mere*)
	- **Sredina populacije** $\mu$ -> matematično upanje slučajne spremenljivke $X$ na populaciji
		- *Vzorčni modus* => najpogostejša vrednost v vzorcu
		- *Vzorčno mediano* => srednja vrednost v urejenem vzorcu
		- **Vzorčno povprečje** => $\bar x= \frac{1}{n}\sum\limits_{i=1}^{n}x_{i}$
			- Če frekvenčna tabela -> $\bar x= \frac{1}{n}\sum\limits_{i=1}^{r}k_{i}x_{i}$
	- **Povprečni odklon od sredine populacije** $\sigma$ -> standardna deviacija spremenljivke $X$
		- *Vzorčni razmah* => razlika med največjo in najmanjšo vrednostjo
		- **Vzorčna disperzija** => $s^{2}_{0}= \frac{1}{n}\sum\limits_{i=1}^{n}(x_{i}-\bar x)^{2}$
			- Če frekvenčna tabela -> $s^{2}_{0}= \frac{1}{n}\sum\limits_{i=1}^{r}k_{i}(x_{i}-\bar x)^{2}$
			- Deviacija -> $s_{0}=\sqrt{s^{2}_{0}}$
		- **Popravljena vzorčna disperzija** => $s^{2}= \frac{1}{n-1}\sum\limits_{i=1}^{n}(x_{i}-\bar x)^{2}$
			- Deviacija -> $s=\sqrt{s^{2}}$
## Opisna statistika
- **Mediana** => $P(X\le Me)\ge \frac{1}{2}$ oz. $P(X> Me)\le \frac{1}{2}$
	- Za znane vzorce lahko samo vzamemo $\frac{n}{2}$-ti element
	- Če $n$ liho vzamemo povprečje elementov levo in desno od $\frac{n}{2}$
- **$\alpha$-kvantil** => $P(X\le x_{\alpha})\ge\alpha$ oz $P(X>x_\alpha)\le\alpha$
	- Mediana v bistvu $\frac{1}{2}$-kvantil
	- To zgoraj da prvi del kvantila
- **Kvartilni razmik** => Razlika med $x_{1/4}$ in $x_{3/4}$ v $\frac{1}{4}$-kvantilu
---
# Porazdelitveni zakoni vzorčnih statistik
- **Vzorčna statistika** -> Funkcije vzorca, kot slučajnega vektorja
	- Poljubna simetrična funkcija $Y=g(X_{1},\dots,X_{n})$
	- Spet slučajni vektor
	- Standardno deviacijo $Y$ imenujemo tudi *standardna napaka*
## Vzorčno povprečje
$$\overline X = \frac{1}{n}\sum\limits^{n}_{i=1}X_{i}$$
- Denimo $E(X)=\mu$ in $\sigma(X)=\sigma$
- $E(\overline X)= \mu$
- $D(\overline X)= \frac{\sigma^{2}}{n}$ oz. $\sigma(\overline X)= \frac{\sigma}{\sqrt{n}}$
- Če imamo velik $n$ (več od $30$) potem lahko rečemo da ima $\overline X$ normalno porazdelitev $N(\mu, \frac{\sigma}{\sqrt{n}})$
	- Sedal lahko vzamemo $N(0,1)$ porazdeljeno sprem. $Z$ kjer $\overline X= \frac{\sigma}{\sqrt{n}}Z+\mu$
	- Za $P(\overline X \ge \alpha)$ potem $P(Z\le (\alpha-\mu) \sqrt{n}/\sigma)$ in lahko vrednost pogledamo na tabeli
- Deluje dobro samo če poznamo $\sigma$
## Vzorčna disperzija
$$S^{2}_{0}=\frac{1}{n}\sum\limits_{i=1}^{n}(X_{i}-\overline X)^{2};\ S^{2}=\frac{1}{n-1}\sum\limits_{i=1}^{n}(X_{i}-\overline X)^{2}$$
- $\chi^{2}=\frac{n}{\sigma^{2}}S^{2}_{0}=\frac{n-1}{\sigma^{2}}S^{2}= \frac{1}{\sigma^{2}}\sum\limits_{i=1}^{n}(X_{i}-\overline X)^{2}$ 
	- $N(n-1, \sqrt{2n-2})$ za velike $n$
- $E(S^{2}_{0})=(n-1)\sigma^{2}/n$ in $E(S^{2})=\sigma^{2}$
- $D(S^{2}_{0})=(2n-2)\sigma^{4}/n^{2}$ in $D(S^{2})=2\sigma^{4}/(n-1)$
## Studentova porazdelitev
- Uporabimo če ne poznamo $\sigma$
- $T= \frac{\overline X-\mu}{S}\sqrt{n}$
- $P(T<t)= \frac{\Gamma(n/2)}{\sqrt{n}\Gamma((n-1)/2)\sqrt{n-1}}\int\limits^{t}_{-\infty}(1+z^{2}/(n-1))^{-n/2}dz$
	- oz. $p(t)= \frac{1}{\sqrt{n-1}B( \frac{n-1}{2}, \frac{1}{2} )}(1+t^{2}/(n-1))^{-n/2}$
	- oz. $S(n-1)$
- $S(1)$ je znana Cauchyjeva porazdelitev z $p(t)= \frac{1}{\pi(1+t^{2})}$
- Če $n\to\infty$ in potem $p(t)= \frac{1}{\sqrt{2\pi}}e^{-t^{2}/2}$
---
# Cenilke
- Iščemo parameter neke porazdelitve
- Cenilka je nova slučajna spremenljivka, npr. $\bar a$
- **Nepristranska** => $E(\bar a)=a$
- **Doslednost** => $D(\bar a)=0$ ko gre velikost vzorca proti $\infty$
- **Metoda momentov** 
	- Nastavimo $E(X)=\overline X$ 
	- Nekje v $E(X)$ se ti pojavi parameter
	- Obračaš enačbo dokler ne izpostaviš cenilke
- **Metoda maksimalne zanesljivosti**
	- $L(a)=\prod\limits_{i=1}^{n}P(X_{i}=x)=\prod\limits_{i=1}^{n}p_{X}(x_{i})$ če se nekje v verjetnosti pojavi $x$ ga moramo pustiti v produktu
	- $l(a)=\ln L(a)$ razdeliš logaritem na več logaritmov
	- Nastaviš $\frac{dl}{da}\approx0$ in izraziš $a$
---
# Interval zaupanja
1. Poiščemo cenilko za parameter npr. $\bar a$
2. $c: \Phi(c)= \frac{\beta}{2}$ kjer je $\beta$ stopnja zaupanja
3. $\Delta: \Delta=c*\sqrt{ \frac{D(X)}{n} }$
4. Potem je interval zaupanja $[\bar a-\Delta,\bar a +\Delta]$
- Za $N(\mu,\sigma)$:
	- Če ne vemo $\sigma$ vzamemo za $D(X)=S^{2}$ in $c_{\mu}=t_{\frac{1+\beta}{2}}(n-1)$
	- Če iščemo $\sigma$ vzamemo vzamemo $c_{1,2}=\chi^{2}_{\frac{1\mp\beta}{2}}(n-1)$ in interval potem $S\sqrt{\frac{n-1}{c_{2}}}\le\sigma\le S\sqrt{ \frac{n-1}{c_{1}}}$
---
# Hipoteze
- Vedno preizkušamo hipotezo proti alternativni
- Stopnja značilnosti $\alpha$ -> verjetnost da zavrnemo pravilno hipotezo
1. **Test $Z$** -> predpostavljamo $X\approx N(\mu,\sigma)$; $\sigma$ znan, $\mu$ neznan
	- Hipoteza $H_{0}(\mu=\mu_{0});\ H_{1}(\mu\ne\mu_{0})$
	- $Z= \frac{\bar X-\mu_{0}}{\sigma}\sqrt{n}\approx N(0,1)$
	- $H_{0}$ zavrnemo če $Z$ leži v t.i. kritičnem območju $K_{\alpha}=(-\infty,-z_{\alpha/2}]\cup[z_{\alpha/2},\infty)$
		- $P(Z>z_{\alpha/2})=\frac{\alpha}{2}$ dobimo iz tabele
2. **Test $T$** -> $X\approx N(\mu,\sigma)$; $\mu,\sigma$ nista znana
	- Hipoteza $H_{0}(\mu=\mu_{0});\ H_{1}(\mu\ne\mu_{0})$
	- $T= \frac{\bar X-\mu_{0}}{S}\sqrt{n}\approx \text{Student}(n-1)$
		- $S^{2}=\frac{1}{n-1}\sum\limits_{i=1}^{n}(X_{i}-\overline X)^{2}$
	- $K_{\alpha}=(-\infty,-t_{\alpha/2}]\cup[t_{\alpha/2},\infty)$
		- $P(T>t_{\alpha/2})=\frac{\alpha}{2}$ dobimo iz tabele
3. **Test $\chi^{2}$** (oz. test variance) -> $X\approx N(\mu,\sigma)$, neznan $\sigma$
	- $H_{0}(\sigma=\sigma_{0});\ H_{0}(\sigma\ne\sigma_{0})$
	- $\chi^{2}= \frac{(n-1)S^{2}}{\sigma_{0}^{2}}\approx \chi^{2}(n-1)$
	- $K_{\alpha}=(-\infty,\chi^{2}_{\alpha/2}(n-1))\cup(\chi^{2}_{1-\alpha/2}(n-1),\infty)$
4. **Studentov primerjalni test** -> 2 neodvisna vzorca velikosti $m$ in $n$, enak $\sigma$
	- $(X_{1},\dots,X_{m})$ kjer $X\approx N(\mu_{x},\sigma)$
	- $(Y_{1},\dots,Y_{N})$ kjer $Y\approx N(\mu_{y},\sigma)$
	- Skupna disperzija $S^{2}= \frac{\sum\limits_{i=1}^{m}(X_{i}+\bar X)^{2}+\sum\limits_{i=1}^{n}(Y_{i}-\bar Y)^{2}}{m+n-2}$
	- Testna statistika $T= \frac{\bar X-\bar Y}{S}\sqrt{\frac{mn}{m+n}}\approx \text{Student}(m+n-2)$
	- Testiramo $H_{0}(\mu_{x}=\mu_{y});\ H_{1}(\mu_{x}\ne \mu_{y})$
		- Enako kritično območje kot test $T$
	- Če pa $H_{0}(\mu_{x}=\mu_{y});\ H_{1}(\mu_{x}>\mu_{y})$
		- $K_{\alpha}=(-\infty,-t_{\alpha}]\cup[t_{\alpha},\infty)$
5. **Test $H_{0}(\sigma_{x}=\sigma_{y});\ H_{1}(\sigma_{x}\ne\sigma_{y})$** -> 2 neodvisna vzorca velikosti $m$ in $n$
	- $(X_{1},\dots,X_{m})$ kjer $X\approx N(\mu_{x},\sigma_{x})$
	- $(Y_{1},\dots,Y_{n})$ kjer $Y\approx N(\mu_{y},\sigma_{y})$
	- Testna statistika $F= \frac{S^{2}_{X}}{S_{Y}^{2}}\approx F(m-1,n-1)$
		- Fischerjeva porazdelitev oz. Snedikorjeva 
		- $F(m,n)$
			- $p(x)=\frac{m^{\frac{m}{2}}*n^{\frac{n}{2}}*(x^{\frac{m}{2}}-1)}{B(\frac{m}{2},\frac{n}{2})(n+mx)^{\frac{m+n}{2}}}$ če $x\le 0$
			- podobna $\chi^{2}$
			- $E(F)=\frac{n}{n-2};\ n\ge 3$
	- $P(F\le c_{1})= \frac{\alpha}{2}=P(F\ge c_{2})$
	- Kritično območje $K_{\alpha}=[0,c_{1}]\cup[c_{2},\infty)$
6. **Test $\chi^{2}$** -> $X$ neznane porazdelitve $F$, velikosti $n$
	- $H_{0}(F=F_{0});\ H_{1}(F\ne F_{0})$
	- Zalogo vrednosti razdelimo na $r$ razredov $S_{1},\dots,S_{r}$
		- različni rezultati odvisno od $r$
	- $p_{k}=P(X\in S_{k}|H_{0});\ k\in\{1,\dots,r\}$
		- $\sum\limits p_{k}=1$
	- $N_{k}$ => št. vrednosti vzorca $S_{k}$
		- $\sum\limits N_{k}=n$
	- $\chi^{2}=\sum\limits_{k=1}^{r} \frac{(N_{k}-np_{k})^{2}}{np_{k}}\approx\chi^{2}(r-1)$
	- $K_\alpha=[\chi^{2}_{1-\alpha}(r-1),\infty)$
---
# Linearna regresija
$$Y=a+bX+U$$
- $U\approx N(0,\sigma)$ napaka, $\sigma$ tudi neznan
- $a, b$ neznana parametra
- $\tilde Y=a+bX$ regresijska premica
- Za $x_{1},\dots,x_{n}$ dobimo $Y_{1},\dots,Y_{n}$ kjer $Y_{i}\approx N(a+bx_{k},\sigma)$
- Radi bi ocenili paremetra $a,b$
- $\hat b= \frac{S_{XY}- \frac{1}{n}S_{X}S_{Y}}{S_{XX}- \frac{1}{n}S^{2}_{X}}$ in $\hat a = \bar Y-\hat b\bar x$
	- $S_{X}=\sum\limits_{k=1}^{n}x_{k}$
	- $S_{Y}=\sum\limits^{n}_{k=1}Y_{k}$
	- $S_{XX}=\sum\limits_{k=1}^{n}x_{k}^{2}$
	- $S_{XY}=\sum\limits_{k=1}^{n}x_{k}Y_{k}$
- Interval zaupanja:
	- $\Delta a=\hat a \pm t_{\frac{a+1}{2}}(n-2)* \frac{S}{\sqrt{n- S_{X}^{2}/S_{XX}}}$
	- $\Delta b=\hat b\pm t_{\frac{a+1}{2}}(n-2)* \frac{S}{\sqrt{S_{XX}- S_{X}^{2}/n}}$
- $T_{a}= \frac{\hat a-a}{S}\sqrt{n- \frac{S_{X}^{2}}{S_{XX}}}\approx\text{Student}(n-2)$
- $T_{b}= \frac{\hat b-b}{S}\sqrt{S_{XX}- \frac{S_{X}^{2}}{n}}\approx\text{Student}(n-2)$
	- Potem lahko delamo hipoteze $H_{0}(a=a_{0})$ in $H_{0}(b=b_{0})$
		- $|T_{a}|>t_{\alpha/2}$ in $|T_b|>t_{\alpha/2}$
		- Ali $a_{0}\in\Delta a$ oz. $b_{0}\in\Delta b$
- $R^{2}= \frac{RVK}{SVK}= 1- \frac{VKR}{SVK}$ -> Koeficient determinacije
	- $SVK=VKR+RVK$
	- $SVK=\sum\limits_{i=1}^{n}(Y_{i}-\bar Y)^{2}$
	- $VKR=\sum\limits_{i=1}^{n}(Y_{i}-\tilde Y_{i})^{2}$
---
# Testiranje neodvisnosti
- Prilagoditveni test
	- $H_{0}$ je, da sta spremenljivki $A$ in $B$ neodvisni
	- ![[Pasted image 20260603123037.png]]
	- Cenilke
		- $\hat p _{i}=\frac{1}{n}\sum\limits^{s}_{j=1}X_{ij}$
		- $\hat q_{i}= \frac{1}{n}\sum\limits^{r}_{i=1}X_{ij}$
	- Hipotezo zavrnemo če $\chi^{2}>c$
		- $\chi^{2}=\sum\limits_{i=1}^{r}\sum\limits_{j=1}^{s} \frac{(X_{ij}-n\hat p_{i}\hat q_{j})^{2}}{n\hat p_{i}\hat q_{j}}$
		- $c= \chi^{2}_{1-\alpha}((r-1)(s-1))$
---
# Neparametrični testi
- Dozdej preiskušal hipoteze na znanih porazdelitvah
- Sedaj ne moremo privzeti porazdelitve 
1. **Test z znaki**
	- Ista populacija za $X$ in $Y$
		- $X$ porazdeljen z $F_{X}$
		- $Y$ z $F_{Y}$
	- $D_{i}=X_{i}-Y_{i}\ne 0$ 
		-  Če je enako nič, ignoriramo vrednosti (t.j. zmanjšamo $n$ in preskočimo razliko)
	- $H_{0}(X\approx Y)$
		- Potem $P(D_{i}>0)=\frac{1}{2}=P(D_{i}<0)$
		- $S^{+}$ => št. pozitivnih (oz. $X_{i}>Y_{i}$)
		- $S^{-}$ => št. negativnih (oz. $X_{i}<Y_{i}$)
		- Kritično območje $K_\alpha=\{k\in\{1,\dots,n\}\le k_{\alpha}\text{ ali } k>n-k_{\alpha}\}$
			- Če $S^{+}\in K_{\alpha}$ zavrnemo $H_{0}$ 
			- $P(S^{+}\le k_\alpha)\ge \frac{\alpha}{2}$ oz. $\alpha$ za enostranski test
	- **Studentov primerjalni**
		- Ko velik $n$ je $S^{+}\approx N(\frac{n}{2},\frac{\sqrt{n}}{2})$
		- $Z= \frac{2S^{+}-n}{\sqrt{n}}\approx N(0,1)$
		- $K_{\alpha}=(-\infty,-z_{\alpha/2}]\cup[z_{\alpha/2},\infty)$
2. **Inverzijski test**
	- $X=(X_{1},\dots,X_{m})$ in $Y=(Y_{1},\dots,Y_{n})$
		- $m\le n$
	- $H_{0}(F_{X}=F_{Y})$
	- $R_{i}=\text{rang}(X_{i})=k$ če $X_{i}=X_{k}$
		- oz. mesta kjer je vrednost iz $X$
	- $V=\sum\limits R_{i}\approx N( \frac{m(m+n+1)}{2}, \sqrt{ \frac{mn(m+n+1)}{12}})$
		- $Z= \sqrt{\frac{12}{mn(m+n+1)}}(V- \frac{m(m+n+1)}{2})\approx N(0,1)$
		- $H_{0}$ zavrnemo če $Z$ leži v $K_{\alpha}=(-\infty,-z_{\alpha/2}]\cup[z_{\alpha/2},\infty)$
			- $P(Z>z_{\alpha/2})=\frac{\alpha}{2}$ dobimo iz tabel oz. $\alpha$ za enostransko
---
# Rodovne funkcije
- Spremenljivka $X$ vrednosti v $\Bbb N$