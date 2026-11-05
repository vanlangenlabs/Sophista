# Sophista — productconcept

## Probleem

Organisatiekennis in documenten is niet vanzelf betrouwbaar, vindbaar en
herbruikbaar op het moment dat iemand een vraag stelt. Een gebruiker van een
taalmodel heeft daarom een manier nodig om een vraag te laten beantwoorden met
relevante organisatiekennis, in plaats van alleen met de algemene kennis van
een onderliggend model.

## Beoogde gebruikers

- Mensen die via OpenWebUI of een vergelijkbare client vragen stellen en een
  Sophista-profiel kiezen.
- De mensen die Sophista-profielen en de bijbehorende kenniscontext beheren;
  hun precieze rol is nog niet bevestigd.

Sophista beheert zelf geen gebruikers. Gebruikersbeheer wordt verzorgd door een
andere applicatie.

## Gewenst resultaat

Sophista biedt clients een compatibele middleware-interface met geconfigureerde
profielen die als afzonderlijke taalmodelkeuzes beschikbaar zijn. Een profiel
bepaalt welke organisatiekennis bij een vraag wordt opgehaald en naar welk
taalmodel het verzoek wordt gerouteerd. Sophista verrijkt zo het verzoek met
relevante context; als de client om streaming vraagt, ontvangt die het antwoord
stapsgewijs.

De informatie uit de organisatiekennis die voor het antwoord wordt gevonden en
gebruikt, wordt als bron bij het resultaat getoond. Als er geen relevante bron
wordt gevonden, mag het onderliggende taalmodel de vraag met zijn eigen kennis
proberen te beantwoorden; het resultaat maakt dan duidelijk dat dit antwoord
niet op gevonden organisatiekennis is gebaseerd.

De eigenaar heeft aangegeven dat deze profiel-, kennisverrijkings- en
routeringsarchitectuur de kern van het product vormt, niet een optionele
uitbreiding.

## Productgrenzen en niet-doelen

- Sophista verwerkt verzoeken en leest de reeds voorbereide kenniscontext.
- Het verwerken, inlezen en indexeren van brondocumenten gebeurt in een
  afzonderlijke applicatie; Sophista wijzigt de kennisopslag niet tijdens het
  beantwoorden van verzoeken.
- Sophista heeft geen eigen gebruikersbeheer; een andere applicatie is hiervoor
  verantwoordelijk.
- De organisatiekennis kan uit verschillende soorten bronnen komen, waaronder
  code, handleidingen van machines, klant-URS'en en wiki's. Deze voorbeelden
  beperken de mogelijke kennisdomeinen niet.
- De concrete technische uitwerking van de in de specificatie genoemde
  API-compatibiliteit, providers, vectoropslag, configuratie en streaming hoort
  bij de Design-fase, na goedkeuring van het Concept en vóór implementatie. Die
  uitwerking moet vóór implementatie volledig zijn vastgelegd; dit Concept kiest
  geen aanvullende technische details.
- Andere productgrenzen en expliciete niet-doelen zijn nog niet bevestigd.

## Succesmaten

De eerste gewenste gebruikersuitkomst is dat Sophista vragen over een onderwerp
kan beantwoorden met relevante inhoud uit de voorbereide Markdown-documenten,
en dat de gebruiker de gebruikte informatie kan terugvinden via een bron bij
het antwoord. De documenten worden buiten Sophista verwerkt, bijvoorbeeld
opgedeeld in stukken en gevectoriseerd, voordat Sophista ze voor antwoorden
gebruikt.

Er zijn nog geen meetmethode, streefwaarde of acceptatiedrempel gekozen.

## Besluiten en bewijs

- De eigenaar beschreef Sophista als een OpenAI-compatibele middlewareproxy die
  profielen aanbiedt en verzoeken verrijkt met context uit organisatiekennis,
  waarna ze naar het bijbehorende taalmodel worden gerouteerd.
- De eigenaar bevestigde dat de beschreven profiel-, RAG-, embedding-,
  routerings- en streamingarchitectuur vanaf het begin centraal moet staan.
- De eigenaar gaf aan dat documentverwerking en indexering in een afzonderlijke
  applicatie plaatsvinden en dat Sophista de kennisopslag tijdens verzoeken
  alleen-lezen gebruikt.
- De eigenaar noemde code, machinehandleidingen, klant-URS'en en wiki's als
  mogelijke kennisbronnen, zonder de kennisdomeinen daartoe te beperken.
- De eigenaar vereist dat gevonden en in het antwoord gebruikte informatie als
  bron bij het resultaat wordt weergegeven.
- Als geen relevante organisatiebron wordt gevonden, mag het taalmodel volgens
  de eigenaar antwoorden met eigen kennis, mits dit duidelijk wordt vermeld.
- De eigenaar gaf aan dat Sophista zelf geen gebruikersbeheer heeft en dat een
  andere applicatie dit verzorgt.
- De eigenaar noemde als eerste gewenste gebruikersuitkomst dat Sophista vragen
  over een onderwerp kan beantwoorden op basis van toegevoegde Markdown-documenten
  die vooraf zijn opgedeeld en gevectoriseerd, en dat de gebruikte informatie
  met een bron terug te vinden is.
- Bewijs: de door de eigenaar aangeleverde Sophista-specificatie en
  verduidelijkingen in de taakconversatie van 2026-11-05.

## Open vragen

- Welke meetmethode, streefwaarde of acceptatiedrempel past bij deze gewenste
  uitkomst, is nog niet bepaald.
