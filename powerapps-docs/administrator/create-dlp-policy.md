---
title: Een beleid ter preventie van gegevensverlies (DLP) maken | Microsoft Docs
description: In deze snelstartgids leest u hoe u een beleid ter preventie van gegevensverlies (DLP) kunt maken in PowerApps.
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/30/2018
ms.author: jimholtz
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 2ebacd128846e45cc936e3f66560f6fcf27d50b8
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42840675"
---
# <a name="create-a-data-loss-prevention-dlp-policy"></a>Een beleid ter preventie van gegevensverlies (DLP) maken
Als u de gegevens in uw organisatie wilt beschermen, kunt u in PowerApps een beleid ter preventie van gegevensverlies (DLP) maken waarmee wordt bepaald met welke consumentenconnectors zakelijke gegevens mogen worden gedeeld. Met dit beleid wordt gedefinieerd hoe gegevens mogen worden gedeeld. Het beleid wordt aangeduid als beleid ter preventie van gegevensverlies (DLP). Met een DLP-beleid zorgt u ervoor dat gegevens in uw organisatie op uniforme wijze worden beheerd en voorkomt u dat belangrijke zakelijke gegevens onbedoeld naar connectors zoals socialemediasites worden gepubliceerd.

In dit onderwerp leest u hoe u een DLP-beleid voor één omgeving maakt om te voorkomen dat gegevens die in uw Common Data Service- en SharePoint-databases zijn opgeslagen op Twitter worden gepubliceerd.

## <a name="prerequisites"></a>Vereisten
Voor het uitvoeren van de stappen is **één** van de volgende items vereist:
* Machtiging als tenantbeheerder van Azure Active Directory
* Globale beheerdersmachtigingen voor Office 365
* Machtiging voor omgevingsbeheer voor PowerApps plus een PowerApps-abonnement 2, Microsoft Flow-Abonnement 2 of een [PowerApps-abonnement 2](https://web.powerapps.com/signup?redirect=marketing&email=) proeflicentie

Zie [Omgevingen beheren in PowerApps](environments-administration.md) voor meer informatie.

## <a name="sign-in-to-the-powerapps-admin-center"></a>Aanmelden bij PowerApps-beheercentrum
Meld u aan bij het beheercentrum op [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="create-a-dlp-policy"></a>Een DLP-beleid maken
1. Klik of tik in het navigatiedeelvenster op **Gegevensbeleid** en klik of tik op **Nieuw beleid**.

    ![](./media/create-dlp-policy/new-data-policy.png)
2. Het veld **Naam van het gegevensbeleid** wordt automatisch ingevuld met een naam gebaseerd op de tijd en datum waarop het beleid is gemaakt. Vervang dit door **Beveiligde gegevenstoegang voor Contoso**.

    ![](./media/create-dlp-policy/policy-name.png)
3. De opties voor het tabblad **Omgevingen** verschillen afhankelijk van of u een omgevingsbeheerder of een tenantbeheerder bent. Selecteer indien u een omgevingsbeheerder bent een omgeving in de vervolgkeuzelijst en klik of tik daarna op **Doorgaan**.

    ![](./media/create-dlp-policy/select-environment.png)

    Indien u een tenantbeheerder bent kunt u DLP-beleid maken dat van toepassing is op één of meerdere omgevingen, of op alle omgevingen binnen de tenant (inclusief de omgevingen die gemaakt zijn met een proeflicentie). Klik of tik voor dit onderwerp op **ALLEEN toepassen op geselecteerde omgevingen**, selecteer een omgeving in de vervolgkeuzelijst en klik of tik daarna op **Doorgaan**.

    ![](./media/create-dlp-policy/select-environment-tenant.png)

    Merk op dat DLP-beleid voor omgevingen tenantbreed DLP-beleid niet kan overschrijven.
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
In dit onderwerp hebt u geleerd hoe u een DLP-beleid maakt voor één omgeving om te voorkomen dat belangrijke bedrijfsgegevens per ongeluk worden gepubliceerd op connectors zoals Twitter. Als u meer wilt weten over DLP-beleidsregels, leest u het onderstaande artikel voor informatie over het beheer van deze regels.

> [!div class="nextstepaction"]
> [Beleid ter preventie van gegevensverlies (DLP) beheren](prevent-data-loss.md)
