---
title: Snelstartgids voor het maken van een beleid ter preventie van gegevensverlies (DLP) | Microsoft Docs
description: In deze snelstartgids leest u hoe u een beleid ter preventie van gegevensverlies (DLP) kunt maken in PowerApps.
services: powerapps
suite: powerapps
documentationcenter: na
author: SKjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: quickstart
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: sharik
ms.openlocfilehash: 651510bbe4ed71dbdb267ebee04e10ea13d36e15
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-create-a-data-loss-prevention-dlp-policy"></a>Snelstartgids: een beleid ter preventie van gegevensverlies (DLP) maken
Als u de gegevens in uw organisatie wilt beschermen, kunt u in PowerApps een beleid ter preventie van gegevensverlies (DLP) maken waarmee wordt bepaald met welke consumentenconnectors zakelijke gegevens mogen worden gedeeld. Met dit beleid wordt gedefinieerd hoe gegevens mogen worden gedeeld. Het beleid wordt aangeduid als beleid ter preventie van gegevensverlies (DLP). Met een DLP-beleid zorgt u ervoor dat gegevens in uw organisatie op uniforme wijze worden beheerd en voorkomt u dat belangrijke zakelijke gegevens onbedoeld naar connectors zoals socialemediasites worden gepubliceerd.

In deze snelstartgids leert u hoe u een DLP-beleid kunt maken waarmee wordt voorkomen dat gegevens die in de Common Data Service- en SharePoint-databases zijn opgeslagen, naar Twitter worden gepubliceerd.

## <a name="prerequisites"></a>Vereisten
Als u de stappen in deze snelstartgids wilt volgen, zijn de volgende items vereist:
* PowerApps-abonnement 2 of Flow-abonnement 2. U kunt zich ook aanmelden voor een [gratis proefversie van PowerApps-abonnement 2](https://web.powerapps.com/signup?redirect=marketing&email=).
* Machtigingen voor omgevingsbeheerder van PowerApps, tenantbeheerder van Azure Active Directory en machtigingen voor ten minste één omgeving. Zie het Engelstalige artikel [Environments administration in PowerApps](environments-administration.md) (Omgevingen beheren in PowerApps) voor meer informatie.

## <a name="sign-in-to-the-powerapps-admin-center"></a>Aanmelden bij PowerApps-beheercentrum
Meld u aan bij het beheercentrum op [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="create-a-dlp-policy"></a>Een DLP-beleid maken
1. Klik of tik in het navigatiedeelvenster op **Gegevensbeleid** en klik of tik op **Nieuw beleid**.

    ![](./media/create-dlp-policy/new-data-policy.png)
2. Voer als naam voor het gegevensbeleid **Beveiligde gegevenstoegang voor Contoso** in.
3. Selecteer op het tabblad **Omgevingen** een omgeving in de vervolgkeuzelijst en klik of tik op **Doorgaan**.

    ![](./media/create-dlp-policy/select-environment.png)
4. Klik of tik op het tabblad **Gegevensgroepen** onder **Alleen zakelijke gegevens** op **Toevoegen**.

    ![](./media/create-dlp-policy/data-groups.png)
5. Selecteer in het venster **Connectoren toevoegen** de optie **Common Data Service** en vervolgens **SharePoint** (het kan zijn dat u omlaag moet schuiven) en klik of tik op **Connectoren toevoegen** om ze toe te voegen aan de gegevensgroep **Alleen zakelijke gegevens**.

    ![](./media/create-dlp-policy/add-connectors.png)

    De connectors kunnen zich in slechts één gegevensgroep tegelijk bevinden en worden standaard toegevoegd aan de groep **Geen zakelijke gegevens toegestaan**. Als u Common Data Service en SharePoint naar de groep **Alleen zakelijke gegevens** verplaatst, voorkomt u dat gebruikers stromen en apps kunnen maken waarin deze twee connectors worden gecombineerd met een van de connectors in de groep **Geen zakelijke gegevens toegestaan**.
6. Klik op **Beleid opslaan**.

    ![](./media/create-dlp-policy/save-policy.png)

Het beleid Beveiligde gegevenstoegang voor Contoso is gemaakt en wordt weergegeven in de lijst met beleidsregels ter preventie van gegevensverlies. Omdat de Twitter-connector zich in de gegevensgroep **Geen zakelijke gegevens toegestaan** bevindt, zorgt dit beleid ervoor dat Common Data Service en SharePoint geen gegevens met Twitter delen.

Beheerders wordt aangeraden een lijst met DLP-beleidsregels met hun organisatie te delen, zodat gebruikers op de hoogte zijn van de regels voordat ze apps maken.

## <a name="next-steps"></a>Volgende stappen
In deze snelstartgids hebt u geleerd hoe u een DLP-beleid kunt maken om te voorkomen dat belangrijke zakelijke gegevens onbedoeld worden gepubliceerd naar connectors zoals Twitter. Als u meer wilt weten over DLP-beleidsregels, leest u het onderstaande artikel voor informatie over het beheer van deze regels.

> [!div class="nextstepaction"]
> [Beleid ter preventie van gegevensverlies (DLP) beheren](prevent-data-loss.md)
