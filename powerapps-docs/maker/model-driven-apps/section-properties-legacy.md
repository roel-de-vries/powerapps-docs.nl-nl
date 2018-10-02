---
title: Sectie-eigenschappen voor hoofdformulieren voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Inzicht in de sectie-eigenschappen voor een hoofdformulier
Keywords: Main form; Section properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 2d3af6e9-e8a4-4129-b708-383b2740c015
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-form-section-properties"></a>Sectie-eigenschappen voor formulieren voor modelgestuurde apps

 Een sectie in een formulier neemt de ruimte in beslag die beschikbaar is in een tabbladkolom. Secties hebben een label dat kan worden weergegeven en een regel kan onder het label worden weergegeven.  
  
 Secties kunnen maximaal 4 kolommen hebben en bevatten opties om weer te geven hoe labels voor velden in de sectie worden weergegeven.  
  
 Kop- en voetteksten zijn vergelijkbaar met secties maar kunnen niet worden verwijderd. Als ze niets bevatten, worden ze niet weergegeven. 

U kunt **Eigenschappen van sectie** openen via de PowerApps-site. 
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**. 

3.  In de lijst met formulieren opent u het formulier van het type **Hoofd**. Dubbelklik vervolgens in een van de secties om de sectie-eigenschappen weer te geven. 

    ![sectie-eigenschappen](media/section-properties.png)
  
|Tabblad|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Weergave**|**Name**|**Vereist**: De unieke naam voor de sectie die wordt gebruikt wanneer ernaar wordt verwezen in scripts. De naam mag alleen alfanumerieke tekens en onderstrepingstekens bevatten.|  
||**Label**|**Vereist**: Het lokaliseerbare label voor de sectie die zichtbaar is voor gebruikers.|  
||**Geef het label van deze sectie weer op het formulier**|Secties worden vaak gebruikt zonder labels om de indeling van de velden daarin te beheren.|  
||**Geef een regel weer boven aan de sectie**|Met een regel boven aan een sectie kan de indeling van het formulier worden verdeeld.|  
||**Breedte van het veldlabel**|**Vereist**: Stel een waarde in tussen 50 en 250 om de ruimte tussen veldlabels te specificeren.<br /><br /> Elementen van kop- en voetteksten hebben ook deze eigenschap.|  
||**Zichtbaarheid**|Weergave van de sectie is optioneel en kan worden beheerd met behulp van scripts. Meer informatie: [Zichtbaarheidsopties](visibility-options-legacy.md)|  
||**Beschikbaarheid**|Geef op of het tabblad beschikbaar moet zijn op de telefoon.|  
||**Het tabblad op het formulier blokkeren**|Hierdoor wordt voorkomen dat de sectie per ongeluk wordt verwijderd en dat personen de inhoud verwijderen.<br /><br /> Door een sectie te verwijderen, wordt niet alleen de sectie verwijderd, maar ook de velden daarbinnen.<br /><br /> Iemand die deze sectie wil verwijderen, moet deze instelling wijzigen alvorens de sectie te verwijderen.|  
|**Opmaak**<br /><br /> Onderdelen van kop- en voetteksten hebben ook deze eigenschap.|**Indeling**|Specificeer maximaal vier kolommen in de sectie.|  
||**Uitlijning van veldlabels**|Labels voor velden in de sectie kunnen links, rechts of in het midden worden uitgelijnd.|  
||**Positie van veldlabels**|Labels voor velden in de sectie kunt aan de zijkant of boven aan de velden worden geplaatst.|  


Een nieuw type sectie met de naam **verwijzingenpaneel** kan ook worden toegevoegd. Een verwijzingenpaneel is een sectie met één kolom. U kunt subrasters, besturingselementen voor snelle weergave of het besturingselement Zoeken in Knowledge Base invoegen in een sectie Verwijzingenpaneel. Elk besturingselement dat u in het verwijzingenpaneel hebt toegevoegd, wordt bij uitvoering in het paneel weergegeven als verticaal tabblad. U kunt de verschillende besturingselementen slepen en neerzetten in de sectie Verwijzingenpaneel. Het standaardtabblad tijdens runtime is het eerste besturingselement dat in het verwijzingenpaneel is toegevoegd. De andere tabbladen worden weergegeven in de volgorde waarin ze zijn toegevoegd in de formuliereneditor. Als u een tabblad wilt verwijderen, gebruikt u de toets Delete op het toetsenbord.  
  
Als u een verwijzingpaneel invoegt, wordt dit standaard als laatste sectie toegevoegd aan het tabblad. U kunt slechts één verwijzingenpaneel per formulier toevoegen.  
  
> [!IMPORTANT]
>  Standaard is de sectie Verwijzingenpaneel vergrendeld in deze standaardformulieren: Aanvragen, Accounts en Contactpersonen. Als u de sectie wilt verwijderen of wijzigen, moet u deze ontgrendelen. 

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
