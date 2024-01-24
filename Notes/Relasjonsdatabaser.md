# Relasjonsdatabaser
## Intro
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/Relasjonsdatabaser.png" alt="Modeller" width="500"/>
</p>

### Tabeller/Relasjoner
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/Tabeller.png" alt="Modeller" width="500"/>
</p>

- Skjema ("intention") beskriver tabellen
    - Tabellnavn
    - Kolonner (attributter)
    - Kolonnenes datatyper
    - Restriksjoner
        - Primærnøkkel (entydig identifikator) og andre restriksjoner
- Forekomst av data ("extention")
    - Rader/tuppler med lovlige verdier
- Spesiell NULL-verdi
    - Der vi ikke har noen verdi ("ukjent eller mangler")
- Fremmednøkkel
    - Verdi som viser til en rad (tuppel) i en annen tabell (ev.samme tabell)
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/Skjema.png" alt="Modeller" width="500"/>
</p>
- EierPnr er en fremmednøkkel mot Person(Pnr)
- OfferPnr er en fremmednøkkel mot Person(Pnr)
- GjerningshundRegNr er en fremmednøkkel mot Hund(RegNr)

### Innhold
<div style="display: flex; justify-content: center; align-items: center;">
  <img src="../Pictures/Relasjonsdatabaser/Innhold1.png" alt="Innhold1" style="height: 250px; margin-right: 10px;"/>
  <img src="../Pictures/Relasjonsdatabaser/Innhold2.png" alt="Innhold2" style="height: 250px;"/>
</div>

- Standard relasjonsdatabaser har
    - Atomiske verdier i domenene (datatypene)
    - En verdi for hvert attributt (i en rad)
    - Dette gir oss "flate, 2-dimensjonale tabeller"
- Ikke-standard relasjonsdatabaser kan ha
    - Sammensatte attributter (poster, tabeller), repeterende grupper (fler-verdi-attributter)
- **Entitetsintegritet**
    - En relasjon (tabell) er en _mengde_ tuppler (rader)
        - Kan ikke ha to like tuppler
    - Alle tabeller må ha en **primærnøkkel** (unik identifikator)
        - For å sikre at primærnøkkelen har unike verdier tillates ikke NULL-verdier i primærnøkkel (som kan bestå av flere attributter)
- **Referanseintegritet**
    - Fremmednøkler må referere til et tuppel (rad) som finnes i den tabellen det refereres til eller bare bestå av NULL-verdi(er)

## Mapping fra ER-modeller

### Regulære entitetsklasser
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/RegEntitetstyper.png" alt="Modeller" width="500"/>
</p>

En tabell for entitetsklassen med entitetsklassen nøkkelattributt og en-verdi-attributter. For samensatte attributter beholdes "løv-attributtene".

### Svake entitetsklasser
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/SvakeEntitetsklasser.png" alt="Modeller" width="500"/>
</p>
En tabell for entitetsklassens delvise nøkkelattributt og en-verdi-attributter. I tillegg må nøkkelattributten(e) til den identifisernde entitetsklassen tas med som nøkkelattributter. Dette vil være en fremmednøkkel mot den aktuelletabellen som ikke kan ha NULL-verdier.

### Binære 1:1 relasjonsklasser
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/BinæreRelasjonskl1-1.png" alt="Modeller" width="500"/>
</p>

- Legger til en fremmed nøkkel i en av tabellene eller lager en egen koblingstabell. 
- Velger ofte den løsningen som gir minst NULL-verdier.

### Binære 1:n relasjonsklasser
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/BinæreRelasjonskl1-n.png" alt="Modeller" width="500"/>
</p>
Kan legge til fremmednøkkel og evt. attributter som hører til relasjonsklassen, i tabellen som representerer mange-siden i relasjonsklassen. Alternativt kan det legges til en koblingstabell.

### Binære n:m relasjonsklasser
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/BinæreRelasjonskln-m.png" alt="Modeller" width="500"/>
</p>

Må ha egen koblingstabell med fremmednøkler til begge entitetsklasse-tabellene. Fremmednøklene utgjør sammen primærnøkkelen. Evt. attributter i relasjonsklassen tas med i koblingstabellen.

### Fler-verdiattributter
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/FlerVerdiAtt.png" alt="Modeller" width="500"/>
</p>

Fler-verdiattributt må (vanligvis) håndteres i en egen tabell, med en fremmed-nøkkel til entitetstabellen. Det kan være flere muligheter når det gjelder nøkkel i denne fler-verdi-attributt-tabellen. Hvis flere personer kan dele tlfNr blir det som illustrert over. Hvis det er maks en pers pr tlfNr, vil ikke Pnr være med i nøkkelen.

### N-ære relasjonsklasser
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/N-æreRelasjonskl.png" alt="Modeller" width="500"/>
</p>

### Spesialisering/Generalisering
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/Generalisering.png" alt="Modeller" width="500"/>
</p>
- Ingen egentlig støtte for dette
- A: Både superklasser-tabell og subklasse-tabell
- B: Bare subklasse-tabeller 
- C/D: Bare superklasse-tabell
- Kan velge ulike alternativer ulike steder i EER-modell

### Kategorier
<p align="center">
  <img src="../Pictures/Relasjonsdatabaser/Kategorier.png" alt="Modeller" width="500"/>
</p>

- Lager egen tabell for kategori-entitetsklassen (vanlige regler, unntatt primærnøkkel)
- Superklassene har som regel ulike nøkler, lager i disse tilfellene en **spesiell primærnøkkel** for kategori-tabellen ("surrogatnøkkel")
- Legger _surrogatnøkkelen_ inn som _fremmednøkkel_ i alle superklasse-tabeller
- Legger inn et **type-attributt** i kategori-tabellen som viser hvilken super klasse hver kategori-entitet er.

## Relasjonsalgebra
- Operasjon for _manipulere_ tabeller
  - Vi ser kun på spørrefunksjonalitet, ikke innsetting, endring eller sletting
  - Viktig grunnlag for å forstå hva man kan gjøre med tabeller, for normaliseringsteorien og for spørreoptimalisering og spørreutføring
- Husk: Tabellforekomster er mengder av tuppler
- Operatorene er _lukket_  over tabeller 