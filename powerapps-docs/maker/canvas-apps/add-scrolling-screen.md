---
title: Een scrollscherm toevoegen | Microsoft Docs
description: Maak een scherm waardoor gebruikers kunnen scrollen om meer soorten inhoud te bekijken dan in één keer in het scherm kunnen worden weergegeven.
author: lonu
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: lonu
ms.openlocfilehash: 4a8b92e012f9669f2b445ef864d3360ef42fbc01
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015979"
---
# <a name="add-a-scrolling-screen-in-powerapps"></a>Een scrollscherm toevoegen in PowerApps
Maak een scherm waardoor gebruikers kunnen scrollen om verschillende items te bekijken. Mogelijk wilt u bijvoorbeeld een app maken om gegevens in een kolomdiagram en lijndiagram weer te geven. Als u een scrollscherm toevoegt, kunt u meerdere besturingselementen toevoegen die gebruikers kunnen bekijken door te scrollen.

Als u meerdere besturingselementen in een sectie toevoegt, behouden de besturingselementen hun relatieve positie binnen die sectie, ongeacht of het om een telefoon-app of een tablet-app gaat. Het schermformaat en de weergaverichting kunnen doorslaggevend zijn bij het bepalen hoe secties worden ingedeeld.  

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="create-a-scrolling-screen"></a>Een scrollscherm maken
1. Op het tabblad **Startpagina** klikt of tikt u op **Nieuw scherm**:
   
    ![Optie om een scherm aan een app toe te voegen][1]
2. Op het tabblad **Startpagina** klikt of tikt u op **Indelingen** en klikt of tikt u op de optie om een oneindig scrollcanvas toe te voegen:  
   
    ![Optie om een oneindig scrollcanvas toe te voegen][2]
   
    Het canvas wordt toegevoegd:  
   
    ![Een scherm met een oneindig scrollcanvas, zoals het standaard wordt weergegeven][3]

## <a name="add-elements"></a>Elementen toevoegen
U gaat nu enkele besturingselementen toevoegen aan het canvas om te bekijken hoe het scrollscherm werkt.

1. In het canvas dat u hebt toegevoegd, klikt of tikt u op **Een item toevoegen van het tabblad Invoegen**.
   
    ![][4]
2. Klik of tik op het tabblad **Invoegen** op **Diagrammen** en klik of tik vervolgens op **Kolomdiagram**.
   
    ![De optie om een kolomdiagram toe te voegen][5]
   
    Er wordt op de eerste kaart op het scherm een kolomdiagram weergegeven:  
   
    ![Standaardkolomdiagram][7]
3. Klik of tik op het tabblad **Invoegen** op **Tekst** en klik of tik vervolgens op **Peninvoer**:  
   
    ![Optie voor het toevoegen van een penbesturingselement][8]
4. Plaats het penbesturingselement onder het diagram en wijzig de grootte ervan zodat de onderkant van de kaart wordt bedekt:  
   
    ![Het penbesturingselement verplaatsen en de grootte ervan wijzigen][9]

## <a name="add-a-section"></a>Een sectie toevoegen
U gaat nu een andere kaart toevoegen met een ander besturingselement.

1. Klik of tik onder aan het scherm op **Sectie toevoegen**:  
   
    ![Optie voor het toevoegen van een sectie][10]
   
    Er wordt een nieuwe kaart toegevoegd aan het scherm:  
   
    ![Een nieuwe kaart onder de standaardsectie][11]
2. Nu de kaart nog steeds is geselecteerd, gaat u naar het tabblad **Invoegen**, klikt of tikt u op **Diagrammen** en klikt of tikt u op **Lijndiagram**.
   
    Het nieuwe diagram is te groot om weer te geven op het scherm met de andere besturingselementen:  
   
    ![Een lijndiagram toegevoegd onder de nieuwe kaart][12]
3. Open de previewmodus door op F5 te drukken (of door op het pictogram voor afspelen in de rechterbovenhoek te klikken of tikken).
   
    ![Preview-modus openen](./media/add-scrolling-screen/open-preview.png)
4. Scroll omlaag om het nieuwe lijndiagram weer te geven.  
   
    ![In de preview wordt het lijndiagram weergegeven][13]

[1]: ./media/add-scrolling-screen/add-screen.png
[2]: ./media/add-scrolling-screen/add-canvas.png
[3]: ./media/add-scrolling-screen/default-canvas.png
[4]: ./media/add-scrolling-screen/insert-visual.png
[5]: ./media/add-scrolling-screen/add-chart.png
[7]: ./media/add-scrolling-screen/default-chart.png
[8]: ./media/add-scrolling-screen/add-pen.png
[9]: ./media/add-scrolling-screen/move-resize-pen.png
[10]: ./media/add-scrolling-screen/add-section.png
[11]: ./media/add-scrolling-screen/new-card.png
[12]: ./media/add-scrolling-screen/add-line-chart.png
[13]: ./media/add-scrolling-screen/line-chart-preview.png
