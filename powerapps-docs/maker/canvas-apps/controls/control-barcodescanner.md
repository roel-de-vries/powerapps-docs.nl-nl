---
title: 'Besturingselement voor streepjescodescanner: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Streepjescodescanner
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 853558273521491467fa7474688ce9c984ac5db6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42862463"
---
# <a name="barcode-scanner-control-experimental-in-powerapps"></a>Besturingselement Streepjescodescanner (experimenteel) in PowerApps
Een experimenteel besturingselement waarmee de gebruiker foto’s kan maken met behulp van de streepjescodescanner op het apparaat.

## <a name="description"></a>Beschrijving
Als u dit besturingselement toevoegt, kan de gebruiker een gegevensbron bijwerken met een of meer foto's, vanaf elke locatie waar de app wordt uitgevoerd.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**streepjescodescanner**: op een apparaat met meer dan één streepjescodescanner is dit de numerieke id van de streepjescodescanner die de app gebruikt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**ShowLiveBarcodeDetection**: of visuele aanwijzingen worden weergegeven die de status van de streepjescodedetectie aangeven. Gele rechthoeken vertegenwoordigen gebieden die worden onderzocht. Een groene lijn over een rechthoek geeft geslaagde streepjescode-identificatie aan.

**Stream**: automatisch bijgewerkte foto op basis van de eigenschap **StreamRate**.

**StreamRate**: hoe vaak de foto in de eigenschap **Stream** wordt bijgewerkt, in milliseconden.  Dit kan een waarde tussen 100 (1/10e van een seconde) tot 3.600.000 (1 uur) zijn.

**Text**: waarde van de streepjescode die als laatste is geïdentificeerd door de scanner.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Patch**( *Gegevensbron*, *Basisrecord*, *Wijzigingsrecord* )](../functions/function-patch.md)

## <a name="example"></a>Voorbeeld
### <a name="add-photos-to-an-image-gallery-control"></a>Foto's toevoegen aan een besturingselement Afbeeldingengalerie
1. Voeg een besturingselement **Streepjescodescanner** toe en geef het de naam **MijnStreepjescodescanner**

    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Voeg een besturingselement **Label** toe en stel de uitvoer in op **Text** van de streepjescodescanner.  
3. Scan een streepjescode van het type dat is ingesteld met de eigenschap BarcodeType.
4. De gescande streepjescode wordt in het label weergegeven.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="video-alternatives"></a>Alternatieven voor video
* U kunt een **[Label](control-text-box.md)** toevoegen met de **[Text](properties-core.md)** ingesteld op de **Text** van de streepjescodescanner. Aangezien de streepjescodescanner de geïdentificeerde streepjescodewaarde niet weergeeft, wordt de scanner toegankelijk voor iedereen, niet alleen voor mensen met een visuele handicap, wanneer het bovenstaande wordt uitgevoerd.

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.

    > [!NOTE]
  > Schermlezers melden het wanneer een nieuwe streepjescode is gevonden. De waarde wordt niet gemeld. Zolang de streepjescode in beeld is, wordt u er om de vijf seconden door schermlezers aan herinnerd dat nog steeds dezelfde streepjescode wordt geïdentificeerd.
