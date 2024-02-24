# Datamodellering med ER-modeller

## Fra "Miniverden" til Realisert Database
- **Databasen som Modell** av en del av virkeligheten: Databaser er ikke bare lagringsenheter; de representerer en modell av virkelige prosesser og objekter.
- **Miniverden** refererer til den spesifikke delen av virkeligheten vi ønsker å modellere. Denne tilnærmingen hjelper oss med å identifisere:
  - **Relevante (data-)Objekter**: De grunnleggende elementene vi vil representere i databasen.
  - **Relevante Sammenhenger** mellom objekter: Hvordan disse objektene er relatert eller forbundet.
  - **Relevante Regler** som gjelder: Restriksjoner og forretningslogikk som styrer objektene og deres interaksjoner.

 Prosessen går fra **Miniverden** til **Konseptuell Modell**, deretter til **Logisk Modell** og til slutt til **Fysisk Modell (Database)**.
<p align="center">
  <img src="../Pictures/Datamodellering/Modeller.png" alt="Modeller" width="500"/>
</p>


## Entity-Relationship-Modeller
- **Mange Dialekter**: Det finnes forskjellige måter å representere ER-modeller på.
- **Konseptuell Datamodell**: Denne modellen fokuserer på høynivå, begrepsorientert design som er lett forståelig.
  - **Datastruktur**:
    - **Entiteter (Objekter)** og **Relasjoner** mellom disse.
    - **Entitetsklasser** og **Relasjonsklasser**.
    - **Attributter**: Egenskaper eller beskrivende detaljer av entiteter og relasjoner.
  - **Restriksjoner (Constraints)**:
    - Nøkkelsrestriksjoner og datatyper for attributter.
    - Strukturelle restriksjoner som påvirker hvordan dataene er organisert.
- Dataoperasjoner som innsetting, endring, sletting og spørring er mindre relevant i denne fasen.
<p align="center">
  <img src="../Pictures/Datamodellering/Tankekart.png" alt="Tankekart" width="500"/>
</p>


## Entiteter og Entitetsklasser
- **Entitet**: Et objekt eller element som har en eksistens i miniverdenen, med spesifikke egenskaper representert av **attributter**.
  - Attributter henter verdier fra et **domene** (datatype).
  - Typer av attributter inkluderer enkle, sammensatte, avledede og nøkkelattributter (unike identifikatorer).
<p align="center">
  <img src="../Pictures/Datamodellering/Entitet%20eks.png" alt="Entitet" width="500"/>
</p>


- **Entitetsklasse/-type**: En gruppe av likeartede entiteter som deler felles egenskaper. Alle entitetsklasser krever en unik identifikator (nøkkel).
<p align="center">
  <img src="../Pictures/Datamodellering/Entitetsklasse.png" alt="Entitetsklasse" width="500"/>
</p>


## Relasjoner og Relasjonsklasser
- **Relasjon**: En forbindelse eller et forhold mellom to eller flere entiteter. For eksempel, "en student har tatt eksamen i et emne".
  - Kan ha egenskaper, lik entiteter, representert ved attributter.
  - Relasjonen eksisterer kun når de relevante entitetene er til stede.
<p align="center">
  <img src="../Pictures/Datamodellering/Relasjoner.png" alt="Relasjoner" width="500"/>
</p>


- **Relasjonsklasser/-typer**: En samling av likeartede relasjoner mellom de samme entitetsklassene.
<p align="center">
  <img src="../Pictures/Datamodellering/Relasjonsklasser.png" alt="Relasjonsklasser" width="500"/>
</p>


- **Restriksjoner**:
  - **Kardinalitetsforhold**: Begrenser antall entiteter en entitet kan ha relasjon til.
    <p align="center">
      <img src="../Pictures/Datamodellering/Restriksjoner1.png" alt="Restriksjoner" width="500"/>
    </p>
  - **Deltakelseskrav**: Angir om en entitet må ha en relasjon til minst en annen entitet.
    <p align="center">
      <img src="../Pictures/Datamodellering/Restriksjoner2.png" alt="Restriksjoner" width="500"/>
    </p>
  - **Strukturelle Restriksjoner**: Kombinerer kardinalitets- og eksistensrestriksjoner.
    <p align="center">
      <img src="../Pictures/Datamodellering/Restriksjoner3.png" alt="Restriksjoner" width="500"/>
    </p>
  - **Sammenligning**:
    - Alternative måter å spesifisere det samme.
    - Legg merke til at "maks" bytter side.
    - Husk forskjellen mellom delvis og total deltakelse.
    <p align="center">
      <img src="../Pictures/Datamodellering/Restriksjoner4.png" alt="Restriksjoner" width="500"/>
    </p>


## Forekomst-nivå
<p align="center">
  <img src="../Pictures/Datamodellering/Forekomstniv%C3%A5.png" alt="Forekomstnivå" width="500"/>
</p>


## Om relasjoner
- Relasjoner kan ha __egenskaper__ som modelleres som attributter
<p align="center">
  <img src="../Pictures/Datamodellering/OmRelasjoner1.png" alt="Om relasjoner" width="500"/>
</p>


- Relasjonens __grad__ (degree) er antall entiteter som inngår
<p align="center">
  <img src="../Pictures/Datamodellering/OmRelasjoner2.png" alt="Om relasjoner" width="500"/>
</p>


- Relasjoner eksisterer _ikke_ uten de entitetene som inngår

## Utvikling av Datamodell
- Følg disse trinnene for å utvikle en robust datamodell:
  1. Identifiser nødvendige **entitetsklasser**.
  2. Definer **attributter** for hver entitetsklasse.
  3. Identifiser nødvendige **relasjonsklasser**.
  4. Definer **attributter** for hver relasjonsklasse.
  5. Bestem **nøkler** for hver entitetsklasse.
  6. Definer **restriksjoner** for relasjonsklassene.
  7. Vurder og juster modellen etter behov.


# ER-modellering: Rekursive relasjonsklasser

## Enkelt Eksempel på en ER-modell: Emne-Student_Vurdering
Denne modellen illustrerer en grunnleggende ER-struktur hvor studenter evalueres i forskjellige emner.
<p align="center">
  <img src="../Pictures/Datamodellering/Eks1.png" alt="Eksempel" width="500"/>
</p>


## Rekursive Relasjonsklasser
En interessant aspekt ved ER-modellering er rekursive relasjonsklasser, hvor samme entitetsklasse deltar flere ganger, men i ulike roller.
<p align="center">
  <img src="../Pictures/Datamodellering/RekRelkl.png" alt="Rekursive relasjonsklasser" width="500"/>
</p>

## Eksempel: Ledelseshierarki
Dette eksempelet viser et ledelseshierarki. For eksempel, Kong Harald (leder) for Statsminister Erna, som igjen er leder for ministerne Guri og Iselin. Iselin leder så statssekretærene Lucie og Lars.
<div style="display: flex; justify-content: center; align-items: center;">
  <img src="../Pictures/Datamodellering/Hierarki1.png" alt="Hierarki" style="height: 250px; margin-right: 10px;"/>
  <img src="../Pictures/Datamodellering/Hierarki2.png" alt="Hierarki" style="height: 250px;"/>
</div>

# ER-modellering: Svake entitetsklasser

## Svake Entitetsklasser
I en entitetsklasse, som er en samling unike entiteter, er det avgjørende at hver entitet kan identifiseres unikt. Et eksempel er kommuner og gater, hvor hver kommune har et unikt nummer og navn, og hver gate er unik innenfor sin kommune.
<p align="center">
  <img src="../Pictures/Datamodellering/SvakeEnt1.png" alt="Svake entitetsklasser1" width="500"/>
</p>
En utfordring oppstår når en entitetsklasse, som Gate, mangler en naturlig nøkkel.

En løsning kan være å introdusere et ekstra nøkkelattributt, som GateNr, som gjør Gate til en regulær entitetsklasse. Dette krever ekstra administrasjon for å sikre unikhet på tvers av kommuner.
<p align="center">
  <img src="../Pictures/Datamodellering/SvakeEnt2.png" alt="Svake entitetsklasser2" width="500"/>
</p>
En alternativ løsning er å bruke en identifiserende relasjonsklasse for å definere svake entitetsklasser, som ikke har en egen nøkkel. Dette eliminerer behovet for et ekstra nøkkelattributt. For eksempel, i kombinasjon, blir KommuneNr og Gatenavn en unik identifikator.
<p align="center">
  <img src="../Pictures/Datamodellering/SvakeEnt3.png" alt="Svake entitetsklasser3" width="500"/>
</p>

## Enhanced ER (EER)
Enhanced Entity-Relationship (EER)-modellering er en utvidelse av den standard Entity-Relationship (ER) modelleringen. EER inkluderer avanserte konsepter som spesialisering/generalisering, kategorier (union-typer), og arving av relasjonsklasser og attributter. La oss utdype disse konseptene:
- **Standard ER Pluss:**
  - **Støtte for Spesialisering/Generalisering:** Dette omfatter subklasser og superklasser.
  - **Entitetsklasser med Entiteter fra Ulike Entitetsklasser**: Dette refererer til kategorier eller union-typer.
  - **Arving**: Inkluderer arving av relasjonsklasser og attributter.

## Spesialisering/Generalisering
- **Spesialisering**: Prosessen med å definere underklasser for en gitt superklasse. Dette involverer å identifisere unike egenskaper som er spesifikke for subklassene.
- **Generalisering**: Å samle lignende entitetsklasser som subklasser under en felles superklasse. Felles egenskaper er modellert på superklassenivå.
- **Unike Egenskaper for Subklasser**: De egenskapene som er spesifikke for en subklasse, modelleres på subklassen.
<p align="center">
  <img src="../Pictures/Datamodellering/Spesialisering.png" alt="Spesialisering" width="500"/>
</p>

## Notasjon og Egenskaper
- **Rolle i Subklasse**: En entitet i en subklasse har alltid en rolle som en del av superklassen, men med spesielle egenskaper.
- **Arv av Attributter og Relasjoner**: Entiteter i subklasser arver alle attributter og relasjoner fra superklassen og kan ha sine egne unike attributter og relasjonsklasser.
- **Deltakelse i Subklasser**: Ikke alle entiteter må være med i en subklasse, men det kan være et krav. En entitet kan tilhøre bare én eller flere subklasser.
<p align="center">
  <img src="../Pictures/Datamodellering/Notasjon.png" alt="Notasjon" width="500"/>
</p>

## Eksempel: Sykehus
- Dette er et konkret eksempel som illustrerer bruken av EER-modellering i en praktisk sammenheng, som et sykehusdatabase-system.
<p align="center">
  <img src="../Pictures/Datamodellering/Sykehus.png" alt="Sykehus" width="500"/>
</p>

#### Forekomstdiagram
<p align="center">
  <img src="../Pictures/Datamodellering/ShusForekomst.png" alt="Forekomstdiagram" width="500"/>
</p>

## Restriksjoner i EER-modeller

- **Deltakelse i Subklasse**: Kan være regelbasert eller brukerstyrt.
<p align="center">
  <img src="../Pictures/Datamodellering/Restriksjoner4-1.png" alt="Restriksjoner" width="500"/>
</p>

- **Subklassetyper**: Disjunkte (ikke-overlappende) eller overlappende.
<p align="center">
  <img src="../Pictures/Datamodellering/Restriksjoner4-2.1.png" alt="Restriksjoner" width="500"/>
</p>

- **Spesialiseringstype**: Delvis eller total (frivillig eller tvungen).
<p align="center">
  <img src="../Pictures/Datamodellering/Restriksjoner4-2.2.png" alt="Restriksjoner" width="500"/>
</p>

- **Kombinasjoner av Restriksjoner**: Det er fire hovedmuligheter for hvordan disse restriksjonene kan kombineres.
<p align="center">
  <img src="../Pictures/Datamodellering/Restriksjoner4-4.png" alt="Restriksjoner" width="500"/>
</p>

## Eksempel: Kameradatabase
- Dette eksempelet viser hvordan en ER-modell kan konverteres til en EER-modell for å gi en mer detaljert og nøyaktig representasjon av virkeligheten.
<p align="center">
  <img src="../Pictures/Datamodellering/Kameradatabase-ER.png" alt="Kameradatabase" width="500"/>
</p>
<p align="center">
  <img src="../Pictures/Datamodellering/Kameradatabase-EER.png" alt="Kameradatabase" width="500"/>
</p>

## Kategorier: Subklasser med flere superklasser
- Mengden entiteter i en kategori er en delmengde av entitetene i superklassene
- Kategorier kalles også union-klasse, derfor U i sirkelen
- JuridiskPerson er enten Selskap eller Person
- Selektiv aving
<p align="center">
  <img src="../Pictures/Datamodellering/Kategorier1.png" alt="Kategori" width="500"/>
</p>

## Kategorier: Restriksjoner: Delvis/Totalt
<p align="center">
  <img src="../Pictures/Datamodellering/Kategorier2.png" alt="Kategori" width="500"/>
</p>

## Total kategori eller Superklasse 
<p align="center">
  <img src="../Pictures/Datamodellering/Kategorier3.png" alt="Kategori" width="500"/>
</p>
Når alle entiteter i superklasene for en kategori må delta i kategorien bør vi vurdere om en løsning med spesialisering/generalisering blir bedre
