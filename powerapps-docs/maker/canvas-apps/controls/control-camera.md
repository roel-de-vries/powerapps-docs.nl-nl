---
title: 'Besturingselement voor camera: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Camera
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
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: a3a724ad42082962ec8aea4e616f1d75aa7299ec
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="camera-control-in-powerapps"></a>Besturingselement voor camera in PowerApps
Een besturingselement waarmee de gebruiker foto's kan maken met behulp van de camera van het apparaat.

## <a name="description"></a>Beschrijving
Als u dit besturingselement toevoegt, kan de gebruiker een gegevensbron bijwerken met een of meer foto's, vanaf elke locatie waar de app wordt uitgevoerd.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**Camera**: op een apparaat dat meerdere camera’s heeft, is dit de numerieke id van de camera die door de app wordt gebruikt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**Brightness**: hoeveel licht de gebruiker waarschijnlijk in een foto waarneemt.

**Contrast**: hoe gemakkelijk de gebruiker vergelijkbare kleuren in een foto kan onderscheiden.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**OnStream**: hoe de app reageert wanneer de eigenschap **Stream** wordt bijgewerkt.

**Photo**: het beeld dat wordt vastgelegd wanneer de gebruiker een foto maakt.

**Stream**: automatisch bijgewerkte foto op basis van de eigenschap **StreamRate**.

**StreamRate**: hoe vaak de foto in de eigenschap **Stream** wordt bijgewerkt, in milliseconden.  Dit kan een waarde tussen 100 (1/10e van een seconde) tot 3.600.000 (1 uur) zijn.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**Zoom**: het percentage waarmee een foto van een camera wordt vergroot of de weergave van een bestand in een PDF-viewer.

## <a name="related-functions"></a>Verwante functies
[**Patch**( *Gegevensbron*, *Basisrecord*, *Wijzigingsrecord* )](../functions/function-patch.md)

## <a name="example"></a>Voorbeeld
### <a name="add-photos-to-an-image-gallery-control"></a>Foto's toevoegen aan een besturingselement Afbeeldingengalerie
1. Voeg een besturingselement **Camera** toe, geef het besturingselement de naam **MijnCamera** en stel de eigenschap **[OnSelect](properties-core.md)** in op deze formule:<br>
   **Collect(MyPix, MyCamera.Photo)**
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
   
    Wilt u meer informatie over de functie **[Collect](../functions/function-clear-collect-clearcollect.md)** of [andere functies](../formula-reference.md)?
2. Druk op F5 en maak een foto door op **MijnCamera** te klikken of te tikken.
3. Voeg een besturingselement **[Afbeeldingengalerie](control-gallery.md)** toe en pas het formaat van het besturingselement **[Afbeeldingen](control-image.md)** van de galerie, de sjabloon en het besturingselement **Afbeeldingengalerie** zelf aan zodat deze op het scherm passen.
4. Stel de eigenschap **[Items](properties-core.md)** van het besturingselement **Afbeeldingengalerie** in op deze expressie:<br>**MijnAfbeeldingen.Url**.
5. Stel de eigenschap **[Items](properties-visual.md)** van het besturingselement **Afbeelding** in de galerie in op deze expressie:<br>
   **ThisItem.Url**
   
    De foto die u hebt gemaakt, wordt weergegeven in het besturingselement **Afbeeldingengalerie**.
6. Maak zo veel foto's als u wilt en ga vervolgens terug naar de standaardwerkruimte door op Esc te drukken.
7. (Optioneel) Stel de eigenschap **OnSelect** van het besturingselement **Afbeelding** in het besturingselement **Afbeeldingengalerie** in op **Remove(MijnAfbeeldingen, ThisItem)**, druk op F5 en klik of tik op een foto om deze te verwijderen.

Gebruik de functie **[SaveData](../functions/function-savedata-loaddata.md)** om de foto's lokaal op te slaan of de functie **[Patch](../functions/function-patch.md)** om een gegevensbron bij te werken.

