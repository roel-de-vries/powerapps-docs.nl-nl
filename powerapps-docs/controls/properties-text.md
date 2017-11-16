---
title: Teksteigenschappen | Microsoft Docs
description: Naslagmateriaal voor eigenschappen als Text, Tooltip en HintText
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
ms.openlocfilehash: 1f3d05d98755e8f0eff8af5e3dde5921d0de0301
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="text-properties-in-powerapps"></a>Teksteigenschappen in PowerApps
## <a name="overview"></a>Overzicht
Configureer de tekst die wordt weergegeven op een besturingselement, in de knopinfo of als een hint wanneer de gebruiker gegevens typt, en geef andere tekstgerelateerde kenmerken op.

## <a name="text-appearance"></a>Tekenopmaak
**Font**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Exporteren](control-export-import.md)**, **[HTML-tekst](control-html-text.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Cirkeldiagram](control-pie-chart.md)**, **[Keuzerondje](control-radio.md)**, **[Tekstinvoer](control-text-input.md)** en **[Timer](control-timer.md)**.

**FontWeight**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Exporteren](control-export-import.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Keuzelijst](control-list-box.md)**, **[Keuzerondje](control-radio.md)**, **[Tekstinvoer](control-text-input.md)** en **[Timer](control-timer.md)**.

**Italic**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Exporteren](control-export-import.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Keuzelijst](control-list-box.md)**, **[Keuzerondje](control-radio.md)**, **[Tekstinvoer](control-text-input.md)** en **[Timer](control-timer.md)**.

**Size**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Kolomdiagram](control-column-line-chart.md)**, **[Datumkiezer](control-date-picker.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Exporteren](control-export-import.md)**, **[HTML-tekst](control-html-text.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Lijndiagram](control-column-line-chart.md)**, **[Keuzelijst](control-list-box.md)**, **[Peninvoer](control-pen-input.md)**, **[Cirkeldiagram](control-pie-chart.md)**, **[Keuzerondje](control-radio.md)**, **[Tekstinvoer](control-text-input.md)** en **[Timer](control-timer.md)**.

**Strikethrough**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Exporteren](control-export-import.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Keuzelijst](control-list-box.md)**, **[Keuzerondje](control-radio.md)**, **[Tekstinvoer](control-text-input.md)** en **[Timer](control-timer.md)**.

**Underline**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Vervolgkeuzelijst](control-drop-down.md)**, **[Exporteren](control-export-import.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Keuzelijst](control-list-box.md)**, **[Keuzerondje](control-radio.md)**, **[Tekstinvoer](control-text-input.md)** en **[Timer](control-timer.md)**.

## <a name="text-placement"></a>Tekstplaatsing
**Align**: de locatie van tekst in verhouding tot het horizontale midden van het besturingselement.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Exporteren](control-export-import.md)**, **[Importeren](control-export-import.md)**, **[Label](control-text-box.md)**, **[Keuzerondje](control-radio.md)**, **[Tekstinvoer](control-text-input.md)** en **[Timer](control-timer.md)**.

**LineHeight**: de afstand tussen bijvoorbeeld regels tekst of items in een lijst.

* Is van toepassing op de besturingselementen **[Keuzelijst](control-list-box.md)**, **[Label](control-text-box.md)**, **[Keuzerondje](control-radio.md)** en **[Tekstinvoer](control-text-input.md)**.

**VerticalAlign**: de locatie van de tekst in een besturingselement in verhouding tot het verticale midden van dat besturingselement.

* Is van toepassing op de besturingselementen **[Afbeelding toevoegen](control-add-picture.md)**, **[Knop](control-button.md)**, **[Selectievakje](control-check-box.md)**, **[Exporteren](control-export-import.md)**, **[Importeren](control-export-import.md)** en **[Label](control-text-box.md)**.

