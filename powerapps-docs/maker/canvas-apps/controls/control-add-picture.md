---
title: 'Besturingselement voor toevoegen van afbeeldingen: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Afbeelding toevoegen
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.reviewer: anneta
ms.openlocfilehash: 694222de50280325e6648362fbe9e745131b716b
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014875"
---
# <a name="add-picture-control-in-powerapps"></a>Besturingselement voor toevoegen van afbeeldingen in PowerApps
Hiermee wordt een foto gemaakt of worden afbeeldingen geladen van het lokale apparaat.

## <a name="description"></a>Beschrijving
Met dit besturingselement kunnen gebruikers foto's maken of afbeeldingsbestanden uploaden van hun apparaat en de gegevensbron met deze inhoud bijwerken. Op een mobiel apparaat kan de gebruiker in een dialoogvenster kiezen tussen het maken van een foto of het selecteren van een beschikbare foto.

Dit besturingselement is een gegroepeerd besturingselement dat twee besturingselementen bevat: een **Afbeelding** en een knop **Media toevoegen**. Het besturingselement **Afbeelding** toont de geüploade afbeelding of een tijdelijke aanduiding als geen afbeelding is geüpload. De **knop Media toevoegen** vraagt om een afbeelding die moet worden geüpload.

Zie de [verwijzing naar het besturingselement van Afbeelding](control-image.md) voor eigenschappen van **Afbeelding**.

## <a name="add-media-button-properties"></a>Eigenschappen van de knop media toevoegen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers. Het doel van het toevoegen van een foto moet worden beschreven.

**[Align](properties-text.md)**: de locatie van tekst in verhouding tot het horizontale midden van het besturingselement.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**ChangePictureText**: tekst die wordt weergegeven op de knop wanneer een afbeelding is geüpload.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**Error**: als er een probleem is opgetreden bij het uploaden van een afbeelding, bevat deze eigenschap een relevant foutbericht.

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

**Media**: een identificatie voor de clip die met het besturingselement voor audio of video wordt afgespeeld.

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[Padding](properties-size-location.md)**: de afstand tussen de tekst op een knop voor importeren of exporteren en de randen van die knop.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**[Size](properties-text.md)**: de tekengrootte van de tekst die in een besturingselement wordt weergegeven.

**[Strikethrough](properties-text.md)**: hiermee wordt aangegeven of een streep door de tekst van een besturingselement wordt weergegeven.

**[TabIndex](properties-accessibility.md)**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

**[Tekst](properties-core.md)**: tekst die wordt weergegeven op de knop als een afbeelding niet is geüpload.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**[Underline](properties-text.md)**: hiermee wordt aangegeven of onder de tekst in een besturingselement een streep wordt weergegeven.

**[VerticalAlign](properties-text.md)**: de locatie van de tekst in een besturingselement in verhouding tot het verticale midden van dat besturingselement.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Patch**( *Gegevensbron*, *Basisrecord*, *Wijzigingsrecord* )](../functions/function-patch.md)

## <a name="examples"></a>Voorbeelden
### <a name="add-images-to-an-image-gallery-control"></a>Afbeeldingen toevoegen aan een besturingselement Afbeeldingengalerie
1. Voeg een besturingselement **Afbeelding toevoegen** toe en klik of tik er vervolgens driemaal op.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Klik of tik in het dialoogvenster **Openen** op een afbeeldingsbestand en klik of tik vervolgens op **Openen**.
3. Voeg een besturingselement **[Knop](control-button.md)** toe, plaats deze onder het besturingselement **Afbeelding toevoegen** en stel vervolgens de eigenschap **[OnSelect](properties-core.md)** van het besturingselement **[Knop](control-button.md)** in op deze formule:<br>
   **Collect(MyPix, AddMediaButton1.Media)**
   
    Wilt u meer informatie over de functie **[Collect](../functions/function-clear-collect-clearcollect.md)** of [andere functies](../formula-reference.md)?
4. Voeg een besturingselement **Afbeeldingengalerie** toe en stel de eigenschap **[Items](properties-core.md)** van de galerie in op **MijnAfbeeldingen**.
5. Druk op F5 en klik of tik op het besturingselement **[Knop](control-button.md)**.
   
    De afbeelding uit het besturingselement **Afbeelding toevoegen** wordt weergegeven in het besturingselement **Afbeeldingengalerie**. Als de afbeelding een andere hoogte-breedteverhouding heeft dan het besturingselement **[Afbeelding](control-image.md)** in het besturingselement **Afbeeldingengalerie**, stelt u de eigenschap **[ImagePosition](properties-visual.md)** van het besturingselement **[Afbeelding](control-image.md)** in op **Passend**.
6. Klik of tik op het besturingselement **Afbeelding toevoegen**, klik of tik op een ander afbeeldingsbestand, klik of tik op **Openen** en klik of tik op het besturingselement **[Knop](control-button.md)** dat u hebt toegevoegd.
   
    De tweede afbeelding wordt weergegeven in het besturingselement **Afbeeldingengalerie**.
7. (Optioneel) Herhaal de vorige stap een of meer keren, en ga vervolgens terug naar de standaardwerkruimte door op Esc te drukken.

Gebruik de functie **[SaveData](../functions/function-savedata-loaddata.md)** om de afbeeldingen lokaal op te slaan of de functie **[Patch](../functions/function-patch.md)** om een gegevensbron bij te werken.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
Dezelfde richtlijnen voor **[Knop](control-button.md)** en **[Afbeelding](control-image.md)** zijn van toepassing. Bekijk bovendien de volgende scenario's:

### <a name="color-contrast"></a>Kleurcontrast
* **Knop Media toevoegen** moet voldoende contrast hebben tussen de tekst en de achtergrond. Omdat de geüploade afbeelding verschillende kleuren kan hebben, gebruikt u een ondoorzichtige **[Fill](properties-color-border.md)** op de **knop Media toevoegen** om te zorgen voor consistent contrast.

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **Knop Media toevoegen** moet **Text** en **ChangePictureText** bevatten, die de gebruiker vraagt een afbeelding toe te voegen of te wijzigen.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **Knop Media toevoegen** moet **[TabIndex](properties-accessibility.md)** nul of groter hebben, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* **Knop Media toevoegen** moet duidelijk zichtbare focusindicatoren hebben. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
 