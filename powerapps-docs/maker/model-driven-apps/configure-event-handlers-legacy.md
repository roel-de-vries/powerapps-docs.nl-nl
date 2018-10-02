---
title: Gebeurtenishandlers voor hoofdformulieren voor modelgestuurde apps configureren in PowerApps | MicrosoftDocs
description: Informatie over het configureren van gebeurtenishandlers in Dynamics 365 for Customer Engagement
Keywords: Main form; Configure event handlers; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.assetid: dc0ebb3f-0c00-413a-968f-9cfd107055c0
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-model-driven-app-form-event-handlers"></a>Gebeurtenishandlers voor hoofdformulieren voor modelgestuurde apps configureren

 Gebeurtenishandlers voor PowerApps-formulieren kunnen voor de volgende gebieden in een formulier worden geconfigureerd:  
  
|Element|Gebeurtenis|Beschrijving|  
|-------------|-----------|-----------------|  
|formulier|`OnLoad`|Treedt op wanneer het formulier wordt geladen.|  
||`OnSave`|Treedt op wanneer gegevens worden opgeslagen.|  
|Tabblad|`TabStateChange`|Treedt op wanneer het tabblad wordt uitgevouwen of samengevouwen.|  
|Veld|`OnChange`|Treedt op wanneer gegevens in het veld worden gewijzigd en het besturingselement de focus kwijtraakt.|  
|IFRAME|`OnReadyStateComplete`|Treedt op wanneer de inhoud van een IFrame wordt geladen.|  
  
 Een gebeurtenishandler bestaat uit een verwijzing naar een JavaScript-webresource en een functie die binnen deze webresource is gedefinieerd en wordt uitgevoerd wanneer de gebeurtenis optreedt. Elk element mag maximaal 50 afzonderlijke geconfigureerde gebeurtenis-handlers hebben.  
  
> [!IMPORTANT]
>  Het onjuist configureren van een gebeurtenis-handler kan resulteren in scriptfouten waardoor het formulier niet kan worden geladen of niet goed functioneert. Als u niet de ontwikkelaar van het script bent, zorg er dan voor dat u precies begrijpt welke configuratieopties het script vereist.  
>   
>  Configureer een scriptgebeurtenis-handler niet met een bibliotheek die niet afkomstig is uit een bron die u vertrouwt. Scripts kunnen worden gebruikt om een actie uit te voeren die een gebruiker kan uitvoeren en een slecht geschreven script kan de prestaties van een formulier ernstig beschadigen.  
>   
>  Nadat u een gebeurtenis-handler hebt geconfigureerd, test dan altijd of deze correct werkt.  
  
### <a name="to-configure-an-event-handler"></a>Een gebeurtenis-handler configureren 
  
1.  Selecteer in de formuliereneditor het element met de gebeurtenis waarvoor u een handler wilt configureren.  
  
2.  Selecteer op het [tabblad Start](form-editor-user-interface-legacy.md#home-tab) in de groep **Bewerken** de optie **Eigenschappen wijzigen** of dubbelklik op het element.  
  
3.  Selecteer in het dialoogvenster van elementeneigenschappen het tabblad **Gebeurtenissen**.  
  
4.  Vouw het gebied **Formulierbibliotheken** uit. Als de bibliotheek met de functie die u wilt instellen als gebeurtenis-handler nog niet is vermeld, voegt u de bibliotheek toe.  
  
5.  Een formulierbibliotheek aan een gebeurtenis-handler toevoegen:  
    1.  Selecteer in de sectie **Formulierbibliotheken** van **Gebeurtenissenlijst** de optie **Toevoegen**.  
  
    2.  Zoek de JavaScript-webresource in de lijst met beschikbare webresources. Selecteer deze en selecteer **Toevoegen**.  
  
         Als de JavaScript-webresource die u zoekt niet bestaat, selecteert u **Nieuw** om een nieuw webresourceformulier te openen en een webresource te maken.  
  
    3.  Een JavaScript-webresource maken:  
        1.  Stel de volgende eigenschappen in het webresourceformulier in:  
  
            |Eigenschap|Waarde|  
            |--------------|-----------|  
            |Naam|**Vereist**. Typ de naam van de webresource.|  
            |weergavenaam|**Vereist**. Typ de naam die in de lijst met webresources moet worden weergegeven.|  
            |Beschrijving|Optioneel. Typ een beschrijving van de webresource.|  
            |Type|**Vereist**. Selecteer **Script (JScript)**.|  
            |Taal|Optioneel. Kies een van de talen die beschikbaar zijn voor uw organisatie.|  
  
        2.  Als u een script hebt gekregen, wordt het ten zeerst aanbevolen dat u de knop **Bladeren** gebruikt om het bestand te zoeken en te uploaden.  
  
             U kunt ook de knop **Teksteditor** kiezen en de inhoud van het script in het dialoogvenster **Inhoud bewerken** plakken of typen.  
  
            > [!NOTE]
            >  Omdat deze eenvoudige teksteditor geen functies biedt om de juistheid van het script te controleren, moet u altijd een afzonderlijke toepassing, zoals Visual Studio, proberen te gebruiken om scripts te bewerken en vervolgens te uploaden.  
  
        3.  Kies **Opslaan** en sluit het webresourcedialoogvenster.  
  
        4.  De webresource dat u hebt gemaakt is nu geselecteerd in het dialoogvenster **Record opzoeken**. Kies **Toevoegen** om het dialoogvenster te sluiten.  
6.  Selecteer in de sectie **Gebeurtenis-handlers** de gebeurtenis waarvoor u een gebeurtenis-handler wilt instellen.  
  
7.  Kies **Toevoegen** om het dialoogvenster **Handlereigenschappen** te openen.  
  
8. Kies op het tabblad **Details** de voorkeursbibliotheek en typ de naam van de functie die moet worden uitgevoerd voor de gebeurtenis.  
  
9. De gebeurtenis-handler is standaard ingeschakeld. Schakel het selectievakje **Ingeschakeld** uit als u deze gebeurtenis niet wilt inschakelen.  
  
     Voor bepaalde functies is een uitvoeringscontext vereist om door te geven aan de functie. Selecteer **Uitvoeringscontext doorgeven als eerste parameter** als dit vereist is.  
  
     Sommige functies kunnen een reeks parameters accepteren om het gedrag van een functie te beheren. Als deze vereist zijn, geeft u ze op in de **Door komma's gescheiden lijst met parameters die worden doorgegeven aan de functie**.  
  
10. Voeg op het tabblad **Afhankelijkheden** alle velden toe waarvan het script afhankelijk is in het gebied **Afhankelijke velden**.  
  
11. Selecteer **OK** om het dialoogvenster **Handlereigenschappen** te sluiten.  
  
12. Als de gebeurtenis-handler is ingevoerd, kunt u de volgorde aanpassen waarin de functie met betrekking tot de andere onderdelen wordt uitgevoerd door de groene pijlen te gebruiken om het omhoog of omlaag te verplaatsen.  
  
13. Selecteer **OK** om het dialoogvenster met elementeigenschappen te sluiten.  
  
14. Selecteer **Opslaan** om uw wijzigingen op te slaan. Selecteer **Publiceren** om het formulier te publiceren.  
  
> [!NOTE]
>  Hoewel de gebruikersinterface (UI) u de mogelijkheid biedt de volgorde aan te passen waarin scripts worden geladen met de groene pijlen voor omhoog en omlaag, worden de script niet sequentieel geladen.   

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
