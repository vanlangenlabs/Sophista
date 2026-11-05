# Sophista — productconcept

## Probleem

Organisatiekennis in documenten is niet vanzelf betrouwbaar, vindbaar en
herbruikbaar op het moment dat iemand een vraag stelt. Een gebruiker van een
taalmodel heeft daarom een manier nodig om antwoorden te krijgen die relevante
organisatiekennis meenemen, in plaats van alleen een rechtstreeks antwoord van
een onderliggend model.

## Beoogde gebruikers

- Mensen die via een client vragen stellen en daarvoor een geconfigureerd
  Sophista-profiel kiezen.
- De mensen of teams die profielen en de bijbehorende kennisbronnen beschikbaar
  maken.

De precieze gebruikersrollen en organisatiecontext zijn nog niet bevestigd.

## Gewenst resultaat

Een gebruiker kan een profiel kiezen dat past bij diens vraag. Sophista gebruikt
de kennis die bij dat profiel hoort om het antwoord van een taalmodel van
relevante context te voorzien, zodat de gebruiker een bruikbaar antwoord krijgt
op basis van de beschikbare organisatiekennis.

## Productgrenzen en niet-doelen

- Sophista is de middleware tussen clients, geconfigureerde profielen,
  organisatiekennis en taalmodellen.
- Het verwerken en indexeren van brondocumenten valt buiten Sophista en gebeurt
  in een afzonderlijke applicatie.
- Tijdens het beantwoorden van verzoeken gebruikt Sophista de reeds
  geïndexeerde kennis alleen-lezen.
- De aangeleverde specificatie noemt concrete API-, provider-, opslag-,
  configuratie- en streamingkeuzes. Die horen niet thuis in dit concept en
  worden hier niet als aanvullende ontwerpbesluiten vastgelegd.
- Andere productgrenzen en expliciete niet-doelen zijn nog niet bevestigd.

## Succesmaten

Voorgestelde kwalitatieve indicatoren, afgeleid van de aangeleverde
productspecificatie:

- Gebruikers kunnen een passend profiel kiezen en ontvangen antwoorden waarin
  relevante organisatiekennis is verwerkt.
- De profielkeuze leidt tot antwoorden die aansluiten bij de bijbehorende
  kenniscontext.
- Het beantwoorden van verzoeken blijft gescheiden van het verwerken en
  indexeren van brondocumenten.

Er zijn nog geen meetmethoden, streefwaarden of acceptatiedrempels opgegeven.

## Besluiten en bewijs

- De eigenaar beschreef Sophista als een middlewareproxy die clients
  geconfigureerde profielen aanbiedt en antwoorden met relevante kenniscontext
  verrijkt.
- De eigenaar gaf aan dat documentverwerking en indexering in een afzonderlijke
  applicatie plaatsvinden en dat Sophista de kennisopslag tijdens verzoeken
  alleen-lezen gebruikt.
- Bewijs: de door de eigenaar aangeleverde Sophista-specificatie in de
  taakconversatie van 2026-11-05.
- De specificatie bevat ook implementatie- en interfacekeuzes. Hun status als
  bindende productvereisten is nog niet vastgesteld; ze zijn daarom niet
  uitgewerkt in dit concept.

## Open vragen

- Welke gebruikersrollen en organisatiecontext zijn leidend?
- Welke meetbare doelen en drempelwaarden bepalen of antwoorden voldoende
  betrouwbaar, vindbaar en bruikbaar zijn?
- Welke productgrenzen of niet-doelen ontbreken nog?
- Zijn de genoemde API-, provider-, vectoropslag-, configuratie- en
  streamingkeuzes bindende eisen of PoC-richtingen voor een latere fase?
