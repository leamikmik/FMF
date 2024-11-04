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
## In onesnazenje
$$a(N)=a_{0}-bN-c\int^t_0{Ndt}$$
- $c$ -> koeficient onesnazenja
- $P=\int^{t}_{0}N dt$ -> Onesnazenje se ne zmanjsuje, $\frac{dP}{dt}=N$
- Predpostavimo $b=0$, torej ni ucinka goscenja oz. upocasnevanja rasti zaradi omejitve virov
- $\frac{1}{N} \frac{dN}{dt}=a_{0}-cP$ -> $N=N_{0}+a_{0}P- \frac{cP^{2}}{2}$
 %%ToDo
![[Pasted image 20241104111948.png]]
 %%

---
