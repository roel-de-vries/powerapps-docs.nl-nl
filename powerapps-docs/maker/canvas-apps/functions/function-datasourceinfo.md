---
title: De functie DataSourceInfo | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functie DataSourceInfo in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/11/2015
ms.author: gregli
ms.openlocfilehash: 696da621bfc14cd2dfd36f4a03d7e1117e07e670
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39022235"
---
# <a name="datasourceinfo-function-in-powerapps"></a>De functie DataSourceInfo in PowerApps
Biedt informatie over een [gegevensbron](../working-with-data-sources.md).

## <a name="overview"></a>Overzicht
Gegevensbronnen kunnen een schat aan informatie bieden om de gebruikerservaring te optimaliseren.

U kunt informatie op het niveau van de [kolom](../working-with-tables.md#columns) gebruiken om gebruikersinvoer te valideren en direct feedback te geven aan de gebruiker voordat u de functie **[Patch](function-patch.md)** gebruikt. De functie **[Validate](function-validate.md)** maakt gebruik van dezelfde informatie.

U kunt informatie op het niveau van de gegevensbron gebruiken om bijvoorbeeld knoppen **Bewerken** en **Nieuw** uit te schakelen of te verbergen voor gebruikers die geen machtigingen hebben om [records](../working-with-tables.md#records) te bewerken en te maken.

Gegevensbronnen variëren in de hoeveelheid informatie die ze leveren en soms leveren ze deze informatie helemaal niet.  [Verzamelingen](../working-with-data-sources.md#collections) leveren geen informatie. Als een stukje informatie niet is opgegeven, wordt er een standaardwaarde gebruikt of wordt *leeg* geretourneerd.

## <a name="description"></a>Beschrijving
### <a name="column-information"></a>Kolominformatie
U kunt **DataSourceInfo** gebruiken om informatie op te halen over een bepaalde kolom van een gegevensbron:  

| Informatieargument | Resultaattype | Beschrijving |
| --- | --- | --- |
| **DataSourceInfo.DisplayName** |Tekenreeks |Weergavenaam voor de kolom. Als er geen weergavenaam is gedefinieerd, wordt de naam van de kolom geretourneerd. |
| **DataSourceInfo.MaxLength** |Getal |Maximumaantal tekens dat de kolom kan bevatten. Alleen van toepassing op kolommen met tekenreeksen. Als er geen maximum is ingesteld, wordt *leeg* geretourneerd. |
| **DataSourceInfo.MaxValue** |Getal |Maximale numerieke waarde die een kolom kan bevatten. Alleen van toepassing op kolommen die getallen bevatten. Als er geen maximum is ingesteld, wordt *leeg* geretourneerd. |
| **DataSourceInfo.MinValue** |Getal |Minimale numerieke waarde die een kolom kan bevatten. Alleen van toepassing op kolommen die getallen bevatten. Als er geen minimum is ingesteld, wordt *leeg* geretourneerd. |
| **DataSourceInfo.Required** |Booleaans |Is er een waarde vereist voor deze kolom? Als het niet is ingesteld door de gegevensbron, wordt **false** geretourneerd. |

Het derde argument is de naam van een kolom als een tekenreeks.  Bijvoorbeeld: de kolom **Telefoonnummer** in de verzameling **Mensen** wordt doorgegeven als **"Telefoonnummer"**, inclusief de dubbele aanhalingstekens.

### <a name="data-source-information"></a>Informatie over de gegevensbron
U kunt ook **DataSourceInfo** gebruiken om informatie over een gegevensbron als geheel op te halen:  

| Informatieargument | Resultaattype | Beschrijving |
| --- | --- | --- |
| **DataSourceInfo.AllowedValues** |Booleaans |Welke typen machtigingen kunnen aan gebruikers worden verleend voor deze gegevensbron? Als de typen niet zijn ingesteld door de gegevensbron, wordt *blank* geretourneerd. |
| **DataSourceInfo.CreatePermission** |Booleaans |Heeft de huidige gebruiker rechten om records te maken in deze gegevensbron? Als het niet is ingesteld door de gegevensbron, wordt **true** geretourneerd. |
| **DataSourceInfo.DeletePermission** |Booleaans |Heeft de huidige gebruiker rechten om records te verwijderen in deze gegevensbron? Als het niet is ingesteld door de gegevensbron, wordt **true** geretourneerd. |
| **DataSourceInfo.EditPermission** |Booleaans |Heeft de huidige gebruiker rechten om records te bewerken in deze gegevensbron? Als het niet is ingesteld door de gegevensbron, wordt **true** geretourneerd. |
| **DataSourceInfo.ReadPermission** |Booleaans |Heeft de huidige gebruiker rechten om records te lezen in deze gegevensbron? Als het niet is ingesteld door de gegevensbron, wordt **true** geretourneerd. |

## <a name="syntax"></a>Syntaxis
**DataSourceInfo**( *DataSource*, *Information*, *ColumnName* )

* *DataSource* - vereist. De gegevensbron die moet worden gebruikt.
* *Information* - vereist. Het type informatie dat u wilt ophalen.
* *ColumnName* - optioneel. Voor informatie op kolomniveau, de naam van de kolom als een tekenreeks. De kolom **Telefoonnummer** wordt doorgegeven als **"Telefoonnummer"**, inclusief de dubbele aanhalingstekens. Het argument *ColumnName* kan niet worden gebruikt voor informatie op het niveau van de gegevensbron.
  
    > [!NOTE]
  > Vervang elke spatie in SharePoint- en Excel-gegevensbronnen met kolomnamen met spaties door **‘\_x0020\_’**. Geef **'Naam kolom'** bijvoorbeeld op als **'Naam_x0020_kolom'**.

## <a name="examples"></a>Voorbeelden
Voor de voorbeelden in dit gedeelte wordt de gegevensbron **IJs** gebruikt:

![](media/function-datasourceinfo/icecream.png)

De gegevensbron levert ook deze informatie:

* De weergavenaam voor **Hoeveelheid** is "Hoeveelheid in voorraad".
* De maximale lengte van **Smaak** is 30 tekens.
* De kolom **Smaak** moet een waarde bevatten. De kolom **Hoeveelheid** is niet vereist.
* De minimale **Hoeveelheid** is 0.
* De maximale **Hoeveelheid** is 100.
* De huidige gebruiker kan de records van de gegevensbron **IJs** lezen en bewerken maar kan geen records maken of verwijderen.

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.DisplayName,&nbsp;"Hoeveelheid"&nbsp;)** |Retourneert de weergavenaam voor de kolom **Hoeveelheid** van de gegevensbron **IJs**. |"Hoeveelheid in voorraad" |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.MaxLength,&nbsp;"Smaak"&nbsp;)** |Retourneert de maximale lengte van de tekenreeks voor de kolom **Smaak** van de gegevensbron **IJs**. |30 |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.Required,&nbsp;"Smaak"&nbsp;)** |Is de kolom **Smaak** van de gegevensbron **IJs** vereist? |**true** |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.Required,&nbsp;"Hoeveelheid"&nbsp;)** |Is de kolom **Hoeveelheid** van de gegevensbron **IJs** vereist? |**false** |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.MaxValue,&nbsp;"Hoeveelheid"&nbsp;)** |Retourneert de maximale numerieke waarde voor de kolom **Hoeveelheid** van de gegevensbron **IJs**. |100 |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.MinValue,&nbsp;"Hoeveelheid"&nbsp;)** |Retourneert de minimale numerieke waarde voor de kolom **Hoeveelheid** van de gegevensbron **IJs**. |0 |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.ReadPermission)** |Kan de huidige gebruiker records lezen in de gegevensbron **IJs**? |**true** |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.EditPermission)** |Kan de huidige gebruiker records bewerken in de gegevensbron **IJs**? |**true** |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.CreatePermission)** |Kan de huidige gebruiker records maken in de gegevensbron **IJs**? |**false** |
| **DataSourceInfo(&nbsp;IJs, DataSourceInfo.DeletePermission)** |Kan de huidige gebruiker records verwijderen van de gegevensbron **IJs**? |**false** |

