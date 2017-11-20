---
title: 'Besturingselement voor bijlagen: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Bijlagen
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
ms.date: 09/29/2017
ms.author: fikaradz
ms.openlocfilehash: 2fd5db380eead5403d4cc7d927da5a24aa24abc9
ms.sourcegitcommit: ce66ba8eadc41d5f260217d164f8317b90ae1504
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2017
---
# <a name="attachments-control-in-powerapps"></a>Besturingselement voor bijlagen in PowerApps
Een besturingselement waarmee gebruikers bestanden naar hun apparaat kunnen downloaden.  De uploadfunctionaliteit is binnenkort beschikbaar.

## <a name="description"></a>Beschrijving
Met het besturingselement **Bijlagen** kunt u bestanden openen die in een gegevensbron zijn opgeslagen.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Items](properties-core.md)**: de bron die de bestanden beschrijft die kunnen worden gedownload.

**MaxAttachments**: het maximum aantal bestanden dat voor het besturingselement is toegestaan.

**OnAttach**: de manier waarop de app reageert wanneer de gebruiker een nieuwe bestandsbijlage toevoegt.

**OnRemove**: de manier waarop de app reageert wanneer de gebruiker een bestaande bijlage verwijdert.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een bijlage klikt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**AddAttachmentText**: de tekst van het label voor de knop die wordt gebruikt voor het toevoegen van een nieuwe bijlage.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**NoAttachmentsText**: instructietekst die voor de gebruiker wordt weergegeven wanneer er geen bijlagen zijn om weer te geven.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (of het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (of het scherm als er geen bovenliggende container is).


## <a name="example"></a>Voorbeeld
1. Maak een app op basis van gegevens waarbij u een SharePoint-lijst als gegevensbron gebruikt.  U kunt ook een formulier aan uw app toevoegen en een SharePoint-lijst als de gegevensbron van het formulier instellen.

2. Selecteer het besturingselement **Formulier** in de structuurweergave aan de linkerkant.

3. Klik op **Gegevens** op het tabblad Eigenschappen in het deelvenster met opties aan de rechterkant.

4. Schakel onder **Velden** het veld **Bijlagen** in.

    Het aan de SharePoint-lijst gekoppelde veld Bijlagen wordt in het formulier weergegeven.

Weet u niet hoe u [een besturingselement kunt toevoegen of configureren](../add-configure-controls.md)?
