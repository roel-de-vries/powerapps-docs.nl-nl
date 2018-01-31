---
title: Een app genereren voor het beheren van gegevens in een SharePoint-lijst | Microsoft Docs
description: Genereer een app met drie schermen om gegevens in een SharePoint-lijst te beheren. Deze site kan on-premises zijn of in de cloud.
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/05/2017
ms.author: sharik
ms.openlocfilehash: 36a9188615c14262de0bfdea21d58010a053e01f
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="generate-an-app-to-manage-data-in-a-sharepoint-list"></a>Een app genereren voor het beheren van gegevens in een SharePoint-lijst



Genereer in PowerApps automatisch een app met drie schermen om gegevens in een SharePoint-lijst te beheren. Deze site kan on-premises zijn of in de cloud.

Standaard bevat elke gegenereerde app een scherm om in records te bladeren, een scherm om de details van een record te tonen en een scherm om records te maken of bij te werken. De indeling en inhoud voor elk scherm worden in eerste instantie automatisch bepaald, maar u kunt de app aan uw eigen wensen aanpassen.

Zie [Introduction to PowerApps](getting-started.md) (Inleiding tot PowerApps) als u onbekend bent met PowerApps.

Op het moment van schrijven ondersteunt PowerApps aangepaste lijsten, maar geen bibliotheken. Daarnaast kunt u gegevens weergeven in sommige typen kolommen, bijvoorbeeld **Keuze** en **Afbeelding**. U kunt de gegevens echter niet bijwerken. Zie [Bekende problemen](connections/connection-sharepoint-online.md#known-issues) voor meer informatie.

> [!NOTE]
> Als een kolomnaam een spatie bevat, wordt deze in PowerApps weergegeven als **‘\_x0020\_’**. **'Kolomnaam'** wordt bijvoorbeeld weergegeven als **'Kolom_x0020_naam'**.

## <a name="specify-a-sharepoint-app"></a>Een SharePoint-app opgeven
1. Maak [verbinding met SharePoint](connect-to-sharepoint.md) als u dat nog niet hebt gedaan.
2. Open PowerApps op *een van deze twee* manieren:
   
   * [Installeer PowerApps Studio voor Windows](http://aka.ms/powerappsinstall), open het en meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren. Klik of tik aan de linkerkant op **Nieuw**.
     
       ![Optie Nieuw in het menu Bestand](./media/app-from-sharepoint/file-menu.png)
   * [Open de webversie van PowerApps Studio](https://create.powerapps.com/api/start) in een browser.
     
       Zie [Create or edit apps in a browser](create-app-browser.md) (Apps in een browser maken of bewerken) voor een lijst met ondersteunde browsers en de beperkingen in de preview-versie van de webversie van PowerApps Studio.
3. Klik of tik onder **Beginnen met uw gegevens** op **Telefoonindeling** op de SharePoint-tegel.
   
    ![](./media/app-from-sharepoint/sharepoint-tile.png)

## <a name="specify-a-site-and-a-list"></a>Een site en een lijst opgeven
1. Typ of plak onder **Connect to a SharePoint site** de URL naar de site die de lijst bevat die u wilt gebruiken en klik of tik vervolgens op **Go**.
   
    > [!NOTE]
> Neem geen specifieke lijst in de URL op.
   
    ![](./media/app-from-sharepoint/specify-site.png)
2. Klik of tik onder **Choose a list** de naam van de lijst die u wilt gebruiken.
   
    U kunt de lijstnamen alfabetisch sorteren door op de sorteerknop te klikken.
   
    ![](./media/app-from-sharepoint/sort-button.png)
   
    U kunt ook ten minste één letter in het zoekvak typen of plakken om alleen die lijstnamen weer te geven met de tekst die u opgeeft.
   
    ![](./media/app-from-sharepoint/choose-list.png)
   
    Niet alle soorten lijsten worden standaard weergegeven. Als de naam van de lijst die u wilt gebruiken niet wordt weergegeven, scrolt u naar beneden en typt u de lijstnaam in het vak **Een aangepaste lijstnaam invoeren**.
   
    ![](./media/app-from-sharepoint/custom-list.png)
3. Klik of tik op **Connect** om de app te genereren.
   
    ![Knop Connect](./media/app-from-sharepoint/connect-button.png)
4. Als u wordt voorgesteld de inleidende rondleiding te volgen, klikt of tikt u op **Volgende** om vertrouwd te raken met de belangrijkste gedeelten van de PowerApps-interface (of klik of tik op **Overslaan**).
   
    ![Scherm van de inleidende rondleiding openen](./media/app-from-sharepoint/quick-tour.png)
   
    U kunt de rondleiding altijd later volgen door op het vraagtekenpictogram in de rechterbovenhoek te klikken of tikken en vervolgens op **Take the intro tour**.

## <a name="next-steps"></a>Volgende stappen
* Druk op Ctrl+S om de zojuist gegenereerde app op te slaan.
* Zie [Customize a layout](customize-layout-sharepoint.md) (Een indeling aanpassen) voor het aanpassen van het bladerscherm (dat standaard wordt weergegeven).
* Zie [Een formulier aanpassen](customize-forms-sharepoint.md) voor het aanpassen van de detail- of bewerkingsschermen.

