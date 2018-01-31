---
title: Gebruikerslicenties weergeven | Microsoft Docs
description: Beheerders kunnen een lijst met gebruikerslicenties voor PowerApps en Microsoft Flow downloaden
services: 
suite: powerapps
documentationcenter: na
author: manasmamsft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/02/2017
ms.author: manasma
ms.openlocfilehash: bc3d1c94deec6cf5e7c0ba5b73e65cab67d3ee25
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="identify-powerapps-users-in-your-organization"></a>Gebruikers van PowerApps in uw organisatie identificeren
Als u een globale beheerder voor Office 365 of een tenantbeheerder voor Azure Active Directory bent, kunt u een lijst downloaden van gebruikers in uw organisatie die niet alleen een licentie hebben om PowerApps en/of Microsoft Flow te gebruiken, maar ook daadwerkelijk een van deze producten hebben gebruikt. De lijst bevat de naam, het e-mailadres, het type licentie en andere gegevens van elke gebruiker. Een gebruiker kan bijvoorbeeld het volgende hebben:

* een proeflicentie voor PowerApps of Microsoft Flow
* toegang tot beide producten via een Office 365-licentie
* toegang tot beide producten via een Dynamics 365-licentie
* toegang via PowerApps- en Microsoft Flow-abonnementen

### <a name="download-the-list-of-users"></a>De lijst met gebruikers downloaden
1. Klik of tik in het beheercentrum van PowerApps op **Gebruikerslicenties** aan de linkerkant.
   
    > [!IMPORTANT]
> Deze optie is alleen beschikbaar voor globale beheerders van Office 365 en tenantbeheerders van Azure Active Directory.
   
    ![Bestand en Delen](./media/admin-view-user-licenses/leftnav.png)
2. Klik of tik op **Een lijst met actieve gebruikerslicenties downloaden**.
   
    ![Bestand en Delen](./media/admin-view-user-licenses/download-list.png)
   
    Het downloaden van het bestand kan een paar minuten duren. Wacht enkele minuten totdat het CSV-bestand is gedownload en open dit vervolgens in Excel.
   
    > [!NOTE]
> Als u het venster sluit voordat het downloaden van het bestand is voltooid, moet u het proces wellicht opnieuw opstarten.

In dit voorbeeld ziet u twee gebruikers die op verschillende manieren licenties hebben verkregen voor zowel PowerApps als Microsoft Flow. Maria Beukema heeft toegang via een abonnement op Office 365 en Arnoud Wolthuis heeft voor elk product een proeflicentie gekregen.

![Bestand en Delen](./media/admin-view-user-licenses/table2.png)

Deze lijst bevat geen gebruikers die wel licenties hebben voor PowerApps en Microsoft Flow, maar deze nog nooit hebben gebruikt. U kunt alle gebruikerslicenties bekijken via het [Office 365-beheercentrum][1].

Als een gebruiker de organisatie heeft verlaten, wordt in de lijst **Onbekend** weergegeven in kolommen zoals **Gebruikersnaam** en **E-mail**adres. Als in de lijst **Onbekend** wordt weergegeven, maar niemand de organisatie heeft verlaten, wacht u enkele minuten en download u de lijst vervolgens opnieuw.

Om gebruikerslicenties toe te voegen, opent u het [Office 365-beheercentrum][1].

<!--Reference links in article-->
[1]:https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc
