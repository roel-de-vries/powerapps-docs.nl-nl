---
title: 'Besturingselementen voor audio en video: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over de besturingselementen Audio en Video
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
ms.openlocfilehash: a79ef2ff58667b5a2516056f29845330745e5936
ms.sourcegitcommit: 68eee592c351688e5d0bd458f33a70be507fa53f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2018
---
# <a name="audio-and-video-controls-in-powerapps"></a>Besturingselementen voor audio en video in PowerApps
Een besturingselement voor het afspelen van een geluidsbestand, een videobestand of een video op YouTube.

## <a name="description"></a>Beschrijving
Een besturingselement **Audio** is bedoeld voor het afspelen van een geluidsfragment uit een bestand, een opname van een besturingselement **[Microfoon](control-microphone.md)** of het audiospoor uit een videobestand. Een besturingselement **Video** is bedoeld voor het afspelen van een videoclip uit een bestand of van YouTube als u een URL opgeeft, eventueel met ondertiteling.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**Loop**: bepaalt of een geluidsfragment of een videoclip automatisch opnieuw wordt gestart zodra het afspelen is voltooid.

**Media**: een identificatie voor de clip die met het besturingselement voor audio of video wordt afgespeeld.

**ShowControls**: bepaalt of een audio- of videospeler bijvoorbeeld een knop Afspelen en een volumeregelaar bevat, en of een besturingselement Pen bijvoorbeeld pictogrammen weergeeft voor Tekenen en Wissen.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**AutoPause**: bepaalt of een audio- of videoclip automatisch moet worden onderbroken als de gebruiker naar een ander scherm navigeert.

**AutoStart**: bepaalt of een besturingselement voor audio of video automatisch een clip moet afspelen wanneer de gebruiker naar het scherm navigeert dat dit besturingselement bevat.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**ClosedCaptionsUrl**: dit is alleen een videobesturingselement.  URL van de ondertitelingsbestand in WebVTT-indeling.  De URL’s van de video en de ondertiteling moeten in HTTPS-indeling zijn. Voor de hostserver van zowel de video als de ondertiteling moet CORS zijn ingeschakeld.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[Image](properties-visual.md)**: de naam van de afbeelding die wordt weergegeven in een besturingselement voor een afbeelding, audio of microfoon.

**[ImagePosition](properties-visual.md)**: de positie (**Opvullen**, **Passend maken**, **Uitrekken**, **Naast elkaar** of **Centreren**) van een afbeelding in een scherm of een besturingselement als dit niet even groot is als de afbeelding.

**OnEnd**: hoe een app reageert wanneer het afspelen van een geluidsfragment of een videoclip is voltooid.

**OnPause**: hoe een app reageert wanneer de gebruiker de clip onderbreekt die door het besturingselement voor audio of video wordt afgespeeld.

**OnStart**: hoe de app reageert wanneer de gebruiker een opname start met het besturingselement Microfoon.

**Paused**: *true* als een besturingselement voor het afspelen van media op dat moment is onderbroken, anders *false*.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**Start**: bepaalt of een geluidsfragment of een videoclip wordt afgespeeld.

**StartTime**: de tijd na het begin van een geluidsfragment of videoclip waarop de clip wordt afgespeeld.

**Tijd**: de huidige positie van een besturingselement voor media.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**First**( *Tabelnaam* )](../functions/function-first-last.md)

## <a name="examples"></a>Voorbeelden
### <a name="play-an-audio-or-video-file"></a>Een audio- of videobestand afspelen
1. Klik of tik in het menu **Bestand** op **Media**, klik of tik op **Video's** of **Audio** en klik of tik vervolgens op **Bladeren**.
2. Blader naar het bestand dat u wilt gebruiken, klik of tik erop, en klik of tik vervolgens op **Openen**.
3. Druk op Esc om terug te keren naar de standaardwerkruimte, voeg een besturingselement **Audio** of **Video** toe en stel de eigenschap **Media** van het besturingselement in op het bestand dat u hebt toegevoegd.

    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?
4. Druk op F5 en speel het fragment vervolgens af door op de afspeelknop te klikken of te tikken van het besturingselement dat u hebt toegevoegd.

    > [!TIP]
> De afspeelknop van het besturingselement **Video** wordt weergegeven wanneer u het besturingselement aanwijst.
5. Druk op Esc om terug te gaan naar de standaardwerkruimte.

### <a name="play-a-youtube-video"></a>Een YouTube-video afspelen
1. Voeg een besturingselement **Video** toe en stel de eigenschap **Media** in op de URL van een YouTube-video. Plaats de URL tussen dubbele aanhalingstekens.
2. Druk op F5 en speel het fragment vervolgens af door op de afspeelknop te klikken of te tikken van het besturingselement **Video**.
3. Druk op Esc om terug te gaan naar de standaardwerkruimte.
