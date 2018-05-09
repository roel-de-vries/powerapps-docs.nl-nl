---
title: Eigenschappen voor toegankelijkheid | Microsoft Docs
description: Naslaginformatie over eigenschappen zoals TabIndex en Tooltip
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/26/2017
ms.author: fikaradz
ms.openlocfilehash: 062267a93ca625513d0280c753eefaaacd743811
ms.sourcegitcommit: 4710a56d308efe67fe60a7688143e61f5e5f2b44
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="accessibility-properties-in-powerapps"></a>Eigenschappen voor toegankelijkheid in PowerApps
Eigenschappen configureren om alternatieve manieren van communicatie mogelijk maken met besturingselementen voor gebruikers met een handicap.

### <a name="properties"></a>Eigenschappen
**AccessibleLabel**: label voor schermlezers. Door een lege waarde voor de bedieningselementen afbeelding, pictogram en vorm worden de besturingselementen onzichtbaar gemaakt voor de schermlezer en als sierelementen behandeld.

**TabIndex**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

De waarde is standaard nul, wat betekent dat de tabbladvolgorde standaard is, op basis van de XY-coördinaat van het besturingselement.  Als u een waarde groter dan nul instelt, wordt de volgorde van de tabbladen van het besturingselement aangepast.  De TabIndex-waarde 2 voor een besturingselement gaat vóór een besturingselement met de TabIndex-waarde 3 of hoger.

Bij containers met de besturingselementen Formulier en Galerie wordt altijd door alle elementen van de container gebladerd voordat wordt doorgegaan met de besturingselementen buiten de container.  De tabbladvolgorde van de container komt overeen met die van de laagste TabIndex-waarde van een onderliggend besturingselement.

Als TabIndex op -1 wordt ingesteld, wordt de toegang tot de tab via het besturingselement uitgeschakeld. Van afbeeldingen, pictogrammen en vormen worden ook niet-interactieve elementen gemaakt.
