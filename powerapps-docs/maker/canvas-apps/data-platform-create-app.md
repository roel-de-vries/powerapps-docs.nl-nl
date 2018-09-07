---
title: Een canvas-app genereren in Common Data Service for Apps | Microsoft Docs
description: In PowerApps automatisch een canvas-app genereren voor het beheren van gegevens in Common Data Service for Apps
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: quickstart
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/06/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: bf19983217afad23b75a0f0dbd1e307e6539d3f5
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42825943"
---
# <a name="generate-a-canvas-app-from-common-data-service-for-apps-in-powerapps"></a>In PowerApps een canvas-app genereren in Common Data Service for Apps

Genereer in PowerApps automatisch een canvas-app op basis van een lijst met voorbeeldaccounts in [Common Data Service (CDS) for Apps](../common-data-service/data-platform-intro.md). In deze app kunt u naar alle accounts bladeren, details van een account weergeven en een account maken, bijwerken of verwijderen.

Als u zich niet hebt geregistreerd voor PowerApps, kunt u zich hier [gratis registreren](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) voordat u begint.

## <a name="prerequisites"></a>Vereisten

Als u deze snelstart wilt volgen, moet u [overschakelen naar een omgeving](working-with-environments.md) waarin een database is gemaakt in CDS for Apps die gegevens bevat en updates toestaat. Als er geen dergelijke omgeving bestaat en u administratorbevoegdheden hebt, kunt u [een omgeving maken](../../administrator/environments-administration.md#create-an-environment) die voldoet aan deze vereiste.

## <a name="generate-an-app"></a>Een app genereren

1. Meld u aan bij [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) en schakel, indien nodig, over van omgeving zoals eerder in dit onderwerp is aangegeven.

    ![PowerApps-startpagina](./media/data-platform-create-app/sign-in.png)

1. Beweeg de muisaanwijzer onder **Apps zoals deze maken** over **Starten vanuit gegevens** en selecteer vervolgens **Deze app maken**.

    ![Optie voor het maken van een app](./media/data-platform-create-app/make-this-app.png)

1. Selecteer op de tegel **Common Data Service** de optie **Telefoonindeling**.

    ![De tegel Verbinding](./media/data-platform-create-app/connection-tile.png)

1. Selecteer onder **Een tabel kiezen** de optie **Accounts** en selecteer vervolgens **Verbinding maken**.

1. Selecteer **Overslaan** in het dialoogvenster **Welkom bij PowerApps Studio**.

Uw app wordt geopend in het bladerscherm. Hierin ziet u een lijst met accounts in een besturingselement dat een galerie wordt genoemd. Aan de bovenkant van het scherm ziet u op een titelbalk pictogrammen om de gegevens in de galerie te vernieuwen, de gegevens in de galerie op alfabetische volgorde te sorteren en gegevens toe te voegen aan de galerie. Onder de titelbalk biedt een zoekvak de mogelijkheid om de gegevens in de galerie te filteren op basis van tekst die u typt of plakt. 

In de galerie worden standaard een e-mailadres, een plaats en een accountnaam weergegeven. U ziet in [Volgende stappen](data-platform-create-app.md#next-steps) dat u de galerie kunt aanpassen om te wijzigen hoe de gegevens worden weergegeven en zelfs andere typen gegevens weer te geven.

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
