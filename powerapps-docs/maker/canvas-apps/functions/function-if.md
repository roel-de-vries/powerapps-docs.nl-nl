---
title: De functies If en Switch | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies If en Switch in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/24/2017
ms.author: gregli
ms.openlocfilehash: 5293cd448d96633e2d8d2cda9dfbd6d3c162c953
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39017382"
---
# <a name="if-and-switch-functions-in-powerapps"></a>De functies If en Switch in PowerApps
Hiermee wordt bepaald of een voorwaarde in een set true is (**If**) of dat het resultaat van een formule overeenkomt met een willekeurige waarde in een set (**Switch**). Vervolgens wordt een resultaat geretourneerd of een actie uitgevoerd.

## <a name="description"></a>Beschrijving
De functie **If** test één of meer voorwaarden totdat een **true** resultaat is gevonden. Als een dergelijk resultaat wordt gevonden, wordt er een overeenkomende waarde geretourneerd. Als een dergelijk resultaat niet wordt gevonden, wordt er een standaardwaarde geretourneerd. In beide gevallen kan de geretourneerde waarde een tekenreeks die u kunt weergeven, een formule die u kunt evalueren of een ander soort resultaat zijn.

De functie **Switch** evalueert een formule en bepaalt of het resultaat overeenkomt met een waarde in een volgorde die u opgeeft. Als er een overeenkomst wordt gevonden, wordt er een overeenkomende waarde geretourneerd. Als er geen overeenkomst wordt gevonden, wordt er een standaardwaarde geretourneerd. In beide gevallen kan de geretourneerde waarde een tekenreeks die u kunt weergeven, een formule die u kunt evalueren of een ander soort resultaat zijn.

**If** en **Switch** zijn vergelijkbaar, maar het is raadzaam om de aanbevolen functie te gebruiken voor uw situatie:

* Gebruik **If** om één voorwaarde evalueren. De meestvoorkomende syntaxis voor deze functie is **If**( *Condition*, *ThenResult*, *DefaultResult* ). Dit resulteert in het veelvoorkomende patroon 'if ...  then … else …' dat in andere programmeertools te zien is.
* Gebruik **If** om meerdere niet-gerelateerde voorwaarden te evalueren. In PowerApps (in tegenstelling tot Microsoft Excel) kunt u meerdere voorwaarden opgeven zonder **If**-formules te moeten nesten.
* Gebruik **Switch** om één voorwaarde te evalueren ten opzichte van meerdere mogelijke overeenkomsten. U kunt in dit geval ook **If** gebruiken, maar dan moet u de formule herhalen voor elke mogelijke overeenkomst.

U kunt beide functies gebruiken in [gedragformules](../working-with-formulas-in-depth.md) om vertakkingen te maken tussen twee of meer acties. Slechts één vertakking activeert een actie. Voorwaarden en overeenkomsten worden op volgorde geëvalueerd en het proces wordt gestopt als een voorwaarde **true** is of er een overeenkomst is gevonden.

*Blank* wordt geretourneerd als geen voorwaarden **true** zijn, er geen overeenkomsten zijn gevonden en u geen standaardresultaat opgeeft.

## <a name="syntax"></a>Syntaxis
**If**( *Condition*, *ThenResult* [, *DefaultResult* ] )<br>**If**( *Condition1*, *ThenResult1* [, *Condition2*, *ThenResult2*, ... [ , *DefaultResult* ] ] )

* *Condition(s)* - vereist. Formule(s) om te controleren op **true**. Deze formules bevatten gewoonlijk vergelijkings-[operators](operators.md) (zoals **<**, **>** en **=**) en testfuncties zoals **[IsBlank](function-isblank-isempty.md)** en **[IsEmpty](function-isblank-isempty.md)**.
* *ThenResult(s)* - vereist. De overeenkomstige waarde die voor een voorwaarde moet worden geretourneerd en die wordt beoordeeld als **true**.
* *DefaultResult* - optioneel. De waarde die moet worden geretourneerd als geen voorwaarden **true** is.  Als u dit argument niet opgeeft, wordt *blank* geretourneerd.

**Switch**( *Formula*, *Match1*, *Result1* [, *Match2*, *Result2*, ... [, *DefaultResult* ] ] )

* *Formule* - vereist. De formule die moet worden geëvalueerd op overeenkomsten.  Deze formule wordt slechts één keer geëvalueerd.
* *Match(s)* - vereist. Waarden die moeten worden vergeleken met het resultaat van *Formula*.  Als een exacte overeenkomst wordt gevonden, wordt het bijbehorende *Result* geretourneerd.
* *Result(s)* - vereist. De overeenkomstige waarde die moet worden geretourneerd wanneer er een exacte overeenkomst is gevonden.
* *DefaultResult* - optioneel. Als er geen exacte overeenkomst wordt gevonden, wordt deze waarde geretourneerd. Als u dit argument niet opgeeft, wordt *blank* geretourneerd.

## <a name="examples"></a>Voorbeelden
### <a name="values-in-formulas"></a>Waarden in formules
In de volgende voorbeelden heeft een **schuifregelaar** met de naam **Schuifregelaar1** een waarde van **25**.

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Als( Schuifregelaar1.Value&nbsp;=&nbsp;25, "Result1" )** |De voorwaarde is **true** en het bijbehorende resultaat wordt geretourneerd. |"Result1" |
| **Als( Schuifregelaar1.Value&nbsp;=&nbsp;25, "Result1", "Result2" )** |De voorwaarde is **true** en het bijbehorende resultaat wordt geretourneerd. |"Result1" |
| **Als( Schuifregelaar1.Value&nbsp;>&nbsp;1000, "Result1" )** |De voorwaarde is **false** en er is geen *DefaultResult* opgegeven. |*leeg* |
| **If( Schuifregelaar1.Waarde&nbsp;>&nbsp;1000, "Result1", "Result2" )** |De voorwaarde is **false**, er is een *DefaultResult* opgegeven en deze wordt geretourneerd. |"Result2" |
| **Als( Schuifregelaar1.Waarde&nbsp;=&nbsp;25, "Result1", Schuifregelaar1.Value&nbsp;>&nbsp;0, "Result2" )** |De eerste voorwaarde is **true** en het bijbehorende resultaat wordt geretourneerd. De tweede voorwaarde is ook **true**, maar deze wordt niet geëvalueerd omdat deze later in de lijst met argumenten staat dan een voorwaarde die wordt geëvalueerd als **true**. |"Result1" |
| **If( IsBlank(&nbsp;Schuifregelaar1.Value&nbsp;), "Result1", IsNumeric(&nbsp;Schuifregelaar1.Value&nbsp;), "Result2" )** |De eerste voorwaarde is **false** omdat de schuifregelaar niet *leeg* is. De tweede voorwaarde is **true** omdat de waarde van de schuifregelaar een getal is; het bijbehorende resultaat wordt geretourneerd. |"Result2" |
| **If( Schuifregelaar1.Value&nbsp;>&nbsp;1000, "Result1", Schuifregelaar1.Value&nbsp;>&nbsp;50, "Result2", "Result3")** |Zowel de eerste als de tweede voorwaarde is **false** en *DefaultResult* is opgegeven en geretourneerd. |"Result3" |
| **Switch( Schuifregelaar1.Value, 25, "Result1" )** |De waarde van de schuifregelaar komt overeen met de eerste waarde die moet worden gecontroleerd en het bijbehorende resultaat wordt geretourneerd. |"Result1" |
| **Switch( Schuifregelaar1.Value, 20, "Result1", 25, "Result2", 30, "Result3" )** |De waarde van de schuifregelaar komt overeen met de tweede waarde die moet worden gecontroleerd en het bijbehorende resultaat wordt geretourneerd. |"Result2" |
| **Switch( Schuifregelaar1.Value, 20, "Result1", 10, "Result2", 0, "Result3", "DefaultResult" )** |De waarde van de schuifregelaar komt niet overeen met een van de waarden die worden gecontroleerd.  Een *DefaultResult* is opgegeven, dus deze wordt geretourneerd. |"DefaultResult" |

### <a name="branching-in-behavior-formulas"></a>Vertakkingen in gedragsformules
In deze voorbeelden is in een **[Tekstinvoer](../controls/control-text-input.md)**-besturingselement met de naam **FirstName** de waarde 'John' getypt.

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Als( ! IsBlank( Voornaam.Text ), Navigate(&nbsp;Scherm1, Schermovergang.None) )** |De voorwaarde is **true** dus de functie **[Navigate](function-navigate.md)** wordt uitgevoerd. U kunt de functie **[IsBlank](function-isblank-isempty.md)** gebruiken om te testen of een verplicht formulierveld is ingevuld.  Als **Voornaam** [leeg](function-isblank-isempty.md) was, zou deze formule geen effect hebben. |**true**<br><br>De weergave wordt gewijzigd naar **Scherm1**. |
| **If( IsBlank( Voornaam.Text ), Navigate(&nbsp;Scherm1, Schermovergang.None), Terug() )** |Zonder de operator **!** is de voorwaarde **false**, dus wordt de functie **[Navigate](function-navigate.md)** niet uitgevoerd. De functie **[Terug](function-navigate.md)** is opgegeven als een *DefaultResult*, dus deze wordt uitgevoerd. |**true**<br><br>De weergave gaat terug naar het scherm dat eerder werd weergegeven. |
| **Switch( Voornaam.Text, "Carlos", Navigate(&nbsp;Scherm1, Schermovergang.None ), "Kirstin", Navigate( Scherm2, Schermovergang.None ), "John", Navigate( Scherm3, Schermovergang.None ) )** |De waarde van **Voornaam.Text** wordt vergeleken met 'Carlos', 'Kirstin' en 'John', in die volgorde. Er is een overeenkomst gevonden met 'John', dus de app navigeert naar **Scherm3**. |**true**<br><br>De weergave wordt gewijzigd naar **Scherm3**. |

### <a name="step-by-step"></a>Stap voor stap
1. Voeg een **[Tekstinvoer](../controls/control-text-input.md)**-besturingselement toe en noem het **Tekst1** als het die naam niet standaard al heeft.
2. Typ in **Tekst1** **30**.
3. Voeg een besturingselement van het type **Label** toe en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze formule:<br>
   **If( Value(Text1.Text) < 20, "Bestel VEEL meer!", Value(Text1.Text) < 40, "Bestel meer!", Text1.Text )**
   
    In het besturingselement **Label** wordt **Bestel meer!** weergegeven omdat de waarde van **Tekst1** hoger is dan 20, maar lager dan 40.
4. Typ in **Tekst1** **15**.
   
    In het besturingselement **Label** wordt **Bestel VEEL meer!** weergegeven omdat de waarde van **Tekst1** lager is dan 20.
5. Typ in **Tekst1** **50**.
   
    Het besturingselement **Label** geeft de waarde weer die u hebt getypt, omdat deze hoger is dan 40.

