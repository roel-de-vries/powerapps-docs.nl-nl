---
title: Delegeerbare gegevensbronnen | Microsoft Docs
description: Een lijst met alle ondersteunde delegeerbare gegevensbronnen
services: 
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/15/2017
ms.author: archanan
ms.openlocfilehash: 94e4eaa5209bbcaf6cd191ed2dfdf27d9eab1d5f
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="delegable-data-sources"></a>Delegeerbare gegevensbronnen
Zoals uitvoerig wordt beschreven in het artikel [Delegering](delegation-overview.md), vindt delegering plaats als PowerApps de verwerking van gegevens overdraagt aan de gegevensbron in plaats van gegevens over te brengen naar de app om ze daar lokaal te verwerken.

Delegering wordt alleen ondersteund voor tabelgegevensbronnen. Deze lijst vermeldt de verschillende tabelgegevensbronnen en geeft aan of ze ondersteuning bieden voor delegering. Meer details vindt u in de volgende sectie.

* Common Data Service - **Ja**
* SharePoint - **Ja**
* SQL Server - **Ja**
* Dynamics 365 - **Ja**
* Salesforce - **Ja**
* Excel - **Binnenkort**
* Dynamics 365 for Operations - Nog niet
* Dynamics 365 for Financials - Nog niet
* Dynamics NAV - Nog niet
* Google Sheets - Nog niet

Er worden regelmatig nieuwe tabelgegevensbronnen met ondersteuning voor delegering toegevoegd.

In dit document vindt u de huidige status van ondersteunde delegering per gegevensbron.

**Vereisten**

* Bekend zijn met de inhoud van het artikel [Delegering](delegation-overview.md).

## <a name="list-of-data-sources-and-supported-delegation"></a>Lijst met gegevensbronnen en ondersteunde delegering
Deze lijst met gegevensbronnen en delegeerbare functies en predicaten wordt regelmatig bijgewerkt met de actuele status van ondersteuning voor delegering in PowerApps.

### <a name="top-level-delegable-functions"></a>Delegeerbare functies op hoogste niveau
| &nbsp; | Common Data Service | SharePoint | SQL Server | Dynamics 365 | Salesforce |
| --- | --- | --- | --- | --- | --- |
| Average |Nee |Nee |Ja |Nee |Nee |
| Filter |Ja |Ja |Ja |Ja |Ja |
| LookUp |Ja |Ja |Ja |Ja |Ja |
| Max. |Nee |Nee |Ja |Nee |Nee |
| Min |Nee |Nee |Ja |Nee |Nee |
| Search |Ja<sup>1</sup> |Nee |Ja |Ja |Ja |
| Sorteren |Ja |Ja |Ja |Ja |Ja |
| SorterenOpKolommen |Ja |Ja |Ja |Ja |Ja |
| Sum |Nee |Nee |Ja |Nee |Nee |

<sup>1</sup>Alleen voor tekenreeksvelden

### <a name="filter-and-lookup-delegable-predicates"></a>Delegeerbare predicaten van Filter en LookUp
| &nbsp; | Common Data Service | SharePoint | SQL Server | Dynamics 365 | Salesforce |
| --- | --- | --- | --- | --- | --- |
| Not |Ja |Nee |Ja |Ja |Ja |
| IsBlank |Nee |Nee |Ja |Ja |Nee |
| TrimEnds |Nee |Nee |Ja |Nee |Nee |
| Len |Nee |Nee |Ja |Nee |Nee |
| +, - |Nee |Nee |Ja |Nee |Nee |
| <, <=, =, <>, >, >= |Ja |Ja (alleen =) |Ja |Ja |Ja |
| And (&&), Or (&#124;&#124;), Not (!) |Ja<sup>2</sup> |Ja (behalve Not(!)) |Ja |Ja |Ja |
| in |Nee |Nee |Ja |Nee |Ja |
| StartsWith |Nee |Ja |Nee |Nee |Nee |

<sup>2</sup>Alleen voor operatoren. Functie And/Or/Not niet gedelegeerd.

