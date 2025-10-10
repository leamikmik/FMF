```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Definicija
- vpelje strog mat. jezik (sintaksa)
- postavi pravila sklepanja
---
# Izjavni račun
- Izjava -> Stavek ki je resnicen ali neresnicen
- Log. operacije:
	- Zdruzijo dve izjavi v novo
- Operacije:
	- Konjukcija (and) -> $\wedge$ (samo res ko obadva res)
	- disjunkcija (or) -> $\vee$ (res ko en res)
	- eksluzivna disjunkcija (xor) -> $\veebar$
	- negacija -> $\neg$
	- Max 16 operacij z dvema clenoma
		- NOR -> $\downarrow$ al pa $\neg(A\vee B)$
		- XNOR -> $A\iff B$
		- implikacija -> $A\Rightarrow B$ (1101)
			- ce vrednost enaka ali gre gor, potem 1
			- Semanticna -> $\vDash$
		- NAND -> $\uparrow$ 
---
# Predikatni racun
- $A=$ "Vsi ljudje so smrtni"
- $B=$ "Sokrat je clovke"
- $C =$ "Sokrat je smrten"
- Zdi se da iz $A$ in $B$ sledi $C$
	- Vendar veljavnost tega sklepa ne moremo dokazati z metodami izjavnega racuna.
- **Predikati** -> nekaksne funckije, ki slikajo iz prostora objektov v prostor izjav
	- $P(x):=$ "x je smrten"
	- $Q(x):=$ "x je clovek"
	- Ce je mnozica objektov (npr. zivih bitji) koncna, $U:=\{\text{clovek},\text{psi},\dots\}$
	- Predikat ima lahko vec spremenljivk: $R(x,y), T(x,y,z),\dots$
- $B=Q(\text{Sokrat})$
- $C=P(\text{Sokrat})$
- $A=\forall x.(Q(x)\Rightarrow P(x))$
- Torej: $\forall x.(Q(x)\Rightarrow P(x)),Q(\text{Sokrat})\vDash P(\text{Sokrat})$
- Pojem izjavnega izraza iz izjavnega racuna lahko posplosimo s predikati. Poleg simbolov, ki nastopajo v izjavnem racunu, dodamo se:
	- Simbole za predikate
	- Spremenljivke
	- Oznake za konstante
	- Znaka za kvantifikatorja: $\forall,\exists$
- 