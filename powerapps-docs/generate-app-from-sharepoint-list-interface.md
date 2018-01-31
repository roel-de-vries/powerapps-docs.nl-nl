---
title: Een app genereren vanuit een SharePoint-lijst | Microsoft Docs
description: Genereer een app met drie schermen om items vanuit een SharePoint-lijst te beheren. De site kan on-premises of in de cloud staan.
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
ms.date: 01/21/2017
ms.author: sharik
ms.openlocfilehash: 8ac8fb34f9cdeb0c9e0ce6172938cef33ecccbc5
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="generate-an-app-from-within-sharepoint-using-powerapps"></a>Een app genereren vanuit SharePoint met behulp van PowerApps



Genereer in PowerApps automatisch een app waarin gebruikers items in een aangepaste SharePoint Online-lijst kunnen beheren. De app heeft drie schermen waarmee gebruikers het volgende kunnen doen:

* door alle records in de lijst bladeren (**BrowseScreen1**)
* alle velden voor een bepaalde record weergeven (**DetailsScreen1**)
* een record maken of bewerken (**EditScreen1**)

Als u een app maakt van een aangepaste lijst via de opdrachtbalk in SharePoint Online, wordt de app weergegeven als een weergave van die lijst. U kunt de app niet alleen in een webbrowser uitvoeren, maar ook op een Windows Phone-, iOS- of Android-apparaat.

> [!IMPORTANT]
> PowerApps biedt geen ondersteuning voor alle soorten SharePoint-gegevens. Zie [Bekende problemen](connections/connection-sharepoint-online.md#known-issues) voor meer informatie.

## <a name="generate-an-app"></a>Een app genereren
1. Open een aangepaste lijst in SharePoint Online, klik of tik op **PowerApps** op de opdrachtbalk en klik op of tik vervolgens op **Een app maken**.
   
    ![](./media/generate-app-from-sharepoint-list-interface/generate-new-app.png)
2. Typ een naam voor uw app in het deelvenster dat verschijnt en klik of tik op **Maken**.
   
    ![](./media/generate-app-from-sharepoint-list-interface/enter-app-name.png)
   
    Er wordt een nieuw tabblad weergegeven in de webbrowser, met daarop de app die u automatisch hebt gegenereerd op basis van de SharePoint-lijst.
   
    ![](./media/generate-app-from-sharepoint-list-interface/powerapp-studio-for-web.png)  
3. Klik of tik op het browsertabblad voor uw SharePoint-lijst en klik of tik daarna op **Openen**.
   
    > [!NOTE]
> Mogelijk moet u het browservenster vernieuwen (bijvoorbeeld door op F5 te drukken) voordat de app wordt geopend.
   
    ![](./media/generate-app-from-sharepoint-list-interface/open-app-in-browser.png)
   
    De app wordt op een afzonderlijk browsertabblad geopend.
   
    ![](./media/generate-app-from-sharepoint-list-interface/open-app.png)

## <a name="manage-the-app"></a>De app beheren
![](./media/generate-app-from-sharepoint-list-interface/command-bar.png)

* Als u klikt of tikt op **Bewerken in PowerApps**, wordt de app geopend in een afzonderlijk browsertabblad, waar u de app kunt bijwerken in de webversie van PowerApps Studio.
* Als u klikt of tikt op **Deze weergave openbaar maken**, kunnen andere personen in uw organisatie deze zien. Standaard ziet u alleen weergaven die u zelf maakt. Als u wilt dat anderen uw app kunnen bewerken, moet u de app [met hen delen](share-app.md) en hen vervolgens machtigen als **Medewerker**.
* Als u klikt of tikt op **Deze weergave verwijderen**, verwijdert u de weergave uit SharePoint, maar de app blijft aanwezig in PowerApps, tenzij u deze [verwijdert](delete-app.md).

## <a name="next-steps"></a>Volgende stappen
* Zie de sectie De lijst beheren met de app in [Open app from a SharePoint Online list](open-app-embedded-in-sharepoint.md) (Een app openen via een SharePoint Online-lijst) als u items aan de lijst wilt toevoegen of deze wilt bijwerken.
* Zie [Customize a layout](customize-layout-sharepoint.md) (Een indeling aanpassen) voor het aanpassen van het bladerscherm (dat standaard wordt weergegeven).
* Zie [Een formulier aanpassen](customize-forms-sharepoint.md) voor het aanpassen van de detail- of bewerkingsschermen.
* Als u de app wilt verwijderen, verwijdert u de weergave uit SharePoint en [verwijdert u de app](delete-app.md) uit PowerApps.

