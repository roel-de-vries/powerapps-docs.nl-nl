---
title: Functies Back en Navigate | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Navigate en Back in PowerApps
documentationcenter: na
author: gregli-msft
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/08/2015
ms.author: gregli
ms.openlocfilehash: e00ee9b3a58bf3255b9f581f405381af05aa07f9
ms.sourcegitcommit: 6d9fe9967841e381b108a7fb53c9057e295336ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948567"
---
# <a name="back-and-navigate-functions-in-powerapps"></a>De functies Back en Navigate in PowerApps
Wijzigen welk scherm wordt weergegeven.

## <a name="overview"></a>Overzicht
De meeste apps bevatten meerdere schermen.  Gebruik de functies **Back** en **Navigate** om te wijzigen welk scherm wordt weergegeven. Stel bijvoorbeeld de eigenschap **[OnSelect](../controls/properties-core.md)** van een knop in op een formule die de functie **Navigate** bevat als u een ander scherm wilt weergeven wanneer een gebruiker die knop selecteert. In die formule kunt u een visuele overgang, zoals **Fade**, opgeven om te bepalen hoe het ene scherm overgaat naar het andere.  

**Back** en **Navigate** wijzigen alleen welk scherm wordt weergegeven. Schermen die momenteel niet worden weergegeven, blijven werken achter de schermen. U kunt formules maken die verwijderen naar eigenschappen van besturingselementen op een ander scherm. Een gebruiker kan bijvoorbeeld de waarde van een schuifregelaar op het ene scherm wijzigen, navigeren naar een ander scherm dat die waarde in een formule gebruikt en zien hoe dit van invloed is op het nieuwe scherm.  De gebruiker kan vervolgens terugkeren naar het oorspronkelijke scherm en zien dat de schuifregelaar zijn waarde heeft behouden.

[Contextvariabelen](../working-with-variables.md#create-a-context-variable) blijven ook behouden wanneer een gebruiker tussen schermen navigeert. U kunt **Navigate** gebruiken om een of meer contextvariabelen in te stellen voor het scherm dat de formule weergeeft. Dit is de enige manier om een contextvariabele buiten het scherm in te stellen. U kunt deze methode gebruiken om parameters door te geven aan een scherm. Als u een ander programmeerhulpmiddel gebruikt, is deze methode vergelijkbaar met het doorgeven van parameters aan procedures.

## <a name="description"></a>Beschrijving
### <a name="back"></a>Back
De functie **Back** geeft het scherm weer dat het meest recent is weergegeven. U geeft geen argumenten op voor deze functie.

### <a name="navigate"></a>Navigate
In het eerste argument geeft u de naam op van het scherm dat moet worden weergegeven.  

 In het tweede argument geeft u op hoe het oude scherm overgaat naar het nieuwe scherm:

| Overgangsargument | Beschrijving |
| --- | --- |
| **ScreenTransition.Cover** |Het nieuwe scherm schuift in beeld en bedekt het huidige scherm. |
| **ScreenTransition.Fade** |Het oude scherm vervaagt, waarna het nieuwe scherm zichtbaar wordt. |
| **ScreenTransition.None** |Het oude scherm wordt snel vervangen door het nieuwe scherm. |
| **ScreenTransition.UnCover** |Het oude scherm schuift uit beeld, waardoor het nieuwe scherm verschijnt. |

U kunt **Navigate** gebruiken om contextvariabelen van het nieuwe scherm te maken of bij te werken. Als optioneel derde argument kunt u een [record](../working-with-tables.md#records) doorgeven die de naam van de contextvariabele bevat als [kolom](../working-with-tables.md#columns)naam en de nieuwe waarde voor de contextvariabele.  Deze record is dezelfde als de record die u gebruikt met de functie **[UpdateContext](function-updatecontext.md)**.

Stel de eigenschap **[OnHidden](../controls/control-screen.md)** van het oude scherm, de eigenschap **[OnVisible](../controls/control-screen.md)** van het nieuwe scherm of beide in om extra wijzigingen aan te brengen tijdens de overgang. De eigenschap **App.ActiveScreen** wordt bijgewerkt om de wijziging te weerspiegelen.

**Back** retourneert normaal **true**, maar retourneert **false** als de gebruiker op het eerste scherm is en er geen vorig scherm is.  **Navigate** retourneert normaal **true** , maar retourneert **false** als er een probleem met een van de argumenten.

U kunt deze functies alleen gebruiken binnen een [gedragsformule](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaxis
**Back**()

**Navigate**( *Screen*, *Transition* [, *UpdateContextRecord* ] )

* *Screen* - vereist. Het scherm dat moet worden weergegeven.
* *Transition* - vereist.  De visuele overgang tussen het huidige scherm en het volgende scherm. Bekijk de lijst met geldige waarden voor dit argument eerder in dit onderwerp.
* *UpdateContextRecord* - optioneel.  Een record die de naam bevat van ten minste één kolom en een waarde voor elke kolom. Deze record werkt de contextvariabelen van het nieuwe scherm bij alsof het is doorgegeven aan de functie **[UpdateContext](function-updatecontext.md)**.

## <a name="examples"></a>Voorbeelden

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Navigate( Details, ScreenTransition.None )** |Geeft het scherm **Details** weer zonder overgang en zonder de waarde van een contextvariabele te wijzigen. |Het scherm **Details** wordt snel weergegeven. |
| **Navigate( Details, ScreenTransition.Fade )** |Geeft het scherm **Details** weer met de overgang **Fade**.  Er wordt geen waarde van een contextvariabele gewijzigd. |Het huidige scherm vervaagt terwijl het scherm **Details** verschijnt. |
| **Navigate( Details, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;} )** |Geeft het scherm **Details** weer met de overgang **Fade** en werkt de waarde van de contextvariabele **ID** bij naar **12**. |Het huidige scherm vervaagt terwijl het scherm **Details** verschijnt en de contextvariabele **ID** op dat scherm wordt ingesteld op **12**. |
| **Navigate( Details, ScreenTransition.Fade, {&nbsp;ID:&nbsp;12&nbsp;,&nbsp;Tint:&nbsp;Color.Red&nbsp;} )** |Geeft het scherm **Details** weer met de overgang **Fade**. Werkt de waarde van de contextvariabele **ID** bij naar **12** en werkt de waarde van de contextvariabele **Tint** bij naar **Color.Red**. |Het huidige scherm vervaagt terwijl het scherm **Details** verschijnt. De contextvariabele **ID** op het scherm **Details** wordt ingesteld op **12** en de contextvariabele **Tint** wordt ingesteld op **Color.Red**. Als u de eigenschap **Fill** van een besturingselement op het scherm **Details** instelt op **Tint**, wordt dat besturingselement rood weergegeven. |

### <a name="step-by-step"></a>Stap voor stap
1. Geef het standaardscherm de naam **Standaardscherm**, voeg er een label aan toe en stel de eigenschap **[Text](../controls/properties-core.md)** van dat label zo in dat **Standaard** wordt weergegeven.
2. Voeg een scherm toe en noem het **ToegevoegdScherm**.
3. Voeg een label toe aan **ToegevoegdScherm** en stel de eigenschap **[Text](../controls/properties-core.md)** van het label in op **Toevoegen**.
4. Voeg een knop toe aan **ToegevoegdScherm** en stel de eigenschap **[OnSelect](../controls/properties-core.md)** ervan in op deze functie:<br>**Navigate(Standaardscherm, ScreenTransition.Fade)**
5. Druk op **ToegevoegdScherm** op F5 en selecteer vervolgens de knop.<br>**Standaardscherm** wordt weergegeven.

[Een ander voorbeeld](../add-screen-context-variables.md)

