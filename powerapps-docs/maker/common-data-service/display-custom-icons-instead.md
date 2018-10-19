---
title: Aangepaste pictogrammen in plaats van waarden weergeven in lijstweergaven met PowerApps | MicrosoftDocs
description: Leer hoe u aangepaste pictogramafbeeldingen kunt afbeelden in een weergave
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="display-custom-icons-instead-of-values-in-list-views"></a>Aangepaste pictogrammen weergeven in plaats van waarden in lijstweergaven

<a name="GridIcons"></a>   

 Beheerders en aanpassers van PowerApps-omgevingen kunnen afbeeldingen toevoegen aan een weergave en de logica vaststellen die wordt gebruikt voor het selecteren van de afbeelding op basis van kolomwaarden met behulp van JavaScript. De mogelijkheid om lijstweergaven te tonen waarin pictogrammen worden weergegeven in plaats van tekst of numerieke waarden werd in Relatie-inzichten geïntroduceerd. 
  
> [!NOTE]
>  Rasterpictogrammen worden alleen weergegeven in de webinterface. Deze worden niet weergegeven in [!INCLUDE[pn_Outlook_short](../../includes/pn-outlook-short.md)] of de mobiele toepassing.  
  
### <a name="add-custom-graphics-and-javascript-as-web-resources"></a>Aangepaste afbeeldingen en JavaScript toevoegen als webresources  
  
1.  Maak de nieuwe grafische bestanden die nodig zijn voor het aanpassen. We raden een pictogramgrootte van 16x16 pixels aan (grotere afbeeldingen worden verkleind).  
  
2.  Schrijf een of meer JavaScript-functies die bepalen welke pictogrammen worden gebruikt voor het weergeven van welke waarden (normaal gesproken voegt u één functie toe voor elke kolom die u wilt aanpassen). Elke functie moet een object met rijgegevens en een taalcode (LCID) als invoer accepteren en een matrix met een afbeeldingsnaam en knopinfo retourneren. Een voorbeeldweergave vindt u in [Voorbeeld van JavaScript-functie](#SampleJavascript) verderop in dit onderwerp.  
  
3.  Meld u aan bij uw omgeving als beheerder en open de [oplossingenverkenner](../model-driven-apps/advanced-navigation.md#solution-explorer).  
  
4.  Het pop-upvenster **Standaardoplossing** wordt geopend. Navigeer hier naar **Onderdelen** > **Webresources**.  
  
5.  Nu kunt u aangepaste afbeeldingen één voor één uploaden als webresources. Selecteer de knop **Nieuw** op de werkbalk als u een nieuwe webresource wilt maken. Er wordt een pop-upvenster geopend om u te helpen bij het maken van de resource. Ga hiervoor als volgt te werk:  
  
    1.  Geef de nieuwe resource een betekenisvolle **Naam**. Dit is de naam die u gebruikt voor het verwijzen naar elke afbeelding vanuit uw JavaScript-code.  
  
    2.  Stel **Type** in op de grafische indeling die u hebt gebruikt om uw grafische bestand (PNG, JPEG of GIF) op te slaan.  
  
    3.  Selecteer **Bestand kiezen** om een bestandsbrowservenster te openen. Hierin kunt u uw grafische bestand zoeken en selecteren.  
  
    4.  Voeg desgewenst een **Weergavenaam** en/of een **Beschrijving** toe.  
  
    5.  Selecteer **Opslaan** en sluit het venster **Webresource**.  
  
6.  Herhaal de voorgaande stap voor elk grafisch bestand.  
  
7.  Nu voegt u JavaScript toe als de laatste webresource. Selecteer **Nieuw** op de werkbalk als u een nieuwe webresource wilt maken. Er wordt een pop-upvenster geopend om u te helpen bij het maken van de resource. Ga hiervoor als volgt te werk:  
  
    1.  Geef de nieuwe resource een betekenisvolle **Naam**.  
  
    2.  Stel het **Type** in op **Script (JScript)**.  
  
    3.  Selecteer **Teksteditor** (naast de instelling **Type**) om een teksteditorvenster te openen. Plak hier uw JavaScript-code en selecteer **OK** om deze op te slaan.  
  
    4.  Voeg desgewenst een **Weergavenaam** en/of een **Beschrijving** toe.  
  
    5.  Selecteer **Opslaan** en sluit het venster **Webresource**.  
  
8.  Met het pop-upvenster **Standaardoplossing** geopend, vouwt u de structuur **Onderdelen** > **Entiteiten** uit en gaat u naar de entiteit die u wilt aanpassen.  
  
9. Vouw de entiteit uit en selecteer het pictogram **Weergaven**.  
  
10. U ziet nu een lijst met weergaven voor de geselecteerde entiteit. Selecteer een weergave in de lijst. Open vervolgens de vervolgkeuzelijst **Meer acties** op de werkbalk en selecteer **Bewerken**.  
  
11. Er wordt een pop-upvenster geopend met besturingselementen voor het bewerken van de geselecteerde weergave. Elke kolom die deel uitmaakt van de weergave, wordt getoond. Selecteer de doelkolom en selecteer vervolgens op de optie **Eigenschappen wijzigen** in het vak **Algemene taken**. Het dialoogvenster **Kolomeigenschappen wijzigen** wordt geopend. Kies hier de volgende instellingen:  
  
    - **Webresource**: geef de naam op van de webresource die u hebt gemaakt voor uw Javascript-functies (selecteer **Bladeren** om uit een lijst te kiezen).  
  
    - **Functienaam**: typ de naam van de functies die u hebt ingevoerd om de geselecteerde kolom en de weergave aan te passen.  
  
12. Selecteer **OK** om het dialoogvenster **Kolomeigenschappen wijzigen** te sluiten.  
  
13. Selecteer **Opslaan en sluiten** om de weergave op te slaan.  
  
14. Herhaal deze stappen naar wens voor elke entiteit, weergave en kolom.  
  
15. Als u gereed bent, selecteert u **Alle aanpassingen publiceren** om uw wijzigingen te publiceren. Vervolgens sluit u het pop-upvenster **Standaardoplossing**.  
  
<a name="SampleJavascript"></a>   

### <a name="sample-javascript-function"></a>Voorbeeld van JavaScript-functie  
 De JavaScript-functie voor het weergeven van aangepaste pictogrammen en knopinfo verwacht de volgende twee argumenten: het volledige rijobject, opgegeven in layoutxml, en de landinstelling-id van de aanroepende gebruiker (LCID). Met de LCID-parameter kunt u de knopinfotekst in meerdere talen opgeven. Voor meer informatie over de talen die door de omgeving worden ondersteund, raadpleegt u [Talen inschakelen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) en [Taalpakketten installeren of bijwerken voor Dynamics 365](https://technet.microsoft.com/library/hh699674.aspx). Een lijst van LCID-waarden die u in uw code kunt gebruiken, vindt u in [Id's voor landinstellingen die door Microsoft worden toegewezen](https://go.microsoft.com/fwlink/?linkid=829588).

  
 Aannemende dat u waarschijnlijk aangepaste pictogrammen toevoegt voor een kenmerk van het type optieset, dat een beperkte set voorgedefinieerde opties heeft, moet u erop letten dat u de integerwaarde van de opties gebruikt in plaats van het label om lokalisatieproblemen te voorkomen.  
  
 De volgende voorbeeldcode geeft pictogrammen en knopinfo weer op basis van een van de volgende drie waarden (1: Heet, 2: Warm, 3: Koud) in het kenmerk opportunityratingcode (Kwalificatie). De voorbeeldcode geeft ook aan hoe u gelokaliseerde knopinfotekst kunt weergeven. Om dit voorbeeld te laten functioneren, moet u drie afbeeldingswebresources met 16 x 16 afbeeldingen maken met de volgende namen: new_Hot, new_Warm en new_Cold.  
  
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
  
 Dit resulteert in de weergave van knopinfo in de kolom **Kwalificatie** die afhangt van de waarde in elke rij. Het resultaat kan er als volgt uitzien:  
  
 ![Voorbeeld van aangepaste kolomafbeeldingen](media/custom-column-graphics-example.png "Voorbeeld van aangepaste kolomafbeeldingen")  
 
 ### <a name="see-also"></a>Zie ook
 [Weergaven maken of bewerken](../model-driven-apps/create-edit-views.md)
