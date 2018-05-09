---
title: 'Besturingselement voor peninvoer: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Peninvoer
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 84981a00a516f553d3f1b318f12a6f68064c66b2
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="pen-input-control-in-powerapps"></a>Besturingselement voor peninvoer in PowerApps
Een besturingselement waarin de gebruiker kan tekenen, wissen en gebieden van een afbeelding kan markeren.

## <a name="description"></a>Beschrijving
De gebruiker kan dit besturingselement gebruiken als een whiteboard, en om grafieken te tekenen en woorden te schrijven die naar getypte tekst kunnen worden geconverteerd.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Kleur](properties-color-border.md)**: de kleur van de invoerlijnen.

**Modus**: het besturingselement heeft de modus **Tekenen** of **Wissen**.  De modus Selecteren is afgeschaft.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers. Kan worden gebruikt om het doel van het besturingselement en alternatieve methoden voor invoer te beschrijven.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**Input**: invoer.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[SelectionColor](properties-color-border.md)**: de tekstkleur van geselecteerde items in een lijst of de kleur van het selectiehulpmiddel in een besturingselement Pen.

**SelectionThickness**: de dikte van het selectiehulpmiddel voor een besturingselement voor peninvoer.

**ShowControls**: bepaalt of een audio- of videospeler bijvoorbeeld een knop Afspelen en een volumeregelaar bevat, en of een besturingselement Pen bijvoorbeeld pictogrammen weergeeft voor Tekenen en Wissen.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Collect**( *NaamVerzameling*, *TeVerzamelenGegevens* )](../functions/function-clear-collect-clearcollect.md)

## <a name="example"></a>Voorbeeld
### <a name="create-a-set-of-images"></a>Een reeks afbeeldingen maken
1. Voeg een besturingselement **Peninvoer** toe, geef het de naam **MijnKrabbels** en stel de eigenschap **ShowControls** in op **true**.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Voeg een besturingselement **[Knop](control-button.md)** toe, plaats de knop onder **MijnKrabbels** en stel de eigenschap **[Text](properties-core.md)** van het besturingselement **[Knop](control-button.md)** in op **Toevoegen**.
3. Stel de eigenschap **[OnSelect](properties-core.md)** van het besturingselement **[Knop](control-button.md)** in op deze formule:<br>
   **Collect(Doodles, {Sketch:MyDoodles.Image})**
4. Voeg een besturingselement **Afbeeldingengalerie** toe, plaats de galerie onder het besturingselement **[Knop](control-button.md)** maak het besturingselement **Afbeeldingengalerie** zo smal totdat er drie items worden weergegeven.
5. Stel de eigenschap **[Items](properties-core.md)** van het besturingselement **Afbeeldingengalerie** in op **Doodles** en druk op F5.
6. Teken een afbeelding in **MijnKrabbels** en klik of tik op het besturingselement **[Knop](control-button.md)**.
   
    De tekening die u hebt gemaakt, wordt weergegeven in het besturingselement **Afbeeldingengalerie**.
7. (Optioneel) Klik of tik in het besturingselement **Peninvoer** op het pictogram om de tekening te verwijderen die u hebt getekend, maak een andere tekening, en klik of tik vervolgens op het besturingselement **[Knop](control-button.md)**.
8. Stel in het besturingselement **Afbeeldingenggalerie** de eigenschap **[OnSelect](properties-core.md)** van het besturingselement **[Image](control-image.md)** in op deze formule:<br>
   **Remove(Doodles, ThisItem)**
9. Verwijder een tekening door erop te klikken of tikken in het besturingselement **Afbeeldingengalerie**.

Gebruik de functie **[SaveData](../functions/function-savedata-loaddata.md)** om de tekeningen lokaal op te slaan of de functie **[Patch](../functions/function-patch.md)** om ze in een gegevensbron op te slaan.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **[BorderColor](properties-color-border.md)** en de kleur buiten het besturingselement (als er een rand is)
* **[Fill](properties-color-border.md)** en de kleur buiten het besturingselement (als er geen rand is)

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.

    > [!IMPORTANT]
> **Peninvoer** is niet toegankelijk voor gebruikers van schermlezers. Geef altijd een alternatieve vorm van invoer. Als bijvoorbeeld een schets vereist is, kunt u een besturingselement toevoegen voor **[Afbeelding toevoegen](control-add-picture.md)** waarmee gebruikers een afbeelding kunnen uploaden. Beide methoden kunnen worden aangeboden en de gebruiker kan de optie kiezen waarmee hij het meest vertrouwd is.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord

> [!IMPORTANT]
> **Peninvoer** is niet toegankelijk voor toetsenbordgebruikers. Geef altijd een alternatieve vorm van invoer. Als bijvoorbeeld een handtekening vereist is, kunt u een **[Tekstinvoer](control-text-input.md)** toevoegen waarmee gebruikers hun naam kunnen invoeren. Beide methoden kunnen worden aangeboden en de gebruiker kan de optie kiezen waarmee hij het meest vertrouwd is.
