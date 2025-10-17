- Objekti $a,b,c,...$(oz. najmanjsa neprazna mnozica)
- Mnozica $A,B,M,X,...$
- "relacija" pripadnosti:
	- $a\ ...$ objekt
	- $A\dots$ mnozica
	- $a$ lahko pripada $A$ ($a\in A$), ali pa ne pripada $(a\notin A)$
- Mn. je natanko dolocena, z podatkom, katere el. vsebuje
- $\forall A\forall B:A=B\iff\forall x:(x\in A\iff x\in B)$
- Objekta $a$ in $b$ sta enaka objekta, ce:
	- $\forall A:a\in A\iff b\in A$
- Def: Mnozica $A$ je podmnozice $B$ $(A\subseteq B)$, ce in samo ce:
	- $\forall x: x\in A\Rightarrow x\in B$
	- tj. $A=B\iff A\subseteq B\wedge B\subseteq A$
- Kako definiramo mnozico:
	1. Nastejemo el.
	2. Predikat -> $A=\{x|P(x)\}$
	3. S pomocnjo funkcije -> $A=\{2x|x\in\Bbb Z\}$
- $\emptyset=\{x;x\ne x\}$
- Operacije:
	- unija $\cup$ -> $A\cup B := \{x;x\in A \vee x\in B\}$
	- presek $\cap$ -> $A\cap B:=\{x;x\in A\wedge x\in B\}$
	- razlika $-$ -> $A-B:=\{x;x\in A\wedge x\notin B\}$
	- simetricna razlika $\oplus$ -> $A\oplus B:=\{x;(x\in A\wedge x\notin B)\vee (x\notin A\wedge x\in B\}=(A-B)\cup(B-A)$
	- komplement (ce imamo **univerzalno mnozico** $U$) -> $\bar A=U-A$
- 