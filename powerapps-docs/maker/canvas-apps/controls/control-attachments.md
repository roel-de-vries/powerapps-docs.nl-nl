---
title: 'Besturingselement voor bijlagen: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Bijlagen
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 04/23/2018
ms.author: fikaradz
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: da9c8f85844e37d6af8e1063b36496c820fbfa07
ms.sourcegitcommit: e2a9d1a6090cdd8aa78515b49f38ed2365217ea6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2018
ms.locfileid: "49384243"
---
# <a name="attachments-control-in-powerapps"></a>Besturingselement voor bijlagen in PowerApps
Een besturingselement waarmee gebruikers bestanden kunnen downloaden op hun apparaat en ook bestanden kunnen uploaden naar en verwijderen uit een SharePoint-lijst of een Common Data Service for Apps-entiteit.

## <a name="limitations"></a>Beperkingen
Het besturingselement voor bijlagen heeft de volgende beperkingen:
1. Bijlagen worden ondersteund met SharePoint-lijsten en CDS for Apps-entiteiten.

1. De functies uploaden en verwijderen werken alleen binnen een formulier.  Besturingselement bijlagen lijkt uitgschakeld wanneer het zich bewerkingsmodus bevindt en niet in een formulier. Merk op dat om het toevoegen en verwijderen van bestanden aan de backend te besparen de eindgebruiker het formulier moet opslaan.

1. U kunt alleen bestanden met een maximale grootte van 10 MB uploaden.  

## <a name="description"></a>Beschrijving
Met het besturingselement **Attachments** kunt u bestanden openen in, toevoegen aan of verwijderen uit een Share-lijst of een CDS for Apps-entiteit.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Items](properties-core.md)**: de bron die de bestanden beschrijft die kunnen worden gedownload.

**MaxAttachments**: het maximum aantal bestanden dat voor het besturingselement is toegestaan.

**MaxAttachmentSize** – de maximaal toegestane bestandsgrootte in MB van elke nieuwe bijlage.  Er is momenteel een limiet van 10 MB.

**OnAttach**: de manier waarop de app reageert wanneer de gebruiker een nieuwe bestandsbijlage toevoegt.

**OnRemove**: de manier waarop de app reageert wanneer de gebruiker een bestaande bijlage verwijdert.

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een bijlage klikt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers. Het doel van de bijlagen moet worden beschreven.

**AddAttachmentText** - De labeltekst voor de koppeling die gebruikt wordt om een nieuwe bijlage toe te voegen.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[DisplayMode](properties-core.md)** - Of het besturingselement het toevoegen en verwijderen van bestanden toestaat (**Bewerken**), alleen gegevens weergeeft (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**MaxAttachmentsText** - de tekst die de koppeling 'bestand bijvoegen' vervangt wanneer het besturingselement het maximaal aantal toegestande bestanden bevat.

**NoAttachmentsText** - Informatieve tekst die wordt weergegeven voor de gebruiker wanneer er geen bestanden zijn bijgevoegd.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (of het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (of het scherm als er geen bovenliggende container is).


## <a name="example"></a>Voorbeeld
1. Maak een app op basis van gegevens waarbij u een SharePoint-lijst als gegevensbron gebruikt. U kunt ook een formulier aan uw app toevoegen en een SharePoint-lijst als de gegevensbron van het formulier instellen.

2. Selecteer het besturingselement **Formulier** in de structuurweergave aan de linkerkant.

3. Klik op **Gegevens** op het tabblad Eigenschappen in het deelvenster met opties aan de rechterkant.

4. Schakel onder **Velden** het veld **Bijlagen** in.

    Het aan de SharePoint-lijst gekoppelde veld Bijlagen wordt in het formulier weergegeven.

[Informatie over het toevoegen en configureren van een besturingselement].(../add-configure-controls.md)


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **ItemColor** en **ItemFill**
* **ItemHoverColor** en **ItemHoverFill**
* **ItemPressedColor** en **ItemPressedFill**
* **AddedItemColor** en **AddedItemFill**
* **RemovedItemColor** en **RemovedItemFill**
* **ItemErrorColor** en **ItemErrorFill**
* **AddAttachmentColor** en **Fill**
* **MaxAttachmentsColor** en **Fill**
* **NoAttachmentsColor** en **Fill**

Dit komt bovenop de [standaardvereisten voor kleurcontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
De volgende eigenschappen moeten aanwezig zijn:
* **[AccessibleLabel](properties-accessibility.md)**
* **AddAttachmentsText**
* **MaxAttachmentsText**
* **NoAttachmentsText**

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
