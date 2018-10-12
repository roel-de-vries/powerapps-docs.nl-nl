---
title: Modelgestuurde app-rasters (lijsten) bewerkbaar maken met het aangepaste besturingselement voor bewerkbaar raster met PowerApps | MicrosoftDocs
description: Meer informatie over hoe u het aangepaste besturingselement voor bewerkbaar raster gebruikt
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
ms.openlocfilehash: 704280dbed2177ba9a5467e2897980f78c31b050
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680556"
---
# <a name="make-model-driven-app-grids-lists-editable-using-the-editable-grid-custom-control"></a>Modelgestuurde app-rasters (lijsten) bewerkbaar maken met het aangepaste besturingselement voor bewerkbaar raster

In eerdere versies van Dynamics CRM konden gebruikers gegevens niet rechtstreeks invoeren in rasters (soms ook wel lijsten genoemd) of subrasters op formulieren. Ze moesten de record in het raster selecteren om een formulier te openen, de gegevens bewerken en vervolgens opslaan; een handeling waarvoor meerdere stappen vereist waren. Met bewerkbare rasters kunnen gebruikers uitgebreide inline bewerkingen rechtstreeks vanuit rasters en subrasters uitvoeren, of ze nu een web-app, tablet of telefoon gebruiken.  
  
 ![Voorbeelden van bewerkbare rasters](media/editable-grid-examples.png "Voorbeelden van bewerkbare rasters")  
  
 Wanneer bewerkbare rasters worden ingeschakeld via het aangepaste besturingselement voor bewerkbare rasters, kunnen gebruikers de meeste typen velden bewerken, waaronder eenvoudige opzoekvelden en optiesets.  

**Ondersteuning voor bewerkbare rasters:**
  
-   Records op het niveau van de entiteit of het subraster (inclusief aangepaste entiteiten) inline bewerken  
  
-   Systeemweergaven en persoonlijke weergaven  
  
-   Clients voor web en mobiel  
  
-   Navigatie met een toetsenbord of muis  
  
-   Groeperen en sorteren (u kunt groeperen/sorteren op elke kolom in de huidige weergave)  
  
-   Filteren  
  
-   Kolommen verplaatsen en het formaat ervan wijzigen  
  
-   Paginering  
  
-   Wijzigingen opslaan van een sessie naar een andere voor groeperen, sorteren, filteren en pagineren, en kolommen verplaatsen en het formaat ervan wijzigen  
  
-   Opzoekconfiguratie  
  
-   Berekende velden en samengetelde velden  
  
-   Bedrijfsregels (Foutbericht weergeven, Veldwaarde instellen, Instellen bedrijf vereist, Standaardwaarde instellen, Veld vergrendelen of ontgrendelen)  
  
-   JavaScript-gebeurtenissen  
  
-   Cellen in- of uitschakelen op basis van de beveiligingsrol  
  
-   Gebruikers kunnen zoeken en grafieken blijven gebruiken, en hebben toegang tot de actiebalk zoals met alleen-lezen rasters  
  
## <a name="make-main-grids-editable"></a>Belangrijkste rasters bewerkbaar maken  
  
1.  Open [Solution Explorer](advanced-navigation.md#solution-explorer).  
  
2.  Open in de lijst **Entiteiten** de gewenste entiteit, selecteer het tabblad **Besturingselementen** en selecteer vervolgens **Besturingselement toevoegen**.  
  
     ![Aangepast besturingselement voor bewerkbare rasters toevoegen](media/add-editable-grids-custom-control.png "Aangepast besturingselement voor bewerkbare rasters toevoegen")  
  
3.  Selecteer in het dialoogvenster**Besturingselement toevoegen** de optie **Bewerkbaar raster** en selecteer vervolgens **Toevoegen**.  
  
4.  Selecteer in de rij **Bewerkbaar raster** die is toegevoegd, de vormfactor(en) die u op het raster wilt toepassen. Hierdoor wordt het besturingselement voor het bewerkbare raster het standaardbesturingselement voor de geselecteerde vormfactor(en).  
  
     ![Rij Bewerkbaar raster met vormfactorselectie](media/editable-grid-row-wit-factor-selection.png "Rij Bewerkbaar raster met vormfactorselectie")    

   > [!NOTE]
   >  Tijdens runtime kunnen gebruikers schakelen tussen bewerkbare rasters en alleen-lezen rasters.  
      
5.  Als u een opzoekopdracht wilt toevoegen, selecteert u in de optiegroep **Bewerkbaar raster** de optie **Opzoeken toevoegen** en in het dialoogvenster **Eigenschap 'Opzoeken toevoegen' configureren** doet u vervolgens het volgende:  
  
    1.  In de lijst **Beschikbare weergaven** selecteert u de weergave waaraan u de opzoekopdracht wilt toevoegen (selecteer bijvoorbeeld **Mijn actieve accounts**).  
  
    2.  Selecteer in de lijst **Beschikbare kolommen** de opzoekkolom die u wilt toevoegen (selecteer bijvoorbeeld **Primaire contactpersoon**).  
  
    3.  Selecteer in de lijst **Standaardweergave** de gegevensbron voor het opzoekveld.  
  
    4.  Als u de weergegeven records wilt beperken, schakelt u het selectievakje **Alleen records weergeven waarin** in en selecteert u vervolgens uw criteria in de lijst. Klik daarna op **OK**.  
  
         ![Opzoeken toevoegen in een besturingselement voor bewerkbaar raster](media/add-lookup-in-editable-grid-control.png "Opzoeken toevoegen in een besturingselement voor bewerkbaar raster")  
     
6.  Als u een genest raster hebt, selecteert u het potloodpictogram voor **Geneste rasterweergave** en selecteert u vervolgens de entiteit en de weergave voor het geneste raster. Voor **Bovenliggende id van genest raster** selecteert u de relatie voor de entiteiten. Het veld ParentAccountID verbindt bijvoorbeeld de entiteiten **Account** en **Contactpersoon**.  
  
    > [!NOTE]
    >  Geneste rasters zijn alleen beschikbaar voor telefoons en tablets, niet voor het web.  
  
7.  Als u niet wilt dat de gebruiker gegevens groepeert op een kolom in de weergave (bijvoorbeeld om ruimte te besparen), selecteert u in de rij **Groeperen op kolom** het potloodpictogram en in het dialoogvenster **Eigenschap 'Groeperen op kolom' configureren** selecteert u **Uitgeschakeld** en vervolgens **OK**.  
  
    > [!TIP]
    >  Dit is vooral handig voor subrasters in formulieren.  
  
8.  Als u JavaScript-gebeurtenissen wilt toevoegen, selecteert u het tabblad **Gebeurtenissen** en selecteert u vervolgens de juiste entiteiten, velden en gebeurtenissen. Meer informatie: [Documentatie voor ontwikkelaars: bewerkbare rasters gebruiken](/dynamics365/customer-engagement/developer/customize-dev/use-editable-grids-dynamics-365.md)  
  
     ![Gebeurtenissen toevoegen in een besturingselement voor bewerkbaar raster](media/add-events-in-editable-grid-control.png "Gebeurtenissen toevoegen in een besturingselement voor bewerkbaar raster")  
  
9. Als u uw werk wilt opslaan, selecteert u **Opslaan** in de actiebalk.  
  
10. Wanneer u er klaar voor bent om de wijzigingen voor uw team beschikbaar te stellen, selecteert u **Publiceren** in de actiebalk.  
  
11. Als u uw wijzigingen wilt testen, gaat u naar de weergave die u in stap 5 hebt opgegeven en brengt u enkele inline bewerkwijzigingen aan.  
  
## <a name="make-a-sub-grid-on-a-form-editable"></a>Een subraster op een formulier bewerkbaar maken

> [!NOTE] 
> - Als u een wijziging in een bewerkbaar raster binnen een subraster wilt opslaan, moet de gebruiker expliciet opslaan voordat hij het formulier verlaat.
> - Als u verouderde formulieren gebruikt (versies voorafgaand aan Dynamics CRM 2016) en een bewerkbaar raster in een subraster inschakelt, wordt het bewerkbare subraster niet weergegeven. Systeembeheerders kunnen, indien nodig, verouderde formulieren uitschakelen in systeeminstellingen.
  
1.  Open [Solution Explorer](advanced-navigation.md#solution-explorer).  
  
2.  Open het formulier dat het subraster bevat.  
  
3.  Selecteer het betreffende besturingselement en selecteer vervolgens **Eigenschappen wijzigen** op het lint.  
  
4.  Selecteer in het dialoogvenster **Eigenschappen instellen** de optie **Besturingselementen**, selecteer **Besturingselement toevoegen** en volg dezelfde stappen die hierboven ook worden vermeld.  
  
## <a name="supported-standard-entities"></a>Ondersteunde standaardentiteiten  
  
||||  
|-|-|-|  
|**Web/tablet/telefoon**|**Alleen tablet/telefoon**|**Alleen web**|  
|Account<br /><br /> Afspraak<br /><br /> Boekbare resource<br /><br /> Boekbare resourcereservering<br /><br /> Header boekbare resourcereservering<br /><br /> Categorie boekbare resource<br /><br /> Toegewezen categorie boekbare resource<br /><br /> Kenmerk boekbare resource<br /><br /> Boekbare resourcegroep<br /><br /> Boekingsstatus<br /><br /> Case<br /><br /> Categorie<br /><br /> Kenmerk<br /><br /> Concurrent<br /><br /> Contact<br /><br /> E-mail<br /><br /> Recht<br /><br /> Feedback<br /><br /> Factuur<br /><br /> Kennisartikel<br /><br /> Weergaven kennisartikel<br /><br /> Knowledge Base-record<br /><br /> Lead<br /><br /> Verkoopkans<br /><br /> Bestelling<br /><br /> Telefoongesprek<br /><br /> Prijslijst<br /><br /> Product<br /><br /> Wachtrij<br /><br /> Offerte<br /><br /> Beoordelingsmodel<br /><br /> Beoordelingswaarde<br /><br /> SLA KPI-exemplaar<br /><br /> Sociale activiteit<br /><br /> Sociaal profiel<br /><br /> Synchronisatiefout<br /><br /> Taak<br /><br /> Team<br /><br /> User|Activiteit<br /><br /> Bijlage<br /><br /> Item profielregel kanaaltoegang<br /><br /> Adres van de concurrent<br /><br /> Verbinding<br /><br /> Verbindingsrol<br /><br /> E-mailhandtekening<br /><br /> E-mailsjabloon<br /><br /> Verlopen proces<br /><br /> Factuurproduct<br /><br /> Kennisartikelincident<br /><br /> Lead naar verkoopkans<br /><br /> Proces<br /><br /> Postvak<br /><br /> Nieuw proces<br /><br /> Opmerking<br /><br /> Product verkoopkans<br /><br /> Proces verkoopkans<br /><br /> Productbestelling<br /><br /> Organisatie<br /><br /> Telefoon-naar-case-proces<br /><br /> Item van prijslijst<br /><br /> Wachtrij-item<br /><br /> Productofferte<br /><br /> SharePoint-document<br /><br /> Vertaalproces|Campagne<br /><br /> Campagneactiviteit<br /><br /> Reactie op campagne<br /><br /> Profiel kanaaltoegang<br /><br /> Profielregel kanaaltoegang<br /><br /> Contract<br /><br /> Rechtensjabloon<br /><br /> Externe partij<br /><br /> Fax<br /><br /> Letter<br /><br /> Marketinglijst<br /><br /> Positie<br /><br /> Snelle campagne<br /><br /> Terugkerende afspraak<br /><br /> Documentatie over verkoop<br /><br /> SLA|  
 
##  <a name="data-types-that-arent-editable-in-an-editable-grid"></a>Gegevenstypen die niet bewerkbaar zijn in een bewerkbaar raster
De volgende gegevenstypen zijn niet bewerkbaar in bewerkbare rasters: opzoekvelden Klant en Partylist; samengestelde (adres-) velden; velden Status/Toestand; entiteit-gerelateerde opzoekvelden (de accountentiteit bevat bijvoorbeeld een opzoekcontactpersoon, waarbij het veld Contactpersoon kan worden bewerkt, maar het veld EmailAdress(Contact) niet bewerkbaar is).  
 
## <a name="next-steps"></a>Volgende stappen  
 [Sneltoetsen gebruiken in bewerkbare rasters](https://docs.microsoft.com/dynamics365/customer-engagement/basics/keyboard-shortcuts#editable-grids-views)

