---
title: De app aanpassen (Common Data Service) | Microsoft Docs
description: Schermen, besturingselementen en velden van de app bijwerken
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: wHy72cOe8Os
courseduration: 12m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: bc5ce767124f531e70c32c34087e0572a87923f2
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="customize-the-app-common-data-service"></a>De app aanpassen (Common Data Service)
In de eerste twee onderwerpen van deze sectie hebt u een app gegenereerd op basis van een Common Data Service-entiteit en hebben we de app nader verkend om een beter beeld te krijgen van de manier waarop apps met drie schermen zijn samengesteld. De app die PowerApps heeft gegenereerd is handig, maar u zult een app vaak willen aanpassen nadat deze is gegenereerd. In dit onderwerp behandelen we enkele wijzigingen voor het bladerscherm van de app. U kunt elk van de schermen aanpassen, maar we wilden ons met maar één ervan bezighouden om wat dieper in te gaan op de aanpassingen. Neem een van de apps die u hebt gegeneerd – op basis van een entiteit, een Excel-bestand of een andere bron – en zie hoe u deze kunt aanpassen. Dit is zonder meer de beste manier om te leren hoe apps worden samengesteld.

## <a name="change-gallery-and-data-bindings"></a>Galerie en gegevensbindingen wijzigen
Toen PowerApps de app genereerde, werd gekozen voor een bepaalde indeling en specifieke velden om op elk scherm weer te geven. Voor deze app kiezen we voor een galeriebesturingselement met een statusbalk (we gaan de statusbalk verderop aanpassen). Selecteer de gewenste indeling op het tabblad **Indeling** in het rechterdeelvenster. U ziet onmiddellijk de resultaten, omdat PowerApps de app bijwerkt terwijl u de wijzigingen aanbrengt.

![De indeling van het bladerscherm wijzigen](./media/learning-case-app-customize/change-layout.png)

Vanuit de juiste basisindeling gaat u nu de weergegeven velden wijzigen. Klik of tik op een veld in het eerste item en wijzig vervolgens in het rechterdeelvenster de gegevens die voor elk item worden weergegeven. Dat biedt een beter overzicht van elk item in de entiteit.

![De velden in het bladerscherm wijzigen](./media/learning-case-app-customize/change-browse-fields.png)

## <a name="change-the-app-theme"></a>Het app-thema wijzigen
PowerApps biedt een reeks thema's die u in uw app kunt gebruiken, net zoals in PowerPoint. In het volgende scherm wordt het thema **Dune** toegepast, samen met een eenvoudig logo dat we in de app hebben geplakt. Dit zijn eenvoudige wijzigingen, maar ze kunnen het uiterlijk van uw app aanzienlijk verbeteren. 

![Het thema wijzigen en een logo toevoegen](./media/learning-case-app-customize/change-theme.png)

## <a name="use-a-formula-to-show-the-case-status"></a>Een formule gebruiken om de status van een case weer te geven
Een van de grootste voordelen van PowerApps is dat u geen traditionele toepassingscode hoeft te schrijven: u hoeft dus geen ontwikkelaar te zijn om apps te maken! Maar u hebt wel een manier nodig om logica in een app op te nemen en om het navigeren, filteren, sorteren en andere functionaliteit van een app te regelen. Hier komt het gebruik van formules van pas.

Als u Excel-formules hebt gebruikt, zal de manier waarop PowerApps werkt u bekend voorkomen. Stel dat de statusbalk groen moet worden als een case is afgesloten of rood als dat niet het geval is. U doet dit door het statusbesturingselement op het scherm te selecteren en de eigenschap **Fill** van dat besturingselement in te stellen voor deze formule in de formulebalk: `If(Status="Resolved", Color.Green, Color.Red)`. Dit is net zoals bij een Excel-formule, maar PowerApps-formules verwijzen naar besturingselementen en andere app-elementen in plaats van naar cellen in een werkblad. In de volgende afbeelding ziet u waar de formule wordt ingesteld, samen met het resultaat in de app.

![Formule om de status van een case weer te geven](./media/learning-case-app-customize/case-status.png)

## <a name="sort-and-filter-based-on-date"></a>Sorteren en filteren op basis van datum
In het bladerscherm kunt u met de gegenereerde app zoeken naar cases en de lijst met items in de galerie sorteren. We gaan de functionaliteit voor zoeken en sorteren verwijderen om in plaats daarvan cases op basis van een datum weer te geven. U kunt deze methoden combineren, maar we gebruiken voor deze app de op datums gebaseerde aanpak. In de volgende afbeelding ziet u de items die zijn toegevoegd:

* Een tekstlabel ("Show cases after:") zodat gebruikers weten wat ze moeten doen: **Invoegen** > **Tekst** > **Label**; wijzig de formule **Vullen** in **Wit**.
* Een datumkiezer: **Invoegen** > **Besturingselementen** > **Datumkiezer**.
* Een formule om de eigenschap **Items** van de bladergalerie te koppelen aan de datumkiezer: `Filter(Case, DatePicker1.SelectedDate < LastModifiedDateTime)`.

De datum wordt ingesteld op 20 oktober en u ziet als resultaat dat de app de cases laat zien die na deze datum zijn gemaakt. Standaard hebben alle cases in de entiteit dezelfde datum voor de laatste wijziging. U kunt er een of meer bijwerken om te zien hoe filteren werkt. Verderop in de cursus behandelen we het werken met entiteitgegevens.

![App bijgewerkt om datumkiezer te gebruiken](./media/learning-case-app-customize/date-picker.png)

## <a name="show-total-number-of-cases"></a>Totaal aantal cases weergeven
We hebben hier heel wat zaken behandeld, maar we zijn bijna klaar met de aanpassingen. Het laatste wat we in dit onderwerp gaan doen is labels toevoegen die twee getallen bevatten: het totaal aantal cases en het aantal cases dat overeenkomt met ons datumfilter.

![Totaal aantal en gefilterde cases weergeven](./media/learning-case-app-customize/number-cases.png)

De video laat zien hoe de twee labels worden toegevoegd, maar hier zijn de basisbeginselen met betrekking tot de eigenschappen die we voor elk label instellen:

* **Uitlijnen** = `Center`
* **Breedte** = `Parent.Width/2`
* Linkervak **Tekst** = `"Total cases: " & CountRows(Case)`. Dit omvat alle cases die zich in de entiteit bevinden. 
* Rechtervak **Tekst** = `Filtered cases: " & CountRows(BrowseGallery1.AllItems)`. Dit omvat alleen de cases die overeenkomen met het datumfilter.

Daarmee zijn de aanpassingen van de app achter de rug. In het volgende onderwerp gaan we een gegevensbron en een stroom toevoegen en krijgt u de voltooide app te zien.

