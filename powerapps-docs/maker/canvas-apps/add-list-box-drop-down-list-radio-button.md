---
title: Een keuzelijst, een vervolgkeuzelijst of keuzerondjes toevoegen aan een canvas-app | Microsoft Docs
description: In PowerApps opties voor meervoudige selectie in een canvas-app maken of configureren
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/24/2018
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 293c850c5af980a480a56cb9fb3b8c7866950580
ms.sourcegitcommit: 097ddfb25eb0f09f0229b866668c2b02fa57df55
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2018
ms.locfileid: "49991741"
---
# <a name="add-a-list-box-a-drop-down-list-or-radio-buttons-to-a-canvas-app"></a>Een keuzelijst, een vervolgkeuzelijst of keuzerondjes toevoegen aan een canvas-app

Geef één kolom met gegevens (bijvoorbeeld uit een tabel met meerdere kolommen) weer in een canvas-app, zodat gebruikers een of meer items uit een lijst kunnen selecteren.

- Voeg een keuzelijst toe, zodat gebruikers meer dan één optie kunnen kiezen.
- Voeg een vervolgkeuzelijst toe die minder ruimte op het scherm inneemt.
- Voeg een set keuzerondjes toe voor een bepaald ontwerpeffect.

In dit onderwerp worden keuzelijsten en keuzerondjes besproken, maar dezelfde principes zijn van toepassing op vervolgkeuzelijsten.

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="create-a-simple-list"></a>Een voorbeeldlijst maken

1. Voeg een besturingselement **Keuzelijst** toe met de naam **MyListBox** en stel de eigenschap **Items** in op deze expressie:

    ```["circle","triangle","rectangle"]```  <br/>

    Uw ontwerp ziet er ongeveer als volgt uit:

    ![][4]

4. Op het tabblad **Invoegen** selecteert u **Pictogrammen** en vervolgens de cirkel. Verplaats deze naar onder **MyListBox**:

    ![][5]  

5. Voeg een driehoek en een rechthoek toe en plaats de vormen in een rij onder **MyListBox**:

    ![][6]  

6. Stel de eigenschap **[Visible](controls/properties-core.md)** van de volgende vormen in op de volgende functies:  

   | Vorm | Stel de functie Visible in op |
   | --- | --- |
   | cirkel |```If("circle" in MyListBox.SelectedItems.Value, true)``` |
   | driehoek |```If("triangle" in MyListBox.SelectedItems.Value, true)``` |
   | rechthoek |```If("rectangle" in MyListBox.SelectedItems.Value, true)``` |

7. Selecteer een of meer vormen in **MyListBox** terwijl u de Alt-toets ingedrukt houdt.

    Alleen de vorm of vormen die u selecteert worden weergegeven.

Tijdens deze stappen hebt u gebruikgemaakt van een expressie om een lijst met items te maken. U kunt dit toepassen op andere elementen binnen uw bedrijf. U kunt bijvoorbeeld het besturingselement **Vervolgkeuzelijst** gebruiken om productafbeeldingen, productbeschrijvingen e.d. weer te geven.

## <a name="add-radio-buttons"></a>Keuzerondjes toevoegen
1. Selecteer op het tabblad **Start** de optie **Nieuw scherm** en selecteer vervolgens **Leeg**.

2. Selecteer op het tabblad **Invoegen** de optie **Besturingselementen** en selecteer vervolgens **Keuzerondje**.

    ![][10]  

3. Wijzig de naam van het besturingselement **Keuzerondje** in **Choices** en stel de eigenschap **[Items](controls/properties-core.md)** in op deze formule:  
   ```["red","green","blue"]```  <br/>

    ![][12]  

    Indien nodig wijzigt u het formaat van het besturingselement zodat alle opties worden weergegeven.

4. Selecteer op het tabblad **Invoegen** de optie **Pictogrammen** en selecteer de cirkel.

5. Stel de eigenschap **[Fill](controls/properties-color-border.md)** van de cirkel in op de volgende functie:  
   ```If(Choices.Selected.Value = "red", Red, Choices.Selected.Value = "green", Green, Choices.Selected.Value = "blue", Blue)```  

    Met deze formule verandert de kleur van de cirkel op basis van welk keuzerondje u selecteert.

6. Plaats de cirkel onder het besturingselement **Keuzerondje**, zoals in dit voorbeeld:

    ![][14]  

7. Selecteer een ander keuzerondje terwijl u de Alt-toets ingedrukt houdt om de kleur van de cirkel te wijzigen.

[1]: ./media/add-list-box-drop-down-list-radio-button/preview.png
[2]: ./media/add-list-box-drop-down-list-radio-button/listbox.png
[3]: ./media/add-list-box-drop-down-list-radio-button/renamelistbox.png
[4]: ./media/add-list-box-drop-down-list-radio-button/itemslistbox.png
[5]: ./media/add-list-box-drop-down-list-radio-button/circle.png
[6]: ./media/add-list-box-drop-down-list-radio-button/allshapes.png
[10]: ./media/add-list-box-drop-down-list-radio-button/radiobutton.png
[12]: ./media/add-list-box-drop-down-list-radio-button/itemsradio.png
[14]: ./media/add-list-box-drop-down-list-radio-button/radiocircle.png
[15]: ./media/add-list-box-drop-down-list-radio-button/dropdown.png
