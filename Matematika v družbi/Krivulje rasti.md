```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Matematicni model
## Splosni model rasti
$$\frac{dN}{dt}=aN$$
- $N$ -> Velikost narascajoce kolicine
- $t$ -> Cas
- $a$ -> Koeficient rasti 
## Standardna oblika
$$\frac{dN}{N*dt}=a(t)$$

---
# Eksponenta rast
- Koeficient $a(t)$ je **konstanten** -> $a_{0}$
- $N=N_{0}*e^{a_{0}t}$ 
---
# Rast po krivulji normalne porazdelitve
- *Bell curve*
- Linearno padajoci koef. rasti $a(t)=a_{0}(1-mt)$, $m$ -> konstanta
- $N=N_{0}*e^{a_{0}(t-\frac{m}{2}t^{2})}$
---
# Sinusni koeficient rasti
$$N=N_{0}*e^{a_{0}t-\frac{a_{1}}{\omega}(\cos(\omega t)-1)}$$
- Koeficient rasti -> $a(t)=a_{0}+a_{1}\sin(\omega t)$
---
# Logisticna rast
$$N=\frac{N_*}{1+(N_{*}/N_{0}-1)e^{-a_{0}t}}$$
- **Verhultova enacba**
- $\frac{dN}{dt}=a_{0}N(1-\frac{N}{N_{*}})$
- Koeficient rasti -> $a(N)=a_{0}-bN=a_{0}(1-\frac{N}{N_*})$
- $b$ -> Konstanta - koeficient goscenja $b=a_{0}/N_{*}$
- $N_{*}$ -> Konstanta - ravnotezna vrednost ob koncu rasti
- $tanh(x)$ podobno
- Prevojna tocka (simetricno razpolovi):
	- $N_{p}=\frac{N_{*}}{2}$ 
- Klodoida