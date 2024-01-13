## Fra "miniverden" til realisert database
- _Databasen som modell_ av en del av virkeligheten
- _Miniverden_ er den relevante delen av virkelighetem
- Miniverdenen gir oss
  - Relevante (data-)__objekter__
  - Relevante __sammenhenger__ mellom objekter
  - Relevante __regler__ som gjelder

 Miniverden --> Konseptuell modell --> Logisk modell --> Fysisk modell (DB)
 BILDE MINIVERDEN


## Entity-Relationship-modeller
- Mange dialekter
- Konseptuell datmodell
  - Høynivå, begrepsorientert og orientert mot menneskelig kommunikasjon (forståelse og dokumentasjon)
- Datastruktir
  - __Entiteter__ (objekter) og __relasjoner__ mellom entiteter
  - __Entitetsklasser__ og __relasjonsklasser__
  - __Attributter__
- Restriksjoner (constraints)
  - Nøkkelsrestriksjoner
  - Datatyper for attributter
  - Strukturelle restriksjoner
- Dataoperasjoner (innsetting, endring, sletting og spørring)
  - Lite relevant for konsepuelle datamodeller
BILDE TANKEKART

## Entiteter 
- __Entitet__: objekt eller "noe" som eksisterer i miniverdenen
- Beskriver _egenskaper_ ved entiteter vha. __attributter__
- Attributt henter sine mulige __verdier__ fra et __domene_ (datatype)
- Ulike __typer__ attributter
  - Enkle, sammensatte
  - En eller flere verdier
  - Avledet (vha. en regel)
  - Nøkkelattributter (entydige identifikatorer)
BILDE ENTITET
 
## Entitetsklasse/-type
- Mengden av alle likeartede _entiteter som er av samme klasse_ og har samme egenskaper
- Alle entitetsklasser må ha en unik identifikator (nøkkel)
- Datatyper tas vanligvis ikke med i diagrammer
BILDE ENTITETSKLASSE
 
## Relasjoner
- __Relasjon__: sammenheng mellom to eller flere entiteter
- Modellerer informasjon som viser en sammen heng mellom to eller flere entiteter
  - "en student har tatt eksamen i et emne"
  - "en person eier en bil"
- Kan ha _egenskaper_ på samme måte som entiteter, altså egne _attributter_
  - "karakteren som en student fikk på eksamen i et emne"
- Relasjonen eksisterer _ikke_ uten de entitetene som deltar
BILDE RELASJONER

## Relasjonsklasser/-typer
- Mengden av likeartede relasjoner mellom samme entitetsklasser
BILDE RELASJONSKLASSER
- Restiksjoner
  - Kardinalitetsforhold: Begrenser hvor mange entiteter en entitet kan ha samme relasjon til
    BILDE RESTRIKSJONER1
    Person - BittAv - Hund: mange til mange relasjon
  - Deltakelseskrav: Kan spesifisere at en entitet _må_ ha en relasjon til minst en entitet
    BILDE RESTRIKSJONER2
  - Strukturelle restriksjoner: Spesifiserer både kardinalitets- og eksistensrestriksjoner i et min-maks-par
    BILDE RESTRIKSJONER3
  - Sammenligning
    - Alternative måter å spesifisere det samme
    - Legg merke til at "maks" bytter side
    - Husk forskjellen mellom delvis og total deltakelse
      BILDE RESTRIKSJONER4

## Forekomst-nivå
BILDE FOREKOMSTNIVÅ

## Om relasjoner
- Relasjoner kan ha __egenskaper__ som modelleres som attributter
BILDE OMRELASJONER1
- Relasjonens __grad__ (degree) er antall entiteter som inngår
BILDE OMRELASJONER2
- Relasjoner eksisterer _ikke_ uten de entitetene som inngår

## Trinn i utvikling av datamodell
1. Finn de nødvendige _entitetsklassene_
2. Finn _attributter_ for entitetsklassene
3. Finn de nødvendige _entitetsklassene_
4. Finn _attributter_ for relasjonsklassene
5. Bestem _nøkler_ for entitetsklassene
6. Bestem _restriksjoner_ for relasjonsklassene
7. _Vurder_ om du har en god modell, gjør ev. nødvendige endringer








  
