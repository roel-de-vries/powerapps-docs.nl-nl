---
title: Zelfstudie voor het toevoegen of bewerken van onderdelen van modelgestuurde apps met PowerApps | MicrosoftDocs
description: De PowerApps-appontwerper gebruiken voor het toevoegen of bewerken van onderdelen
keywords: ''
ms.date: 03/30/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
author: Mattp123
ms.assetid: be93b9d7-f1c2-4ee7-8d7c-0f5c34dfa5f7
ms.author: matp
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 17
topic-status: Drafting
ms.openlocfilehash: 87fec3bff3ad21a5c0474b67f001cca5c902d609
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679940"
---
# <a name="tutorial-add-or-edit-model-driven-app-components-in-the-powerapps-app-designer"></a>Zelfstudie: componenten van modelgestuurde apps toevoegen of bewerken in de PowerApps-appontwerper

In deze zelfstudie leert u hoe u onderdelen kunt toevoegen aan en verwijderen uit een modelgestuurde app. 

Een modelgestuurde app bestaat uit verschillende onderdelen. U kunt twee soorten onderdelen toevoegen aan een app: artefacten en entiteitsassets. In de context van de appontwerper zijn entiteiten, dashboards en bedrijfsprocesstromen allemaal artefacten van een app. Entiteitsassets zijn formulieren, weergaven, grafieken en dashboards.  
  
De appontwerper verwijst naar bestaande metagegevens in de standaardoplossing. U kunt deze gebruiken om onderdelen te maken zoals formulieren, weergaven, grafieken en dashboards.  
  
## <a name="app-designer-layout"></a>Indeling appontwerper  
 De appontwerper bevat twee hoofdgebieden. Links is het canvas, waar u app-onderdelen kunt toevoegen.  
  
![Canvas appontwerper](../model-driven-apps/media/app-designer-canvas-pane.png)

 Aan de rechterkant staan tabbladen die u gebruikt voor het selecteren van onderdelen en instellen van de eigenschappen van onderdelen.  
  
 ![Onderdelen appontwerper](../model-driven-apps/media/app-designer-canvas-components-tab.png "Onderdelen appontwerper")  
  
 Op het canvas ziet u de gebieden voor het siteoverzicht, de bedrijfsprocesstroom, het dashboard en de entiteiten. Wanneer u een dashboard of bedrijfsprocesstroom selecteert of een siteoverzicht configureert, voegt de app-ontwerper de entiteiten die worden gebruikt in deze onderdelen automatisch toe aan het canvas. Nadat de entiteiten op hun plaats staan, hoeft u alleen maar elke entiteit te selecteren en er de vereiste entiteitsassets aan toe te voegen, zoals formulieren, weergaven en grafieken.
 
 U kunt ook **Canvas doorzoeken** gebruiken om te zoeken naar onderdelen op het canvas. Wanneer u **Canvas doorzoeken** selecteert, wordt er een nieuw tabblad geopend rechts van de tabbladen in het rechterdeelvenster.   
  
 ![Zoekopties Canvas](media/app-designer-search-tab.png "Canvas doorzoeken")

## <a name="open-an-app"></a>Een app openen
1. Meld u aan bij [PowerApps](https://web.powerapps.com/). 

2. Selecteer **Modelgestuurde** > **Apps** en selecteer een bestaande app of selecteer **Een app maken**. Zie [Een modelgestuurde app maken of bewerken met de app-ontwerper](create-edit-app.md#create-an-app) voor meer informatie over het maken van een app.

## <a name="add-an-artifact-entity-dashboard-or-business-process-flow"></a>Een artefact (entiteit, dashboard of bedrijfsprocesstroom) toevoegen  
 Wanneer u een dashboard of bedrijfsprocesstroom toevoegt aan een app, worden de entiteiten die ze gebruiken automatisch toegevoegd aan de app. Wanneer u een entiteit toevoegt, worden de tegels voor de assets automatisch toegevoegd. Er zijn twee manieren waarop u artefacten kunt toevoegen aan het canvas van de ontwerper: met de knop **Toevoegen** ![Knop Toevoegen in de ontwerper](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") op de opdrachtbalk of met de tegels op het tabblad **Onderdelen**.  
  
 Hier volgen de stappen voor het toevoegen van een dashboard aan de app. Gebruik dezelfde stappen voor het toevoegen van een bedrijfsprocesstroom of entiteit.  
  
1.  Selecteer op het canvas van de appontwerper de tegel **Dashboards**.  
  
     Op het canvas van de appontwerper ziet u in het rechterdeelvenster de dashboards die beschikbaar zijn in de standaardoplossing.  
  
    > [!TIP]
    >  U kunt ook het volgende doen:  
    >   
    > - Selecteer de knop **Toevoegen** ![Knop Toevoegen in de ontwerper](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") en selecteer vervolgens **Dashboards**.  
    > - Selecteer op het tabblad **Onderdelen** onder **Artefacten** de optie **Dashboards**.  
  
2.  In het vak **Zoeken** typt u een aantal trefwoorden voor het dashboard dat u zoekt.  
  
     De lijst met dashboards wordt gefilterd om de resultaten weer te geven die overeenkomen met uw trefwoorden.  
  
3.  Als u wilt dat uw gebruikers alleen geselecteerde dashboards kunnen gebruiken, selecteert u het selectievakje voor de dashboards die u wilt toevoegen. U kunt kiezen uit de volgende typen dashboards:
    - **Klassieke dashboards** worden weergeven in zowel de web-app als de Unified Interface-app.
    - **Interactieve dashboards** worden alleen weergegeven in Unified Interface-app. Als u het clienttype voor de app hebt geselecteerd als web-app, wordt de optie **Interactieve dashboards** niet weergegeven.

     Deze dashboards worden toegevoegd aan de tegel **Dashboard** op het canvas van de appontwerper. Op de tegel **Dashboard** wordt ook een aantal dashboards weergeven dat u hebt toegevoegd aan de app. Als u geen dashboard selecteert, wordt **Alle** weergegeven in plaats van het aantal dashboards, en zijn alle dashboards beschikbaar voor gebruikers wanneer ze de app gebruiken.  
  
     Alle entiteiten die worden gebruikt in het dashboard zijn ook toegevoegd aan het gebied **Entiteitsweergave**. Als u bijvoorbeeld het dashboard Customer Service Manager toevoegt, worden de entiteiten Case, Entitlement en Queue Item toegevoegd aan het gebied Entiteitsweergave. Voor elke entiteit worden ook tegels voor de assets toegevoegd. U kunt deze tegels gebruiken om formulieren, weergaven en grafieken toe te voegen. Meer informatie: [Onderdelen van modelgestuurde apps toevoegen of bewerken in de PowerApps-appontwerper](add-edit-app-components.md#bkmk_AddEntityAssets)   
  
    ![Een entiteit toevoegen aan het canvas van appontwerper](../model-driven-apps/media/add-entity-app-designer-canvas.png "Een entiteit toevoegen aan het canvas van appontwerper")  
  
4.  Als het dashboard dat u wilt niet in de standaardoplossing aanwezig is, kunt u een dashboard maken door **Nieuw** te selecteren op het tabblad **Onderdelen** aan de rechterkant van het canvas.  
  
     ![Nieuwe koppeling maken op het tabblad Onderdelen van de appontwerper](../model-driven-apps/media/app-designer-components-tab-create-new.png "Nieuwe koppeling maken op het tabblad Onderdelen van de appontwerper")  
  
     De dashboardontwerper wordt geopend. Meer informatie: [Dashboards maken en bewerken](create-edit-dashboards.md)  
  
    > [!NOTE]
    > - Wanneer u een bedrijfsprocesstroom of entiteit toevoegt, opent u met de optie **Nieuwe maken** de bijbehorende ontwerper. Zie [Een bedrijfsprocesstroom maken](/flow/create-business-process-flow) en [Een aangepaste entiteit maken](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-create-entity) voor meer informatie over het maken van bedrijfsprocesstromen of entiteiten.  
      
  
5.  Wanneer u klaar bent met het toevoegen van artefacten, selecteert u **Opslaan** op de opdrachtbalk.  
  
<a name="bkmk_AddEntityAssets"></a>   
## <a name="add-entity-assets-forms-views-charts-or-dashboards"></a>Entiteitsassets toevoegen (formulieren, weergaven, grafieken of dashboards)  
 Wanneer de artefacten op hun plaats staan, kunt u entiteitsassets zoals formulieren, weergaven, grafieken en dashboards toevoegen.
Als u de Unified Interface-app gebruikt, kunt u ook dashboardassets toevoegen aan de app.  
  
 In dit gedeelte worden de stappen beschreven voor het toevoegen van een formulier aan de app. Gebruik dezelfde stappen voor het toevoegen van een weergave of een grafiek aan de app.  
  
1.  Selecteer op het canvas van de appontwerper de tegel **Formulieren** voor de entiteit waaraan u een formulier wilt toevoegen.  
  
     Op het canvas van de appontwerper wordt de hele rij voor de entiteit geselecteerd. Aan de rechterkant ziet u alle bestaande formulieren voor de geselecteerde entiteit.  
  
    > [!NOTE]
    >  U kunt ook het volgende doen:  
    >   
    > - Selecteer de knop **Toevoegen** ![Knop Toevoegen in de ontwerper](../model-driven-apps/media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") en selecteer vervolgens **Formulieren**.  
    > - Selecteer op het tabblad **Onderdelen** onder **Entiteitsassets** de optie **Formulieren**.  
  
    > [!TIP]
    >  Voor alle entiteiten die zijn geselecteerd voor de app wordt een knop **Meer opties** (**...**) weergegeven in de lijst **Entiteiten selecteren** op het tabblad **Onderdelen**. Als u alle assets voor de geselecteerde entiteit wilt toevoegen, selecteert u **Meer opties** (**...** ) en vervolgens **Alle assets toevoegen**.  
  
2.  Als u wilt dat de gebruikers van uw app alleen geselecteerde formulieren kunnen gebruiken, selecteert u het selectievakje voor de formulieren die u wilt toevoegen. Formulieren definiëren hoe gebruikers de gegevens in de app zien en gebruiken. 
 
     Op de tegel Formulieren van de geselecteerde entiteit wordt het aantal toegevoegde formulieren weergegeven.  
  
     ![Tegel Formulieren voor entiteit Case](../model-driven-apps/media/add-forms-entity.png "Tegel Formulieren voor entiteit Case")  
  
     Als u bijvoorbeeld geen formulier voor een entiteit selecteert, zijn alle formulieren voor die entiteit zichtbaar voor de eindgebruikers wanneer ze de app gebruiken. Dit gebeurt ook bij weergaven en grafieken als u geen weergave of grafiek hebt geselecteerd. Op deze manier kunt u snel apps maken als u alle beschikbare onderdelen nodig hebt; u hoeft tijdens het ontwerpen van de app niet elk onderdeel te selecteren.  

     Als u geen dashboards of bedrijfsprocesstromen voor een entiteit selecteert, zijn alle dashboards of bedrijfsprocesstromen voor die entiteit zichtbaar voor de eindgebruikers wanneer ze de app gebruiken.
  
    > [!NOTE]
    > Voor het kunnen uitvoeren van de app moet elke entiteit die u toevoegt ten minste een actief formulier hebben. Als u meerdere formulieren hebt geselecteerd, wordt het eerste actieve formulier dat wordt weergegeven in de standaardoplossing gebruikt wanneer gebruikers de app uitvoeren.  
  
3.  Als u een nieuw formulier wilt toevoegen dat niet beschikbaar is in de lijst, selecteert u **Nieuwe maken**.  
  
     Selecteer in de vervolgkeuzelijst het type formulier dat u wilt maken.  
  
    > [!NOTE]
    >  De vervolgkeuzelijst is alleen beschikbaar wanneer u formulieren toevoegt. Deze is niet beschikbaar voor weergaven en grafieken.  
  
     De formulierontwerper wordt geopend. Meer informatie: [Formulieren maken en bewerken](create-design-forms.md)  
  
     Wanneer u een weergave of grafiek toevoegt, opent u met de optie **Nieuwe maken** de bijbehorende ontwerper. Meer informatie: [Weergaven begrijpen](create-edit-views.md) en [Een systeemgrafiek maken of bewerken](create-edit-system-chart.md)  
  
    > [!NOTE]
    >  Wanneer u een weergave toevoegt, kunt u alleen verwijzen naar openbare weergaven die worden vermeld onder het knooppunt **Weergaven** in de Solution Explorer.  
  
4. Selecteer de pijl-omlaag ![Pictogram vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel uit te vouwen en een overzicht van toegevoegde formulieren weer te geven.  
  
     ![Tegel Formulieren uitgevouwen in appontwerper](../model-driven-apps/media/app-designer-expanded-form-tile.png "Tegel Formulieren uitgevouwen in appontwerper")  
  
5.  Herhaal deze stappen om entiteitsweergaven en -grafieken toe te voegen aan de app.  
  
6.  Selecteer **Opslaan**.  
  
## <a name="edit-or-remove-artifacts"></a>Artefacten bewerken of verwijderen  
  
- Als u een dashboard of bedrijfsprocesstroom wilt bewerken, selecteert u de pijl-omlaag ![Pictogram vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel uit te vouwen. Selecteer vervolgens de knop Siteoverzichtontwerper ![Knop Siteoverzichtontwerper openen](../model-driven-apps/media/dynamics365-open-designer.PNG "Knop Siteoverzichtontwerper openen") voor het dashboard of de bedrijfsprocesstroom die u wilt bewerken.  
  
     De ontwerpfunctie voor het geselecteerde artefact wordt geopend.  
  
- Als u een dashboard of bedrijfsprocesstroom wilt bewerken, selecteert u de pijl-omlaag ![Pictogram vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel uit te vouwen en selecteert u het dashboard of de bedrijfsprocesstroom die u wilt verwijderen. Selecteer **Verwijderen** op de opdrachtbalk.  

    Een andere manier om een dashboard of bedrijfsprocesstroom te verwijderen is door het bijbehorende selectievakje uit te schakelen op het tabblad **Onderdelen**.
  
- Als u een entiteit wilt bewerken of verwijderen, selecteert u de tegel van de entiteit en selecteert u vervolgens in de opdrachtbalk **Bewerken** of **Verwijderen**. Wanneer u een entiteit bewerkt, wordt de Solution Explorer geopend, waarin u wijzigingen kunt aanbrengen in de entiteit.  
  
     Een andere manier om een onderdeel te verwijderen is door de tegel van het dashboard, de bedrijfsprocesstroom of de entiteit te selecteren. Schakel op het tabblad **Onderdelen** de selectievakjes uit voor de artefacten die u wilt verwijderen uit de ontwerper.  
  
    > [!NOTE]
    >  Wanneer u wijzigingen aanbrengt in een entiteit&mdash;zoals het wijzigen van de naam of beschrijving van een entiteit&mdash;worden de wijzigingen niet weergegeven in de appontwerper, tenzij de wijzigingen worden gepubliceerd in de Solution Explorer.  
  
## <a name="edit-or-remove-entity-assets"></a>Entiteitsassets bewerken of verwijderen  

### <a name="edit-entity-assets"></a>Entiteitsassets bewerken
  
1. Selecteer de pijl-omlaag ![Pictogram vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel voor formulieren, weergaven, grafieken of dashboards uit te vouwen.  
  
2. Selecteer het formulier, de weergave, de grafiek of het dashboard dat u wilt bewerken.  
  
3. Selecteer **Bewerken**  op de opdrachtbalk.

   of

   Selecteer de knop Siteoverzichtontwerper ![Knop Siteoverzichtontwerper openen](../model-driven-apps/media/dynamics365-open-designer.PNG "Knop Siteoverzichtontwerper openen") voor het formulier, de weergave, de grafiek of het dashboard.  

### <a name="remove-entity-assets"></a>Entiteitsassets verwijderen  

1. Selecteer de pijl-omlaag ![Pictogram vervolgkeuzelijst](../model-driven-apps/media/drop-down-icon.png "pijl-omlaag") om de tegel voor formulieren, weergaven, grafieken of dashboards uit te vouwen.  
  
2. Selecteer het formulier, de weergave, de grafiek of het dashboard dat u wilt bewerken.

3. Selecteer **Verwijderen** op de opdrachtbalk. 

U kunt ook de tegel voor formulieren, weergaven en grafieken of dashboards selecteren en vervolgens op het tabblad **Onderdelen** de selectievakjes uitschakelen voor de assets die u wilt verwijderen uit de ontwerper.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Een siteoverzicht voor een app maken](create-site-map-app.md) </br>  
 [Een app valideren en publiceren](validate-app.md)
