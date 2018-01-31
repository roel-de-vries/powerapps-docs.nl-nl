---
title: De functies Average, Max, Min, StdevP, Sum en VarP | Microsoft Docs
description: Referentie-informatie voor de functies Average, Max, Min, StdevP, Sum en VarP in PowerApps, inclusief syntaxis en voorbeelden
services: 
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/15/2017
ms.author: gregli
ms.openlocfilehash: 40cc6703b2f3467365b6fab36e390fa9ff0f1659
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="average-max-min-stdevp-sum-and-varp-functions-in-powerapps"></a>De functies Average, Max, Min, StdevP, Sum en VarP in PowerApps
Statistische functies die een groep getallen samenvatten.

## <a name="description"></a>Beschrijving
De functie **Average** berekent het gemiddelde, of rekenkundig gemiddelde, van de argumenten.

De functie **Max** zoekt de maximumwaarde.

De functie **Min** zoekt de minimumwaarde.

De functie **Sum** berekent de som van de argumenten.

De functie **StdevP** berekent de standaarddeviatie van de argumenten.

De functie **VarP** berekent de afwijking van de argumenten.

U kunt de waarden voor deze functies als volgt opgeven:

* Afzonderlijke argumenten. **Sum( 1, 2, 3 )** retourneert bijvoorbeeld 6.
* Een [tabel](../working-with-tables.md) en een formule om toe te passen op die tabel.  De statistische waarde wordt berekend op basis van de waarden van de formule voor elke [record](../working-with-tables.md#records).  

[!INCLUDE [record-scope](../includes/record-scope.md)]

Deze functies worden alleen op numerieke waarden toegepast. Andere typen waarden, zoals tekenreeksen of records, worden genegeerd. Gebruik de functie **[Value](function-value.md)** om een tekenreeks naar een getal te converteren.

De functies **Average**, **Max**, **Min** en **Sum** kunnen worden gedelegeerd wanneer ze worden gebruikt in combinatie met een [gegevensbron die het delegeren van deze functies ondersteunt](../delegation-list.md).  **StdevP** en **VarP** kunnen voor geen enkele gegevensbron worden overgedragen.  Als de delegering niet wordt ondersteund, wordt alleen het eerste gedeelte van de gegevens opgehaald, waarna de functie lokaal wordt toegepast.  Het resultaat geeft daardoor mogelijk geen volledig beeld.  U ziet tijdens het maken van de app een blauwe stip om u te herinneren aan deze beperking, zodat u waar mogelijk nog kunt overschakelen naar delegeerbare alternatieven. Zie [Overzicht van delegeren](../delegation-overview.md) voor meer informatie.

## <a name="syntax"></a>Syntaxis
**Average**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Max**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Min**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**Sum**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**StdevP**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )<br>**VarP**( *NumericalFormula1*, [ *NumericalFormula2*, ... ] )

* *NumericalFormula(s)* - vereist.  Numerieke waarden waarop de bewerking wordt toegepast.

**Average**( *Table*, *NumericalFormula* )<br>**Max**( *Table*, *NumericalFormula* )<br>**Min**( *Table*, *NumericalFormula* )<br>**Sum**( *Table*, *NumericalFormula* )<br>**StdevP**( *Table*, *NumericalFormula* )<br>**VarP**( *Table*, *NumericalFormula* )

* *Tabel* - vereist.  De tabel waarop de bewerking wordt toegepast.
* *NumericalFormula* - vereist. De formule die moet worden geëvalueerd voor elke record. Het resultaat van deze formule wordt gebruikt voor de aggregatie. U kunt kolommen van de tabel in de formule gebruiken.

## <a name="examples"></a>Voorbeelden
### <a name="step-by-step"></a>Stap voor stap
Stel dat u een [gegevensbron](../working-with-data-sources.md) met de naam **Verkoop** hebt met een kolom **KostenPerEenheid** en een kolom **VerkochteEenheden** en u de eigenschap **[Text](../controls/properties-core.md)** van een label instelt op deze functie:<br>
**Sum(Verkoop, KostenPerEenheid * VerkochteEenheden)**

Het label toont de totale verkoop door de waarden in die kolommen voor elke record te vermenigvuldigen en vervolgens de resultaten van alle records op te tellen:<br>![Totale verkoop berekenen met aantal verkochte eenheden en kosten per eenheid](./media/function-aggregates/total-sales.png)

Een ander voorbeeld: stel dat u schuifregelaars hebt met de naam **Schuifregelaar1**, **Schuifregelaar2** en **Schuifregelaar3** en een label waarvan de eigenschap **[Text](../controls/properties-core.md)** is ingesteld op deze formule:<br>
**Sum(Slider1.Value, Slider2.Value, Slider3.Value)**

Het label toont de som van alle waarden waarop de schuifregelaars zijn ingesteld.

