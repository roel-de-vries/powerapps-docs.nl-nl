---
title: Formulieren voor snelle invoer maken of bewerken voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Informatie over maken of bewerken van een formulier voor snelle invoer
ms.custom: ''
ms.date: 05/23/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 68ca9059-cc5a-45e7-88bd-cc57186bbb48
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-model-driven-app-quick-create-forms-for-a-streamlined-data-entry-experience"></a>Formulieren voor snelle invoer voor modelgestuurde apps maken of bewerken voor een gestroomlijnde gegevensinvoerervaring

In dit onderwerp maakt en bewerkt u een formulier voor snelle invoer.

 Met formulieren voor snelle invoer kunt u in uw app genieten van een gestroomlijnde gegevensinvoer met volledige ondersteuning voor logica gedefinieerd door formulierscripts en bedrijfsregels. In een modelgestuurde app in PowerApps verschijnen formulieren voor snelle invoer wanneer u de knop **Maken** selecteert in de navigatiebalk of wanneer u **+ Nieuw** kiest als u een nieuwe record maakt vanuit een opzoekactie of een subraster.
  
 De mobiele apps voor Dynamics 365 Customer Engagement gebruiken formulieren voor snelle invoer voor het maken van nieuwe records. Als voor een entiteit al een formulier voor snelle invoer is geconfigureerd, gebruiken de mobiele apps dat formulier. Als voor een entiteit geen formulier voor snelle invoer is geconfigureerd, genereert PowerApps een formulier voor snelle invoer voor het maken van records in de mobiele apps op basis van de hoofdformulierdefinitie.  
  
<a name="BKMK_QuickCreateFormEntities"></a>   
## <a name="entities-with-quick-create-forms"></a>Entiteiten met formulieren voor snelle invoer  
 Standaard bevatten alleen de volgende systeementiteiten formulieren voor snelle invoer.  
  
|||||  
|-|-|-|-|  
|Account|Campagnerespons|Aanvraag|Concurrent|  
|Contactpersoon|Potentiële klant|Kans||  
  
Hoewel u formulieren voor snelle invoer kunt maken voor systeemactiviteitsentiteiten, met uitzondering van de afspraakentiteit, bieden deze geen ondersteuning voor formulieren voor snelle invoer. Met de versie van Dynamics 365, versie 9.0, bevat de afspraakentiteit een formulier voor snelle invoer om te gebruiken in de Unified Interface. Momenteel wordt de optie om het formulier voor snelle invoer uit te schakelen voor de afspraakentiteit, niet ondersteund. Alle andere [bijgewerkte entiteiten](create-design-forms.md) en alle aangepaste entiteiten kunnen worden ingeschakeld om deze formulieren te ondersteunen door **Snel maken toestaan** te selecteren in de entiteitdefinitie en een formulier voor snelle invoer te maken voor de entiteit. 

U kunt aangepaste activiteitsentiteiten inschakelen om formulieren voor snelle invoer te ondersteunen en u kunt formulieren voor snelle invoer voor die entiteiten maken. Het formulier voor snelle invoer voor aangepaste activiteitsentiteiten wordt echter niet gebruikt wanneer mensen **Maken** op de navigatiebalk selecteren. Deze formulieren voor snelle invoer kunnen alleen worden gebruikt wanneer men een nieuwe record voor een subraster toevoegt die de specifieke aangepaste activiteitsentiteit weergeeft.  
  
<a name="BKMK_CreateQuickCreate"></a>   
## <a name="create-a-quick-create-form"></a>Een formulier voor snelle invoer maken  
 Hoewel u meerdere formulieren voor snelle invoer kunt definiëren, kan er maar een formulieer voor snelle invoer door iedereen worden gebruikt. Het formulier dat iedereen zal gebruiken wordt is ingesteld met de formuliervolgorde. Formulieren voor snelle invoer kunnen niet worden toegewezen aan beveiligingsrollen en bieden niet de de mogelijkheid voor de gebruiker om van formulieren te wisselen.  
  
> [!NOTE]
>  De entiteit moet de optie **Snel maken toestaan** hebben ingeschakeld zodat het formulier voor snelle invoer wordt weergegeven. 
  
### <a name="how-to-create-a-quick-create-form"></a>Een formulier voor snelle invoer maken  
  
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

> [!IMPORTANT]
> Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**.  

3.  Selecteer **Formulier toevoegen** > **Formulier voor snelle invoer** op de werkbalk.  
  
4.  In de formulierontwerper sleept u de gewenste velden van **Veldverkenner** naar de secties in het formulier.  
  
5.  Als u klaar bent, kiest u **Opslaan**.  
  
6.  Selecteer **Publiceren** om het nieuwe formulier in de toepassing te bekijken.  
  
<a name="BKMK_EditQuickCreate"></a>   
## <a name="edit-a-quick-create-form"></a>Een formulier voor snelle invoer bewerken  
 Terwijl formulieren voor snelle invoer formulierscripts en bedrijfsregels ondersteunen, verschilt hun doel van hoofdformulieren en ondersteunen ze niet alle mogelijkheden van hoofdformulieren. Formulieren voor snelle invoer hebben een sectie met drie kolommen. U kunt geen extra secties of kolommen toevoegen.  
  
 De volgende besturingselementen kunnen niet worden toegevoegd om formulieren voor snelle invoer te maken:  
  
-   Subrasters  
  
-   Snelle-weergaveformulieren  
  
-   Webresources  
  
-   iFrames  
  
-   Opmerkingen  
  
-   Bing Kaarten  
  
Als u een samengesteld veld toevoegt aan een formulier voor snelle invoer, dan wordt dit weergegeven als afzonderlijke velden.  
  
### <a name="to-edit-a-quick-create-form"></a>Een formulier voor snelle invoer bewerken  
  
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

> [!IMPORTANT]
> Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment).    
  
2. Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**.    

3. Selecteer in de formulierlijst een formulier waarvoor **Formuliertype** is ingesteld op **Snelle invoer**.  
  
3.  Sleep welk veld dan ook van de **Veldverkenner** in de secties in het formulier.  
  
     Bekijk [Gebeurtenis-handlers configureren](configure-event-handlers-legacy.md) voor informatie over het bewerken van gebeurtenis-handlers voor formulierscripts.  
  
4.  Als u klaar bent, kiest u **Opslaan**.  
  
5.  Selecteer **Publiceren** om het gewijzigde formulier in de toepassing te bekijken.  
  
### <a name="next-steps"></a>Volgende stappen  
[Overzicht van de gebruikersinterface van de formuliereneditor](form-editor-user-interface-legacy.md)
