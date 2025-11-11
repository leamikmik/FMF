- Obravnavali bomo metode/algoritme za resevanje nelin enacb kjer:
	- $f(x)=0$
	- $f:I\subseteq \Bbb R\to\Bbb R$
	- nelinearna funkcija
- Na splosno je o stevilu resitev enacbe $f(x)=0$ tezko karkoli povedati
	- npr: $f(x)=e^{x}+x$
		- ena resitev
# Obcutljivost nicel
- Def.: Naj bo $\alpha$ nicla dovoljkrat zvezno odvedljive funkcije $f$, torej $f(\alpha)=0$
	- Ce $f'(\alpha)\ne0$ je nicla **enostavna**
	- Ce $f'(\alpha)=0$ je nicla **veckratna**
	- Ce $f(\alpha)=0,f'(\alpha)=0,\dots,f^{(m-1)}(\alpha)=0$ in $f^{(m)}(\alpha)\ne0$ je nicla **m-kratna**
- Naj bo $\alpha$ enostavna nicla $f$ in $\bar\alpha$ priblizek za $\alpha$, tak da velja $f(\bar\alpha)=\epsilon$ 
	- $f(\alpha)=0,\alpha=f^{-1}(0)$
	- $f(\bar\alpha)=\epsilon,\bar\alpha=f^{-1}(\epsilon)$
	- $\bar\alpha=f^{-1}(0+\epsilon)=\alpha+\epsilon(f^{-1})'(0)+O(\epsilon^{2})$
	- $(f^{-1})'(0)=\frac{1}{f'(\alpha)}$
	- $|\bar\alpha-\alpha|\approx\epsilon|\frac{1}{f'(\alpha)}|$
	- **Obcutljivost enostavne nicle** => $|\frac{1}{f'(\alpha)}|$
- $\alpha$ je m-kratna nicla
	- taylorja $f(\alpha +\bar\alpha-\alpha)$
	- $\epsilon\approx \frac{f^{(m)}\alpha}{m!}(\bar\alpha-\alpha)^{m}$
	- $|\bar\alpha-\alpha|\approx\sqrt[m]{ \frac{m!}{|f^{(m)}(\alpha)|}}\sqrt[m]{\epsilon}$
	- za m-kratne nicle lahko pricakujemo, da jih bomo lahko zracunali le na natancnost $10^{\frac{-16}{m}}$
# Bisekcija
- Naj bo $f:\Bbb R\to\Bbb R$ zvezna, naj bo $[a,b]$ tak interval, da je $f(a)f(b)<0$ 
- Iz zveznosti sledi, da ima $f$ na intervalu vsaj eno ničlo
- Pri bisekciji razpolovimo interval $[a,b]$ in pogledamo na katerem od podintervalov je funkcija razlicno predznacena (aka. umes nicla). Postopek ponavljamo na tem podintervalu
- **Algoritem**:
	- Vhodni podatki: funkcija $f$, $a$, $b$, toleranca $\epsilon$
```
	while |b-a|>epsilon
		c = a + (b-a)/2
		if sigm(f(a))=sigm(f(c))
			a = c
		else
			b = c
		endif
	end
```
- Metoda ne deluje za nicle sode kratnosti
- Ce je na intervalu vec nicel bomo z bisekcijo izracunali samo eno
- Koliko korakov potrebujemo za izracun nicle na natancnost $\epsilon$?
	- $\frac{b-a}{2^{k}}<\epsilon$ => $k>\log_{2}(\frac{b-a}{\epsilon})$

- Navadna iteracija $f(x)=0$
	- $x=g(x)$
	- Izberemo $x_{0}$ ponavljamo $r=0,1,2,3$
	- $x_{r+1}=g(x_{r})$
	- zaustavitveni kriterij $\frac{|x_{r+1}-x_{r}|}{|x_{r+1}|}<$ toleranca
	- $g(\alpha)=\alpha$ kjer $\alpha$ fiksna tocka
	- Ce odvod g $<1$ je $\alpha$ privlacna fiksna tocka
## Hitrost konvergence
- $\alpha$ privlacna fiksna tocka iteracijske funk. $g$ in naj bo $x_{r+1}=g(x_{r})$ zaporedje iteracij
- Pravimo, da je hitrost konvergence tega zap. (red konvergence) enaka $p$ ce obstajata konstanti $c_{1},c_{2}$ da velja $c_{1}|x_{r}-\alpha|^{p}\le|x_{r+1}-\alpha|\le c_{2}|x_{r}-\alpha|^{p}$ za vse dovolj pozne clene zaporedja
- **Ekvivalentno** $|x_{r}-\alpha|=O(|x_{r}-\alpha|^{p})=C|x_{r}-\alpha|^{p}+$ cleni visjega reda
	- $\lim_{r\to\infty} \frac{|x_{r+1}-\alpha|}{|x_{r}-\alpha|^{p}}=C$
- naj bo iteracijska funkcija $g$ v okolci $\alpha$ fiksne tocke p-krat zvezno odvedljiva in naj velja $g(\alpha)=\alpha,g'(\alpha)=0,\dots,g^{(p-1)}(\alpha)=0,p^{(p)}\ne0$
	- Potem je red konvergence enak $p$
- $p=1$ lin konvergenca
- $p=2$ kvadraticna konv.
	- ko smo dovolj blizu resitve, se na vsakem koraku st. tocnik decimalk priblizno podvoji (v splosnem je $*p$)
- $p=3$ kubicna konv.
## Tangentna metoda (newtnova metoda)
- je poseben primer navadne iteracije
- resujemo enacbo $f(x)=0$
- Tangentna premica 
	- $p(x)=f(x_{0})+f'(x_{0})(x-x_{0})$
	- presecisce z premico $p(x)=0$
		- $x=x_{0}- \frac{f(x_{0})}{f'(x_{0})}$
		- to vzamemo za nov priblizek
	- postopek ponavljamo 
	- tj. tangentna metoda
		- izberemo zacetni $x_{0}$ ponavljamo $r=0,1,2,\dots$
		- $x_{r+1}=x_{r}- \frac{f(x_{r})}{f'(x_{r})}$
- drug nacin izpeljave/dokaz:
	- iz razvoja v Taylorja 
	- Naj bo $f(x_{r})\approx0$. Iscemo popravek $h$, da bo $f(x_{r}+h)=0$
	- $0=f(x_{r})+f'(x_{r})h+ \frac{1}{2}f''(x_{r})h^{2}+\dots$
	- zanemarimo od vlkjucno drugega odvoda
	- tj. $h=- \frac{f(x_{r})}{f'(x_r)}$
	- ker je to priblizek za popravek nam $x_{r}+h=x_{r}-\frac{f(x_{r})}{f'(x_{r})}=x_{r+1}$
- Iteracijska funkcija za tangento metodo je $g(x)=x- \frac{f(x)}{f'(x)}$