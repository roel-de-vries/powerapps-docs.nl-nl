---
title: Presentaties van hoofdformulieren in modelgestuurde apps in PowerApps | MicrosoftDocs
description: Informatie over hoe hoofdformulieren worden weergegeven op verschillende apparaten
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
ms.openlocfilehash: b8dee40f6dbeba62128434b3eb122add9cb0b373
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674663"
---
# <a name="how-model-driven-app-main-forms-appear-on-different-devices"></a>Hoe hoofdformulieren van modelgestuurde apps op verschillende apparaten worden weergegeven

Het hoofdformulier wordt gebruikt door alle clients van modelgestuurde apps. Dit formulier biedt een consistente gebruikerservaring ongeacht of iemand een webbrowser, Dynamics 365 voor telefoons, Dynamics 365 voor tablets of Dynamics 365 voor Outlook gebruikt.  
  
<a name="BKMK_MainFormPresentations"></a>   
## <a name="main-forms"></a>Hoofdformulieren  
 Alle hoofdformulieren van een entiteit kunnen anders worden weergegeven, afhankelijk van de factoren in de onderstaande tabel. Houd bij het ontwerpen van een hoofdformulier rekening met hoe het werkt in de verschillende presentaties.  
  
|Presentatie|Beschrijving|  
|------------------|-----------------|  
|**Bijgewerkt**|Voor de [Bijgewerkte entiteiten en klassieke entiteiten](create-design-forms.md#updated-versus-classic-entities) en eventuele aangepaste entiteiten in Dynamics 365 (online) en Dynamics 365 on-premises, zorgt het bijgewerkte formulier voor een nieuwe gebruikerservaring. Deze formulieren hebben het nieuwere ontwerp voor de opdrachtbalk en bieden extra functies zoals automatisch opslaan en bedrijfsprocesstromen.|  
|**Dynamics 365 voor tablets**| Dynamics 365 voor tablets geeft de inhoud van het hoofdformulier weer op een manier die is geoptimaliseerd voor een tablet.|  
|**Dynamics 365 voor telefoons**| Dynamics 365 voor telefoons geeft de inhoud van het hoofdformulier weer op een manier die is geoptimaliseerd voor een telefoons.|  
|**Klassiek**|Deze formulieren zijn voor de entiteiten die niet zijn bijgewerkt. Ze gebruiken het lint in plaats van de opdrachtbalk en het navigatievenster aan de linkerkant van het formulier.<br /><br /> Deze formulieren hebben een indeling in twee kolommen.|  
  
<a name="BKMK_MainFormComponentsForUpdatedEntities"></a>   
## <a name="updated-forms"></a>Bijgewerkte formulieren  
 Dit diagram bevat de algemene onderdelen van bijgewerkte entiteitsformulieren.  
  
 ![Diagram toont Structuur van bijgewerkte entiteitsformulieren in Dynamics 365](media/updated-form-diagram.png "Diagram toont Structuur van bijgewerkte entiteitsformulieren in Dynamics 365")  
  
 Voor bijgewerkte entiteiten werkt de indeling van het formulier met een breed scala aan weergaven en venstergrootten. Naarmate de breedte van het venster afneemt, worden de tabbladkolommen omlaag verplaatst zodat u naar beneden kunt schuiven om ermee te werken, in plaats van dat ze worden gecomprimeerd of u naar rechts moet schuiven.  
  
 De volgende tabel geeft een overzicht van de beschikbare onderdelen van het hoofdformulier voor bijgewerkte entiteiten.  
  
|Component|Samenvatting|  
|---------------|-------------|  
|**Navigatiebalk**|Deze gebruikt de gegevens in de sitemap om de mogelijkheid te bieden naar verschillende delen van de toepassing te gaan.<br /><br /> Het navigatievenster dat in klassieke formulieren wordt gebruikt, is niet opgenomen in het bijgewerkte formulier. In de context van een record biedt de navigatiebalk toegang tot weergaven van gerelateerde records. In plaats van naar verwante records te navigeren met behulp van het navigatievenster of door de navigatiebalk te gebruiken, biedt het toevoegen van subrasters die zijn geconfigureerd om nuttige gerelateerde entiteitsrecords weer te geven, voor de meeste mensen een betere ervaring.|  
|**Opdrachtbalk**|Deze gebruikt de gegevens die zijn gedefinieerd voor linten om voor de record relevante opdrachten te leveren.<br /><br /> De eerste vijf opdrachten worden weergegeven gevolgd door een beletselteken (![Knop Meer opdrachten](media/not-available.gif "Knop Meer opdrachten")) die een vervolgmenu biedt voor het kiezen van extra opdrachten.|  
|**Afbeelding**|Wanneer een entiteit een afbeeldingsveld heeft en de entiteit **Primaire afbeelding** is ingesteld op **Standaardafbeelding**, kan een afbeelding in de header worden weergegeven wanneer het formulier is geconfigureerd om de afbeelding weer te geven.|  
|**Header**|Velden in de header blijven zichtbaar wanneer mensen door de hoofdtekst van het formulier naar beneden schuiven.<br /><br /> U kunt maximaal vier velden in de header plaatsen. Meerdere regels tekst, webresources of iFrames zijn niet toegestaan in de header. De kop- en voettekst delen enkele eigenschappen met secties.|  
|**Procesbeheer**|Wanneer een entiteit actieve bedrijfsprocesstromen heeft, wordt het procesbesturingselement weergegeven onder de header. Meer informatie: [Overzicht bedrijfsprocesstromen](/flow/business-process-flows-overview)|  
|**Hoofdtekst**|Het hoofdgedeelte is het schuifbare deel van het formulier dat de tabbladen bevat.|  
|**Tabbladen**|In de hoofdtekst van het formulier bieden tabbladen horizontale scheiding. Tabbladen hebben een label dat kan worden weergegeven. Als het label wordt weergegeven, kunt u dit label selecteren om de tabbladen uit te vouwen of samen te vouwen en de inhoud weer te geven of te verbergen.<br /><br /> Tabbladen bevatten maximaal drie kolommen en de breedte van elke kolom kan worden ingesteld op een percentage van de totale breedte. Wanneer u een nieuw tabblad maakt, wordt elke kolom vooraf gevuld met een sectie.|  
|**Secties**|Een sectie neemt de beschikbare ruimte in een tabbladkolom in beslag. Secties hebben een label dat kan worden weergegeven en er kan een regel worden weergegeven onder het label.<br /><br /> Secties kunnen maximaal vier kolommen bevatten en opties bieden om weer te geven hoe labels voor velden in de sectie worden weergegeven.|  
|**Velden**|Velden geven besturingselementen weer die mensen gebruiken om gegevens in een entiteitsrecord te bekijken of te bewerken. Velden kunnen zo worden opgemaakt dat deze maximaal vier kolommen in een sectie bevatten.|  
|**Tussenruimte**|Met een tussenruimte kunt u een lege ruimte toevoegen aan een sectiekolom.|  
|**Subrasters**|Met een subraster kan een lijst in het formulier worden weergegeven. De mogelijkheid om diagrammen weer te geven via een subraster is niet beschikbaar in formulieren voor bijgewerkte entiteiten.|  
|**Formulier voor snelle weergave**|In een formulier voor snelle weergave worden gegevens weergegeven van een record waarnaar wordt verwezen door een opzoekveld in het formulier. De entiteit die het doel van de zoekopdracht is, moet een formulier voor snelle weergaven hebben voordat deze aan het formulier kan worden toegevoegd. Meer informatie: [Formulieren voor snelle weergave maken en bewerken](create-edit-quick-view-forms.md)|  
|**Webresources**|HTML- en Microsoft Silverlight-webresources kunnen worden toegevoegd aan hoofdformulieren, maar ze worden niet weergegeven bij het gebruik van Dynamics 365 voor telefoons en tablets.|  
|**iFrame**|Een inline-frame dat u configureert om een webpagina van een andere website weer te geven. **Belangrijk:**  <ul><li>Wanneer de pagina die wordt weergegeven in een iFrame zich in een ander domein bevindt, wordt in browsers een hoger beveiligingsniveau toegepast. Hierdoor kunnen strengere vereisten worden gesteld aan de inhoud van een iFrame voor de interactie met gegevens in het formulier.</li><li>Het weergeven van een entiteitsformulier in een iFrame dat is ingesloten in een ander entiteitsformulier, wordt niet ondersteund. 
|**Bing Kaarten**|Wanneer dit besturingselement aanwezig is in een formulier voor een bijgewerkte entiteit en de systeeminstelling **Bing Kaarten inschakelen** is ingeschakeld met een geldige Bing Kaarten-sleutel, kan dit besturingselement één keer in een formulier worden gebruikt om de locatie weer te geven van een van de adressen in een bijgewerkte entiteit. Meer informatie: [Bing Kaarten configureren](configure-bing-maps-legacy.md)|  
|**Voettekst**|Er kan een willekeurig aantal velden, webresources of iFrames worden toegevoegd aan de voettekst. Velden die worden weergegeven in de voettekst zijn alleen-lezen. De kop- en voettekst delen enkele eigenschappen met secties.|  
|**Statusbalk**|De statusbalk toont het statusveld voor de record, een systeemvak en een knop voor opslaan.|  
  
<a name="BKMK_CRMforTabletsPresentation"></a>   
## <a name="dynamics-365-for-phones-and-tablets-forms"></a>Formulieren in Dynamics 365 voor telefoons en tablets  
 De meeste systeementiteiten en aangepaste entiteiten zijn beschikbaar voor Dynamics 365 voor telefoons en tablets. Het hoofdformulier voor deze entiteiten wordt omgezet in een presentatie die is geoptimaliseerd voor telefoons of tablets.  
  
<a name="BKMK_EntitiesEnabledForCRMForTablets"></a>   
### <a name="entities-enabled-for-dynamics-365-for-phones-and-tablets"></a>Ingeschakelde entiteiten voor Dynamics 365 voor telefoons en tablets  
 Alleen entiteiten die zijn ingeschakeld voor Dynamics 365 voor telefoons en tablets maken gebruik van deze presentatie van het hoofdformulier. Meer informatie: [Weergegeven entiteiten in Dynamics 365 voor telefoons en tablets](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_CustomEntity)  
  
### <a name="form-design"></a>Formulierontwerper  
 Dynamics 365 voor telefoons en tablets bevat veel van de elementen van het hoofdformulier en presenteert deze op een manier die is geoptimaliseerd voor telefoons of tablets. De volgende diagrammen tonen de dynamische aanpassing van de web-app naar de tablet- en telefoon-apps.  
  
 **Web-app**  
  
 ![Dynamische aanpassing van formulier van web-app in Dynamics 365](media/custon-reflow-web-app.png "Dynamische aanpassing van formulier van web-app in Dynamics 365")  
  
 **Tablet-app**  
  
 ![Dynamische aanpassing van formulier naar tablet-app in Dynamics 365](media/reflow-tablet-app.png "Dynamische aanpassing van formulier naar tablet-app in Dynamics 365")  
  
 **Telefoon-app**  
  
 ![Dynamische aanpassing van formulier naar telefoon-app in Dynamics 365](media/custon-reflow-phone-app.png "Dynamische aanpassing van formulier naar telefoon-app in Dynamics 365")  
  
 De formulierelementen worden omgezet in een brede panorama-indeling in Dynamics 365 voor tablets, waarbij gebruikers over het scherm vegen om elementen te wijzigen die zichtbaar zijn in een weergavepoort. In Dynamics 365 voor telefoons vegen gebruikers over het scherm om een andere kolom of een deelvenster met elementen te zien, en wordt het procesbeheer voor elke kolom weergegeven.  
  
### <a name="view-port-element"></a>Element weergavepoort  
 De volgende items zijn altijd zichtbaar in de weergavepoort in de context van een formulier:  
  
 **Navigatiebalk**  
 De navigatiebalk is een presentatie van de sitemap die is geoptimaliseerd voor aanraking. Meer informatie: [Navigatieopties wijzigen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_NavigationOptions)  
  
 **Start**  
 De knop Start brengt gebruikers naar het dashboard dat de startpagina is voor Dynamics 365 voor telefoons en tablets.  
  
 **Procesbeheer**  
 Als voor de entiteit een bedrijfsproces is ingeschakeld, wordt dit weergegeven in de rechterbovenhoek naast het zoekbesturingselement in Dynamics 365 voor tablets, en bovenaan het scherm in Dynamics 365 voor telefoons.  
  
 **Zoeken**  
 Gebruikers kunnen op het besturingselement voor zoeken tikken om het zoekscherm voor records te openen.  
  
 **Opdrachtbalk**  
 Sommige van de opdrachten die worden weergegeven in de app die in een webbrowser wordt uitgevoerd, worden standaard niet weergegeven in Dynamics 365 voor telefoons en tablets. Net als bij de webtoepassing is de opdrachtbalk contextgevoelig, dus de beschikbare opdrachten zijn afhankelijk van wat er op dat moment wordt bekeken of geselecteerd. Meer informatie [Opdrachten wijzigen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/customize-phones-tablets#BKMK_ChangeCommands)  
  
### <a name="form-elements"></a>Formulierelementen  
 De weergegeven formulierelementen zijn afkomstig uit het hoofdformulier en worden gepresenteerd als een reeks panelen die gebruikers zien via de weergavepoort.  
  
 In Dynamics 365 voor tablets geeft het eerste paneel contactgegevens weer over relaties die voor de record bestaan. In Dynamics 365 voor telefoons geeft het eerste paneel ook headervelden weer vanuit het formulier boven de relatietegels.  
  
 ![Relatiepanelen in Dynamics 365 voor tablets](media/mobile-app-form-relationships.png "Relatiepanelen in Dynamics 365 voor tablets")  
  
 Voor contact- en gebruikersformulieren geeft het bovenste item een communicatiekaart voor de record weer. De communicatiekaart biedt knoppen om de communicatie met de persoon te starten. Voor andere entiteiten wordt een communicatiekaart weergegeven als er een formulier voor snelle weergave voor contact is ingesloten in het hoofdformulier.  
  
 U kunt aanvullende tegels weergeven op basis van relaties van entiteiten, maar u kunt de tegels voor de volgende entiteiten niet aanpassen:  
  
|Entiteit|Tegels|  
|------------|-----------|  
|Account|Owner|  
|Contact|Bedrijfsnaam, Eigenaar|  
|Lead|Owner|  
|Verkoopkans|Account, Eigenaar|  
  
 U kunt de resterende tegels aanpassen met de formuliereneditor. De volgorde is vast, maar u kunt instellen welke elementen zichtbaar zijn in het deelvenster relatie.  
  
 In Dynamics 365 voor tablets begint het tweede deelvenster met de naam van het eerste tabblad in het formulier. Alle velden die zijn opgenomen in de header worden opgenomen en vormen vervolgens de inhoud van het eerste tabblad. In Dynamics 365 voor telefoons worden headers in de eerste kolom weergegeven.  
  
 ![CRM voor tablets formulier eerste deelvenster](media/mobile-app-form-first-panel.png "CRM voor tablets formulier eerste deelvenster")  
  
 Als er een processtroom voor het formulier actief is, worden taken in het derde tabblad weergegeven voor de huidige fase van het proces in Dynamics 365 voor tablets. In Dynamics 365 voor telefoons zweeft het procesbeheer boven de deelvensters, wordt het groter boven het huidige deelvenster van de gebruiker wanneer het wordt geselecteerd en is het altijd zichtbaar en uitvoerbaar.  
  
 De overige panelen van het formulier bevatten de inhoud van de tabbladen in het formulier. Eventuele subrasters worden weergegeven als een apart paneel.  
  
 In het formulier van Dynamics 365 voor telefoons en tablets worden altijd de labels voor tabbladen en subrasters weergegeven. De instelling **Label weergeven op formulier** wordt niet toegepast.  
  
> [!NOTE]
>  Voor optimale prestaties op mobiele apparaten is het aantal objecten beperkt tot 5 tabbladen of 75 velden en 10 subrasters.  
  
 Formulieren voor Dynamics 365 voor telefoons en tablets bieden geen ondersteuning voor het volgende:  
   
-   Bing Kaarten  
  
-   Yammer
  
-   Activiteitsfeeds  
  
-   Thema 's  
  
 Daarnaast zijn entiteitsafbeeldingen zichtbaar in lijstweergaven en contactkaarten, maar niet in het daadwerkelijke formulier.  
  
<a name="BKMK_MultipleForms"></a>   
### <a name="multiple-forms"></a>Meerdere formulieren  
 Dynamics 365 voor telefoons en tablets biedt ondersteuning voor meerdere formulieren, maar biedt geen manier voor gebruikers om over te schakelen tussen formulieren als ze toegang hebben tot meerdere formulieren. Gebruikers zien het eerste formulier in de volgorde waarin ze toegang hebben.  
  
 Als u bijvoorbeeld de volgende hoofdformulieren voor de entiteit Verkoopkans hebt en de volgende beveiligingsrollen voor elke entiteit hebt toegewezen, is de volgorde van de formulieren zoals in de volgende tabel.  
  
|Formuliervolgorde|Formuliernaam|Beveiligingsrollen|  
|----------------|---------------|--------------------|  
|1|**Verkoopformulier één**|Verkoper|  
|2|**Verkoopformulier twee**|Verkoper en Verkoopmanager|  
|3|**Verkoopformulier drie**|Verkoopmanager|  
|4|**Verkoopformulier vier**|Adjunct-directeur verkoop|  
  
-   Personen met de rol Verkoper zien altijd **Verkoopformulier één**.  
  
-   Personen met de rol Verkoopmanager zien altijd **Verkoopformulier twee**.  
  
-   Personen met de rol Adjunct-directeur verkoop zien altijd **Verkoopformulier vier**.  
  
<a name="BKMK_ClassicPresentation"></a>   
## <a name="classic-forms"></a>Klassieke formulieren  
 Het volgende diagram toont de onderdelen van hoofdformulieren die worden gebruikt in de klassieke presentatie.  
  
 ![Onderdelen hoofdformulier](media/elements.png "Onderdelen hoofdformulier")  
  
 In de formulieren voor bijgewerkte entiteiten zijn veel onderdelen overgenomen uit de klassieke formulieren, maar er zijn belangrijke verschillen.  
  
 Formulieren die gebruikmaken van de klassieke presentatie bevatten niet de navigatiebalk en het lint wordt gebruikt in plaats van de opdrachtbalk. Deze formulieren ondersteunen geen entiteitsafbeeldingen, procesbeheer, formulieren voor snelle weergave, automatisch opslaan of Bing Kaarten. Velden in de header kunnen niet worden bewerkt.  
  
 De formulierenassistent is beschikbaar voor bepaalde entiteiten, zoals `Article`.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Formulieren maken en ontwerpen](create-design-forms.md)   

 
