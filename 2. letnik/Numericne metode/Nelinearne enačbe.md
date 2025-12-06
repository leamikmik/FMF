```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Uvod
- Obravnavali bomo metode/algoritme za reševanje nelinearnih enačb oblike:
	- $f(x)=0$
	- $f:I\subseteq \Bbb R\to\Bbb R$
	- nelinearna funkcija
- Za obstoj rešitve je težko veliko povedati.
	- En pogoj je Legrangeev izrek
		- Ko je $f$ realna zvezna funkcija na $[a,b]$ in $f(a)f(b)<0$
		- Potem je nek $\phi\in[a,b]$ da $f(\phi)=0$
## Občutljivost ničel
- Def.: Naj bo $\alpha$ ničla dovoljkrat zvezno odvedljive funkcije $f$, torej $f(\alpha)=0$
	- Ce $f'(\alpha)\ne0$ je ničla **enostavna**
	- Ce $f'(\alpha)=0$ je ničla **večkratna**
	- Ce $f(\alpha)=0,f'(\alpha)=0,\dots,f^{(m-1)}(\alpha)=0$ in $f^{(m)}(\alpha)\ne0$ je ničla **m-kratna**
- Naj bo $\alpha$ enostavna ničla $f$ in $\bar\alpha$ približek za $\alpha$, tak da velja $f(\bar\alpha)=\epsilon$ 
	- $f(\alpha)=0,\alpha=f^{-1}(0)$
	- $f(\bar\alpha)=\epsilon,\bar\alpha=f^{-1}(\epsilon)$
	- $\bar\alpha=f^{-1}(0+\epsilon)=\alpha+\epsilon(f^{-1})'(0)+O(\epsilon^{2})$
	- $(f^{-1})'(0)=\frac{1}{f'(\alpha)}$
	- $|\bar\alpha-\alpha|\approx\epsilon|\frac{1}{f'(\alpha)}|$
	- **Občutljivost enostavne ničle** => $|\frac{1}{f'(\alpha)}|$
- $\alpha$ je m-kratna ničla
	- taylorja $f(\alpha +\bar\alpha-\alpha)$
	- $\epsilon\approx \frac{f^{(m)}\alpha}{m!}(\bar\alpha-\alpha)^{m}$
	- $|\bar\alpha-\alpha|\approx\sqrt[m]{ \frac{m!}{|f^{(m)}(\alpha)|}}\sqrt[m]{\epsilon}$
	- za m-kratne ničle lahko pričakujemo, da jih bomo lahko izračunali le na natančnost $10^{\frac{-16}{m}}$
---
# Bisekcija
- Naj bo $f:\Bbb R\to\Bbb R$ zvezna, naj bo $[a,b]$ tak interval, da je $f(a)f(b)<0$ 
- Iz zveznosti sledi, da ima $f$ na intervalu vsaj eno ničlo
- Pri bisekciji razpolovimo interval $[a,b]$ in pogledamo na katerem od podintervalov je funkcija različno predznačena (aka. vmes ničla). Postopek ponavljamo na tem podintervalu
- **Algoritem**:
	- Vhodni podatki: funkcija $f$, $a$, $b$, toleranca $\epsilon$
```
	while |b-a|>epsilon
		c = a + (b-a)/2
		if sign(f(a))=sign(f(c))
			a = c
		else
			b = c
		endif
	end
```
- Metoda ne deluje za ničle sode kratnosti
- Ce je na intervalu več ničel bomo z bisekcijo izračunali samo eno
- Koliko korakov potrebujemo za izracun nicle na natancnost $\epsilon$?
	- $\frac{b-a}{2^{k}}<\epsilon$ => $k>\log_{2}(\frac{b-a}{\epsilon})$
---
# Navadna iteracija
- $f(x)=0$
- $x=g(x)$ kjer je $g(x)$ iteracijska funkcija
	- Dobimo da iz $f(x)=0$ izpostavimo $x$ (z tem lahko dobimo več različnih $g$, z različno konvergenco)
- Izberemo $x_{0}$ ponavljamo $r=0,1,2,3$
- $x_{r+1}=g(x_{r})$
- $g(x)$ mora imeti fiksne točke v ničlah $f(x)$
- zaustavitveni kriterij $\frac{|x_{r+1}-x_{r}|}{|x_{r+1}|}<$ toleranca
- $g(\alpha)=\alpha$ kjer $\alpha$ **fiksna točka**
	- torej da izračunamo fiksne točke nastavimo enačbo $x=g(x)$
- Če $|g'(\alpha)|<1$ je $\alpha$ **privlačna** fiksna točka
	- $|g'(x)|<1$ => dobimo interval iz katerega lahko izberemo začetne približke 
- Oceno napake približka => $|x_{r}-\alpha|$
	- $\alpha$ je točna rešitev (ničla)
	- $|x_{r}-\alpha|\le \frac{m}{1-m}|x_{r}-x_{r-1}|$
	- $m$ je število za katerega velja $|g'(x)|\le m<1$ za $\forall x\in I$ kjer je $I$ interval, ki vsebuje $\alpha$ (lahko vzamemo največjo vrednost $|g'(x)|$ na danem intervalu)
## Hitrost konvergence
- $\alpha$ privlačna fiksna točka iteracijske funk. $g$ in naj bo $x_{r+1}=g(x_{r})$ zaporedje iteracij
- Pravimo, da je hitrost konvergence tega zap. (red konvergence) enaka $p$ če obstajata konstanti $c_{1},c_{2}$ da velja $c_{1}|x_{r}-\alpha|^{p}\le|x_{r+1}-\alpha|\le c_{2}|x_{r}-\alpha|^{p}$ za vse dovolj pozne člene zaporedja
- **Ekvivalentno** $|x_{r}-\alpha|=O(|x_{r}-\alpha|^{p})=C|x_{r}-\alpha|^{p}+$ členi višjega reda
	- $\lim_{r\to\infty} \frac{|x_{r+1}-\alpha|}{|x_{r}-\alpha|^{p}}=C$
- Naj bo iteracijska funkcija $g$ v okolici $\alpha$ fiksne točke $p$-krat zvezno odvedljiva in naj velja $g(\alpha)=\alpha,g'(\alpha)=0,\dots,g^{(p-1)}(\alpha)=0,g^{(p)}\ne0$
	- Potem je red konvergence enak $p$
- $p=1$ linearna konvergenca
- $p=2$ kvadratna konv.
	- ko smo dovolj blizu rešitve, se na vsakem koraku število točnih decimalk približno podvoji (v splošnem je $*p$)
- $p=3$ kubična konv.
---
# Tangentna metoda (newtnova metoda)
- je poseben primer navadne iteracije
- rešujemo enačbo $f(x)=0$
- Tangentna premica:
	- $p(x)=f(x_{0})+f'(x_{0})(x-x_{0})$
	- Presečišče z premico $p(x)=0$
		- $x=x_{0}- \frac{f(x_{0})}{f'(x_{0})}$
		- to vzamemo za nov približek
	- postopek ponavljamo 
	- tj. **tangentna metoda**
		- izberemo začetni $x_{0}$ ponavljamo $r=0,1,2,\dots$
		- $x_{r+1}=x_{r}- \frac{f(x_{r})}{f'(x_{r})}$
- drug način izpeljave/dokaz:
	- iz razvoja v Taylorja 
	- Naj bo $f(x_{r})\approx0$. Iščemo popravek $h$, da bo $f(x_{r}+h)=0$
	- $0=f(x_{r})+f'(x_{r})h+ \frac{1}{2}f''(x_{r})h^{2}+\dots$
	- zanemarimo od vključno drugega odvoda
	- tj. $h=- \frac{f(x_{r})}{f'(x_r)}$
	- ker je to priblizek za popravek nam $x_{r}+h=x_{r}-\frac{f(x_{r})}{f'(x_{r})}=x_{r+1}$
- Iteracijska funkcija za tangento metodo je $g(x)=x- \frac{f(x)}{f'(x)}$