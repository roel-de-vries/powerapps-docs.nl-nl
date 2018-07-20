---
title: Kerneigenschappen | Microsoft Docs
description: Naslaginformatie over de eigenschappen Disabled, Visible en ReadOnly
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: 98a8e22e4101c1c151fa197e967d21942041bef4
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015151"
---
# <a name="core-properties-in-powerapps"></a>Kerneigenschappen in PowerApps
Configureer of de gebruiker een besturingselement kan zien er hier invloed op heeft.

### <a name="properties"></a>Eigenschappen
**Default**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

* Is van toepassing op de besturingselementen **[Kaart](control-card.md)**, **[Selectievakje](control-check-box.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Galerie](control-gallery.md)**, **[Keuzelijst](control-list-box.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)** en **[Wisselknop](control-toggle.md)**.

**DelayOutput**: ingesteld op true om actie tijdens tekstinvoer te vertragen.

* Is van toepassing op de besturingselementen **[Tekstinvoer](control-text-input.md)**, **[Kaart](control-card.md)**

**DisplayMode**: mogelijke waarden zijn **Bewerken, Weergeven** of **Uitgeschakeld**. Configureert of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).  In de modus **Weergeven**worden alleen de tekstwaarden van invoerbesturingselementen zoals **[Tekstinvoer](control-text-input.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Datumkiezer](control-date-picker.md)** weergegeven en worden niet alle interactieve elementen of versieringen weergegeven.  Hierdoor zijn ze geschikt om te worden weergegeven in Formulieren of als leesbare uitvoer.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Audio](control-audio-video.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Exporteren](control-export-import.md)**, **[Galerie](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Pictogram](control-shapes-icons.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)** , **[Cirkeldiagram](control-pie-chart.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Vorm](control-shapes-icons.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

**Items**: de gegevensbron die wordt weergegeven in een besturingselement zoals een galerie, een lijst of een grafiek.

* Is van toepassing op de besturingselementen **[Kolomdiagram](control-column-line-chart.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Galerie](control-gallery.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Cirkeldiagram](control-pie-chart.md)** en **[Keuzerondje](control-radio.md)**.

**OnChange**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Keuzelijst](control-list-box.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)** en **[Wisselknop](control-toggle.md)**.

**OnSelect**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Exporteren](control-export-import.md)**, **[HTML-tekst](control-html-text.md)**, **[Pictogram](control-shapes-icons.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)**, **[Cirkeldiagram](control-pie-chart.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Vorm](control-shapes-icons.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstvak](control-text-input.md)**, **[Timer](control-timer.md)** en **[Wisselknop](control-toggle.md)**.

**Reset**: of een besturingselement wordt teruggezet op de standaardwaarde.  Zie ook de functie **[Opnieuw instellen](../functions/function-reset.md)**.

* Is van toepassing op de besturingselementen **[Audio](control-audio-video.md)**, **[Selectievakje](control-check-box.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

**Text**: de tekst die wordt weergegeven in een besturingselement of die de gebruiker in een besturingselement typt.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Exporteren](control-export-import.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Tekstinvoer](control-text-input.md)** en **[Timer](control-timer.md)**.

**Tooltip**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

* Is van toepassing op de besturingselementen **[Audio](control-audio-video.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Selectievakje](control-check-box.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[HTML-tekst](control-html-text.md)**, **[Afbeelding](control-image.md)**, **[Label](control-text-box.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

**Value**: de waarde van een besturingselement voor invoer.

* Is van toepassing op de besturingselementen **[Selectievakje](control-check-box.md)**, **[Keuzerondje](control-radio.md)**, **[Schuifregelaar](control-slider.md)** en **[Wisselknop](control-toggle.md)**.

**Visible**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Audio](control-audio-video.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Kaart](control-card.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Weergaveformulier](control-form-detail.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Bewerkingsformulier](control-form-detail.md)**, **[Exporteren](control-export-import.md)**, **[Galerie](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Pictogram](control-shapes-icons.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)**, **[Cirkeldiagram](control-pie-chart.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Vorm](control-shapes-icons.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

