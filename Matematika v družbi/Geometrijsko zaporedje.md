```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Definicija
$$a_{n}=a_{1}*k^{n-1}$$
- *"Zap. je geometrijsko, kadar je količnik dveh sosednjih členov konstanten"*
- $k = \frac{a_{n+1}}{a_{n}}$
---
# Geometrijska sredina
$$g_{s}=\sqrt{a*b}$$
- Geometrijska sredina a in b je $\sqrt{a*b}$ 
- Vsak člen je geo. sredina sosedov
---
# Končna vrsta
$$S_{n}=a_0\frac{k^n-1}{k-1}=a_{1}+a_1*k+a_1*k^2+\dots+a_{1}*k^{n-1}$$
- Seštevek n-tih členov zaporedja
---
# Eulerjevo število
$$e=\lim_{m\to\infty}{(1+\frac{1}{m})^{m}}\approx2.71828$$

---
# Obrestni račun
## Varčevanje več kot 1 leto
- **Enostavni** => $a_{n}=a_{0}+n\sigma a_{0}$
	- $\sigma$ -> Obrestna mera \[%/leto]
	- <u>Vsako leto</u> $n$ <u>se prišteje obrest</u>
- **Obrestno** => $a_{n}=a_{0}r^{n}$
	- $r=1+\sigma$ -> Faktor obresti
	- <u>Vsako leto</u> $n$ <u>se poveča vrednost za</u> $\sigma$%

## Varčevanje manj kot 1 leto
- *Kapitalizacijska doba* -> čas varčevanja do pripisa obresti k glavnici
- **Relativna obrestna mera**:
	- Letna  => $\sigma$
	- Četrtletna => $\sigma/{4}$
	- Mesečna => $\sigma/12$
	- Dnevna => $\sigma/365$
- **Konformna obrestna mera** => $r_{m}=\sqrt[m]{r}$
- <u>Varčevanje z mesečnim pologom in mesešnimi stroški</u> 
	- $a_{n}=a_{0}\frac{r^{n+1}-1}{r-1}-c\frac{r^{n}-1}{r-1}$
	- Oz če ni vplačila po zaključku varčevanja $a_{m}=(a_{0}r-c)\frac{r^{m}-1}{r-1}$
	- $a_{0}$ -> Mesečni polog
	- $r$ -> Mesečni faktor obresti
	- $c$ -> Mesečni stroški 
	
## Krediti
- $a_{0}$ -> **Posojilo**
- $r=\sqrt[12]{r_{letni}}$
- **Mesečno plačilo** => $b=a_{0}\frac{r^{m}(r-1)}{r^{m}-1}$
---
