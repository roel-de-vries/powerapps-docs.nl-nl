---
title: 'Besturingselement voor keuzelijst: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Keuzelijst
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a2cb87cf68457771605e78970b8d7a923af61fce
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42835167"
---
# <a name="list-box-control-in-powerapps"></a>Besturingselement voor keuzelijst in PowerApps
Een lijst waarin de gebruiker een of meer items kan selecteren.

## <a name="description"></a>Beschrijving
Een besturingselement **Keuzelijst** toont altijd alle beschikbare opties (in tegenstelling tot een besturingselement **[Vervolgkeuzelijst](control-drop-down.md)**) en de gebruiker kan meer dan een item tegelijk kiezen kan (in tegenstelling tot een besturingselement **[Keuzerondje](control-radio.md)**).

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Default](properties-core.md)**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

**[Items](properties-core.md)**: de gegevensbron die wordt weergegeven in een besturingselement zoals een galerie, een lijst of een grafiek.

Wanneer u een galerie, lijst of diagram toevoegt, wordt in de eigenschappenlijst standaard **Items** weergegeven zodat u eenvoudig de gegevens kunt opgeven die met het nieuwe besturingselement moeten worden weergegeven. U kunt bijvoorbeeld de eigenschap **Items** van een galerie instellen op de tabel **Account** in Salesforce, een tabel met de naam **Inventory** die u hebt gemaakt in Excel en is geüpload naar de cloud of een SharePoint-lijst met de naam **ConferenceSpeakers**.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**ItemPaddingLeft**: de afstand tussen de tekst in een keuzelijst en de linkerrand daarvan.

**[LineHeight](properties-text.md)**: de afstand tussen bijvoorbeeld regels tekst of items in een lijst.

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**[SelectionColor](properties-color-border.md)**: de tekstkleur van geselecteerde items in een lijst of de kleur van het selectiehulpmiddel in een besturingselement Pen.

**[SelectionFill](properties-color-border.md)**: de achtergrondkleur van geselecteerde items in een lijst of een geselecteerd gebied van een besturingselement Pen.

**SelectMultiple**: bepaalt of een gebruiker meerdere items in een keuzelijst kan selecteren.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Distinct**( *Gegevensbron*, *Kolomnaam* )](../functions/function-distinct.md)

## <a name="example"></a>Voorbeeld
1. Voeg een besturingselement **Keuzelijst** toe, geef het de naam **CategoryList** en stel de eigenschap **[Items](properties-core.md)** van het besturingselement in op deze formule:<br>
   **["Carpet","Hardwood","Tile"]**
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
   
    ![Categorieën vloermateriaal in keuzelijst](./media/control-list-box/category-listbox.png)
2. Voeg drie besturingselementen **[Vervolgkeuzelijst](control-drop-down.md)** toe, plaats ze onder **CategoryList** en geef ze de naam **CarpetList**, **HardwoodList** en **TileList**.
3. Stel de eigenschap **[Items](properties-core.md)** van elk besturingselement **[Vervolgkeuzelijst](control-drop-down.md)** in op een van deze waarden:
   
   * CarpetList: **["Caserta Stone Beige","Ageless Beauty Clay", "Lush II Tundra"]**
   * HardwoodList: **["Golden Teak","Natural Hickory", "Victoria Mahogany"]**
   * TileList: **["Honey Onyx Marble","Indian Autumn Slate", "Panaria Vitality Ceramic"]**
     
     ![Namen van vloermateriaal in vervolgkeuzelijsten](./media/control-list-box/flooring-names.png)
4. Stel de eigenschap **[Visible](properties-core.md)** van elk besturingselement **[Vervolgkeuzelijst](control-drop-down.md)** in op een van deze waarden:
   
   * CarpetList: **If("Carpet" in CategoryList.SelectedItems.Value, true)**
   * HardwoodList: **If("Hardwood" in CategoryList.SelectedItems.Value, true)**
   * TileList: **If("Tile" in CategoryList.SelectedItems.Value, true)**
     
     Wilt u meer informatie over de functie **[If](../functions/function-if.md)** of [andere functies](../formula-reference.md)?
5. Druk op F5 en kies vervolgens een of meer items in **CategoryList**.
   
    Op basis van uw keuze of keuzes worden er een of meer besturingselementen **[Vervolgkeuzelijst](control-drop-down.md)** weergegeven.
   
    ![Namen van vloermateriaal in vervolgkeuzelijsten](./media/control-list-box/selected-lists.png)
6. (Optioneel) Druk op Esc om terug te gaan naar de standaardwerkruimte.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
Er moet voldoende kleurcontrast zijn tussen:
* **SelectionColor** en **SelectionFill**
* **SelectionFill** en **[Fill](properties-color-border.md)**
* **[HoverFill](properties-color-border.md)** en **[Fill](properties-color-border.md)**
* **[PressedFill](properties-color-border.md)** en **[Fill](properties-color-border.md)**

Dit komt bovenop de [standaardvereisten voor kleurcontrast](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.

    > [!NOTE]
  > Met de tab-toets navigeert u naar de **Keuzelijst** of ervan weg. Met de pijltoetsen navigeert u door de inhoud van de **Keuzelijst**.
