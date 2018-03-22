---
title: Grootte- en locatie-eigenschappen | Microsoft Docs
description: Naslagmateriaal voor eigenschappen als Height en Width
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: 991262698ee12d4149dee95e27ecc3df311a849e
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="size-and-location-properties-in-powerapps"></a>Grootte- en locatie-eigenschappen in PowerApps
## <a name="overview"></a>Overzicht
Configureer hoe groot een besturingselement (of een element van een besturingselement) is en waar dit zich ten opzichte van het scherm bevindt.

## <a name="position"></a>Positie
**X**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is). Als u een besturingselement **[Kaart](control-card.md)** hebt in een container met meerdere kolommen, bepaalt deze eigenschap de kolom waarin de kaart wordt weergegeven.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Audio](control-audio-video.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Kaart](control-card.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Weergaveformulier](control-form-detail.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Bewerkingsformulier](control-form-detail.md)**, **[Exporteren](control-export-import.md)**, **[Galerie](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Pictogram](control-shapes-icons.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)**, **[Cirkeldiagram](control-pie-chart.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Vorm](control-shapes-icons.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

**Y**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is). Als u een besturingselement **[Kaart](control-card.md)** hebt in een container met meerdere rijen, bepaalt deze eigenschap de rij waarin de kaart wordt weergegeven.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Audio](control-audio-video.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Kaart](control-card.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Weergaveformulier](control-form-detail.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Bewerkingsformulier](control-form-detail.md)**, **[Exporteren](control-export-import.md)**, **[Galerie](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Pictogram](control-shapes-icons.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)**, **[Cirkeldiagram](control-pie-chart.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Vorm](control-shapes-icons.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

## <a name="size"></a>Grootte
**Height**: de afstand tussen de boven- en onderrand van een besturingselement.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Audio](control-audio-video.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Kaart](control-card.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Weergaveformulier](control-form-detail.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Bewerkingsformulier](control-form-detail.md)**, **[Exporteren](control-export-import.md)**, **[Galerie](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Pictogram](control-shapes-icons.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)**, **[Cirkeldiagram](control-pie-chart.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Vorm](control-shapes-icons.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

**AutoHeight**: bepaalt of de hoogte van een label automatisch wordt aangepast als de eigenschap **[Text](properties-core.md)** meer tekens bevat dan het besturingselement kan weergeven.  

* Is van toepassing op het besturingselement **[Label](control-text-box.md)**

**Width**: de afstand tussen de linker- en rechterrand van een besturingselement.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Audio](control-audio-video.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Kaart](control-card.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Weergaveformulier](control-form-detail.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Bewerkingsformulier](control-form-detail.md)**, **[Exporteren](control-export-import.md)**, **[Galerie](control-gallery.md)**, **[HTML-tekst](control-html-text.md)**, **[Pictogram](control-shapes-icons.md)**, **[Afbeelding](control-image.md)**, **[Label](control-text-box.md)**, **[Importeren](control-export-import.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)**, **[Cirkeldiagram](control-pie-chart.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Vorm](control-shapes-icons.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

**WidthFit**: bepaalt of een besturingselement automatisch horizontaal meeschaalt om lege ruimte te vullen in een containerbesturingselement, zoals een besturingselement **[Formulier bewerken](control-form-detail.md)**. Als deze eigenschap voor meerdere kaarten is ingesteld op **true**, wordt de ruimte over de kaarten verdeeld. Zie [De indeling van een gegevensformulieren begrijpen](../working-with-form-layout.md) voor meer informatie.

* Is van toepassing op **[Kaart](control-card.md)**

## <a name="padding"></a>Opvulling
**Padding**: de afstand tussen de tekst op een knop voor importeren of exporteren en de randen van die knop.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Exporteren](control-export-import.md)** en **[Importeren](control-export-import.md)**.

**PaddingBottom**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[HTML-tekst](control-html-text.md)**, **[Afbeelding](control-image.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Keuzerondje](control-radio.md)** en **[Tekstinvoer](control-text-input.md)**.

**PaddingLeft**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[HTML-tekst](control-html-text.md)**, **[Afbeelding](control-image.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Keuzerondje](control-radio.md)** en **[Tekstinvoer](control-text-input.md)**.

**PaddingRight**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[HTML-tekst](control-html-text.md)**, **[Afbeelding](control-image.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Keuzerondje](control-radio.md)** en **[Tekstinvoer](control-text-input.md)**.

**PaddingTop**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[HTML-tekst](control-html-text.md)**, **[Afbeelding](control-image.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Keuzerondje](control-radio.md)** en **[Tekstinvoer](control-text-input.md)**.

## <a name="radius"></a>Radius
**RadiusBottomLeft**: de mate waarin de linkerbenedenhoek van een besturingselement wordt afgerond.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Exporteren](control-export-import.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)** en **[Tekstinvoer](control-text-input.md)**.

**RadiusBottomRight**: de mate waarin de rechterbenedenhoek van een besturingselement wordt afgerond.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Exporteren](control-export-import.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)** en **[Tekstinvoer](control-text-input.md)**.

**RadiusTopLeft**: de mate waarin de linkerbovenhoek van een besturingselement wordt afgerond.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Exporteren](control-export-import.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)** en **[Tekstinvoer](control-text-input.md)**.

**RadiusTopRight**: de mate waarin de rechterbovenhoek van een besturingselement wordt afgerond.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Exporteren](control-export-import.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)** en **[Tekstinvoer](control-text-input.md)**.

