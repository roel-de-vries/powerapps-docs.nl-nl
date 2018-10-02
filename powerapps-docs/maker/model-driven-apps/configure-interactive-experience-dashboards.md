---
title: Dashboards voor interactieve ervaring in modelgestuurde apps configureren in PowerApps | Microsoft Docs
description: Leer dashboards voor interactieve ervaring configureren in PowerApps
keywords: Interactieve dashboards; Customer Service; Microsoft Dynamics 365; Interactieve servicehub
author: Mattp123
ms.author: matp
manager: kvivek
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: d1446a95-14bf-4b15-a905-72fce07f4c76
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="configure-model-driven-app-interactive-experience-dashboards"></a>Dashboards voor interactieve ervaring in modelgestuurde apps configureren

Interactieve ervaringsdashboards kunnen een centrale alomvattende werkruimte vormen voor app-gebruikers, zoals verkoopmedewerkers, waar ze werkbelastingsinformatie kunnen bekijken en actie kunnen ondernemen. Zij zijn volledig configureerbaar, gebaseerd op beveiligingsrollen en leveren werkbelastingsinformatie voor meerdere gegevensstromen in realtime. Interactieve dashboardgebruikers hoeven niet door de toepassing te bladeren op zoek naar een bepaalde record; zij kunnen hierop rechtstreeks acties uitvoeren vanuit het dashboard. 

 De interactieve dashboards bestaan in twee soorten: multi-gegevensstroom en enkele-gegevensstroom. Bovendien kunnen multi-gegevensstroomdashboards specifiek voor een startpagina of voor een entiteit zijn. De entiteitspecifieke dashboards worden geconfigureerd in een ander deel van de gebruikersinterface en worden vooraf gedeeltelijk geladen met de entiteitspecifieke configuratie-informatie.  
  
 De multi-gegevensstroomdashboards tonen gegevens in realtime over meerdere gegevensstromen. Er is geen limiet voor het aantal gegevensstromen dat u op het dashboard kunt configureren. De gegevens in een gegevensstroom kunnen alleen op een entiteit worden gebaseerd, elke gegevensstroom kan op een andere entiteit worden gebaseerd. In de entiteitspecifieke dashboard zijn alle gegevensstromen gebaseerd op dezelfde entiteit. De gegevens stromen vanuit verschillende weergaven of wachtrijen, zoals **Mijn activiteiten**, **Mijn Aanvragen**, or **Aanvragen in de Bankwachtrij**. 
  
 De enkele-gegevensstroom dashboards tonen real time-gegevens van één gegevensstroom op basis van een weergave of wachtrij van een entiteit. De tegels worden geplaatst aan de rechterkant van de dashboards en altijd weergegeven. De enkele-gegevensstroom dashboards zijn nuttig voor laag 2-serviceleads of managers die minder, maar meer complexe of geëscaleerde aanvragen controleren.  
  
 Multi-gegevensstroom en enkele-gegevensstroom dashboards bevatten interactieve diagrammen met een telling van relevante records, zoals aanvragen op prioriteit of status. Deze diagrammen fungeren ook als visuele filters. De visuele filters (interactieve diagrammen) zijn gebaseerd op meerdere entiteiten, en in de enkele-gegevensstroom dashboards definieert de entiteit in de gegevensstroom de visuele filterentiteit.   
  
 Gebruikers kunnen aanvullende filtering toepassen met algemene filter en tijdsbestekfilter. Het algemene filter werkt op veldniveau op alle diagrammen, evenals op gegevensstromen en tegels die zijn gebaseerd op de filterentiteit (u specificeert de filterentiteit als u de visuele filters configureert). 
  
> [!NOTE]
>  De interactieve dashboards zijn oplossingsbewust en kunnen vervolgens in een andere omgeving als een oplossing worden geëxporteerd en geïmporteerd. Maar de wachtrijen waarop de gegevensstromen en tegels zijn gebaseerd zijn niet oplossingsbewust. Voordat de dashboardoplossing in het doelsysteem kan worden geïmporteerd, moeten de wachtrijen handmatig in het doelsysteem worden gemaakt in **Instellingen** > **Servicebeheer** > **Wachtrijen**. Nadat u de wachtrijen hebt gemaakt, importeert u de dashboardoplossing in het doelsysteem; daarna bewerkt u de gegevensstromen en of tegels die op wachtrijen zijn gebaseerd, en wijst u de zojuist gemaakte wachtrijen toe.  
  
 De illustraties in dit onderwerp tonen multi-gegevensstroom en enkele-gegevensstroom dashboards met het koptekstdeelvenster. Onder de koptekst ziet u visuele filters en gegevensstromen. In het enkele-gegevensstroom dashboard ziet u ook tegels. Voor elk dashboardtype kunt u kiezen uit verschillende indelingen die ook worden weergegeven. De hier weergegeven dashboardkoptekst bevat de volgende besturingselementen en selecteer pictogrammen, van links naar rechts: dashboardselector, vernieuwen, pictogram visueel filter, algemene filterknop en tijdsbestekfilter.  
  
### <a name="multi-stream-dashboard-standard-view"></a>Standaardweergave van multi-gegevensstroom dashboard  
 In het multi-gegevensstroom dashboard ziet u een rij visuele filters bovenin, met de gegevensstromen eronder.  
 
![Interactief dashboard met meerdere streams](../model-driven-apps/media/interactive-dashboards-multi-stream.png) 
   
### <a name="multi-stream-dashboard-tile-view"></a>Tegelweergave van multi-gegevensstroom dashboard  
 Hetzelfde dashboard, maar in de tegelweergave.  
  
 ![Tegelweergave van multi-gegevensstroom dashboard](../model-driven-apps/media/interactive-dashboards-multi-stream-tiles.png "Tegelweergave van multi-gegevensstroom dashboard")  
  
### <a name="multi-stream-dashboard-layouts"></a>Indelingen voor multi-gegevensstroom dashboards  
 Voor multi-gegevensstroomdashboards kunt u uit vier verschillende indelingen kiezen.  

 > [!div class="mx-imgBorder"] 
 > ![Indelingen voor multi-gegevensstroom dashboards](../model-driven-apps/media/interactive-dashboards-multi-stream-layout.png "Indelingen voor multi-gegevensstroom dashboards")  
  
### <a name="multi-stream-entity-specific-dashboard"></a>Entiteitspecifiek multi-gegevensstroomdashboard  
 Het entiteitspecifieke dashboard voor de entiteit `Case` wordt hier getoond.  
  
 ![Dashboard voor aanvragen openen](../model-driven-apps/media/interactive-dashboard-cases-dashboard.PNG "Dashboard voor aanvragen openen")  
  
### <a name="single-stream-dashboard"></a>Enkele-gegevensstream dashboard  
 Het enkele-gegevensstroom dashboard bevat de gegevensstroom aan de linkerzijde en visuele filters en tegels aan de rechterzijde.  
  
 ![Dashboard met enkele gegevensstream in interactieve servicehub](../model-driven-apps/media/interactive-dashboards-single-stream.png "Dashboard met enkele gegevensstream in interactieve servicehub")  
  
### <a name="single-stream-dashboard-layouts"></a>Indelingen voor enkele-gegevensstroom dashboards  
 Voor enkele-gegevensstroomdashboards kunt u uit vier verschillende indelingen kiezen.  
 
 > [!div class="mx-imgBorder"] 
 > ![Indelingen voor dashboards met enkele gegevensstroom](../model-driven-apps/media/interactive-dashboards-single-stream-layout.png "Indelingen voor dashboards met enkele gegevensstroom")  
  
<a name="BKMK_Enable"></a>   
## <a name="configure-entities-fields-and-security-roles-for-the-interactive-dashboards"></a>Entiteiten, velden en beveiligingsrollen voor de interactieve dashboards configureren  
 Als u interactieve dashboards configureert, is uw eerste taak is het inschakelen van entiteiten, velden en beveiligingsrollen voor de interactieve ervaring.  
  
### <a name="entities-enabled-for-interactive-experience"></a>Entiteiten ingeschakeld voor interactieve ervaring
 Alle entiteiten die in de Unified Interface worden ondersteund, zijn nu ingeschakeld voor de dashboards voor interactieve ervaring.
  
### <a name="configure-fields"></a>Velden configureren  
 Als u wilt dat een veld in het algemene filter wordt weergegeven en dat het wordt opgenomen in de sorteerbewerking van de gegevensstroom, moet u twee markeringen instellen, zoals in het onderstaande voorbeeld wordt weergegeven voor het veld **IsEscalated** van de entiteit Aanvraag.  

 > [!div class="mx-imgBorder"] 
 > ![Een veld voor een algemeen filter inschakelen en sorteren](../model-driven-apps/media/global-filter-sort-8.png "Een veld voor een algemeen filter inschakelen en sorteren")  
  
### <a name="configure-global-filter-fields"></a>Algemene filtervelden configureren  
 Als u wilt dat een veld in het algemene filter wordt weergegeven, moet u de markering **Wordt weergegeven in algemeen filter in interactieve ervaring** voor dit veld instellen. De velden die u configureert, worden weergegeven in het flyoutvenster van het algemene filter als u op het pictogram van het algemene filter op de dashboardkoptekst klikt. In het flyoutvenster kunnen servicemedewerkers de velden selecteren waarop ze het algemene filter willen toepassen, in diagrammen, en ook in gegevensstromen en filters waarop de filterentiteit is gebaseerd. Voor meer informatie over de filterentiteit zie het gedeelte "Multi-gegevensstroom interactieve dashboard configureren" verderop in dit onderwerp.  
  
 Het flyoutvenster van het algemene filter wordt hieronder getoond:  
  
 ![Twee algemene filtervelden toevoegen](../model-driven-apps/media/interactive-dashboards-global-filter-two-fields.png "Twee algemene filtervelden toevoegen")  
  
> [!NOTE]
>  Als u een visueel filter (interactief diagram) configureert op basis van velden als status basis of prioriteit, wordt u aangeraden deze velden (prioriteit, status) ook in te schakelen zodat ze in het algemene filter worden weergegeven.  
  
De volgende procedure bevat de stappen voor het instellen van de algemene filtermarkering:
  
1. Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).  
  
2. Vouw onder **Onderdelen** achtereenvolgens **Entiteiten** en de gewenste entiteit uit. Als de gewenste entiteit niet wordt weergegeven, selecteert u **Bestaande toevoegen** om de entiteit toe te voegen.  
  
3.  In het navigatiedeelvenster selecteert u **Velden** en in het raster dubbelklikt u op het veld dat u wilt inschakelen.  
  
4.  Selecteer op het tabblad **Algemeen** het selectievakje **Wordt weergegeven in algemeen filter in interactieve ervaring**. Kies **Opslaan en sluiten**.  
  
5.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
6.  Selecteer **Clientaanpassingen voorbereiden**.  
  
### <a name="configure-sortable-fields"></a>Sorteerbare velden configureren  
 Als u wilt dat een veld wordt gebruikt bij het sorteren van gegevensstroomgegevens moet u de markering **Sorteerbaar in dashboard voor interactieve ervaring** voor dit veld instellen. De velden die u voor sorteren configureert, worden in de vervolgkeuzelijst in het flyoutvenster **Eigenschap bewerken** weergegeven als de gebruiker **Meer (…)** selecteert in de koptekst van de gegevensstroom. In de volgende afbeelding ziet u het flyoutvenster met de lijst van beschikbare velden voor sorteren in de vervolgkeuzelijst **Sorteren op**. De standaardsorteerbewerking is altijd ingesteld op het veld **Gewijzigd op**.  
  
 ![Sorteren op vervolgkeuzelijst](../model-driven-apps/media/interactive-dashboard-sortable-fields-dropdown.png "Sorteren op vervolgkeuzelijst")  
  
De volgende procedure bevat de stappen voor het instellen van de sorteermarkering:
  
1. Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).   
2. Vouw onder **Onderdelen** achtereenvolgens **Entiteiten** en de gewenste entiteit uit. Als de gewenste standaardentiteit niet wordt weergegeven, selecteert u **Bestaande toevoegen** om de entiteit toe te voegen.  
  
3.  In het navigatiedeelvenster selecteert u **Velden** en in het raster dubbelklikt u op het veld dat u wilt inschakelen.  
  
4.  Selecteer op het tabblad **Algemeen** het selectievakje **Sorteerbaar in dashboard voor interactieve ervaring**. Kies **Opslaan en sluiten**.  
  
5.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
6.  Selecteer **Clientaanpassingen voorbereiden**.  
  
### <a name="enable-security-roles"></a>Beveiligingsrollen inschakelen  
 Selecteer beveiligingsrollen die de interactieve dashboards kunnen weergeven, en schakel ze in.  
  
De volgende procedure bevat de stappen om de beveiligingsrollen van de interactieve ervaring in te schakelen:
  
1. Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).  
  
2. Selecteer onder **Onderdelen** de optie **Dashboards**.  
  
4.  Selecteer in het raster het gewenste interactieve dashboard en selecteer **Beveiligingsrollen inschakelen** op de taakbalk.  
  
5.  Selecteer in het dialoogvenster **Beveiligingsrollen toewijzen** de optie **Alleen aan deze geselecteerde beveiligingsrollen weergeven** en selecteer de rollen die u wilt inschakelen. Selecteer **OK**.  
  
6.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
7.  Selecteer **Clientaanpassingen voorbereiden**.  
  
 ![Beveiligingsrollen inschakelen](../model-driven-apps/media/interactive-dashboards-enable-security-roles.png "Beveiligingsrollen inschakelen")  
  
 ![Beveiligingsrollen toewijzen](../model-driven-apps/media/interactive-dashboards-assign-security-roles.png "Beveiligingsrollen toewijzen")  
  
<a name="BKMK_Configure"></a>   
## <a name="configure-interactive-experience-dashboards"></a>Dashboards voor interactieve ervaring configureren  
 In de volgende gedeelten wordt beschreven hoe u verschillende typen interactieve dashboards kunt configureren.  
  
### <a name="configure-a-multi-stream-interactive-dashboard-using-the-4-column-layout"></a>Een interactief multi-gegevensstroomdashboard met 4 kolommen configureren  
 
1.  Meld u aan bij [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

2.  Selecteer **Modelgestuurd** (onderste links).  
  
3.  Selecteer **Gegevens** > **Entiteiten** > selecteer de gewenste entiteit. 

4.  Selecteer het tabblad **Dashboards**, klik op op de werkbalk en selecteer **Dashboard toevoegen**.  
  
5.  Kies de indeling, kolombreedte 2, 3, of 4.  
  
6.  Als het dashboardformulier wordt weergegeven, vult u de filtergegevens boven aan het formulier in, zoals hieronder weergegeven.  
 
 > [!div class="mx-imgBorder"] 
 > ![Visuele filters toevoegen](../model-driven-apps/media/interactive-dashboards-add-visual-filters.png "Visuele filters toevoegen")  
  
   - **Filterentiteit**: De visuele filters (interactieve diagrammen) en de algemene filterkenmerken worden gebaseerd op deze entiteit.  
      
    - **Entiteitsweergave**: De visuele filters (interactieve diagrammen) worden op deze weergave gebaseerd.  
      
    - **Filteren op**: Het het veld waarop de tijdsbestekfilter van toepassing is.  
      
    - **Tijdsbestek**: De standaardwaarde van het tijdsbestekfilter voor het veld **Filteren op**.  
      
 Nadat u de gewenste filterinformatie hebt opgegeven, begint u met het toevoegen van onderdelen voor de diagrammen en de gegevensstromen. Als u een onderdeel wilt toevoegen, selecteert u eenvoudigweg het element in het midden van het diagram of de gegevensstroom, en als het dialoogvenster wordt weergegeven voert u de vereiste gegevens in, zoals weergegeven in de volgende illustraties.  
  
 Voeg het ringdiagram **Activiteiten per prioriteit** toe.
  
 > [!div class="mx-imgBorder"] 
 > ![Onderdeel van een ringdiagram toevoegen](../model-driven-apps/media/interactive-dashboards-add-chart-circle.png "Onderdeel van een ringdiagram toevoegen")  
  
 Sommige diagrammen zoals staafdiagrammen of cirkeldiagrammen, geven de gegevens weer die in het systeem zijn opgeslagen. De ringdiagrammen en de codediagrammen worden als statische afbeeldingen geladen, en zijn geen voorbeeldweergave van de werkelijke gegevens.  
  
> [!NOTE]
>  De diagrammen die zijn geconfigureerd voor de visuele filters kunnen velden van de entiteit **Filter** gebruiken, maar ook die van gerelateerde entiteiten. Wanneer u diagrammen gebruikt op basis van velden uit gerelateerde entiteiten, kunnen klantenservicevertegenwoordigers diagrammen filteren met behulp van deze velden uit gerelateerde entiteiten. De velden die zijn gebaseerd op de gerelateerde entiteit hebben meestal de volgende notatie in het venster van de diagramconfiguratie: "veldnaam (entiteitsnaam)", bijvoorbeeld het veld **Gewijzigd door (gemachtigde)**. Als u diagrammen met meerdere entiteiten wilt maken, moet u velden van een gerelateerde entiteit toevoegen aan een van de weergaven, en deze velden vervolgens gebruiken bij het maken van diagrammen.  
 
 > [!div class="mx-imgBorder"] 
 > ![Diagrammen maken voor visuele filters](../model-driven-apps/media/interactive-dashboard-visual-charts-x-y-axes.PNG "Diagrammen maken voor visuele filters")  
  
 Configureer vervolgens de gegevensstromen. Net als bij het toevoegen van onderdelen in de diagrammen, selecteert u het element in het gegevensstroompaneel. Wanneer het dialoogvenster wordt geopend, selecteert u **Weergave** of **Wachtrij** afhankelijk van het element dat u de gegevensstroom wilt laten gebruiken. Voer de vereiste informatie in zoals deze in de volgende illustratie wordt weergegeven.  
  
> [!NOTE]
>  De optie **Wachtrij** is alleen in het dialoogvenster beschikbaar voor entiteiten met wachtrij. Bij entiteitdashboards ziet u de optie **Wachtrij** niet in het dialoogvenster als voor de entiteit de wachtrij niet is ingeschakeld. U kunt de **optie Weergave** alleen gebruiken in de dashboardstroom voor entiteiten waarvoor de wachtrij niet is ingeschakeld.  
  
 Configureer de gegevensstroom voor de **Items die beschikbaar zijn om aan te werken** zoals hieronder getoond:  
  
 ![Een gegevensstroom met mijn actieve aanvragen toevoegen](../model-driven-apps/media/interactive-dashboards-add-stream-case.png "Een gegevensstroom met mijn actieve aanvragen toevoegen")  
  
 In de volgende afbeelding wordt een voorbeeld van het grafiekpaneel weergegeven, van links naar rechts: ringdiagram, codediagram, staafdiagram:  
 
 > [!div class="mx-imgBorder"] 
 > ![Alle interactieve grafieken](../model-driven-apps/media/interactive-dashboards-add-all-charts.png "Alle interactieve grafieken")  
  
 Deze weergave is een voorbeeld van het gegevensstroompaneel met verschillende gegevensstromen:  
 
 > [!div class="mx-imgBorder"] 
 > ![Alle gegevensstromen toevoegen](../model-driven-apps/media/interactive-dashboards-add-all-streams.png "Alle gegevensstromen toevoegen")  
  
 Nadat u het configureren van het dashboard hebt voltooid, slaat u het op en publiceert u de aanpassingen zodat de wijzigingen van kracht worden. Zorg er ook voor dat u **Clientaanpassingen voorbereiden** selecteert.  
  
#### <a name="edit-or-delete-individual-streams-of-an-existing-dashboard"></a>Afzonderlijke gegevensstromen in een bestaand dashboard bewerken of verwijderen  
  
1. Meld u aan bij [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).   
  
2. Selecteer **Modelgestuurd** (onderste links), **Gegevens**, > **Entiteiten** > selecteer de gewenste entiteit. Selecteer het tabblad **Dashboards**.  
  
     -OF-  
   
   Open [oplossingenverkenner](advanced-navigation.md#solution-explorer) en selecteer vervolgens onder **Onderdelen** **Dashboards**.
  
3.  Selecteer in het raster het interactieve dashboard dat u wilt bewerken om het te openen.  
  
4.  Selecteer de gegevensstroom die u wilt bewerken om deze te selecteren en selecteer **Onderdeel bewerken**.  
  
5.  Afhankelijk van of u een weergave of een wachtrij wilt toevoegen aan de gegevensstroom, selecteert u de details van de weergave of de wachtrij van de gegevensstroom en vervolgens **Instellen**.  
  
6.  Selecteer **Opslaan**.  
  
 U kunt ook een individuele gegevensstroom uit een dashboard verwijderen. Als u dit wilt doen, selecteert u de gegevensstroom en selecteert u in de opdrachtbalk de optie **Verwijderen**.  
  
### <a name="configure-an-entity-specific-dashboard"></a>Een entiteitspecifiek dashboard configureren  
 Een entiteitspecifiek dashboard is een multi-gegevensstroomdashboard. Het configureren van dit dashboard is vergelijkbaar met het configureren van een multi-gegevensstroomdashboard op de startpagina, maar u werkt in een andere plek in de gebruikersinterface en er zijn nog enkele andere kleine verschillen. Bijvoorbeeld, in plaats van het selecteren van een entiteit, zijn sommige velden in het entiteitspecifieke dashboard vooraf ingesteld op de entiteit waarvoor u het dashboard creëert.  
  
1.  Meld u aan bij [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

2.  Selecteer **Modelgestuurd** (onderste links).  
  
3.  Selecteer **Gegevens** > **Entiteiten** > selecteer de gewenste entiteit. 

4.  Selecteer het tabblad **Dashboards**, klik op op de werkbalk en selecteer **Dashboard toevoegen**.  
  
5.  Kies de indeling, kolombreedte 2, 3, of 4.    
  
6.  Als het dashboardformulier wordt geopend, is **Filterentiteit** vooraf ingesteld op de entiteit waarvoor u het dashboard creëert. De vervolgkeuzelijst **Entiteitsweergave** bevat de beschikbare weergaven voor de entiteit. Selecteer de weergave en vul de overige vereiste informatie op de pagina in.  
  
 De rest van het instellen lijkt sterk op het instellen van het dashboard van de startpagina multi-gegevensstroom, dat in het vorige hoofdstuk wordt beschreven.  
  
### <a name="configure-a-single-stream-dashboard"></a>Een enkele-gegevensstroom dashboard configureren  
 Het configureren van een enkel-gegevensstroom dashboard is vergelijkbaar met het configureren van een multi-gegevensstroom dashboard. Alle stappen waarmee u door de gebruikersinterface navigeert, zijn dezelfde als voor het multi-gegevensstroom dashboard. U kunt een indeling kiezen die tegels bevat of een indeling die geen tegels bevat. Als de indeling tegels bevat, worden deze altijd op het dashboard weergegeven. Als u een tegel wilt configureren, selecteert u het pictogram in het midden van de tegel. Als het venster **Tegel toevoegen** wordt geopend, vult u de vereiste gegevens in. In de volgende illustratie ziet u een voorbeeld van hoe een tegel wordt ingesteld.  
  
 ![Een tegel toevoegen aan het dashboard met enkele gegevensstroom](../model-driven-apps/media/interactive-dashboard-add-tile-single-stream.png "Een tegel toevoegen aan het dashboard met enkele gegevensstroom")  
  
<a name="BKMK_ConfigureColors"></a>   
## <a name="configure-dashboard-colors"></a>Dashboardkleuren configureren  
 Voor alle velden van het type **Optieset** en **Twee opties**, zoals de velden **Aanvraagtype**, **IsEscalated** of **Prioriteit** van de entiteit `Case` kunt u een bepaalde kleur instellen die voor bepaalde velden wordt gebruikt in de diagrammen en gegevensstromen. Zo kunnen bijvoorbeeld, aanvragen met een hoge prioriteit in rood, met een gemiddelde prioriteit in blauw en met een lage prioriteit in groen worden weergegeven in de interactieve diagrammen. In de gegevensstromen wordt de kleur weergegeven in de dunne verticale lijn links van de werkitembeschrijving.  
  
> [!NOTE]
>  De kleurencodering is niet beschikbaar voor codediagrammen en ringdiagrammen. Deze diagrammen worden op het dashboard in witte, grijze en donkere tinten weergegeven.  
  
1.  Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).  
2.  Vouw onder **Onderdelen** achtereenvolgens **Entiteiten** en de gewenste entiteit uit. Als de gewenste entiteit niet wordt weergegeven, selecteert u **Bestaande toevoegen** om de entiteit toe te voegen.  
  
3.  Selecteer in het navigatiedeelvenster de optie **Velden**. Dubbelklik in het raster op het veld waarvoor u de kleur wilt configureren.  
  
4.  Selecteer op het tabblad **Algemeen** in het subgebied **Type** **Ja** en selecteer vervolgens **Bewerken**.  
  
5.  Als het dialoogvenster **Lijstwaarde wijzigen** wordt weergegeven, stelt u de nieuwe waarde in het tekstvak **Kleur** in. Selecteer **OK**.  
  
     Kies **Opslaan en sluiten**.  
  
7.  Selecteer **Publiceren** om de wijzigingen van kracht te laten worden.  
  
In het volgende voorbeeld wijzigen we de kleur voor het veld **IsEscalated**. Gebruik de knop **Bewerken** om het dialoogvenster **Lijstwaarde wijzigen** te openen:  
 
 > [!div class="mx-imgBorder"] 
 > ![Kleur wijzigen in het dashboard](../model-driven-apps/media/interactive-dashboards-change-color-edit-button.PNG "Kleur wijzigen in het dashboard")  
  
Als het dialoogvenster **Lijstwaarde wijzigen** wordt weergegeven, kiest u de kleur, zoals weergegeven:  
  
 ![De dashboardkleur wijzigen](../model-driven-apps/media/interactive-dashboards-modify-color-value.png "De dashboardkleur wijzigen")  
  
### <a name="next-steps"></a>Volgende stappen  
 
[Dashboards maken of bewerken](create-edit-dashboards.md)
 

