---
title: Formuliereigenschappen voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Inzicht in de eigenschappen van het hoofdformulier
Keywords: Main form properties; Dynamics 365
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
ms.assetid: 4ed30bb7-dca1-4de8-80f3-842152ea921a
ms.openlocfilehash: 4aec7fd8a117257d4f21ac2f692643785fd21791
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677103"
---
# <a name="model-driven-app-form-properties"></a>Formuliereigenschappen voor modelgestuurde apps 

U hebt toegang tot **Formuliereigenschappen** in Solution Explorer. Vouw onder **Onderdelen** **Entiteiten** uit, vouw de gewenste entiteit uit en klik vervolgens op **Formulieren**. Open in de lijst met formulieren het formulier van het type **Hoofd**. Selecteer vervolgens op het tabblad **Start** de optie **Formuliereigenschappen**.

![form-properties](media/form-properties.png)

De volgende tabel bevat de formuliereigenschappen:  
  
|Tabblad|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Gebeurtenissen**|**Formulierbibliotheken**|Beheer welke JavaScript-webresources in het formulier beschikbaar zijn en de volgorde waarin ze worden geladen.|  
||**Gebeurtenis-handlers**|Configureer welke JavaScript-functies van de formulierbibliotheken worden uitgevoerd voor de `OnLoad`- en `OnSave`-formuliergebeurtenissen en de volgorde waarin ze worden uitgevoerd.|  
|**Weergave**|**Formuliernaam**|Voer een naam in die zinvol is. Deze naam wordt weergegeven voor gebruikers wanneer ze het formulier gebruiken. Als u meerdere formulieren kunt gebruiken die zijn geconfigureerd voor de entiteit, wordt deze naam gebruikt om onderscheid te maken tussen de beschikbare formulieren.|  
||**Description**|Voer een beschrijving in waarmee wordt uitgelegd hoe dit formulier verschilt van andere hoofdformulieren. Deze beschrijving wordt alleen weergegeven in de lijst met formulieren voor een entiteit in Solution Explorer.|  
||**Formulierassistent**|Schakel het selectievakje in als u de formulierassistent wilt inschakelen of het formulier standaard uitgevouwen wilt bekijken.|
||**Paginanavigatie**|U kunt ervoor kiezen navigatie-items niet weer te geven.<br /><br /> In formulieren voor bijgewerkte entiteiten betekent dit dat de waarde van de primaire naam voor het record dat momenteel wordt weergegeven, niet op de navigatiebalk verschijnt om te kunnen navigeren naar gekoppelde weergaven.<br /><br /> In formulieren met de klassieke presentatie worden de navigatieopties voor het kiezen van de gekoppelde weergaven aan de linkerkant van het formulier niet weergegeven.|  
||**Afbeelding**|Wanneer een entiteit een afbeeldingsveld heeft en de optie **Primaire afbeelding** van de entiteit is ingesteld, wordt met deze instelling het afbeeldingsveld in de kop van dit formulier weergegeven.<br /><br /> Zie [Entiteitsopties in- of uitschakelen](../common-data-service/edit-entities.md#enable-or-disable-entity-options) voor meer informatie over entiteitsopties.|  ||**Weergave**|**Stel een maximumbreedte in (in pixels)** om de breedte van het formulier te beperken. De standaardwaarde is 1900.|  
||**Weergave**|Geef hier in pixels op welke maximale breedte u voor het formulier wilt gebruiken.|
|**Parameters**|**Parameters**|Elk formulier kan met code worden geopend via een URL. De URL kan ook gegevens bevatten die kunnen worden doorgegeven aan het formulier met behulp van een querytekenreeks die wordt toegevoegd aan de URL. Querytekenreeksen zien eruit als in het volgende voorbeeld:<br />`?p_firstName=Jim&p_lastName=Daly`<br /><br /> Als veiligheidsmaatregel accepteren formulieren geen onbekende parameters voor querytekenreeksen. Gebruik deze lijst met parameters om parameters op te geven die door dit formulier moeten worden geaccepteerd om code te ondersteunen waarmee gegevens aan de formulieren worden doorgegeven met behulp van een querytekenreeks.<br /><br /> De naam en het type gegevens worden gecontroleerd en het formulier wordt niet geopend als er ongeldige parameters voor de querytekenreeks worden doorgegeven.<br /><br />**Opmerking:** de naam mag niet beginnen met een onderstrepingsteken (_) of crm\_. Deze moet beginnen met alfanumerieke tekens, gevolgd door een onderstrepingsteken (\_). Bijvoorbeeld: parameter_1 of 1_parameter. De naam mag geen afbreekstreepjes (-), dubbele punten (:), puntkomma's (;), komma's (,) of punten (.) bevatten. <br /><br />|  
|**Afhankelijkheden van niet-gebeurtenissen**|**Afhankelijke velden**|Elke gebeurtenis-handler heeft een vergelijkbare eigenschap **Afhankelijke velden** zodat alle velden die worden vereist door het script, kunnen worden geregistreerd. De afhankelijke velden kunnen door niemand worden verwijderd.<br /><br /> Sommige scripts gebruiken het formulier, maar zijn niet geconfigureerd in een gebeurtenis-handler. Scripts die vanaf de opdrachtbalk worden gestart, hebben geen plaats waar afhankelijke velden kunnen worden geregistreerd. Deze formuliereigenschap biedt een plaats waar afhankelijke velden voor deze scripts kunnen worden geregistreerd.|  

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de bijbehorende onderdelen gebruiken](use-main-form-and-components.md)