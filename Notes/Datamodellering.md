# Datamodellering med ER-modeller

## Fra "Miniverden" til Realisert Database
- **Databasen som Modell** av en del av virkeligheten: Databaser er ikke bare lagringsenheter; de representerer en modell av virkelige prosesser og objekter.
- **Miniverden** refererer til den spesifikke delen av virkeligheten vi ønsker å modellere. Denne tilnærmingen hjelper oss med å identifisere:
  - **Relevante (data-)Objekter**: De grunnleggende elementene vi vil representere i databasen.
  - **Relevante Sammenhenger** mellom objekter: Hvordan disse objektene er relatert eller forbundet.
  - **Relevante Regler** som gjelder: Restriksjoner og forretningslogikk som styrer objektene og deres interaksjoner.

 Prosessen går fra **Miniverden** til **Konseptuell Modell**, deretter til **Logisk Modell** og til slutt til **Fysisk Modell (Database)**.
<p align="center">
  <img src="../Pictures/Video%201/Modeller.png" alt="Modeller" width="500"/>
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
  <img src="../Pictures/Video%201/Tankekart.png" alt="Tankekart" width="500"/>
</p>


## Entiteter og Entitetsklasser
- **Entitet**: Et objekt eller element som har en eksistens i miniverdenen, med spesifikke egenskaper representert av **attributter**.
  - Attributter henter verdier fra et **domene** (datatype).
  - Typer av attributter inkluderer enkle, sammensatte, avledede og nøkkelattributter (unike identifikatorer).
<p align="center">
  <img src="../Pictures/Video%201/Entitet%20eks.png" alt="Entitet" width="500"/>
</p>


- **Entitetsklasse/-type**: En gruppe av likeartede entiteter som deler felles egenskaper. Alle entitetsklasser krever en unik identifikator (nøkkel).
<p align="center">
  <img src="../Pictures/Video%201/Entitetsklasse.png" alt="Entitetsklasse" width="500"/>
</p>


## Relasjoner og Relasjonsklasser
- **Relasjon**: En forbindelse eller et forhold mellom to eller flere entiteter. For eksempel, "en student har tatt eksamen i et emne".
  - Kan ha egenskaper, lik entiteter, representert ved attributter.
  - Relasjonen eksisterer kun når de relevante entitetene er til stede.
<p align="center">
  <img src="../Pictures/Video%201/Relasjoner.png" alt="Relasjoner" width="500"/>
</p>


- **Relasjonsklasser/-typer**: En samling av likeartede relasjoner mellom de samme entitetsklassene.
<p align="center">
  <img src="../Pictures/Video%201/Relasjonsklasser.png" alt="Relasjonsklasser" width="500"/>
</p>


- **Restriksjoner**:
  - **Kardinalitetsforhold**: Begrenser antall entiteter en entitet kan ha relasjon til.
    <p align="center">
      <img src="../Pictures/Video%201/Restriksjoner1.png" alt="Restriksjoner" width="500"/>
    </p>
  - **Deltakelseskrav**: Angir om en entitet må ha en relasjon til minst en annen entitet.
    <p align="center">
      <img src="../Pictures/Video%201/Restriksjoner2.png" alt="Restriksjoner" width="500"/>
    </p>
  - **Strukturelle Restriksjoner**: Kombinerer kardinalitets- og eksistensrestriksjoner.
    <p align="center">
      <img src="../Pictures/Video%201/Restriksjoner3.png" alt="Restriksjoner" width="500"/>
    </p>
  - **Sammenligning**:
    - Alternative måter å spesifisere det samme.
    - Legg merke til at "maks" bytter side.
    - Husk forskjellen mellom delvis og total deltakelse.
    <p align="center">
      <img src="../Pictures/Video%201/Restriksjoner4.png" alt="Restriksjoner" width="500"/>
    </p>


## Forekomst-nivå
<p align="center">
  <img src="../Pictures/Video%201/Forekomstniv%C3%A5.png" alt="Forekomstnivå" width="500"/>
</p>


## Om relasjoner
- Relasjoner kan ha __egenskaper__ som modelleres som attributter
<p align="center">
  <img src="../Pictures/Video%201/OmRelasjoner1.png" alt="Om relasjoner" width="500"/>
</p>


- Relasjonens __grad__ (degree) er antall entiteter som inngår
<p align="center">
  <img src="../Pictures/Video%201/OmRelasjoner2.png" alt="Om relasjoner" width="500"/>
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
  <img src="../Pictures/Video%201/Eks1.png" alt="Eksempel" width="500"/>
</p>


## Rekursive Relasjonsklasser
En interessant aspekt ved ER-modellering er rekursive relasjonsklasser, hvor samme entitetsklasse deltar flere ganger, men i ulike roller.
<p align="center">
  <img src="../Pictures/Video%201/RekRelkl.png" alt="Rekursive relasjonsklasser" width="500"/>
</p>

## Eksempel: Ledelseshierarki
Dette eksempelet viser et ledelseshierarki. For eksempel, Kong Harald (leder) for Statsminister Erna, som igjen er leder for ministerne Guri og Iselin. Iselin leder så statssekretærene Lucie og Lars.
<div style="display: flex; justify-content: center;">
  <img src="../Pictures/Video%201/Hierarki1.png" alt="Hierarki" style="height: 300px;"/>
  <img src="../Pictures/Video%201/Hierarki2.png" alt="Hierarki" style="height: 300px;"/>
</div>


# ER-modellering: Svake entitetsklasser

## Svake Entitetsklasser
I en entitetsklasse, som er en samling unike entiteter, er det avgjørende at hver entitet kan identifiseres unikt. Et eksempel er kommuner og gater, hvor hver kommune har et unikt nummer og navn, og hver gate er unik innenfor sin kommune.
<p align="center">
  <img src="../Pictures/Video%201/SvakeEnt1.png" alt="Svake entitetsklasser1" width="500"/>
</p>
En utfordring oppstår når en entitetsklasse, som Gate, mangler en naturlig nøkkel.

En løsning kan være å introdusere et ekstra nøkkelattributt, som GateNr, som gjør Gate til en regulær entitetsklasse. Dette krever ekstra administrasjon for å sikre unikhet på tvers av kommuner.
<p align="center">
  <img src="../Pictures/Video%201/SvakeEnt2.png" alt="Svake entitetsklasser2" width="500"/>
</p>
En alternativ løsning er å bruke en identifiserende relasjonsklasse for å definere svake entitetsklasser, som ikke har en egen nøkkel. Dette eliminerer behovet for et ekstra nøkkelattributt. For eksempel, i kombinasjon, blir KommuneNr og Gatenavn en unik identifikator.
<p align="center">
  <img src="../Pictures/Video%201/SvakeEnt3.png" alt="Svake entitetsklasser3" width="500"/>
</p>
