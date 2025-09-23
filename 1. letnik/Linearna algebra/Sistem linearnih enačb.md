```table-of-contents
title: # Kazalo
style: nestedOrderedList
```

---
# Sistem enačb 
$$\alpha_{m1}x_{1}+\dots+\alpha_{mn}x_{n}=\beta_{m}$$
- Imamo $m$ enačb za $n$ spremenljivk
- **Matrika koeficientov** -> $A=\left[\begin{matrix}\alpha_{11} & \dots & \alpha_{1n} \\ \vdots && \vdots \\ \alpha_{m1} & \dots & \alpha_{mn}\end{matrix}\right]$
- **Vektor desnih strani** -> $b=\left[\begin{matrix}\beta_{1} \\ \vdots \\ \beta_{m}\end{matrix}\right]$
- **Vektor neznank** -> $x=\left[\begin{matrix}x_{1} \\ \vdots \\ x_{n}\end{matrix}\right]$

- Sistem lahko zapišemo potem kot $Q*Ax=Q*b$
	- Za vsako **obrljivo** matriko $Q$
- Če ima $\tilde A$ v zadnjem stolpcu pivot, sistem ni rešljiv.
- Če v kakem stoplcu $VKF(A)$ **ni** pivota ima ustrezna spremenljivka poljubno vrednost -> *neskončno rešitev*
- Sistem ima eno rešitev ko [[Determinante|determinanta]] $\det(A)\ne0$
	- Če $\det(A)=0$ sistem ni rešljiv, oz ima <u>neskončno rešitev</u>
- **Homogen sistem**:
	- Kadar so na desni same $0$ -> $Ax=0$
	- Rešujemo enako, le da običajno ne pišemo desne strani
	- Zmeraj vsaj ena trivialna rešitev (vse spremenljivke so $0$)
	- $\tilde A=A$
	- Če $A\in\Bbb R^{m\times n}$ in $m<n$ ima sistem vedno neskončno rešitev
- Če je $A$ kvadratna matrika je $x=b*A^{-1}$
- $rang(A)$ določi največjo neničelno determinanto matrike
## Gaussova eliminacija
1. Zapišemo *razširjeno matriko sistema* -> $\tilde A=[A\vdots B]$
2. Izračunamo $VKF(\tilde A)$ ([[Matrike#Vrstična kanonična forma]])
3. Preberemo rešitve (zadnji stolpec $VKF(\tilde A)$)
## Matrične enačbe
$$A*X=B$$
- $A\in\Bbb R^{m\times n};\ X\in\Bbb R^{n\times r};\ B\in\Bbb R^{m\times r}$
- Rešuje enako z *Gaussovo eliminacijo*
- Če na $B$ strani ni pivotov je sistem rešljiv.
- **Poseben primer** $B=I=\left[\begin{matrix}1&&\huge 0 \\ &\ddots& \\ \huge 0&&1\end{matrix}\right]$
	- Mi bomo reševali samo take primere
	- $X$ je inverz $A$
	- $VKF(\ [A\vdots I]\ )\Rightarrow[I\vdots X]$
	- $A*X=X*A$
---