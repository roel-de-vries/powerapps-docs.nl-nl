---
title: Toegankelijke apps maken | Microsoft Docs
description: Hoe u apps toegankelijk maakt voor mensen met beperkingen
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
ms.date: 04/03/2018
ms.author: fikaradz
ms.openlocfilehash: bc8a014909ceb817397107b4f64b59aa0c2013f2
ms.sourcegitcommit: 97c0db2968dc07d1bcb21d02e6a6a5c345daa2d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2018
---
# <a name="create-accessible-apps"></a>Toegankelijke apps maken
Een toegankelijke app stelt gebruikers met visuele, gehoor- of andere beperkingen in staat de app goed te kunnen gebruiken.  Toegankelijkheid is een vereiste voor veel regeringen en organisaties. Daarnaast kunt u door onderstaande richtlijnen te volgen uw app beter bruikbaar maken voor alle gebruikers.

## <a name="layout-and-color"></a>Indeling en kleur
Met gezond verstand en een eenvoudig ontwerp kunt u apps toegankelijker maken voor alle gebruikers ervan.  Houd rekening met onderstaande suggesties wanneer u grote aanpassingen aan apps maakt.  PowerApps-thema's zijn standaard toegankelijk.
- Zorg ervoor dat alle elementen duidelijk zichtbaar zijn en dat de tekst groot genoeg is.  Alle inhoud moet met het blote oog eenvoudig kunnen worden gelezen en begrepen.
- Sleutel niet aan de zichtbaarheidseigenschap van items om elementen beter zichtbaar te maken.  Als u iets afhankelijk van een voorwaarde moet weergeven, maakt u de inhoud op een nieuw scherm, zodat gebruikers erheen en terug kunnen navigeren.
- Zorg ervoor dat invoerelementen gelabeld zijn op het scherm. De eigenschap **[AccessibilityLabel](controls/properties-accessibility.md)** definieert wat de schermlezer zal aankondigen.
- Als u kleuren aanpast, moet u ervoor zorgen dat het contrast tussen tekst en achtergrond 4,5:1 of groter is.  Er zijn softwareprogramma's beschikbaar om u hierbij te helpen.
- Zorg ervoor dat de indeling een logische stroom volgt wanneer de inhoud wordt gelezen van boven naar onder, van links naar rechts.


## <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
Wanneer u de toegankelijkheid van de app test, moet u controleren of deze kan worden gebruikt met alleen het toetsenbord, de toegankelijkheidsmodus van iOS/Android en of u erheen kunt navigeren wanneer de schermlezer is ingeschakeld.

Zorg bij toetsenbordnavigatie (met of zonder schermlezer) voor een logische volgorde wanneer u met de TAB-toets navigeert naar invoervelden. Dit doet u door de eigenschap **[TabIndex](controls/properties-accessibility.md)** van elk besturingselement in te stellen:
- Besturingselementen voor label, afbeelding, pictogram en vorm: voor interactieve elementen (knoppen) stelt u TabIndex in op 0 en voor decoratieve elementen of tekst stelt u TabIndex in op -1.
- Stel TabIndex niet hoger in dan 0.

## <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
De volgende combinaties van software zijn de ondersteunde aanbevelingen voor het gebruik van PowerApps met een schermlezer:

- **Windows**: Edge / Verteller
- **macOS**: Safari / VoiceOver
- **Android**: PowerApps-app / TalkBack
- **iOS**: PowerApps-app / VoiceOver

Het volgende is aanbevolen om een goede ervaring met de schermlezer te garanderen:

- Zorg ervoor dat de eigenschap **[AccessibilityLabel](controls/properties-accessibility.md)** is ingesteld voor alle invoerelementen.
- Geef voor afbeeldingen bij **[AccessibilityLabel](controls/properties-accessibility.md)** een toepasselijke beschrijving op.
  - Als een afbeelding niet wordt gebruikt als knop of link (als het pictogram enkel decoratief is) en niet moet worden gelezen door de schermlezer, moet u **[AccessibilityLabel](controls/properties-accessibility.md)** leeg laten of niet instellen.
  - Als een afbeelding of pictogram wordt gebruikt als knop stelt u **[TabIndex](controls/properties-accessibility.md)** in op 0 en geeft u voor **[AccessibilityLabel](controls/properties-accessibility.md)** de beschrijving van de link op.


## <a name="multimedia"></a>Multimedia
Zorg ervoor dat alle video's zijn voorzien van ondertiteling en dat de gebruiker toegang heeft tot transcripten van alle audio-opnamen.  Het besturingselement voor **video** ondersteunt ondertiteling in WebVTT-indeling via de eigenschap **ClosedCaptionsUrl**.

Houd er rekening mee dat **Timer**, wanneer de schermlezer is ingeschakeld, niet de tijd van de knop leest, maar hoeveel tijd er is verstreken.  U kunt aankondigingen niet uitschakelen, zelfs niet wanneer de timer is verborgen met een lage dekking.

## <a name="working-with-signatures"></a>Werken met handtekeningen
Als u een handtekeningenveld gebruikt met het besturingselement PenInput, moet u een alternatieve methode voor de invoer van handtekeningen inschakelen.  De aanbevolen manier is een TextInput-besturingselement weer te geven waar de gebruiker zijn naam kan typen.  Zorg ervoor dat de instructies voor ondertekenen zijn opgenomen in de eigenschap **[AccessibilityLabel](controls/properties-accessibility.md)** en dat het besturingselement dicht bij de peninvoer staat (rechts ernaast of direct eronder).



Gerelateerde informatie: **[eigenschappen voor toegankelijkheid](controls/properties-accessibility.md)**
