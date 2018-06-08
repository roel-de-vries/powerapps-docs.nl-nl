---
title: Een app genereren vanuit Excel | Microsoft Docs
description: PowerApps gebruiken voor het automatisch genereren van een app met een Excel-bestand dat is opgeslagen in een cloud-opslagaccount
documentationcenter: na
author: AFTOWen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 54d53d5f3385be4b5d38a2bf220da139ba3bd3a4
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31827253"
---
# <a name="generate-an-app-from-excel-in-powerapps"></a>Een app genereren vanuit Excel in PowerApps
In dit onderwerp genereert u uw eerste app automatisch in PowerApps met gegevens uit een Excel-tabel. U selecteert een Excel-bestand, genereert een app en voert vervolgens de app uit die u hebt gegenereerd. Elke gegenereerde app bevat schermen om te bladeren in records, recordgegevens weer te geven en records te maken of bij te werken. Door het genereren van een app kunt u snel een werkende app krijgen met Excel-gegevens. Vervolgens kunt u de app aan uw eigen behoeften aanpassen. 

Het Excel-bestand moet zich in een cloudopslagaccount bevinden, zoals OneDrive, Google Drive of Dropbox. In dit onderwerp wordt gebruikgemaakt van OneDrive voor bedrijven.

Als u geen licentie voor PowerApps hebt, kunt u zich [gratis registreren](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Vereisten ##
Download het bestand [Flooring Estimates](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx) in Excel en sla het op in uw [cloud-opslagaccount](connections/cloud-storage-blob-connections.md) om dit onderwerp exact te volgen.

> [!IMPORTANT]
> U kunt uw eigen Excel-bestand gebruiken maar de gegevens moeten zijn opgemaakt als tabel. Zie voor meer informatie [Een tabel opmaken](how-to-excel-tips.md). 

## <a name="generate-the-app"></a>De app genereren
1. Meld u aan bij [PowerApps](https://web.powerapps.com).

    ![PowerApps-startpagina](./media/get-started-create-from-data/sign-in.png)

1. Beweeg de muisaanwijzer onder **Apps zoals deze maken** over **Starten vanuit gegevens** en selecteer vervolgens **Deze app maken**.

    ![Optie voor het maken van een app](./media/get-started-create-from-data/make-this-app.png)

1. Klik of tik onder **Beginnen met uw gegevens** op **Telefoonindeling** op de tegel voor uw cloudopslagaccount.

    ![Optie voor het maken van een app](./media/get-started-create-from-data/odfb-tile.png)

1. Als u hierom wordt gevraagd, klikt of tikt u op **Verbinding maken** en geeft u uw referenties voor dat account op.

1. Klik of tik onder **Choose an Excel file** op **FlooringEstimates.xlsx**. 

1. Klik of tik onder **Choose a table** op **FlooringEstimates** en vervolgens op **Connect**.

    ![Optie voor het maken van een app](./media/get-started-create-from-data/choose-table.png)

## <a name="run-the-app"></a>De app uitvoeren
1. Open Preview door op F5 te drukken (of door op het pictogram voor afspelen in de rechterbovenhoek te klikken of tikken).

    ![Preview openen](./media/get-started-create-from-data/open-preview.png)

1. Schakel de sorteervolgorde om door te klikken of tikken op het pictogram voor sorteren bij de rechterbovenhoek.

    ![Pictogram voor sorteren](./media/get-started-create-from-data/sort-icon.png)

1. U kunt de lijst filteren door een of meer tekens in het zoekvak te typen of te plakken.

1. Klik of tik op het plus-pictogram om een record toe te voegen, voeg de gewenste gegevens toe en klik of tik op het vinkje om uw wijzigingen op te slaan.

1. Klik of tik op de pijl Volgende voor de record die u hebt toegevoegd, klik of tik op het potloodpictogram voor het bewerken van de record, werk een of meer velden bij en klik of tik op het vinkje om uw wijzigingen op te slaan.

1. Klik of tik op de pijl Volgende voor de record die u hebt toegevoegd, klik of tik op het potloodpictogram voor het bewerken van de record, werk een of meer velden bij en klik of tik op het pictogram voor annuleren om uw wijzigingen te negeren.

1. Klik of tik op de pijl Volgende voor de record dat u hebt toegevoegd en klik of tik vervolgens op het prullenbakpictogram om de record verwijderen.

## <a name="next-steps"></a>Volgende stappen
Pas het standaardscherm voor bladeren aan uw eigen behoeften aan. U kunt bijvoorbeeld de lijst op productnaam sorteren en filteren, en niet op categorie.

> [!div class="nextstepaction"]
> [Een standaardscherm voor bladeren aanpassen](customize-layout-sharepoint.md).