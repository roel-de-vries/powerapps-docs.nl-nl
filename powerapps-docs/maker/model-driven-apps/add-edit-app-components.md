---
title: Zelfstudie om onderdelen voor modelgestuurde apps toe te voegen of te bewerken met PowerApps | MicrosoftDocs
description: Gebruik de PowerApps-appontwerper om onderdelen toe te voegen of te bewerken
keywords: ''
ms.date: 03/30/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: be93b9d7-f1c2-4ee7-8d7c-0f5c34dfa5f7
ms.author: matp
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 17
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-add-or-edit-model-driven-app-components-in-the-powerapps-app-designer"></a>Zelfstudie: Onderdelen voor modelgestuurde apps toevoegen of bewerken in de appontwerper van PowerApps

In deze zelfstudie leert u hoe u onderdelen kunt toevoegen aan en verwijderen uit een modelgestuurde app. 

Een modelgestuurde app is samengesteld uit verschillende onderdelen. U kunt twee typen onderdelen toevoegen aan een app: artefacten en entiteitsassets. In de context van de appontwerper zijn entiteiten, het dashboard en bedrijfsprocesstromen allemaal artefacten van een app. Entiteitsassets bestaan uit formulieren, weergaven, c en dashboards.  
  
De appontwerper verwijst naar bestaande metagegevens in de standaardoplossing. U kunt hiermee onderdelen maken als formulieren, weergaven, grafieken en dashboards.  
  
## <a name="app-designer-layout"></a>Indeling van de appontwerper  
 De appontwerper bestaat uit twee hoofdgebieden. Links bevindt zich het canvas, waar u apponderdelen toevoegt.  
  
![Het canvas van de appontwerper](../model-driven-apps/media/app-designer-canvas-pane.png)

 Aan de rechterkant worden tabbladen weergegeven die u kunt gebruiken om de onderdelen te selecteren en onderdeeleigenschappen in te stellen.  
 
 > [!div class="mx-imgBorder"]
 > ![Onderdelen appontwerper](../model-driven-apps/media/app-designer-canvas-components-tab.png "Onderdelen appontwerper")  
  
 Het canvas bevat gebieden voor het siteoverzicht, de bedrijfsprocesstroom, het dashboard en entiteiten. Wanneer u een dashboard of een bedrijfsprocesstroom selecteert of een siteoverzicht configureert, worden aan het canvas automatisch de entiteiten toegevoegd die worden gebruikt in deze onderdelen. Nadat de entiteiten zijn toegevoegd, hoeft u alleen nog maar elke entiteit te selecteren en hieraan de benodigde entiteitsassets zoals formulieren, weergaven en grafieken toe te voegen.
 
 U kunt **Canvas doorzoeken** gebruiken om te zoeken naar onderdelen op het canvas. Als u **Canvas doorzoeken** selecteert, wordt een nieuw zoektabblad geopend rechts van de tabbladen in het meest rechtse deelvenster.   
 
 > [!div class="mx-imgBorder"]
 > ![Optie Canvas doorzoeken](media/app-designer-search-tab.png "Canvas doorzoeken")

## <a name="open-an-app"></a>Een app openen
1. Meld u aan bij [PowerApps](https://web.powerapps.com/). 

2. Selecteer **Modelgestuurd** > **Apps** en selecteer een bestaande app of selecteer **Een app maken**. Zie [Een modelgestuurde app maken of bewerken met de appontwerper](create-edit-app.md#create-an-app) voor informatie over het maken van een app.

## <a name="add-an-artifact-entity-dashboard-or-business-process-flow"></a>Een artefact (entiteit, dashboard of bedrijfsprocesstroom) toevoegen  
 Wanneer u een dashboard of een bedrijfsprocesstroom aan een app toevoegt, worden de gebruikte entiteiten automatisch toegevoegd aan de app. Als u een entiteit toevoegt, worden de tegels voor de assets automatisch toegevoegd. Er zijn twee manieren waarop u artefacten aan het canvas van de ontwerper kunt toevoegen: met de knop **Toevoegen** ![Knop Toevoegen in de ontwerper](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") op de opdrachtbalk of de tegels op het tabblad **Onderdelen**.  
  
 Hier vindt u de stappen voor het toevoegen van een dashboard aan de app. Ga op dezelfde manier te werk als wanneer u een bedrijfsprocesstroom of entiteit toevoegt.  
  
1.  Selecteer op het canvas van de appontwerper de tegel **Dashboards**.  
  
     In het canvas van de appontwerper worden in het venster uiterst rechts de dashboards getoond die in de standaardoplossing beschikbaar zijn.  
  
    > [!TIP]
    >  U kunt ook een of meer van de volgende handelingen uitvoeren:  
    >   
    > - Selecteer de knop **Toevoegen** ![Knop Toevoegen in de ontwerper](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") en selecteer vervolgens **Dashboards**.  
    > - Selecteer op het tabblad **Onderdelen** onder **Artefacten** de optie **Dashboards**.  
  
2.  Typ in het vak **Zoeken** een paar trefwoorden voor de dashboardnaam die u zoekt.  
  
     De dashboardlijst wordt gefilterd zodat alleen resultaten worden weergegeven die overeenkomen met uw trefwoorden.  
  
3.  Als u wilt dat uw gebruikers alleen geselecteerde dashboards gebruiken, schakelt u het selectievakje in voor de dashboards die u wilt toevoegen. U kunt van de volgende typen dashboards selecteren:
    - **Klassieke dashboards** worden weergegeven in zowel de webapp als de Unified Interface-app.
    - **Interactieve dashboards** worden alleen weergegeven in de United Interface-app. Als u webapp hebt geselecteerd als clienttype voor de app, wordt de optie **Interactieve dashboards** niet weergegeven.

     Deze dashboards worden toegevoegd aan de tegel **Dashboard** op het canvas van de appontwerper. Op de tegel **Dashboard** wordt ook een telling getoond van het aantal dashboards dat u hebt toegevoegd aan de app. Als u geen dashboard selecteert, wordt **Alle** weergegeven in plaats van het dashboardaantal en zijn alle dashboards beschikbaar voor gebruikers wanneer ze de app gebruiken.  
  
     Alle entiteiten die het dashboard gebruikt, worden ook aan het gebied **Entiteitsweergave** toegevoegd. Wanneer u het dashboard Manager van klantenservice toevoegt, worden bijvoorbeeld de entiteiten Aanvraag, Recht en Wachtrij-item toegevoegd aan het gebied Entiteitsweergave. Voor elke entiteit worden de tegels voor de bijbehorende assets eveneens toegevoegd. U kunt deze tegels gebruiken om formulieren, weergaven en grafieken toe te voegen. Meer informatie:[Apponderdelen toevoegen of bewerken in de PowerApps-appontwerper](add-edit-app-components.md#bkmk_AddEntityAssets)   
  
    ![Entiteit toevoegen aan canvas van appontwerper](../model-driven-apps/media/add-entity-app-designer-canvas.png "Een entiteit toevoegen aan canvas van appontwerper")  
  
4.  Als het gewenste dashboard niet in de standaardoplossing bestaat, maakt u een dashboard door **Nieuw maken** te selecteren op het tabblad **Onderdelen** aan de rechterkant van het canvas.  
  
     > [!div class="mx-imgBorder"]
     > ![Nieuwe koppeling maken op het tabblad Onderdelen van appontwerper](../model-driven-apps/media/app-designer-components-tab-create-new.png "Nieuwe koppeling maken op het tabblad Onderdelen van de appontwerper")  
  
     De dashboardontwerper wordt geopend. Meer informatie: [Dashboards maken en bewerken](create-edit-dashboards.md)  
  
    > [!NOTE]
    > - Als u een bedrijfsprocesstroom of entiteit toevoegt, wordt met de optie **Nieuw(e) maken** de juiste ontwerper geopend. Zie [Een bedrijfsprocesstroom maken](/flow/create-business-process-flow) en [Een aangepaste entiteit maken](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-create-entity) voor meer informatie over het maken van bedrijfsprocesstromen of entiteiten.  
      
  
5.  Als u klaar bent met het toevoegen van artefacten, selecteert u **Opslaan**.  
  
<a name="bkmk_AddEntityAssets"></a>   
## <a name="add-entity-assets-forms-views-charts-or-dashboards"></a>Entiteitsassets (formulieren, weergaven, grafieken of dashboards) toevoegen  
 Als de artefacten zijn toegevoegd, kunt u beginnen met het toevoegen van entiteitsassets als formulieren, weergaven, grafieken en dashboards aan de app.
Bovendien kunt u, als u de Unified Interface-client gebruikt, ook entiteitsassets van het type dashboard toevoegen aan de app.  
  
 In dit gedeelte worden de stappen voor het toevoegen van een formulier aan de app beschreven. Gebruik dezelfde stappen om een weergave of grafiek aan de app toe te voegen.  
  
1.  Selecteer op het canvas van de appontwerper de tegel **Formulieren** voor de entiteit waaraan u een formulier wilt toevoegen.  
  
     Op het canvas van de appontwerper wordt de hele rij voor de entiteit geselecteerd. Aan de rechterkant vindt u alle bestaande formulieren voor de geselecteerde entiteit.  
  
    > [!NOTE]
    >  U kunt ook een of meer van de volgende handelingen uitvoeren:  
    >   
    > - Selecteer de knop **Toevoegen** ![Knop Toevoegen in de ontwerper](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") en selecteer vervolgens **Formulieren**.  
    > - Selecteer op het tabblad **Onderdelen** onder **Entiteitsassets** de optie **Formulieren**.  
  
    > [!TIP]
    >  Voor alle entiteiten die zijn geselecteerd voor de app wordt er een knop **Meer opties** (**...**) weergegeven in de lijst **Entiteiten selecteren** op het tabblad **Onderdelen** . Om alle assets toe te voegen voor de geselecteerde entiteit, selecteert u **Meer opties** (**...**) en selecteert u **Alle assets toevoegen**.  
  
2.  Als u wilt dat uw appgebruikers alleen bepaalde formulieren kunnen selecteren, schakelt u de selectievakjes in voor de formulieren die u wilt toevoegen. De formulieren bepalen hoe gebruikers de gegevens in de app te zien krijgen en kunnen gebruiken. 
 
     Op de formuliertegel van de geselecteerde entiteit wordt het aantal toegevoegde formulieren weergegeven.  
  
     ![Formuliertegel voor aanvraagentiteit](../model-driven-apps/media/add-forms-entity.png "Formuliertegel voor aanvraagentiteit")  
  
     Als u bijvoorbeeld geen formulier voor een entiteit selecteert, worden alle formulieren voor deze entiteit aan eindgebruikers weergegeven terwijl ze de app gebruiken. Dit gedrag is vergelijkbaar voor weergaven en grafieken als geen weergave of grafiek is geselecteerd. Zo kunt u snel apps maken wanneer u alle beschikbare onderdelen moet gebruiken. Tijdens het appontwerp hoeft niet elk onderdeel te zijn geselecteerd.  

     Als geen dashboards of bedrijfsprocesstromen zijn geselecteerd, zijn alle dashboards en bedrijfsprocesstromen beschikbaar voor gebruikers terwijl zij de app gebruiken.
  
    > [!NOTE]
    > De app kan alleen worden uitgevoerd als elke entiteit die u toevoegt, ten minste één actief formulier bevat. Als u meerdere formulieren hebt geselecteerd, wordt het eerste actieve formulier dat in de standaardoplossing verschijnt, gebruikt wanneer gebruikers de app uitvoeren.  
  
3.  Als u een nieuw formulier wilt toevoegen dat niet beschikbaar is in de lijst, selecteert u **Nieuw(e) maken**.  
  
     Selecteer het type formulier dat u wilt maken in de vervolgkeuzelijst.  
  
    > [!NOTE]
    >  De vervolgkeuzelijst is alleen beschikbaar als u formulieren toevoegt. De vervolgkeuzelijst is niet beschikbaar voor weergaven en grafieken.  
  
     De formulierontwerper wordt geopend. Meer informatie: [Formulieren maken en ontwerpen](create-design-forms.md)  
  
     Als u een weergave of grafiek toevoegt, wordt met de optie **Nieuw(e) maken** de juiste ontwerper geopend. Meer informatie: [Weergaven begrijpen](create-edit-views.md) en [Een systeemgrafiek maken of bewerken](create-edit-system-chart.md)  
  
    > [!NOTE]
    >  Als u een weergave toevoegt, kunt u alleen openbare weergaven gebruiken die onder het knooppunt **Weergaven** worden weergegeven in de oplossingenverkenner.  
  
4. Selecteer de pijl-omlaag ![Pictogram voor vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel uit te vouwen en een lijst met formulieren te bekijken die zijn toegevoegd.  
  
     ![Formuliertegel die is uitgevouwen in appontwerper](../model-driven-apps/media/app-designer-expanded-form-tile.png "Formuliertegel die is uitgevouwen in de appontwerper")  
  
5.  Herhaal deze stappen om entiteitsweergaven en grafieken aan de app toe te voegen.  
  
6.  Selecteer **Opslaan**.  
  
## <a name="edit-or-remove-artifacts"></a>Artefacten bewerken of verwijderen  
  
- Als u een dashboard of een bedrijfsprocesstroom wilt bewerken, selecteert u de pijl-omlaag ![Pictogram voor vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel uit te vouwen en selecteert u vervolgens de knop voor de siteoverzichtontwerper ![Knop Siteoverzichtontwerper openen](../model-driven-apps/media/dynamics365-open-designer.PNG "Knop Siteoverzichtontwerper openen") die overeenkomt met het dashboard dat of de bedrijfsprocesstroom die u wilt bewerken.  
  
     De ontwerper voor het geselecteerde artefact wordt geopend.  
  
- Als u een dashboard of een bedrijfsprocesstroom wilt verwijderen, selecteert u de pijl-omlaag ![Pictogram voor vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel uit te vouwen, en selecteert u het dashboard dat of de bedrijfsprocesstroom die u wilt verwijderen. Selecteer de optie **Verwijderen** op de opdrachtbalk.  

    Een andere manier om een dashboard of een bedrijfsprocesstroom te verwijderen is door het bijbehorende selectievakje op het tabblad **Onderdelen** uit te schakelen.
  
- Als u een entiteit wilt bewerken of verwijderen, selecteert u de entiteittegel en selecteert u op de opdrachtbalk de optie **Bewerken** of **Verwijderen**. Als u een entiteit bewerkt, wordt de oplossingenverkenner geopend. Hierin kunt u wijzigingen aanbrengen in de entiteit.  
  
     Een andere manier om een onderdeel te verwijderen is door het dashboard, de bedrijfsprocesstroom of de entiteittegel te selecteren. Schakel op het tabbad **Onderdelen** de selectievakjes uit voor de artefacten die u uit de ontwerper wilt verwijderen.  
  
    > [!NOTE]
    >  Als u wijzigingen in een entiteit aanbrengt, zoals wanneer u een entiteitsweergavenaam of -beschrijving wijzigt, worden de wijzigingen alleen in de appontwerper weergegeven als de wijzigingen in de oplossingenverkenner worden gepubliceerd.  
  
## <a name="edit-or-remove-entity-assets"></a>Entiteitsassets bewerken of verwijderen  

### <a name="edit-entity-assets"></a>Entiteitsassets bewerken
  
1. Selecteer de pijl-omlaag ![Pictogram voor vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel voor formulieren weergaven, grafieken of dashboards uit te vouwen.  
  
2. Selecteer het formulier, de weergave, de grafiek of het dashboard dat u wilt bewerken.  
  
3. Selecteer **Bewerken** op de opdrachtbalk.

   of

   Selecteer de knop Siteoverzichtontwerper ![Knop Siteoverzichtontwerper openen](../model-driven-apps/media/dynamics365-open-designer.PNG "Knop Siteoverzichtontwerper openen") die overeenkomt met het formulier, de weergave, de grafiek of het dashboard.  

### <a name="remove-entity-assets"></a>Entiteitsassets verwijderen  

1. Selecteer de pijl-omlaag ![Pictogram voor vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel voor formulieren weergaven, grafieken of dashboards uit te vouwen.  
  
2. Selecteer het formulier, de weergave, de grafiek of het dashboard dat u wilt bewerken.

3. Selecteer de optie **Verwijderen** op de opdrachtbalk. 

U kunt ook de tegel voor de formulieren, weergaven, grafieken of dashboards selecteren en vervolgens op het tabblad **Onderdelen**, de selectievakjes uitschakelen voor de assets die u wilt verwijderen uit de ontwerper.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Een siteoverzicht voor een app maken](create-site-map-app.md) </br>  
 [Een app valideren en publiceren](validate-app.md)
