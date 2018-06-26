---
title: Snelstartgids voor het downloaden van een lijst met actieve gebruikers in uw tenant | Microsoft Docs
description: In deze snelstartgids leest u hoe u een lijst met actieve gebruikers in uw tenant kunt downloaden.
author: jimholtz
ms.service: powerapps
ms.component: pa-admin
ms.topic: quickstart
ms.date: 03/21/2018
ms.author: jimh
ms.openlocfilehash: 1488b0231009ef3dd3b0b93e21a14a61f3d1c3cd
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34552479"
---
# <a name="quickstart-download-a-list-of-active-users-in-your-tenant"></a>Snelstartgids: een lijst met actieve gebruikers in uw tenant downloaden
Als u een globale beheerder van Office 365 of tenantbeheerder van Azure Active Directory bent, kunt u een lijst met actieve gebruikers in uw tenant downloaden, zodat u niet alleen kunt zien wie toegang heeft gekregen tot PowerApps en/of Microsoft Flow, maar ook de licenties kunt zien die aan deze gebruikers zijn toegewezen.

In deze snelstartgids leest u hoe u een lijst met actieve gebruikers kunt downloaden naar een CSV-bestand, dat u vervolgens in Excel kunt bekijken.

Als u de stappen in deze snelstartgids wilt volgen, moet u machtigingen voor een globale beheerder van Office 365 of tenantbeheerder van Azure Active Directory hebben.

## <a name="sign-in-to-the-powerapps-admin-center"></a>Aanmelden bij het PowerApps-beheercentrum
Meld u aan bij het beheercentrum op [https://admin.powerapps.com]([https://admin.powerapps.com).

## <a name="download-the-list-of-users"></a>De lijst met gebruikers downloaden
Klik of tik in het navigatiedeelvenster op **Gebruikerslicenties** en klik of tik op **Een lijst met actieve gebruikerslicenties downloaden**.

![Bestand en Delen](./media/admin-view-user-licenses/download-list.png)

De lijst met gebruikers wordt gedownload naar een CSV-bestand. Dit proces kan enkele minuten duren. Zorg ervoor dat u het venster pas sluit als de lijst volledig is gedownload. Anders kan het zijn dat u het proces opnieuw moet starten.

## <a name="view-the-list"></a>De lijst bekijken
Nadat het CSV-bestand is gemaakt, opent u het in Excel. De lijst bevat de naam, het e-mailadres, het type licentie en andere gegevens van elke gebruiker.

Een gebruiker die minimaal één keer toegang tot een product heeft gehad, wordt beschouwd als een *actieve gebruiker*. Omdat dit een lijst is met actieve gebruikers, worden gebruikers die een licentie voor PowerApps en Microsoft Flow hebben maar deze producten nog nooit hebben gebruikt, niet in deze lijst weergegeven. U kunt alle gebruikerslicenties bekijken via het [Office 365-beheercentrum](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

In dit voorbeeld ziet u twee gebruikers die licenties hebben voor zowel PowerApps als Microsoft Flow. Ans Jansen heeft toegang via een abonnement op Office 365 en Arnoud Schoonen heeft voor elk product een proeflicentie.

![Bestand en Delen](./media/admin-view-user-licenses/table2.png)

Als een gebruiker de organisatie heeft verlaten, wordt in de lijst de tekst **Onbekend** weergegeven in de kolommen **Gebruikersnaam** en **E-mailadres**. Als in de lijst **Onbekend** wordt weergegeven, maar niemand de organisatie heeft verlaten, wacht u enkele minuten en download u de lijst vervolgens opnieuw.

Om gebruikerslicenties toe te voegen, opent u het [Office 365-beheercentrum](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

## <a name="next-steps"></a>Volgende stappen
In deze snelstartgids hebt u gelezen hoe u een lijst met actieve gebruikers in uw tenant kunt downloaden. Als u wilt leren hoe u een lijst kunt downloaden met de apps die in uw omgevingen zijn gemaakt, gaat u door met de volgende snelstartgids.

> [!div class="nextstepaction"]
> [Een lijst downloaden met de apps die in uw omgevingen zijn gemaakt](admin-view-apps.md)
