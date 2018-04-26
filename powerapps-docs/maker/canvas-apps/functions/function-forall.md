---
title: De functie ForAll | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie ForEach in PowerApps
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
ms.openlocfilehash: 7df5e270e92930fa494ec8a30a59d46d022fd915
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="forall-function-in-powerapps"></a>De functie ForAll in PowerApps
Berekent waarden en voert acties uit voor alle [records](../working-with-tables.md#records) van een [tabel](../working-with-tables.md).

## <a name="description"></a>Beschrijving
De functie **ForAll** evalueert een formule voor alle records van een tabel.  De formule kan een waarde berekenen en/of acties uitvoeren, zoals het wijzigen van gegevens of het werken met een verbinding.

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

### <a name="return-value"></a>Retourwaarde
Het resultaat van elke formule-evaluatie wordt in een tabel geretourneerd in dezelfde volgorde als de invoertabel.

Als het resultaat van de formule één waarde is, zal de resulterende tabel een tabel met één kolom zijn.  Als het resultaat van de formule een record is, zal de resulterende tabel records bevatten met dezelfde kolommen als de resultaatrecord.  

Als het resultaat van de formule een *lege* waarde is, zal er geen record voor die invoerrecord in de resultaattabel zijn.  In dit geval zullen er minder records in de resultaattabel staan dan in de brontabel.

### <a name="taking-action"></a>Actie uitvoeren
De formule kan functies bevatten die actie ondernemen, zoals het wijzigen van de records van een gegevensbron met de functies **[Patch](function-patch.md)** en **[Verzamelen](function-clear-collect-clearcollect.md)**.  De formule kan ook methoden aanroepen bij verbindingen.  Met de [**;**-operator](operators.md) kunnen meerdere acties per record worden uitgevoerd. U kunt de tabel die het onderwerp van de functie **ForAll** vormt niet wijzigen.

Houd bij het opstellen van uw formule in gedachten dat records in elke willekeurige volgorde en, indien mogelijk, parallel kunnen worden verwerkt.  De eerste record van de tabel kan mogelijk na de laatste record worden verwerkt.  Wees voorzichtig om afhankelijkheden in de volgorde te voorkomen.  U kunt daarom niet de functies **[UpdateContext](function-updatecontext.md)**, **[Wissen](function-clear-collect-clearcollect.md)** en **[ClearCollect](function-clear-collect-clearcollect.md)** in een **ForAll**-functie gebruiken omdat ze gemakkelijk kunnen worden gebruikt om variabelen te bevatten die vatbaar zijn voor dit effect.  U kunt **[Verzamelen](function-clear-collect-clearcollect.md)** gebruiken, maar de volgorde waarin de records worden toegevoegd, is niet gedefinieerd.

Verschillende functies die gegevensbronnen kunnen wijzigen, inclusief **Verzamelen**, **Verwijderen** en **Bijwerken**, retourneren de gewijzigde gegevensbron als hun geretourneerde waarde.  Deze geretourneerde waarden kunnen groot zijn en aanzienlijke bronnen gebruiken als ze voor elke record van de tabel **ForAll** worden geretourneerd.  Mogelijk merkt u ook dat deze geretourneerde waarden niet aan uw verwachtingen voldoen omdat **ForAll** parallel kan werken en de neveneffecten van deze functies mogelijk kan scheiden, zodat hun resultaat niet wordt behaald.  Als de geretourneerde waarde van **ForAll** niet daadwerkelijk wordt gebruikt, wat vaak het geval is met functies voor gegevensbewerkingen, zal de geretourneerde waarde gelukkig niet worden gemaakt en is er geen sprake van problemen met bronnen of volgordes.  Als u echter het resultaat van een **ForAll** en een van de functies die een gegevensbron retourneert gebruikt, moet u zorgvuldig nadenken over de manier waarop u het resultaat structureert en deze eerst op kleine gegevenssets uitproberen.  

### <a name="alternatives"></a>Alternatieven
Veel functies in PowerApps kunnen meer dan een waarde tegelijk verwerken door het gebruik van een tabel met één kolom.  De functie **Len** kan bijvoorbeeld een tabel met tekstwaarden verwerken en op dezelfde manier als **ForAll** een tabel met lengten retourneren.  Dit kan in veel gevallen de noodzaak om **ForAll** te gebruiken wegnemen, en efficiënter en gemakkelijker te lezen zijn.

Een andere overweging is dat **ForAll** niet kan worden gedelegeerd, terwijl dat voor andere functies, zoals **Filter**, mogelijk wel kan.  

### <a name="delegation"></a>Delegering
[!INCLUDE [delegation-no-one](../../../includes/delegation-no-one.md)]

## <a name="syntax"></a>Syntaxis
**ForAll**( *Tabel*, *Formule* )

* *Tabel* - vereist. Tabel waarvoor actie moet worden uitgevoerd.
* *Formule* - vereist.  De formule die moet worden geëvalueerd voor elke record van de *Tabel*.

## <a name="examples"></a>Voorbeelden
### <a name="calculations"></a>Berekeningen
De volgende voorbeelden gebruiken de [gegevensbron](../working-with-data-sources.md) **Kwadraten**:

![](media/function-forall/squares.png)

Stel de eigenschap **OnSelect** van een **Knop**-besturingselement in op de volgende formule, open de voorbeeldmodus en klik of tik op de knop om deze gegevensbron als een verzameling te maken:

* **ClearCollect( Kwadraten, [ "1", "4", "9" ] )**

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **ForAll(&nbsp;Kwadraten, Sqrt(&nbsp;Waarde&nbsp;)&nbsp;)**<br><br>**Sqrt(&nbsp;Kwadraten&nbsp;)** |Berekent voor alle records van de invoertabel de vierkantswortel van de kolom **Waarde**.  De functie **Sqrt** kan ook worden gebruikt voor een tabel met één kolom, waardoor het mogelijk is om dit voorbeeld uit te voeren zonder **ForAll** te gebruiken. |<style> img { max-width: none } </style> ![](media/function-forall/sqrt.png) |
| **ForAll(&nbsp;Kwadraten, Power(&nbsp;Waarde,&nbsp;3&nbsp;)&nbsp;)** |Verhoogt de kolom **Waarde** voor alle records van de invoertabel tot de derde macht.  De functie **Power** ondersteunt geen tabellen met één kolom. Daarom moet in dit geval **ForAll** worden gebruikt. |<style> img { max-width: none } </style> ![](media/function-forall/power3.png) |

### <a name="using-a-connection"></a>Een verbinding gebruiken
De volgende voorbeelden gebruiken de [gegevensbron](../working-with-data-sources.md) **Uitdrukkingen**:

![](media/function-forall/translate.png)

Stel de eigenschap **OnSelect** van een **Knop**-besturingselement in op de volgende formule, open de voorbeeldmodus en klik of tik op de knop om deze gegevensbron als een verzameling te maken:

* **ClearCollect( Uitdrukkingen, [ "Hallo", "Goedemorgen", "Bedankt", "Tot ziens" ] )**

Dit voorbeeld gebruikt ook een verbinding met [Microsoft Translator](../connections/connection-microsoft-translator.md).  Raadpleeg het onderwerp over [verbindingen beheren](../add-manage-connections.md) om deze verbinding aan uw app toe te voegen.

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **ForAll( Uitdrukkingen, MicrosoftTranslator.Translate( Waarde, "es" ) )** |Vertaal de inhoud van de kolom **Waarde** voor alle records in de tabel Uitdrukkingen in het Spaans (afgekort tot "es"). |<style> img { max-width: none } </style> ![](media/function-forall/translate-es.png) |
| **ForAll( Uitdrukkingen, MicrosoftTranslator.Translate( Waarde, "fr" ) )** |Vertaal de inhoud van de kolom **Waarde** voor alle records in de tabel Uitdrukkingen in het Frans (afgekort tot "fr"). |<style> img { max-width: none } </style> ![](media/function-forall/translate-fr.png) |

### <a name="copying-a-table"></a>Een tabel kopiëren
Soms moet u gegevens filteren, vormen, sorteren en manipuleren.  PowerApps biedt een aantal functies om dit te doen, zoals **Filter**, **AddColumns** en **Sorteren**.  PowerApps behandelt elke tabel als een waarde, waardoor deze door formules kan stromen en gemakkelijk kan worden verbruikt.      

Soms wilt u een kopie van dit resultaat maken voor later gebruik.  Of u wilt informatie van de ene gegevensbron naar de andere verplaatsen.  PowerApps biedt de functie **Verzamelen** om gegevens te kopiëren.

Denk voordat u een kopie maakt echter zorgvuldig na of hij echt nodig is.  Veel situaties kunnen worden aangepakt door de onderliggende gegevensbron op verzoek te filteren en vorm te geven met een formule. Een aantal nadelen van het maken van een kopie:

* Twee kopieën van dezelfde informatie betekent dat een ervan mogelijk niet langer wordt gesynchroniseerd.  
* Het maken van een kopie kan veel computergeheugen, netwerkbandbreedte en/of tijd kosten.  
* Voor de meeste gegevensbronnen kan het kopiëren niet worden gedelegeerd, wat beperkingen inhoudt voor de hoeveelheid gegevens die kan worden verplaatst.      

De volgende voorbeelden gebruiken de [gegevensbron](../working-with-data-sources.md) **Producten**:

![](media/function-forall/prod.png)

Stel de eigenschap **OnSelect** van een **Knop**-besturingselement in op de volgende formule, open de voorbeeldmodus en klik of tik op de knop om deze gegevensbron als een verzameling te maken:

* **ClearCollect( Producten, Table( { Product: "Widget", 'Gevraagde hoeveelheid': 6, 'Beschikbare hoeveelheid': 3 }, { Product: "Gadget", 'Gevraagde hoeveelheid': 10, 'Beschikbare hoeveelheid': 20 }, { Product: "Gizmo", 'Gevraagde hoeveelheid': 4, 'Beschikbare hoeveelheid': 11 }, { Product: "Apparaat", 'Gevraagde hoeveelheid': 7, 'Beschikbare hoeveelheid': 6 } ) )**

Het is ons doel om te werken met een afgeleide tabel die alleen de artikelen bevat waarvan er meer zijn gevraagd dan er beschikbaar zijn, en waarvoor we dus een bestelling moeten plaatsen:

![](media/function-forall/prod-order.png)  

We kunnen deze taak uitvoeren op een aantal verschillende manieren die allemaal hetzelfde resultaat met diverse voordelen en nadelen opleveren.

#### <a name="table-shaping-on-demand"></a>Tabel vormgeven op aanvraag
Maak geen kopie!  We kunnen de volgende formule gebruiken waar we hem maar nodig hebben:

* **ShowColumns( AddColumns( Filter( Producten, 'Gevraagde hoeveelheid' > 'Beschikbare hoeveelheid' ), "Te bestellen hoeveelheid", 'Gevraagde hoeveelheid' - 'Beschikbare hoeveelheid' ), "Product", "Te bestellen hoeveelheid" )**

Er wordt een [recordbereik](../working-with-tables.md#record-scope) door de functies **Filter** en **AddColumns** gemaakt om de vergelijkings- en aftrekbewerkingen uit te voeren met de velden **'Gevraagde hoeveelheid'** en **'Beschikbare hoeveelheid'** van elk record.

In dit voorbeeld kan de functie **Filter** worden gedelegeerd.  Dit is belangrijk omdat hij alle producten kan vinden die aan de criteria voldoen - zelfs als dat slechts een paar records uit een tabel met miljoenen records zijn.  Op dit moment kunnen **ShowColumns** en **AddColumns** niet worden gedelegeerd. Daarom zal het daadwerkelijke aantal producten dat moet worden besteld beperkt zijn.  Deze benadering werkt prima als u weet dat de omvang van dit resultaat altijd relatief klein is.

Omdat we geen kopie hebben gemaakt, is er ook geen extra kopie van de informatie die moet worden beheerd of die kan verouderen.  

#### <a name="forall-on-demand"></a>ForAll op aanvraag
Een andere benadering is het gebruik van de functie **ForAll** om de functies voor het vormgeven van de tabel te vervangen:

* **ForAll( Producten, If( 'Gevraagde hoeveelheid' > 'Beschikbare hoeveelheid', { Product: Product, 'Te bestellen hoeveelheid': 'Gevraagde hoeveelheid' - 'Beschikbare hoeveelheid' } ) )**

Deze formule is voor sommige mensen mogelijk eenvoudiger te lezen en te schrijven.

Geen deel van **ForAll** kan worden gedelegeerd.  Alleen het eerste deel van de tabel **Producten** zal worden geëvalueerd. Dat kan een probleem zijn als deze tabel erg groot is.  Omdat **Filter** in het vorige voorbeeld kan worden gedelegeerd, kan deze mogelijk beter werken met grote gegevenssets.

#### <a name="collect-the-result"></a>Het resultaat verzamelen
In sommige gevallen is mogelijk een kopie van gegevens vereist.  U moet mogelijk informatie van de ene gegevensbron naar de andere verplaatsen.  In dit voorbeeld worden bestellingen geplaatst via een tabel **NieuweBestelling** in het systeem van de leverancier.  U wilt voor snelle gebruikersinteracties mogelijk een lokale kopie van een tabel in het cachegeheugen opslaan, zodat er geen sprake is van serverlatentie.

We gebruiken dezelfde tabelvormgeving als in de vorige twee voorbeelden, maar we leggen het resultaat vast in een verzameling:

* **ClearCollect( NieuweBestelling, ShowColumns( AddColumns( Filter( Producten, 'Gevraagde hoeveelheid' > 'Beschikbare hoeveelheid' ), "Te bestellen hoeveelheid", 'Gevraagde hoeveelheid' - 'Beschikbare hoeveelheid' ), "Product", "Te bestellen hoeveelheid" ) )**
* **ClearCollect( NieuweBestelling, ForAll( Producten, If( 'Gevraagde hoeveelheid' > 'Beschikbare hoeveelheid', { Product: Product, 'Te bestellen hoeveelheid': 'Gevraagde hoeveelheid' - 'Beschikbare hoeveelheid' } ) ) )**

**ClearCollect** en **Verzamelen** kunnen niet worden overgedragen.  Als gevolg daarvan is de hoeveelheid gegevens die op deze manier kan worden verplaatst beperkt.

#### <a name="collect-within-forall"></a>Verzamelen binnen ForAll
Ten slotte kunnen we **Verzamelen** rechtstreeks binnen **ForAll** uitvoeren:

* **ClearCollect( TeBestellenProducten); ForAll( Producten, If( 'Gevraagde hoeveelheid' > 'Beschikbare hoeveelheid', Collect( NieuweBestelling, { Product: Product, 'Te bestellen hoeveelheid': 'Gevraagde hoeveelheid' - 'Beschikbare hoeveelheid' } ) ) )**

De functie **ForAll** kan opnieuw niet worden gedelegeerd.  Als onze tabel **Producten** te groot is, zal **ForAll** alleen naar de eerste set met records kijken en missen we mogelijk bepaalde producten die moeten worden besteld.  Deze benadering werkt echter prima voor tabellen waarvan we weten dat ze klein blijven.

Houd er rekening mee dat we het resultaat van **ForAll** niet vastleggen.  De aanroepen van de functie **Verzamelen** die van daaruit worden gemaakt, zullen de gegevensbron **NieuweBestelling** voor alle records retourneren, wat een grote hoeveelheid gegevens kan opleveren als we die zouden vastleggen.  

