---
title: Kolommen in weergaven voor modelgestuurde apps kiezen en configureren in PowerApps | MicrosoftDocs
description: Weergaven selecteren en configureren voor uw app
keywords: ''
ms.date: 06/11/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 31bfcf18-58c3-491c-91b5-f9b0f5424852
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 25
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-choose-and-configure-columns-in-model-driven-app-views"></a>Zelfstudie: Kolommen in weergaven voor modelgestuurde apps kiezen en configureren

<a name="BKMK_ChooseAndConfigureColumns"></a>   

 Samen met de filtercriteria zijn de kolommen die zichtbaar zijn in een PowerApps-weergave van groot belang voor de waarde die door de weergave wordt verstrekt. In deze zelfstudie maakt of bewerkt u weergaven door de volgende taken uit te voeren:  

-   [De weergave-editor openen](choose-and-configure-columns.md#open-the-view-editor)  
   
-   [Kolommen toevoegen](choose-and-configure-columns.md#BKMK_AddColumns)  
  
-   [Kolommen verwijderen](choose-and-configure-columns.md#BKMK_RemoveColumns)  
  
-   [De kolombreedte wijzigen](choose-and-configure-columns.md#BKMK_ChangeColumnWidth)  
  
-   [Een kolom verplaatsen](choose-and-configure-columns.md#BKMK_MoveAColumns)  
  
-   [Aanwezigheid voor een kolom in- of uitschakelen](choose-and-configure-columns.md#BKMK_EnableOrDisablePresence)  
  
-   [Zoekkolommen toevoegen](choose-and-configure-columns.md#BKMK_AddFindColumns)  

### <a name="open-the-view-editor"></a>De weergave-editor openen

1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](../model-driven-apps/media/model-driven-switch.png)

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Weergaven**. 

    > [!div class="mx-imgBorder"] 
    > ![Weergaven](media/available-views.png)

3. Selecteer een bestaande weergave om deze te openen of selecteer op de werkbalk **Weergave toevoegen**. 

<a name="BKMK_AddColumns"></a>   
### <a name="add-columns"></a>Kolommen toevoegen  
 U kunt kolommen opnemen van de huidige entiteit of van een van de gerelateerde entiteiten die een 1:N-entiteitsrelatie met de huidige entiteit hebben.  
  
 Zo kunt u bijvoorbeeld de eigenaar van een entiteit die eigendom van een gebruiker is weergeven in een kolom. U kunt het veld **Eigenaar** van de huidige entiteit kiezen om de naam van de eigenaar weer te geven. Dit wordt weergegeven als een koppeling voor het openen van de record **Gebruiker** voor degene die de eigenaar is. In dit geval hebt u ook de optie voor [Aanwezigheid voor een kolom in- of uitschakelen](choose-and-configure-columns.md#BKMK_EnableOrDisablePresence).  
  
 Als u het telefoonnummer wilt weergeven voor de eigenaar van de record, moet u **Gebruiker die eigenaar is (Gebruiker)** selecteren in de vervolgkeuzelijst **Recordtype** en vervolgens het veld **Telefoonnummer 1** selecteren.  
  
#### <a name="add-columns-to-views"></a>Kolommen aan weergaven toevoegen  
  
1.  Selecteer **Kolommen toevoegen** tijdens het maken en bewerken van weergaven. 

    > [!div class="mx-imgBorder"] 
    > ![Kolommen toevoegen in weergave-editor](media/view-editor.png)

    Het dialoogvenster **Kolommen toevoegen** wordt weergegeven.

    > [!div class="mx-imgBorder"] 
    > ![Kolommen toevoegen](media/add-columns.png)
  
2.  Selecteer het **Recordtype** als u velden uit verwante entiteiten wilt opnemen.  
  
3.  U kunt meerdere velden selecteren, zelfs van verwante entiteiten.  
  
4.  Wanneer u de gewenste velden hebt geselecteerd, selecteert u **OK** om het dialoogvenster **Kolommen toevoegen** te sluiten.  
  
 Door kolommen toe te voegen, maakt u de weergave breder. Als de breedte van de weergave de beschikbare ruimte overschrijdt voor weergave op de pagina, stellen horizontale schuifbalken gebruikers in staat om te schuiven en de verborgen kolommen te bekijken.  
  
> [!TIP]
>  Als uw weergave filtert op gegevens voor een bepaald veld zodat alleen de records met een bepaalde waarde worden weergegeven, neemt u die kolom niet op in de weergave. Als u bijvoorbeeld alleen actieve records weergeeft, neemt u de statuskolom niet op in de weergave. Geef de weergave in plaats daarvan een zodanige naam dat alle records in de weergave actief zijn.  
  
> [!NOTE]
>  Als u kolommen toevoegt aan opzoekweergaven voor bijgewerkte entiteiten, worden alleen de eerste drie kolommen weergegeven.  
  
<a name="BKMK_RemoveColumns"></a>   
### <a name="remove-columns"></a>Kolommen verwijderen  
  
1.  Terwijl u weergaven maakt en bewerkt, kiest u de kolom die u wilt verwijderen.  
  
2.  Selecteer in het gebied **Algemene taken** de optie **Verwijderen**.  
  
3.  Selecteer **OK** in het bevestigingsbericht.  
  
<a name="BKMK_ChangeColumnWidth"></a>   
### <a name="change-column-width"></a>De kolombreedte wijzigen  
  
1.  Terwijl u weergaven maakt en bewerkt, kiest u de kolom die u wilt wijzigen.  
  
2.  In het gebied **Algemene taken** selecteert u **Eigenschappen wijzigen**.  
  
3.  In het dialoogvenster **Kolomeigenschappen wijzigen** selecteert u een optie om de kolombreedte in te stellen en vervolgens selecteert u **OK**.  
  
<a name="BKMK_MoveAColumns"></a>   
### <a name="move-a-column"></a>Een kolom verplaatsen  
  
1.  Terwijl u weergaven maakt en bewerkt, kiest u de kolom die u wilt verplaatsen.  
  
2.  Gebruik in het gebied **Algemene taken** de pijlen om de kolom naar links of naar rechts te verplaatsen.  
  
<a name="BKMK_EnableOrDisablePresence"></a>   
### <a name="enable-or-disable-presence-for-a-column"></a>Aanwezigheid voor een kolom in- of uitschakelen  
 Als de volgende voorwaarden waar zijn, kunnen gebruikers in lijsten een onlineaanwezigheidbesturingselement voor Skype voor Bedrijven te zien krijgen dat alleen wordt weergegeven als de persoon beschikbaar is, zodat gebruikers met hen kunnen communiceren via chatberichten:  
  
-   Mensen gebruiken Edge of Internet Explorer.  
  
-   De persoon heeft Skype voor Bedrijven geïnstalleerd.  
  
-   Mensen hebben Microsoft ActiveX ingeschakeld in Internet Explorer.  
  
-   Uw organisatie heeft aanwezigheid ingeschakeld voor het systeem in de systeeminstellingen.  
  
 Het aanwezigheidsbesturingselement en de instelling voor het inschakelen hiervan zijn alleen beschikbaar voor kolommen met primaire velden voor entiteiten waarvoor e-mail is ingeschakeld (gebruikers, contactpersonen, verkoopkansen, leads of aangepaste entiteiten).  
  
#### <a name="enable-or-disable-skype-for-business-presence-for-a-column"></a>Aanwezigheid Skype voor Bedrijven voor een kolom in- of uitschakelen  
  
1.  Terwijl u weergaven maakt en bewerkt, kiest u de kolom die u wilt wijzigen.  
  
2.  In het gebied **Algemene taken** selecteert u **Eigenschappen wijzigen**.  
  
3.  Selecteer in het dialoogvenster **Kolomeigenschappen wijzigen** de optie **Aanwezigheid inschakelen voor deze kolom** of hef de selectie op en selecteer vervolgens **OK**.  
  
<a name="BKMK_AddFindColumns"></a>   
### <a name="add-find-columns"></a>Zoekkolommen toevoegen  
 Zoekkolommen zijn de kolommen die door de toepassing worden doorzocht wanneer gebruikers het tekstvak **Zoeken naar records** gebruikten dat wordt weergegeven voor lijsten of als de mogelijkheid bestaat om records te doorzoeken voor een entiteit in de toepassing, zoals wanneer gebruikers een record zoeken voor een opzoekveld.  
  
1.  Open een weergave voor **Snel zoeken**. Raadpleeg voor meer informatie over de weergave Snel zoeken [Typen weergaven](create-edit-views.md#types-of-views).  
  
2.  Selecteer **Zoekkolommen toevoegen** om het dialoogvenster te openen.  
  
3.  Selecteer de velden die de gegevens bevatten waarnaar u wilt zoeken.  
  
4.  Selecteer **OK** om het dialoogvenster **Zoekkolommen toevoegen** te sluiten.  

## <a name="community-tools"></a>Community-hulpprogramma's

**View Layout Replicator** en **View Designer** zijn hulpprogramma's die door de XrmToolbox-community zijn ontwikkeld voor Dynamics 365 Customer Engagement. Raadpleeg het onderwerp [Ontwikkelaarhulpmiddelen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) voor door de community ontwikkelde hulpprogramma's.

> [!NOTE]
> De community-hulpprogramma's zijn geen product van Microsoft Dynamics en Microsoft biedt geen ondersteuning voor de community-hulpprogramma's. Als u vragen hebt over het hulpprogramma, raadpleegt u de uitgever hiervan. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com). 

## <a name="next-steps"></a>Volgende stappen
[Weergaven maken of bewerken](create-edit-views.md)
