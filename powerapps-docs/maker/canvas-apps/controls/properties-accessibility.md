---
title: Eigenschappen voor toegankelijkheid | Microsoft Docs
description: Naslaginformatie over eigenschappen zoals TabIndex en Tooltip
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
ms.date: 01/26/2017
ms.author: fikaradz
ms.openlocfilehash: d35b4bc7a6e479ce47ad0a0b841a6ed9ccfd1a52
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="accessibility-properties-in-powerapps"></a>Eigenschappen voor toegankelijkheid in PowerApps
Eigenschappen configureren om alternatieve manieren van communicatie mogelijk maken met besturingselementen voor gebruikers met een handicap.

### <a name="properties"></a>Eigenschappen
**AccessiblityLabel**: beschrijving van het besturingselement dat moet worden gelezen door schermlezers.   Door een lege waarde voor de bedieningselementen afbeelding, pictogram en vorm worden de besturingselementen onzichtbaar gemaakt voor de schermlezer en als sierelementen behandeld.

* Is van toepassing op de besturingselementen **[Audio](control-audio-video.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Selectievakje](control-check-box.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[HTML-tekst](control-html-text.md)**, **[Afbeelding](control-image.md)**, **[Label](control-text-box.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

**TabIndex**: past de tabbladvolgorde van besturingselementen tijdens runtime aan wanneer.

De waarde is standaard nul, wat betekent dat de tabbladvolgorde standaard is, op basis van de XY-coördinaat van het besturingselement.  Als u een waarde groter dan nul instelt, wordt de volgorde van de tabbladen van het besturingselement aangepast.  De TabIndex-waarde 2 voor een besturingselement gaat vóór een besturingselement met de TabIndex-waarde 3 of hoger.

Bij containers met de besturingselementen Formulier en Galerie wordt altijd door alle elementen van de container gebladerd voordat wordt doorgegaan met de besturingselementen buiten de container.  De tabbladvolgorde van de container komt overeen met die van de laagste TabIndex-waarde van een onderliggend besturingselement.

Als TabIndex op -1 wordt ingesteld, wordt de toegang tot de tab via het besturingselement uitgeschakeld. Van afbeeldingen, pictogrammen en vormen worden ook niet-interactieve elementen gemaakt.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)**, **[Keuzelijst](control-list-box.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)** en **[Wisselknop](control-toggle.md)**.
