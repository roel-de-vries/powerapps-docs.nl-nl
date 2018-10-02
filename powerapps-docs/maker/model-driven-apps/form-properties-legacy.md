---
title: Formulieren voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Inzicht in de belangrijkste formuliereigenschappen
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="model-driven-app-form-properties"></a>Formuliereigenschappen voor modelgestuurde apps 

U kunt toegang krijgen tot **Formuliereigenschappen** in de oplossingsverkenner. Vouw onder **Onderdelen** achtereenvolgens **Entiteiten** en de gewenste entiteit uit en selecteer vervolgens **Formulieren**.. In de lijst met formulieren opent u het formulier van het type **Hoofd**. Selecteer vervolgens op het tabblad **Start** de optie **Formuliereigenschappen**.

![formuliereigenschappen](media/form-properties.png)

De volgende tabel geeft de formuliereigenschappen weer:  
  
|Tabblad|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Gebeurtenissen**|**Formulierbibliotheken**|Beheer welke JavaScript-websources beschikbaar zijn in het formulier en de volgorde waarin ze worden geladen.|  
||**Gebeurtenis-handlers**|Configureer welke JavaScript-functies uit de formulierbibliotheken worden uitgevoerd voor de formuliergebeurtenissen `OnLoad` en `OnSave`, en de volgorde waarin ze worden uitgevoerd.|  
|**Weergeven**|**Formuliernaam**|Voer een naam in die begrijpelijk is voor mensen. Deze naam wordt weergegeven wanneer mensen het formulier gebruiken. Als ze meerdere formulieren kunnen gebruiken die voor de entiteit zijn geconfigureerd, zullen ze deze naam gebruiken om onderscheid te maken tussen de beschikbare formulieren.|  
||**Beschrijving**|Voer een beschrijving in waarin wordt uitgelegd hoe dit formulier van andere hoofdformulieren verschilt. Deze beschrijving wordt alleen weergegeven in de lijst met formulieren voor een entiteit in de oplossingsverkenner.|  
||**Formulierassistent**|Schakel het selectievakje in als u formulierenassistent wilt inschakelen of het formulier standaard uitgevouwen wilt weergeven.|
||**Paginanavigatie**|U kunt ervoor kiezen om navigatie-items niet weer te geven.<br /><br /> In formulieren voor bijgewerkte entiteiten betekent dit dat de primaire naamwaarde voor de record die momenteel wordt weergegeven niet zal verschijnen in de navigatiebalk voor gekoppelde weergaven.<br /><br /> In formulieren met de klassieke weergave zullen de navigatieopties om gekoppelde weergaven aan de linkerkant van het formulier te kiezen niet worden weergegeven.|  
||**Afbeelding**|Wanneer een entiteit een afbeeldingsveld heeft en de optie **Primaire afbeelding** van de entiteit is ingesteld, wordt het afbeeldingsveld in de koptekst van het formulier weergegeven.<br /><br /> Zie [Entiteitopties in- of uitschakelen](../common-data-service/edit-entities.md#enable-or-disable-entity-options) voor meer informatie over entiteitopties.|  ||**Weergave**|**Voer maximale breedte (in pixels) in** om de breedte van het formulier te beperken. De standaardwaarde is 1900.|  
||**Weergave**|Voer hier in pixels de maximale breedte voor het formulier in.|
|**Parameters**|**Parameters**|Elk formulier kan worden geopend met code via een URL. De URL kan ook gegevens bevatten die naar het formulier kunnen worden doorgegeven via een querytekenreeks die is toegevoegd aan de URL. Querytekenreeksen zien eruit als dit voorbeeld:<br />`?p_firstName=Jim&p_lastName=Daly`<br /><br /> Als veiligheidsmaatregel accepteren formulieren geen onbekende queryreeksparameters. Gebruik deze parameterlijst om parameters op te geven die dit formulier moet accepteren om code te ondersteunen die gegevens doorgeeft naar de formulieren via een querytekenreeks.<br /><br /> De naam en het type gegevens worden gecontroleerd en het formulier wordt niet geopend als er ongeldige queryreeksparameters naar zijn doorgegeven.<br /><br />**Opmerking:** De naam mag niet beginnen met een onderstrepingsteken (_) of crm\_. De naam moet beginnen met alfanumerieke tekens gevolgd door een onderstrepingsteken (\_). Bijvoorbeeld, parameter_1 of 1_parameter. De naam mag geen afbreekstreepjes (-), dubbele punten (:), puntkomma's (;), komma's (,) en punten (.) bevatten. <br /><br />|  
|**Afhankelijkheden van niet-gebeurtenissen**|**Afhankelijke velden**|Elke gebeurtenis-handler heeft een vergelijkbare **Afhankelijke velden**-eigenschap zodat alle velden die in het script worden vereist kunnen worden geregistreerd. Iedereen die de afhankelijke velden probeert te verwijderen, kan dit niet doen.<br /><br /> Sommige scripts werken op het formulier maar zijn niet op een gebeurtenis-handler geconfigureerd. Scripts die van de opdrachtbalk worden uitgevoerd, hebben geen plaats waar afhankelijke velden kunnen worden geregistreerd. Deze formuliereigenschap biedt een plaats op deze scripts waar afhankelijke velden geregistreerd kunnen worden.|  

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
