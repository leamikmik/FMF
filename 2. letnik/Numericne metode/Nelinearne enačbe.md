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