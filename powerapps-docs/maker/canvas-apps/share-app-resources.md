---
title: Resources delen die in uw canvas-app worden gebruikt | Microsoft Docs
description: Begrijpen hoe u resources deelt die uw canvas-app gebruikt in PowerApps
author: archnair
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/28/2016
ms.author: archanan
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f6adc46eafda2f5bd9798c13b292a82d567e34a7
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42831331"
---
# <a name="share-canvas-app-resources-in-powerapps"></a>Resources in een canvas-app delen in PowerApps

Voordat u [een canvas-app deelt](share-app.md), moet u de typen resources in acht nemen waarvan de app gebruikmaakt, zoals:

* entiteiten in Common Data Service for Apps

    Zie [Machtigingen voor entiteiten beheren](share-app.md#manage-entity-permissions) als u wilt weten hoe u gebruikers toegang biedt tot deze gegevens.
    
* een verbinding met een gegevensbron
* een on-premises gegevensgateway
* een aangepaste connector
* een Excel-werkmap of andere service
* een stroom

Sommige van deze resources worden automatisch gedeeld wanneer u de app deelt. Voor andere resources moet u of moeten de personen met wie u de app deelt, extra stappen uitvoeren zodat de app op de verwachte manier werkt.

U kunt ook uw verbindingen, aangepaste connectors en on-premises gegevensgateway met uw hele organisatie delen.

## <a name="connections"></a>Verbindingen

Bepaalde typen verbindingen, zoals SQL Server, worden automatisch gedeeld, maar voor andere verbindingen moeten gebruikers hun eigen verbindingen met de gegevensbron of bronnen in de app maken.

Op [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) kunt u bepalen of een verbinding automatisch wordt gedeeld, en kunt u machtigingen voor delen bijwerken. Klik of tik in de linkernavigatiebalk op **Manage**, klik of tik op **Connections** en klik of tik op een verbinding. Als het tabblad **Share** wordt weergegeven, wordt de verbinding automatisch gedeeld.

  ![Tabblad Share op pagina met verbindingsdetails](./media/share-app-resources/shared-connections.png)

## <a name="on-premises-data-gateways"></a>On-premises gegevensgateways
Als u een app met gegevens uit een on-premises bron maakt en deelt, worden de [on-premises gegevensgateway](gateway-management.md) zelf en bepaalde typen verbindingen met die gateway automatisch gedeeld. Verbindingen die niet automatisch worden gedeeld, kunt u handmatig (zoals u in de vorige sectie kunt zien) delen of u kunt gebruikers in de app vragen hun eigen verbindingen te maken. Ga als volgt te werk om de verbindingen weer te geven waarmee een gateway is geconfigureerd:

1. Open [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), klik of tik in de linkernavigatiebalk op **Manage** en klik of tik op **Gateways**.
2. Klik of tik op een gateway en klik of tik vervolgens op het tabblad **Connections**.

> [!NOTE]
> Als u een of meer verbindingen handmatig deelt, kan het zijn dat u ze in de volgende situaties opnieuw moet delen:

* U voegt een on-premises gegevensgateway toe aan een app die u al hebt gedeeld.
* U wijzigt de set met personen of groepen met wie u een app hebt gedeeld die een on-premises gegevensgateway bevat.

## <a name="custom-connectors"></a>Aangepaste connectors
Wanneer u een app deelt waarin gebruik wordt gemaakt van een aangepaste connector, wordt deze automatisch gedeeld, maar moeten gebruikers hun eigen verbindingen met de connector maken.

Op [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) kunt u de machtigingen voor een aangepaste connector weergeven of bijwerken. Klik of tik in de linkernavigatiebalk op **Manage**, klik of tik op **Connections** en klik of tik op **New connection** (in de rechterbovenhoek). Klik of tik op **Custom** en klik of tik op een aangepaste connector om de gegevens over de API weer te geven.

## <a name="excel-workbooks"></a>Excel-werkmappen
Als een gedeelde app gebruikmaakt van gegevens waartoe niet alle gebruikers toegang hebben (zoals een Excel-werkmap in een cloudopslagaccount), kunt u [de gegevens delen](share-app-data.md).

## <a name="flows"></a>Stromen
Als u een app deelt die een stroom bevat, wordt gebruikers die de app uitvoeren gevraagd de verbindingen te bevestigen of bij te werken die in de stroom worden gebruikt. Alleen de maker van de stroom kan de bijbehorende parameters aanpassen. U kunt bijvoorbeeld een stroom maken waarmee e-mail wordt verzonden naar een adres dat u opgeeft, terwijl andere gebruikers dit adres niet kunnen wijzigen.

