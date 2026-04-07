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