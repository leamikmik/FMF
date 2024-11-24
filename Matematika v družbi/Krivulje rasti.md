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
# Logistična rast
$$N=\frac{N_*}{1+(N_{*}/N_{0}-1)e^{-a_{0}t}}$$
- **Verhultova enačba**
- $\frac{dN}{dt}=a_{0}N(1-\frac{N}{N_{*}})$
- Koeficient rasti -> $a(N)=a_{0}-bN=a_{0}(1-\frac{N}{N_*})$
- $a_{0}$ se lahko zračuna z [[#Eksponenta rast|enačbo eksponentne rasti]]
- $b$ -> Konstanta - koeficient goščenja $b=a_{0}/N_{*}$
- $N_{*}$ -> Konstanta - ravnotežna vrednost ob koncu rasti
- $tanh(x)$ podobno
- Prevojna točka (simetrično razpolovi):
	- $N_{p}=\frac{N_{*}}{2}$ 
	- $t_{p}=\frac{1}{a_{0}}\ln\left( \frac{N_{*}}{N_{0}}-1 \right)$
	- $\left( \frac{dN}{dt} \right)_{p}=\frac{a_{0}N_{*}}{4}$
- [Klodoida](https://external-content.duckduckgo.com/iu/?u=https%3A%2F%2Ftse4.mm.bing.net%2Fth%3Fid%3DOIP.tpLJiES_FR3LBliyqlL63AHaG9%26pid%3DApi&f=1&ipt=4a1b63fa7e8fa8f49cd767be9516d3481674b621c9193e15127657e76c858d2c&ipo=images)
## Onesnaženje
$$N=N_{0}+a_{0}P- \frac{cP^{2}}{2}$$
- $c$ -> koeficient onesnaženja
- $P=\int^{t}_{0}N dt$ -> Onesnaženje, se ne zmanjšuje, $\frac{dP}{dt}=N$
- Predpostavimo $b=0$, torej ni učinka goščenja oz. upočasnevanja rasti zaradi omejitve virov
- $\frac{1}{N} \frac{dN}{dt}=a_{0}-cP$ -> $a(N)=a_{0}-bN-c\int^t_0{Ndt}$
- **V odvisnosti od časa**: ($a_{*}=\sqrt{a^{2}_{0}+2cN_{0}}$; $\phi=\tanh^{-1} \frac{a_{0}}{a_{*}}$)
	- $P=\frac{a_{0}}{c}\left(1+ \frac{a_{*}}{a_{0}}\tanh(\frac{a_{*}t}{2}-\phi)\right)$
	- $N=\frac{a_{*}^{2}}{2c}\left(\cosh(\frac{a_{*}t}{2}-\phi)\right)^{-2}$
- Ker ima $cosh^{-2}(x)$ maxsimum pri $x=0$, ima populacija maximum $N_{maks}=\frac{a_{*}^{2}}{2c}$ pri času $t_{maks}=\frac{2\phi}{a_{*}}$

```functionplot
---
title: tanh, arctanh
xLabel: x
yLabel: y
bounds: [-10,10,-10,10]
disableZoom: true
grid: true
---
f(x)=tanh(x)
g(x)=atanh(x)
```
```functionplot
---
title: cosh, cosh^-2
xLabel: x
yLabel: y
bounds: [-5,5,-5,5]
disableZoom: true
grid: true
---
f(x)=cosh(x)
g(x)=cosh(x)^-2
```
---
