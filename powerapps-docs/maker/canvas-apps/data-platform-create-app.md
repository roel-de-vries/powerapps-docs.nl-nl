---
title: 'Snelstart: Een app genereren vanuit Common Data Service for apps | Microsoft Docs'
description: Automatisch een app genereren in PowerApps voor het beheren van gegevens in Common Data Service for Apps
author: AFTOwen
ms.service: powerapps
ms.topic: conceptual
ms.component: canvas
ms.date: 03/10/2018
ms.author: anneta
ms.openlocfilehash: a70145ee3db44b4ce5d58be2d7804bffb5a56369
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-generate-an-app-from-common-data-service-for-apps-in-powerapps"></a>Snelstart: Een app genereren vanuit Common Data Service for apps in PowerApps

In deze snelstart gebruikt u Microsoft PowerApps voor het automatisch genereren van een app op basis van een lijst voorbeeldaccounts in [Common Data Service (CDS) for Apps](../common-data-service/data-platform-intro.md). In deze app kunt u naar alle accounts bladeren, details van een account weergeven en een account maken, bijwerken of verwijderen.

Als u deze snelstart wilt volgen, moet u [overschakelen naar een omgeving](working-with-environments.md) waarin een database is gemaakt in CDS for Apps die gegevens bevat en updates toestaat. Als er geen dergelijke omgeving bestaat en u administratorbevoegdheden hebt, kunt u [een omgeving maken](../../administrator/environments-administration.md#create-an-environment) die voldoet aan deze vereiste.

Als u geen licentie voor PowerApps hebt, kunt u zich [gratis registreren](../signup-for-powerapps.md).

## <a name="generate-an-app"></a>Een app genereren
1. Meld u aan bij [PowerApps](https://web.powerapps.com) en schakel, indien nodig, over van omgeving zoals eerder in dit onderwerp is aangegeven.

    ![PowerApps-startpagina](./media/data-platform-create-app/sign-in.png)

1. Beweeg de muisaanwijzer onder **Apps zoals deze maken** over **Starten vanuit gegevens** en selecteer vervolgens **Deze app maken**.

    ![Optie voor het maken van een app](./media/data-platform-create-app/make-this-app.png)

1. Selecteer op de tegel **Common Data Service** de optie **Telefoonindeling**.

    ![De tegel Verbinding](./media/data-platform-create-app/connection-tile.png)

1. Selecteer onder **Een tabel kiezen** de optie **Accounts** en selecteer vervolgens **Verbinding maken**.

1. Selecteer **Overslaan** in het dialoogvenster **Welkom bij PowerApps Studio**.

Uw app wordt geopend in het bladerscherm. Hierin ziet u een lijst met accounts. Aan de bovenkant van het scherm worden in een titelbalk pictogrammen getoond voor het vernieuwen en sorteren van de lijst en voor het maken van een account. Onder de titelbalk biedt een zoekvak de mogelijkheid om de lijst te filteren op basis van tekst die u typt of plakt. 

In de lijst worden standaard een e-mailadres, een plaats en een id voor de account weergegeven. U kunt de lijst (ook wel een galerie genoemd) echter aanpassen om andere typen gegevens weer te geven.

![Bladerscherm](./media/data-platform-create-app/browse-screen.png)

## <a name="save-the-app"></a>De app opslaan
U wilt waarschijnlijk meer wijzigingen aanbrengen voordat u deze app gebruikt of met anderen deelt. Het wordt aanbevolen uw werk tot nu toe opslaan voordat u doorgaat.

1. Selecteer in de linkerbovenhoek het tabblad **Bestand**.

1. Op de pagina **App-instellingen** stelt u de app-naam in op **AppGen**, verandert u de achtergrondkleur in dieprood en verandert u het pictogram in een vinkje.

    ![De pagina App-instellingen](./media/data-platform-create-app/app-settings.png)

1. Selecteer bij de linkerrand **Opslaan** en selecteer vervolgens in de linkerbenedenhoek **Opslaan**.

## <a name="next-steps"></a>Volgende stappen
Met behulp van deze snelstart hebt u een app gemaakt om voorbeeldgegevens over accounts te beheren in CDS for Apps. De volgende stap is dat u de galerie en andere elementen van het standaardscherm voor bladeren aan uw eigen behoeften aanpast.

> [!div class="nextstepaction"]
> [Een galerie aanpassen](customize-layout-sharepoint.md).
