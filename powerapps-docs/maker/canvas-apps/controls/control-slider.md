---
title: 'Besturingselement voor schuifregelaar: naslag | Microsoft Docs'
description: Informatie, waaronder eigenschappen en voorbeelden, over het besturingselement Schuifregelaar
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
ms.openlocfilehash: dc10ac44c1c14f182c39176a6b0216f3ede3816d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="slider-control-in-powerapps"></a>Besturingselement voor schuifregelaar in PowerApps
Een besturingselement waarmee de gebruiker een waarde kan opgeven door een schuifknop te slepen.

## <a name="description"></a>Beschrijving
De gebruiker kan een waarde kiezen, tussen een minimum- en maximumwaarde die u opgeeft, door het schuifblokje van de schuifregelaar naar links of rechts of omhoog of omlaag te slepen, afhankelijk van de richting die u kiest.

## <a name="key-properties"></a>Belangrijkste eigenschappen
**[Default](properties-core.md)**: de aanvankelijke waarde van een besturingselement voordat deze door de gebruiker wordt gewijzigd.

**Max**: de maximale waarde waarop de gebruiker een schuifregelaar of een waardering kan instellen.

**Min**: de minimale waarde waarop de gebruiker een schuifregelaar kan instellen.

**[Value](properties-core.md)**: de waarde van een besturingselement voor invoer.

## <a name="additional-properties"></a>Aanvullende eigenschappen
**[BorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement.

**[BorderStyle](properties-color-border.md)**: hiermee wordt aangegeven of de rand van een besturingselement **effen**, **onderbroken** of **gestippeld** is, of dat er **geen** rand is.

**[BorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement.

**[FocusedBorderThickness](properties-color-border.md)**: de dikte van de rand van een besturingselement wanneer deze de toetsenbordfocus heeft.

**[DisplayMode](properties-core.md)**: of invoer van de gebruiker is toegestaan (**Bewerken**), alleen gegevens worden weergegeven (**Weergeven**) of is uitgeschakeld (**Uitgeschakeld**).

**[DisabledBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement als de eigenschap **[DisplayMode](properties-core.md)** is ingesteld op **Uitgeschakeld**.

**HandleActiveFill**: de kleur van de schuifknop van een schuifregelaar als de gebruiker de waarde ervan verandert.

**HandleFill**: de kleur van de schuifknop (het element dat van positie verandert) van een wisselknop of schuifregelaar.

**HandleHoverFill**: de kleur van de schuifknop van een schuifregelaar wanneer de gebruiker de knop aanwijst.

**[Height](properties-size-location.md)** : de afstand tussen de boven- en onderrand van een besturingselement.

**[HoverBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker de muisaanwijzer op dat besturingselement plaatst.

**Layout**: bepaalt of de gebruiker door een galerie kan bladeren of een schuifregelaar moet verplaatsen; van boven naar beneden (**Verticaal**) of van links naar rechts (**Horizontaal**).

**[OnChange](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker de waarde van een besturingselement wijzigt (bijvoorbeeld door een schuifregelaar aan te passen).

**[OnSelect](properties-core.md)**: de manier waarop de app reageert wanneer de gebruiker op een besturingselement tikt of klikt.

**[PressedBorderColor](properties-color-border.md)**: de kleur van de rand van een besturingselement wanneer de gebruiker op dat besturingselement tikt of klikt.

**RailFill**: de achtergrondkleur van de rechthoek in een wisselknop als de waarde daarvan **false** is, of de kleur van de lijn, rechts van de schuifknop van een schuifregelaar.

**RailHoverFill**: als u de muis boven een wisselknop of schuifregelaar houdt, is dit de achtergrondkleur van de rechthoek in een wisselknop als de waarde daarvan **false** is, of de kleur van de lijn, rechts van de schuifknop van een schuifregelaar.

**ReadOnly**: bepaalt of een gebruiker de waarde van een schuifregelaar of besturingselement voor waardering mag wijzigen.

**[Reset](properties-core.md)**: of een besturingselement wordt teruggezet op de standaardwaarde.

**ShowValue**: bepaalt of de waarde van een schuifregelaar of waardering wordt weergegeven wanneer de gebruiker die waarde verandert of het besturingselement aanwijst.

**[TabIndex](properties-accessibility.md)**: past de tabvolgorde van besturingselementen tijdens runtime aan wanneer hier een andere waarde dan nul is ingesteld.

**[Tooltip](properties-core.md)**: beschrijvende tekst die wordt weergegeven wanneer de gebruiker een besturingselement aanwijst.

**ValueFill**: de achtergrondkleur van de rechthoek in een wisselknop als de waarde daarvan **true** is, of de kleur van de lijn, links van de schuifknop van een schuifregelaar.

**ValueHoverFill**: als u de muisaanwijzer boven een wisselknop of schuifregelaar houdt, is dit de achtergrondkleur van de rechthoek in een wisselknop als de waarde daarvan **true** is, of de kleur van de lijn, links van de schuifknop van een schuifregelaar.

**[Visible](properties-core.md)**: hiermee wordt aangegeven of een besturingselement zichtbaar of verborgen is.

**[Width](properties-size-location.md)**: de afstand tussen de linker- en rechterrand van een besturingselement.

**[X](properties-size-location.md)**: de afstand tussen de linkerrand van een besturingselement en de linkerrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

**[Y](properties-size-location.md)**: de afstand tussen de bovenrand van een besturingselement en de bovenrand van de bovenliggende container (het scherm als er geen bovenliggende container is).

## <a name="related-functions"></a>Verwante functies
[**Sum**( *Waarde1*, *Waarde2* )](../functions/function-aggregates.md)

## <a name="example"></a>Voorbeeld
1. Voeg een knop toe en stel de eigenschap **[BijSelecteren](properties-core.md)** ervan in op deze formule:
   <br>**ClearCollect(Inwonersaantallen, {Stad:"Londen", Land:"Engeland", Inwonersaantal:8615000}, {Stad:"Berlijn", Land:"Duitsland", Inwonersaantal:3562000}, {Stad:"Madrid", Land:"Spanje", Inwonersaantal:3165000}, {Stad:"Rome", Land:"Italië", Inwonersaantal:2874000}, {Stad:"Parijs", Land:"Frankrijk", Inwonersaantal:2273000}, {Stad:"Hamburg", Land:"Duitsland", Inwonersaantal:1760000}, {Stad:"Barcelona", Land:"Spanje", Inwonersaantal:1602000}, {Stad:"München", Land:"Duitsland", Inwonersaantal:1494000}, {Stad:"Milaan", Land:"Italië", Inwonersaantal:1344000})**
   
    Weet u niet hoe u [een besturingselement kunt toevoegen, een naam kunt geven of kunt configureren](../add-configure-controls.md)?
   
    Wilt u meer informatie over de functie **[ClearCollect](../functions/function-clear-collect-clearcollect.md)** of een [andere functie](../formula-reference.md)?
2. Druk op F5, selecteer de knop en druk op Esc.
3. Voeg een schuifregelaar toe, plaats deze onder de knop en geef het besturingselement de naam **MinsteAantalInwoners**.
4. Stel de eigenschap **Max** van de schuifregelaar in op **5000000** en de eigenschap **Min** op **1000000**.
5. Voeg een tekstgalerie toe met de richting verticaal/staand, plaats deze onder de schuifregelaar en stel de eigenschap **[Items](properties-core.md)** van de galerie in op deze formule:<br>
   **Filter(CityPopulations, Population > MinPopulation)**
6. Stel in het eerste item van de galerie de eigenschap **[Text](properties-core.md)** van het bovenste label in op **ThisItem.Stad** en de eigenschap **[Text](properties-core.md)** van het onderste label in op deze formule:<br> **Text(ThisItem.Inwonersaantal, "##,###")**
7. Druk op F5 en pas vervolgens **MinsteAantalInwoners** aan om alleen die steden weer te geven met meer inwoners dan de waarde die u opgeeft.
8. Druk op Esc om terug te gaan naar de standaardwerkruimte.

