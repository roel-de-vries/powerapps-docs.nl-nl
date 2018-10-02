---
title: iFrame-eigenschappen voor hoofdformulieren voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Verkrijg inzicht in de iFrame-eigenschappen voor hoofdformulieren
Keywords: Main form; iFrame properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 1b7e6a0c-18a9-47e2-aa7d-0cffb8c93b19
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="iframe-properties-for-model-driven-app-main-forms"></a>iFrame-eigenschappen voor hoofdformulieren voor modelgestuurde apps

U kunt iFrames toevoegen aan een formulier om inhoud van een andere website in een formulier te integreren. 

Ga als volgt te werk om iFrame-eigenschappen weer te geven.

1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](../model-driven-apps/media/model-driven-switch.png)

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**. 

3. In de lijst met formulieren opent u een formulier van het type **Hoofd**. Vervolgens selecteert u op het tabblad **Invoegen** IFRAME om Eigenschappen van IFRAME weer te geven.

![iframe-eigenschappen](media/iframe-properties.png)


> [!NOTE]
> Formulieren zijn niet ontworpen om binnen een iFrame te worden weergegeven.  
  
|Tab|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Algemeen**|**Name**|**Vereist**: Een unieke naam voor de iFrame. De naam mag alleen alfanumerieke tekens en onderstrepingstekens bevatten.|  
||**URL**|**Vereist**: De URL voor de pagina die wordt weergegeven in de iFrame.|  
||**Recordobject-typecode en unieke id's als parameters doorgeven**|Gegevens over de organisatie, de gebruiker en de record kunnen worden doorgegeven aan de iFrame. Meer informatie: [Parameters aan iFrames doorgeven](iframe-properties-legacy.md#BKMK_PassParametersToIFRAMEs)|  
||**Label**|**Vereist**: Een label om weer te geven voor de iFrame.|  
||**Bijschrift op het formulier weergeven**|Of het label moet worden weergegeven.|  
||**Het uitvoeren van scripts tussen frames beperken, indien ondersteund**|Het wordt beschouwd als een beveiligingsrisico als interactie wordt toegestaan tussen pagina's van een andere website en de Dynamics 365-toepassing met behulp van scripts. Gebruik deze optie om het uitvoeren van scripts tussen frames voor pagina's die u niet beheert te beperken.<br /><br />|  
||**Standaard zichtbaar**|Weergave van de iFrame is optioneel en kan worden beheerd met behulp van scripts. Meer informatie: [Zichtbaarheidsopties](visibility-options-legacy.md)|
||**Inschakelen voor mobiel**|Schakel het selectievakje in om de iFrame voor mobiel in te schakelen.|  
|**Opmaak**|**Selecteer het aantal kolommen dat het besturingselement in beslag neemt**|Als de sectie die de iFrame bevat meer dan één kolom heeft, kunt u het veld zo instellen dat het evenveel kolommen bezet als sectie.|  
||**Selecteer het aantal rijen dat het besturingselement in beslag neemt**|U kunt de hoogte van de iFrame beheren door een aantal rijen op te geven dat het besturingselement in beslag neemt.|  
||**Vouw automatisch uit om de beschikbare ruimte te gebruiken**|In plaats van de hoogte in te stellen met een aantal rijen, kunt u toestaan dat de iFramehoogte wordt uitgevouwen tot de beschikbare ruimte.|  
||**Selecteer het schuiftype voor de iFrame**|U hebt drie opties:<br /><br /> - **Zo nodig**: Schuifbalken weergeven als de omvang van de iFrame groter is dan de beschikbare ruimte.<br />- **Altijd**: Altijd schuifbalken weergeven.<br />- **Nooit**: Nooit schuifbalken weergeven.|  
||**Rand weergeven**|Geef een rand om de iFrame weer.|  
|**Afhankelijkheden**|**Afhankelijke velden**|Er kan interactie bestaan tussen een iFrame en velden in het formulier dat een script gebruikt. Als een veld wordt verwijderd uit het formulier, dan kan het script in de iFrame worden onderbroken. Voeg velden toe waaraan door scripts gerefereerd wordt in de iFrames aan de **Afhankelijke velden** zodat ze niet per ongeluk kunnen worden verwijderd.|  
  
## <a name="pass-parameters-to-iframes"></a>Geef parameters door aan iFrames  
 De gegevens over de record kunnen worden doorgegeven door de optie **Geef de typecode van het recordobject en de unieke id's als parameters door** in te schakelen. De doorgegeven waarden zijn:  
  
|Parameter|Beschrijving|  
|---------------|-----------------|  
|`orglcid`|De standaardtaal-LCID van de Organisatie.|  
|`orgname`|De naam van de organisatie.|  
|`userlcid`|De voorkeurstaal-LCID van de gebruiker|  
|`type`|De code van het entiteittype. Deze waarde kan voor aangepaste entiteiten in andere organisaties verschillend zijn. Gebruik in plaats daarvan `typename`.|  
|`typename`|De naam van het entiteittype.|  
|`id`|De id-waarde van de record. Deze parameter heeft pas een waarde als de entiteitrecord wordt opgeslagen.|  

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
