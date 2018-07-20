---
title: Functies Concat en Concatenate | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Concat en Concatenate in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 2ead46b4b34e2013205a412eacd86197a3c3b552
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39015818"
---
# <a name="concat-and-concatenate-functions-in-powerapps"></a>De functies Concat en Concatenate in PowerApps
Voegt afzonderlijke tekenreeksen of tekst en tekenreeksen samen in [tabellen](../working-with-tables.md).

## <a name="description"></a>Beschrijving
De functie **Concat** voegt de resultaten samen van een formule die is toegepast op alle [records](../working-with-tables.md#records) van een tabel, wat resulteert in een enkele tekenreeks. Gebruik deze functie om een overzicht van de tekenreeksen van een tabel te maken, zoals de functie **[Sum](function-aggregates.md)** doet voor getallen.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Gebruik de functie **[Split](function-split.md)** om een tekenreeks te splitsen in een tabel met subtekenreeksen.

De functie **Concatenate** voegt afzonderlijke tekenreeksen en een tabel met één kolom met tekenreeksen samen. Als u deze functie op afzonderlijke tekenreeksen toepast, heeft deze functie een vergelijkbare uitwerking als de **&** [operator](operators.md). U kunt een formule gebruiken die de functie **[ShowColumns](function-table-shaping.md)** bevat om een tabel met één kolom te maken vanuit een tabel met meerdere kolommen.

## <a name="syntax"></a>Syntaxis
**Concat**( *Table*, *Formula* )

* *Tabel* - vereist.  De tabel waarop de bewerking wordt toegepast.
* *Formule* - vereist.  De formule om toe te passen op alle records van de tabel.

**Concatenate**( *String1* [, *String2*, ...] )

* *String(s)* - vereist.  Een combinatie van afzonderlijke tekenreeksen of een tabel met één kolom met tekenreeksen.

## <a name="examples"></a>Voorbeelden
#### <a name="concat"></a>Concat
1. Voeg een besturingselement van het type **[Button](../controls/control-button.md)** toe en stel de bijbehorende eigenschap **[OnSelect](../controls/properties-core.md)** in op deze formule:
   
    **Collect(Producten, {Snaar:"Viool", Blaas:"Trombone", Slag:"Bongo"}, {Snaar:"Cello", Blaas:"Trompet", Slag:"Tamboerijn"})**
2. Druk op F5, klik op de knop en druk op Esc om terug te keren naar de ontwerpwerkruimte.
3. Voeg een besturingselement van het type **[Label](../controls/control-text-box.md)** toe en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze formule:
   
    **Concat(Producten, Snaar & " ")**
   
    Het label toont **Viool Cello**.

#### <a name="concatenate"></a>Samenvoegen
1. Voeg een besturingselement van het type **[Tekstinvoer](../controls/control-text-input.md)** toe en geef het de naam **Auteurnaam**.
2. Voeg een besturingselement van het type **[Label](../controls/control-text-box.md)** toe en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze formule:<br>
   **Concatenate ("Door ", Auteurnaam.Tekst)**
3. Typ uw naam in **Auteurnaam**.
   
    Het label toont **Door** gevolgd door uw naam.

Als u een tabel **Werknemers** hebt met een kolom **Voornaam** en een kolom **Achternaam**, voegt deze formule de gegevens in elke rij van deze kolommen samen.
<br>**Concatenate(Werknemers.Voornaam, " ", Werknemers.Achternaam)**

