---
title: 'Besturingselement voor tekstinvoer: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Tekstinvoer
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: fikaradz
ms.openlocfilehash: 7f78cc61b4e6af34af7bf6944e70e783872bc255
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37897496"
---
# <a name="text-input-control-in-powerapps"></a>Besturingselement voor tekstinvoer in PowerApps
Een vak waarin de gebruiker tekst, cijfers en andere gegevens kan typen.

## <a name="description"></a>Beschrijving
De gebruiker kan gegevens opgeven door te typen in een besturingselement voor tekstinvoer. Afhankelijk van hoe u de app configureert, worden die gegevens toegevoegd aan een gegevensbron, gebruikt om een tijdelijke waarde te berekenen of op een andere manier verwerkt.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Default](properties-core.md)**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

**[Text](properties-core.md)**: de tekst die wordt weergegeven in een besturingselement of die de gebruiker in een besturingselement typt.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[AccessibleLabel](properties-accessibility.md)**: label voor schermlezers.

**[Align](properties-text.md)**: de locatie van tekst in verhouding tot het horizontale midden van het besturingselement.

**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**Clear**: bepaalt of het besturingselement voor tekstinvoer een 'X' bevat waarop de gebruiker kan tikken of klikken om de inhoud van dat besturingselement te wissen.

**[Color](properties-color-border.md)**: de kleur van de tekst in een besturingselement.

**DelayOutput**: als deze eigenschap is ingesteld op true, wordt de gebruikersinvoer na een vertraging van een halve seconde geregistreerd.  Dit is handig voor het uitstellen van tijdrovende bewerkingen totdat een gebruiker klaar is met het invoeren van tekst (om te filteren als invoer wordt gebruikt in andere formules).

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledColor](properties-color-border.md)**: de kleur van tekst in een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[DisabledFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**[Fill](properties-color-border.md)**: de achtergrondkleur van een besturingselement.

**[FocusedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer de focus op het besturingselement is.

**[Font](properties-text.md)**: de naam van de lettertypefamilie waarin de tekst wordt weergegeven.

**[FontWeight](properties-text.md)**: het gewicht van de tekst in een besturingselement: **Bold**, **Semibold**, **Normal** of **Lighter**.

**Indeling**: of de gebruikersinvoer is beperkt tot alleen getallen of dat tekst mogelijk is.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**HintText**: lichtgrijze tekst die in een besturingselement voor tekstinvoer wordt weergegeven als dit leeg is.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**[HoverColor](properties-color-border.md)**: de kleur van de tekst in een besturingselement wanneer de gebruiker de muisaanwijzer op de tekst plaatst.

**[HoverFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker de muisaanwijzer op de achtergrond plaatst.

**[Italic](properties-text.md)**: hiermee wordt aangegeven of de tekst in een besturingselement cursief is.

**[LineHeight](properties-text.md)**: de afstand tussen bijvoorbeeld regels tekst of items in een lijst.

**MaxLength**: het aantal tekens dat de gebruiker in een besturingselement voor tekstinvoer kan typen.

**Mode**: het besturingselement staat in de modus **SingleLine**, **MultiLine** of **Password**.

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PaddingBottom](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de onderrand van het besturingselement.

**[PaddingLeft](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de linkerrand van het besturingselement.

**[PaddingRight](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de rechterrand van het besturingselement.

**[PaddingTop](properties-size-location.md)**: de afstand tussen de tekst in een besturingselement en de bovenrand van het besturingselement.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedColor](properties-color-border.md)**: de kleur van tekst in een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[PressedFill](properties-color-border.md)**: de achtergrondkleur van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**[RadiusBottomLeft](properties-size-location.md)**: de mate van afronding van de linkerbenedenhoek van een besturingselement.

**[RadiusBottomRight](properties-size-location.md)**: de mate van afronding van de rechterbenedenhoek van een besturingselement.

**[RadiusTopLeft](properties-size-location.md)**: de mate van afronding van de linkerbovenhoek van een besturingselement.

**[RadiusTopRight](properties-size-location.md)**: de mate van afronding van de rechterbovenhoek van een besturingselement.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

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
[**DateTimeValue**( *Tekenreeks* )](../functions/function-datevalue-timevalue.md)

## <a name="examples"></a>Voorbeelden
### <a name="collect-data"></a>Gegevens verzamelen
1. Voeg twee besturingselementen voor tekstinvoer toe en noem ze **inputFirst** en **inputLast**.
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
2. Voeg een knop toe, stel de eigenschap **[Text](properties-core.md)** van de knop in op **Toevoegen** en de eigenschap **[OnSelect](properties-core.md)** op deze formule:<br>
   **Collect(Names, {FirstName:inputFirst.Text, LastName:inputLast.Text})**
   
    Wilt u meer informatie over de functie **[Collect](../functions/function-clear-collect-clearcollect.md)** of [andere functies](../formula-reference.md)?
3. Voeg een tekstgalerie toe in de afdrukstand staand/verticaal, stel de eigenschap **[Items](properties-core.md)** van de galerie in op **Namen** en stel de eigenschap **[Text](properties-core.md)** van **Subtitel1** in op **ThisItem.FirstName**.
4. (Optioneel) Verwijder in de galerie met sjablonen het onderste label met de naam **Hoofdtekst1** en stel de eigenschap **[TemplateSize](control-gallery.md)** van de galerie in op **80**.
5. Druk op F5, typ een tekenreeks in **inputFirst** en **inputLast**, en klik of tik op de knop **Toevoegen**.
6. (Optioneel) Voeg meer namen toe aan de verzameling en druk vervolgens op Esc om terug te keren naar de standaardwerkruimte.

### <a name="prompt-for-a-password"></a>Vragen om een wachtwoord

1. Voeg een besturingselement voor tekstinvoer toe, geef het de naam **inputPassword** en stel de eigenschap **Mode** in op **Wachtwoord**.

1. Voeg een label toe en stel de eigenschap **[Text](properties-core.md)** in op deze formule:<br>
   **If(inputPassword.Text = "P@ssw0rd", "Access granted", "Access denied")**

    Wilt u meer informatie over de functie **[If](../functions/function-if.md)** of [andere functies](../formula-reference.md)?

1. Druk op F5 en typ vervolgens **P@ssw0rd** bij **inputPassword**.

    Wanneer u klaar bent met het typen van het wachtwoord, wordt in plaats van de tekst **Toegang geweigerd** de tekst **Toegang verleend** weergegeven.

1. Druk op Esc om terug te gaan naar de standaardwerkruimte.

1. (Optioneel) Voeg een besturingselement zoals een pijl toe, configureer dit om te navigeren naar een ander scherm en geef de pijl pas weer nadat de gebruiker het wachtwoord heeft ingevoerd.

1. (Optioneel) Voeg een knop toe, configureer de eigenschap **[Text](properties-core.md)** van de knop voor het weergeven van **Aanmelden**, voeg een timer toe en schakel het besturingselement voor tekstinvoer gedurende een bepaalde tijd uit als de gebruiker het verkeerde wachtwoord typt en vervolgens op de knop **Aanmelden** klikt of tikt.


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="color-contrast"></a>Kleurcontrast
* [De standaardvereisten voor kleurcontrast](../accessible-apps-color.md) zijn van toepassing.

### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **[AccessibleLabel](properties-accessibility.md)** moet aanwezig zijn.

### <a name="keyboard-support"></a>Ondersteuning voor toetsenbord
* **[TabIndex](properties-accessibility.md)** moet nul of groter zijn, zodat toetsenbordgebruikers ernaartoe kunnen navigeren.
* De focusindicatoren moeten duidelijk zichtbaar zijn. Gebruik hiervoor **[FocusedBorderColor](properties-color-border.md)** en **[FocusedBorderThickness](properties-color-border.md)**.
 