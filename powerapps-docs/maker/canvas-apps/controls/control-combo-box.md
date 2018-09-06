---
title: 'Besturingselement voor keuzelijst met invoervak: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Keuzelijst met invoervak
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/13/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 278560c1ececafd6d4c57945d6058879cf55170f
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42858308"
---
# <a name="combo-box-control-in-powerapps"></a>Besturingselement voor keuzelijst met invoervak in PowerApps
Een besturingselement waarmee gebruikers selecties kunnen maken in geboden opties.  Ondersteunt zoeken en meervoudige selectie.

## <a name="description"></a>Beschrijving
Met een besturingselement voor **keuzelijst met invoervak** kunt u zoeken naar items die u gaat selecteren.  De zoekopdracht wordt aan de serverzijde uitgevoerd op de eigenschap SearchField, zodat de prestaties niet worden beïnvloed door zeer grote gegevensbronnen.  

De modus voor enkelvoudige of meervoudige selectie wordt geconfigureerd via de eigenschap SelectMultiple.

Wanneer u zoekt naar items om te selecteren, kunt u bij elk item ervoor kiezen één gegevenswaarde, twee waarden of een afbeelding en twee waarden (Persoon) weer te geven door de instelling Indeling in het deelvenster Gegevens te wijzigen.

## <a name="people-picker"></a>Personen selecteren
Als u personen wilt selecteren met behulp van een **keuzelijst met invoervak**, kiest u de sjabloon **Persoon** bij de opmaakinstellingen in het deelvenster Gegevens en configureert u de desbetreffende gegevenseigenschappen die voor de onderstaande persoon moeten worden weergegeven.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Items](properties-core.md)**: de gegevensbron waarin selecties kunnen worden gemaakt.

**DefaultItems**: het/de aanvankelijk geselecteerde item(s) voordat de gebruiker het besturingselement gebruikt.

**SelectedItems**: een lijst met geselecteerde items als gevolg van gebruikersinteractie.

**SelectMultiple**: bepaalt of de gebruiker één item of meerdere items kan selecteren.

**IsSearchable**: bepaalt of de gebruiker naar items kan zoeken alvorens ze te selecteren.

**SearchFields**: de gegevensvelden van de betreffende gegevensbron wanneer de gebruiker tekst invoert.  Als u wilt zoeken op meerdere velden, stelt u ComboBox1.SearchFields = ["MyFirstColumn", "MySecondColumn"] in

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Default](properties-core.md)**: de aanvankelijke selectie voordat de gebruiker deze wijzigt in de modus voor enkelvoudige selectie.

**DisplayFields**: Een lijst met velden die worden weergegeven voor elk item dat de zoekopdracht retourneert.  Dit is het gemakkelijkst te configureren via het deelvenster Gegevens op het tabblad Eigenschappen.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**InputTextPlaceholder**: instructietekst die aan eindgebruikers wordt getoond wanneer er geen items zijn geselecteerd.

**OnChange**: hoe de app reageert wanneer de gebruiker een selectie wijzigt.

**OnNavigate**: hoe de app reageert wanneer de gebruiker op een item klikt.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement voor **keuzelijst met invoervak** toe via het menu Besturingselementen op het tabblad Invoegen.  
2. Klik op het tabblad Eigenschappen op Gegevens.  
3. Selecteer de gegevensbron, indeling en verwante eigenschappen daaronder.
4. Stel op het tabblad Geavanceerd de eigenschap **SelectMultiple** in.

    Er verschijnt een functionele **keuzelijst met invoervak** in uw app.

    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **ChevronFill** en **ChevronBackground**
* **ChevronHoverFill** en **ChevronHoverBackground**
* **SelectionColor** en **SelectionFill**
* **SelectionFill** en **[Fill](properties-color-border.md)**
* **SelectionTagColor** en **SelectionTagFill**

Dit komt bovenop de [standaardvereisten voor kleurcontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.

    > [!NOTE]
  > Op aanraakschermen kunnen gebruikers van de schermlezer achtereenvolgens door de inhoud van de keuzelijst met invoervak navigeren. De keuzelijst met invoervak werkt als een knop die, indien geselecteerd, de inhoud weergeeft of verbergt.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.

    > [!NOTE]
  > Met de tab-toets navigeert u naar of van de keuzelijst met invoervak. Met de pijltoetsen navigeert u door de inhoud van de keuzelijst met invoervak. Met de Escape-toets sluit u de vervolgkeuzelijst wanneer deze is geopend.
