---
title: De weergave van hoofdformulieren voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Lees hoe hoofdformulieren worden gepresenteerd wanneer deze op verschillende apparaten worden weergegeven
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: da3ac59a-5413-46cb-b355-1987e42e3853
caps.latest.revision: 35
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="how-model-driven-app-main-forms-appear-on-different-devices"></a>Hoe hoofdformulieren voor modelgestuurde apps worden weergegeven op verschillende apparaten

Het hoofdformulier wordt gebruikt door alle modelgestuurde app-clients. Dit formulier biedt een consistente gebruikerservaring, of iemand nu een webbrowser, Dynamics 365 for phones, Dynamics 365 for tablets of Dynamics 365 for Outlook gebruikt.  
  
<a name="BKMK_MainFormPresentations"></a>   
## <a name="main-forms"></a>Hoofdformulieren  
 Hoofdformulieren die voor een entiteit bestaan kunnen verschillend worden weergegeven, afhankelijk van de factoren in de onderstaande tabel. Wanneer u een hoofdformulier ontwerpt, bedenk hoe dit in verschillende presentaties werkt.  
  
|Presentatie|Beschrijving|  
|------------------|-----------------|  
|**Bijgewerkt**|Voor [Bijgewerkte entiteiten en klassieke entiteiten](create-design-forms.md#updated-versus-classic-entities) en alle aangepaste entiteiten in Dynamics 365 (online) en Dynamics 365 On-premises biedt het bijgewerkte formulier een nieuwe gebruikerservaring. Deze formulieren beschikken over het nieuwere opdrachtbalkontwerp en maken extra functies mogelijk, zoals automatisch opslaan en bedrijfsprocesstromen.|  
|**Dynamics 365 for tablets**| Dynamics 365 for tablets presenteert de inhoud van het hoofdformulier op een wijze die voor een tablet is geoptimaliseerd.|  
|**Dynamics 365 for phones**| Dynamics 365 for phones presenteert de inhoud van het hoofdformulier op een wijze die voor een telefoon is geoptimaliseerd.|  
|**Klassiek**|Deze formulieren zijn voor de entiteiten die niet zijn bijgewerkt. Ze gebruiken het lint en niet de opdrachtbalk en het navigatiedeelvenster aan de linkerkant van het formulier.<br /><br /> Deze formulieren hebben een indeling in twee kolommen.|  
  
<a name="BKMK_MainFormComponentsForUpdatedEntities"></a>   
## <a name="updated-forms"></a>Bijgewerkte formulieren  
 Dit diagram geeft algemene onderdelen weer die in bijgewerkte entiteitsformulieren werden gevonden.  
  
 ![In het diagram wordt de bijgewerkte entiteitsformulierstructuur in Dynamics 365 weergegeven](media/updated-form-diagram.png "In het diagram wordt de bijgewerkte entiteitsformulierstructuur in Dynamics 365 weergegeven")  
  
 De indeling van het formulier werkt voor aangepaste entiteiten met een brede reeks van weergaven en venstergrootten. Naarmate de breedte van het venster vermindert, verplaatsen tabbladkolommen naar beneden zodat u naar beneden kunt schuiven om met ze te werken en ze niet hoeft te verkleinen of naar rechts moet te schuiven.  
  
 In de volgende tabel worden beschikbare onderdelen van het hoofdformulier voor bijgewerkte entiteiten samengevat.  
  
|Onderdeel|Overzicht|  
|---------------|-------------|  
|**Navigatiebalk**|Maakt gebruik van de gegevens in het siteoverzicht om de mogelijkheid te bieden om naar andere gebieden van de toepassing te verplaatsen.<br /><br /> Het navigatiedeelvenster dat in de klassieke formulieren wordt gebruikt is niet opgenomen in het bijgewerkte formulier. In de context van een record, biedt de navigatiebalk toegang tot weergaven van gerelateerde records. In plaats van te navigeren naar gerelateerde records met behulp van het navigatiedeelvenster of door de navigatiebalk te gebruiken, biedt het toevoegen van subrasters die zijn geconfigureerd om nuttige gerelateerde entiteitsrecords te tonen een betere ervaring voor de meeste mensen.|  
|**Opdrachtbalk**|Gebruikt de gegevens die zijn gedefinieerd voor linten om opdrachten die relevant zijn voor de record te verschaffen.<br /><br /> De eerste vijf opdrachten worden weergegeven gevolgd door een beletselteken (![Meer opdrachtknop](media/not-available.gif "Meer opdrachtknop")) dat een flyoutmenu biedt om bijkomende opdrachten te kiezen.|  
|**Afbeelding**|Wanneer een entiteit een afbeeldingveld heeft en de optie in de entiteit **Primaire afbeelding** is ingesteld op **Standaardafbeelding**, kan een afbeelding in de koptekst worden weergegeven wanneer het formulier wordt geconfigureerd om de afbeelding weer te gegeven.|  
|**Koptekst**|Velden die zijn geplaatst ik de koptekst blijven zichtbaar wanneer mensen naar beneden schuiven door de hoofdtekst van het formulier.<br /><br /> Maximaal vier velden kunnen in de koptekst worden geplaatst. Meerdere tekstregels, webresources, of iFrames zijn niet toegestaan in de koptekst. De kop- en voettekst delen enkele eigenschappen met paragrafen.|  
|**Procesbesturingselement**|Wanneer een entiteit actieve bedrijfsprocesstromen heeft, geeft het procesbesturingselement de onderstaande koptekst weer. Meer informatie: [Bedrijfsprocesstromen](/flow/business-process-flows-overview)|  
|**Tekst**|De hoofdtekst is het schuifbare deel van het formulier dat het tabblad bevat.|  
|**Tabbladen**|In de hoofdtekst van het formulier bieden tabbladen horizontale scheiding. Tabbladen hebben een label dat kan worden weergegeven. Als het label wordt weergegeven, kunnen tabbladen worden uitgevouwen of samengevouwen om de inhoud weer te geven of te verbergen door het label te selecteren.<br /><br /> Tabbladen bevatten maximaal drie kolommen en de breedte van elke kolom kan op een percentage van de totale breedte worden ingesteld. Als u een nieuw tabblad maakt, dan wordt elke kolom ingevuld met een sectie.|  
|**Secties**|Een sectie neem de ruimte in beslag die beschikbaar is in een tabbladkolom. Secties hebben een label dat kan worden weergegeven en een regel kan onder het label worden weergegeven.<br /><br /> Secties kunnen maximaal 4 kolommen hebben en bevatten opties om weer te geven hoe labels voor velden in de sectie worden weergegeven.|  
|**Velden**|Velden geven de besturingselementen weer die mensen gebruiken om gegevens in een entiteitsrecord weer te geven of te bewerken. Velden kunnen zo worden opgemaakt dat ze maximaal vier kolommen binnen een sectie in beslag nemen.|  
|**Opvulling**|Met een opvulling kunt een een lege ruimte toevoegen aan een sectiekolom.|  
|**Subrasters**|U kunt met subrasters lijst in het formulier weergeven. De mogelijkheid om diagrammen weer te geven met een subraster is niet beschikbaar voor bijgewerkte entiteiten.|  
|**Snelle-weergaveformulier**|Een snelle-weergaveformulier geeft gegevens weer van een record die is gekoppeld aan een opzoekveld op het formulier. De entiteit die het doel is van het opzoekveld moet een snelle-weergaveformulier hebben voordat er een kan worden toegevoegd aan het formulier. Meer informatie: [Snelle-weergaveformulieren maken en bewerken](create-edit-quick-view-forms.md)|  
|**Webresources**|HTML- en Microsoft Silverlight-webresources kunnen worden toegevoegd aan hoofdformulieren, maar ze worden niet weergegeven bij gebruik van Dynamics 365 for phones en Dynamics 365 for tablets.|  
|**iFrame**|Een inline-frame dat u configureert om een webpagina van een andere website te tonen. **Belangrijk:**  <ul><li>Wanneer de pagina wordt weergegeven in een iFrame in een ander domein, passen browsers een hoger niveau van beveiliging toe. Dit kan de vereisten compliceren voor de inhoud van een iFrame om te communiceren met gegevens in het formulier.</li><li>Het weergeven van een entiteitsformulier in een iFrame ingesloten in een ander entiteitsformulier wordt niet ondersteund. 
|**Bing-kaarten**|Wanneer dit besturingselement aanwezig is in een formulier voor een bijgewerkte entiteit en de systeeminstelling **Bing-kaarten inschakelen** is ingeschakeld met een geldige Bing Maps-sleutel, kan dit besturingselement eenmaal worden gebruikt in een formulier om de locatie voor een van de adressen een bijgewerkte entiteit te tonen. Meer informatie: [Bing-kaarten configureren](configure-bing-maps-legacy.md)|  
|**Voettekst**|Ieder aantal velden, webresources of iFrames kan aan de voettekst worden toegevoegd. Velden zijn alleen-lezen wanneer ze worden weergegeven in de voettekst. De kop- en voettekst delen enkele eigenschappen met paragrafen.|  
|**Statusbalk**|De statusbalk geeft het statusveld voor de record, een systeemvak en een knop voor opslaan weer.|  
  
<a name="BKMK_CRMforTabletsPresentation"></a>   
## <a name="dynamics-365-for-phones-and-tablets-forms"></a>Formulieren in Dynamics 365 voor telefoons en tablets  
 De meeste systeementiteiten en aangepaste entiteiten zijn beschikbaar voor Dynamics 365 for phones en Dynamics 365 for tablets. Het hoofdformulier voor deze entiteiten wordt getransformeerd tot een presentatie die voor telefoons of tablets is geoptimaliseerd.  
  
<a name="BKMK_EntitiesEnabledForCRMForTablets"></a>   
### <a name="entities-enabled-for-dynamics-365-for-phones-and-tablets"></a>Entiteiten die zijn ingeschakeld voor Dynamics 365 voor telefoons en tablets  
 Alleen entiteiten die voor Dynamics 365 for phones en Dynamics 365 for tablets zijn ingeschakeld, gebruiken deze presentatie van het hoofdformulier. Meer informatie: [Entiteiten die in Dynamics 365 for phones en tablets worden weergegeven](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_CustomEntity)  
  
### <a name="form-design"></a>Formulierontwerp  
 In Dynamics 365 for phones en Dynamics 365 for tablets worden veel van de hoofdformulierelementen gebruikt en op een wijze gepresenteerd die is geoptimaliseerd voor telefoons en tablets. De volgende diagrammen laten zien hoe de webapp zich verhoudt tot de apps voor tablets en telefoons.  
  
 **Webapp**  
  
 ![Dynamics 365 formulierterugstroom vanuit webapp](media/custon-reflow-web-app.png "Dynamics 365 formulierterugstroom vanuit webapp")  
  
 **App voor tablets**  
  
 ![Dynamics 365 formulierterugstroom naar tablet-app](media/reflow-tablet-app.png "Dynamics 365 formulierterugstroom naar tablet-app")  
  
 **App voor telefoons**  
  
 ![Dynamics 365 formulierterugstroom naar telefoon-app](media/custon-reflow-phone-app.png "Dynamics 365 formulierterugstroom naar telefoon-app")  
  
 De formulierelementen zijn getransformeerd tot een breed panorama in Dynamics 365 for tablets, waarin gebruikers over het scherm kunnen vegen om elementen te wijzigen die in een weergavepoort zichtbaar zijn. In Dynamics 365 for phones vegen gebruikers over het scherm om een andere kolom of een ander deelvenster met elementen te bekijken en de procesbesturing vindt plaats voor elke kolom.  
  
### <a name="view-port-element"></a>Weergavepoortelement  
 De volgens items zijn altijd zichtbaar in de weergavepoort in de context van een formulier:  
  
 **Navigatiebalk**  
 De navbalk een presentatie van het siteoverzicht dat voor aanraken is geoptimaliseerd. Meer informatie: [Navigatieopties wijzigen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_NavigationOptions)  
  
 **Start**  
 Met de startknop gaan gebruikers naar het dashboard. Dat is de startpagina voor Dynamics 365 for phones en Dynamics 365 for tablets.  
  
 **Procesbesturingselement**  
 Wordt voor de entiteit een bedrijfsproces ingeschakeld, dan wordt dit in de rechterbovenhoek naast de zoekoptie weergegeven in Dynamics 365 for tablets en boven aan het scherm in Dynamics 365 for phones.  
  
 **Zoeken**  
 Gebruikers kunnen het zoekbesturingselement in de rechterbovenhoek aantikken om het scherm voor het zoeken naar records te openen.  
  
 **Opdrachtbalk**  
 Standaard worden sommige opdrachten die in de app worden uitgevoerd in een webbrowser niet weergegeven in de apps Dynamics 365 for phones en Dynamics 365 for tablets. Op vergelijkbare wijze als de webtoepassing, is de opdrachtbalk contextafhankelijk, zodatu de beschikbare opdrachten variëren, afhankelijk van wat er op dat moment wordt weergegeven of geselecteerd. Meer informatie [Opdrachten wijzigen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_ChangeCommands)  
  
### <a name="form-elements"></a>Formulierelementen  
 De weergegeven formulierelementen worden gehaald uit het hoofdformulier en als een reeks panelen weergegeven die gebruikers door de weergavepoort zien.  
  
 In Dynamics 365 for tablets worden in het eerste deelvenster contactgegevens weergegeven over relaties die voor de record bestaan. In Dynamics 365 for phones bevat het eerste deelvenster tevens koptekstvelden uit het formulier boven de relatietegels.  
  
 ![Deelvenster relaties Dynamics 365 voor tablets](media/mobile-app-form-relationships.png "Deelvenster relaties Dynamics 365 voor tablets")  
  
 Voor formulieren Contactpersoon en Gebruiker, geeft het hoogste item een communicatiekaart voor de record weer. De communicatiekaart verschaft knoppen om communicatie met de persoon te beginnen. Voor andere entiteiten wordt een communicatiekaart weergegeven indien er een snelle-weergaveformulier Contactpersoon in het hoofdformulier is ingesloten.  
  
 U kunt aanvullende tegels weergeven op basis van entiteitsrelaties, maar u kunt de tegels niet aanpassen voor de volgende entiteiten:  
  
|Entiteit|Tegels|  
|------------|-----------|  
|Account|Eigenaar|  
|Contactpersoon|Bedrijfsnaam, eigenaar|  
|Potentiële klant|Eigenaar|  
|Kans|Account, eigenaar|  
  
 U kunt de resterende tegels aanpassen met de formuliereneditor. De volgorde is vast, maar u kunt wel instellen welke elementen zichtbaar zijn in het relatiedeelvenster.  
  
 In Dynamics 365 for tablets begint het tweede deelvenster met de naam van het eerste tabblad op het formulier. Alle velden in de koptekst zijn opgenomen op het eerste tabblad. In Dynamics 365 for phones verschijnen kopteksten in de eerste kolom.  
  
 ![Formulier eerste deelvenster CRM voor tablets](media/mobile-app-form-first-panel.png "Formulier eerste deelvenster CRM voor tablets")  
  
 Als er een processtroom actief is voor het formulier, worden op het derde tabblad taken voor de huidige fase van het proces in Dynamics 365 for tablets weergegeven. In Dynamics 365 for phones wordt de procesbesturing boven de deelvensters weergegeven en bij selectie over het huidige deelvenster van de gebruiker uitgevouwen. De procesbesturing is altijd zichtbaar en bruikbaar.  
  
 De resterende deelvensters van het formulier bevatten de inhoud van de tabbladen op het formulier. Alle gevonden subrasters worden weergegeven als een afzonderlijk deelvenster.  
  
 Het formulier voor Dynamics 365 for phones en Dynamics 365 for tablets bevat altijd de labels voor tabbladen en subrasters. De instelling **Label in het formulier weergeven** wordt niet toegepast.  
  
> [!NOTE]
>  Teneinde de prestaties op mobiele apparaten te optimaliseren, is het aantal objecten beperkt tot 5 tabbladen of 75 velden en 10 subrasters.  
  
 Formulieren voor Dynamics 365 for phones en Dynamics 365 for tablets bieden geen ondersteuning voor het volgende:  
   
-   Bing-kaarten  
  
-   Yammer
  
-   Activiteitsfeeds  
  
-   Themagebruik  
  
 Bovendien, zijn entiteitafbeeldingen zichtbaar in lijstweergaven en visitekaartjes, maar niet in het werkelijke formulier.  
  
<a name="BKMK_MultipleForms"></a>   
### <a name="multiple-forms"></a>Meerdere formulieren  
 Dynamics 365 for phones en Dynamics 365 for tablets ondersteunen meerdere formulieren maar bieden voor gebruikers geen manier om tussen formulieren te schakelen als ze toegang tot meerdere formulieren hebben. Men zal het eerste formulier in de formuliervolgorde zien waartoe ze toegang hebben.  
  
 Als u bijvoorbeeld de volgende hoofdformulieren voor de verkoopkansentiteit hebt en de volgende beveiligingsrollen voor alle hebt toegewezen, dan zult u de formuliervolgorde zien die in de volgende tabel wordt weergegeven.  
  
|Formuliervolgorde|Formuliernaam|beveiligingsrollen|  
|----------------|---------------|--------------------|  
|1|**Verkoopformulier 1**|verkoper|  
|2|**Verkoopformulier 2**|Verkoper en verkoopdirecteur|  
|3|**Verkoopformulier 3**|Verkoopdirecteur|  
|4|**Verkoopformulier 4**|Adjunct-directeur van Verkoop|  
  
-   De gebruiker met de rol Verkoper zal altijd **Verkoopformulier 1** zien.  
  
-   De gebruiker met de rol Verkoopdirecteur zal altijd **Verkoopformulier 2** zien.  
  
-   De gebruiker met de rol Adjunct-directeur van verkoop zal altijd **Verkoopformulier 4** zien.  
  
<a name="BKMK_ClassicPresentation"></a>   
## <a name="classic-forms"></a>Klassieke formulieren  
 Het volgende diagram toont de hoofdformulieronderdelen die in de klassieke weergave worden gebruikt.  
  
 ![Belangrijkste formulierelementen](media/elements.png "Belangrijkste formulierelementen")  
  
 De formulieren voor bijgewerkte entiteiten hebben vele onderdelen van de klassieke formulieren overgenomen, maar er zijn significante verschillen.  
  
 Formulieren die de klassieke weergave gebruiken bevatten geen navigatiebalk en het lint wordt gebruikt in plaats van de opdrachtbalk. Deze formulieren ondersteunen geen entiteitafbeeldingen, procesbesturingselementen, snelle-weergaveformulieren of Bing Maps. Velden in de koptekst zijn niet bewerkbaar.  
  
 De formulierenassistent wordt blootgesteld voor bepaalde entiteiten, zoals `Article`.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Formulieren maken en ontwerpen](create-design-forms.md)   

 
