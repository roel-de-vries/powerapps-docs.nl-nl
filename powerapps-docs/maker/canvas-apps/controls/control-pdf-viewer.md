---
title: 'Besturingselement voor PDF-viewer: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement PDF-viewer
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 44272022daf547de64ebd175f29630175c7e3757
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39016554"
---
# <a name="pdf-viewer-control-experimental-in-powerapps"></a>Besturingselement voor PDF-viewer (experimenteel) in PowerApps
Een experimenteel besturingselement dat de inhoud van een PDF-bestand toont.

## <a name="description"></a>Beschrijving
U kunt tekst, afbeeldingen en andere inhoud uit een PDF-bestand weergeven door dit type besturingselement toe te voegen en de eigenschap **Document** in te stellen op de URL (tussen dubbele aanhalingstekens) van het bestand dat u wilt weergeven.

## <a name="limitations"></a>Beperkingen
Houd er rekening mee dat PDF Viewer, als gevolg van de beveiligingsarchitectuur van PowerApps, alleen ondersteuning biedt voor HTTPS-koppelingen, niet voor HTTP.  
Als het PDF-document zich op een server met beperkende CORS-instellingen bevindt, kunt u dit mogelijk niet weergeven in uw app.  Om dit probleem op te lossen moet de server die PDF-documenten host toestemming geven aan cross origin requests (CORS) die afkomstig zijn van powerapps.com.

Als het document kan niet worden geopend in PowerApps, wordt de optie om het document in een externe browser te openen voor de eindgebruiker gepresenteerd.  Deze optie is ook beschikbaar in het systeemmenu voor alle externe documenten.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**Document**: de URL, tussen dubbele aanhalingstekens, van een PDF-bestand.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**ActualZoom**: de werkelijke zoomfactor van het besturingselement. Deze kan verschillen van de zoomfactor die met de eigenschap **Zoom** is gevraagd.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**CurrentFindText**: de zoekterm die op dat moment wordt gebruikt.

**CurrentPage**: het nummer van de pagina in een PDF-bestand die op dat moment wordt weergegeven.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**FindNext**: hiermee wordt het volgende exemplaar van **FindText** in het document gezocht.

**FindPrevious**: hiermee wordt het vorige exemplaar van **FindText** in het document gezocht.

**FindText**: de zoekterm die in het document wordt gezocht.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**OnStateChange**: hoe een app reageert wanneer de status van het besturingselement verandert.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**Page**: het nummer van de pagina die u wilt weergeven.

**PageCount**: het aantal pagina's in een document.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**ShowControls**: bepaalt of een audio- of videospeler bijvoorbeeld een knop Afspelen en een volumeregelaar bevat, en of een besturingselement Pen bijvoorbeeld pictogrammen weergeeft voor Tekenen en Wissen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**Zoom**: het percentage waarmee een foto van een camera wordt vergroot of de weergave van een bestand in een PDF-viewer.

## <a name="example"></a>Voorbeeld

Voeg een besturingselement **PDF-viewer** toe en stel de eigenschap **Document** in op de URL (tussen dubbele aanhalingstekens) van een PDF-bestand, zoals in dit voorbeeld:

  **"https://blog.mozilla.org/security/files/2015/05/HTTPS-FAQ.pdf"**

    The control shows the PDF file.

    Don't know how to [add and configure a control](../add-configure-controls.md)?

## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid

Niet alle toegankelijkheidsfuncties van PDF-documenten worden ondersteund omdat de **PDF-viewer** nog steeds in de experimentele fase is. **ShowControls** moet daarom worden ingesteld op **true**, zodat gebruikers het document in een externe toepassing kunnen openen.

Informatie over het maken van toegankelijke PDF-documenten met de standaarden [WCAG 2.0](https://www.w3.org/TR/WCAG-TECHS/pdf.html) en [PDF/UA](https://www.pdfa.org/pdfua-the-iso-standard-for-universal-accessibility/).

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* U kunt een koptekst met een  **[Label](control-text-box.md)** toevoegen, als het PDF-document niet over een titel beschikt. De kop kan direct vóór de **PDF-viewer** worden geplaatst.
