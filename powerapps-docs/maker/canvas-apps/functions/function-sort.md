---
title: De functies Sorteren en SorterenOpKolommen | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Sorteren en SorterenOpKolommen in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: 6ba2186e7f6618cdaa6eef8073e5f3897628ae8f
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="sort-and-sortbycolumns-functions-in-powerapps"></a>Functies Sorteren en SorterenOpKolommen in PowerApps
Sorteert een [tabel](../working-with-tables.md).

## <a name="description"></a>Beschrijving
De functie **Sorteren** sorteert een tabel op basis van een formule.  

De formule wordt geëvalueerd voor elke [record](../working-with-tables.md#records) van de tabel en de resultaten worden gebruikt om de tabel te sorteren.  De formule moet resulteren in een getal, tekenreeks of booleaanse waarde. De formule kan niet resulteren in een tabel of record.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Als u eerst op één kolom wilt sorteren en vervolgens op een andere, sluit u een **Sorteren**-formule in een andere formule in. U kunt bijvoorbeeld deze formule gebruiken om een tabel **Contactpersonen** eerst te sorteren op de kolom **Achternaam** en vervolgens op de kolom **Voornaam**:  **Sorteren( Sorteren( Contactpersonen, Achternaam ), Voornaam )**.

De functie **SorterenOpKolommen** kan ook worden gebruikt om een tabel te sorteren die is gebaseerd op een of meer kolommen.

De lijst met parameters voor **SorterenOpKolommen** bevat de namen van de kolommen waarop u wilt sorteren en de sorteerrichting per kolom.  Sorteren wordt uitgevoerd in de volgorde van de parameters (eerst gesorteerd op de eerste kolom, daarna op de tweede, enzovoort).  Kolomnamen worden opgegeven als tekenreeksen, waarbij dubbele aanhalingstekens vereist zijn indien rechtstreeks opgenomen in de lijst met parameters.  Bijvoorbeeld: **SorterenOpKolommen( TabelKlanten, "Achternaam" )**.

U kunt **SorterenOpKolommen** combineren met een besturingselement **[Vervolgkeuzelijst](../controls/control-drop-down.md)** of **[Keuzelijst](../controls/control-list-box.md)** zodat gebruikers de kolom kunnen selecteren waarop zij willen sorteren.

Naast sorteren in oplopende of aflopende volgorde, kan **SorterenOpKolommen** sorteren op basis van een tabel met één kolom met waarden.  U kunt bijvoorbeeld records sorteren op basis van de naam van een weekdag door **[ "maandag", "dinsdag", "woensdag", "donderdag", "vrijdag", "zaterdag", "zondag" ]** op te geven als sorteervolgorde.  Alle records met **maandag** komen dan eerst, gevolgd door **dinsdag**, enzovoort.  Gevonden records die niet in de sorteertabel worden weergegeven, worden aan het einde van de lijst geplaatst.

[Tabellen](../working-with-tables.md) vormen een waarde in PowerApps, net als een tekenreeks of getal.  Ze kunnen worden doorgegeven aan en geretourneerd uit functies.  **Sorteren** en **SorterenOpKolommen** wijzigen een tabel niet. In plaats daarvan gebruiken ze een tabel als argument en retourneren ze een nieuwe tabel die is gesorteerd.  Zie [working with tables (werken met tabellen)](../working-with-tables.md) voor meer informatie.

[!INCLUDE [delegation](../../../includes/delegation.md)]

## <a name="syntax"></a>Syntaxis
**Sorteren**( *Tabel*, *Formule* [, *Sorteervolgorde* ] )

* *Tabel* - vereist. Tabel die u wilt sorteren.
* *Formule* - vereist. Deze formule wordt geëvalueerd voor elke record van de tabel en de resultaten worden gebruikt om de tabel te sorteren.  U kunt verwijzen naar kolommen in de tabel.
* *Sorteervolgorde* - optioneel. Geef **Sorteervolgorde.Aflopend** op om de tabel in aflopende volgorde te sorteren. **Sorteervolgorde.Oplopend** is de standaardwaarde.

**SorterenOpKolommen**( *Tabel*, *NaamKolom1* [, *Sorteervolgorde1*, *NaamKolom2*, *Sorteervolgorde2*, ... ] )

* *Tabel* - vereist. Tabel die u wilt sorteren.
* *NaamKolom(men)* - vereist. De namen van de kolommen waarop moet worden gesorteerd, als tekenreeksen.
* *Sorteervolgorde(n)* - optioneel.  **Sorteervolgorde.Oplopend** of **Sorteervolgorde.Aflopend**.  **Sorteervolgorde.Oplopend** is de standaardinstelling.  Als meerdere *Kolomnamen* worden opgegeven, moeten alle kolommen behalve de laatste een *Sorteervolgorde* bevatten.
  
    > [!NOTE]
> Vervang elke spatie in SharePoint- en Excel-gegevensbronnen met kolomnamen met spaties door **‘\_x0020\_’**. Geef **'Naam kolom'** bijvoorbeeld op als **'Naam_x0020_kolom'**.

**SorterenOpKolommen**( *Tabel*, *NaamKolom*, *SorteervolgordeTabel* )

* *Tabel* - vereist. Tabel die u wilt sorteren.
* *NaamKolom* - vereist. De naam van de kolom waarop moet worden gesorteerd, als tekenreeksen.
* *SorteervolgordeTabel* - vereist.  Eén kolomtabel met waarden om op te sorteren.
  
    > [!NOTE]
> Vervang elke spatie in SharePoint- en Excel-gegevensbronnen met kolomnamen met spaties door **‘\_x0020\_’**. Geef **'Naam kolom'** bijvoorbeeld op als **'Naam_x0020_kolom'**.

## <a name="examples"></a>Voorbeelden
Voor de volgende voorbeelden gebruiken we de [gegevensbron](../working-with-data-sources.md) **IJsjes**, die de gegevens in deze tabel bevat:

![](media/function-sort/icecream.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Sorteren( IJsjes, Smaak )**<br><br>**SorterenOpKolommen( IJsjes, "Smaak" )** |Sorteert **IJsjes** op de kolom **Smaak**. De kolom **Smaak** bevat tekenreeksen. Hierdoor wordt de tabel alfabetisch gesorteerd. Standaard wordt oplopend gesorteerd. |<style> img { max-width: none; } </style> ![](media/function-sort/icecream-flavor.png) |
| **Sorteren( IJsjes, Aantal )**<br><br>**SorterenOpKolommen( IJsjes, "Aantal" )** |Sorteert **IJsjes** op de kolom **Aantal**.  De kolom **Aantal** bevat getallen. Hierdoor wordt de tabel numeriek gesorteerd.  Standaard wordt oplopend gesorteerd. |![](media/function-sort/icecream-quantity-asc.png) |
| **Sorteren( IJsjes, Aantal, Sorteervolgorde.Aflopend )**<br><br>**SorterenOpKolommen( IJsjes, "Aantal", Sorteervolgorde.Aflopend )** |Sorteert **IJsjes** op de kolom **Aantal**.  De kolom **Aantal** bevat getallen. De sortering verloopt dus numeriek.  De sorteervolgorde is opgegeven als Aflopend. |![](media/function-sort/icecream-quantity-desc.png) |
| **Sorteren( IJsjes, Aantal + OpBestelling )** |Sorteert **IJsjes** op de som van de kolommen **Aantal** en **OpBestelling** voor elke afzonderlijke record. De som is een getal. Hierdoor wordt de tabel numeriek gesorteerd.  Standaard wordt oplopend gesorteerd.  Omdat we op een formule sorteren en niet op onbewerkte kolomwaarden, is er geen equivalent met behulp van **SorterenOpKolommen**. |![](media/function-sort/icecream-total.png) |
| **Sorteren( Sorteren( IJsjes, OpBestelling ), Aantal )**<br><br>**SorterenOpKolommen( IJsjes, "OpBestelling", Oplopend, "Aantal", Oplopend )** |Sorteert **IJsjes** eerst op de kolom **OpBestelling** en vervolgens op de kolom **Aantal**.  Opmerking: "Pistache" was hoger vermeld dan "Vanille" bij de eerste sortering op basis van **OpBestelling**. Daarna verschoven ze naar hun juiste plaats op basis van **Aantal**. |![](media/function-sort/icecream-onorder-quantity.png) |
| **SorterenOpKolommen( IJsjes, "Smaak" [&nbsp;"Pistache",&nbsp;"Aardbei"&nbsp;] )** |Sorteert **IJsjes** op de kolom **Smaak** op basis van de tabel met één kolom die "Pistache" en "Aardbei" bevat.  Records met een **Smaak** "Pistache" wordt eerst weergegeven in het resultaat, gevolgd door records die "Aardbei" bevatten.  Waarden in de kolom **Smaak** zonder overeenkomst, zoals "Vanille", worden weergegeven na de items die wel een overeenkomst hebben. |![](media/function-sort/icecream-onflavor-sorttable.png) |

### <a name="step-by-step"></a>Stap voor stap
Als u deze voorbeelden zelf wilt uitvoeren, maakt u de gegevensbron **IJsjes** als een [verzameling](../working-with-data-sources.md#collections):

1. Voeg een knop toe en stel de eigenschap **[BijSelecteren](../controls/properties-core.md)** ervan in op deze formule:<br>**ClearCollect( IJsjes, { Smaak: "Chocolade", Aantal: 100, OpBestelling: 150 }, { Smaak: "Vanille", Aantal: 200, OpBestelling: 20 }, { Smaak: "Aardbei", Aantal: 300, OpBestelling: 0 }, { Smaak: "Muntchocolade", Aantal: 60, OpBestelling: 100 }, { Smaak: "Pistache", Aantal: 200, OpBestelling: 10 } )**
2. Bekijk een voorbeeld van de app, klik op de knop en druk op Esc om terug te keren naar de standaardwerkruimte.
3. Selecteer **Verzamelingen** in het menu **Bestand** om de verzameling weer te geven die u zojuist hebt gemaakt en druk op Esc om terug te keren naar de standaardwerkruimte.

#### <a name="sort"></a>Sorteren
1. Voeg een andere knop toe en stel de eigenschap **[BijSelecteren](../controls/properties-core.md)** ervan in op deze formule:<br>
   **ClearCollect (SorterenOpSmaak, Sorteren (IJsjes, Smaak))**
   
     De vorige formule maakt een tweede verzameling, met de naam **SorterenOpSmaak**, die dezelfde gegevens als **IJsjes** bevat. De nieuwe verzameling bevat echter de gegevens, die alfabetisch in oplopende volgorde gesorteerd zijn op de kolom **Smaak**.
2. Druk op F5, selecteer de nieuwe knop en druk op Esc.
3. Selecteer **Verzamelingen** in het menu **Bestand** om beide verzamelingen weer te geven en druk op Esc om terug te keren naar de standaardwerkruimte.
4. Herhaal de laatste drie stappen, maar wijzig de naam van de verzameling die u wilt maken en vervang de formule **Sorteren** door een andere formule uit de tabel met voorbeelden eerder in deze sectie die gebruikmaakt van **Sorteren**.

#### <a name="sortbycolumns"></a>SorterenOpKolommen
1. Voeg een andere knop toe en stel de eigenschap **[BijSelecteren](../controls/properties-core.md)** ervan in op deze formule:<br>
   **ClearCollect (SorterenOpAantal, SorterenOpKolommen (IJsjes, "Aantal", Oplopend, "Smaak", Aflopend))**
   
     De vorige formule maakt een derde verzameling, met de naam **SorterenOpAantal**, die dezelfde gegevens als **IJsjes** bevat. De nieuwe verzameling bevat echter de gegevens, numeriek gesorteerd op de kolom **Aantal** in oplopende volgorde en vervolgens op de kolom **Smaak** in aflopende volgorde.
2. Druk op F5, selecteer de nieuwe knop en druk op Esc.
3. Selecteer **Verzamelingen** in het menu **Bestand** om alle drie verzamelingen weer te geven en druk op Esc om terug te keren naar de standaardwerkruimte.
4. Herhaal de laatste drie stappen, maar wijzig de naam van de verzameling die u wilt maken en vervang de formule **SorterenOpKolommen** door een andere formule uit de tabel met voorbeelden eerder in deze sectie die gebruikmaakt van **SorterenOpKolommen**.

