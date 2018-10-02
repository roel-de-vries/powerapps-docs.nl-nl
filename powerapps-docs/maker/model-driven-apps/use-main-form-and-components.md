---
title: Het hoofdformulier voor modelgestuurde apps en de onderdelen gebruiken in PowerApps | Microsoft Docs
description: Ontdek hoe u het hoofdformulier en de onderdelen ervan in de Unified Interface-apps gebruikt
keywords: Hoofdformulieren; Klantenservice; Customer Service-hub; Dynamics 365
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 43bfface-4dc2-411d-99a1-83e934646989
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-the-model-driven-app-main-form-and-its-components"></a>Het hoofdformulier voor modelgestuurde apps en de onderdelen gebruiken

Formulieren in de Unified Interface-apps bieden een betere gebruikerservaring voor optimale agentproductiviteit en helpen gebruikers de context te bewaren wanneer zij werken aan gerelateerde records. U kunt de formulieren bekijken die in de oplossingsverkenner worden vermeld. Het formuliertype van het nieuwe formulier is **Hoofd**.

In dit onderwerp wordt uitgelegd hoe u een hoofdformulier kunt bewerken en verschillende elementen van het formulier kunt toevoegen of wijzigen.

## <a name="open-the-form-editor"></a>De formuliereneditor openen.

Als u een formulier wilt bewerken of elementen wilt toevoegen of wijzigen, gebruikt u de formuliereneditor. In de formuliereneditor kunt u formulieren voor alle Unified Interface-apps bewerken.

Voer de onderstaande procedures uit om de formuliereneditor te openen. 

> [!NOTE]
> Als u nieuwe oplossingsonderdelen maakt tijdens het bewerken van het formulier, gebruiken de namen van de onderdelen het aanpassingsvoorvoegsel van de oplossingsuitgever voor de standaardoplossing en worden deze onderdelen alleen opgenomen in de standaardoplossing. Als u wilt dat nieuwe oplossingsonderdelen worden opgenomen in een specifieke onbeheerde oplossing, moet u de formuliereneditor openen via die onbeheerde oplossing.


### <a name="access-the-form-editor-through-app-designer-in-powerapps"></a>De formuliereneditor openen via de appontwerper in PowerApps

1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

2.  In het linkernavigatiedeelvenster selecteert u **Apps**, selecteert u de gewenste app en selecteert u **Bewerken** op de werkbalk.  

3. Selecteer op het canvas van de appontwerper de pijl-omlaag ![Pijl-omlaag voor appontwerper](media/down-arrow-app-designer.png) naast een entiteit om te zien welke formulieren beschikbaar zijn voor die entiteit. 

4. Selecteer de knop voor het openen van de ontwerper ![ontwerper openen](media/site-map-designer.png)voor het formulier dat u wilt bewerken.

   ![Formuliereneditor in appontwerper](media/app-designer-forms.png)
 
5. In de formulierontwerper voert u uw wijzigingen door en vervolgens selecteert u **Opslaan** om de wijzigingen op te slaan en selecteer **Publiceren** om deze te exporteren voor gebruik in de app. 

> [!NOTE]
> Als u andere wijzigingen hebt aangebracht in de app, publiceert u deze met de optie voor publicatie op appniveau. Zie [Een app valideren en publiceren met de appontwerper](validate-app.md) voor meer informatie.

> [!NOTE]
> Het hoofdformulier voor de webclient is ook compatibel met de Customer Service-hub en kan worden bewerkt met de appontwerper.


### <a name="access-the-form-editor-through-the-default-solution"></a>De formuliereneditor openen via de standaardoplossing

1.  Op de site [PowerApps](https:///?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

     ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**.  

3. In de lijst met formulieren opent u het formulier van het type **Hoofd**.

### <a name="access-the-form-editor-for-an-unmanaged-solution"></a>De formuliereneditor voor een onbeheerde oplossing openen

1. Open [oplossingen](advanced-navigation.md#solutions).
2. Dubbelklik op de onbeheerde oplossing waarmee u wilt werken. Het type oplossing, beheerd of onbeheerd, wordt weergegeven in de kolom **Pakkettype**.
3. Zoek in de lijst met onderdelen de entiteit met het formulier dat u wilt bewerken. Als de entiteit er niet is, moet u die toevoegen.

#### <a name="add-an-entity-to-an-unmanaged-solution"></a>Een entiteit toevoegen aan een onbeheerde oplossing

1. Selecteer terwijl de onbeheerde oplossing is geopend in de oplossingenverkenner het knooppunt **Entiteiten**. Selecteer vervolgens **Bestaande toevoegen** op de werkbalk boven de lijst.

     > [!div class="mx-imgBorder"] 
     > ![Bestaande entiteit toevoegen](media/add-existing-entity.png)

2. Selecteer de entiteit die u wilt toevoegen in het dialoogvenster **Oplossingsonderdelen selecteren**, waarbij de schakelaar **Onderdeeltype** is ingesteld op **Entiteit** en selecteer **OK**.

3. Als het dialoogvenster **Er ontbreken vereiste onderdelen** wordt weergegeven, kunt u de optie **Nee, vereiste onderdelen niet toevoegen** selecteren als u niet van plan bent de onbeheerde oplossing naar een andere organisatie te exporteren. Als u ontbrekende vereiste onderdelen op dit moment niet wilt opnemen, kunt u ze later toevoegen. U ontvangt opnieuw een melding als u deze oplossing in de toekomst exporteert.

4. Vouw in de oplossingsverkenner de entiteit uit met het formulier dat u wilt bewerken en selecteer **Formulieren**.

5. In de lijst met formulieren opent u het formulier van het type **Hoofd**.

#### <a name="publish-the-changes-for-use-in-the-app"></a>De wijzigingen publiceren voor gebruik in de app

Bepaalde aanpassingen die wijzigingen in de gebruikersinterface toepassen, moeten worden gepubliceerd voordat mensen ze kunnen gebruiken in de toepassing. Als u uw aanpassing wilt publiceren, selecteert u op de werkbalk van de oplossingenverkenner de optie **Alle aanpassingen publiceren**.

## <a name="form-editor-user-interface"></a>Gebruikersinterface van de formuliereneditor

Zie [Overzicht van de gebruikersinterface van de formuliereneditor](form-editor-user-interface-legacy.md) voor gedetailleerde informatie over de gebruikersinterface van de formuliereneditor.

## <a name="form-properties"></a>Formuliereigenschappen

Zie [Formuliereigenschappen](form-properties-legacy.md) voor gedetailleerde informatie over de formuliereigenschappen.

## <a name="visibility-options"></a>Zichtbaarheidsopties  
 Sommige typen formulierelementen hebben standaard de optie om te worden weergegeven of te worden verborgen. Tabbladen, secties en velden bieden alle deze optie. Met formulierscripts of bedrijfsregels kan de zichtbaarheid van deze elementen worden beheerd om een dynamisch formulier te maken om een gebruikersinterface te bieden die zich aanpast aan voorwaarden in het formulier. 
  
> [!NOTE]
>  Het verbergen van formulierelementen is geen aanbevolen manier om beveiliging af te dwingen. Er zijn verschillende manieren waarop personen alle elementen en gegevens in het formulier kunnen zien wanneer elementen zijn verborgen. Zie [Formulierelementen weergeven of verbergen](visibility-options-legacy.md) voor meer informatie. 
  
## <a name="tab-properties"></a>Tabbladeigenschappen  

In de hoofdtekst van een formulier bieden tabbladen horizontale scheiding. Tabbladen hebben een label dat kan worden weergegeven. Als het label wordt weergegeven, kunnen tabbladen worden uitgevouwen of samengevouwen om de inhoud weer te geven of te verbergen door het label te kiezen. Raadpleeg [Tabbladeigenschappen](tab-properties-legacy.md) voor gedetailleerde informatie over de tabbladeigenschappen.


## <a name="section-properties"></a>Eigenschappen van sectie  

Een sectie in een formulier neemt de ruimte in beslag die beschikbaar is in een tabbladkolom. Secties hebben een label dat kan worden weergegeven en een regel kan onder het label worden weergegeven. Raadpleeg [Sectie-eigenschappen](section-properties-legacy.md) voor gedetailleerde informatie over de sectie-eigenschappen.
  
## <a name="timeline"></a>Tijdlijn  
 Op de tijdlijn worden gerelateerde activiteiten voor een bepaalde entiteit weergegeven.  
  
 De volgende typen activiteiten worden ondersteund: taak, afspraak, telefoongesprek, e-mail, sociale activiteit, aangepaste activiteit.  
  
 Op de tijdlijn worden ook notities en systeem- en gebruikersberichten weergegeven. U ziet de activiteiten waarvoor het veld **Betreft** is ingesteld op de entiteit die u bekijkt. Voor notities is het veld **Betreft** niet zichtbaar voor de gebruiker, het is impliciet als het wordt gemaakt via de tijdlijn.  
  
 Elke activiteit die op de tijdlijn wordt getoond, heeft dezelfde snelle acties die beschikbaar zijn op de opdrachtbalk van de activiteit.  

## <a name="common-field-properties"></a>Algemene veldeigenschappen  

Raadpleeg [Algemene veldeigenschappen](common-field-properties-legacy.md) voor gedetailleerde informatie over de algemene veldeigenschappen. 
  
## <a name="special-field-properties"></a>Speciale veldeigenschappen  
 De eigenschappen van alle velden worden vermeld in [Algemene veldeigenschappen](common-field-properties-legacy.md), maar bepaalde velden bevatten aanvullende eigenschappen. Raadpleeg [Speciale veldeigenschappen](special-field-properties-legacy.md) voor meer informatie.

  
## <a name="sub-grid-properties"></a>Eigenschappen van subraster  

U kunt een subraster op een formulier configureren om een lijst met records of een grafiek weer te geven. Raadpleeg [Eigenschappen van subraster](sub-grid-properties-legacy.md) voor gedetailleerde informatie over de subrastereigenschappen.

## <a name="quick-view-control-properties"></a>Eigenschappen van besturingselement Snelle weergave  

Met een besturingselement voor snelle weergave in een formulier worden gegevens weergegeven van een record die is geselecteerd in een opzoekveld op het formulier. Zie [Eigenschappen van besturingselement snelle weergave](quick-view-control-properties-legacy.md) voor meer informatie over de eigenschappen van het besturingselement Snelle weergave.
  
## <a name="web-resource-properties"></a>Webresource-eigenschappen  

U kunt webresources toevoegen aan of bewerken in een formulier om het aantrekkelijker en bruikbaarder te maken voor app-gebruikers. Webresources met formulieren zijn besturingselementen voor afbeeldingen, HTML-bestanden of Silverlight. Kom meer te weten over de webresource-eigenschappen. Ga naar [Webresource-eigenschappen](web-resource-properties-legacy.md). 
  
## <a name="iframe-properties"></a>Eigenschappen van IFrame  

U kunt iFrames toevoegen aan een formulier om inhoud van een andere website in een formulier te integreren. Raadpleeg [Eigenschappen van IFRAME](iframe-properties-legacy.md) voor meer informatie over de IFRAME-eigenschappen. 
  
## <a name="edit-navigation"></a> Navigatie bewerken  
 Met de navigatie binnen het formulier kunnen personen lijsten met gerelateerde records bekijken. Elke entiteitsrelatie heeft eigenschappen om te beheren of de relatie moet worden weergegeven. Meer informatie: [Navigatiedeelvensteritem voor primaire entiteit ](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity)
  
 Alle entiteitsrelaties die zijn geconfigureerd om te worden weergegeven, kunnen worden genegeerd in de formuliereneditor.  
  
 Raadpleeg [Formuliernavigatie voor gerelateerde entiteiten toevoegen](add-edit-form-navigation-related-entities.md) voor stapsgewijze instructies.
  
 Om navigatie bewerken in te schakelen, moet u eerst **Navigatie** selecteren in de groep **Selecteren** van het tabblad **Start**.  
  
 In de **Relatieverkenner** kunt u filteren met behulp van 1:N (een-op-veel)- of N:N (veel-op-veel)-relaties, of alle beschikbare relaties bekijken. Het **selectievakje Alleen ongebruikte relaties weergeven** is uitgeschakeld en geselecteerd. U kunt elke relatie dus slechts één keer toevoegen.  
  
 Als u een relatie van de **Relatieverkenner** wilt toevoegen, dubbelklikt u er gewoon op en de relatie wordt toegevoegd onder de momenteel geselecteerde relatie in het navigatiegebied. Dubbelklik op een relatie in het navigatiegebied en u kunt het label op het tabblad **Weergeven** wijzigen. Op het tabblad **Naam** kunt u informatie over de relatie zien. Gebruik de knop **Bewerken** om de definitie van de entiteit te openen.  
  
 Er zijn vijf groepen in het navigatiegebied. U kunt ze verslepen om ze te verplaatsen en erop dubbelklikken om het label te wijzigen, maar u kunt ze niet verwijderen. Deze groepen worden alleen weergegeven wanneer er iets in zit. Als u een groep niet wilt weergeven, moet er u niets aan toevoegen.  
  
## <a name="configure-event-handlers"></a>Gebeurtenis-handlers configureren  

Een gebeurtenishandler bestaat uit een verwijzing naar een JavaScript-webresource en een functie die binnen deze webresource is gedefinieerd en wordt uitgevoerd wanneer de gebeurtenis optreedt. Raadpleeg [Gebeurtenishandlers configureren](configure-event-handlers-legacy.md) voor meer informatie over het configureren van gebeurtenishandlers. 
  
## <a name="next-steps"></a>Volgende stappen  
 [Formulieren maken en ontwerpen](create-design-forms.md)   
 [Formulieren voor snelle invoer maken en bewerken](create-edit-quick-view-forms.md)   
 [Snelle-weergaveformulieren maken en bewerken](create-edit-quick-view-forms.md)
