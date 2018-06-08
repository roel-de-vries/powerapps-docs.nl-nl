---
title: 'Besturingselement voor kolom: naslag | Microsoft Docs'
description: Dit onderwerp bevat informatie over het besturingselement Kolom in Microsoft PowerApps.
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 06/05/2017
ms.author: kfend
ms.openlocfilehash: e79314b8e615a931a3ba8116a53b216afe5d145a
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31826035"
---
# <a name="column-control-in-powerapps"></a>Besturingselement Kolom in PowerApps
Dit besturingselement biedt de weergave-ervaring voor één veld in een besturingselement [**Gegevenstabel**](control-data-table.md).

## <a name="description"></a>Beschrijving
Het besturingselement [**Gegevenstabel**](control-data-table.md) toont een gegevensset in tabelvorm, en elke kolom in deze tabelvorm wordt vertegenwoordigd door een besturingselement **Kolom**. Het besturingselement **Kolom** heeft eigenschappen waarmee de maker van de app het uiterlijk en het gedrag van de kolom kan aanpassen.

## <a name="capabilities"></a>Functionaliteit
### <a name="now-available"></a>Nu verkrijgbaar
* De breedte van een besturingselement **Kolom** wijzigen.
* De tekst voor een besturingselement **Kolom** wijzigen.
* Navigeer door te klikken of te tikken op de waarde in een besturingselement **Kolom**.

### <a name="not-yet-available"></a>Nog niet beschikbaar
* De stijl van een besturingselement **Kolom** aanpassen.

### <a name="known-issues"></a>Bekende problemen
* De eigenschap **Visible** werkt nog niet.

## <a name="properties"></a>Eigenschappen
* **DisplayName**: de tekst die wordt weergegeven in de koptekst voor de kolom.
  
  > [!NOTE]
  > De naam van deze eigenschap wordt binnenkort gewijzigd in **HeaderText**.
  > 
  > 
* **Is hyperlink** : een waarde die bepaalt of de gegevens in de kolom moeten worden onderstreept om aan te geven dat het een hyperlink is.
* [**Width**](properties-size-location.md): de afstand tussen de linker- en rechterrand van het besturingselement **Kolom**.

## <a name="examples"></a>Voorbeelden
### <a name="resize-a-column"></a>Formaat van een kolom wijzigen
1. Maak een lege tablet-app.
2. Klik of tik op het tabblad **Invoegen** op **Gegevenstabel** en wijzig vervolgens het formaat van het besturingselement **Gegevenstabel**, zodat de tabel het volledige scherm vult.
3. Klik of tik in het rechterdeelvenster op het pijl-omlaag naast de tekst **Er is geen gegevensbron geselecteerd** en klik of tik vervolgens op **Een gegevensbron toevoegen**.
4. Klik of tik in de lijst met verbindingen op de verbinding voor de database Common Data Service.
5. Klik of tik in de lijst met entiteiten op **Account** en klik of tik vervolgens op **Verbinding maken**.
   
    Het besturingselement **Gegevenstabel** wordt geïnitialiseerd en er wordt een reeks standaardvelden weergegeven.
6. Klik of tik op de kolom **Volledige naam**.
   
    ![Het besturingselement Kolom geselecteerd](./media/control-column/pre-resize-column.png)
7. Sleep de hoek aan de rechterkant om de grootte van het veld aan te passen.
   
    ![Formaat van het besturingselement Kolom wijzigen](./media/control-column/post-resize-column.png)


## <a name="accessibility-guidelines"></a>Richtlijnen voor toegankelijkheid
### <a name="screen-reader-support"></a>Ondersteuning voor schermlezers
* **DisplayName** moet aanwezig zijn.
