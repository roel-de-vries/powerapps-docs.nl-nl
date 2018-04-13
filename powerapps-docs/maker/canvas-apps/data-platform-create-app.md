---
title: In PowerApps een app genereren voor Common Data Service for Apps (snelstartgids) | Microsoft Docs
description: Automatisch een app genereren in PowerApps voor het beheren van gegevens in Common Data Service for Apps
services: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/10/2018
ms.author: anneta
ms.openlocfilehash: 78429fc5d0220b5cc9e8dc726583c2e9e543f85a
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-for-generating-an-app-in-powerapps-for-the-common-data-service-for-apps"></a>Snelstartgids voor het in PowerApps genereren van apps voor Common Data Service for Apps

In deze snelstartgids gebruikt u PowerApps voor het automatisch genereren van uw eerste app op basis van een lijst voorbeeldaccounts uit [Common Data Service for Apps](../common-data-service/data-platform-intro.md). In deze app kunt u naar alle accounts bladeren, details van een account weergeven en een account maken, bijwerken of verwijderen.

Als u deze zelfstudie wilt volgen, moet u overschakelen naar een [omgeving](working-with-environments.md) waarin een database is gemaakt in Common Data Service die gegevens bevat. Als er geen dergelijke omgeving bestaat en u administratorbevoegdheden hebt, kunt u [een omgeving maken](../../administrator/environments-administration.md#create-an-environment) die voldoet aan deze vereiste.

Als u geen licentie voor PowerApps hebt, kunt u zich [gratis registreren](../signup-for-powerapps.md).

## <a name="generate-an-app"></a>Een app genereren
1. Meld u aan bij [PowerApps](https://web.powerapps.com).

    ![PowerApps-startpagina](./media/data-platform-create-app/sign-in.png)

1. Beweeg de muisaanwijzer onder **Apps zoals deze maken** over **Starten vanuit gegevens** en selecteer vervolgens **Deze app maken**.

    ![Optie voor het maken van een app](./media/data-platform-create-app/make-this-app.png)

1. Onder **Beginnen met uw gegevens** selecteert u de pijl naar rechts.

    ![Pijlpictogram](./media/data-platform-create-app/right-arrow.png)

1. Onder **Verbindingen** selecteert u de verbinding met de Common Data Service.

1. Typ **Accounts** in het zoekvak (bij de rechterrand), selecteer **Accounts** onder **Een tabel kiezen** en selecteer vervolgens **Verbinding maken**.

    ![Een entiteit selecteren](./media/data-platform-create-app/select-entity.png)

Na een paar minuten wordt uw app geopend in het bladerscherm. Hierin ziet u een lijst met accounts. Aan de bovenkant van het scherm worden in een titelbalk pictogrammen getoond voor het vernieuwen en sorteren van de lijst en voor het maken van een account. Onder de titelbalk biedt een zoekvak de mogelijkheid om de lijst te filteren op basis van tekst die u typt of plakt. 

In de lijst worden standaard een afbeelding, een e-mailadres, een plaats en een id voor het account weergegeven. U kunt de lijst (ook wel een galerie genoemd) echter aanpassen om andere typen gegevens weer te geven.

![Bladerscherm](./media/data-platform-create-app/browse-screen.png)

## <a name="save-the-app"></a>De app opslaan
U wilt waarschijnlijk meer wijzigingen aanbrengen voordat u deze app gebruikt of met anderen deelt. Het wordt aanbevolen uw werk tot nu toe opslaan voordat u doorgaat.

1. Klik of tik in de linkerbovenhoek op het tabblad **Bestand**.

1. Op de pagina **App-instellingen** stelt u de app-naam in op **AppGen**, verandert u de achtergrondkleur in dieprood en verandert u het pictogram in een vinkje.

    ![De pagina App-instellingen](./media/data-platform-create-app/app-settings.png)

1. Klik of tik aan de linkerkant op **Opslaan**.

## <a name="next-steps"></a>Volgende stappen
Met behulp van deze snelstartgids hebt u een app gemaakt om voorbeeldgegevens over accounts te beheren in Common Data Service for Apps. De volgende stap is dat u het standaardscherm voor bladeren aan uw eigen behoeften aanpast.

> [!div class="nextstepaction"]
> [Pas een standaardscherm voor bladeren aan](customize-layout-sharepoint.md).
