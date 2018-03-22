---
title: 'Besturingselement voor keuzelijst met invoervak: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Keuzelijst met invoervak
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
ms.date: 09/13/2017
ms.author: fikaradz
ms.openlocfilehash: 4d298e24ea967cbf5cb47638d4296f6efbd758c7
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="combo-box-control-in-powerapps"></a>Besturingselement voor keuzelijst met invoervak in PowerApps
Een besturingselement waarmee gebruikers selecties kunnen maken in geboden opties.  Ondersteunt zoeken en meervoudige selectie.

## <a name="description"></a>Beschrijving
Met een besturingselement voor **keuzelijst met invoervak** kunt u zoeken naar items die u gaat selecteren.  De zoekopdracht wordt aan de serverzijde uitgevoerd op de eigenschap SearchField, zodat de prestaties niet worden beïnvloed door zeer grote gegevensbronnen.  

De modus voor enkelvoudige of meervoudige selectie wordt geconfigureerd via de eigenschap SelectMultiple.

Wanneer u zoekt naar items om te selecteren, kunt u bij elk item ervoor kiezen één gegevenswaarde, twee waarden of een afbeelding en twee waarden (Persoon) weer te geven door de instelling Indeling in het deelvenster Gegevens te wijzigen.

## <a name="people-picker"></a>Personen selecteren
Als u personen wilt selecteren met behulp van een **keuzelijst met invoervak**, kiest u de sjabloon **Persoon** bij de opmaakinstellingen in het deelvenster Gegevens en configureert u de desbetreffende gegevenseigenschappen die voor de onderstaande persoon moeten worden weergegeven.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Items](properties-core.md)**: de gegevensbron waarin selecties kunnen worden gemaakt.

**DefaultItems**: het/de aanvankelijk geselecteerde item(s) voordat de gebruiker het besturingselement gebruikt.

**SelectedItems**: een lijst met geselecteerde items als gevolg van gebruikersinteractie.

**SelectMultiple**: bepaalt of de gebruiker één item of meerdere items kan selecteren.

**IsSearchable**: bepaalt of de gebruiker naar items kan zoeken alvorens ze te selecteren.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Default](properties-core.md)**: de aanvankelijke selectie voordat de gebruiker deze wijzigt in de modus voor enkelvoudige selectie.

**DisplayFields**: Een lijst met velden die worden weergegeven voor elk item dat de zoekopdracht retourneert.  Dit is het gemakkelijkst te configureren via het deelvenster Gegevens op het tabblad Eigenschappen.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**InputTextPlaceholder**: instructietekst die aan eindgebruikers wordt getoond wanneer er geen items zijn geselecteerd.

**OnChange**: hoe de app reageert wanneer de gebruiker een selectie wijzigt.

**OnNavigate**: hoe de app reageert wanneer de gebruiker op een item klikt.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement voor **keuzelijst met invoervak** toe via het menu Besturingselementen op het tabblad Invoegen.  
2. Klik op het tabblad Eigenschappen op Gegevens.  
3. Selecteer de gegevensbron, indeling en verwante eigenschappen daaronder.
4. Stel op het tabblad Geavanceerd de eigenschap **SelectMultiple** in.

    Er verschijnt een functionele **keuzelijst met invoervak** in uw app.

    Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?
