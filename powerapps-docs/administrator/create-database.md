---
title: Een Common Data Service-database maken | Microsoft Docs
description: Maak een Common Data Service-database.
services: powerapps
documentationcenter: na
author: manasmams
manager: kfend
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 2215d02af78d0983292cfca8c9f8ac4f6737a3d0
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="create-a-common-data-service-database"></a>Een Common Data Service-database maken
U kunt een database maken en apps bouwen door Common Data Service als een gegevensarchief te gebruiken. U kunt uw eigen aangepaste entiteiten maken of de vooraf gedefinieerde entiteiten gebruiken. Als u een database wilt maken, moet u eerst een omgeving maken of als **omgevingsbeheerder** aan een bestaande omgeving worden toegewezen. Daarnaast moet u aan de juiste licentie zijn toegewezen. Zie [Prijzen](pricing-billing-skus.md) voor informatie over het aanschaffen van een abonnement voor het gebruik van Common Data Service.

Er zijn drie manieren om een database te maken:

* Via het PowerApps-beheercentrum
* In het deelvenster **Entiteiten** van powerapps.com

## <a name="create-a-database-in-the-admin-center"></a>Een database maken in het beheercentrum
1. Klik in het linkernavigatiedeelvenster van het [beheercentrum](https://admin.powerapps.com) op **Omgevingen**.
    
2. Selecteer de omgeving waarin u de database wilt maken.
    
    ![](./media/create-database/environment-list-new.png)

3. Klik op het tabblad **Details** op **Een database maken**. 
    
    ![](./media/create-database/Create-DB-From-Details.png)

4. Kies de valuta en de taal om door te gaan met het maken van de database. 
    
    ![](./media/create-database/DB-Choose-options.png)



## <a name="create-a-database-in-the-entities-pane-of-powerappscom"></a>Maak een database in het deelvenster Entiteiten op powerapps.com
1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

2. Klik op **Database maken** om de database te maken.

    ![](./media/create-database/Create-DB-From-Entities.png)


## <a name="security-model-for-the-databases"></a>Beveiligingsmodel voor de databases
Wanneer een database wordt gemaakt, behouden de gebruikers aan wie de omgevingsrollen zijn toegewezen de bevoegdheden voor deze rollen.  
    Gebruikers met de rol **Omgevingsbeheerder** worden nu toegewezen aan de rol **Systeembeheerder**. Gebruikers met de rol **Omgevingsmaker** blijven in het bezit van dezelfde rol.

U kunt extra gebruikers aan de vooraf gedefinieerde rollen toewijzen of [aangepaste rollen][1] maken. Zie het Engelstalige artikel [Database Security](create-database.md) (Databasebeveiliging) voor meer informatie.

> [!NOTE]
> Wanneer u de database maakt, wordt de beveiligingsgroep die aan de rol Omgevingsbeheerder of de rol Omgevingsmaker is toegewezen, niet meer gebruikt. Op dit moment wordt de AAD-beveiligingsgroep niet ondersteund wanneer u machtigingen in de database toewijst.


## <a name="license-and-security-permissions"></a>Licentie en beveiligingsmachtigingen
Om een database te maken, moet u een beheerder in de geselecteerde omgeving zijn. Ook moet de juiste licentie aan u zijn toegewezen. In de omgeving kunt u de beveiligingsmachtigingen verder configureren voor andere gebruikers via het tabblad **Beveiliging**. Zie [Databasebeveiliging configureren](database-security.md) en [Beveiligingsmodel](https://docs.microsoft.c../maker/common-data-service/entity-reference/security-model) voor meer informatie.

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard.  We gebruiken die kennis om Common Data Model voor onze klanten te verbeteren. De entiteits- en veldnamen die u maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, zijn niet toegankelijk voor en worden niet gebruikt door Microsoft. Ook worden de gegevens niet gerepliceerd buiten de regio waarin de database is ingericht. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht veel waarde aan uw privacy, zoals beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).


<!--Reference links in article-->
[1]: https://technet.microsoft.com/library/dn531130.aspx
