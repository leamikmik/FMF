# Kriterij
1. **Večinskost** => kandidat dobi *absolutno večino* glasov oz. preferenc bi moral <u>zmagati</u>
2. **Condorcetov kriterij** => kandidat v primerjavi 1:1 boljši od drugih bi moral <u>zmagati</u>
3. **Nesposobnost** => je kandidat zadnji na preferenčnih listih večine volilcev bi moral <u>zgubiti</u>
4. **Monotonost** => bi kandidat zmagal na volitval, a se nato glasovnice spremenijo njemu v prid, bi moral še vedno <u>zmagati</u>
5. **IIA** (*Independance of Irrelevan Alternatives*) => bi kandidat A zmagal, a je nato kandidat B diskvalificiran, bi moral A še vedno <u>zmagati</u>
# Večinski
![[Pasted image 20250111181804.png]]
## Relativni
- **Enokrožni večinski sistem** oz. *winner takes all*
- Najpogosteje uporabljen
- Izvoljen je kandidat z **največjim številom glasov**
## Absolutni
- **Dvokrožni večinski sistem** oz. *double ballot*
- Uporabljen v Slo za volitve predsednika republike
- Če v **prvem krogu** noben kandidat nima <u>50% ali več glasov</u>, se prvo in drugo-uvrščeni pomerita v **drugem krogu**
- Drugi krog ne potrebuje **absolutne večine** (*neveljavni glasovi*)
## Alternativni glas
- Enokrožni večinski sistem s **prerazporejanjem preferenčnih glasov** oz. *plurality with elimination*
- Na glasovnici volilec označi **kandidate po vrsti** (določi preference). Prešteti so glasovi po številu prvih (*najbolj zaželen*) preferenc. Kandidat z **najmanjšim št. prvih preferenc** odpade. Preostale kandidate se presortira in postopek ponovi, dokler ne ostane 1 kandidat.
- Ordinalni (*vrstilni*) sistem
## Borda
- Enokrožni večinski sistem s **točkovanjem kandidatov**
- Kandidatom **pripišejo točke** glede na pozicijo na preferenčni listi (Prva pozicija - največ točk, ...)
- Ordinalni (*vrstilni*) sistem
- Sistem favorizira kandidate ki so "*kompromis*"
## Primerjava kandidatov
- Enokrožni večinski sistem s točkovanjem kandidatov, ki jih **paroma (1:1)** primerjamo med sabo
- Primerjava med dvema kandidatoma, boljši dobi točko. Če primerjava kandidatov 50/50 potem vsak dobi pol točke.

---
# Proporcionalni
- Sistem *predstavnikov*, kjer se glasovi ne izgubijo (vsak *predstavnik* ima **volilno moč**)
- Posebne **volilne moči**:
	- <u>diktatorska moč</u> => brez predstavnika *ni mogoče sprejeti nobene odločitve*
	- <u>moč veta</u> => predstavnik lahko *sam sprejme* odločitev ampak ni obvezen 
	- <u>nobena moč</u> => v primeru diktature, ...
- Zapis oblike $[\text{Prag};P_{1},P_{2},\dots,P_{n}]$
- **Prag** -> Potrebnih glasov za sprejem odločitve
- **Koalicija** -> *Zveza predstavnikov* z težo vsote števil glasov članic
	- <u>Zmagovalna</u> koalicija => teža vsaj enaka pragu
	- Število koalicij = $2^n$ 
	- Najlažji način preverjanja vseh zmagovalnih z <u>binarno metodo</u>
- **Kritičnost** -> Predstavnik čigar sodelovanje je <u>nujno</u>, da koalicija ostane zmagovalna  => $N_{k}(P_{n})$
- **Pivot**:
	- <u>Zaporedna koalicija</u> => Vrstni red je pomemben $\left< P_{1},\dots,P_{n} \right>$
	- Predstavnik, pri katerem teža zaporedne koalicije doseže prag odločanja
	- Število pivotov za danega predstavnika je $N_{p}(P_{i})$
# Banzhafov indeks
$$B_{r}(P_{i})=\frac{N_{k}(P_{i})}{\sum\limits^{n}_{j=1} N_{k}(P_{j})}$$
- **Relativni** => Seštevek vseh je $1$
# Shapley-Shubikov indeks
$$SS(P_{i})=\frac{N_{p}(P_{i})}{!n}$$
- **Relativni** => Seštevek vseh je $1$