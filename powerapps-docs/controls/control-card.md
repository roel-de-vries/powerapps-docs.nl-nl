---
title: 'Besturingselement voor kaart: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Kaart
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: e85b7ce4c51e693d566fb50b51be48f9ab3edadd
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="card-control-in-powerapps"></a>Besturingselement voor kaart in PowerApps
Gebruik dit besturingselement voor het weergeven en bewerken van één veld van een besturingselement **[Formulier weergeven](control-form-detail.md)** of **[Formulier bewerken](control-form-detail.md)**.

## <a name="description"></a>Beschrijving
De besturingselementen **[Formulier weergeven](control-form-detail.md)** en **[Formulier bewerken](control-form-detail.md)** fungeren als containers voor het weergeven en bewerken van volledige records. Elke container kan een set **Kaart**-besturingselementen bevatten die afzonderlijke velden weergeven of die het mogelijk maken die velden bij te werken. Elke kaart heeft een eigenschap **DataField** die aangeeft om welk veld van de record het gaat.  

Er zijn vooraf gedefinieerde kaarten voor verschillende gegevenstypen en gebruikerservaringen.  Zo is er een kaart om een numeriek veld met een besturingselement **[Tekstinvoer](control-text-input.md)** te bewerken, wat handig is voor gebruik met het toetsenbord. Een andere kaart kan het bewerken van een getal met behulp van een besturingselement **[Schuifregelaar](control-slider.md)** mogelijk maken. Als u het besturingselement in het formulier hebt geselecteerd, kunt u in het deelvenster aan de rechterkant eenvoudig een kaart selecteren op basis van een veld.

Kaarten zelf bevatten besturingselementen. De besturingselementen van een kaart bepalen de ervaring voor het weergeven en bewerken van één veld. Een numerieke kaart kan bijvoorbeeld bestaan uit een besturingselement **[Label](control-text-box.md)** voor de weergavenaam van het veld en een besturingselement **[Tekstinvoer](control-text-input.md)** voor het invoeren van de waarde van het veld. De kaart kan ook een besturingselement **[Label](control-text-box.md)** hebben waarin eventuele validatiefouten worden beschreven en een besturingselement **[Label](control-text-box.md)** voor een sterretje om aan te geven dat een veld vereist is.

U kunt de besturingselementen van een vooraf gedefinieerde kaart aanpassen door het formaat van de kaart te wijzigen, de kaart te verbergen, door er besturingselementen aan toe te voegen en door andere wijzigingen aan te brengen. U kunt ook beginnen met een volledig lege kaart, een 'aangepaste kaart', waaraan u zelf besturingselementen gaat toevoegen.

Vooraf gedefinieerde kaarten zijn standaard *vergrendeld*. In een vergrendelde kaart kunt u alleen bepaalde eigenschappen van de kaart of besturingselementen in de kaart wijzigen. Het is niet mogelijk om een vergrendelde kaart te verwijderen. U kunt de kaartvergrendeling weergeven en deze ontgrendelen op het tabblad **Beeld** van de weergave **Geavanceerd**. Als een eigenschap is vergrendeld en niet kan worden gewijzigd, wordt er naast de naam van de eigenschap een slotpictogram weergegeven. Het ontgrendelen van een kaart is een geavanceerde activiteit die met zorg moet worden uitgevoerd. De reden hiervoor is dat er dan niet langer automatisch een formule wordt gegenereerd voor de kaart en u een kaart niet opnieuw kunt vergrendelen.

In de container van het formulier is de record **ThisItem** beschikbaar met daarin alle velden van de record.  Zo is de eigenschap **[Standaard](properties-core.md)** van een kaart vaak ingesteld op **ThisItem**.*veldnaam*.

U kunt de verwijzing **Parent** gebruiken om een besturingselement te laten verwijzen naar de eigenschappen van een kaart.  Zo kan een besturingselement **Parent.Default** gebruiken om de beginstatus van het veld uit de gegevensbron te lezen. Door **Parent** te gebruiken in plaats van de gewenste informatie rechtstreeks te benaderen, wordt de kaart beter ingekapseld en kunt u de kaart koppelen aan een ander veld zonder interne formules te verbreken.

Zie [Informatie over gegevenskaarten](../working-with-cards.md) voor voorbeelden van het aanpassen, ontgrendelen en maken van kaarten.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**DataField**: de naam van het veld in een record die met deze kaart wordt weergegeven en bewerkt.

* Geef de naam op als een statische tekenreeks tussen dubbele aanhalingstekens (bijvoorbeeld **"Naam"**), niet als een formule.
* U kunt een kaart loskoppelen door de eigenschap **DataField** *leeg* te laten. De eigenschappen **Valid** en **Update** worden genegeerd voor niet-afhankelijke kaarten.

**[Default](properties-core.md)**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

* Voor elk besturingselement in een kaart moet u deze eigenschap instellen op **Parent.Default** om te verwijzen naar de standaardwaarde van het veld op basis van de gegevensbron. Stel de eigenschap **[Standaard](properties-core.md)** van een schuifregelaar bijvoorbeeld in op **Parent.Default** om ervoor te zorgen dat de gebruiker begint met een algemene waarde voor de schuifregelaar.

**DisplayMode**: mogelijke waarden zijn **Bewerken, Weergeven** of **Uitgeschakeld**. Configureert of invoer van de gebruiker in de kaart is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).  

* Door deze eigenschap te configureren, die standaard is gekoppeld aan het gedrag van het formulier, kan één kaart worden gebruikt in formulieren voor zowel bewerken als weergeven.
* In de modus **Weergeven**worden alleen de tekstwaarden van onderliggende besturingselementen zoals **[Tekstinvoer](control-text-input.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Datumkiezer](control-date-picker.md)** weergegeven en worden niet alle interactieve elementen of versieringen weergegeven.

**DisplayName**: de gebruiksvriendelijke naam voor een veld in een gegevensbron.

* De functie **[DataSourceInfo](../functions/function-datasourceinfo.md)** biedt deze metagegevens aan vanuit de gegevensbron.
* Besturingselementen in de kaart moeten **Parent.DisplayName** gebruiken om te verwijzen naar de naam van het veld.

**Error**: het foutbericht dat voor dit veld wordt weergegeven als de validatie is mislukt.

* Deze eigenschap wordt ingesteld wanneer **SubmitForm** wordt aangeroepen.  
* Het bericht beschrijft validatieproblemen op basis van metagegevens uit de gegevensbron en een controle van de eigenschap **Vereist** van de kaart.

**Required**: bepaalt of een kaart voor het bewerken van het veld van een gegevensbron een waarde moet bevatten.

* De functie **[DataSourceInfo](../functions/function-datasourceinfo.md)** biedt de vereiste metagegevens aan vanuit de gegevensbron.
* Besturingselementen in de kaart moeten **Parent.Required** gebruiken om te bepalen of het veld van deze kaart vereist is.

**Update**: de waarde die moet worden teruggeschreven naar de gegevensbron voor een veld.

* Gebruik de formule van deze eigenschap om de waarden op te halen uit de besturingselementen voor bewerken van de kaart om deze terug te schrijven naar de gegevensbron. Stel de eigenschap **Bijwerken** van een kaart bijvoorbeeld in op **Slider.Value** om de gegevensbron bij te werken met een waarde van de schuifregelaar in deze kaart.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[WidthFit](properties-size-location.md)**: bepaalt of een besturingselement automatisch horizontaal meeschaalt om lege ruimte te vullen in een containerbesturingselement, zoals een besturingselement **[Formulier bewerken](control-form-detail.md)**. Als deze eigenschap voor meerdere kaarten is ingesteld op **true**, wordt de ruimte over de kaarten verdeeld. Zie [De indeling van een gegevensformulieren begrijpen](../working-with-form-layout.md) voor meer informatie.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**Valid**: geeft aan of een besturingselement **Kaart** of **[Formulier bewerken](control-form-detail.md)** geldige vermeldingen bevat die kunnen worden verzonden naar de gegevensbron.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is). Als u een besturingselement **[Kaart](control-card.md)** hebt in een container met meerdere kolommen, bepaalt deze eigenschap de kolom waarin de kaart wordt weergegeven.

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is). Als u een besturingselement **[Kaart](control-card.md)** hebt in een container met meerdere rijen, bepaalt deze eigenschap de rij waarin de kaart wordt weergegeven.

## <a name="examples"></a>Voorbeelden
Zie [Gegevenskaarten begrijpen](../working-with-cards.md) en [De indeling van een gegevensformulier begrijpen](../working-with-form-layout.md) voor voorbeelden.

