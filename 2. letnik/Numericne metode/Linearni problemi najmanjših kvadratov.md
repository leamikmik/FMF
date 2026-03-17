

23.2.
Algoritem (gran-schmidtov postpek)
```
for i=1:n
	q^(0)_i = a_i
end
for i=1:n
	r_ii = ||q^(i-1)_i||_2
	q_i = 1/r_ii q^(i-1)_i
	for j=i+1:n
		r_ij = q^T_i * a_j
		q^(i)_j = q^(i-1)_j - r_ij * q_i
	end
end
```
Vrstica 8. taka kot je, recemo Klasicni GSP (CGS)
Al pa (`r_ij = q^T_i * q^(i-1)_j`) Modificiran GSP (MGS)
CGS in MGS nam data enak eksakten rezultat, pri numericnem je pa MGS bolj stabilen.

Kako z pomocjo $QR$ razcepa do resitve $Ax=b$ po MNK?
- $A=QR$
- $A^{T}Ax=A^{T}b$
- $(QR)^{T}QRx=(QR)^{T}b$
- $R^{T}Q^{T}QRx=R^{T}Q^{T}b$
- $Rx=Q^{T}b$
