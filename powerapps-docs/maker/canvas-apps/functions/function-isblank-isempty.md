---
title: Functies Blank, Samenvoegen, IsBlank en IsEmpty | Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies Blank, Samenvoegen, IsBlank en IsEmpty in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 07/24/2017
ms.author: gregli
ms.openlocfilehash: 80d06a30dbe334f7fa9691d2a56805d53876693c
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="blank-coalesce-isblank-and-isempty-functions-in-powerapps"></a>Functies Blank, Samenvoegen, IsBlank en IsEmpty in PowerApps
Hiermee wordt getest of een waarde leeg is of een [tabel](../working-with-tables.md) geen [records](../working-with-tables.md#records) bevat. Dit biedt een manier om *lege* waarden te maken.

## <a name="overview"></a>Overzicht
*Blank* (leeg) is een tijdelijke aanduiding voor "geen waarde" of "onbekende waarde". Een besturingselement van het type **[Tekstinvoer](../controls/control-text-input.md)** is *leeg* als de gebruiker er geen tekens in heeft getypt. Hetzelfde besturingselement is niet langer *leeg* zodra de gebruiker er een teken in typt.  Sommige gegevensbronnen kunnen NULL-waarden opslaan en retourneren. Deze worden in PowerApps weergegeven als *leeg*.

> [!NOTE]
> Het opslaan van *lege* waarden wordt op dit moment alleen ondersteund voor lokale verzamelingen. We weten dat veel gegevensbronnen *lege* waarden (NULL) ondersteunen. Deze beperking wordt zo snel mogelijk opgelost.

Elke eigenschap of berekende waarde kan *leeg* zijn.  Een booleaanse waarde heeft bijvoorbeeld normaal een van de twee waarden: **true** of **false**.  Naast deze twee waarden kan hij echter ook *leeg* zijn.  Dit is vergelijkbaar met Microsoft Excel, waar een werkbladcel in eerste instantie leeg is, maar onder andere de waarden **true** of **false** kan bevatten. De inhoud van de cel kan op elk gewenst moment worden verwijderd, waarna hij terugkeert naar een *lege* staat.

*Empty* (leeg) geldt specifiek voor tabellen die geen records bevatten. De tabelstructuur is mogelijk intact, inclusief [kolom](../working-with-tables.md#columns)namen, maar er zijn geen gegevens in de tabel. Een tabel kan mogelijk in eerste instantie leeg zijn, records bevatten en niet langer leeg zijn, waarna de records worden verwijderd en hij opnieuw leeg is.

## <a name="description"></a>Beschrijving
De functie **Blank** retourneert een *lege* waarde. Hiermee wordt een NULL-waarde opgeslagen in een gegevensbron die ondersteuning biedt voor deze waarden, waardoor een waarde uit het veld wordt verwijderd.

De functie **IsBlank** test op een *blank*-waarde. Deze *lege* waarden worden gevonden in situaties zoals de onderstaande:

* De geretourneerde waarde van de functie **Blank**.
* Er is geen formule voor de eigenschap van een besturingselement ingesteld.
* Er is geen waarde in een besturingselement voor tekstinvoer getypt of er is geen selectie gemaakt in een keuzelijst. U kunt **IsBlank** gebruiken om feedback te geven dat een veld verplicht is.
* Een tekenreeks die geen tekens bevat, heeft een **[Len](function-len.md)** van 0.
* Er is een fout opgetreden in een functie. Vaak was een van de argumenten voor de functie niet geldig. Veel functies retourneren *leeg* als de waarde van een argument *leeg* is.
* Verbonden [gegevensbronnen](../working-with-data-sources.md), zoals SQL Server, kunnen mogelijk "null"-waarden gebruiken. Deze waarden worden in PowerApps als *leeg* weergegeven.
* Het *anders*-gedeelte van een **[Als](function-if.md)**-functie was niet gespecificeerd en alle voorwaarden waren **false**.
* U gebruikte de functie **[Update](function-update-updateif.md)**, maar gaf geen waarde op voor alle kolommen. Daardoor werden geen waarden geplaatst in de kolommen die u niet hebt gespecificeerd.

De functie **Samenvoegen** evalueert de argumenten op volgorde en retourneert de eerste waarde die niet *leeg* is.  Gebruik deze functie om een *lege* waarde te vervangen door een andere waarde, waarbij niet-*lege* waarden niet worden gewijzigd.  De functie retourneert *leeg* als alle argumenten *leeg* zijn.  Alle argumenten voor **Samenvoegen** moeten van hetzelfde type zijn. U kunt bijvoorbeeld geen cijfers combineren met tekenreeksen.  **Samenvoegen( waarde1, waarde2 )** is de meer beknopte equivalent van **If( IsBlank( waarde1 ) waarde1, waarde2 )** en vereist geen dubbele evaluatie van **waarde1**.  

De functie **IsEmpty** test of een tabel records bevat. Hij is gelijk aan het gebruik van de functie **[CountRows](function-table-counts.md)** en controleren op nul. U kunt controleren op fouten in een gegevensbron door **IsEmpty** te combineren met de functie **[Errors](function-errors.md)**.

De resulterende waarde voor zowel **IsBlank** als **IsEmpty** is de booleaanse waarde **true** of **false**.

## <a name="syntax"></a>Syntaxis
**Blank**()

**Samenvoegen**( *Waarde1* [, *Waarde2*, ... ] )

* *Waarde(n)* – Vereist. Te testen waarden.  Elke waarde wordt op volgorde geëvalueerd totdat een niet-*lege* waarde wordt gevonden.  Waarden achter de eerste niet-*lege* waarde worden niet geëvalueerd.  

**IsBlank**( *Value* )

* *Value* - vereist. Te testen waarde.

**IsEmpty**( *Table* )

* *Tabel* - vereist. Tabel die u wilt testen voor records.

## <a name="examples"></a>Voorbeelden
### <a name="blank"></a>Blank
> [!NOTE]
> Op dit moment is het volgende voorbeeld alleen van toepassing op lokale verzamelingen.  We weten dat veel gegevensbronnen *lege* waarden (NULL) ondersteunen. Deze beperking wordt zo snel mogelijk opgelost.

1. Maak een volledig nieuwe app en voeg een besturingselement van het type **Knop** toe.
2. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van de knop in op deze formule:
   
    **ClearCollect( Steden, { Naam: "Seattle", Weer: "Regenachtig" } )**
3. Klik of tik op de knop die u hebt toegevoegd om een voorbeeld te bekijken van uw app en sluit vervolgens het voorbeeld.  
4. Klik of tik in het menu **File** op **Verzamelingen**.
   
     De verzameling **Steden** wordt weergegeven, met daarin één record met "Seattle" en "Regenachtig":
   
    ![Verzameling met Seattle en weer Regenachtig](./media/function-isblank-isempty/seattle-rainy.png)
5. Klik of tik op de pijl naar links om terug te gaan naar de standaardwerkruimte.
6. Voeg een besturingselement van het type **Label** toe en stel de eigenschap **Text** in op deze formule:
   
    **IsBlank( First( Steden ).Weer )**
   
    Het label heeft de status **false**, omdat het veld **Weer** een waarde bevat ("Regenachtig").
7. Voeg een tweede knop toe en stel de eigenschap **OnSelect** ervan in op deze formule:
   
    **Patch( Steden, First( Steden ), { Weer: Blank() } )**
8. Klik of tik op de knop die u hebt toegevoegd om een voorbeeld te bekijken van uw app en sluit vervolgens het voorbeeld.  
   
    Het veld **Weer** van de eerste record in **Steden** is vervangen door een *leeg* veld, waardoor "Regenachtig" is verwijderd.
   
    ![Verzameling met Seattle en veld Weer leeg](./media/function-isblank-isempty/seattle-blank.png)
   
    Het label heeft de status **true**, omdat het veld **Weer** geen waarde bevat.

### <a name="coalesce"></a>Samenvoegen
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Samenvoegen( Blank(), 1 )** |De geretourneerde waarde van de functie **Blank** wordt getest. Deze retourneert altijd een *lege* waarde. Omdat het eerste argument *leeg* is, wordt de evaluatie van het volgende argument voortgezet totdat een niet-*lege* waarde is gevonden. |**1** |
| **Samenvoegen( Blank(), Blank(), Blank(), Blank(), 2, 3 )** |**Samenvoegen** begint aan het begin van de lijst met argumenten en evalueert elk argument totdat er een niet-*lege* waarde is gevonden.  In dit geval retourneren de eerste vier argumenten allemaal *leeg*. De evaluatie wordt dus voortgezet met het vijfde element. Het vijfde argument is niet *leeg*. Daarom stopt de evaluatie hier. De waarde van het vijfde argument wordt geretourneerd en het zesde argument wordt niet geëvalueerd. |**2** |

### <a name="isblank"></a>IsBlank
1. Maak een hele nieuwe app en voeg een besturingselement voor tekstinvoer toe met de naam **Voornaam**.
2. Voeg een label toe en stel de eigenschap **[Text](../controls/properties-core.md)** in op deze formule:
   
    **If( IsBlank( Voornaam.Text ), "Voornaam is een verplicht veld." )**
   
    De eigenschap **[Text](../controls/properties-core.md)** van een besturingselement voor tekstinvoer is standaard ingesteld op **"Tekstinvoer"**. Omdat de eigenschap een waarde bevat, is deze niet leeg en toont het label geen bericht.
3. Verwijder alle tekens, inclusief eventuele spaties, uit het besturingselement voor tekstinvoer.
   
    Omdat de eigenschap **[Text](../controls/properties-core.md)** geen tekens meer bevat, is deze *leeg* en heeft **IsBlank( Voornaam.Text )** de status **true**. Het bericht voor een verplicht veld wordt weergegeven.

Zie de functie **[Validate](function-validate.md)** en [werken met gegevensbronnen](../working-with-data-sources.md) voor meer informatie over het uitvoeren van validatie met behulp van andere hulpprogramma's.  

Andere voorbeelden:

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **IsBlank( Blank() )** |De geretourneerde waarde van de functie **Blank** wordt getest. Deze retourneert altijd een *lege* waarde. |**true** |
| **IsBlank( "" )** |Een tekenreeks die geen tekens bevat. |**true** |
| **IsBlank( "Hallo" )** |Een tekenreeks die een of meer tekens bevat. |**false** |
| **IsBlank( *AnyCollection* )** |Omdat de [verzameling](../working-with-data-sources.md#collections) bestaat, is hij niet leeg, zelfs al zou hij geen records bevatten. Gebruik in plaats daarvan **IsEmpty** om te controleren op een lege verzameling. |**false** |
| **IsBlank( Mid( "Hallo", 17, 2 ) )** |Het eerste teken voor **[Mid](function-left-mid-right.md)** ligt voorbij het einde van de tekenreeks.  Het resultaat is een lege tekenreeks. |**true** |
| **IsBlank( If( false, false ) )** |Een **[If](function-if.md)**-functie zonder *ElseResult*.  Omdat de voorwaarde altijd **false** is, retourneert deze **[If](function-if.md)** altijd *leeg*. |**true** |

### <a name="isempty"></a>IsEmpty
1. Maak een volledig nieuwe app en voeg een besturingselement van het type **Knop** toe.
2. Stel de eigenschap **[OnSelect](../controls/properties-core.md)** van de knop in op deze formule:
   
    **Collect( IJs, { Smaak: "Aardbei", Hoeveelheid: 300 }, { Smaak: "Chocola", Hoeveelheid: 100 } )**
3. Klik of tik op de knop die u hebt toegevoegd om een voorbeeld te bekijken van uw app en sluit vervolgens het voorbeeld.  
   
    Er wordt een verzameling met de naam **IJs** gemaakt die de volgende gegevens bevat:
   
    ![](media/function-isblank-isempty/icecream-strawberry-chocolate.png)
   
    Deze verzameling heeft twee records en is niet leeg. **IsEmpty( IJs )** retourneert **false** en **CountRows( IJs )** retourneert **2**.
4. Voeg een tweede knop toe en stel de eigenschap **[OnSelect](../controls/properties-core.md)** ervan in op deze formule:
   
    **Clear( IJs )**
5. Klik of tik op de tweede knop om een voorbeeld te bekijken van uw app en sluit vervolgens het voorbeeld.  
   
    De verzameling is nu leeg:
   
    ![](media/function-isblank-isempty/icecream-clear.png)
   
    De functie **[Wissen](function-clear-collect-clearcollect.md)** verwijdert alle records uit een verzameling, wat een lege verzameling oplevert. **IsEmpty( IJs )** retourneert **true** en **CountRows( IJs )** retourneert **0**.

U kunt, zoals deze voorbeelden aantonen, **IsEmpty** ook gebruiken om te testen of een berekende tabel leeg is:

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **IsEmpty( [&nbsp;1,&nbsp;2,&nbsp;3 ] )** |De tabel met één kolom bevat drie records en is daarom niet leeg. |**false** |
| **IsEmpty( [&nbsp;] )** |De tabel met één kolom bevat geen records en is leeg. |**true** |
| **IsEmpty( Filter( [&nbsp;1,&nbsp;2,&nbsp;3&nbsp;], Waarde > 5 ) )** |De tabel met één kolom bevat geen waarden die groter zijn dan 5.  Het resultaat van het filter bevat geen records en is leeg. |**true** |

