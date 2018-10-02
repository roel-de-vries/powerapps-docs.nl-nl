---
title: Rasters van modelgestuurde apps (lijsten) bewerkbaar maken met het aangepaste besturingselement Bewerkbaar raster met PowerApps | MicrosoftDocs
description: Lees hoe u het aangepaste besturingselement Bewerkbaar raster kunt gebruiken
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: cefbc0c2-769b-4230-ab5a-b28a84630a42
caps.latest.revision: 8
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="make-model-driven-app-grids-lists-editable-using-the-editable-grid-custom-control"></a>Rasters van modelgestuurde apps (lijsten) bewerkbaar maken met het aangepaste besturingselement Bewerkbaar raster

In eerdere versies van Dynamics CRM konden gebruikers niet rechtstreeks gegevens invoeren in rasters (ook wel aangeroepen lijsten) of subrasters van formulieren. Zij moesten op record in het raster selecteren om een formulier te openen, de gegevens bewerken en opslaan, wat meerdere stappen vereiste. Met bewerkbare rasters kunnen gebruikers de opmaak rechtstreeks in-line bewerken vanuit rasters en subrasters wanneer zij een web-app,telefoon of tablet gebruiken.  
  
 ![Voorbeelden bewerkbare rasters](media/editable-grid-examples.png "Voorbeelden bewerkbare rasters")  
  
 Wanneer bewerkbare rasters door het besturingselement Bewerkbare rasters zijn ingeschakeld, kunnen gebruikers de meeste veldtypen, inclusief basisopzoekvelden en optiesets, bewerken.  

**Bewerkbare rasters ondersteunen:**
  
-   Inline bewerken van records op het entiteits- of subrasterniveau (inclusief aangepaste entiteiten)  
  
-   Systeemweergaven en persoonlijke weergaven  
  
-   Web- en mobiele clients  
  
-   Navigatie met een toetsenbord of de muis  
  
-   Groeperen en sorteren (u kunt groeperen/sorteren op elke kolom in de huidige weergave)  
  
-   Filteren  
  
-   Kolommen verplaatsen en het formaat wijzigen  
  
-   Paginering  
  
-   Wijzigingen van de ene naar de andere sessie opslaan voor groeperen, sorteren, filteren, paginering en het verplaatsen en formaat wijzigen van de kolommen  
  
-   Opzoekconfiguratie  
  
-   Berekende velden en roll-upvelden  
  
-   Bedrijfsregels (foutbericht weergeven, veldwaarde instellen, vereisen van onderneming instellen, standaardwaarde instellen, veld vergrendelen of ontgrendelen)  
  
-   JavaScript-gebeurtenissen  
  
-   Het inschakelen of uitschakelen van cellen op basis van beveiligingsrol  
  
-   Gebruikers kunnen zoekopdrachten en grafieken blijven gebruiken en hebben toegang tot de actiebalk met alleen-lezen rasters  
  
## <a name="make-main-grids-editable"></a>Hoofdrasters bewerkbaar maken  
  
1.  Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).  
  
2.  Open in de lijst **Entiteiten** de betreffende entiteit, selecteer het tabblad **Besturingselementen** en selecteer vervolgens **Besturingselement toevoegen**.  
  
     ![Aangepast besturingselement voor bewerkbaar raster toevoegen](media/add-editable-grids-custom-control.png "Aangepast besturingselement voor bewerkbaar raster toevoegen")  
  
3.  Selecteer in het dialoogvenster **Besturingselement toevoegen** de optie **Bewerkbaar raster** en selecteer vervolgens **Toevoegen**.  
  
4.  Selecteer in de toegevoegde rij **Bewerkbaar raster** de formulierfactor die u wilt toepassen in het raster. Hierdoor maakt u het besturingselement bewerkbaar raster tot het standaard besturingselement voor de geselecteerde formulierfactor(en).  
  
     ![De rij uit bewerkbaar raster met selectie van formulierfactor](media/editable-grid-row-wit-factor-selection.png "De rij uit bewerkbaar raster met selectie van formulierfactor")    

   > [!NOTE]
   >  Bij het uitvoeren kunnen gebruikers schakelen tussen bewerkbare rasters en alleen-lezen rasters.  
      
5.  Als u een opzoekactie wilt toevoegen, selecteert u in het groepsvak **Bewerkbaar raster** de optie **Opzoekveld toevoegen** en vervolgens in het dialoogvenster **Eigenschap configureren Opzoekveld toevoegen**:  
  
    1.  Selecteer in de lijst **Beschikbare weergaven** de weergave die u wilt toevoegen aan het opzoekveld (bijvoorbeeld **Mijn actieve accounts**).  
  
    2.  Selecteer in de lijst **Beschikbare kolommen** de opzoekkolom die u wilt toevoegen (bijvoorbeeld **Primaire contactpersoon**).  
  
    3.  Selecteer in de lijst **Standaardweergave** de gegevensbron voor het opzoekveld.  
  
    4.  Als u de weergegeven records wilt beperken, sschakelt u het selectievakje **Alleen records weergeven waar**, selecteert u de criteria in de lijst en selecteert u **OK**.  
  
         ![Opzoeken toevoegen besturingselement voor bewerkbare rasters](media/add-lookup-in-editable-grid-control.png "Opzoeken toevoegen besturingselement voor bewerkbare rasters")  
     
6.  Als u een genest raster hebt, selecteert u de potloodknop voor **Geneste rasterweergave** en selecteert u vervolgens de entiteit en weergave voor het geneste raster. Selecteer voor **Bovenliggende id van genest raster** de relatie voor de entiteiten. Het veld ParentAccountID-veld verbindt bijvoorbeeld de entiteiten **Account** en **Contactpersoon**.  
  
    > [!NOTE]
    >  De geneste rasters zijn alleen beschikbaar voor telefoons en tablets, niet voor internet.  
  
7.  Als u de gebruiker niet wilt toestaan om gegevens te groeperen op een kolom in de weergave (u wilt bijvoorbeeld ruimte besparen), selecteert u in de rij **Groeperen op kolom** de potloodknop en daarna in het dialoogvenster **Eigenschap confirugeren Groeperen op kolom** de optie **Uitgeschakeld**, waarna u **OK** selecteert.  
  
    > [!TIP]
    >  Dit is vooral handig voor subrasters in formulieren.  
  
8.  Als u JavaScript-gebeurtenissen wilt toevoegen, selecteert u het tabblad **Gebeurtenissen** en selecteert u vervolgens de benodigde entiteiten, velden en gebeurtenissen. Meer informatie: [Documentatie voor ontwikkelaars: Bewerkbare rasters gebruiken](/dynamics365/customer-engagement/developer/customize-dev/use-editable-grids-dynamics-365.md)  
  
     ![Gebeurtenissen toevoegen besturingselement voor bewerkbare rasters](media/add-events-in-editable-grid-control.png "Gebeurtenissen toevoegen besturingselement voor bewerkbare rasters")  
  
9. Selecteer **Opslaan** op de actiebalk om uw werk op te slaan.  
  
10. Wanneer u klaar bent om de wijzigingen aan uw team beschikbaar te stellen, selecteert u **Publiceren** op de actiebalk.  
  
11. Om uw wijzigingen te testen gaat u naar de weergave die u in stap 5 hebt ogpegeven, en brengt u in-line wijzigingen aan.  
  
## <a name="make-a-sub-grid-on-a-form-editable"></a>Een subraster bewerkbaar maken in een formulier

> [!NOTE] 
> - Als u een wijziging in een bewerkbaar raster wilt opslaan in een subraster, moet u expliciet opslaan voordat u het formulier verlaat.
> - Als u oude formulieren (versies voor Dynamics CRM 2016) gebruikt en een bewerkbaar raster in een subraster inschakelt, wordt het bewerkbare raster niet weergegeven. Systeembeheerders kunnen oude formulieren zo nodig uitschakelen in systeeminstellingen.
  
1.  Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).  
  
2.  Open het formulier dat het subraster bevat.  
  
3.  Selecteer het besturingselement en selecteer vervolgens **Eigenschappen wijzigen** op het lint.  
  
4.  Selecteer in het dialoogvenster **Eigenschappen instellen** de optie **Besturingselementen**, **Besturingselement toevoegen** en voer vervolgens de bovenstaande stappen uit.  
  
## <a name="supported-standard-entities"></a>Ondersteunde standaardentiteiten  
  
||||  
|-|-|-|  
|**Internet/tablet/telefoon**|**Alleen tablet/telefoon**|**Alleen internet**|  
|Account<br /><br /> Afspraak<br /><br /> Boekbare resource<br /><br /> Boeking van boekbare resources<br /><br /> Header boeking van boekbare resource<br /><br /> Categorie van boekbare resources<br /><br /> Toewijzing van categorie van boekbare resources<br /><br /> Kenmerk van boekbare resources<br /><br /> Boekbare resourcegroep<br /><br /> Boekingsstatus<br /><br /> Aanvraag<br /><br /> Categorie<br /><br /> Kenmerk<br /><br /> Concurrent<br /><br /> Contactpersoon<br /><br /> E-mail<br /><br /> Recht<br /><br /> Feedback<br /><br /> Factuur<br /><br /> Knowledge-artikel<br /><br /> Weergaven van Knowledge Base-artikelen<br /><br /> Knowledge Base-record<br /><br /> Potentiële klant<br /><br /> Verkoopkans<br /><br /> Order<br /><br /> Telefoongesprek<br /><br /> Prijslijst<br /><br /> Product<br /><br /> Wachtrij<br /><br /> Prijsopgave<br /><br /> Beoordelingsmodel<br /><br /> Beoordelingswaarde<br /><br /> SLA-KPI-exemplaar<br /><br /> Sociale activiteit<br /><br /> Sociaal profiel<br /><br /> Synchronisatiefout<br /><br /> Taak<br /><br /> Team<br /><br /> Gebruiker|Activiteit<br /><br /> Bijlage<br /><br /> Methodetoegangsprofielregelitem<br /><br /> Adres van concurrent<br /><br /> Verbinding<br /><br /> Verbindingsrol<br /><br /> E-mailhandtekening<br /><br /> E-mailsjabloon<br /><br /> Verlopen proces<br /><br /> Factuurproduct<br /><br /> Knowledge-artikel-incident<br /><br /> Verkoop voor potentiële klant naar verkoopkans<br /><br /> Proces<br /><br /> Postvak<br /><br /> Nieuw proces<br /><br /> Notitie<br /><br /> Verkoopkansproduct<br /><br /> Verkoopproces verkoopkans<br /><br /> Orderproduct<br /><br /> Organisatie<br /><br /> Telefoneren om aanvraag te verwerken<br /><br /> Prijslijstitem<br /><br /> Wachtrij-item<br /><br /> Offerteproduct<br /><br /> SharePoint-document<br /><br /> Vertaalproces|Campagne<br /><br /> Campagneactiviteit<br /><br /> Campagnerespons<br /><br /> Methodetoegangsprofiel<br /><br /> Methodetoegangsprofiel-regel<br /><br /> Contract<br /><br /> Rechtsjabloon<br /><br /> Externe partij<br /><br /> Fax<br /><br /> Brief<br /><br /> Marketinglijst<br /><br /> Positie<br /><br /> Snelle campagne<br /><br /> Terugkerende afspraak<br /><br /> Verkoopdocumentatie<br /><br /> SLA (Service Level Agreement)|  
 
##  <a name="data-types-that-arent-editable-in-an-editable-grid"></a>Gegevenstypen die niet bewerkbaar zijn in een bewerkbaar raster
De volgende gegevenstypen kunnen niet worden bewerkt in bewerkbare rasters: opzoekvelden Klant en Partylist; Samengestelde (adres)velden; statusvelden; aan de entiteit van de opzoekweergave gerelateerde velden (bijvoorbeeld bij de opzoekweergave Contactpersonen voor de entiteit Account is het veld Contactpersoon bewerkbaar, maar E-mailadres (contactpersoon) niet).  
 
## <a name="next-steps"></a>Volgende stappen  
 [Sneltoetsen gebruiken in bewerkbare rasters](https://docs.microsoft.com/dynamics365/customer-engagement/basics/keyboard-shortcuts#editable-grids-views)

