---
title: 'Besturingselementen Formulier weergeven en Formulier bewerken: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over de besturingselementen Formulier weergeven en Formulier bewerken
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/06/2017
ms.author: gregli
ms.openlocfilehash: 6e34b107c9ad47b5eee7711f5c2b474eb3f1a836
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39017842"
---
# <a name="edit-form-and-display-form-controls-in-powerapps"></a>Besturingselementen Formulier weergeven en Formulier bewerken in PowerApps
Een record weergeven, bewerken en maken in een gegevensbron.

## <a name="description"></a>Beschrijving
Als u een besturingselement **Formulier weergeven** toevoegt, kan de gebruiker alle velden van een record weergeven of alleen de velden die u opgeeft. Als u een besturingselement **Formulier bewerken** toevoegt, kan de gebruiker die velden bewerken, een record maken en de wijzigingen opslaan in een gegevensbron.

![Voorbeeld van de besturingselementen Formulier bewerken en Formulier weergeven](./media/control-form-detail/form-detail-intro.png)

Als u een besturingselement **[Galerie](control-gallery.md)** toevoegt, kunt u instellen dat met het besturingselement een tabel uit een gegevensbron wordt weergegeven. Vervolgens kunt u een formulier configureren om de record te laten zien die de gebruiker selecteert in de galerie. U kunt ook een of meer besturingselementen **[Knop](control-button.md)** toevoegen die de gebruiker kan selecteren om bewerkingen op te slaan of te annuleren, en om een record te maken. Door besturingselementen in combinatie te gebruiken, kunt u [een complete oplossing maken](../working-with-forms.md).

### <a name="record-selection"></a>Recordselectie
Voor beide typen formulieren geldt dat u de eigenschap **DataSource** instelt op een tabel met records. De eigenschap **Item** van het formulier stelt u dan in op een specifieke record uit die tabel. U kunt de eigenschap **Item** van een formulier bijvoorbeeld instellen op de eigenschap **SelectedItem** van een besturingselement **[Galerie](control-gallery.md)**. Wanneer de gebruiker een record selecteert in de galerie, wordt dezelfde record weergegeven in het formulier, met het verschil dat het formulier meer velden kan bevatten. Als de gebruiker teruggaat naar de galerie en een andere record selecteert, verandert de waarde van de eigenschap **SelectedItem** van de galerie. Hierdoor wordt de eigenschap **Item** van het formulier bijgewerkt, zodat daar de nieuw geselecteerde record wordt weergegeven.

Elk formulierbesturingselement bevat een of meer besturingselementen **[Kaart](control-card.md)**. Via de eigenschap **[DataField](control-card.md)** van een kaart kunt u [opgeven welk veld in de kaart wordt weergegeven en andere details](../add-form.md).

### <a name="create-a-record"></a>Een record maken
Wanneer de modus **Bewerken** actief is voor een besturingselement **Formulier bewerken**, kan de gebruiker de record bijwerken die is opgegeven in de eigenschap **Item** van het formulier. Bij inspectie retourneert de eigenschap **Mode** de waarde **Edit**.

Wanneer echter de modus **Nieuw** actief is voor een besturingselement **Formulier bewerken**, wordt de eigenschap **Item** genegeerd. In het formulier wordt geen bestaande record weergegeven. De waarden in elk veld komen in plaats daarvan overeen met de standaardwaarden van de gegevensbron waarmee u het formulier hebt geconfigureerd. De functie **[NewForm](../functions/function-form.md)** zorgt ervoor dat een formulier in deze modus wordt geplaatst.

U kunt bijvoorbeeld de eigenschap **[Text](properties-core.md)** van een knop instellen op de waarde **Nieuw** en de eigenschap **[OnSelect](properties-core.md)** op een formule waarin de functie **[NewForm](../functions/function-form.md)** wordt gebruikt. Als de gebruiker dan die knop selecteert, wordt het formulier in de modus **Nieuw** gezet zodat de gebruiker een record kan gaan maken met bekende waarden.

Een formulier wordt weer in de modus **Bewerken** geplaatst als de functie **[ResetForm](../functions/function-form.md)** of **[SubmitForm](../functions/function-form.md)** wordt voltooid.

* U kunt de eigenschap **[Text](properties-core.md)** van een knop instellen op de waarde **Annuleren** en de eigenschap **[OnSelect](properties-core.md)** op een formule waarin de functie **[ResetForm](../functions/function-form.md)** wordt gebruikt. Als de gebruiker die knop dan selecteert, worden eventuele wijzigingen die in behandeling zijn, verwijderd en komen de waarden in het formulier weer overeen met de standaardwaarden van de gegevensbron.
* U kunt de eigenschap **[Text](properties-core.md)** van een knop instellen op de waarde **Wijzigingen opslaan** en de eigenschap **[OnSelect](properties-core.md)** op een formule waarin de functie **[SubmitForm](../functions/function-form.md)** wordt gebruikt. Als de gebruiker dan die knop selecteert en de gegevensbron wordt bijgewerkt, worden de waarden in het formulier teruggezet op de standaardwaarden van de gegevensbron.

### <a name="save-changes"></a>Wijzigingen opslaan
Als u een knop **Wijzigingen opslaan** maakt zoals in de vorige sectie wordt beschreven, kan de gebruiker een record maken of bijwerken en vervolgens die knop selecteren om de wijzigingen op te slaan in de gegevensbron. U kunt in plaats daarvan een besturingselement **[Afbeelding](control-image.md)**  of een ander besturingselement configureren voor het uitvoeren van dezelfde taak, op voorwaarde dat u dat besturingselement configureert met de functie **[SubmitForm](../functions/function-form.md)**. In alle gevallen kunt u de eigenschappen **Error**, **ErrorKind**, **OnSuccess** en **OnFailure** gebruiken om feedback te geven over het resultaat.

Wanneer de functie **[SubmitForm](../functions/function-form.md)** wordt uitgevoerd, worden eerst de gegevens gevalideerd die de gebruiker wil verzenden. Als een vereist veld geen waarde bevat of een andere waarde niet voldoet aan een andere beperking, wordt de eigenschap **ErrorKind** ingesteld en wordt de formule **OnFailure** uitgevoerd. U kunt de knop **Wijzigingen opslaan** of een ander besturingselement zo configureren dat de gebruiker de knop alleen kan kiezen als de gegevens geldig zijn (als de eigenschap **Valid** van het formulier de waarde **true** heeft). De gebruiker moet niet alleen het probleem met de invoer oplossen, maar ook de knop **Wijzigingen opslaan** opnieuw selecteren om de eigenschappen **Error** en **ErrorKind** opnieuw in te stellen (of de wijzigingen verwijderen door de knop **Annuleren** te selecteren, zoals eerder beschreven).

Als de gegevens geldig zijn, worden ze met **[SubmitForm](../functions/function-form.md)** naar de gegevensbron verstuurd. Afhankelijk van de netwerklatentie kan dit enige tijd duren.

* Als de gegevens zijn verstuurd, wordt de eigenschap **Error** gewist, wordt de eigenschap **ErrorKind** ingesteld op **ErrorKind.None** en wordt de formule **OnSuccess** uitgevoerd. Als de gebruiker een record heeft gemaakt (de modus **Nieuw** was actief voor het formulier), wordt het formulier overgeschakeld naar de modus **Bewerken** zodat de gebruiker de nieuwe record of een andere record kan bewerken.
* Als het verzenden van de gegevens is mislukt, bevat de eigenschap **Error** een foutbericht afkomstig uit de gegevensbron waarin het probleem wordt toegelicht. De eigenschap **ErrorKind** wordt overeenkomstig het probleem ingesteld en de formule **OnFailure** wordt uitgevoerd.

Sommige gegevensbronnen kunnen vaststellen wanneer twee personen tegelijk dezelfde record proberen bij te werken. In dit geval wordt de eigenschap **ErrorKind** ingesteld op **ErrorKind.Conflict**. Het probleem kan worden opgelost door de gegevensbron te vernieuwen met de wijzigingen van de andere gebruiker en de wijziging van deze gebruiker opnieuw toe te passen.

> [!TIP]
> Als u een knop **Annuleren** opneemt op het formulier zodat de gebruiker wijzigingen kan afbreken,moet u ook de functie **[ResetForm](../functions/function-form.md)** toevoegen aan de eigenschap **[OnSelect](properties-core.md)** van de knop, zelfs als die eigenschap een functie **[Navigate](../functions/function-navigate.md)** bevat om van scherm te veranderen. Als u dat niet doet, blijven de wijzigingen van de gebruiker aanwezig in het formulier.

### <a name="layout"></a>Indeling
De standaardinstelling is dat kaarten in één kolom worden ingedeeld voor telefoon-apps en in drie kolommen voor tablet-apps. U kunt bij het configureren van het formulier opgeven hoeveel kolommen een formulier heeft en of kaarten moeten worden uitgelijnd op kolommen. Deze instellingen worden niet weergegeven als eigenschappen omdat ze alleen worden gebruikt om de eigenschappen **X**, **Y** en **Width** van de kaarten in te stellen.

Zie [De indeling van een gegevensformulieren begrijpen](../working-with-form-layout.md) voor meer informatie.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**DataSource**: de gegevensbron met de record die de gebruiker gaat weergeven, bewerken of maken.

* Als u deze eigenschap niet instelt, kan de gebruiker geen record weergeven, bewerken of maken, worden er geen aanvullende metagegevens aangeboden en is er geen validatie mogelijk.

**DefaultMode**: de eerste modus van het formulierbesturingselement.  Zie de beschrijving van **Mode** hieronder voor de toegestane waarden en hun betekenis. 

**DisplayMode**: de modus om te gebruiken voor gegevenskaarten en besturingselementen in het formulierbesturingselement.  

Afgeleid van de eigenschap **Mode** en kan niet onafhankelijk worden ingesteld:

| Modus | DisplayMode | Beschrijving |
| --- | --- | --- |
| **FormMode.Edit** |**DisplayMode.Edit** |Gegevenskaarten en besturingselementen zijn bewerkbaar, klaar om wijzigingen aan een record te accepteren. |
| **FormMode.New** |**DisplayMode.Edit** |Gegevenskaarten en besturingselementen zijn bewerkbaar, klaar om een nieuw record te accepteren. |
| **FormMode.View** |**DisplayMode.View** |Gegevenskaarten en besturingselementen zijn niet bewerkbaar en geoptimaliseerd om weer te geven. |

**Error**: een foutbericht dat voor dit formulier wordt weergegeven als de functie **[SubmitForm](../functions/function-form.md)** mislukt.

* Deze eigenschap is alleen van toepassing op het besturingselement **Formulier bewerken**.
* Deze eigenschap verandert alleen wanneer de functie **[SubmitForm](../functions/function-form.md)**, **EditForm** of **[ResetForm](../functions/function-form.md)** wordt uitgevoerd.
* Als er geen fout optreedt, is deze eigenschap *leeg* en wordt **ErrorKind** ingesteld op **ErrorKind.None**.
* Indien mogelijk wordt het foutbericht weergegeven in de taal van de gebruiker. Bepaalde foutberichten zijn rechtstreeks afkomstig uit de gegevensbron en zijn daarom mogelijk niet in de taal van de gebruiker opgesteld.

**ErrorKind**: als er tijdens de uitvoering van **SubmitForm** een fout optreedt, bevat deze eigenschap het soort fout dat is opgetreden.

* Deze eigenschap is alleen van toepassing op een besturingselement **Formulier bewerken**.
* Deze eigenschap heeft dezelfde opsomming als de functie **[Errors](../functions/function-errors.md)**. Een besturingselement **Formulier bewerken** kan deze waarden retourneren:

| ErrorKind | Beschrijving |
| --- | --- |
| **ErrorKind.Conflict** |Een andere gebruiker heeft dezelfde record gewijzigd, wat leidt tot een conflict. Voer de functie **[Refresh](../functions/function-refresh.md)** uit om de record opnieuw te laden en probeer de wijziging vervolgens opnieuw. |
| **ErrorKind.None** |De fout is van een onbekend type. |
| **ErrorKind.Sync** |De gegevensbron heeft een fout gemeld. Controleer de eigenschap **Error** voor meer informatie. |
| **ErrorKind.Validation** |Er is een algemeen probleem met de validatie geconstateerd. |

**Item**: de record in de **DataSource** die de gebruiker gaat weergeven of bewerken.

**LastSubmit**: de laatst ingediende record, inclusief alle door de server gegenereerde velden.

* Deze eigenschap is alleen van toepassing op het besturingselement **Formulier bewerken**.
* Als de gegevensbron automatisch velden genereert of berekent, zoals een veld **Id** met een uniek nummer, bevat de eigenschap **LastSubmit** deze nieuwe waarde nadat **SubmitForm** is voltooid.
* De waarde van deze eigenschap is beschikbaar in de formule **OnSuccess**.

**Mode**: het besturingselement bevindt zich in de modus **Bewerken** of **Nieuw**.

| Modus | Beschrijving |
| --- | --- |
| **FormMode.Edit** |De gebruiker kan een record bewerken met behulp van het formulier. De waarden in de kaarten van het formulier worden vooraf ingevuld op basis van de bestaande record, zodat de gebruiker deze kan wijzigen. Als de uitvoering **[SubmitForm](../functions/function-form.md)** goed wordt uitgevoerd, wordt een bestaande record gewijzigd. |
| **FormMode.New** |De gebruiker kan een record maken met behulp van het formulier. De waarden in de besturingselementen van het formulier worden vooraf ingevuld met de standaardwaarden voor een record van de gegevensbron. Als de functie **[SubmitForm](../functions/function-form.md)** goed wordt uitgevoerd, wordt er een record gemaakt. |
| **FormMode.View** |De gebruiker kan een record bekijken met behulp van het formulier. De waarden in de besturingselementen van het formulier worden vooraf ingevuld met de standaardwaarden voor een record van de gegevensbron. |

Het formulier wordt overgeschakeld van de modus **Nieuw** naar de modus **Bewerken** als zich een van deze wijzigingen voordoet:

* Het formulier is verzonden en er is een record gemaakt. Als de galerie zo is ingesteld dat automatisch deze nieuwe record moet worden geselecteerd, bevindt het formulier zich in de modus **Bewerken** voor de gemaakte record zodat de gebruiker aanvullende wijzigingen kan aanbrengen.
* De functie **[EditForm](../functions/function-form.md)** wordt uitgevoerd.
* De functie **[ResetForm](../functions/function-form.md)** wordt uitgevoerd. Dit gebeurt als de gebruiker bijvoorbeeld een knop **Annuleren** kiest die met deze functie is geconfigureerd.

**OnFailure**: hoe een app reageert wanneer een gegevensbewerking is mislukt.

* Deze eigenschap is alleen van toepassing op het besturingselement **Formulier bewerken**.

**OnReset**: hoe een app reageert wanneer het besturingselement **Edit form** opnieuw wordt ingesteld.

* Deze eigenschap is alleen van toepassing op het besturingselement **Formulier bewerken**.

**OnSuccess**: hoe een app reageert wanneer een gegevensbewerking is geslaagd.

* Deze eigenschap is alleen van toepassing op het besturingselement **Formulier bewerken**.

**Unsaved**: True als het besturingselement **Edit form** gebruikerswijzigingen bevat die niet zijn opgeslagen.

* Deze eigenschap is alleen van toepassing op het besturingselement **Formulier bewerken**.
* Gebruik deze eigenschap om de gebruiker te waarschuwen dat er niet-opgeslagen wijzigingen verloren gaan.  Om te voorkomen dat de gebruiker een andere record selecteert in een besturingselement **[Galerie](control-gallery.md)** voordat de wijzigingen in de huidige record zijn opgeslagen, stelt u de eigenschap **[Disabled](properties-core.md)** van de galerie in op **Form.Unsaved**. Bewerkingen om te vernieuwen moeten eveneens worden uitgeschakeld.

**Updates**: de waarden die moeten worden teruggeschreven naar de gegevensbron voor een record die in een formulierbesturingselement is geladen.  

* Deze eigenschap is alleen van toepassing op het besturingselement **Formulier bewerken**.
* Gebruik deze eigenschap om de veldwaarden op te halen uit de kaarten in het besturingselement.  U kunt deze waarden vervolgens gebruiken om de gegevensbron handmatig bij te werken via een aanroep van de functie **[Patch](../functions/function-patch.md)** of via een andere methode die beschikbaar wordt gemaakt door een verbinding.  U hoeft deze eigenschap niet te gebruiken als u de functie **[SubmitForm](../functions/function-form.md)** gebruikt.
* Deze eigenschap retourneert een record met waarden.  Als het formulierbesturingselement bijvoorbeeld kaartbesturingselementen bevat voor de velden **Naam** en **Aantal** en de waarden van de eigenschap **[Update](control-card.md)** voor deze kaarten respectievelijk 'Widget' en 10 retourneren, retourneert de eigenschap **Updates** voor het formulierbesturingselement **{ Naam: 'Widget', Aantal: 10 }**.

**Valid**: geeft aan of een besturingselement **[Kaart](control-card.md)** of **Formulier bewerken** geldige vermeldingen bevat die kunnen worden verzonden naar de gegevensbron.

* Deze eigenschap is alleen van toepassing op het besturingselement **Formulier bewerken**.
* De eigenschap **Valid** van een besturingselement **Formulier** is een verzameling van de eigenschappen **Valid** van alle besturingselementen **[Kaart](control-card.md)** in het formulier. De eigenschap **Valid** van een formulier is alleen **true** als de gegevens in alle kaarten in het formulier geldig zijn; anders heeft de eigenschap **Valid** van het formulier de waarde **false**.
* Als u een knop zo wilt instellen dat hiermee alleen gegevens in een formulier kunnen worden opgeslagen als de gegevens geldig zijn maar nog niet zijn verzonden, stelt u de eigenschap **DisplayMode** van de knop in op deze formule:
  
    **SubmitButton.DisplayMode = If(IsBlank( Form.Error ) || Form.Valid, DisplayMode.Edit, DisplayMode.Disabled)**

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="more-information"></a>Meer informatie
Zie [Gegevensformulieren begrijpen](../working-with-forms.md) voor een uitgebreid overzicht van de werking van formulieren.

## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* U kunt aan het formulier een kop toevoegen met een **[Label](control-text-box.md)**.
