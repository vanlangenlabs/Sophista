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

Gebruikersaccounts en -rollen vallen volgens de eigenaar onder OpenWebUI. Het
is nog onduidelijk of Sophista daarnaast gebruikersidentiteit nodig heeft om
toegang tot verschillende kennisbronnen te begrenzen.

## Gewenst resultaat

Sophista biedt clients een compatibele middleware-interface met geconfigureerde
profielen die als afzonderlijke taalmodelkeuzes beschikbaar zijn. Een profiel
bepaalt welke organisatiekennis bij een vraag wordt opgehaald en naar welk
taalmodel het verzoek wordt gerouteerd. Sophista verrijkt zo het verzoek met
relevante context; als de client om streaming vraagt, ontvangt die het antwoord
stapsgewijs.

De eigenaar heeft aangegeven dat deze profiel-, kennisverrijkings- en
routeringsarchitectuur de kern van het product vormt, niet een optionele
uitbreiding.

## Productgrenzen en niet-doelen

- Sophista verwerkt verzoeken en leest de reeds voorbereide kenniscontext.
- Het verwerken, inlezen en indexeren van brondocumenten gebeurt in een
  afzonderlijke applicatie; Sophista wijzigt de kennisopslag niet tijdens het
  beantwoorden van verzoeken.
- Gebruikersaccounts en -rollen worden door OpenWebUI beheerd, niet door
  Sophista.
- De concrete technische uitwerking van de in de specificatie genoemde
  API-compatibiliteit, providers, vectoropslag, configuratie en streaming hoort
  bij de Design-fase, na goedkeuring van het Concept en vóór implementatie. Die
  uitwerking moet vóór implementatie volledig zijn vastgelegd; dit Concept kiest
  geen aanvullende technische details.
- Andere productgrenzen en expliciete niet-doelen zijn nog niet bevestigd.

## Succesmaten

Met succesmaten bedoel ik hoe we kunnen vaststellen dat het product het
bedoelde resultaat voor gebruikers bereikt. Dit gaat om uitkomsten van de
applicatie, niet om een ontwerpkeuze. Mogelijke onderwerpen om later meetbaar
te maken zijn bijvoorbeeld of de opgehaalde kennis relevant is voor de vraag,
of antwoorden aantoonbaar op die kennis steunen en hoe lang een antwoord op
zich laat wachten. Dit zijn voorbeelden, geen vastgestelde eisen of doelen.

De eigenaar heeft nog geen meetmethode, streefwaarde of acceptatiedrempel
gekozen.

## Besluiten en bewijs

- De eigenaar beschreef Sophista als een OpenAI-compatibele middlewareproxy die
  profielen aanbiedt en verzoeken verrijkt met context uit organisatiekennis,
  waarna ze naar het bijbehorende taalmodel worden gerouteerd.
- De eigenaar bevestigde dat de beschreven profiel-, RAG-, embedding-,
  routerings- en streamingarchitectuur vanaf het begin centraal moet staan.
- De eigenaar gaf aan dat documentverwerking en indexering in een afzonderlijke
  applicatie plaatsvinden en dat Sophista de kennisopslag tijdens verzoeken
  alleen-lezen gebruikt.
- Gebruikersaccounts en -rollen worden volgens de eigenaar door OpenWebUI
  afgehandeld.
- Bewijs: de door de eigenaar aangeleverde Sophista-specificatie en
  verduidelijkingen in de taakconversatie van 2026-11-05.

## Open vragen

- Welke soorten kennis en vragen vallen in de eerste productcontext? Zijn de
  HR- en technische profielen uit de specificatie voorbeelden of de beoogde
  startcontext?
- Als bij een vraag geen relevante organisatiekennis wordt gevonden, moet
  Sophista dan geen inhoudelijk antwoord geven, of mag het onderliggende model
  ook algemene kennis gebruiken? Moet een antwoord laten zien op welke
  brondocumenten het steunt?
- Is het voldoende dat OpenWebUI accounts en rollen beheert, of moet Sophista
  ook identiteit of toegangscontext ontvangen om kennis per gebruiker te
  filteren?
- Welke gebruikersuitkomst is voor jou het belangrijkst om als eerste te
  beoordelen: relevante opgehaalde kennis, antwoorden die op die kennis
  steunen, reactietijd, of iets anders? Welke manier van beoordelen zou voor
  jou overtuigend zijn? Er zijn nog geen getallen nodig.
