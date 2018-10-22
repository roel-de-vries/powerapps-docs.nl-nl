---
title: Een canvas-app genereren vanuit een SharePoint-lijst | Microsoft Docs
description: Automatisch een canvas-app genereren in PowerApps om gegevens in een SharePoint-lijst te beheren
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 08/09/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 15aa49787d6b2c3d3981e374aeb43c54a2d7a7ec
ms.sourcegitcommit: 02d0234bd84352bf1c43d0fc9225ab60947a0add
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/15/2018
ms.locfileid: "49317086"
---
# <a name="generate-a-canvas-app-in-powerapps-from-a-sharepoint-list"></a>In PowerApps een canvas-app genereren vanuit een SharePoint-lijst

In dit onderwerp gebruikt u PowerApps voor het automatisch genereren van een canvas-app op basis van items op een SharePoint-lijst. U kunt de app genereren in PowerApps of SharePoint Online. U kunt in PowerApps de app genereren op basis van een lijst in een on-premises SharePoint-site als u [verbinding maakt met de site](connect-to-sharepoint.md) via een gegevensgateway.

De app die u genereert bevat drie schermen:

- In het scherm voor bladeren kunt u door alle items in de lijst bladeren.
- In het scherm met details kunt u alle informatie over een enkel item in de lijst weergeven.
- In het scherm voor bewerken kunt u een item maken of informatie bijwerken over een bestaand item.

U kunt de concepten en technieken in dit onderwerp toepassen op elke lijst in SharePoint. U kunt, wanneer u de stappen nauwkeurig volgt:

1. op een SharePoint Online-site een lijst maken met de naam **SimpleApp**;
2. in een kolom met de naam **Titel** vermeldingen maken voor **Vanille**, **Chocolade** en **Aardbeien**.

De beginselen van het genereren van een app worden niet gewijzigd, zelfs als u een lijst maakt die veel complexer is, met veel kolommen van verschillende typen, zoals tekst, datums, getallen en valuta.

> [!IMPORTANT]
> PowerApps biedt geen ondersteuning voor alle soorten SharePoint-gegevens. Zie [Bekende problemen](connections/connection-sharepoint-online.md#known-issues) voor meer informatie.

## <a name="generate-an-app-from-within-powerapps"></a>Een app genereren in PowerApps

1. Meld u aan bij [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Wijs onder **Uw eigen app maken** de optie **Starten vanuit gegevens** aan en selecteer vervolgens **Deze app maken**.

    ![Optie voor het maken van een app](./media/app-from-sharepoint/start-from-data.png)

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

## <a name="generate-an-app-from-within-sharepoint-online"></a>Een app genereren in SharePoint Online

Als u een app maakt van een aangepaste lijst via de opdrachtbalk in SharePoint Online, wordt de app weergegeven als een weergave van die lijst. U kunt de app niet alleen in een webbrowser, maar ook op een iOS- of Android-apparaat uitvoeren.

1. Open in SharePoint Online een aangepaste lijst, selecteer **PowerApps** op de opdrachtbalk en selecteer vervolgens **Een app maken**.

    ![Een app maken](./media/app-from-sharepoint/generate-new-app.png)

2. Typ een naam voor uw app in het deelvenster dat verschijnt en selecteer daarna **Maken**.

    ![De app een naam geven](./media/app-from-sharepoint/app-name.png)

    Er wordt een nieuw tabblad weergegeven in de webbrowser, met daarop de app die u automatisch hebt gegenereerd op basis van de SharePoint-lijst. De app wordt weergegeven in PowerApps Studio, waar u deze kunt aanpassen.

    ![Standaard-app](./media/app-from-sharepoint/default-app.png)

3. (optioneel) Vernieuw het browsertabblad voor uw SharePoint-lijst (door deze te selecteren en vervolgens bijvoorbeeld op F5 te drukken), en volg vervolgens deze stappen als u uw app wilt uitvoeren of beheren:

    - Selecteer **Open** voor het uitvoeren van de app (in een afzonderlijk browsertabblad).
    - Als u wilt dat anderen in uw organisatie de app kunnen uitvoeren, selecteert u **Deze weergave openbaar maken**.

        Als u wilt dat anderen uw app kunnen bewerken, [deelt u deze](share-app.md) met de machtigingen **Mag bewerken**.

    - Als u de weergave uit SharePoint wilt verwijderen, selecteert u **Deze weergave verwijderen**.

        Als u de app uit PowerApps wilt verwijderen, [verwijdert u de app](delete-app.md).

## <a name="next-steps"></a>Volgende stappen
In dit onderwerp hebt u een app gemaakt voor het beheren van gegevens in een SharePoint-lijst. Genereer als volgende stap een app uit een complexere lijst en pas vervolgens de app (te beginnen met het scherm voor bladeren) aan uw eigen behoeften aan.

> [!div class="nextstepaction"]
> [Een standaardscherm voor bladeren aanpassen](customize-layout-sharepoint.md)
