---
title: Een keuzelijst, een vervolgkeuzelijst en keuzerondjes toevoegen aan een canvas-app | Microsoft Docs
description: In PowerApps opties voor meervoudige selectie in een canvas-app maken of configureren
author: lonu
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/23/2016
ms.author: lonu
ms.openlocfilehash: b4988157a8f194f7b1148cff79de1b5ce44add14
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/02/2018
ms.locfileid: "39471024"
---
# <a name="add-a-list-box-a-drop-down-list-or-radio-buttons-to-a-canvas-app-in-powerapps"></a>In PowerApps een keuzelijst, een vervolgkeuzelijst of keuzerondjes toevoegen aan een canvas-app

PowerApps bevat opties voor meervoudige en enkelvoudige selectie voor canvas-apps, zoals keuzelijsten, vervolgkeuzelijsten en keuzerondjes. In dit onderwerp worden deze besturingselementen toegevoegd en wordt de formule **Table** gebruikt om de lijsten te creëren. Wanneer een item in de lijst wordt geselecteerd, worden de andere besturingselementen bijgewerkt.

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="add-a-list-box"></a>Een keuzelijst toevoegen

1. Selecteer op het tabblad **Invoegen** de optie **Besturingselementen** en selecteer vervolgens **Keuzelijst**:  

    ![][2]  

2. Wijzig de naam van het besturingselement **Keuzelijst** in **MyListBox**:  

    ![][3]

3. Stel de eigenschap **[Items](controls/properties-core.md)** in op de volgende expressie:  
   ```["circle","triangle","rectangle"]```  <br/>

    Uw ontwerp ziet er ongeveer als volgt uit:

    ![][4]

4. Op het tabblad **Invoegen** selecteert u **Pictogrammen** en vervolgens de cirkel. Verplaats deze naar onder het besturingselement **Keuzelijst**:

    ![][5]  

5. Voeg een driehoek en een rechthoek toe en plaats de vormen in een rij onder het besturingselement **Keuzelijst**:

    ![][6]  

6. Stel de eigenschap **[Visible](controls/properties-core.md)** van de volgende vormen in op de volgende functies:  

   | Vorm | Stel de functie Visible in op |
   | --- | --- |
   | cirkel |```If("circle" in MyListBox.SelectedItems.Value, true)``` |
   | driehoek |```If("triangle" in MyListBox.SelectedItems.Value, true)``` |
   | rechthoek |```If("rectangle" in MyListBox.SelectedItems.Value, true)``` |

7. Bekijk een voorbeeld van wat u hebt gemaakt: ![][1]. Selecteer de verschillende vormen in het besturingselement **Keuzelijst**. Alleen de vorm of vormen die u selecteert worden weergegeven. Druk op ESC of selecteer **X** om terug te keren naar uw scherm.

Tijdens deze stappen hebt u gebruikgemaakt van een expressie om een lijst items te maken in het besturingselement **Keuzelijst**. Afhankelijk van wat u hebt gekozen in het besturingselement **Keuzelijst** worden er verschillende vormen weergegeven. U kunt dit toepassen op andere elementen binnen uw bedrijf. U kunt bijvoorbeeld het besturingselement **Keuzelijst** gebruiken om productafbeeldingen, productbeschrijvingen e.d. weer te geven.

## <a name="add-radio-buttons"></a>Keuzerondjes toevoegen
1. Selecteer op het tabblad **Startpagina** de optie **Nieuw scherm**.

2. Selecteer op het tabblad **Invoegen** de optie **Besturingselementen** en selecteer vervolgens **Keuzerondje**.

    ![][10]  

3. Wijzig de naam van het besturingselement **Keuzerondje** in **Choices** en stel de eigenschap **[Items](controls/properties-core.md)** in op deze formule:  
   ```["red","green","blue"]```  <br/>

    ![][12]  

    Indien nodig wijzigt u het formaat van het besturingselement zodat alle opties worden weergegeven.

4. Selecteer op het tabblad **Invoegen** de optie **Pictogrammen** en selecteer de cirkel.

5. Stel de eigenschap **[Fill](controls/properties-color-border.md)** van de cirkel in op de volgende functie:  
   ```If(Choices.Selected.Value = "red", RGBA(192, 0, 0, 1), Choices.Selected.Value = "green", RGBA(0, 176, 80, 1), Choices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```  

    Met deze formule verandert de kleur van de cirkel op basis van welk keuzerondje u selecteert.

6. Plaats de cirkel onder het besturingselement **Keuzerondje**, zoals in dit voorbeeld:

    ![][14]  

7. Bekijk een voorbeeld van wat u hebt gemaakt: ![][1]. Selecteer een ander keuzerondje om de kleur van de cirkel te wijzigen. Druk op ESC of selecteer **X** om terug te keren naar uw scherm.

## <a name="add-a-drop-down-list"></a>Een vervolgkeuzelijst toevoegen
1. Voeg een scherm toe en voeg dan het besturingselement **Vervolgkeuzelijst** toe.

    ![][15]  

2. Wijzig de naam van het besturingselement naar **DDChoices** en stel de eigenschap **[Items](controls/properties-core.md)** in op deze formule:<br>
   **["rood","groen","blauw"]**

3. Voeg een cirkel toe, plaats deze onder het besturingselement **Vervolgkeuzelijst** en stel de eigenschap **[Fill](controls/properties-color-border.md)** van de cirkel in op deze formule:  
   ```If(DDChoices.Selected.Value = "red", RGBA(192, 0, 0, 1), DDChoices.Selected.Value = "green", RGBA(0, 176, 80, 1), DDChoices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```

4. Bekijk een voorbeeld van wat u hebt gemaakt: ![][1]. Selecteer de verschillende opties om de kleur van de cirkel te wijzigen.

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
