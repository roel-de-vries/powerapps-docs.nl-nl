---
title: Overzicht van de gebruikersinterface van de formuliereneditor voor modelgestuurde apps voor PowerApps | MicrosoftDocs
description: Leer de gebruikersinterface van de formuliereneditor kennen om formulieren te bewerken in PowerApps
keywords: Formulieren; Hoofdformulier; Unified Interface-apps; Dynamics 365 for customer engagement
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.assetid: 146f8035-4fcd-4572-8e71-4270cd150495
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="overview-of-the-model-driven-app-form-editor-user-interface"></a>Overzicht van de gebruikersinterface van de formuliereneditor voor modelgestuurde apps

De formuliereneditor geeft opdrachten weer op drie tabbladen: **Bestand**, **Start** en **Invoegen**.  

- [Tabblad Bestand](#file-tab)
- [Tabblad Start](#home-tab)
- [Tabblad Invoegen](#insert-tab)
  
De formuliereneditor is verdeeld in drie gebieden: **Navigatie**, **Hoofdtekst** en **Verkenner**.  

> [!div class="mx-imgBorder"] 
> ![Gebruikersinterface van de formuliereneditor](media/form-user-interface.png)
  
**Navigatie**  
Gebruik het navigatiegebied, aan de linkerkant, om toegang tot verwante entiteiten te beheren of koppelingen naar URL's toe te voegen die in het hoofdvenster van het formulier moeten worden weergegeven. Om de navigatie te bewerken, moet u eerst de opdracht **Navigatie** selecteren in de groep **Selecteren** van het tabblad **Start**.

Hoofdformulieren bieden navigatieopties via de navigatiebalk, maar gebruiken dezelfde gegevens in het navigatiegebied om te beheren welke navigatieopties beschikbaar zijn. Meer informatie: [Navigatie bewerken](use-the-form-editor-legacy.md)  


**Tekst** <br>
Gebruik het hoofdtekstgebied, in het midden, om de indeling van het formulier te beheren. U kunt formulierelementen selecteren en verslepen om ze te plaatsen. Bij dubbelklikken op een element worden de eigenschappen van het element geopend. 

Standaard bevatten de hoofdformulieren Aanvraag, Contactpersoon en Account in de eerste sectie onder het tabblad **Samenvatting** het account- of visitekaartjeformulier van het type **Snel weergeven**. Voor aangepaste entiteiten is deze sectie niet standaard beschikbaar. U kunt een nieuwe sectie met daarin een snel-weergaveformulier invoegen. In het kaartformulier worden maximaal vijf velden getoond. Behalve velden is het niet mogelijk om andere besturingselementen in de blauwe tegel te tonen, zelfs als het snelle-weergaveformulier deze bevat. 
 
>[!NOTE] 
> Om de kaartindeling (zoals weergegeven in onderstaande afbeelding) te behouden, raden we aan de snelle-weergaveformulier niet naar een andere sectie op het formulier te verplaatsen.

> [!div class="mx-imgBorder"] 
> ![Kaartindeling](media/card-format.png)
   
Meer informatie: [Snelle-weergaveformulieren maken en bewerken](create-edit-quick-view-forms.md)  
 
-   Als u een veld wilt toevoegen, selecteert u het vanuit **Veldverkenner** en sleept het in een sectie.  
  
    -   Om een element toe te voegen dat geen veld is, selecteert u waar u het wilt plaatsen en gebruikt u de juiste opdracht vanuit het tabblad **Invoegen**.  
  
    -   Om een element te verwijderen, selecteert u het en gebruikt u de opdracht **Verwijderen** in de groep **Bewerken** van het tabblad **Start**.  
  
    -   Als u de **Koptekst** of **Voettekst** op het formulier wilt bewerken, moet u eerst de overeenkomstige opdracht in de groep **Selecteren** van het tabblad **Start** selecteren.  
  
**Verkenner**  
De inhoud van het verkennersgebied, aan de rechterkant, hangt af van de context.  
  
Als u **Hoofdtekst**, **Koptekst** of **Voettekst** in de groep **Selecteren** van het tabblad **Start** selecteert, ziet u de **Veldverkenner**. Gebruik de **Veldverkenner** om velden te verslepen die u in een sectie in het formulier of in de kop- of voettekst wilt weergeven. U kunt hetzelfde veld meerdere keren in een formulier opnemen. Gebruik de knop **Nieuw veld** als snelkoppeling om een nieuw veld te maken.  
  
Als u **Navigatie** in de groep **Selecteren** van het tabblad **Start** selecteert, ziet u de **Relatieverkenner**. Sleep de relaties naar een van de groepen in het navigatiegebied. U kunt dezelfde relatie niet twee keer toevoegen. Relaties zijn beschikbaar op basis van de manier waarop ze zijn geconfigureerd. Als u een relatie zo configureert dat deze niet wordt weergegeven, wordt deze niet weergegeven in de **Relatieverkenner**. Voor informatie over hoe u de standaardweergave-opties voor relaties configureert, raadpleegt u [Navigatiedeelvensteritem voor primaire entiteit](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity).
  
U kunt de knoppen **Nieuwe 1:N** en **Nieuwe N:N** gebruiken als snelkoppeling om nieuwe entiteitsrelaties toe te voegen.  

## <a name="file-tab"></a>Tabblad Bestand

Selecteer het tabblad **Bestand** om de volgende opties toe te voegen/weer te geven:

- **Nieuwe activiteit** Een nieuwe activiteit toevoegen
- **Nieuwe record** Een nieuwe record toevoegen
- **Extra** Opties als Gegevens importeren, Duplicatendetectie en Wizard Bulksgewijs verwijderen gebruiken
- **Opties** De standaardweergave-instellingen wijzigen om de standaardoplossing aan uw wensen aan te passen en uw e-mailsjablonen te beheren
    - Algemeen
    - Synchronisatie
    - Activiteiten
    - Notaties
    - E-mailsjablonen
    - E-mailhandtekeningen
    - E-mailadres
    - Privacy
    - Talen
- Help
- Sluiten


## <a name="home-tab"></a>Tabblad Start  
 Het tabblad **Start** bevat de opdrachten in de volgende tabel:

> [!div class="mx-imgBorder"] 
> ![home-tab](media/home-tab.png)

|Groep|Opdracht|Beschrijving|
|-----------|-------------|-----------------| 
|**Opslaan**|**Opslaan** **(Ctrl+S)**|Sla het formulier op.|
||**Opslaan als**|Maak een kopie van dit formulier met een andere naam.|
||**Opslaan en sluiten**|Sla het formulier op en sluit de formuliereneditor.|
||**Publiceren**|Publiceer het formulier. Meer informatie: Aanpassingen publiceren|
|**Bewerken**|**Eigenschappen wijzigen**|Wijzig de eigenschappen van het geselecteerde item in de hoofdtekst.<br /><br /> Raadpleeg de volgende secties afhankelijk van het geselecteerde item:<br /><br /> -   [Tabbladeigenschappen](tab-properties-legacy.md)<br />-   [Eigenschappen van sectie](section-properties-legacy.md)<br />-   [Algemene veldeigenschappen](common-field-properties-legacy.md)<br />-   [Speciale veldeigenschappen](special-field-properties-legacy.md)<br />-  [Eigenschappen van subraster](sub-grid-properties-legacy.md)<br />-   [Eigenschappen van besturingselement Snelle weergave](quick-view-control-properties-legacy.md)|
||**Verwijderen**|Wis het geselecteerde item.|
||**Ongedaan maken** **(Ctrl+Z)**|Maak de vorige actie ongedaan.|
||**Opnieuw** **(Ctrl+Y)**|Voer de vorige actie opnieuw uit.|
|**Selecteren**|**Tekst**|Bewerk de hoofdtekst van het formulier.|
||**Koptekst**|Bewerk de koptekst van het formulier.|
||**Voettekst**|Bewerk de formuliervoettekst.|
||**Navigatie**|Bewerk de formuliernavigatie.<br /><br /> Meer informatie: [Navigatie bewerken](use-the-form-editor-legacy.md)
|**Formulier**|**Bedrijfsregels**|Bedrijfsregels weergeven, bewerken of maken met de Bedrijfsregelsverkenner **Opmerking:** Voor interactieve formulieren wordt alleen het bereik "Entiteit" en "Alle formulieren" ondersteund.<br /><br /> Meer informatie: [Bedrijfsregels maken en bewerken](create-business-rules-recommendations-apply-logic-form.md)|
||**Formuliereigenschappen**| Meer informatie: [Formuliereigenschappen](form-properties-legacy.md)|  
||**Preview**|Gebruik dit om te zien hoe het formulier er na publicatie uitziet. U kunt de voorbeeldfunctie ook gebruiken om scripts te testen die zijn gekoppeld aan formuliergebeurtenissen.|         
||**Beveiligingsrollen inschakelen**|Gebruik dit om in te stellen welke beveiligingsrollen toegang tot de formulieren hebben. Meer informatie: [Toegang tot rapporten beheren](control-access-forms.md) **Belangrijk:** als u een nieuw formulier aanmaakt, krijgen alleen de beveiligingsrollen Systeembeheerder en Systeemaanpasser toegang tot het formulier. U moet toegang tot andere beveiligingsrollen toewijzen voordat mensen het kunnen gebruiken.|  
||**Afhankelijkheden weergeven**|Zie welke oplossingsonderdelen van dit formulier afhankelijk zijn en welke oplossingsonderdelen door dit formulier worden vereist. |  
||**Beheerde eigenschappen**|De opdracht Beheerde eigenschappen heeft twee eigenschappen: **Aanpasbaar** en **Kan worden verwijderd**. Als u deze eigenschappen op onwaar instelt, kan het formulier niet meer worden aangepast of verwijderd nadat u het in een oplossing hebt opgenomen, deze oplossing exporteert als een beheerde oplossing en die beheerde oplossing in een andere omgeving importeert. Meer informatie: [Beheerde eigenschappen](../common-data-service/solutions-overview.md#managed-properties)| 
|**Upgraden**|**Formulieren samenvoegen**|Indien van toepassing kunt u dit formulier met deze optie samenvoegen met een formulier uit een eerdere versie van Dynamics 365|
  

## <a name="insert-tab"></a>Tabblad Invoegen  
> [!div class="mx-imgBorder"] 
> ![insert-tab](media/insert-tab.png)
 
Het tabblad Invoegen geeft de opdrachten in de volgende tabel weer:

|Groep|Opdracht|Beschrijving|
|-----------|-------------|-----------------| 
||**Sectie**|Een sectie toevoegen aan een geselecteerd tabblad. U kunt een sectie met een tot vier kolommen opnemen.<br /><br /> U kunt ook een verwijzingenpaneel invoegen in de interactieve formulieren. Het verwijzingenpaneel wordt ook als een sectie toegevoegd aan het formulier Hoofd - interactieve ervaring. Standaard wordt de sectie Verwijzingenpaneel toegevoegd aan de formulieren Aanvraag, Account, Contactpersoon en aangepaste entiteitsformulieren.<br /><br /> Meer informatie: [Eigenschappen van sectie](section-properties-legacy.md)|  
|**3 Tabbladen**|**Drie kolommen**|Voeg een tabblad met drie kolommen in die gelijke breedte hebben.<br /><br /> Meer informatie: [Tabbladeigenschappen](tab-properties-legacy.md)|  
||**Drie kolommen**|Voeg een tabblad met drie kolommen in waarvan de middelste kolom breder is.|  
|**2 Tabbladen**|**Twee kolommen**|Voeg een tabblad met twee kolommen in waarvan de rechter kolom breder is.|  
||**Twee kolommen**|Voeg een tabblad met twee kolommen in waarvan de linker kolom breder is.|  
||**Twee kolommen**|Voeg een tabblad met twee kolommen in die gelijke breedte hebben.|  
|**Tabblad**|**Eén kolom**|Voeg een tabblad met één kolom in.|  
|**Besturingselement**|**Subraster**|Maak een subraster op en voeg dit in het formulier in.<br /><br /> Meer informatie: [Eigenschappen van subraster](sub-grid-properties-legacy.md)|  
||**Opvulling**|Voeg een lege ruimte in.|  
||**Snelle-weergaveformulier**|Voeg een Snelle-weergaveformulier in.<br /><br /> Meer informatie: [Eigenschappen van besturingselement snelle weergave](quick-view-control-properties-legacy.md)|  
||**Webresource**|Voeg een webresource in om inhoud van andere locaties op één pagina in te sluiten.<br /><br /> Meer informatie: [Eigenschappen van webresource](web-resource-properties-legacy.md)|  
||**IFRAME**|U kunt een IFRAME toevoegen aan een formulier om inhoud van een andere website in een formulier te integreren.| 
||**Tijdlijn**|Voeg een tijdlijnbesturingselement in het formulier in. Dit besturingselement toont de tijdlijn van activiteiten die aan de entiteit op een formulier zijn gerelateerd.|  
||**Navigatiekoppeling**|Met deze optie kunt u een koppeling in een formuliernavigatie invoegen.|  
||**Timer**|Voeg een timer control in een entiteitsformulier in om tijd bij te houden voor een SLA. Meer informatie: [Een timerbesturingselement toevoegen](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-timer-control-case-form-track-time-against-sla)|
||**Zoeken in de Knowledge Base**|Voeg een zoekbesturingselement in waarmee gebruikers kennisartikelen kunnen zoeken. Meer informatie: [Zoekbesturingselement voor Knowledge Base](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-knowledge-base-search-control-forms)|  
||**Relatieassistent**|Met deze optie kunt u een besturingselement voor Relatieassistent in het formulier invoegen.|

>[!Note] 
>De volgende onderdelen worden niet ondersteund in de hoofdformulieren:<br> <ul> <li>Bing-kaarten <br><li>Yammer <br><li>Activiteitsfeeds <br> </li> </ul>


## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)  
