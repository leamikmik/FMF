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
	- $t_{p}=\frac{1}{a_{0}}\ln\left( \frac{N_{*}}{N_{0}}-1 \right)$
	- $\left( \frac{dN}{dt} \right)_{p}=\frac{a_{0}N_{*}}{4}$
- Klodoida
## In onesnazenje
$$a(N)=a_{0}-bN-c\int^t_0{Ndt}$$
- $c$ -> koeficient onesnazenja
- $P=\int^{t}_{0}N dt$ -> Onesnazenje se ne zmanjsuje, $\frac{dP}{dt}=N$
- Predpostavimo $b=0$, torej ni ucinka goscenja oz. upocasnevanja rasti zaradi omejitve virov
- $\frac{1}{N} \frac{dN}{dt}=a_{0}-cP$ -> $N=N_{0}+a_{0}P- \frac{cP^{2}}{2}$
- V odvisnosti od časa: ($a_{*}=\sqrt{a^{2}_{0}+2cN_{0}}$; $\phi=\tanh^{-1} \frac{a_{0}}{a_{*}}$)
	- $P=\frac{a_{0}}{c}\left(1+ \frac{a_{*}}{a_{0}}\tanh(\frac{a_{*}t}{2}-\phi)\right)$
	- $N=\frac{a_{*}^{2}}{2c}\left(\cosh(\frac{a_{*}t}{2}-\phi)\right)^{-2}$
- Ker ima $cosh^{-2}(x)$ maxsimum pri $x=0$, ima populacija maximum $N_{maks}=\frac{a_{*}^{2}}{2c}$ pri času $t_{maks}=\frac{2\phi}{a_{*}}$
---
