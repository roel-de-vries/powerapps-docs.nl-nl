---
title: Een app maken op basis van een sjabloon | Microsoft Docs
description: Stapsgewijze instructies voor het automatisch maken van apps op basis van een sjabloon en deze vervolgens opslaan.
services: 
suite: powerapps
documentationcenter: na
author: linhtranms
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/03/2017
ms.author: karthikb
ms.openlocfilehash: 17214cf93b22973198b7d801ae95d159ef467d38
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="create-and-run-an-app-from-a-template"></a>Een app maken op basis van een sjabloon en deze uitvoeren
Maak automatisch een app voor een specifiek scenario op basis van een sjabloon en voer de app uit om het standaardgedrag ervan te begrijpen. Experimenteer met het aanpassen van een app, sla de app vervolgens op en deel deze.

**Vereisten**

* [Registreer u](signup-for-powerapps.md) voor PowerApps, [installeer](http://aka.ms/powerappsinstall) het, open het en meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.
  
    **Opmerking**: als u deze functie wilt gebruiken, zorg er dan voor dat u versie 2.0.510 of hoger uitvoert. Als u uw versie wilt identificeren, opent u het menu **Bestand** (aan de linkerkant), klikt of tikt u op **Account** en kijkt u onder **Product information**.
* Een account voor cloudopslag, zoals Dropbox, OneDrive of Google Drive.

## <a name="create-an-app"></a>Een app maken
1. Klik of tik vanuit PowerApps Studio voor Windows of PowerApps Studio voor internet op **Nieuw** (bij de linkerrand van het scherm).
   
    ![De optie Nieuw in het menu Bestand](./media/get-started-test-drive/file-new.png)
2. Klik of tik onder **App-sjablonen** op **Telefoonindeling**.
   
   **Opmerking**: u kunt ook een app voor tabletindelingen maken met een sjabloon, maar deze zelfstudie richt zich op apps voor telefoons.
   
   ![De optie om apps te maken voor tablets of telefoons](./media/get-started-test-drive/phone-app.png)
   
   Er verschijnt een lijst met sjablonen.
3. Als u geen verbinding hebt met een account voor cloudopslag:
   
   1. Klik of tik onder aan het scherm op **Kiezen**.
      
       ![De optie om verbinding te maken in een sjabloonweergave](./media/get-started-test-drive/add-connection.png)
   2. Klik of tik op het account dat u wilt gebruiken.
      
       ![Lijst met verbindingen om apps van sjablonen te maken](./media/get-started-test-drive/store-data.png)
   3. Geef uw referenties op en klik of tik vervolgens op **Gebruik** om toegang te verlenen.
      
       Uw verbinding wordt onder aan het scherm weergegeven.
4. Klik of tik in de lijst met sjablonen op een sjabloon en vervolgens op **Use** (rechtsonder).
   
    ![Een PowerApps-sjabloon openen](./media/get-started-test-drive/open-template.png)
   
    De voorbeeldgegevens worden gekopieerd naar het account voor de cloudopslag, de app wordt gemaakt en de startpagina voor de app verschijnt.

## <a name="run-the-app"></a>De app uitvoeren
Er wordt een app op basis van een sjabloon geopend in de standaardwerkruimte, waar u de meeste tijd bezig zult zijn met het aanpassen van de app. Volg, voordat u wijzigingen aanbrengt aan de app, de stappen in deze sectie om te ontdekken hoe de app werkt in de **previewmodus**.

**Tip:**ontwerp en ontwikkel apps in de standaardwerkruimte, maar test ze in de **previewmodus** voordat u ze met anderen deelt.

1. Volg de rondleiding (of klik of tik op **Overslaan**) als u nog niet eerder PowerApps hebt gebruikt.
   
    ![Scherm van de rondleiding openen](./media/get-started-test-drive/quick-tour.png)
   
    U kunt de rondleiding altijd later volgen door op het vraagtekenpictogram in de rechterbovenhoek te klikken of tikken en vervolgens op **Take the intro tour**.
2. Klik of tik in de linkernavigatiebalk op het bovenste scherm.
3. Druk op F5 (of klik of tik op de pijl-rechts in de rechterbovenhoek) om de app te openen in de **previewmodus**.
   
    ![Knop voor het openen van de previewmodus](./media/get-started-test-drive/open-preview.png)
   
    De app is vooraf gevuld met voorbeeldgegevens om de functionaliteit ervan te demonstreren. Zo bevat de app Kostenraming gegevens voor het maken van afspraken en het schatten van de kosten voor het installeren van een bepaalde vloer in een kamer van bepaalde afmetingen.
4. Ontdek het standaardgedrag van de app en controleer of de gegevens in uw cloudaccount uw wijzigingen volgen.
   
    Maak bijvoorbeeld een afspraak en een schatting van de kosten in de app Kostenraming.
5. Ga terug naar de standaardwerkruimte door in de rechterbovenhoek (onder de titelbalk van PowerApps) het pictogram met de **X** te selecteren.
   
    ![Knop voor het sluiten van de previewmodus](./media/get-started-test-drive/close-preview.png)

## <a name="customize-the-app"></a>De app aanpassen
U kunt deze of een andere app onder meer op deze manieren aanpassen:

* [de schermgrootte, stand of beide wijzigen](set-aspect-ratio-portrait-landscape.md)
* [een gegevensbron toevoegen](add-data-connection.md)
* [een of meer schermen toevoegen](add-screen-context-variables.md)
* [meer besturingselementen toevoegen en configureren](add-configure-controls.md)
* [het gedrag van de app wijzigen](working-with-formulas.md)

## <a name="next-steps"></a>Volgende stappen
1. Druk op Ctrl+S, geef de app een naam en klik of tik op **Opslaan** om de app in de cloud op te slaan.
2. [De app delen](share-app.md) met andere personen in de organisatie.
   
    **Opmerking**: zorg, voordat u een app deelt, dat de personen met wie u de app wilt delen, toegang hebben tot de gegevens. U moet bijvoorbeeld [een Excel- of ander bestand delen](share-app-data.md) in een account voor cloudopslag.

