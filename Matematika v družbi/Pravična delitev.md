```table-of-contents
title: # Kazalo
style: nestedOrderedList
```
---
# Definicija
- **Stvari ki delimo**:
	- *Zvezno deljive* -> Stvar lahko razdelimo na dele (torta, denar, ...)
	- *Nedeljive* -> En igralec prevzame celotno stvar (umetnine, premičnine, ...)
- **Igralci** -> osebe, države, stranke, ...
- **Vrednotenje stvari** -> vsak igralec ima <u>svoj sistem vrednotenja</u>
- **Proporcionalna delitev** -> vsak izmed $n$ igralcev meni da je dobil vsaj $n$-ti del torte
- **Delitev brez zavisti** -> vsak igralec meni da nihče ni dobil več od njega
- **Predpostavimo**:
	- *Racionalnost igralcev*
	- *Sodelovanje* -> vsi igralci brezpogojno sprejmejo pravila
	- *Tajnost* -> vrednotenje drugih igralcev ni znano, razen če igralec sam pove
	- *Enakost* -> vsi imajo pravice dobiti enak delež
---
# Zvezna delitev
- Predmet delitve je zvezno in neskončno deljiv
## 2 igralca
### Reži in izberi
- En igralec je **delilec**, drugi pa **izbiralec**

1. **Delilec** razdeli stvar na <u>sebi</u> dva enaka dela
2. **Izbiralec** izbere enega izmed dveh delov
3. Drugi del obdrži **delilec**

## 3 ali več igralcev
### En delilec za 3 igralce
- 1943, Steinhaus
- 1 **delilec ($D$)**, 2 **izbiralca ($C_{1},\ C_{2}$)**
- Vedno proporcionalno, ni vedno brez zavisti

1. $D$ deli torto na tri <u>zanj</u> enake dele
2. **Izbiralca** zapišeta svoj preferenčni del:
	1. Če izbereta <u>dva različna dela</u>, dobita vsak svojega preferenčnega, **delilec** dobi preostali del
	2. Če izbereta <u>dva enaka dela</u>, lahko **delilec** izbere enega izmed preostalih delov, **izbiralca** pa uporabita [[#Reži in izberi|metodo reži in izberi]] da razdelita seštevek preferenčnega dela in ostanka

### En izbiralec za $N$ igralcev
- 1964, Fink
- $N$ **igralcev**, 1 **izbiralec**, ostali **delitelji**
- Vedno proporcionalno, ni vedno brez zavisti

1. **Delilci** razdelijo torto na $N-1$ delov
2. Vsak **delilec** razdeli svoj del na $N$ delov
3. **Izbiralec** pri vsakemu vzame en kos

### Banach - Knaster
- cca. 1940, za 3 ali več igralcev

1. Izžreba se vrstni red igralcev
2. Prvi določi svoj proporcionalni del ($\frac{1}{n}$)
3. Vsak naslednji igralec ima pravico prvemu zmanjšati del, a z tem postane lastnik dela
4. Del ostane tistemu igralci, ki ga je zadnji manjšal. Ta izstopi iz igre
5. Ponovi postopek od 2. točke ($n=n-1$), dokler ne ostaneta dva igrala. Ta delita z reži in izberi
---
# Nedeljiva delitev
- **Vsak nedeljiv predmet v celoti prejme en igralec**
- Delitev je proporiconalna, v osnovni izvedbi pa ni vedno brez zavisti
## Zapečatene ponudbe
- 1948: Steinhaus - Knasterjev postopek
- Primerno za delitev <u>manjšega števila predmetov</u>, ki so lahko zelo različni po vrednosti
- Poštena delitev je možna samo z uporabo dodatnih menjalnih sredstev **zvezne narave** (npr. <u>denar</u>)

1. Vsak igralec *tajno* poda svoje vrednotenje za vsak predmet
2. Po vseh ponudbah dobijo posamezne predmete ponudniki, ki so za predmet <u>ponudili največ</u>
3. Vsak igralec primerja svoj del (koliko je ponudil skupaj za vse predmete $/$ št. igralcev) z vrednostmi pridobljenih predmetov in:
	1. Če je del **manjši** kot skupna vrednost, mora povrniti razliko z menjalnim sredstvom (*denar*) v **skupno blagajno**
	2. Če je del **večji**, prejme igralec nadomestilo z menjalnim sredstvom iz **skupne blagajne**
4. Ostanek menjalnega sredstva se razdeli proporcionalno med igralci

## Metoda zaznamkov
- 1975: Lucas
- Primerna za delitev <u>večjega števila predmetov</u>, ki naj bodo približno enakih vrednosti. Predmetov naj bo znatno več, kot igralcev
- Ni potrebe za dodatno menjalno sredstvo

1. Predmete <u>naključno</u> postavimo v zaporedje. Zaporedje se ne spreminja
2. $N$ igralcev <u>tajno</u> razdeli zaporedje v $N$ *vrednostno enakih* segmentov
3. Zaznamki vseh igralcev se prenesejo na zaporedje
4. Segmenti se glede na razporeditev zaznamkov dodelijo igralcem:
	- Prvi segment dobi igralec ki je dal <u>svoj prvi zaznamek</u> najbolj **levo**, ostali zaznamki igralca se zbrišejo
	- Prejšnji korak se ponovi za **vsak segment** (če imata dva igralca zaznamek na istemu mestu, prejemnika določi žreb)
	- Zadnjemu igralcu pripada njegov <u>zadnji</u> segment
	- Delitev preostalih predmetov je zanemarljiva (dogovor, žreb, ...)