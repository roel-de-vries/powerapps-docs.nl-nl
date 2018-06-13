---
title: 'Besturingselement voor microfoon: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Microfoon
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
ms.openlocfilehash: c79e30a404b1e653f1df6547c9fcc818efc79433
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34583504"
---
# <a name="microphone-control-in-powerapps"></a>Besturingselement voor microfoon in PowerApps
Een bedieningselement waarmee app-gebruikers geluiden uit hun apparaat kunnen opnemen.

## <a name="description"></a>Beschrijving
App-gebruikers kunnen audio-opnamen maken als het apparaat waarop de app wordt uitgevoerd, over een microfoon beschikt.

Audio wordt opgeslagen in 3gp-indeling in Android en in AAC-indeling in iOS.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**Mic**: op een apparaat dat meerdere microfoons heeft, is dit de numerieke id van de microfoon die door de app wordt gebruikt.

**OnStop**: hoe de app reageert wanneer de gebruiker een opname stopt met het besturingselement Microfoon.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers. Het doel van de microfoon moet worden beschreven.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Image](properties-visual.md)**: de naam van de afbeelding die wordt weergegeven in een besturingselement voor een afbeelding, audio of microfoon.

**[ImagePosition](properties-visual.md)**: de positie (**Opvullen**, **Passend maken**, **Uitrekken**, **Naast elkaar** of **Centreren**) van een afbeelding in een scherm of een besturingselement als dit niet even groot is als de afbeelding.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**OnStart**: hoe de app reageert wanneer de gebruiker een opname start met het besturingselement Microfoon.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Patch**( *Gegevensbron*, *Basisrecord*, *Wijzigingsrecord* )](../functions/function-patch.md)

## <a name="example"></a>Voorbeeld
### <a name="add-sounds-to-a-custom-gallery-control"></a>Geluiden toevoegen aan een besturingselement Aangepaste galerie
1. Voeg een besturingselement **Microfoon** toe, geef het de naam **MijnMicrofoon** en stel de eigenschap **OnStop** in op deze formule:<br>
   **Collect(MySounds, MyMic.Audio)**

    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?

    Wilt u meer informatie over de functie **[Collect](../functions/function-clear-collect-clearcollect.md)** of [andere functies](../formula-reference.md)?
2. Voeg een besturingselement **Aangepaste galerie** toe, plaats de galerie onder **MijnMicrofoon** en stel de eigenschap **[Items](properties-core.md)** van het besturingselement **Aangepaste galerie** in op **MijnGeluiden**.
3. Voeg in de sjabloon voor het besturingselement **Aangepaste galerie** een besturingselement **[Audio](control-audio-video.md)** toe en stel de eigenschap **Media** hiervan in op **ThisItem.Url**.
4. Druk op F5, klik of tik op **MijnMicrofoon** om te beginnen met opnemen en klik of tik opnieuw te stoppen met opnemen.
5. Klik of tik in het besturingselement **Aangepaste galerie** op de afspeelknop in het besturingselement **[Audio](control-audio-video.md)** om de opname te beluisteren.
6. Voeg zo veel opnames toe als u wilt en ga vervolgens terug naar de standaardwerkruimte door op Esc te drukken.
7. (Optioneel) Voeg in de sjabloon voor het besturingselement **Aangepaste galerie** een besturingselement **[Knop](control-button.md)** toe, stel de eigenschap **[OnSelect](properties-core.md)** van de knop in op **Remove(MijnGeluiden, ThisItem)**, druk op F5 en verwijder vervolgens een opname door op het bijbehorende besturingselement **Knop** te klikken of te tikken.

Gebruik de functie **[SaveData](../functions/function-savedata-loaddata.md)** om de opnames lokaal op te slaan of de functie **[Patch](../functions/function-patch.md)** om een gegevensbron bij te werken.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
Voor de microfoon gelden dezelfde richtlijnen als voor **[knop](control-button.md)** omdat **Microfoon** een gespecialiseerde knop is. Bekijk bovendien de volgende scenario's:

### <a name="audio-alternatives"></a>Alternatieven voor audio
* U kunt een alternatieve invoervorm toevoegen voor gebruikers met een spraakprobleem of gebruikers zonder microfoon. Met **[tekstinvoer](control-text-input.md)** kunnen gebruikers bijvoorbeeld tekst invoeren.

### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **[Afbeelding](properties-visual.md)** en de tekst van knop en het pictogram (indien van toepassing)

Dit komt bovenop de [standaardvereisten voor kleurcontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.
