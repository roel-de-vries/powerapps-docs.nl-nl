---
title: Overzicht van gebruikersinterface van de editor voor modelgestuurde-appformulieren voor PowerApps | MicrosoftDocs
description: De gebruikersinterface van de formuliereneditor leren kennen om formulieren te bewerken in PowerApps
keywords: Formulieren; hoofdformulier; geïntegreerde interface-apps; Dynamics 365 voor Customer Engagement
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.assetid: 146f8035-4fcd-4572-8e71-4270cd150495
ms.openlocfilehash: a44987e7b8809dea46f164224974a21a2d9a5010
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680460"
---
# <a name="overview-of-the-model-driven-app-form-editor-user-interface"></a>Overzicht van gebruikersinterface van de editor voor modelgestuurde-appformulieren

De formuliereneditor toont opdrachten op drie tabbladen: **Bestand**, **Home** en **Invoegen**.  

- [Tabblad Bestand](#file-tab)
- [Tabblad Start](#home-tab)
- [Tabblad Invoegen](#insert-tab)
  
De formuliereneditor is onderverdeeld in drie gebieden: **Navigatie**, **Hoofdtekst** en **Explorer**.  

![Gebruikersinterface van formuliereneditor](media/form-user-interface.png)
  
**Navigatie**  
Gebruik het navigatiegebied aan de linkerkant om te regelen wie toegang heeft tot gerelateerde entiteiten of om koppelingen naar URL's toe te voegen die moeten worden weergegeven in het hoofdvenster van het formulier. Als u navigatie wilt bewerken, moet u eerst de opdracht **Navigatie** selecteren in de groep **Selecteren** van het tabblad **Home**.

Hoofdformulieren bieden navigatieopties via de navigatiebalk, maar gebruiken dezelfde gegevens in het navigatiegebied om te regelen welke navigatieopties beschikbaar zijn. Meer informatie: [Navigatie bewerken](use-the-form-editor-legacy.md)  


**Hoofdtekst** <br>
Gebruik het hoofdgebied in het midden om de opmaak van het formulier te regelen. U kunt formulierelementen selecteren en verslepen naar de gewenste locatie. U kunt de eigenschappen van een element openen door te dubbelklikken op het element. 

Standaard worden voor de hoofdformulieren Casus, Contactpersoon en Account in het eerste gedeelte onder het tabblad **Samenvatting** het account- of visitekaartjeformulier van het type **Snelle weergave** weergegeven. Voor aangepaste entiteiten is dit gedeelte niet standaard beschikbaar. U kunt er een nieuw gedeelte en een formulier voor snelle weergave in invoegen. Op het kaartformulier kunnen maximaal vijf velden worden weergegeven. Er zijn, behalve velden, geen mogelijkheden om andere besturingselementen in de blauwe tegel weer te geven, zelfs als deze wel in het formulier voor snelle weergave staan. 
 
>[!NOTE] 
> Als u de kaartindeling wilt behouden (zoals in de volgende afbeelding wordt weergegeven), wordt aanbevolen het formulier voor snelle weergave niet naar een ander gedeelte van het formulier te verplaatsen.

![Kaartindeling](media/card-format.png)
   
Meer informatie: [Formulieren voor snelle weergave maken en bewerken](create-edit-quick-view-forms.md)  
 
-   Als u een veld wilt toevoegen, selecteert u dit in de **Veldverkenner** en sleept u deze naar een sectie.  
  
    -   Als u een element wilt toevoegen dat geen veld is, selecteert u waar u deze wilt plaatsen en gebruikt u de toepasselijke opdracht van het tabblad **Invoegen** om het toe te voegen.  
  
    -   Als u een element wilt verwijderen, selecteert u dit en gebruikt u de opdracht **Verwijderen** in de groep **Bewerken** van het tabblad **Home**.  
  
    -   Als u de **Koptekst** of **Voettekst** voor het formulier wilt bewerken, moet u eerst de bijbehorende opdracht in de groep **Selecteren** op het tabblad **Home** inschakelen.  
  
**Explorer**  
De inhoud van het verkennersgebied, aan de rechterkant, hangt af van de context.  
  
Wanneer u **Hoofdtekst**, **Koptekst** of **Voettekst** selecteert in de groep **Selecteren** van het tabblad **Home**, ziet u de **Veldverkenner**. Gebruik de **Veldverkenner** om velden die u wilt weergeven naar een gedeelte in het formulier of in de koptekst of voettekst te slepen. U kunt hetzelfde veld meerdere keren in een formulier invoegen. Gebruik de knop **Nieuw veld** als een snelkoppeling om een nieuw veld te maken.  
  
Wanneer u **Navigatie** in de groep **Selecteren** van het tabblad **Home** selecteert, ziet u de **Relatieverkenner**. Versleep een relatie naar een van de groepen in het navigatiegebied. U kunt dezelfde relatie niet twee keer toevoegen. Relaties zijn beschikbaar op basis van de manier waarop ze zijn geconfigureerd. Als u configureert dat een relatie niet wordt weergegeven, wordt deze niet weergegeven in de **Relatieverkenner**. Zie [Item op navigatiedeelvenster voor primaire entiteit](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity) voor informatie over het configureren van standaardweergaveopties voor relaties.
  
U kunt de knoppen **Nieuwe 1:N** en **Nieuwe N:N** gebruiken als snelkoppeling voor het toevoegen van nieuwe entiteitrelaties.  

## <a name="file-tab"></a>Tabblad Bestand

Selecteer het tabblad **Bestand** voor het toevoegen/weergeven van de volgende opties:

- **Nieuwe activiteit** Een nieuwe activiteit toevoegen
- **Nieuwe record** Een nieuwe record toevoegen
- **Extra** Gebruik opties zoals Gegevens importeren, Duplicaatdetectie en Wizard voor bulksgewijs verwijderen
- **Opties** Wijzig de standaard weergave-instellingen om de standaardoplossing te personaliseren en uw e-mailsjablonen te beheren
    - Algemeen
    - Synchronisatie
    - Activiteiten
    - Indelingen
    - E-mailsjablonen
    - E-mailhandtekeningen
    - E-mail
    - Privacy
    - Talen
- Help
- Sluiten


## <a name="home-tab"></a>Tabblad Start  
 Op het tabblad **Home** worden de opdrachten weergegeven die in de volgende tabel staan:

![home-tab](media/home-tab.png)

|Groep|Opdracht|Beschrijving|
|-----------|-------------|-----------------| 
|**Opslaan**|**Opslaan** **(Ctrl+S)**|Sla het formulier op.|
||**Opslaan als**|Maak een kopie van dit formulier met een andere naam.|
||**Opslaan en sluiten**|Sla het formulier op en sluit de formuliereneditor.|
||**Publiceren**|Publiceer het formulier. Meer informatie: Aanpassingen publiceren|
|**Bewerken**|**Eigenschappen wijzigen**|Wijzig de eigenschappen van het geselecteerde item in de hoofdtekst.<br /><br /> Bekijk de volgende secties afhankelijk van het geselecteerde item:<br /><br /> -   [Tabblad Eigenschappen](tab-properties-legacy.md)<br />-   [Eigenschappen van sectie](section-properties-legacy.md)<br />-   [Algemene veldeigenschappen](common-field-properties-legacy.md)<br />-   [Speciale veldeigenschappen](special-field-properties-legacy.md)<br />-  [Eigenschappen onderliggende raster](sub-grid-properties-legacy.md)<br />-   [Eigenschappen van besturingselement voor snelle weergave](quick-view-control-properties-legacy.md)|
||**Verwijderen**|Verwijder het geselecteerde item.|
||**Ongedaan maken** **(Ctrl+Z)**|Maak de vorige actie ongedaan.|
||**Opnieuw** **(Ctrl+Y)**|Voer de vorige actie opnieuw uit.|
|**Selecteren**|**Hoofdtekst**|Bewerk de hoofdtekst van het formulier.|
||**Koptekst**|Bewerk de koptekst van het formulier.|
||**Voettekst**|Bewerk de voettekst van het formulier.|
||**Navigatie**|Bewerk de formuliernavigatie.<br /><br /> Meer informatie: [Navigatie bewerken](use-the-form-editor-legacy.md)
|**Formulier**|**Bedrijfsregels**|Met de Bedrijfsregelverkenner kunt u nieuwe bedrijfsregels weergeven, bewerken of maken. **Opmerking:** voor de interactieve formulieren worden alleen de bereiken 'Entiteit' en 'Alle formulieren' ondersteund.<br /><br /> Meer informatie: [Bedrijfsregels maken en bewerken](create-business-rules-recommendations-apply-logic-form.md)|
||**Formuliereigenschappen**| Meer informatie: [Formuliereigenschappen](form-properties-legacy.md)|  
||**Preview**|Gebruik deze optie om te zien hoe het formulier er na publicatie uitziet. U kunt ook een preview bekijken om scripts te testen die aan gebeurtenissen zijn gekoppeld.|         
||**Beveiligingsrollen inschakelen**|Gebruik deze optie om in te stellen welke beveiligingsrollen toegang hebben tot de formulieren. Meer informatie: [Toegang tot formulieren controleren](control-access-forms.md) **Belangrijk:** als u een nieuw formulier maakt, hebben alleen gebruikers met de beveiligingsrol van systeembeheerder of systeemaanpasser toegang tot het formulier. U moet toegang toewijzen aan andere beveiligingsrollen voordat gebruikers er gebruik van kunnen maken.|  
||**Afhankelijkheden weergeven**|Bekijk welke oplossingsonderdelen afhankelijk zijn van dit formulier en welke oplossingsonderdelen voor dit formulier vereist zijn. Meer informatie: [Afhankelijkheden van de oplossing](../common-data-service/overview.md)|  
||**Beheerde eigenschappen**|De opdracht beheerde eigenschappen heeft twee eigenschappen: **Aanpasbaar** en **Kan worden verwijderd**. Wanneer u deze eigenschappen op Niet waar instelt, kan het formulier niet worden aangepast of verwijderd nadat u dit in een oplossing hebt ingevoegd, die oplossing als beheerde oplossing hebt geëxporteerd en die beheerde oplossing in een andere omgeving hebt geïmporteerd. Meer informatie: [Beheerde eigenschappen](../common-data-service/solutions-overview.md#managed-properties)| 
|**Upgrade uitvoeren**|**Formulieren samenvoegen**|Waar van toepassing kunt u met behulp van deze optie dit formulier samenvoegen met een formulier uit een eerdere versie van een Dynamics 365-formulier|
  

## <a name="insert-tab"></a>Tabblad Invoegen  
![insert-tab](media/insert-tab.png)
 
Op het tabblad Invoegen worden de opdrachten weergegeven die in de volgende tabel staan:

|Groep|Opdracht|Beschrijving|
|-----------|-------------|-----------------| 
||**Sectie**|Voeg een sectie toe aan een geselecteerd tabblad. U kunt een gedeelte met één tot vier kolommen invoegen.<br /><br /> U kunt ook een referentiedeelvenster invoegen in de interactieve formulieren. Ook is het referentiedeelvenster toegevoegd als onderdeel van het formulier Hoofd - Interactieve ervaring. Standaard wordt het gedeelte met het referentiedeelvenster toegevoegd aan casus-, account- of contactpersoonformulieren of formulieren voor aangepaste entiteiten.<br /><br /> Meer informatie: [Sectie-eigenschappen](section-properties-legacy.md)|  
|**Drie tabbladen**|**Drie kolommen**|Voeg een tabblad met drie kolommen van dezelfde breedte in.<br /><br /> Meer informatie: [Tabblad Eigenschappen](tab-properties-legacy.md)|  
||**Drie kolommen**|Voeg een tabblad met drie kolommen in met een bredere kolom in het midden.|  
|**Twee tabbladen**|**Twee kolommen**|Voeg een tabblad met twee kolommen en maak de rechterkolom breder.|  
||**Twee kolommen**|Voeg een tabblad met twee kolommen in en maak de linkerkolom breder.|  
||**Twee kolommen**|Voeg een tabblad met twee kolommen van dezelfde breedte in.|  
|**Eén tabblad**|**Eén kolom**|Voeg een tabblad met één kolom in.|  
|**Besturingselement**|**Onderliggend raster**|Formatteer een onderliggend raster en voeg dit in het formulier in.<br /><br /> Meer informatie: [Eigenschappen van het onderliggende raster](sub-grid-properties-legacy.md)|  
||**Tussenruimte**|Voeg een spatie in.|  
||**Formulier voor snelle weergave**|Voeg een formulier voor snelle weergave in.<br /><br /> Meer informatie: [Snelle weergave besturingselementeigenschappen](quick-view-control-properties-legacy.md)|  
||**Webresource**|Voeg een webresource in om inhoud uit andere locaties in één pagina in te sluiten.<br /><br /> Meer informatie: [Webresource-eigenschappen](web-resource-properties-legacy.md)|  
||**IFRAME**|U kunt een IFRAME toevoegen aan een formulier om inhoud uit een andere website in een formulier te integreren.| 
||**Tijdlijn**|Voeg een tijdlijnbesturingselement in het formulier in. Dit besturingselement toont de tijdlijn van activiteiten met betrekking tot de entiteit op een formulier.|  
||**Navigatiekoppeling**|Met behulp van deze optie kunt u een koppeling in een formuliernavigatie invoegen.|  
||**Timer**|Voeg een getimed besturingselement in een entiteitsformulier toe om de tijd bij te houden aan de hand van een SLA. Meer informatie: [Een getimed besturingselement toevoegen](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-timer-control-case-form-track-time-against-sla)|
||**Zoeken in Knowledge Base**|Voeg een besturingselement voor zoeken in dat gebruikers kunnen gebruiken om te zoeken in kennisartikelen. Meer informatie: [Besturingselement voor zoeken in Knowledge Base](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-knowledge-base-search-control-forms)|  
||**Relatieassistent**|Met behulp van deze optie kunt u een hulpbesturingselement voor relaties in het formulier invoegen.|

>[!Note] 
>De volgende onderdelen worden niet ondersteund in de hoofdformulieren:<br> <ul> <li>Bing Kaarten <br><li>Yammer <br><li>Activiteitsfeeds <br> </li> </ul>


## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de bijbehorende onderdelen gebruiken](use-main-form-and-components.md)  
