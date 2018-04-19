---
title: 'Besturingselement voor bijlagen: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Bijlagen
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
ms.date: 09/29/2017
ms.author: fikaradz
ms.openlocfilehash: 5bb7e4f27ed7ee0a30fb028d4d8dfd20a5fc250b
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2018
---
# <a name="attachments-control-in-powerapps"></a>Besturingselement voor bijlagen in PowerApps
Een besturingselement waarmee gebruikers bestanden kunnen downloaden op hun apparaat en ook bestanden kunnen uploaden naar en verwijderen van een SharePoint-lijst.

## <a name="limitations"></a>Beperkingen
Het besturingselement voor bijlagen heeft de volgende tijdelijke beperkingen:
1. Downloaden van bijlagen wordt niet ondersteund in Internet Explorer.

1. Uploaden van bijlagen werkt alleen met gegevensbronnen van SharePoint-lijst.  Ondersteuning voor andere gegevensbronnen wordt stapsgewijs geïntroduceerd, beginnend bij CDS.

1. De functies uploaden en verwijderen werken alleen binnen een formulier.  Besturingselement bijlagen lijkt uitgschakeld wanneer het zich bewerkingsmodus bevindt en niet in een formulier.   Merk op dat om het toevoegen en verwijderen van bestanden aan de backend te besparen de eindgebruiker het formulier moet opslaan.

1. U kunt alleen bestanden met een maximale grootte van 10 MB uploaden.  

## <a name="description"></a>Beschrijving
Met een besturingselement **Attachments** kunt u bestanden openen die zijn opgeslagen op een gegevensbron en ook bestanden toevoegen aan en verwijderen van een SharePoint-lijst.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Items](properties-core.md)**: de bron die de bestanden beschrijft die kunnen worden gedownload.

**MaxAttachments**: het maximum aantal bestanden dat voor het besturingselement is toegestaan.

**MaxAttachmentSize** – de maximaal toegestane bestandsgrootte in MB van elke nieuwe bijlage.  Er is momenteel een limiet van 10 MB.

**OnAttach**: de manier waarop de app reageert wanneer de gebruiker een nieuwe bestandsbijlage toevoegt.

**OnRemove**: de manier waarop de app reageert wanneer de gebruiker een bestaande bijlage verwijdert.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een bijlage klikt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**AccessibleLabel** - Het label dat wordt vermeld door schermlezers.

**AddAttachmentText** - De labeltekst voor de koppeling die gebruikt wordt om een nieuwe bijlage toe te voegen.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)** - Of het besturingselement het toevoegen en verwijderen van bestanden toestaat (**Bewerken**), alleen gegevens weergeeft (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**MaxAttachmentsText** - de tekst die de koppeling 'bestand bijvoegen' vervangt wanneer het besturingselement het maximaal aantal toegestande bestanden bevat.

**NoAttachmentsText** - Informatieve tekst die wordt weergegeven voor de gebruiker wanneer er geen bestanden zijn bijgevoegd.

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
