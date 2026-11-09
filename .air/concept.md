# Sophista — productconcept

## Probleem

Organisatiekennis in documenten is niet vanzelf betrouwbaar, vindbaar en
herbruikbaar op het moment dat iemand een vraag stelt. Een gebruiker van een
taalmodel heeft daarom een manier nodig om een vraag te laten beantwoorden met
relevante organisatiekennis, in plaats van alleen met de algemene kennis van
een onderliggend model.

## Beoogde gebruikers

- Mensen die via een client vragen stellen en een
  Sophista-profiel kiezen.
- De mensen die Sophista-profielen en de bijbehorende kenniscontext beheren;
  hun precieze rol is nog niet bevestigd.

Sophista beheert zelf geen gebruikers. Gebruikersbeheer wordt verzorgd door een
andere applicatie.

## Gewenst resultaat

Mensen kunnen Sophista via een client een vraag stellen en een antwoord krijgen
op basis van relevante Markdown-kennis die beschikbaar is voor het gekozen
profiel. Profielen zijn afzonderlijke taalmodelkeuzes en bepalen uit welke een
of meer kenniscategorieën informatie kan worden opgehaald en naar welk taalmodel
het verzoek wordt gerouteerd. Sophista verrijkt zo het verzoek met relevante
context; als de client om streaming vraagt, ontvangt die het antwoord
stapsgewijs.

Sophista biedt een API om gestructureerde kennis te beheren. Kennis kan documenten
met een hiërarchie van geneste knooppunten omvatten. De documenthiërarchie en de
segmenten die voor het ophalen van informatie worden gebruikt, zijn onafhankelijk
van elkaar: een segment kan inhoud uit meerdere onderdelen combineren, ook uit
verschillende hoofdstukken. Meerdere embeddingmodellen kunnen gelijktijdig worden
gebruikt zonder de kennisstructuur te dupliceren.

Externe applicaties importeren en interpreteren bronmateriaal en gebruiken
Sophista om de bijbehorende gestructureerde kennis te beheren. Ze hebben geen
rechtstreekse toegang tot de database. Sophista beheert embeddings afzonderlijk
van het importeren van bronnen en kan ontbrekende of verouderde embeddings
herkennen. Bij incrementele synchronisatie blijven identiteiten waar mogelijk
behouden; alleen embeddings die afhankelijk zijn van gewijzigde inhoud worden
ongeldig gemaakt.

De informatie uit de organisatiekennis die voor het antwoord wordt gevonden en
gebruikt, wordt als controleerbare bron bij het resultaat getoond. De verwijzing
maakt de locatie traceerbaar vanaf het huidige inhoudsknooppunt via de
bovenliggende knooppunten. Als een inhoudsknooppunt geen naam heeft, wordt het
met een contextgebaseerde beschrijving van één zin aangeduid. Of de bronvermelding
ook een URI bevat, is nog niet besloten. Als er geen relevante bron wordt
gevonden, mag het onderliggende taalmodel de vraag met zijn eigen kennis
proberen te beantwoorden; het resultaat maakt dan duidelijk dat dit antwoord
niet op gevonden organisatiekennis is gebaseerd.

De eigenaar heeft aangegeven dat deze profiel-, kennisverrijkings- en
routeringsarchitectuur de kern van het product vormt, niet een optionele
uitbreiding.

## Productgrenzen en niet-doelen

- Deze revisie wijzigt de eerder vastgelegde productgrens: Sophista beheert
  gestructureerde kennis en de embeddings daarvan; het is niet langer uitsluitend
  een lezer van extern voorbereide, onveranderlijke kennis.
- Externe applicaties blijven verantwoordelijk voor het importeren en
  interpreteren van bronmateriaal. Zij beheren de kennis via Sophista en krijgen
  geen rechtstreekse toegang tot de database.
- Sophista beheert kennisstructuur en embeddings, los van het externe
  importproces. Documenthiërarchie en ophaalsegmenten hoeven niet dezelfde
  indeling te volgen.
- Sophista heeft geen eigen gebruikersbeheer; een andere applicatie is hiervoor
  verantwoordelijk.
- De bronvermelding kan de huidige locatie en de bovenliggende documentlocaties
  tonen; inhoud zonder naam wordt met een contextgebaseerde beschrijving van één
  zin aangeduid. Of een URI ook deel uitmaakt van de bronvermelding is nog niet
  besloten.
- De organisatiekennis kan uit verschillende soorten bronnen komen, waaronder
  code, handleidingen van machines, klant-URS'en en wiki's. Deze voorbeelden
  beperken de mogelijke kennisdomeinen niet.
- De concrete technische uitwerking van API-compatibiliteit, kennisbeheer,
  embeddings, providers, opslag, configuratie en streaming hoort bij de
  Design-fase, na goedkeuring van het Concept en vóór implementatie. Die
  uitwerking moet vóór implementatie volledig zijn vastgelegd; dit Concept kiest
  geen schema's, algoritmen, API-contracten of technologieën.
- Andere productgrenzen en expliciete niet-doelen zijn nog niet bevestigd.

## Succesmaten

Het systeem kan een antwoord formuleren met een bronvermelding die de gebruiker
kan controleren. De antwoorden gebruiken relevante inhoud uit Markdown-documenten
die externe applicaties importeren en interpreteren en die via Sophista als
gestructureerde kennis worden beheerd.

De acceptatievoorwaarde is dat het antwoord een controleerbare bronvermelding
bevat. Aanvullende meetmethoden of numerieke streefwaarden zijn voor deze fase
niet nodig.

## Besluiten en bewijs

- De eigenaar beschreef Sophista als een OpenAI-compatibele middlewareproxy die
  profielen aanbiedt en verzoeken verrijkt met context uit organisatiekennis,
  waarna ze naar het bijbehorende taalmodel worden gerouteerd.
- De eigenaar bevestigde dat de beschreven profiel-, RAG-, embedding-,
  routerings- en streamingarchitectuur vanaf het begin centraal moet staan.
- De eigenaar gaf aanvankelijk aan dat documentverwerking en indexering in een
  afzonderlijke applicatie plaatsvinden en dat Sophista de kennisopslag tijdens
  verzoeken alleen-lezen gebruikt. Deze productgrens is door de latere expliciete
  vraag om kennis- en embeddingbeheer via Sophista herzien.
- De eigenaar noemde code, machinehandleidingen, klant-URS'en en wiki's als
  mogelijke kennisbronnen, zonder de kennisdomeinen daartoe te beperken.
- De eigenaar vereist dat gevonden en in het antwoord gebruikte informatie als
  bron bij het resultaat wordt weergegeven.
- Als geen relevante organisatiebron wordt gevonden, mag het taalmodel volgens
  de eigenaar antwoorden met eigen kennis, mits dit duidelijk wordt vermeld.
- De eigenaar gaf aan dat Sophista zelf geen gebruikersbeheer heeft en dat een
  andere applicatie dit verzorgt.
- De eigenaar noemde als eerste gewenste gebruikersuitkomst dat Sophista vragen
  over een onderwerp kan beantwoorden op basis van Markdown-documenten en dat de
  gebruikte informatie met een bron terug te vinden is.
- De eigenaar verduidelijkte dat acceptatie betekent dat het systeem een antwoord
  kan formuleren met een bronvermelding die te valideren is; aanvullende
  meetmethoden of numerieke streefwaarden zijn voor nu niet nodig.
- De eigenaar vroeg om Sophista uit te breiden van alleen-lezen toegang tot
  voorbereide kennis naar beheer van gestructureerde kennis en embeddings.
- De eigenaar legde vast dat externe applicaties bronmateriaal importeren en
  interpreteren, kennis via Sophista beheren en geen rechtstreekse databasetoegang
  krijgen.
- De eigenaar vroeg om hiërarchische documenten met geneste onderdelen, los van
  ophaalsegmenten die meerdere onderdelen en hoofdstukken kunnen combineren.
- De eigenaar vroeg om gelijktijdige ondersteuning van meerdere embeddingmodellen
  zonder duplicatie van de kennisstructuur, en om detectie van ontbrekende of
  verouderde embeddings.
- De eigenaar vroeg om incrementele synchronisatie die identiteiten waar mogelijk
  behoudt en alleen afhankelijke embeddings ongeldig maakt bij gewijzigde inhoud.
- De eigenaar vroeg om profielen die meerdere kenniscategorieën kunnen gebruiken
  en om bronverwijzingen die de oorspronkelijke documentlocatie traceerbaar maken.
- De eigenaar verduidelijkte dat Sophista vragen moet kunnen beantwoorden op
  basis van relevante Markdown-kennis en dat bronvermelding een fundamenteel
  productelement is, geen afzonderlijke feature. De bronvermelding toont de
  huidige inhoudsnode en de bovenliggende nodes; een node zonder naam krijgt een
  contextgebaseerde beschrijving van één zin. URI-ondersteuning is niet bevestigd.
- Bewijs: de door de eigenaar aangeleverde Sophista-specificatie en
  verduidelijkingen in de taakconversatie van 2026-11-05.
