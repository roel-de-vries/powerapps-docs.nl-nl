---
title: Inzicht in modelgestuurde app-onderdelen in PowerApps | MicrosoftDocs
description: Krijg inzicht in verschillende componenten van een modelgestuurde app, zoals gegevens, de gebruikersinterface, logica en visualisatie.
Keywords: fields, attributes, model-driven app
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
ms.openlocfilehash: 249f0d35ce9eb466303ef16658aa01198632875e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674743"
---
# <a name="understand-model-driven-app-components"></a>Componenten van modelgestuurde apps begrijpen
Een goed ontworpen modelgestuurde app bestaat uit verschillende componenten die u selecteert met de ontwerper om de vormgeving en functionaliteit van de voltooide app te bouwen. De componenten en componenteigenschappen die ontwerpers gebruiken bij de constructie van een app, worden de metagegevens. 

Om te begrijpen hoe elk van deze onderdelen zich verhoudt tot app-ontwerp, zijn deze hier verdeeld in de categorieën *Gegevens*, *Gebruikersinterface*, *Logica* en *Visualisatie*. 

## <a name="data"></a>Gegevens
Deze componenten bepalen op welke gegevens de app wordt gebaseerd.


|Component  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|Entiteit     |Een item met eigenschappen die u bijhoudt, zoals een contactpersoon of account. Veel standaardentiteiten zijn beschikbaar. U kunt een standaardentiteit die niet tot het systeem behoort (productie-entiteit) aanpassen of een volledig nieuwe aangepaste entiteit maken.     | [!INCLUDE [powerapps](../../includes/powerapps.md)] entiteitdesigner        |
|Veld     | Een eigenschap die is gekoppeld aan een entiteit. Een veld wordt gedefinieerd door een gegevenstype, waarmee wordt bepaald welk soort gegevens kunnen worden ingevoerd of geselecteerd. Voorbeelden zijn onder meer tekst, getal, datum en tijd, valuta of zoekactie (hiermee maakt u een relatie met een andere entiteit). Velden worden meestal gebruikt voor formulieren, weergaven en zoekopdrachten.        | [!INCLUDE [powerapps](../../includes/powerapps.md)] entiteitdesigner   |
|Relatie     | Entiteitsrelaties definiëren welke relaties entiteiten met elkaar hebben. Dit zijn de soorten relaties: 1:N (een-op-veel), N:1 (veel-op-een) en N:N (veel-op-veel) Wanneer u bijvoorbeeld een zoekveld toevoegt aan een entiteit, zorgt dit voor een nieuwe 1:N-relatie tussen de twee entiteiten en kunt u het opzoekveld op een formulier plaatsen.   | [!INCLUDE [powerapps](../../includes/powerapps.md)] entiteitdesigner        |
|Veld Optieset     | Dit is een speciaal type veld dat de gebruiker een reeks vooraf bepaalde opties biedt. Elke optie heeft een numerieke waarde en een label. Wanneer deze wordt toegevoegd aan een formulier, wordt in dit veld een besturingselement voor de gebruiker weergegeven om een optie te selecteren.  Er zijn twee soorten optiesets; optiesets waarbij de gebruiker slechts één optie kan selecteren en optiesets voor meervoudige selectie, waardoor meer dan één selectie mogelijk is.  | [!INCLUDE [powerapps](../../includes/powerapps.md)] optiesetontwerper     |

Meer informatie: [Gegevens voor uw modelgestuurde app definiëren](define-data-model-driven-app.md) 

## <a name="ui"></a>GEBRUIKERSINTERFACE
Met deze componenten kunt u bepalen hoe gebruikers met de app communiceren. 

|Component  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|App     | Hiermee bepaalt u de grondbeginselen van de app zoals componenten, eigenschappen, clienttype en URL van uw app.      | Appontwerper   |
|Sitemap     | Hiermee geeft u de navigatie voor uw app aan.        | Sitemapontwerper        |
|Formulier     | Een reeks velden voor gegevensinvoer van een bepaalde entiteit die overeenkomt met de items die binnen uw organisatie voor de entiteit worden bijgehouden. Bijvoorbeeld een reeks velden voor gegevensinvoer waar gebruikers relevante informatie invoeren voor het bijhouden van de vorige bestellingen van een klant, samen met specifiek aangevraagde datums voor nieuwe bestellingen.        | Formulierontwerper        |
|Weergeven     | In Weergaven kunt u bepalen hoe een lijst met records voor een specifieke entiteit wordt weergegeven in uw app. In een weergave definieert u de weer te geven kolommen, de breedte van elke kolom, het sorteergedrag en de standaardfilters.   |  Weergaveontwerper       |

![Appontwerper en formulierontwerper](media/model-driven-app-overview/app-and-form-designers.png)

## <a name="logic"></a>Logica
Hiermee bepaalt u de bedrijfsprocessen, de regels en in hoeverre de app is geautomatiseerd. [!INCLUDE [powerapps](../../includes/powerapps.md)]-makers gebruiken een ontwerper die specifiek is voor het type proces of regel. 


|Type logica  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|Zakelijke processtroom     | Een online proces waarin gebruikers een standaard bedrijfsproces doorlopen. Gebruik bijvoorbeeld een zakelijke processtroom als u wilt dat iedereen aanvragen voor klantenservice op dezelfde manier afhandelt, of om medewerkers te verplichten om goedkeuring te vragen voor een factuur voordat zij een order verzenden.        | Ontwerper zakelijke processtroom        |
|Werkstroom     |  Via werkstromen kunt u bedrijfsprocessen automatiseren zonder gebruikersinterface. Ontwerpers gebruiken werkstromen om een automatisering in te stellen waarvoor geen interactie met de gebruiker is vereist.       | Workflow Designer        |
|Acties    |  Acties zijn een type proces waarmee u rechtstreeks vanuit een werkstroom acties handmatig kunt aanroepen, met inbegrip van aangepaste acties.       |  Procesontwerper       |
|Bedrijfsregel     | Wordt gebruikt om een logica voor regels of aanbevelingen toe te passen op een formulier, zoals het stellen van vereisten voor velden, het verbergen van velden of het valideren van gegevens. Appontwerpers implementeren en onderhouden via een eenvoudige interface snel veranderende en veelgebruikte regels.         |  Bedrijfsregelontwerper       |
|Stroom     | Flow is een op de cloud gebaseerde service waarmee u geautomatiseerde werkstromen kunt maken tussen apps en services voor het ophalen van meldingen, synchroniseren van bestanden, het verzamelen van gegevens en nog veel meer.        | Microsoft Flow        |

![Ontwerpers van werkstromen, acties en bedrijfsprocessen](media/model-driven-app-overview/designer-mash.png)

Meer informatie: [Bedrijfslogica in uw modelgestuurde app toepassen](guide-staff-through-common-tasks-processes.md)

## <a name="visualizations"></a>Visualisaties
Hiermee wordt bepaald over welk type gegevensvisualisaties en rapportage de app gaat beschikken.


|Component  |Beschrijving  |Ontwerper  |
|---------|---------|---------|
|Grafiek     | Eén enkele grafische visualisatie die kan worden weergegeven in een weergave of op een formulier, of die kan worden toegevoegd aan een dashboard.        | Grafiekontwerper        |
|Dashboard     | Fungeert als een palet voor een of meer grafische visualisaties die een overzicht van bruikbare bedrijfsgegevens bieden.        | Dashboardontwerper        |
|Ingesloten Power BI     | Ingesloten Power BI-tegels en -dashboards toevoegen aan uw app. Power BI is een cloudservice die u inzicht in business intelligence biedt.        |  Combinatie van grafiekontwerper, dashboardontwerper en Power BI       |

![Voorbeelddashboard](media/model-driven-app-overview/dashboard-designer.png)

## <a name="advanced-model-driven-app-making"></a>Geavanceerde modelgestuurde apps maken
Solution Explorer is een uitgebreid hulpprogramma dat wordt gebruikt voor het bouwen van geavanceerde modelgestuurde apps. In Solution Explorer kunt u met het navigatievenster aan de linkerkant van het hulpprogramma door een hiërarchie navigeren die bestaat uit alle app-componenten.

![Solution Explorer](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

Als u Solution Explorer wilt openen, selecteert u **Modelgestuurd** in het linkerdeelvenster van [!INCLUDE [powerapps](../../includes/powerapps.md)].

  ![Selecteer Modelgestuurd](media/model-driven-app-overview/app-type-picker-mod.png)

Selecteer vervolgens het tabblad **Geavanceerd**.

Meer informatie: [Geavanceerde apps maken en aanpassen](advanced-navigation.md)

## <a name="related-topics"></a>Verwante onderwerpen

[Uw modelgestuurde app valideren en publiceren](validate-app.md)

[Uw modelgestuurde app delen](share-model-driven-app.md)