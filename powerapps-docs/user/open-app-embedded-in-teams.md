---
title: Een app toevoegen aan Microsoft Teams | Microsoft Docs
description: Ontdek hoe u een app toevoegt aan een Microsoft Teams-kanaal, zodat iedereen met wie u de app hebt gedeeld de app via dat kanaal kan openen.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: quickstart
ms.date: 01/18/2018
ms.author: matp
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 0e98f22c3dc0f66893e0cc027488ced5d1dd3535
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850456"
---
# <a name="add-an-app-to-microsoft-teams"></a>Een app toevoegen aan Microsoft Teams

Microsoft Teams is een op chat gebaseerd samenwerkingsplatform dat is gebouwd met Office 365-technologieën. U kunt de Teams-ervaring aanpassen door canvas-apps in PowerApps toe te voegen aan uw kanalen in Teams. In dit onderwerp leert u hoe u de voorbeeld-app Productoverzicht kunt toevoegen aan een Teams-kanaal en vervolgens de app vanuit dat kanaal kunt openen. 

![App ingesloten in Microsoft Teams](./media/open-app-embedded-in-teams/embedded-app.png)

Als u zich niet hebt geregistreerd voor PowerApps, kunt u zich hier [gratis registreren](https://web.powerapps.com/signup?redirect=marketing&email=) voordat u begint.

## <a name="prerequisites"></a>Vereisten

Als u deze procedure wilt volgen, moet u over een [Office 365-abonnement](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) en een [kanaal in Teams](https://www.youtube.com/watch?v=he2f1quaR7M) beschikken.

## <a name="sign-in-to-powerapps"></a>Meld u aan bij PowerApps

Meld u aan bij PowerApps op [https://web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="add-an-app"></a>Een app toevoegen

1. Selecteer in Microsoft Teams een team en een kanaal onder dat team. In dit voorbeeld is het kanaal **Algemeen** onder het team **Bedrijfsontwikkeling**.

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. Kies **+** om een tabblad toe te voegen.

    ![](./media/open-app-embedded-in-teams/teams-add-tab.png)

3. Kies in het dialoogvenster **Een tabblad toevoegen** de optie **PowerApps**.

    ![](./media/open-app-embedded-in-teams/add-a-tab.png)

4. Kies **Voorbeeld-apps** > **Productoverzicht** > **Opslaan**.

    ![](./media/open-app-embedded-in-teams/select-an-app.png)

    De app is nu beschikbaar voor gebruik in het kanaal.

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

> [!NOTE]
> U moet uw eigen apps [delen](../maker/canvas-apps/share-app.md) voordat u ze aan Teams toevoegt (voorbeeld-apps worden standaard gedeeld).

## <a name="open-an-app"></a>Een app openen

1. Kies in Microsoft Teams het team en het kanaal waarin de app is opgenomen.

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. Kies het tabblad **Productoverzicht**.

    ![](./media/open-app-embedded-in-teams/open-tab.png)

    De app wordt geopend in het kanaal.

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

## <a name="known-issues"></a>Bekende problemen

In de bureaublad-app voor Microsoft Teams:

* Apps moeten inhoud, zoals afbeeldingen en PDF-bestanden, laden via een beveiligde verbinding (https).
* Niet alle sensoren, zoals **Versnelling**, **Kompas** en **Locatie**, worden ondersteund.
* Alleen deze audio-indelingen worden ondersteund: AAC, H264, OGG Vorbis en WAV.

## <a name="clean-up-resources"></a>Resources opschonen

Als u de app uit het kanaal wilt verwijderen, kiest u het tabblad **Productoverzicht** > **Verwijderen**.

## <a name="next-steps"></a>Volgende stappen

In dit onderwerp hebt u de voorbeeld-app Productoverzicht toegevoegd aan een Teams-kanaal en vervolgens de app vanuit dat kanaal geopend. Ga verder met de PowerApps-zelfstudie voor meer informatie over PowerApps.

> [!div class="nextstepaction"]
> [PowerApps-zelfstudie](../maker/canvas-apps/get-started-create-from-blank.md)
