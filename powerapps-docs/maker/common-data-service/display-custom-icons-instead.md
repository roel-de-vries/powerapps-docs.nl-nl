---
title: Aangepaste pictogrammen in plaats van waarden weergeven in lijstweergaven met PowerApps | Microsoft Docs
description: Leer hoe u aangepaste pictogramafbeeldingen kunt gebruiken in een weergave
ms.custom: ''
ms.date: 06/21/2018
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
ms.assetid: af866aed-2586-4b6f-bb1c-3519baae3645
caps.latest.revision: 25
ms.author: matp
manager: kvivek
ms.openlocfilehash: 592d2ad73b192d7f03c552563c4f91d52f3d201d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675143"
---
# <a name="display-custom-icons-instead-of-values-in-list-views"></a>Aangepaste pictogrammen in plaats van waarden weergeven in lijstweergaven

<a name="GridIcons"></a>   

 Beheerders en klanten in PowerApps-omgevingen kunnen afbeeldingen toevoegen aan een weergave en de logica te bepalen die wordt gebruikt om de afbeelding te selecteren op basis van kolomwaarden met behulp van JavaScript. De mogelijkheid om lijstweergaven weer te geven met pictogrammen in plaats van tekst of numerieke waarden is geïntroduceerd in Relatie-inzichten. 
  
> [!NOTE]
>  Rasterpictogrammen worden alleen weergegeven in de webinterface. Ze worden niet weergegeven in [!INCLUDE[pn_Outlook_short](../../includes/pn-outlook-short.md)] of de mobiele app.  
  
### <a name="add-custom-graphics-and-javascript-as-web-resources"></a>Aangepaste afbeeldingen en JavaScript toevoegen als webresources  
  
1.  Maak de nieuwe afbeeldingsbestanden die nodig zijn voor de aanpassing. We raden u aan een pictogramgrootte te kiezen van 16x16 pixels (grotere afbeeldingen worden omlaag geschaald).  
  
2.  Schrijf een of meer JavaScript-functies die bepalen welke pictogrammen moeten worden weergegeven voor welke waarden (gewoonlijk hebt u voor elke kolom die u wilt aanpassen, één functie nodig). Elke functie moet een rijgegevensobject en een taalcode (LCID) accepteren als invoer en een matrix retourneren met een afbeeldingsnaam en knopinfotekst. Zie [Voorbeeldfunctie van JavaScript](#SampleJavascript), verderop in dit onderwerp, voor een voorbeeldfunctie.  
  
3.  Meld u als beheerder aan bij uw omgeving en open [Solution Explorer](../model-driven-apps/advanced-navigation.md#solution-explorer).  
  
4.  Het pop-upvenster **Standaardoplossing** wordt geopend. Navigeer hier naar **Onderdelen** > **Webresources**.  
  
5.  Nu gaat u de aangepaste afbeeldingen, één voor één, uploaden als webresources. Selecteer in de werkbalk de knop **Nieuw** om een nieuwe webresource te maken. Er wordt nog een pop-upvenster geopend om u te helpen bij het maken van de resource. Voer de volgende handelingen uit:  
  
    1.  Geef de nieuwe resource een duidelijke **Naam**. Dit is de naam die u gebruikt om vanuit de JavaScript-code naar elke afbeelding te verwijzen.  
  
    2.  Stel het **Type** in op de afbeeldingsindeling die u hebt gebruikt om het afbeeldingsbestand op te slaan (PNG, JPEG of GIF).  
  
    3.  Selecteer **Bestand kiezen** om een browservenster voor bestanden te openen. Gebruik dit venster om het afbeeldingsbestand te zoeken en te selecteren.  
  
    4.  Voeg, als u wilt, een **Weergavenaam** en/of **Beschrijving** toe.  
  
    5.  Selecteer **Opslaan** en sluit vervolgens het venster **Webresource**.  
  
6.  Herhaal de vorige stap voor elk afbeeldingsbestand dat u hebt.  
  
7.  U voegt nu JavaScript toe als de laatste webresource. Selecteer in de werkbalk de optie **Nieuw** om een nieuwe webresource te maken. Er wordt nog een pop-upvenster geopend om u te helpen bij het maken van de resource. Voer de volgende handelingen uit:  
  
    1.  Geef de nieuwe resource een duidelijke **Naam**.  
  
    2.  Stel het **Type** in op **Script (JScript)**.  
  
    3.  Selecteer **Teksteditor** (naast de instelling **Type**) om een venster voor de teksteditor te openen. Plak hier de JavaScript-code en selecteer **OK** om deze op te slaan.  
  
    4.  Voeg, als u wilt, een **Weergavenaam** en/of **Beschrijving** toe.  
  
    5.  Selecteer **Opslaan** en sluit vervolgens het venster **Webresource**.  
  
8.  Laat het pop-upvenster **Standaardoplossing** geopend, vouw de structuur **Onderdelen** > **Entiteiten** uit en zoek de entiteit die u wilt aanpassen.  
  
9. Vouw de entiteit uit en selecteer het bijbehorende pictogram **Weergaven**.  
  
10. U ziet nu een lijst met weergaven voor de geselecteerde entiteit. Selecteer een weergave uit de lijst. Open vervolgens in de werkbalk de vervolgkeuzelijst **Meer acties** en selecteer **Bewerken**.  
  
11. Er wordt een pop-upvenster geopend met besturingselementen om de geselecteerde weergave te bewerken. In het venster wordt elke kolom weergegeven die onderdeel uitmaakt van de weergave. Selecteer de doelkolom en selecteer vervolgens **Eigenschappen wijzigen** in het vak **Algemene taken**. Het dialoogvenster **Kolomeigenschappen wijzigen** wordt geopend. Stel hier de volgende instellingen in:  
  
    - **Webresource**: geef de naam op van de webresource die u hebt gemaakt voor de JavaScript-functies (selecteer **Bladeren** om te kiezen uit de lijst).  
  
    - **Functienaam**: typ de naam van de functie die u hebt geschreven, om de geselecteerde kolom en weergave te wijzigen.  
  
12. Selecteer **OK** om het dialoogvenster **Kolomeigenschappen wijzigen** te sluiten.  
  
13. Selecteer **Opslaan en sluiten** om de weergave op te slaan.  
  
14. Herhaal deze stappen voor elke entiteit, weergave en kolom, indien nodig.  
  
15. Als u klaar bent, selecteert u **Alle aanpassingen publiceren** om de wijzigingen te publiceren. Sluit vervolgens het venster **Standaardoplossing**.  
  
<a name="SampleJavascript"></a>   

### <a name="sample-javascript-function"></a>Voorbeeldfunctie van JavaScript  
 Voor de JavaScript-functie voor het weergeven van aangepaste pictogrammen en knopinfo worden deze twee argumenten verwacht: het hele rijobject in layoutxml en de landinstellingen-id (LCID) van de gebruiker die de aanroep heeft uitgevoerd. Met de LCID-parameter kunt u knopinfotekst weergeven in meerdere talen. Zie [Talen inschakelen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) en [Taalpakketten voor Dynamics 365 installeren of upgraden](https://technet.microsoft.com/library/hh699674.aspx) voor meer informatie over de talen die worden ondersteund in de omgeving. Zie [Landinstellingen-id’s die zijn toegewezen in Microsoft](https://go.microsoft.com/fwlink/?linkid=829588) voor een lijst met landinstellingen-id’s (LCID) die u kunt gebruiken in uw code.

  
 Ervan uitgaande dat u aangepaste pictogrammen gaat toevoegen voor een kenmerk van het type optieset, dat een beperkte set vooraf gedefinieerde opties heeft, moet u ervoor zorgen dat u het geheel getal van de opties gebruikt in plaats van een label. Dit is om lokalisatieproblemen te voorkomen.  
  
 In de volgende voorbeeldcode worden pictogrammen en knopinfo weergegeven op basis van een van drie waarden (1: Heet, 2: Warm, 3: Koud) in het kenmerk opportunityratingcode (classificatie). De voorbeeldcode toont ook hoe gelokaliseerde knopinfotekst moet worden weergegeven. Dit voorbeeld werkt alleen als u drie afbeeldingswebresources maakt met afbeeldingen van 16x16 met de volgende namen: nieuw_Heet, nieuw_Warm en nieuw_Koud.  
  
```  
function displayIconTooltip(rowData, userLCID) {      
    var str = JSON.parse(rowData);  
    var coldata = str.opportunityratingcode_Value;  
    var imgName = "";  
    var tooltip = "";  
    switch (parseInt(coldata,10)) { 
        case 1:  
            imgName = "new_Hot";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Hot";  
                    break;  
                default:  
                    tooltip = "Opportunity is Hot";  
                    break;  
            }  
            break;  
        case 2:  
            imgName = "new_Warm";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Warm";  
                    break;  
                default:  
                    tooltip = "Opportunity is Warm";  
                    break;  
            }  
            break;  
        case 3:  
            imgName = "new_Cold";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Cold";  
                    break;  
                default:  
                    tooltip = "Opportunity is Cold";  
                    break;  
            }  
            break;  
        default:  
            imgName = "";  
            tooltip = "";  
            break;  
    }  
    var resultarray = [imgName, tooltip];  
    return resultarray;  
}  
```  
  
 Dit resulteert in het weergeven van pictogrammen met knopinfo in de kolom **Classificatie** die afhankelijk is van de waarde in elke rij. Het resultaat kan er als volgt uitzien:  
  
 ![Voorbeeld van kolom met aangepaste afbeeldingen](media/custom-column-graphics-example.png "Voorbeeld van kolom met aangepaste afbeeldingen")  
 
 ### <a name="see-also"></a>Zie ook
 [Weergaven maken of bewerken](../model-driven-apps/create-edit-views.md)
