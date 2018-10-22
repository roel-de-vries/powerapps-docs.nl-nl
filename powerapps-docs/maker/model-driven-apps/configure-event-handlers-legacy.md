---
title: Gebeurtenis-handlers voor hoofdformulieren van apps die zijn gebaseerd op een model configureren in PowerApps | MicrosoftDocs
description: Gebeurtenis-handlers configureren in Dynamics 365 voor Customer Engagement
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
ms.openlocfilehash: e05e9d840a2b3ad7d8d5c74e8e3b670504f739b0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39678647"
---
# <a name="configure-model-driven-app-form-event-handlers"></a>Gebeurtenis-handlers voor formulieren van apps die zijn gebaseerd op een model configureren

 Formuliergebeurtenis-handlers voor PowerApps-formulieren kunnen voor de volgende onderdelen van een formulier worden geconfigureerd:  
  
|Element|Gebeurtenis|Beschrijving|  
|-------------|-----------|-----------------|  
|Formulier|`OnLoad`|Vindt plaats wanneer het formulier wordt geladen.|  
||`OnSave`|Vindt plaats wanneer gegevens worden opgeslagen.|  
|Tabblad|`TabStateChange`|Vindt plaats wanneer het tabblad wordt uitgevouwen of samengevouwen.|  
|Veld|`OnChange`|Vindt plaats wanneer gegevens in het veld worden gewijzigd en het besturingselement niet meer de focus heeft.|  
|IFRAME|`OnReadyStateComplete`|Vindt plaats wanneer de inhoud van een IFRAME wordt geladen.|  
  
 Een gebeurtenis-handler bestaat uit een verwijzing naar een JavaScript-webresource en een functie die is gedefinieerd binnen die webresource die wordt uitgevoerd wanneer de gebeurtenis plaatsvindt. Voor elk element kunnen maximaal 50 afzonderlijke gebeurtenis-handlers worden geconfigureerd.  
  
> [!IMPORTANT]
>  Als u een gebeurtenis-handler onjuist configureert, kan dit leiden tot scriptfouten waardoor het formulier mogelijk niet wordt geladen of onjuist functioneert. Als u niet de ontwikkelaar van het script bent, moet u precies weten welke configuratieopties door het script worden vereist.  
>   
>  Configureer geen gebeurtenis-handler voor een script met behulp van een bibliotheek die niet afkomstig is uit een vertrouwde bron. Met scripts kunnen acties worden uitgevoerd die een gebruiker zou kunnen uitvoeren. Door een slecht opgesteld script kunnen de prestaties van een formulier aanzienlijk worden verslechterd.  
>   
>  Na het configureren van een gebeurtenis-handler moet u de handler altijd testen om te controleren of deze correct werkt.  
  
### <a name="to-configure-an-event-handler"></a>Een gebeurtenis-handler configureren 
  
1.  Selecteer in de formuliereditor het element met de gebeurtenis waarvoor u een handler wilt configureren.  
  
2.  Selecteer op het [tabblad Start](form-editor-user-interface-legacy.md#home-tab), in de groep **Bewerken**, de optie **Eigenschappen wijzigen** of dubbelklik gewoon op het element.  
  
3.  Selecteer in het dialoogvenster met de elementeigenschappen het tabblad **Gebeurtenissen**.  
  
4.  Vouw het gedeelte **Formulierbibliotheken** uit. Als de bibliotheek met de functie die u wilt instellen als de gebeurtenis-handler niet wordt vermeld, moet u de bibliotheek toevoegen.  
  
5.  U voegt als volgt een formulierbibliotheek toe aan een gebeurtenis-handler:  
    1.  Selecteer in het gedeelte **Formulierbibliotheken** van de **lijst met gebeurtenissen** de optie **Toevoegen**.  
  
    2.  Zoek de JavaScript-webresource op in de lijst met beschikbare webresources. Selecteer deze en selecteer vervolgens **Toevoegen**.  
  
         Als de JavaScript-webresource die u nodig hebt niet voorkomt, selecteert u **Nieuw** om een nieuw webresourceformulier te openen en een webresource te maken.  
  
    3.  U maakt als volgt een JavaScript-webresource:  
        1.  Stel in het webresourceformulier de volgende eigenschappen in:  
  
            |Eigenschap|Waarde|  
            |--------------|-----------|  
            |Naam|**Vereist**. Voer de naam van de webresource in.|  
            |Weergavenaam|**Vereist**. Voer de naam in die moet worden weergegeven in de lijst met webresources.|  
            |Beschrijving|Optioneel. Voer een beschrijving van de webresource in.|  
            |Type|**Vereist**. Selecteer **Script (JScript)**.|  
            |Taal|Optioneel. Kies een van de talen die beschikbaar zijn voor uw organisatie.|  
  
        2.  Als u al over een script beschikt, kunt u het bestand het beste zoeken met de knop **Bladeren** en dit uploaden.  
  
             U kunt ook de knop **Teksteditor** selecteren en de inhoud van het script in het dialoogvenster **Inhoud bewerken** plakken of hierin invoeren.  
  
            > [!NOTE]
            >  Omdat deze eenvoudige teksteditor niet over de functies beschikt om te controleren of het script correct is, wordt doorgaans aanbevolen een afzonderlijke toepassing (zoals Visual Studio) te gebruiken om scripts te bewerken en deze vervolgens te uploaden.  
  
        3.  Selecteer **Opslaan** en sluit het dialoogvenster met webresources.  
  
        4.  De webresource die u hebt gemaakt, is nu geselecteerd in het dialoogvenster **Record opzoeken**. Selecteer **Toevoegen** om het dialoogvenster te sluiten.  
6.  Selecteer in het gedeelte **Gebeurtenis-handlers** de gebeurtenis waarvoor u een gebeurtenis-handler wilt instellen.  
  
7.  Selecteer **Toevoegen** om het dialoogvenster **Handlereigenschappen** te openen.  
  
8. Kies op het tabblad **Details** de betreffende bibliotheek en voer de naam in van de functie die voor de gebeurtenis moet worden uitgevoerd.  
  
9. De gebeurtenis-handler is standaard ingeschakeld. Schakel het selectievakje **Ingeschakeld** uit als u deze gebeurtenis niet wilt inschakelen.  
  
     Voor sommige functies moet een uitvoeringscontext worden doorgegeven aan de functie. Selecteer **Uitvoeringscontext doorgeven als de eerste parameter** als dat nodig is.  
  
     Sommige functies kunnen een aantal parameters accepteren voor het beheren van het gedrag van een functie. Als deze vereist zijn, voert u deze in de **door komma's gescheiden lijst met parameters die worden doorgegeven aan de functie** in.  
  
10. Voeg op het tabblad **Afhankelijkheden** velden waarvan het script afhankelijk is toe aan het gedeelte **Afhankelijke velden**.  
  
11. Selecteer **OK** om het dialoogvenster **Handlereigenschappen** te sluiten.  
  
12. Wanneer de gebeurtenis-handler is ingevoerd, kunt u de volgorde waarin de functie wordt uitgevoerd ten opzichte van andere functies aanpassen door de functie met behulp van de groene pijlen omhoog of omlaag te verplaatsen.  
  
13. Selecteer **OK** om het dialoogvenster met handlereigenschappen te sluiten.  
  
14. Selecteer **Opslaan** om uw wijzigingen op te slaan. Selecteer **Publiceren** om het formulier te publiceren.  
  
> [!NOTE]
>  Hoewel u in de gebruikersinterface de volgorde waarin de scripts worden geladen met de groene pijlen voor omhoog en omlaag kunt aanpassen, worden de scripts niet opeenvolgend geladen.   

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de bijbehorende onderdelen gebruiken](use-main-form-and-components.md)
