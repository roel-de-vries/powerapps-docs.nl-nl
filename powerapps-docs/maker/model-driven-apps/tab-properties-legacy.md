---
title: Tabbladeigenschappen voor formulieren voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Verkrijg inzicht in de tabeigenschappen voor hoofdformulieren
Keywords: Tab properties; Dynamics 365; Main forms
author: matp
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: Mattp123
manager: kvivek
ms.date: 06/07/2018
ms.service: crm-online
ms.topic: article
ms.assetid: e0790865-c5a4-4e86-bce2-584af2b8ed93
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="tab-properties-for-model-driven-app-forms-overview"></a>Overzicht van tabbladeigenschappen voor formulieren voor modelgestuurde apps

 In de hoofdtekst van een formulier bieden tabbladen horizontale scheiding. Tabbladen hebben een label dat kan worden weergegeven. Als het label wordt weergegeven, kunnen tabbladen worden uitgevouwen of samengevouwen om de inhoud weer te geven of te verbergen door het label te kiezen.  
  
 Tabbladen bevatten maximaal drie kolommen en de breedte van elke kolom kan op een percentage van de totale breedte worden ingesteld. Als u een nieuw tabblad maakt, wordt elke kolom ingevuld met een sectie.  

U kunt **Tabbladeigenschappen** openen via de PowerApps-site. 
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**.  

3.  In de lijst met formulieren opent u het formulier van het type **Hoofd**. Dubbelklik vervolgens op een van de tabbladen op het canvas van het formulier om tabbladeigenschappen weer te geven.

    ![tabbladeigenschappen](media/tab-properties.png)
  
 In de volgende tabel ziet u de eigenschappen die kunnen worden ingesteld voor tabbladen op het formulier:
  
|Tab|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Weergave**|**Name**|**Vereist**: De unieke naam voor het tabblad die wordt gebruikt wanneer ernaar wordt verwezen in scripts. De naam mag alleen alfanumerieke tekens en onderstrepingstekens bevatten.|  
||**Label**|**Vereist**: Het lokaliseerbare label voor het tabblad dat zichtbaar is voor gebruikers.|  
||**Geef het label van dit tabblad weer op het formulier**|Als het label wordt weergegeven, kunnen gebruikers dit selecteren om te schakelen tussen een uitgevouwen of een samengevouwen tabblad. Kies of u het label wilt weergeven.|  
||**Dit tabblad standaard uitvouwen**|De tabbladstatus kan schakelen tussen uitgevouwen en samengevouwen met behulp van formulierscripts of wanneer een persoon het label selecteert. Kies de standaardstatus voor het tabblad.|  
||**Standaard zichtbaar**|Weergave van het tabblad is optioneel en kan worden gewijzigd met behulp van scripts. Kies of het tabblad zichtbaar wordt. Meer informatie: [Zichtbaarheidsopties](visibility-options-legacy.md)|  
||**Beschikbaarheid**|Geef op of het tabblad beschikbaar moet zijn op de telefoon.|  
|**Opmaak**|**Indeling**|Tabbladen kunnen maximaal drie kolommen hebben. Gebruik deze opties om het aantal kolommen en het percentage van de totale breedte dat ze moeten vullen in te stellen.|  
|**Gebeurtenissen**|**Formulierbibliotheken**|Geef JavaScript-webresources op die worden gebruikt in de gebeurtenishandler `TabStateChange` van het tabblad.<br /><br />|  
||**Gebeurtenishandlers**|Configureer de functies van de bibliotheken die moet worden aangevraagd voor de gebeurtenis van het tabblad `TabStateChange`. Meer informatie: [Gebeurtenishandlers configureren](configure-event-handlers-legacy.md)|  
  
## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
