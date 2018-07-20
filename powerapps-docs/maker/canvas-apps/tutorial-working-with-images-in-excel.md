---
title: Afbeeldingen opslaan in een Excel-bestand | Microsoft Docs
description: Afbeeldingen opslaan in een Excel-tabel in een cloudopslagaccount
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/15/2016
ms.author: anneta
ms.openlocfilehash: 5c84da8bb0873fd42f5d352ae463f013113d8fcd
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023868"
---
# <a name="how-to-save-images-in-an-excel-file-and-then-add-these-images-to-your-app"></a>Afbeeldingen in een Excel-bestand opslaan en deze afbeeldingen vervolgens toevoegen aan uw app

In deze zelfstudie worden de volgende punten besproken:

* Een Excel-bestand maken en opmaken als tabel
* Een verbinding met OneDrive voor Bedrijven maken. Dit is mogelijk met ieder soort cloudopslagaccount. In deze zelfstudie wordt OneDrive voor Bedrijven gebruikt.
* Een app maken met een besturingselement voor pen-invoer
* Afbeeldingen gemaakt met behulp van het besturingselement voor pen-invoer opslaan in een Excel-bestand
* Afbeeldingen uit een Excel-bestand weergeven in uw app

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]
* Leer hoe u [een gegevensbron kunt toevoegen](add-data-connection.md)

## <a name="create-the-excel-file-as-a-table"></a>Een Excel-bestand als tabel maken

1. Geef een kolom in een leeg Excel-bestand de naam **Image [image]**.
2. Volg de volgende stappen om een tabel te maken:    
   
   1. Selecteer een gegevenselement in een willekeurige rij en kolom. Selecteer bijvoorbeeld **Image**.
   2. Selecteer **Tabel** op het lintmenu **Invoegen**.
   3. Selecteer in het dialoogvenster **Mijn tabel bevat veldnamen** en selecteer **OK**.
      
      Uw Excel-bestand is nu opgemaakt als tabel. [De opmaak van een Excel-tabel wijzigen](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370) biedt extra informatie over de tabelopmaak in Excel.
   4. Noem de tabel **Drawings**:  
      
      ![De naam van de tabel wijzigen naar Drawings](./media/tutorial-working-with-images-in-excel/drawings-table.png)
3. Noem het Excel-bestand **SavePen.xlsx** en sla het bestand op in uw cloudopslagaccount (OneDrive voor Bedrijven, Dropbox, etc.).

## <a name="create-an-app-with-the-pen-control"></a>Een app maken met het penbesturingselement
1. Maak in PowerApps een [lege app](get-started-create-from-blank.md).
2. Voeg het cloudopslagaccount in uw app toe als een [gegevensbron](add-data-connection.md). Nadat u het account hebt toegevoegd als gegevensbron, voegt u **SavePen.xlsx** toe als verbinding en selecteert u vervolgens de tabel **Drawings**:  
   ![Verbinden](./media/tutorial-working-with-images-in-excel/savepen.png)  
   
   Nu wordt de tabel Drawings vermeld als gegevensbron.
3. Selecteer **Tekst** in het menu **Invoegen** en selecteer vervolgens **Peninvoer**. Wijzig de naam naar **MyPen**:  
   
   ![Naam wijzigen](./media/tutorial-working-with-images-in-excel/rename-mypen.png)
4. Voeg een besturingselement van het type **Button** toe (menu **Invoegen**) en stel de bijbehorende eigenschap **OnSelect** in op deze formule:  
   `Patch(Drawings, Defaults(Drawings), {Image:MyPen.Image})`
5. Voeg een besturingselement **Afbeeldingengalerie** toe (menu **Invoegen** > **Galerie**) en stel de eigenschap **Items** in op `Drawings`. De eigenschap **Image** van het galeriebesturingselement wordt automatisch ingesteld op `ThisItem.Image`.
   
   Uw scherm ziet er nu ongeveer als volgt uit:  
   
   ![Voorbeeldscherm](./media/tutorial-working-with-images-in-excel/screen.png)  
6. Druk op F5 of selecteer Voorbeeld (![](./media/tutorial-working-with-images-in-excel/preview.png)). Teken iets in MyPen en selecteer de knop. In de eerste afbeelding van het galeriebesturingselement wordt weergegeven wat u hebt getekend. Voeg nog iets toe aan uw tekening en selecteer de knop. In de tweede afbeelding van het galeriebesturingselement wordt weergegeven wat u hebt getekend.
   
   Sluit het voorbeeldvenster.
7. Ga naar cloudopslagaccount. Er is automatisch een nieuwe map **SavePen_images** gemaakt. U moet de pagina mogelijk verversen om de nieuwe map te zien. Deze map bevat uw opgeslagen afbeeldingen met id's als bestandsnaam.
   
    Open SavePen.xlsx. De Image-kolom bevat het pad naar deze nieuwe afbeeldingen.

## <a name="add-the-image-in-an-excel-file-to-your-app"></a>De afbeelding in een Excel-bestand toevoegen aan uw app
Een ander voorbeeld: u kunt afbeeldingen opslaan in een cloudopslagaccount en vervolgens een Excel-tabel gebruiken om de afbeeldingen in uw app weer te geven.

In dit voorbeeld gebruiken we de map [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip), die ook enkele JPEG-bestanden bevat.

> [!NOTE]
> Bij het weergeven van afbeeldingen uit een Excel-bestand, moet het pad naar deze afbeeldingen slash-tekens gebruiken. Wanneer PowerApps afbeeldingen opslaat naar een Excel-tabel (zoals in de vorige stap), worden in het pad backslash-tekens gebruikt. U kunt ook de **SavePen_images** uit het vorige voorbeeld gebruiken. Als u dit doet, dient u dus de slash-tekens in de paden in de Excel-tabel te vervangen door backslash-tekens. Anders worden de afbeeldingen niet weergegeven.  

1. Download eerst [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip) en pak de map **Assets** uit naar uw cloudopslagaccount.
2. Maak in een Excel-werkblad een tabel die er ongeveer zo uitziet:
   
    ![Tabel Jackets](./media/tutorial-working-with-images-in-excel/jackets.png)
3. Noem de tabel **Jackets**. Noem het Excel-bestand **Assets.xlsx**. U kunt ook de naam van de map **Assets** wijzigen naar **Assets_images**.
4. Voeg in uw app de tabel **Jackets** toe als gegevensbron.  
5. Voeg een besturingselement **Alleen afbeeldingen** toe (menu **Invoegen** > **Galerie**) en stel de eigenschap **Items** in op `Jackets`:  
   
    ![Eigenschap Items](./media/tutorial-working-with-images-in-excel/items-jackets.png)
   
    De galerie wordt automatisch bijgewerkt met de afbeeldingen:  
   
    ![Afbeeldingen Jacket](./media/tutorial-working-with-images-in-excel/images.png)

Als u de eigenschap Items instelt, wordt de Excel-tabel automatisch bijgewerkt met een nieuwe kolom met de naam **PowerAppsId**.

Het pad naar een afbeelding kan in de Excel-tabel ook de URL naar een afbeelding zijn. Download het voorbeeldbestand [Flooring Estimates](http://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx) naar uw cloudopslagaccount, voeg de tabel `FlooringEstimates` toe als gegevensbron in uw app en stel vervolgens het galeriebesturingselement in op `FlooringEstimates`. De galerie wordt automatisch bijgewerkt met de afbeeldingen.

## <a name="learn-more"></a>Meer informatie
[Een afbeelding, video of geluid toevoegen](add-images-pictures-audio-video.md)  
[Show data in a line, pie, or bar chart in your app (Gegevens in uw app weergeven in een lijn-, cirkel- of staafdiagram)](use-line-pie-bar-chart.md)  
[Understand tables and records in PowerApps (Over tabellen en records in PowerApps)](working-with-tables.md)

