---
title: 'Besturingselement voor afbeeldingen: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Afbeelding
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 165633f54697c80258f29267016c18b6178b8008
ms.sourcegitcommit: 0f6d7bb9e524202c065b9a7ef92a7f54bdc4bc7c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/07/2018
ms.locfileid: "39016117"
---
# <a name="image-control-in-powerapps"></a>Besturingselement voor afbeeldingen in PowerApps
Een besturingselement waarin een afbeelding wordt weergeven, bijvoorbeeld uit een lokaal bestand of een gegevensbron.

## <a name="description"></a>Beschrijving
Als u een of meer besturingselementen **Afbeelding** toevoegt aan een app, kunt u afzonderlijke afbeeldingen weergeven die geen deel uitmaken van een gegevensset of u kunt afbeeldingen uit records in gegevensbronnen opnemen.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Image](properties-visual.md)**: de naam van de afbeelding die wordt weergegeven in een besturingselement voor een afbeelding, audio of microfoon.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**ApplyEXIFOrientation**: geeft aan of de richting die is opgegeven in de EXIF-gegevens die in de installatiekopie zijn ingevoegd, automatisch moet worden toegepast.

**AutoDisableOnSelect**: hiermee wordt het besturingselement automatisch uitgeschakeld terwijl het gedrag OnSelect van toepassing is.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**CalculateOriginalDimensions**: hiermee worden de eigenschappen **OriginalHeight** en **OriginalWidth** ingeschakeld.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**FlipHorizontal**: geeft aan of de afbeelding horizontaal moet worden gespiegeld voordat deze wordt weergegeven.

**FlipVertical**: geeft aan of de afbeelding verticaal moet worden gespiegeld voordat deze wordt weergegeven.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[ImagePosition](properties-visual.md)**: de positie (**Opvullen**, **Passend maken**, **Uitrekken**, **Naast elkaar** of **Centreren**) van een afbeelding in een scherm of een besturingselement als dit niet even groot is als de afbeelding.

**ImageRotation**: geeft aan hoe de afbeelding moet worden gedraaid voordat deze wordt weergegeven.  De mogelijke waarden zijn Geen, 90 graden rechtsom, 90 graden linksom en 180 graden rechtsom.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**OriginalHeight**: de oorspronkelijke hoogte van een afbeelding, mogelijk gemaakt met de eigenschap **CalculateOriginalDimensions**.

**OriginalWidth**: de oorspronkelijke breedte van een afbeelding, mogelijk gemaakt met de eigenschap **CalculateOriginalDimensions**.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[RadiusBottomLeft](properties-size-location.md)**: de mate van afronding van de linkerbenedenhoek van een besturingselement.

**[RadiusBottomRight](properties-size-location.md)**: de mate van afronding van de rechterbenedenhoek van een besturingselement.

**[RadiusTopLeft](properties-size-location.md)**: de mate van afronding van de linkerbovenhoek van een besturingselement.

**[RadiusTopRight](properties-size-location.md)**: de mate van afronding van de rechterbovenhoek van een besturingselement.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**Transparency**: de mate waarin besturingselementen achter een afbeelding zichtbaar blijven.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Remove**( *Gegevensbron*, ThisItem )](../functions/function-remove-removeif.md)

## <a name="examples"></a>Voorbeelden
### <a name="show-an-image-from-a-local-file"></a>Een afbeelding uit een lokaal bestand weergeven
1. Klik of tik in het menu **Bestand** op **Media** en klik of tik vervolgens op **Bladeren**.
2. Klik of tik op het afbeeldingsbestand dat u wilt toevoegen, klik of tik op **Openen** en druk vervolgens op Esc om terug te keren naar de standaardwerkruimte.
3. Voeg een besturingselement**Afbeelding** toe en stel de eigenschap **Afbeelding** van het element in op de naam van het bestand dat u hebt toegevoegd.

    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?

    U ziet de opgegeven afbeelding in het besturingselement **Afbeelding**.

### <a name="show-a-set-of-images-from-a-data-source"></a>Een reeks afbeeldingen uit een gegevensbron weergeven
1. Download dit [Excel-bestand](https://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx) en sla het op een lokaal apparaat op.
2. In PowerApps Studio maakt of opent u een app en klikt of tikt u op **Een gegevensbron toevoegen** in het rechterdeelvenster.

    Als **Een gegevensbron toevoegen** niet wordt weergegeven in het rechterdeelvenster, klikt of tikt u op een scherm in de linkernavigatiebalk.
3. Klik of tik op **Statische gegevens toevoegen aan uw app**, klik of tik op het Excel-bestand dat u hebt gedownload en klik of tik vervolgens op **Openen**.
4. Schakel het selectievakje **FlooringEstimates** in, en klik of tik op **Verbinding maken**.
5. Voeg een besturingselement **Galerie** met afbeeldingen toe en stel de eigenschap **[Items](properties-core.md)** van de galerie in op **FlooringEstimates**.

    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?

    In het besturingselement **Galerie** ziet u afbeeldingen van tapijt, parket en vloertegels op basis van koppelingen in het Excel-bestand dat u hebt gedownload.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
* [Standaardvereisten voor kleurcontrast](../accessible-apps-color.md) zijn van toepassing, indien de afbeelding wordt gebruikt als een knop.
* U kunt controleren op problemen met het contrast in de afbeelding als deze niet alleen voor de sier is.

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn als de afbeelding wordt gebruikt als een knop of als de afbeelding niet alleen voor de sier is.
* **[AccessibleLabel](properties-accessibility.md)** moet leeg zijn of de lege tekenreeks **""** bevatten als de afbeelding alleen voor de sier is. Hierdoor wordt de afbeelding genegeerd door de schermlezer.
* **[AccessibleLabel](properties-accessibility.md)** kan leeg zijn of de lege tekenreeks **""** bevatten als de afbeelding redundante informatie bevat.
  * Bijvoorbeeld: een **Afbeelding** van tandwielen waarvoor **[AccessibleLabel](properties-accessibility.md)** is ingesteld op **Instellingen**. Deze afbeelding wordt niet gebruikt als een knop. Het staat naast een **[label](control-text-box.md)** dat ook **Instellingen** heet. De afbeelding wordt door schermlezers gelezen als **Instellingen** en het label ook als **Instellingen**. Dit is onnodig. In dit geval heeft de **Afbeelding** geen **[AccessibleLabel](properties-accessibility.md)** nodig.

    > [!IMPORTANT]
    > Schermlezers lezen altijd **Afbeelding**en die een **[TabIndex](properties-accessibility.md)** van nul of hoger hebben, zelfs als **[AccessibleLabel](properties-accessibility.md)** leeg is. Dit komt omdat deze als knoppen worden weergegeven. Als er geen **[AccessibleLabel](properties-accessibility.md)** is opgegeven, lezen schermlezers de afbeelding als een **knop**.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn als de afbeelding wordt gebruikt als een knop. Hierdoor kunnen toetsenbordgebruikers naar de afbeelding navigeren.
* Focusindicatoren moet duidelijk zichtbaar zijn als de afbeelding wordt gebruikt als een knop. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.

    > [!NOTE]
  > Wanneer **[TabIndex](properties-accessibility.md)** nul of groter is, wordt de **Afbeelding** weergegeven als een knop. Het uiterlijk van de afbeelding verandert niet, maar de afbeelding wordt door schermlezers juist geïdentificeerd als een knop. Wanneer **[TabIndex](properties-accessibility.md)** kleiner is dan nul, wordt de **Afbeelding** geïdentificeerd als een afbeelding.
