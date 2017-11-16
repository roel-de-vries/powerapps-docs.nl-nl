---
title: 'Besturingselement voor toevoegen van afbeeldingen: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Afbeelding toevoegen
services: 
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 6a7c60755f5623803d20bec4ec9881108b1116c6
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="add-picture-control-in-powerapps"></a>Besturingselement voor toevoegen van afbeeldingen in PowerApps
Hiermee wordt een foto gemaakt of worden afbeeldingen geladen van het lokale apparaat.

## <a name="description"></a>Beschrijving
Met dit besturingselement kunnen gebruikers foto's maken of afbeeldingsbestanden uploaden van hun apparaat en de gegevensbron met deze inhoud bijwerken. Op een mobiel apparaat kan de gebruiker in een dialoogvenster kiezen tussen het maken van een foto of het selecteren van een beschikbare foto.

Dit besturingselement is een samengesteld besturingselement, dat bestaat uit twee besturingselementen.  Klik of tik eenmaal om het buitenste besturingselement te selecteren met daarin de afbeelding die is geladen.  Klik of tik nogmaals om het binnenste besturingselement voor een label te selecteren.

## <a name="outer-control-properties"></a>Eigenschappen van buitenste besturingselement
Deze eigenschappen zijn van toepassing op het buitenste besturingselement.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**Error**: als er een probleem is opgetreden bij het uploaden van een afbeelding, bevat deze eigenschap een relevant foutbericht.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**Media**: een identificatie voor de clip die met het besturingselement voor audio of video wordt afgespeeld.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="inner-text-properties"></a>Eigenschappen van binnenste besturingselement
Deze eigenschappen zijn van toepassing op het binnenste besturingselement voor een label, met daarin standaard de tekst 'Tik of klik om een afbeelding toe te voegen'.  Als u dit binnenste besturingselement wilt selecteren, klikt of tikt u eenmaal op het besturingselement **Afbeelding toevoegen** en daarna nog een keer.

**[Align](properties-text.md)**: de locatie van tekst in verhouding tot het horizontale midden van het besturingselement.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**[Padding](properties-size-location.md)**: de afstand tussen de tekst op een knop voor importeren of exporteren en de randen van die knop.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[Text](properties-core.md)**: de tekst die wordt weergegeven in een besturingselement of die de gebruiker in een besturingselement typt.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[VerticalAlign](properties-text.md)**: de locatie van de tekst in een besturingselement in verhouding tot het verticale midden van dat besturingselement.

## <a name="related-functions"></a>Verwante functies
[**Patch**( *Gegevensbron*, *Basisrecord*, *Wijzigingsrecord* )](../functions/function-patch.md)

## <a name="example"></a>Voorbeeld
### <a name="add-images-to-an-image-gallery-control"></a>Afbeeldingen toevoegen aan een besturingselement Afbeeldingengalerie
1. Voeg een besturingselement **Afbeelding toevoegen** toe en klik of tik er vervolgens driemaal op.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Klik of tik in het dialoogvenster **Openen** op een afbeeldingsbestand en klik of tik vervolgens op **Openen**.
3. Voeg een besturingselement **[Knop](control-button.md)** toe, plaats deze onder het besturingselement **Afbeelding toevoegen** en stel vervolgens de eigenschap **[OnSelect](properties-core.md)** van het besturingselement **[Knop](control-button.md)** in op deze formule:<br>
   **Collect(MijnAfbeeldingen, AddMediaButton1.Media)**
   
    Wilt u meer informatie over de functie **[Collect](../functions/function-clear-collect-clearcollect.md)** of [andere functies](../formula-reference.md)?
4. Voeg een besturingselement **Afbeeldingengalerie** toe en stel de eigenschap **[Items](properties-core.md)** van de galerie in op **MijnAfbeeldingen**.
5. Druk op F5 en klik of tik op het besturingselement **[Knop](control-button.md)**.
   
    De afbeelding uit het besturingselement **Afbeelding toevoegen** wordt weergegeven in het besturingselement **Afbeeldingengalerie**. Als de afbeelding een andere hoogte-breedteverhouding heeft dan het besturingselement **[Afbeelding](control-image.md)** in het besturingselement **Afbeeldingengalerie**, stelt u de eigenschap **[ImagePosition](properties-visual.md)** van het besturingselement **[Afbeelding](control-image.md)** in op **Passend**.
6. Klik of tik op het besturingselement **Afbeelding toevoegen**, klik of tik op een ander afbeeldingsbestand, klik of tik op **Openen** en klik of tik op het besturingselement **[Knop](control-button.md)** dat u hebt toegevoegd.
   
    De tweede afbeelding wordt weergegeven in het besturingselement **Afbeeldingengalerie**.
7. (Optioneel) Herhaal de vorige stap een of meer keren, en ga vervolgens terug naar de standaardwerkruimte door op Esc te drukken.

Gebruik de functie **[SaveData](../functions/function-savedata-loaddata.md)** om de afbeeldingen lokaal op te slaan of de functie **[Patch](../functions/function-patch.md)** om een gegevensbron bij te werken.

