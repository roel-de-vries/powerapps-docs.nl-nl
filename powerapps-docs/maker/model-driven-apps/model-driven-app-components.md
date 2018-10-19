---
title: Inzicht krijgen in onderdelen van modelgestuurde apps in PowerApps | MicrosoftDocs
description: 'Krijg inzicht in verschillende onderdelen van een modelgestuurde app, zoals gegevens, gebruikersinterface, logica en visualisatie.'
Keywords: 'fields, attributes, model-driven app'
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="understand-model-driven-app-components"></a>Inzicht krijgen in onderdelen van modelgestuurde apps
Een goed ontworpen modelgestuurde app bestaat uit verschillende onderdelen die u met de ontwerper selecteert voor het bouwen van de vormgeving en functionaliteit van de voltooide app. De onderdelen en onderdeeleigenschappen die ontwerpers gebruiken bij de constructie van een app worden de metagegevens. 

Om te begrijpen hoe elk van deze onderdelen zich verhoudt tot appontwerp, zijn deze hier onderverdeeld in de categorieën *Gegevens*, *Gebruikersinterface*, *Logica* en *Visualisatie*. 

## <a name="data"></a>Gegevens
Deze onderdelen bepalen op welke gegevens de app wordt gebaseerd.


|Onderdeel  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|Entiteit     |Een item met eigenschappen die u wilt bijhouden, zoals een contactpersoon of account. Veel standaardentiteiten zijn beschikbaar. U kunt een standaardentiteit die niet tot het systeem behoort (productie-entiteit) aanpassen of een volledig nieuwe aangepaste entiteit maken.     | [!INCLUDE [powerapps](../../includes/powerapps.md)]-entiteitontwerper        |
|Veld     | Een eigenschap die is gekoppeld aan een entiteit. Een veld wordt gedefinieerd door een gegevenstype, waarmee wordt bepaald welke soort gegevens kunnen worden ingevoerd of geselecteerd. Voorbeelden zijn onder meer tekst, getal, datum en tijd, valuta of zoekactie (hiermee maakt u een relatie met een andere entiteit). Velden worden meestal gebruikt voor formulieren, weergaven en zoekopdrachten.        | [!INCLUDE [powerapps](../../includes/powerapps.md)]-entiteitontwerper   |
|relatie     | Entiteitsrelaties definiëren welke relaties entiteiten met elkaar hebben. Dit zijn de soorten relaties: 1:N (een-op-veel), N:1 (veel-op-een) en N:N (veel-op-veel). Wanneer u bijvoorbeeld een zoekveld toevoegt aan een entiteit, zorgt dit voor een nieuwe 1:N-relatie tussen de twee entiteiten en kunt u het opzoekveld op een formulier plaatsen.   | [!INCLUDE [powerapps](../../includes/powerapps.md)]-entiteitontwerper        |
|Optiesetveld     | Dit is een speciaal type veld dat de gebruiker een reeks vooraf bepaalde opties biedt. Elke optie heeft een nummerwaarde en label. Wanneer dit veld wordt toegevoegd aan een formulier, wordt in dit veld een besturingselement voor de gebruiker weergegeven om een optie te selecteren.  Er zijn twee soorten optiesets: optiesets waarbij de gebruiker slechts één optie kan selecteren en optiesets voor meervoudige selectie, waardoor meer dan één selectie mogelijk is.  | [!INCLUDE [powerapps](../../includes/powerapps.md)]-optiesetontwerper     |

Meer informatie: [Gegevens definiëren voor uw modelgestuurde app](define-data-model-driven-app.md) 

## <a name="ui"></a>Gebruikersinterface
Met deze componenten kunt u bepalen hoe gebruikers met de app communiceren. 

|Onderdeel  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|App     | Hiermee bepaalt u de grondbeginselen van de app, zoals componenten, eigenschappen, het clienttype en de URL van uw app.      | Appontwerper   |
|Siteoverzicht     | Hiermee geeft u de navigatie voor de app op.        | Ontwerper van siteoverzicht        |
|formulier     | Een reeks velden voor gegevensinvoer van een bepaalde entiteit die overeenkomt met de items die binnen uw organisatie voor de entiteit worden bijgehouden. Bijvoorbeeld een reeks velden voor gegevensinvoer waar gebruikers relevante informatie invoeren voor het bijhouden van de vorige bestellingen van een klant, samen met specifiek aangevraagde datums voor nieuwe bestellingen.        | Formulierontwerper        |
|weergave     | Weergaven bepalen hoe een lijst met records voor een specifieke entiteit worden weergegeven in uw app. In een weergave definieert u de weer te geven kolommen, de breedte van elke kolom, het sorteergedrag en de standaardfilters.   |  Weergaveontwerper       |

![Appontwerper en formulierontwerper](media/model-driven-app-overview/app-and-form-designers.png)

## <a name="logic"></a>Logica
Hiermee bepaalt u de bedrijfsprocessen, de regels en in hoeverre de app is geautomatiseerd. [!INCLUDE [powerapps](../../includes/powerapps.md)]-makers gebruiken een specifieke ontwerper voor het proces- of regeltype. 


|Type logica  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|Bedrijfsprocesstroom     | Een online proces dat gebruikers door een standaardbedrijfsproces leidt. Gebruik bijvoorbeeld een bedrijfsprocesstroom als u wilt dat iedereen aanvragen voor klantenservice op dezelfde manier afhandelt of dat medewerkers goedkeuring voor een factuur moeten verkrijgen voordat zij een order indienen.        | Ontwerper van bedrijfsprocesstromen        |
|Werkstroom     |  De werkstromen automatiseren bedrijfsprocessen zonder een gebruikersinterface. Ontwerpers gebruiken werkstromen om een automatisering in te stellen waarvoor interactie met de gebruiker niet vereist is.       | Werkstroomontwerper        |
|Acties    |  Acties zijn een type proces waarmee u rechtstreeks vanuit een werkstroom acties handmatig kunt aanroepen, met inbegrip van aangepaste acties.       |  Procesontwerper       |
|Bedrijfsregel     | Wordt gebruikt om een logica voor regels of aanbevelingen toe te passen op een formulier, zoals het stellen van vereisten voor velden, het verbergen van velden of het valideren van gegevens. Appontwerpers implementeren en onderhouden via een eenvoudige interface snel veranderende en veelgebruikte regels.         |  Bedrijfsregelontwerper       |
|Flow     | Flow is een op de cloud gebaseerde service waarmee u geautomatiseerde werkstromen kunt maken tussen apps en services voor het ophalen van meldingen, synchroniseren van bestanden, het verzamelen van gegevens en nog veel meer.        | Microsoft Flow        |

![Ontwerpers voor werkstromen, acties en bedrijfsprocesstromen](media/model-driven-app-overview/designer-mash.png)

Meer informatie: [Bedrijfslogica toepassen in uw modelgestuurde app](guide-staff-through-common-tasks-processes.md)

## <a name="visualizations"></a>Visualisaties
Hiermee wordt bepaald welke typen gegevensvisualisaties en rapportage beschikbaar zijn in de app.


|Onderdeel  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|Grafiek     | Eén grafische visualisatie die kan worden weergegeven in een weergave of op een formulier, of die kan worden toegevoegd aan een dashboard.        | Grafiekontwerper        |
|Dashboard     | Fungeert als een palet voor een of meer grafische visualisaties die een overzicht van bruikbare bedrijfsgegevens bieden.        | Dashboardontwerper        |
|Ingesloten Power BI     | Voeg ingesloten Power BI-tegels en -dashboards toe aan uw app. Power BI is een cloudservice die u inzicht in bedrijfsinformatie biedt.        |  Combinatie van grafiekontwerper, dashboardontwerper en Power BI       |

![Voorbeeld van dashboard](media/model-driven-app-overview/dashboard-designer.png)

## <a name="advanced-model-driven-app-making"></a>Geavanceerde modelgestuurde apps maken
De oplossingenverkenner is een uitgebreid hulpprogramma voor het bouwen van geavanceerde modelgestuurde apps. In de oplossingenverkenner kunt u met het navigatievenster aan de linkerkant van het hulpprogramma door een hiërarchie navigeren die bestaat uit alle apponderdelen.

![Oplossingenverkenner](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

U opent de oplossingenverkenner door **Modelgestuurd** in het linkerdeelvenster van [!INCLUDE [powerapps](../../includes/powerapps.md)] te selecteren.

  ![Modelgestuurd selecteren](media/model-driven-app-overview/app-type-picker-mod.png)

Selecteer vervolgens het tabblad **Geavanceerd**.

Meer informatie: [Geavanceerde apps maken en aanpassen](advanced-navigation.md)

## <a name="related-topics"></a>Verwante onderwerpen

[Uw modelgestuurde app valideren en publiceren](validate-app.md)

[Uw modelgestuurde app delen](share-model-driven-app.md)
