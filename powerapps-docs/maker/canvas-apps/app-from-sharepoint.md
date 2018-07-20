---
title: Snelstartgids voor het genereren van een app in PowerApps vanuit SharePoint | Microsoft Docs
description: Automatisch een app genereren in PowerApps voor het beheren van gegevens in een SharePoint-lijst
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/12/2018
ms.author: anneta
ms.openlocfilehash: b9404b2ac7d67f9594b77ee73de55b46a94e7afa
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39016807"
---
# <a name="quickstart-for-generating-an-app-in-powerapps-from-sharepoint"></a>Snelstartgids voor het genereren van een app in PowerApps vanuit SharePoint

In deze snelstartgids gebruikt u PowerApps voor het automatisch genereren van uw eerste app op basis van een lijst die u in SharePoint maakt. In deze app kunt u naar alle items in de lijst bladeren, details van een item weergeven en een item maken, bijwerken of verwijderen.

U kunt concepten en technieken uit deze snelstartgids opdoen als er een lijst in SharePoint aanwezig is. Als u deze snelstartgids exact wilt volgen, maakt u een lijst met de naam **SimpleApp**, die een kolom met de naam **Titel** bevat, in een SharePoint Online-site. Maak in de lijst vermeldingen voor **Vanille**, **Chocolade** en **Aardbeien**.

U kunt een lijst maken die veel complexer is, met veel kolommen van verschillende typen, zoals tekst, datums, getallen en valuta. De beginselen van het genereren van een app worden niet gewijzigd. U kunt ook een app genereren uit een lijst in een on-premises SharePoint-site als u [verbinding maakt met de site](connect-to-sharepoint.md) via een gegevensgateway.

Als u geen licentie voor PowerApps hebt, kunt u zich [gratis registreren](../signup-for-powerapps.md).

## <a name="generate-an-app"></a>Een app genereren
1. Meld u aan bij [PowerApps](https://web.powerapps.com).

    ![PowerApps-startpagina](./media/app-from-sharepoint/sign-in.png)

1. Beweeg de muisaanwijzer onder **Apps zoals deze maken** over **Starten vanuit gegevens** en selecteer vervolgens **Deze app maken**.

    ![Optie voor het maken van een app](./media/app-from-sharepoint/make-this-app.png)

1. Selecteer op de SharePoint-tegel **Telefoonindeling**.

    ![Optie voor het maken van een app](./media/app-from-sharepoint/sharepoint-tile.png)

1. Selecteer, terwijl u de optie **Rechtstreeks verbinding maken** hebt geselecteerd, het item **Maken**.

    ![Verbinding maken](./media/app-from-sharepoint/create-connection.png)

1. Typ of plak onder **Verbinding maken met een SharePoint-site** de URL voor uw SharePoint Online-site en selecteer vervolgens **Start**.

    Voeg alleen de URL van de site toe (niet de naam van de lijst), zoals in dit voorbeeld:<br>`https://microsoft.sharepoint.com/teams/Contoso`

1. Selecteer onder **Een lijst kiezen** de optie **SimpleApp** en selecteer vervolgens **Verbinding maken**.

Na een paar minuten wordt uw app geopend op het scherm voor bladeren waarin de items die u hebt gemaakt in de lijst worden weergegeven. Als uw lijst gegevens bevat in meer kolommen dan alleen **Titel**, worden die gegevens door de app weergegeven. Aan de bovenkant van het scherm worden in een titelbalk pictogrammen weergegeven voor het vernieuwen en sorteren van de lijst, en voor het maken van een item in de lijst. Onder de titelbalk biedt een zoekvak de mogelijkheid om de lijst te filteren op basis van tekst die u typt of plakt. 

![Bladerscherm](./media/app-from-sharepoint/browse-screen.png)

U wilt waarschijnlijk meer wijzigingen aanbrengen voordat u deze app gebruikt of met anderen deelt. Het wordt aanbevolen uw werk tot nu toe op te slaan door op Ctrl + S te drukken voordat u doorgaat. Geef een naam op voor uw app en selecteer vervolgens **Opslaan**.

## <a name="next-steps"></a>Volgende stappen
In deze snelstartgids hebt u een app gemaakt voor het beheren van gegevens in een SharePoint-lijst. Genereer als volgende stap een app uit een complexere lijst en pas vervolgens de app (te beginnen met het scherm voor bladeren) aan uw eigen behoeften aan.

> [!div class="nextstepaction"]
> [Een standaardscherm voor bladeren aanpassen](customize-layout-sharepoint.md)