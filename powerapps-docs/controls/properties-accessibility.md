---
title: Eigenschappen voor toegankelijkheid | Microsoft Docs
description: Naslaginformatie over eigenschappen zoals TabIndex en Tooltip
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
ms.date: 01/26/2017
ms.author: anneta
ms.openlocfilehash: d8cc9d6c8586856dcaa27f67d3ea1fdc17fa0433
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="accessibility-properties-in-powerapps"></a>Eigenschappen voor toegankelijkheid in PowerApps
## <a name="overview"></a>Overzicht
Eigenschappen configureren om alternatieve manieren van communicatie mogelijk maken met besturingselementen zodat gebruikers met een visuele handicap ook aan de slag kunnen.

## <a name="properties"></a>Eigenschappen
**Tooltip**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.  Tekst wordt door Aria-labels gebruikt ter ondersteuning van schermlezers.

* Is van toepassing op de besturingselementen **[Audio](control-audio-video.md)**, **[Knop](control-button.md)**, **[Camera](control-camera.md)**, **[Selectievakje](control-check-box.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[HTML-tekst](control-html-text.md)**, **[Afbeelding](control-image.md)**, **[Label](control-text-box.md)**, **[Keuzelijst](control-list-box.md)**, **[Microfoon](control-microphone.md)**, **[PDF-viewer](control-pdf-viewer.md)**, **[Peninvoer](control-pen-input.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)**, **[Timer](control-timer.md)**, **[Wisselknop](control-toggle.md)** en **[Video](control-audio-video.md)**.

**TabIndex**: past de tabbladvolgorde van besturingselementen tijdens runtime aan wanneer.

De waarde is standaard nul, wat betekent dat de tabbladvolgorde standaard is, op basis van de XY-coördinaat van het besturingselement.  Als u een waarde groter dan nul instelt, wordt de volgorde van de tabbladen van het besturingselement aangepast.  De TabIndex-waarde 2 voor een besturingselement gaat vóór een besturingselement met de TabIndex-waarde 3 of hoger.

Bij containers met de besturingselementen Formulier en Galerie wordt altijd door alle elementen van de container gebladerd voordat wordt doorgegaan met de besturingselementen buiten de container.  De tabbladvolgorde van de container komt overeen met die van de laagste TabIndex-waarde van een onderliggend besturingselement.

Als TabIndex op -1 wordt ingesteld, wordt de toegang tot de tab via het besturingselement uitgeschakeld. Afbeeldingen, pictogrammen en vormen zullen ook onzichtbaar zijn voor de schermlezer.

* Is van toepassing op de besturingselementen **[Knop](control-button.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Afbeelding](control-image.md)**, **[Importeren](control-export-import.md)**, **[Keuzelijst](control-list-box.md)**, **[Keuzerondje](control-radio.md)**, **[Waardering](control-rating.md)**, **[Schuifregelaar](control-slider.md)**, **[Tekstinvoer](control-text-input.md)** en **[Wisselknop](control-toggle.md)**.

