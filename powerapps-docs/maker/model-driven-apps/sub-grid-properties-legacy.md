---
title: Subrastereigenschappen voor hoofdformulieren voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Verkrijg inzicht in de subrastereigenschappen voor hoofdformulieren
Keywords: Main form; Sub-Grid properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/07/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 82892cd3-3436-4677-b96b-f2ccd0a4f078
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="sub-grid-properties-for-model-driven-app-main-forms-overview"></a>Overzicht van subrastereigenschappen voor hoofdformulieren voor modelgestuurde apps

U kunt een subraster op een formulier configureren om een lijst met records of een grafiek weer te geven. Selecteer **Alleen grafiek weergeven** op het tabblad **Weergave** om een grafiek in plaats van een lijst weer te geven.  

U opent **Eigenschappen van subraster** via de PowerApps-site. 
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**. 

3.  In de lijst met formulieren opent u het formulier van het type **Hoofd**. Vervolgens selecteert u op het tabblad **Invoegen** de optie **Subraster** om eigenschappen van subraster weer te geven.

    ![eigenschappen van subraster](media/sub-grid-properties.png)
  
|Tab|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Weergave**|**Name**|**Vereist**: De unieke naam voor het subraster die wordt gebruikt wanneer ernaar wordt verwezen in scripts. De naam mag alleen alfanumerieke tekens en onderstrepingstekens bevatten.|  
||**Label**|**Vereist**: Het lokaliseerbare label voor het subraster dat zichtbaar is voor gebruikers.|  
||**Label in het formulier weergeven**|Of het label op het formulier moet worden weergegeven. Dit is vereist als u **Zoekvak weergeven** inschakelt. U kunt ook besluiten de koptekstkleur van het paneel te gebruiken.|  
||**Records**|Kies uit twee opties:<br /><br /> - **Alleen gerelateerde records**: Het subraster geeft alleen records weer die zijn gerelateerd aan de huidige record.<br />- **Alle recordtypen**: Het subraster geeft alleen records weer die door de standaardweergave zijn gefilterd of, als de weergaveselectie is ingeschakeld, de weergaven die de gebruiker kiest.<br /><br /> De optie die u kiest heeft gevolgen voor het gedrag van het besturingselement Lijst weergeven. Meer informatie: [Lijstgedrag weergeven](sub-grid-properties-legacy.md#BKMK_ShowListControlBehavior)|  
||**Entiteit**|Afhankelijk van de optie die u kiest voor **Records** geeft deze lijst een van de volgende opties weer:<br /><br /> - **Alleen gerelateerde records**: Een lijst met entiteiten die verwant zijn aan deze entiteit met de naam van het opzoekveld op die entiteit die de relatie tussen haakjes definieert.<br />- **Alle recordtypen**: Een lijst van alle entiteiten.|  
||**Standaardweergave**|Selecteer de weergave die standaard wordt toegepast. Als u geen andere weergave inschakelt met behulp van de eigenschap **Weergaveselectie**. Dit zal de enige weergave zijn.<br /><br /> Gebruik de knop **Bewerken** om de standaardweergave voor bewerking te openen. Gebruik de knop **Nieuw** om een nieuwe weergave te maken om voor dit subraster te gebruiken.|  
||**Zoekvak weergeven**|Geef het zoekvak weer. Als deze optie wordt gekozen, is de optie **Label op het formulier weergeven** vereist.|  
||**Index weergeven**|Alleen formulieren die de [Klassieke formulieren](main-form-presentations.md#classic-forms) gebruiken, ondersteunen weergave-index.<br /><br /> Schakel dit selectievakje in als u de alfabetische index bij de lijst wilt weergeven. Hiermee kunt u rechtstreeks naar records met een specifieke beginletter of een specifiek begincijfer gaan.|  
||**Weergave selecteren**|U hebt drie opties:<br /><br /> - **Uit**: Alleen de standaardweergave kan worden gebruikt.<br />- **Alle weergaven weergeven**: Sta mensen toe elke weergave te kiezen.<br />- **Geselecteerde weergaven weergeven**: Gebruik de Ctrl-toets om te selecteren welke beschikbare weergaven worden weergegeven.|  
||**Standaardgrafiek**|Selecteer welke grafiek wordt weergegeven als **Alleen grafiek weergeven** is geselecteerd.|  
||**Alleen grafiek weergeven**|In plaats van een lijst met records wordt een grafiek weergegeven.|  
||**Grafiekselectie weergeven**|Als **Alleen grafiek weergeven** is ingeschakeld, kunnen mensen verschillende grafieken kiezen.|  
||**Beschikbaarheid**|Geef op of de sectie beschikbaar moet zijn op telefoon.|
|**Opmaak**|**Indeling**|**Selecteer het aantal kolommen dat het besturingselement in beslag neemt**.<br /><br /> Als de sectie die het subraster bevat meer dan één kolom heeft, kunt u het veld zo instellen dat het evenveel kolommen bezet als sectie.|  
||**Rij-indeling**|**Aantal rijen** bepaalt hoeveel records op een pagina van een subraster worden weergegeven.<br /><br /> Als **Vouw automatisch uit om de beschikbare ruimte te gebruiken** wordt gekozen, is er plaats voor twee records op het formulier en zal de ruimte worden vergroot als het aantal records stijgt. Als het aantal het **Aantal rijen** overschrijdt, kunnen mensen naar aanvullende pagina's navigeren om de records weer te geven.<br /><br /> Als **Vouw automatisch uit om de beschikbare ruimte te gebruiken** niet wordt gekozen, zal het formulier ruimte bieden voor het aantal records dat is gedefinieerd via **Aantal rijen** en kunnen mensen naar aanvullende pagina's navigeren om de aanvullende records weer te geven.|  
|**Besturingselementen**|**Besturingselementen**|Kies besturingselementen die u wilt toevoegen en selecteer het keuzerondje voor Web, Telefoon of Tablet.|
  
 In formulieren die de [Klassieke formulieren](main-form-presentations.md#classic-forms) gebruiken, waren acties die op een subraster werden uitgevoerd beschikbaar in het lint. Ontwikkelaars kunnen het gedrag voor deze acties aanpassen of aanvullende acties toevoegen door het lint aan te passen.  
  
 In formulieren die de [Bijgewerkte formulieren](main-form-presentations.md#updated-forms) gebruiken, worden acties voor subrasters in de buurt van het subraster geplaatst, zodat ze gemakkelijker toegankelijk zijn. De opdrachtbalk staat echter niet toe aangepaste acties toe te voegen. Ontwikkelaars kunnen het lint bewerken om acties voor de resterende drie acties te wijzigen: lijst weergeven, record toevoegen en record verwijderen.  
  

## <a name="show-list-behavior"></a>Geef lijstgedrag weer  
 Bij het weergeven van een lijst in formulieren met de [Bijgewerkte formulieren](main-form-presentations.md#updated-forms), geeft elk subraster de knop **Weergave openen** ![Knop Weergave openen](media/crm-itpro-cust-openview.PNG "Knop Weergave openen") in de rechterbovenhoek weer wanneer de entiteit ook als een van de entiteiten in het navigatiegebied van de formuliereneditor wordt weergegeven. Door deze knop te kiezen wordt de weergave geopend. Het gedrag verandert afhankelijk van de optie die voor de eigenschap **Records** wordt gekozen.  
  
 Als u **Alleen gerelateerde records** selecteert, wordt de weergave geopend met behulp van een van de gekoppelde weergaven in hetzelfde venster. Om naar het formulier terug te keren, gebruikt u de knop Vorige of kiest u de waarde van het huidige primairenaamrecord in de navigatiebalk.  
  
 Als u **Alle recordtypen** selecteert, wordt de weergave in een nieuw venster geopend.  

## <a name="add-record-behavior"></a>Voeg recordgedrag toe  
 Bij het weergeven van een lijst in formulieren met de [Bijgewerkte formulieren](main-form-presentations.md#updated-forms), geeft elk subraster een knop **Record toevoegen** ![Knop Record toevoegen](media/crm-itpro-cust-subgridadd.PNG "Knop Record toevoegen") rechtsboven in het subraster weer. Door deze knop te kiezen kunt u een record toevoegen. Dit gedrag verandert afhankelijk van de optie die voor de eigenschap **Records** wordt gekozen en of de zoekactie voor activiteitenoverzichten is.  
  
 Als u **Alleen gerelateerde records** selecteert, is het standaardgedrag het gedrag om bestaande records toe te voegen. Personen zien een inlinezoekopdracht om eerst een bestaande recordlijst te zoeken. Hiermee wordt voorkomen dat dubbele records worden gemaakt.  Als ze geen bestaande record kunnen vinden, kunnen ze de optie **Nieuw** kiezen. Wanneer een nieuwe record wordt gemaakt, worden eventuele veldtoewijzingen die in de relatie zijn gedefinieerd toegepast. Meer informatie: [Entiteitsvelden toewijzen](../common-data-service/map-entity-fields.md)   
  
 Wanneer u **Alle recordtypen** selecteert, wordt er als standaardgedrag een nieuwe record toegevoegd. Het snelle-invoerformulier wordt weergegeven als de doelentiteit er een heeft. Als dit niet het geval is, worden het hoofdformulier van de standaardentiteit weergegeven.  
  
 Als het subraster activiteiten weergeeft, moeten personen eerst het type activiteit kiezen en dan zullen ze het gedrag "nieuwe record toevoegen" zien.  
  
## <a name="delete-record-behavior"></a>Recordgedrag verwijderen  
 Wanneer u een record selecteert in een subraster, verschijnt de knop **Verwijderen** ![Sublijst pictogram verwijderen](media/crm-itpro-cust-subgriddelete.PNG "Sublijst pictogram verwijderen") rechts van de rij. Het gedrag van deze verwijderactie kan verschillen afhankelijk van het type relatie met de huidige entiteit.  
  
 Wanneer het subraster een 1-N (een-op-veel)-relatie gebruikt, geeft het normale recordverwijdergedrag een bevestigingsdialoogvenster weer voordat de record wordt verwijderd.  
  
 Wanneer het subraster een N:N (veel-op-veel)-relatie gebruikt, wordt de record in de relatie (of snijd)-entiteit gerelateerd aan twee records verwijderd zonder bevestiging en wordt de record niet meer weergegeven in het subraster. Maar de record die werd weergegeven, wordt niet verwijderd.  

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
