---
title: Eigenschappen voor toegankelijkheid | Microsoft Docs
description: Naslaginformatie over eigenschappen zoals TabIndex en Tooltip
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 01/26/2017
ms.author: fikaradz
ms.openlocfilehash: 94d15ff14ccd57ccc392eae47b6c10d6cec50bb1
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825206"
---
# <a name="accessibility-properties-in-powerapps"></a>Eigenschappen voor toegankelijkheid in PowerApps
Eigenschappen configureren om alternatieve manieren van communicatie mogelijk maken met besturingselementen voor gebruikers met een handicap.

### <a name="properties"></a>Eigenschappen
**AccessibleLabel**: label voor schermlezers. Door een lege waarde voor de bedieningselementen afbeelding, pictogram en vorm worden de besturingselementen onzichtbaar gemaakt voor de schermlezer en als sierelementen behandeld.

**TabIndex**: de navigatievolgorde op het toetsenbord ten opzichte van andere besturingselementen.

De waarde is standaard nul, wat betekent dat de tabbladvolgorde standaard is, op basis van de XY-coördinaat van het besturingselement.  Als u een waarde groter dan nul instelt, wordt de volgorde van de tabbladen van het besturingselement aangepast.  De TabIndex-waarde 2 voor een besturingselement gaat vóór een besturingselement met de TabIndex-waarde 3 of hoger.

Bij containers met de besturingselementen Formulier en Galerie wordt altijd door alle elementen van de container gebladerd voordat wordt doorgegaan met de besturingselementen buiten de container.  De tabbladvolgorde van de container komt overeen met die van de laagste TabIndex-waarde van een onderliggend besturingselement.

Als TabIndex op -1 wordt ingesteld, wordt de toegang tot de tab via het besturingselement uitgeschakeld. Van afbeeldingen, pictogrammen en vormen worden ook niet-interactieve elementen gemaakt.
