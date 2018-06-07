---
title: Overzicht van de Power BI-verbinding | Microsoft Docs
description: De beschikbare Power BI-verbindingen weergeven
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/12/2016
ms.author: lanced
ms.openlocfilehash: a3a5d24efffd7cd3c9430cafd5050dc96632ee76
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803162"
---
# <a name="connect-to-power-bi-from-powerapps"></a>Verbinding maken met Power BI vanuit PowerApps
![Power BI](./media/connection-powerbi/powerbiicon.png)

Power BI is een pakket business analytics-hulpprogramma's waarmee u gegevens kunt analyseren en inzichten kunt delen. U kunt uw bedrijf bewaken en snel antwoorden krijgen met uitgebreide dashboards die op elk apparaat beschikbaar zijn. In uw app kunt u de status controleren van de gegevenswaarschuwingen die u hebt ingesteld in de Power BI-service. Ga naar de [documentatiepagina](https://https://docs.microsoft.com/power-bi/service-set-data-alerts) voor meer informatie over gegevenswaarschuwingen in Power BI.

In dit onderwerp ziet u hoe u de Power BI-verbinding in een app kunt gebruiken en vindt u een overzicht van de beschikbare functies.

## <a name="prerequisites"></a>Vereisten
* [Aanmelden](https://web.powerapps.com)
* De Power BI-[verbinding](https://powerapps.microsoft.com/tutorials/add-manage-connections/) moet zijn toegevoegd
* U hebt een app gemaakt op basis van een [sjabloon](https://powerapps.microsoft.com/tutorials/get-started-test-drive/), op basis van [gegevens](https://powerapps.microsoft.com/tutorials/get-started-create-from-data/) of u hebt een [volledig nieuwe](https://powerapps.microsoft.com/tutorials/get-started-create-from-blank/) app gemaakt

## <a name="use-the-power-bi-connection-in-your-app"></a>De Power BI-verbinding in uw app gebruiken
### <a name="list-the-alerts-that-youve-set-up-in-the-power-bi-service"></a>De waarschuwingen weergeven die u in de Power BI-service hebt ingesteld
1. Selecteer **Gallery** in het menu **Insert** en voeg een van de **tekstgalerieën** toe.
2. Als u de waarschuwingen van de huidige gebruiker wilt weergeven, stelt u de eigenschap [Items](../controls/properties-core.md) van de galerie in op de volgende formule:
   
   `PowerBI.GetAlerts()`

De galerie wordt bijgewerkt met de lijst met waarschuwingen. Voor elke waarschuwing ontvangt u de naam van de waarschuwing, het id-nummer van de waarschuwing en de id van de groepswerkruimte waarin de waarschuwing is geconfigureerd. U hebt de waarschuwings-id nodig als u meer informatie over de waarschuwing wilt.

### <a name="view-the-status-of-an-alert"></a>De status van een waarschuwing weergeven
Als u de status van de waarschuwing wilt weergeven, roept u de functie CheckAlertStatus aan met de waarschuwings-id die u met de bovenstaande stap hebt opgehaald.

De waarschuwings-id kan worden doorgegeven als een letterlijke tekenreeks (bijvoorbeeld 1234) of als een verwijzing naar een galeriesectie die wordt ingevuld met de GetAlerts()-aanroep (bijvoorbeeld Gallery1.Selected.alertId).

Als u wilt doorgaan, voegt u een label toe en stelt u de bijbehorende eigenschap [Text](../controls/properties-core.md) in op een van deze formules:

* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).alertTitle`
* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).currentTileValue`
* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).alertThreshold`
* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).isAlertTriggered`

Het label wordt bijgewerkt met de huidige status van de waarschuwing.

## <a name="view-the-available-functions"></a>De beschikbare functies weergeven
Deze verbinding bevat de volgende functies:

| Functienaam | Beschrijving |
| --- | --- |
| GetAlerts |De waarschuwingen weergeven die u in de Power BI-service hebt ingesteld |
| CheckAlertStatus |De status van een bepaalde waarschuwing controleren |

## <a name="getalerts"></a>GetAlerts
De waarschuwingen weergeven die u in de Power BI-service hebt ingesteld

#### <a name="input-properties"></a>Invoereigenschappen
Geen.

#### <a name="output-properties"></a>Uitvoereigenschappen
| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| value |Matrix |Nee |Een matrix met de gegevenswaarschuwingen die u in de Power BI-service hebt ingesteld. Elk element in de matrix omvat: <ul><li>alertTitle: de titel van de waarschuwing</li><li>alertId: de id van de waarschuwing</li><li>groupId: de id van de groep waarin de waarschuwing is gemaakt</li></ul> |

## <a name="checkalertstatus"></a>CheckAlertStatus
De status van een waarschuwing weergeven.

> [!NOTE]
> Aanvragen naar dit eindpunt worden per waarschuwing beperkt bij te veel aanroepen.

#### <a name="input-properties"></a>Invoereigenschappen
| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| alertId |Geheel getal |Ja |De id van de waarschuwing, zoals geretourneerd door GetAlerts |

#### <a name="output-properties"></a>Uitvoereigenschappen
| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| tileValue |Getal |Nee |De waarde van de tegel wanneer de waarschuwing is geactiveerd |
| tileUrl |Tekenreeks |Nee |URL voor de tegel die de waarschuwing bevat |
| alertTitle |Tekenreeks |Nee |Naam van de waarschuwing |
| isAlertTriggered |Booleaanse waarde |Nee |Hiermee wordt aangegeven of de waarschuwing momenteel wordt geactiveerd |
| alertThreshold |Getal |Nee |De drempelwaarde op basis waarvan de waarschuwing wordt geactiveerd |

## <a name="helpful-links"></a>Nuttige koppelingen
Bekijk alle [beschikbare verbindingen](../connections-list.md).  
Meer informatie over het [toevoegen van verbindingen](../add-manage-connections.md) aan uw apps.

