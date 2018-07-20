---
title: Een app genereren vanuit een SharePoint-lijst | Microsoft Docs
description: Genereer een app met drie schermen om items vanuit een SharePoint-lijst te beheren. De site kan on-premises of in de cloud staan.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
ms.openlocfilehash: 46cf610351cf00d8d947c4006c31a3d5971951d0
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39022450"
---
# <a name="generate-an-app-from-within-sharepoint-using-powerapps"></a>Een app genereren vanuit SharePoint met behulp van PowerApps

Genereer in PowerApps automatisch een app waarin gebruikers items in een aangepaste SharePoint Online-lijst kunnen beheren. De app heeft drie schermen waarmee gebruikers het volgende kunnen doen:

* door alle records in de lijst bladeren (**BrowseScreen1**)
* alle velden voor een bepaalde record weergeven (**DetailsScreen1**)
* een record maken of bewerken (**EditScreen1**)

Als u een app maakt van een aangepaste lijst via de opdrachtbalk in SharePoint Online, wordt de app weergegeven als een weergave van die lijst. U kunt de app niet alleen in een webbrowser, maar ook op een iOS- of Android-apparaat uitvoeren.

> [!IMPORTANT]
> PowerApps biedt geen ondersteuning voor alle soorten SharePoint-gegevens. Zie [Bekende problemen](connections/connection-sharepoint-online.md#known-issues) voor meer informatie.

## <a name="generate-an-app"></a>Een app genereren
1. Open een aangepaste lijst in SharePoint Online, klik of tik op **PowerApps** op de opdrachtbalk en klik op of tik vervolgens op **Een app maken**.

    ![Een app maken](./media/generate-app-from-sharepoint-list-interface/generate-new-app.png)

2. Typ een naam voor uw app in het deelvenster dat verschijnt en klik of tik op **Maken**.

    ![De app een naam geven](./media/generate-app-from-sharepoint-list-interface/app-name.png)

    Er wordt een nieuw tabblad weergegeven in de webbrowser, met daarop de app die u automatisch hebt gegenereerd op basis van de SharePoint-lijst. De app wordt weergegeven in PowerApps Studio, waar u deze kunt aanpassen.

    ![Standaard-app](./media/generate-app-from-sharepoint-list-interface/default-app.png)  
3. Klik of tik op het browsertabblad voor uw SharePoint-lijst en klik of tik daarna op **Openen**.

> [!NOTE]
> Mogelijk moet u het browservenster vernieuwen (bijvoorbeeld door op F5 te drukken) voordat de app wordt geopend.

De app wordt op een afzonderlijk browsertabblad geopend.

## <a name="manage-the-app"></a>De app beheren
![Opdrachtbalk](./media/generate-app-from-sharepoint-list-interface/command-bar.png)

* Als u klikt of tikt op **Bewerken in PowerApps**, wordt de app geopend in een afzonderlijk browsertabblad, waar u de app kunt bijwerken in PowerApps Studio.

* Als u klikt of tikt op **Deze weergave openbaar maken**, kunnen andere personen in uw organisatie deze zien. Standaard ziet u alleen weergaven die u zelf maakt. Als u wilt dat anderen uw app kunnen bewerken, moet u de app [met hen delen](share-app.md) en hen vervolgens machtigen als **Can edit**.

* Als u klikt of tikt op **Deze weergave verwijderen**, verwijdert u de weergave uit SharePoint, maar de app blijft aanwezig in PowerApps, tenzij u deze [verwijdert](delete-app.md).

## <a name="next-steps"></a>Volgende stappen
* Pas de standaard [galerie](customize-layout-sharepoint.md), [formulieren](customize-forms-sharepoint.md) en [kaarten](customize-card.md) aan.
