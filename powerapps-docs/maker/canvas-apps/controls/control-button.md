---
title: 'Besturingselement voor knop: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Knop
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: aec9071cf5cc7cbe451bae32dedc2ba119e21189
ms.sourcegitcommit: 4710a56d308efe67fe60a7688143e61f5e5f2b44
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="button-control-in-powerapps"></a>Besturingselement voor knop in PowerApps
Een besturingselement waarop de gebruiker kan klikken of tikken om interactie te hebben met de app.

## <a name="description"></a>Beschrijving
Configureer de eigenschap **[OnSelect](properties-core.md)** van een besturingselement **Knop** voor het uitvoeren van een of meer formules wanneer de gebruiker op het besturingselement klikt of tikt.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[Text](properties-core.md)**: de tekst die wordt weergegeven in een besturingselement of die de gebruiker in een besturingselement typt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[Align](properties-text.md)**: de locatie van tekst in verhouding tot het horizontale midden van het besturingselement.

**AutoDisableOnSelect**: hiermee wordt het besturingselement automatisch uitgeschakeld terwijl het gedrag **OnSelect** van toepassing is.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**Pressed**: *true* zolang een besturingselement is ingedrukt, anders *false*.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[RadiusBottomLeft](properties-size-location.md)**: de mate van afronding van de linkerbenedenhoek van een besturingselement.

**[RadiusBottomRight](properties-size-location.md)**: de mate van afronding van de rechterbenedenhoek van een besturingselement.

**[RadiusTopLeft](properties-size-location.md)**: de mate van afronding van de linkerbovenhoek van een besturingselement.

**[RadiusTopRight](properties-size-location.md)**: de mate van afronding van de rechterbovenhoek van een besturingselement.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[VerticalAlign](properties-text.md)**: de locatie van de tekst in een besturingselement in verhouding tot het verticale midden van dat besturingselement.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
**[Navigate( *Schermnaam*, *Schermovergang* )](../functions/function-navigate.md)**

## <a name="examples"></a>Voorbeelden
### <a name="add-a-basic-formula-to-a-button"></a>Een eenvoudige formule toevoegen aan een knop
1. Voeg een besturingselement **[Tekstinvoer](control-text-input.md)** toe en geef het de naam **Bron**.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Voeg een besturingselement **Knop** toe en stel de eigenschap **[Text](properties-core.md)** van de knop in op 'Toevoegen' en de eigenschap **[OnSelect](properties-core.md)** op deze formule:<br>
   **UpdateContext({Total:Total + Value(Source.Text)})**
   
    Wilt u meer informatie over de functie **[UpdateContext](../functions/function-updatecontext.md)** of een [andere functie](../formula-reference.md)?
3. Voeg een besturingselement **[Label](control-text-box.md)** toe, stel de eigenschap **[Text](properties-core.md)** in op **Totaal** en druk vervolgens op **F5**.
4. Verwijder de standaardtekst uit **Bron**, typ een getal in en klik of tik op **Toevoegen**.
   
    Het besturingselement **[Label](control-text-box.md)** bevat het getal dat u hebt opgegeven.
5. Verwijder het standaardnummer uit **Bron**, typ een nieuw getal in en klik of tik op **Toevoegen**.
   
    Het besturingselement **[Label](control-text-box.md)** bevat het totaal van de twee getallen die u hebt ingevoerd.
6. (optioneel) Herhaal de vorige stap een of meer keer.
7. Als u wilt terugkeren naar de standaardwerkruimte, drukt u op Esc (of klikt of tikt u op het sluitpictogram in de rechterbovenhoek).

### <a name="configure-a-button-with-multiple-formulas"></a>Een knop met meerdere formules configureren
Voeg een formule toe die het besturingselement **Tekstinvoer** tussen vermeldingen wist.

1. Stel de eigenschap **[HintText](control-text-input.md)** van **Bron** in op 'Een waarde invoeren'.
2. Stel de eigenschap **[OnSelect](properties-core.md)** van **Toevoegen** in op deze formule:
   
    **UpdateContext({Total:Total + Value(Source.Text)});<br>UpdateContext({ClearInput: ""})**
   
    > [!NOTE]
> Scheid meerdere formules met puntkomma's '**;**'.
3. Stel de eigenschap **[Default](properties-core.md)** van **Bron** in op **ClearInput**.
4. Druk op **F5** en test de app vervolgens door verschillende cijfers tegelijkertijd toe te voegen.

### <a name="add-another-button-to-reset-the-total"></a>Een andere knop toevoegen om het totaal opnieuw in te stellen
Voeg een tweede knop toe om het totaal tussen de berekeningen te wissen.

1. Voeg nog een besturingselement **Knop** toe, stel de eigenschap **[Text](properties-core.md)** in op 'Wissen' en stel de bijbehorende eigenschap **[OnSelect](properties-core.md)** in op deze formule:
   
    **UpdateContext({Total:0})**
2. Druk op **F5**, voeg verschillende nummers tegelijkertijd toe en klik of tik op **Wissen** om het totaal te wissen.

### <a name="change-a-buttons-appearance"></a>De weergave van een knop wijzigen
#### <a name="change-a-buttons-shape"></a>De vorm van een knop wijzigen
Het besturingselement **Knop** is in PowerApps standaard rechthoekig met afgeronde hoeken. U kunt eenvoudige wijzigingen aanbrengen aan de vorm van het besturingselement **Knop** door de eigenschappen **[Height](properties-size-location.md)**, **[Width](properties-size-location.md)** en **[Radius](properties-size-location.md)** in te stellen.

> [!NOTE]
> [Pictogrammen en vormen](control-shapes-icons.md) bieden een groot aantal verschillende ontwerpen en kunnen een aantal basisfuncties van het besturingselement **Knop** uitvoeren. **[Pictogrammen en vormen](control-shapes-icons.md)** hebben de eigenschap **[Text](properties-core.md)** echter niet.

1. Voeg het besturingselement **Knop** toe en stel de eigenschappen **[Height](properties-size-location.md)** en **[Width](properties-size-location.md)** in op **300** om een grote vierkante knop te maken.
2. Wijzig de eigenschappen **[RadiusTopLeft](properties-size-location.md)**, **[RadiusTopRight](properties-size-location.md)**, **[RadiusBottomLeft](properties-size-location.md)** en **[RadiusBottomRight](properties-size-location.md)** om de ronding van elke hoek aan te passen. Hier volgen enkele voorbeelden van verschillende vormen, die allemaal beginnen als een vierkante knop van 300 x 300:
   
   * Stel de vier waarden van **[Radius](properties-size-location.md)** in op **150** om een cirkel te maken.
   * Stel de waarden voor **[RadiusTopLeft](properties-size-location.md)** en **[RadiusBottomRight](properties-size-location.md)** in op **300** om een **Knop** in de vorm van een blad te maken.
   * Stel de waarden voor **[RadiusTopLeft](properties-size-location.md)** en **[RadiusTopRight](properties-size-location.md)** in op **300** en de waarden voor **[RadiusBottomLeft](properties-size-location.md)** en **[RadiusBottomRight](properties-size-location.md)** in op **100** om een knop in de vorm van een tabblad te maken.

#### <a name="change-a-buttons-color-when-you-hover-over-it"></a>De kleur van de knop wijzigen wanneer u de muisaanwijzer erop houdt
Standaard wordt de opvulkleur van het besturingselement **Knop** met 20% gedimd wanneer u de muisaanwijzer erop houdt. U kunt dit gedrag aanpassen door de eigenschap **[HoverFill](properties-color-border.md)** te wijzigen. Deze maakt gebruik van de functie **[ColorFade](../functions/function-colors.md)**. Als u de formule voor de **[ColorFade](../functions/function-colors.md)** instelt op een positief percentage, wordt de kleur lichter wanneer u de muisaanwijzer op de knop houdt. Een negatief percentage zorgt ervoor dat de kleur donker wordt.

* Wijzig het percentage van **[ColorFade](../functions/function-colors.md)** in de eigenschap **[HoverFill](properties-color-border.md)** van een van de knoppen die u hebt gemaakt en bekijk wat het effect is.

U kunt ook de kleur van een besturingselement **Knop** opgeven door de eigenschap **[HoverFill](properties-color-border.md)** in te stellen in een formule met de functie **[ColorValue](../functions/function-colors.md)** in plaats van de functie **[ColorFade](../functions/function-colors.md)**, bijvoorbeeld **ColorValue("Red")**.

> [!NOTE]
> De kleurwaarde moet een CSS-kleurdefinitie zijn. Dit kan een naam of hexadecimale waarde zijn.

* Vervang de functie **[ColorFade](../functions/function-colors.md)** door de functie **[ColorValue](../functions/function-colors.md)** in een van de knoppen die u hebt gemaakt en bekijk wat het effect is.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
* De standaardvereisten voor kleurcontrast zijn van toepassing.

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[Text](properties-core.md)** moet aanwezig zijn.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
 