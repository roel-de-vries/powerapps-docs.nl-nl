---
title: Een Common Data Service-database maken | Microsoft Docs
description: Maak een Common Data Service-database.
services: powerapps
documentationcenter: na
author: nimakms
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2016
ms.author: kfend
ms.openlocfilehash: a2224d97c9cfc1261e43f7d30c8d8bdd2dd6e86b
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="create-a-common-data-service-database"></a>Een Common Data Service-database maken
U kunt een database maken en apps bouwen door Common Data Service als een gegevensarchief te gebruiken. U kunt uw eigen aangepaste entiteiten maken of de vooraf gedefinieerde entiteiten gebruiken. Als u een database wilt maken, moet u eerst een omgeving maken of als beheerder aan een bestaande omgeving worden toegewezen. Daarnaast moet u aan de juiste licentie zijn toegewezen. Zie [Prijzen](pricing-billing-skus.md) voor informatie over het aanschaffen van een abonnement voor het gebruik van Common Data Service.

Er zijn drie manieren om een database te maken:

* In het beheercentrum
* In het deelvenster **Start** van powerapps.com
* In het deelvenster **Entiteiten** van powerapps.com

## <a name="create-a-database-in-the-admin-center"></a>Een database maken in het beheercentrum
1. Klik in het linkernavigatiedeelvenster van het [beheercentrum](https://admin.powerapps.com) op **Omgevingen**.
2. Selecteer de omgeving of maak zo nodig een nieuwe omgeving.
3. Klik op het tabblad **Database** op **Een database maken**. De database wordt standaard gemaakt in de open-toegangsmodus.
4. Selecteer **Toegang beperken** als u beveiliging wilt afdwingen.

## <a name="create-a-database-in-the-home-pane-of-powerappscom"></a>Een database maken in het deelvenster Start van powerapps.com
1. Klik in het linkernavigatiedeelvenster op [powerapps.com](https://web.powerapps.com) op **Start**.
2. Zoek in de sectie **Microsoft Common Data Service gebruiken** naar de knop met de naam **Database maken** of **Aan de slag**. De naam van de knop is afhankelijk van uw licentie en machtigingstoewijzingen. U hebt mogelijk geen toestemming om een database te maken in de huidige omgeving.

### <a name="create-database-in-current-environnmet"></a>Database maken in huidige omgeving
1. Klik op **Database maken**.
2. Schakel in het dialoogvenster het selectievakje **Toegang tot database beperken** in als u beveiliging wilt afdwingen.
3. Klik op **Mijn database maken**.

### <a name="get-started-by-creating-a-new-environment"></a>Beginnen door een nieuwe omgeving te maken
1. Klik op **Aan de slag**.
2. Klik in het dialoogvenster op **Nieuwe omgeving maken** om een nieuwe omgeving en database te maken.
3. Vul in het veld **Naam van de omgeving** een unieke naam in. Selecteer in het veld **Regio** de juiste regio.
4. Schakel het selectievakje **Toegang tot database beperken** in als u beveiliging wilt afdwingen.
5. Klik op **Maken**.

## <a name="create-a-database-in-the-entities-pane-of-powerappscom"></a>Maak een database in het deelvenster Entiteiten op powerapps.com
1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Common Data Service** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.
2. Klik op **Aan de slag**. De database wordt gemaakt in de open-toegangsmodus.

## <a name="open-and-restricted-databases"></a>Open en beperkte databases
Standaard wordt een database gemaakt in de open-toegangsmodus. In deze modus wordt de beveiliging voor toegang tot entiteiten niet afgedwongen. De beheerder van de omgeving kan de database instellen in de modus voor beperkte toegang. In deze modus wordt de beveiliging voor toegang tot entiteiten afgedwongen op basis van machtigingensets en rollen.

1. Klik in het linkernavigatiedeelvenster van het [beheercentrum](https://admin.powerapps.com) op **Omgevingen**.
2. Selecteer de omgeving.
3. Volg een van deze stappen op het tabblad **Database**:
   * Selecteer **Toegang beperken** om beveiliging af te dwingen.
   * Selecteer **Open toegang** om de beveiliging uit te schakelen.

## <a name="license-and-security-permissions"></a>Licentie en beveiligingsmachtigingen
Om een database te maken, moet u een beheerder in de geselecteerde omgeving zijn. Ook moet de juiste licentie aan u zijn toegewezen. In de omgeving kunt u de beveiligingsmachtigingen verder configureren voor andere gebruikers via het tabblad **Beveiliging**. Zie [Databasebeveiliging configureren](database-security.md) en [Beveiligingsmodel](https://docs.microsoft.com/en-us/common-data-service/entity-reference/security-model) voor meer informatie.

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard.  We gebruiken die kennis om Common Data Model voor onze klanten te verbeteren. De entiteits- en veldnamen die u maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, zijn niet toegankelijk voor en worden niet gebruikt door Microsoft. Ook worden de gegevens niet gerepliceerd buiten de regio waarin de database is ingericht. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht veel waarde aan uw privacy, zoals beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

