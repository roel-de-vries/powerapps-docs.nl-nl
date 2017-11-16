---
title: 'Besturingselement voor galerie: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Galerie
services: 
suite: powerapps
documentationcenter: na
author: RickSaling
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/25/2017
ms.author: ricksal
ms.openlocfilehash: a85c0f3e0468c249641e40c3a0b7fb7f1d32a916
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="gallery-control-in-powerapps"></a>Besturingselement voor galerie in PowerApps
Een besturingselement dat andere besturingselementen bevat en waarin een reeks gegevens wordt weergegeven.

## <a name="description"></a>Beschrijving
In een besturingselement **Galerie** kunnen meerdere records uit een gegevensbron worden weergegeven, en elke record kan verschillende gegevenstypen bevatten. Zo kan een besturingselement **Galerie** meerdere contactpersonen bevatten, waarbij voor elke persoon contactgegevens worden vermeld zoals een naam, een adres en een telefoonnummer. Elk gegevensveld wordt weergegeven in een afzonderlijk besturingselement binnen het besturingselement **Galerie**. U kunt deze besturingselementen configureren in de sjabloon van de galerie. De sjabloon wordt weergegeven als het eerste item in de galerie, aan de linkerkant van een besturingselement **Galerie** in horizontale/liggende richting en aan de bovenkant van een besturingselement **Galerie** in verticale/staande richting. Alle wijzigingen die u in de sjabloon aanbrengt, worden overal in het besturingselement **Galerie** doorgevoerd.

Er zijn vooraf gedefinieerde galeriesjablonen beschikbaar voor het weergeven van afbeeldingen, tekst en een galerie met items met variabele hoogte.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Standaard](properties-core.md)**: een item of record in de gegevensbron dat is geselecteerd in de galerie wanneer de app wordt gestart.

**[Items](properties-core.md)**: de gegevensbron die wordt weergegeven in een besturingselement zoals een galerie, een lijst of een grafiek.

**Selected**: het geselecteerde item.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**AllItems**: alle items in een galerie, inclusief waarden van aanvullende besturingselementen die deel uitmaken van de sjabloon van de galerie.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**Layout**: bepaalt of de gebruiker door een galerie kan bladeren of een schuifregelaar moet verplaatsen; van boven naar beneden (**Verticaal**) of van links naar rechts (**Horizontaal**).

**NavigationStep**: hoe ver een galerie schuift als de eigenschap **ShowNavigation** is ingesteld op **true** en de gebruiker een navigatiepijl aan een van de einden van die galerie selecteert.

**ShowNavigation**: bepaalt of er een pijl aan elk einde van een galerie wordt weergegeven, zodat een gebruiker door de items in de galerie kan bladeren door op een pijl te tikken of te klikken.

**ShowScrollbar**: bepaalt of er een schuifbalk wordt weergegeven wanneer de gebruiker een galerie aanwijst.

**Snap**: bepaalt of een galerie automatisch vastklikt wanneer een gebruiker door een galerie bladert, zodat het volgende item in het volledige scherm wordt weergegeven.

**TemplateFill**: de achtergrondkleur van een galerie.

**TemplatePadding**: de afstand tussen items in een galerie.

**TemplateSize**: de hoogte van de sjabloon voor een galerie in verticale/staande richting of de breedte van de sjabloon voor een galerie in horizontale/liggende richting.

**Transition**: het visuele effect (**Pop**, **Push** of **None**) dat wordt toegepast wanneer de gebruiker een item in een galerie aanwijst.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**WrapCount**: het aantal items dat per rij of kolom wordt weergegeven op basis van horizontale of verticale indeling.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Filter**( *Gegevensbron*, *Formule* )](../functions/function-filter-lookup.md)

## <a name="examples"></a>Voorbeelden
### <a name="show-and-filter-data"></a>Gegevens weergeven en filteren
* [Tekst weergeven](control-text-box.md#show-data-in-a-gallery)
* [Afbeeldingen weergeven](control-image.md#show-a-set-of-images-from-a-data-source)
* [Gegevens filteren door een optie te selecteren in een lijst](control-drop-down.md#example)
* [Gegevens filteren door een schuifregelaar aan te passen](control-slider.md#example)

### <a name="get-data-from-the-user"></a>Gegevens ophalen van de gebruiker
* [Tekst ophalen](control-text-input.md#collect-data)
* [Afbeeldingen ophalen](control-add-picture.md#add-images-to-an-image-gallery-control)
* [Foto's ophalen](control-camera.md#example)
* [Geluiden ophalen](control-microphone.md#example)
* [Tekeningen ophalen](control-pen-input.md#create-a-set-of-images)

