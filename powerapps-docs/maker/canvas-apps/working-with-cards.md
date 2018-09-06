---
title: Gegevenskaarten begrijpen | Microsoft Docs
description: Gebruik in PowerApps formulierkaarten voor het verzamelen en weergeven van gegevens uit een gegevensbron.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/26/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: db0e42a45af217e9e5703242c2a5a867a52b687b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850525"
---
# <a name="understand-data-cards-in-powerapps"></a>Gegevenskaarten in PowerApps

**[Kaart](controls/control-card.md)** besturingselementen zijn de bouwstenen van de besturingselementen **[Formulier bewerken](controls/control-form-detail.md)** en  **[Formulier weergeven](controls/control-form-detail.md)** in canvas-apps. Het formulier vertegenwoordigt de volledige record en elke kaart één veld van dat record.

U kunt het gemakkelijkst met kaarten werken in het rechterdeelvenster nadat u een formulierbesturingselement in de ontwerpwerkruimte hebt geselecteerd. In dit deelvenster kunt u kiezen welke velden u wilt weergeven, de weergave van elk veld en in welke volgorde deze moeten worden weergegeven. In dit voorbeeld ziet u een besturingselement **Formulier bewerken** in een app die is gebouwd op basis van een SharePoint-lijst met de naam **Assets**.

![Eerste scherm](./media/working-with-cards/first-screen.png)

Als u wilt beginnen met kaarten, leest u [Een formulier toevoegen](add-form.md) en [Gegevensformulieren begrijpen](working-with-forms.md). In de rest van dit onderwerp krijgt u meer informatie over hoe kaarten werken en hoe u deze kunt aanpassen of zelf maken.

## <a name="predefined-cards"></a>Vooraf gedefinieerde kaarten

PowerApps biedt een vooraf gedefinieerde set kaarten voor tekenreeksen, cijfers en andere gegevenstypen. U kunt in het rechterdeelvenster de beschikbare variaties zien en de kaart die wordt gebruikt voor een veld wijzigen:

![](./media/working-with-cards/selected-card.png)

In dit voorbeeld wordt een kaart met één regel tekst geselecteerd, maar de tekst van de URL is langer dan op één regel kan worden weergegeven. Laten we dit wijzigen in een kaart met meerdere regels tekst om onze gebruikers meer ruimte te geven om bewerkingen uit te voeren:

![](./media/working-with-cards/multiline-edit.png)

Verschillende velden van deze gegevensbron worden niet weergegeven, maar u kunt een veld weergeven of verbergen door het bijbehorende selectievakje te selecteren. In dit voorbeeld ziet u hoe u het veld **SecurityCode** kunt weergeven.

![](./media/working-with-cards/add-security-code.png)

## <a name="customize-a-card"></a>Een kaart aanpassen
Kaarten bestaan uit nog meer besturingselementen. In een besturingselement **Formulier bewerken** voert de gebruiker gegevens in een standaardbesturingselement **[Tekstinvoer](controls/control-text-input.md)** dat u kunt toevoegen vanuit het tabblad **Invoegen**.  

We nemen een voorbeeld door van hoe het uiterlijk van de kaart kan worden gewijzigd door besturingselementen te manipuleren.

1. Eerst gaan we terug naar de kaart die we het recentst hebben geplaatst, die voor het veld **SecurityCode**. Selecteer deze kaart door er één keer op te klikken of te tikken:
   
    ![](./media/working-with-cards/select-security-code.png)
2. Selecteer het besturingselement **[Tekstinvoer](controls/control-text-input.md)** in de kaart door op het invoerbesturingselement zelf te klikken of te tikken.
   
    ![](./media/working-with-cards/select-text-input.png)
3. U kunt dit besturingselement binnen de kaart verplaatsen door het selectievakje te slepen, en u kunt de grootte van het besturingselement wijzigen door de ingangen langs de rand van het selectievakje te slepen:
   
    ![](./media/working-with-cards/customize-text-input.png)  

U kunt in een kaart het besturingselement vergroten, verkleinen, verplaatsen of andere wijzigingen aanbrengen, maar u kunt het niet verwijderen zonder het eerst te ontgrendelen.

## <a name="unlock-a-card"></a>Een kaart ontgrendelen
Kaarten bevatten besturingselementen maar zijn zelf ook besturingselementen met eigenschappen en formules net als andere besturingselementen. Wanneer u ervoor kiest om een veld in een formulier weer te geven, maakt het rechterdeelvenster automatisch de kaart voor u en genereert de benodigde formules.  U ziet deze formules in het tabblad **Geavanceerd** van het rechterdeelvenster:

![](./media/working-with-cards/advanced-locked.png)

We zien hier meteen een van de belangrijkste eigenschappen van de kaart: de eigenschap **[DataField](controls/control-card.md)**. Deze eigenschap geeft aan welk veld van de gegevensbron de gebruiker kan zien en bewerken in deze kaart.  

In het tabblad **Geavanceerd** geeft de grote banner bovenaan aan dat de eigenschappen van deze kaart zijn vergrendeld. Er wordt ook een vergrendelingspictogram weergegeven naast de eigenschappen **[DataField](controls/control-card.md)**, **[DisplayName](controls/control-card.md)** en **[Required](controls/control-card.md)**. Het rechterdeelvenster creëert deze formules en de vergrendeling voorkomt onbedoelde wijzigingen aan deze eigenschappen.

![](./media/working-with-cards/lock-icons.png)

Klik of tik op de banner bovenaan voor het ontgrendelen van de kaart zodat u deze eigenschappen kunt wijzigen:

![](./media/working-with-cards/unlocked-card.png)

We wijzigen nu de **[DisplayName](controls/control-card.md)** zodat er een spatie tussen **Asset** en **ID** komt te staan. Door deze wijziging, wijzigen we wat er voor ons is gegenereerd.  Deze kaart heeft in het rechterdeelvenster een andere label:

![](./media/working-with-cards/change-display-name.png)

We hebben nu de controle over deze kaart en kunnen deze verder aanpassen aan wat we nodig hebben. Maar we kunnen de kaart niet meer van de ene weergave in de andere veranderen (bijvoorbeeld tekst met één regel naar tekst met meerdere regels), zoals we eerder hebben gedaan. We hebben de vooraf gedefinieerde kaart omgezet in een 'aangepaste kaart' die we nu zelf bepalen.  

> [!IMPORTANT]
> U kunt een eenmaal ontgrendelde kaart niet meer vergrendelen. U kunt de vergrendelde status herstellen door de kaart te verwijderen en opnieuw in het rechterdeelvenster te plaatsen.

U kunt het uiterlijk en gedrag van een niet-vergrendelde-kaart op verschillende manieren wijzigen, zoals het toevoegen en verwijderen van besturingselementen in de kaart. U kunt bijvoorbeeld een stervorm uit het menu **Pictogrammen** in het tabblad **Invoegen** toevoegen.

![](./media/working-with-cards/add-star.png)

De ster maakt nu deel uit van de kaart en verhuist mee met de kaart als u bijvoorbeeld de volgorde van de kaarten in het formulier wijzigt.

Ontgrendel als ander voorbeeld de kaart **AfbeeldingsURL** en voeg vervolgens een besturingselement **Afbeelding** toe uit het tabblad **Invoegen**:

![](./media/working-with-cards/add-image.png)

Stel in de formulebalk de eigenschap **Image** van dit besturingselement in op *Tekstvak*.**Tekst**. Hierin is *Tekstvak* de naam van het besturingselement **Tekstinvoer** dat de URL bevat:

> [!TIP]
> Druk op de Alt-toets om de naam van elk besturingselement weer te geven.

![](./media/working-with-cards/show-image.png)

En nu kunnen we de afbeeldingen zien en de URL's bewerken. Let op: we hadden **Parent.Default** kunnen gebruiken als de **Image**-eigenschap, maar deze wordt niet bijgewerkt wanneer de gebruiker de URL wijzigt.

We kunnen in het tweede scherm van deze app hetzelfde doen. We gebruiken dan een besturingselement **Formulier weergeven** om de details van een record weer te geven. In dit geval wilt u mogelijk het label verbergen (stel de eigenschap **Visible** van het label, niet de kaart, in op **false**) omdat de gebruiker de URL op dat scherm niet bewerkt:

![](./media/working-with-cards/show-image-display.png)

## <a name="interact-with-a-form"></a>Communiceren met een rapport
Nadat u een kaart hebt ontgrendeld, kunt u de interactie met het formulier wijzigen.

Hieronder vindt u enkele richtlijnen voor hoe besturingselementen moeten werken in combinatie met hun kaart en hoe de kaarten moeten werken in combinatie met het formulier. Dit zijn slechts richtlijnen. Net als bij elk besturingselement in PowerApps kunt u formules maken die verwijzen naar een ander besturingselement in PowerApps, en dat geldt ook voor kaarten en besturingselementen binnen kaarten. Wees creatief: er zijn veel manieren om een app te maken.  

### <a name="datafield-property"></a>De eigenschap DataField
De belangrijkste eigenschap op de kaart is de eigenschap **[DataField](controls/control-card.md)**.  Deze eigenschap bepaalt de validatie, welke veld wordt bijgewerkt, en andere aspecten van de kaart.

### <a name="information-flowing-in"></a>Binnenkomende gegevens
Als container komt op het formulier **ThisItem** beschikbaar voor alle kaarten die het bevat. Deze record bevat alle velden voor de huidige belangrijke record.  

De eigenschap **[Default](controls/properties-core.md)** van elke kaart moet worden ingesteld op **ThisItem**.*FieldName*.  Onder bepaalde omstandigheden is het raadzaam deze waarde in het begin te veranderen. U wilt bijvoorbeeld een tekenreeks opmaken of de waarde naar een andere taal omzetten.

Elk besturingselement in de kaart moet verwijzen naar **Parent.Default** om bij de waarde van het veld te komen. Deze strategie biedt een niveau van inkapseling voor de kaart zodat de eigenschap **[Default](controls/properties-core.md)** van de kaart kan wijzigen zonder dat de interne formules van de kaart worden gewijzigd.

Standaard worden de eigenschappen **DefaultValue** en **[Required](controls/control-card.md)** opgehaald uit de metagegevens van de gegevensbron op basis van de eigenschap **[DataField](controls/control-card.md)**. U kunt deze formules overschrijven met uw eigen logica, en de metagegevens van de gegevensbron integreren met behulp van de functie **[DataSourceInfo](functions/function-datasourceinfo.md)**.

### <a name="information-flowing-out"></a>Uitgaande gegevens
Nadat de gebruiker een record wijzigt met behulp van besturingselementen in de kaarten slaat de functie **[SubmitForm](functions/function-form.md)** de wijzigingen op in de gegevensbron. Wanneer deze functie wordt uitgevoerd, leest het besturingselement in het formulier de waarden van de eigenschap **[DataField](controls/control-card.md)** van elke kaart om te weten welk veld moet worden gewijzigd.  

Het besturingselement van het formulier leest ook de waarde van de eigenschap **[Update](controls/control-card.md)** van elke kaart. Deze waarde wordt opgeslagen in de gegevensbron voor dit veld. Dit is de plek waar u een andere transformatie kunt toepassen, bijvoorbeeld als u de transformatie die is toegepast in de **[Standaard](controls/properties-core.md)**-formule van de kaart ongedaan wilt maken.

De eigenschap **Valid** wordt aangestuurd vanuit de metagegevens van de gegevensbron op basis van de eigenschap **[DataField](controls/control-card.md)**. Deze is ook gebaseerd op de eigenschap **[Required](controls/control-card.md)** en is afhankelijk van of de eigenschap **[Update](controls/control-card.md)** een waarde bevat. Als de waarde in de eigenschap **[Update](controls/control-card.md)** niet geldig is, biedt de eigenschap **Error** een beschrijvend foutbericht.

Als de eigenschap **[DataField](controls/control-card.md)** van een kaart *Leeg* is, is de kaart slechts een container van besturingselementen. De eigenschappen **Valid** en **[Update](controls/control-card.md)** zijn niet actief wanneer het formulier wordt verzonden.

## <a name="dissecting-an-example"></a>Een voorbeeld ontleden
We bekijken de besturingselementen die samen een kaartinvoer van gegevens vormen. De afstand tussen de besturingselementen is vergroot zodat elk besturingselement beter zichtbaar is:

![](./media/working-with-cards/dissect-card1.png)

Houd de Alt-toets ingedrukt om de namen van de besturingselementen weer te geven die samen deze kaart vormen:

![](./media/working-with-cards/dissect-card2.png)

Vier besturingselementen zorgen ervoor dat deze kaart werkt:

| Naam | Type | Beschrijving |
| --- | --- | --- |
| **TextRequiredStar** |Het besturingselement **[Label](controls/control-text-box.md)** |Toont een ster, doorgaans gebruikt in formulieren voor gegevensinvoer om aan te geven dat een veld is vereist. |
| **TextFieldDisplayName** |Het besturingselement **[Label](controls/control-text-box.md)** |Toont de beschrijvende naam van dit veld. Deze naam kan afwijken van de naam in het schema van de gegevensbron. |
| **InputText** |Het besturingselement **InputText** |Toont de beginwaarde van het veld en geeft de gebruiker de gelegenheid die waarde te wijzigen. |
| **TextErrorMessage** |Het besturingselement **[Label](controls/control-text-box.md)** |Toont een beschrijvend foutbericht aan de gebruiker als er een probleem optreedt bij validatie. Zorgt er ook voor dat het veld een waarde bevat, indien dit is vereist. |

Door deze besturingselementen te vullen met gegevens, kunnen de bijbehorende eigenschappen worden bepaald vanuit de eigenschappen van de kaart, via deze formules. Houd er rekening mee dat geen van deze formules naar een bepaald veld verwijst. Alle gegevens zijn afkomstig van de kaart.

| Eigenschap van het besturingselement | Formule | Beschrijving |
| --- | --- | --- |
| **TextRequiredStar.Visible** |**Parent.Required** |De ster wordt alleen weergegeven als het veld is vereist. 'Vereist' is een formule die wordt aangedreven door u of door de metagegevens van de gegevensbron. |
| **TextFieldDisplayName.Text** |**Parent.DisplayName** |Het tekstvakbesturingselement toont de beschrijvende naam die door u of door de metagegevens van de gegevensbron worden geboden en die is ingesteld op de eigenschap van de kaart **[DisplayName](controls/control-card.md)**. |
| **InputText.Default** |**Parent.Default** |In het tekstinvoerbesturingselement vindt u in eerste instantie de waarde van het veld van de gegevensbron, zoals bepaald door de standaardwaarde van de kaart. |
| **TextErrorMessage.Text** |**Parent.Error** |Als een validatieprobleem optreedt, biedt de eigenschap **Error** van de kaart een bijpassend foutbericht. |

Als u gegevens wilt ophalen uit deze besturingselementen en terug in de gegevensbron wilt plaatsen, bieden we de volgende formules:

| De naam van het besturingselement | Formule | Beschrijving |
| --- | --- | --- |
| **DataCard.DataField** |**"ApproverEmail"** |De naam van het veld dat de gebruiker kan weergeven en bewerken in deze kaart. |
| **DataCard.Update** |**InputText.Text** |De waarde die moet worden gevalideerd en teruggeplaatst in de gegevensbron wanneer **[SubmitForm](functions/function-form.md)** wordt uitgevoerd. |

