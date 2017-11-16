---
title: Functie UpdateContext | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie UpdateContext in PowerApps
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
ms.date: 11/08/2015
ms.author: gregli
ms.openlocfilehash: 16d2ed94b44b8b0e521aa5690885fcd1617dc024
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="updatecontext-function-in-powerapps"></a>De functie UpdateContext in PowerApps
Maakt [contextvariabelen](../working-with-variables.md#create-a-context-variable) voor het huidige scherm of werkt ze bij.

## <a name="overview"></a>Overzicht
Gebruik de functie **UpdateContext** om een contextvariabele te maken die tijdelijk een stukje informatie opslaat, zoals het aantal keren dat de gebruiker een knop heeft geselecteerd of het resultaat van een gegevensbewerking.

Contextvariabelen hebben als bereik een scherm, wat betekent dat u geen formule kunt maken die verwijst naar een contextvariabele op een ander scherm. Als u wel eens een ander programmeerhulpmiddel hebt gebruikt, kunt u een contextvariabele vergelijken met een lokale variabele.  Gebruik de [**Set**-functie](function-set.md) om met globale variabelen te werken die beschikbaar zijn in uw app.  

PowerApps zijn gebaseerd op formules die automatisch opnieuw worden berekend terwijl de gebruiker de app gebruikt.  Contextverzamelingen bieden dit voordeel niet, waardoor uw app mogelijk moeilijker te ontwikkelen en te begrijpen is.  Raadpleeg [werken met variabelen](../working-with-variables.md) voordat u een contextvariabele gebruikt.

## <a name="description"></a>Beschrijving
Als u een contextvariabele wilt maken of bijwerken, geeft u één [record](../working-with-tables.md#records) door aan de functie **UpdateContext**. Geef in elke record de naam op van een [kolom](../working-with-tables.md#columns) die de naam bepaalt van de variabele en een waarde waarop u die variabele wilt instellen.

* Als u de naam opgeeft van een variabele die u eerder hebt gedefinieerd, stelt **UpdateContext** de waarde van de variabele in op de opgegeven waarde.
* Als u de naam opgeeft van een variabele die nog niet bestaat, maakt **UpdateContext** een variabele met die naam en stelt de waarde van die variabele in op de opgegeven waarde.
* Als u eerder een variabele hebt gedefinieerd, maar deze variabele niet opgeeft in deze **UpdateContext**-formule, blijft de waarde ervan ongewijzigd.

Contextvariabelen worden impliciet gemaakt met behulp van de functie **UpdateContext** of [**Navigate**](function-navigate.md).  Er is geen expliciete declaratie vereist.  Als u alle **UpdateContext-** en **Navigate-**verwijzingen naar een contextvariabele verwijdert, bestaat die contextvariabele niet meer.  Om een variabele te wissen, stelt u de waarde ervan in op het resultaat van de functie [**Blank**](function-blank.md). 

U ziet de waarden, definities en het gebruik van uw variabelen met de weergave Variabelen onder het menu Bestand in de ontwerpomgeving. 

U verwijst naar een contextvariabele in een formule door de kolomnaam van de variabele te gebruiken. Zo maakt **UpdateContext( { LogoTonen: true } )** bijvoorbeeld een contextvariabele met de naam **LogoTonen**, waarvan de waarde wordt ingesteld op **true**. Vervolgens kunt u de waarde van deze contextvariabele gebruiken door de naam **LogoTonen** te gebruiken in een formule.  U kunt **LogoTonen** gebruiken als formule voor de eigenschap **Visible** van een afbeeldingsbesturingselement en dat element weergeven of verbergen, afhankelijk van het feit of de waarde van de contextvariabele **true** of **false** is.

Zoals de voorbeelden verderop in dit onderwerp laten zien, kunnen contextvariabelen verschillende soorten informatie bevatten, waaronder de volgende:

* één waarde
* een record
* een tabel
* een verwijzing naar een object
* een resultaat van een formule

Een contextvariabele behoudt zijn waarde totdat de app wordt gesloten.  Als u een contextvariabele definieert en de waarde ervan instelt in een bepaald scherm, blijft die informatie behouden, zelfs als de gebruiker overschakelt naar een ander scherm.  Nadat de app is gesloten, gaat de waarde van de contextvariabele verloren en moet die opnieuw worden gemaakt wanneer de app wordt geladen.  

Het bereik van elke contextvariabele is een scherm. Als u een contextvariabele wilt definiëren op het ene scherm en die variabele wilt wijzigen vanaf een ander scherm, moet u een formule maken die is gebaseerd op de functie **[Navigate](function-navigate.md)**.  Of gebruik een globale variabele.

**UpdateContext** heeft geen retourwaarde en u kunt deze functie alleen gebruiken in een [gedragsformule](../working-with-formulas-in-depth.md#behavior-formulas).

## <a name="syntax"></a>Syntaxis
**UpdateContext**( *UpdateRecord* )

* *UpdateRecord* - vereist. Een record die de naam bevat van ten minste één kolom en een waarde voor die kolom. Er wordt een contextvariabele gemaakt of bijgewerkt voor elke kolom en waarde die u opgeeft.

**UpdateContext**( { *ContextVariable1*: *Value1* [, *ContextVariable2*: *Value2* [, ... ] ] } )

* *ContextVariable1* - vereist.  De naam van de contextvariabele die moet worden gemaakt of bijgewerkt.
* *Value1* - vereist.  De waarde die moet worden toegewezen aan de contextvariabele.
* *ContextVariable2*: *Value2*,... - optioneel. Aanvullende contextvariabelen die u wilt maken of bijwerken en hun waarden.

## <a name="examples"></a>Voorbeelden
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **UpdateContext( {&nbsp;Teller:&nbsp;1&nbsp;} )** |Hiermee maakt of wijzigt u de contextvariabele **Teller** en stelt u de waarde in op **1**. |**Teller** heeft de waarde **1**. U kunt verwijzen naar die variabele door de naam **Teller** in een formule te gebruiken. |
| **UpdateContext( {&nbsp;Teller:&nbsp;2&nbsp;} )** |Hiermee stelt u de waarde van de contextvariabele **Teller** uit het vorige voorbeeld in op **2**. |**Teller** heeft de waarde **2**. |
| **UpdateContext( {&nbsp;Naam:&nbsp;"Loes",&nbsp;Score:&nbsp;10&nbsp;} )** |Hiermee maakt of wijzigt u de contextvariabelen **Naam** en **Score** en stelt u de waarden in op respectievelijk **Loes** en **10**. |**Naam** heeft de waarde **Loes**, en **Score** heeft de waarde **10**. |
| **UpdateContext( {&nbsp;Persoon:&nbsp;{&nbsp;Naam:&nbsp;"Jobse", Adres:&nbsp;"Grote&nbsp;Markt&nbsp;1"&nbsp;}&nbsp;} )** |Hiermee maakt of wijzigt u de contextvariabele **Persoon** en stelt u de waarde in op een record. De record bevat twee kolommen, genaamd **Naam** en **Adres**. De waarde van de kolom **Naam** is **Jobse** en de waarde van de kolom **Adres** is **Oude Markt 1**. |**Persoon** heeft de waarde van record **{&nbsp;Naam:&nbsp;"Jobse", Adres:&nbsp;"Grote&nbsp;Markt&nbsp;1"&nbsp;}&nbsp;}**.<br><br>U kunt verwijzen naar deze record in zijn geheel met de naam **Persoon** of u kunt verwijzen naar een afzonderlijke kolom in deze record met **Persoon.Naam** of **Persoon.Adres**. |
| **UpdateContext( {&nbsp;Persoon: Patch (&nbsp;Persoon,&nbsp;{Adres:&nbsp;"Grote&nbsp;Markt&nbsp;2"&nbsp;}&nbsp;) }&nbsp;)** |Gebruikt de functie **[Patch](function-patch.md)** om de contextvariabele **Persoon** bij te werken door de waarde van de kolom **Adres** te wijzigen in **Grote Markt 2**. |**Persoon** heeft nu de waarde van record **{&nbsp;Naam:&nbsp;"Jobse", Adres:&nbsp;"Grote&nbsp;Markt&nbsp;2"&nbsp;}&nbsp;}**. |

### <a name="step-by-step-example"></a>Stapsgewijs voorbeeld
1. Noem het standaardscherm **Bron**, voeg een scherm toe en noem dit scherm **Doel**.
2. Voeg op het scherm **Bron** twee knoppen toe en stel de eigenschap **[Text](../controls/properties-core.md)** van de ene knop in op **Engels** en van de andere knop op **Spaans**.
3. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van de knop **Engels** in op deze formule:<br>**Navigate(Doel, ScreenTransition.Fade, {Taal:"Engels"})**
4. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van de knop **Spaans** in op deze formule:<br>**Navigate(Doel, ScreenTransition.Fade, {Taal:"Spaans"})**
5. Voeg een label toe aan het scherm **Doel** en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze expressie:<br>**If(Taal="Engels", "Hello!", "Hola!")**
6. Selecteer **Vormen** op het tabblad **Invoegen** op het scherm **Doel** en selecteer vervolgens de pijl terug.
7. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van de pijl terug in op deze formule:<br>**Navigate(Bron, Schermovergang.Fade)**
8. Druk op het scherm **Bron** op F5 en selecteer de knop voor een van de talen.
   
    Op het scherm **Doel** wordt het label weergegeven in de taal die overeenkomt met de geselecteerde knop.
9. Selecteer de pijl terug om terug te keren naar het scherm **Bron** en selecteer vervolgens de knop voor de andere taal.
   
    Op het scherm **Doel** wordt het label weergegeven in de taal die overeenkomt met de geselecteerde knop.
10. Druk op Esc om terug te gaan naar de standaardwerkruimte.

[Een ander voorbeeld](../add-screen-context-variables.md)

