---
title: 'Besturingselement voor vervolgkeuzelijst: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Vervolgkeuzelijst
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5fc53e4bfc302819a7899395af4f8f269d6754ef
ms.sourcegitcommit: 5db6e3ac3a622de313a1102417397e126c3f92f2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2018
ms.locfileid: "45640372"
---
# <a name="drop-down-control-in-powerapps"></a>Besturingselement voor vervolgkeuzelijst in PowerApps
Een lijst waarin alleen het eerste item wordt weergegeven, tenzij de gebruiker de lijst opent.

## <a name="description"></a>Beschrijving
Een besturingselement **Vervolgkeuzelijst** bespaart schermruimte, zeker als de lijst een groot aantal opties bevat. Het besturingselement neemt slechts één regel in beslag, tenzij de gebruiker de pijl-omlaag selecteert om andere opties weer te geven.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Standaard](properties-core.md)**: de beginwaarde van een besturingselement voordat de gebruiker een andere waarde opgeeft.

**[Items](properties-core.md)** : de gegevensbron met de items die worden weergegeven in het besturingselement. Als de bron meerdere kolommen heeft, stelt u de eigenschap **Waarde** van het besturingselement in op de kolom met gegevens die u wilt weergeven.
  
**Waarde** : de kolom met gegevens die u wilt weergeven in het besturingselement (bijvoorbeeld als een gegevensbron meerdere kolommen heeft).

**Selected**: het geselecteerde item.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**ChevronBackground**: de kleur achter de pijl-omlaag in een vervolgkeuzelijst.

**ChevronFill**: de kleur van de pijl-omlaag in een vervolgkeuzelijst.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**[SelectionColor](properties-color-border.md)**: de tekstkleur van geselecteerde items in een lijst of de kleur van het selectiehulpmiddel in een besturingselement Pen.

**[SelectionFill](properties-color-border.md)**: de achtergrondkleur van geselecteerde items in een lijst of een geselecteerd gebied van een besturingselement Pen.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="example"></a>Voorbeeld

### <a name="simple-list"></a>Eenvoudige lijst

1. Voeg een besturingselement **Vervolgkeuzelijst** toe, stel de eigenschap **[Items](properties-core.md)** van het besturingselement daarna in op deze expressie:

    ```["Seattle", "Tokyo", "London", "Johannesburg", "Rio de Janeiro"]```

    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?

1. Geef de items in de lijst weer door de pijl-omlaag van het besturingselement te selecteren terwijl u op de Alt-toets drukt.

### <a name="list-from-a-data-source"></a>Lijst van een gegevensbron
De principes in deze procedure zijn van toepassing op [gegevensbronnen die tabellen opleveren](../connections-list.md#tables), maar als u deze stappen exact wilt volgen, opent u een omgeving waarvoor een Common Data Service for Apps-database is gemaakt en de voorbeeldgegevens zijn toegevoegd.

1. [Open een lege app](../data-platform-create-app-scratch.md#open-a-blank-app) en [geef vervolgens de entiteit **Accounts** op](../data-platform-create-app-scratch.md#specify-an-entity).

1. Voeg een besturingselement **Vervolgkeuzelijst** toe en stel de eigenschap **[Items](properties-core.md)** van het besturingselement in op deze formule:

    ```Distinct(Accounts, address1_city)```

    Deze formule toont alle plaatsen in de entiteit **Accounts**. Als meer dan één record dezelfde plaats bevat, wordt door de functie **[Distinct](../functions/function-distinct.md)** de duplicatie in de vervolgkeuzelijst verborgen.

1. (optioneel) Wijzig de naam van het besturingselement **Vervolgkeuzelijst** in **Plaatsen**, voeg een verticaal besturingselement **Galerie** toe en stel de eigenschap **[Items](properties-core.md)** van de galerie in op deze formule:

    ```Filter(Accounts, address1_city = Cities.Selected.Value)```

    Deze **[Filter](../functions/function-filter-lookup.md)**-functie toont alleen die records in de entiteit **Accounts** waarvoor de plaats overeenkomt met de geselecteerde waarde in het besturingselement **Plaatsen**.

## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **ChevronFill** en **ChevronBackground**
* **ChevronHoverFill** en **ChevronHoverBackground**
* **SelectionColor** en **SelectionFill**
* **SelectionFill** en **[Fill](properties-color-border.md)**

Dit komt bovenop de [standaardvereisten voor kleurcontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
