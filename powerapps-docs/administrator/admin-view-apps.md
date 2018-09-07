---
title: Een lijst downloaden met apps die in uw omgevingen zijn gemaakt | Microsoft Docs
description: In deze snelstartgids leert u hoe u een lijst met apps kunt downloaden die in uw omgevingen zijn gemaakt.
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: jimholtz
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 8a94439a1f3de2d269600ed1894c8c3bf991d030
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42845310"
---
# <a name="download-a-list-of-apps-created-in-your-environments"></a>Een lijst downloaden met de apps die in uw omgevingen zijn gemaakt
Als u een omgevingsbeheerder bent, kunt u een lijst bekijken en downloaden met de apps die zijn gemaakt in de omgevingen die u beheert. Als u een globale beheerder van Office 365 of tenantbeheerder van Azure Active Directory bent, kunt u een lijst bekijken en downloaden met de apps die in alle omgevingen in uw organisatie zijn gemaakt.

In dit onderwerp leest u hoe u een lijst met apps die in één omgeving zijn gemaakt, downloadt naar een CSV-bestand dat u vervolgens in Excel kunt bekijken.

## <a name="prerequisites"></a>Vereisten
 Als u de stappen wilt uitvoeren, zijn de volgende items vereist:
 * Een licentie voor PowerApps Plan 2 óf voor Microsoft Flow Plan 2. U kunt zich ook aanmelden voor een [gratis proefversie van een PowerApps-abonnement 2](https://web.powerapps.com/signup?redirect=marketing&email=).
 * Machtigingen voor omgevingsbeheerder van PowerApps, globale beheerder van Office 365 of tenantbeheerder van Azure Active Directory. Zie het Engelstalige artikel [Environments administration in PowerApps](environments-administration.md) (Omgevingen beheren in PowerApps) voor meer informatie.

## <a name="sign-in-to-the-powerapps-admin-center"></a>Aanmelden bij PowerApps-beheercentrum
Meld u aan bij het beheercentrum op [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="download-the-list-of-apps"></a>De lijst met apps downloaden
1. Tik of klik in het navigatiedeelvenster op **Omgevingen** en klik of tik op de omgeving waarvoor u de lijst met apps wilt downloaden.

    ![Bestand en Delen](./media/admin-view-apps/environment.png)
2. Klik of tik op het tabblad **Resources** op **Apps** en klik of tik op **Lijst met apps downloaden**.

    ![Bestand en Delen](./media/admin-view-apps/resources-app.png)

    De lijst met apps wordt gedownload naar een CSV-bestand. Dit proces kan enkele minuten duren. Zorg ervoor dat u het venster pas sluit als de lijst volledig is gedownload. Anders kan het zijn dat u het proces opnieuw moet starten.

## <a name="view-the-list"></a>De lijst bekijken
Nadat het CSV-bestand is gemaakt, opent u het in Excel. De lijst bevat de weergavenaam van de app, de eigenaar van de app, eventuele connectors die de app gebruikt om verbinding met gegevensbronnen te maken en andere informatie.

![Bestand en Delen](./media/admin-view-apps/excel-view.png)

## <a name="next-steps"></a>Volgende stappen
In dit onderwerp hebt u geleerd hoe u een lijst downloadt en weergeeft met de apps die in een omgeving in uw organisatie zijn gemaakt. Hierna leert u hoe u de apps kunt beheren die in uw organisatie zijn gemaakt.

> [!div class="nextstepaction"]
> [De apps beheren die in uw organisatie zijn gemaakt](admin-manage-apps.md)
