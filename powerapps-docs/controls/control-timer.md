---
title: 'Besturingselement voor timer: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Timer
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
ms.openlocfilehash: c84eec1bdd541429d4524640d9e1ffa649b895fd
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="timer-control-in-powerapps"></a>Besturingselement voor timer in PowerApps
Een besturingselement dat kan bepalen hoe uw app reageert nadat een bepaalde hoeveelheid tijd is verstreken.

## <a name="description"></a>Beschrijving
Timers kunnen bijvoorbeeld bepalen hoelang een besturingselement wordt weergegeven, maar kunnen ook worden gebruikt om andere eigenschappen van een besturingselement te wijzigen nadat een bepaalde hoeveelheid tijd is verstreken.

U moet een voorbeeld van de app bekijken om Timer in de ontwerpomgeving te kunnen uitvoeren.  Zo kunt u de timer zonder enige tijdsbeperkingen in de ontwerpomgeving configureren.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**Duration**: hoe lang een timer loopt.

**OnTimerEnd**: hoe een app reageert wanneer een timer is afgelopen.

**Repeat**: bepaalt of een timer automatisch opnieuw wordt gestart als deze is afgelopen.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[Align](properties-text.md)**: de locatie van tekst in verhouding tot het horizontale midden van het besturingselement.

**AutoPause**: bepaalt of een audio- of videoclip automatisch moet worden onderbroken als de gebruiker naar een ander scherm navigeert.

**AutoStart**: bepaalt of een besturingselement voor audio of video automatisch een clip moet afspelen wanneer de gebruiker naar het scherm navigeert dat dit besturingselement bevat.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**OnTimerStart**: hoe een app reageert wanneer een timer begint te lopen.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**Start**: bepaalt of een geluidsfragment of een videoclip wordt afgespeeld.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[Text](properties-core.md)**: de tekst die wordt weergegeven in een besturingselement of die de gebruiker in een besturingselement typt.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Refresh**( *Gegevensbron* )](../functions/function-refresh.md)

## <a name="examples"></a>Voorbeelden
### <a name="show-a-countdown"></a>Een aftelling weergeven
1. Voeg een timer toe en geef deze de naam **Aftelling**.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Stel de eigenschap **Duration** van de timer in op **10000** en de eigenschappen **Repeat** en **AutoStart** op **true**.
3. (Optioneel) Maak de timer gemakkelijker af te lezen door de eigenschap **[Height](properties-size-location.md)** in te stellen op **160**, eigenschap de **[Width](properties-size-location.md)** op **600** en de eigenschap **[Size](properties-text.md)** op **60**.
4. Voeg een label toe en stel de eigenschap **[Text](properties-core.md)** in op deze formule:
   <br>**"Aantal resterende seconden: " & RoundUp(10-Countdown.Value/1000, 0)**
   
    Wilt u meer informatie over de functie **[RoundUp](../functions/function-round.md)** of [andere functies](../formula-reference.md)?
   
    In het label wordt het aantal seconden weergegeven voordat de timer opnieuw wordt gestart.
5. (Optioneel) Stel de eigenschap **[Visible](properties-core.md)** van de timer in op **false**.

### <a name="animate-a-control"></a>Een besturingselement van animatie voorzien
1. Voeg een timer toe en geef deze de naam **Infaden**.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Stel de eigenschap **Duration** van de timer in op **5000** en de eigenschappen **Repeat** en **AutoStart** op **true**.
3. (Optioneel) Maak de timer gemakkelijker af te lezen door de eigenschap **[Height](properties-size-location.md)** in te stellen op **160**, eigenschap de **[Width](properties-size-location.md)** op **600** en de eigenschap **[Size](properties-text.md)** op **60**.
4. Voeg een tekstvak toe en stel de eigenschap **[Label](properties-core.md)** ervan in op **Welkom!** en stel de eigenschap **[Color](properties-color-border.md)** in op deze formule:
   <br>**ColorFade(Color.BlueViolet, Infaden.Value/5000)**
   
    Wilt u meer informatie over de functie **[ColorFade](../functions/function-colors.md)** of [andere functies](../formula-reference.md)?
   
    De tekst in het label vervaagt naar wit, wordt weer met de volledige intensiteit weergegeven, waarna het proces wordt herhaald.
5. (Optioneel) Stel de eigenschap **[Visible](properties-core.md)** van de timer in op **false**.

