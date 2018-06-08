---
title: Een scherm toevoegen en tussen schermen navigeren | Microsoft Docs
description: Een scherm toevoegen aan een app en de pijlen Vorige en Volgende gebruiken om in PowerApps tussen schermen te navigeren
documentationcenter: na
author: aftowen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 07/10/2017
ms.author: anneta
ms.openlocfilehash: 19c06fa9bfc7098227e5f30a1c913522d9e6e7a3
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825252"
---
# <a name="add-a-screen-and-navigate-between-screens"></a>Een scherm toevoegen en tussen schermen navigeren
Maak een app met meerdere schermen en voeg manieren toe waarop gebruikers ertussen kunnen navigeren.

## <a name="prerequisites"></a>Vereisten
* Lees hoe u [een besturingselement kunt configureren](add-configure-controls.md).
* Maak of open een app.

## <a name="add-and-rename-a-screen"></a>Een scherm toevoegen en de naam wijzigen
1. Op het tabblad **Startpagina** klikt of tikt u op **Nieuw scherm**.

    ![De optie Scherm toevoegen op het tabblad Startpagina](./media/add-screen-context-variables/add-screen.png)

2. Klik of tik in het rechterdeelvenster op de naam van het scherm (boven het tabblad **Eigenschappen**) en typ vervolgens de nieuwe naam **Bron**.

    ![De naam van het standaardscherm wijzigen](./media/add-screen-context-variables/name-source-screen.png)

3. Voeg nog een scherm toe en noem het **Target**.

    ![Twee schermen in de navigatiebalk links](./media/add-screen-context-variables/two-screens-in-nav.png)

## <a name="add-navigation"></a>Navigatie toevoegen
1. Wanneer het scherm **Source** is geopend, opent u het tabblad **Invoegen** en klikt of tikt u op **Pictogrammen**. Klik of tik vervolgens op de **pijl Volgende**.  

    ![De optie Vormen op het tabblad Invoegen](./media/add-screen-context-variables/add-next-arrow.png)

2. (optioneel) Verplaats de pijl zodat deze in de rechterbenedenhoek van het scherm wordt weergegeven.

3. Nu de pijl nog is geselecteerd, klikt of tikt u op het tabblad **Actie** en klikt of tikt u op **Navigate**.

    De eigenschap **[OnSelect](controls/properties-core.md)** van de pijl wordt automatisch ingesteld op de functie **Navigate**.  

    ![De eigenschap OnSelect ingesteld op de functie Navigate](./media/add-screen-context-variables/onselect-default.png)

    Wanneer een gebruiker op de pijl klikt of tikt, wordt het scherm **Target** geopend.

4. Op het scherm **Target** voegt u de **pijl Vorige** toe en stelt u de eigenschap **[OnSelect](controls/properties-core.md)** in op deze formule:
   <br>**Navigate(Bron, Schermovergang.Fade)**

5. Open de preview-modus (![](./media/add-screen-context-variables/preview.png) of druk op F5) en schakel tussen de schermen door op de toegevoegde pijlen te klikken of tikken.

6. Druk op **ESC** om terug te gaan naar de standaardwerkruimte.
