---
title: 'Besturingselement voor editor van tekst met opmaak: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement voor de editor van tekst met opmaak
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
ms.date: 05/24/2018
ms.author: fikaradz
ms.openlocfilehash: 36fa317a4611c72ab4d2f6ce09e176b14b688a55
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34585080"
---
# <a name="rich-text-editor-control-experimental-in-powerapps"></a>Besturingselement voor editor van tekst met opmaak (experimenteel) in PowerApps
Dit is een experimenteel bedieningselement waarmee eindgebruikers tekst kunnen opmaken in een WYSIWYG-bewerkingsvak.  De uitvoerindeling is HTML.

## <a name="description"></a>Beschrijving
Het bedieningselement **RTF-editor** biedt de app-gebruiker een WYSIWYG-bewerkingsvak voor het opmaken van tekst.  De invoer- en uitvoerindeling van het bedieningselement is HTML.

Met het bedieningselement kan gekopieerde tekst met opmaak (d.w.z. uit een webbrowser of Word) in het bedieningselement worden geplakt.  

De bedoeling van het bedieningselement is tekst op te maken; het biedt geen garantie dat de integriteit van de ingevoerde HTML wordt behouden.  Alle script-, stijl- en objecttags en andere tags die mogelijk voor problemen zorgen, worden door de editor verwijderd.  Dit betekent dat tekst met opmaak er mogelijk niet hetzelfde uitziet als in het product waarin de tekst is gemaakt als dit buiten PowerApps is gebeurd.

Momenteel worden de volgende functies ondersteund:
- Vet, cursief, onderstrepen
- Tekstkleur, markeringskleur
- Tekengrootte
- Genummerde lijsten, lijsten met opsommingstekens
- Hyperlinks
- Opmaak wissen

Als u het bedieningselement in een formulier wilt gebruiken, selecteert u de kaart Tekst van meerdere regels bewerken en past u deze aan door het RTE-bedieningselement in te voegen.

## <a name="limitations"></a>Beperkingen
De huidige versie van het bedieningselement is experimenteel vanwege de volgende tijdelijke beperkingen:
- Het bedieningselement bevat beperkte functies voor het opmaken van tekst.  

- Het bedieningselement is vooral bedoeld voor gebruik in browsers op grote schermen.  Het gebruik van het bedieningselement op een mobiele telefoon kan een frustrerende ervaring zijn.

- Bekende problemen met de ontwerpervaring bij het gebruik van de Windows-studio of Edge-browser.  Momenteel wordt aanbevolen de webstudio in Chrome te gebruiken.


## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Default](properties-core.md)**: invoereigenschap voor de oorspronkelijke tekstwaarde die in de editor wordt weergegeven.

**HtmlText**: uitvoereigenschap voor de resulterende tekst met opmaak in HTML-indeling.



## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers. Het doel van de bijlagen moet worden beschreven.

**[DisplayMode](properties-core.md)** - Of het besturingselement het toevoegen en verwijderen van bestanden toestaat (**Bewerken**), alleen gegevens weergeeft (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (of het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (of het scherm als er geen bovenliggende container is).