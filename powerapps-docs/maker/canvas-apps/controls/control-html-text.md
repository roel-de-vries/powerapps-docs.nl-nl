---
title: 'Besturingselement voor HTML-tekst: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement HTML-tekst
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
ms.openlocfilehash: d41ef04d3cd070373f6772bdfced029a7d09e244
ms.sourcegitcommit: ebd39753e2a0b60c1d8c016e38c00dd1accf5d0c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2018
ms.locfileid: "49307856"
---
# <a name="html-text-control-in-powerapps"></a>Besturingselement voor HTML-tekst in PowerApps
Een vak waarin tekst wordt weergegeven en HTML-codes worden geconverteerd naar opmaak.

## <a name="description"></a>Beschrijving
Een besturingselement **HTML-tekst** bevat niet alleen gewone tekst en getallen, maar converteert ook HTML-codes, zoals vaste spaties.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**HtmlText**: tekst die wordt weergegeven in een besturingselement voor HTML-tekst en die HTML-codes kan bevatten.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Find**( *Zoektekst*, *Zoekreeks* )](../functions/function-find.md)

## <a name="example"></a>Voorbeeld
1. Voeg een **[Label](control-text-box.md)**-besturingselement met de naam **Bron** toe en stel de eigenschap **[Text](properties-core.md)** in op deze tekenreeks:

\<p> We hebben\&nbsp;een \&quot;letterlijke en figuurlijke\&quot; inhaalslag gemaakt.\<>p

Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?

1. Voeg een besturingselement **HTML-tekst** toe en stel de eigenschap **HtmlText** in op deze waarde:<br>
   **Source.Text**
   
     Het besturingselement **HTML-tekst** bevat dezelfde tekst als het besturingselement **[Label](control-text-box.md)**, maar de codes zijn geconverteerd naar de juiste tekens.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
Het besturingselement **HTML-tekst** moet niet interactief zijn. Het mag alleen worden gebruikt om tekst weer te geven.

### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **[Color](properties-color-border.md)** en **[Fill](properties-color-border.md)**
* Tekst met aangepaste kleuren en de achtergrond

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **HtmlText** moet aanwezig zijn.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **HtmlText** mag geen interactieve elementen bevatten als `<button>`, `<a>` of `<input>`. Het **[TabIndex](properties-accessibility.md)**-systeem in PowerApps houdt geen rekening met elementen in **HtmlText**.
