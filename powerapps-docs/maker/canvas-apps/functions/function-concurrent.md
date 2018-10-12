---
title: De functie Concurrent | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis, voor de functie Concurrent in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/26/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a0fdddcf906a04914ea9ba9a8572798ea5d55378
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42834814"
---
# <a name="concurrent-function-in-powerapps"></a>De functie Concurrent in PowerApps
Hiermee evalueert u meerdere formules gelijktijdig met elkaar.

## <a name="description"></a>Beschrijving
Met dD functie **Concurrent** evalueert u meerdere formules tegelijk. Normaal gesproken worden meerdere formules geëvalueerd door ze aan elkaar te koppelen met de operator [**;**](operators.md) (of [**;;**](operators.md)), die elk opeenvolgend in volgorde evalueert. Wanneer met de app bewerkingen gelijktijdig worden uitgevoerd, hoeven gebruikers minder lang te wachten op hetzelfde resultaat.

In de eigenschap [**OnStart**](../controls/control-screen.md) van uw app gebruikt u **Concurrent** om de prestaties te verbeteren wanneer de app gegevens laadt. Wanneer gegevensaanroepen pas beginnen als de eerdere aanroepen zijn voltooid, moet de app wachten op de som van alle aanvraagtijden. Als gegevensaanroepen gelijktijdig beginnen, hoeft de app alleen maar te wachten op de langste aanvraagtijd. In webbrowsers worden de prestaties vaak verbeterd door gegevensbewerkingen gelijktijdig uit te voeren.

U kunt de volgorde waarin formules binnen de functie **Concurrent** beginnen en stoppen met evalueren niet voorspellen. Formules in de functie **Concurrent** mogen geen afhankelijkheden op andere formules binnen dezelfde functie **Concurrent** bevatten. PowerApps geeft een fout weer als u dat probeert. Van binnenuit kunt u afhankelijkheden op formules buiten de functie **Concurrent** plaatsen, omdat deze worden voltooid voordat de functie **Concurrent** start. Formules na de functie **Concurrent** kunnen veilig afhankelijkheden nemen op formules binnenin: ze worden allemaal voltooid voordat de functie **Concurrent** is voltooid en verdergaat met de volgende formule in een keten (als u de operator **;** of **;;** gebruikt). Kijk uit voor subtiele volgordeafhankelijkheden als u functies of servicemethoden aanroept die neveneffecten hebben.

U kunt formules aan elkaar koppelen met de operator **;** (of **;;**) binnen een argument voor **Concurrent**. **Concurrent( Set( a, 1 ); Set( b, a+1 ), Set( x, 2 ); Set( y, x+2 ) )** evalueert bijvoorbeeld **Set( a, 1 ); Set( b, a+1 )** gelijktijdig met **Set( x, 2 ); Set( y, x+2 )**. In dit geval zijn de afhankelijkheden binnen de formules prima: **a** wordt ingesteld voor **b** en **x** wordt ingesteld voor **y**.

Afhankelijk van het apparaat of de browser waarin de app wordt uitgevoerd, kan mogelijk slechts een handvol formules gelijktijdig worden geëvalueerd. **Concurrent** maakt gebruik van de beschikbare mogelijkheden en wordt pas voltooid wanneer alle formules zijn geëvalueerd.

Als u **Foutbeheer op formuleniveau** inschakelt (in de geavanceerde instellingen), wordt de eerste fout die wordt gevonden in argumentvolgorde geretourneerd vanaf **Concurrent**; anders wordt *leeg* geretourneerd. Als alle formules slagen, wordt *waar* geretourneerd. Als een formule mislukt, stopt de rest van die formule; andere formules blijven echter evalueren.

U kunt **Concurrent** alleen gebruiken in [gedragsformules](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaxis
**Concurrent**( *Formula1*, *Formula2* [, ...] )

* *Formula(s)*: vereist. Formules voor gelijktijdige evaluatie. U moet ten minste twee formules opgeven.

## <a name="examples"></a>Voorbeelden

#### <a name="loading-data-faster"></a>Gegevens sneller laden

1. Maak een app en voeg vier gegevensbronnen toe vanuit Common Data Service voor apps, SQL Server of SharePoint. 

    Dit voorbeeld maakt gebruik van vier tabellen uit de [Adventure Works-voorbeelddatabase voor SQL Azure](https://docs.microsoft.com/azure/sql-database/sql-database-get-started-portal). Nadat u de database hebt gemaakt, maakt u er verbinding mee vanuit PowerApps met behulp van de volledig gekwalificeerde servernaam (bijvoorbeeld srvname.database.windows.net):

    ![Verbinding maken met de database van Adventure Works in Azure](media/function-concurrent/connect-database.png)

2. Voeg een besturingselement van het type **[Knop](../controls/control-button.md)** toe en stel de bijbehorende eigenschap **OnSelect** in op deze formule:

    **ClearCollect( Product, '[SalesLT].[Product]' );<br> ClearCollect( Customer, '[SalesLT].[Customer]' );<br> ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' );<br> ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' )**

3. In [Microsoft Edge](https://docs.microsoft.com/microsoft-edge/devtools-guide/network) of [Google Chrome](https://developers.google.com/web/tools/chrome-devtools/network-performance/) schakelt u ontwikkelhulpprogramma's in om netwerkverkeer te bewaken terwijl uw app wordt uitgevoerd.

1. (optioneel) Schakel netwerkbeperking in om de effecten van deze vergelijking te overdrijven.

4. Houd de Alt-toets ingedrukt, selecteer de knop en bekijk het netwerkverkeer.

    In de hulpprogramma's worden vier aanvragen weergegeven die worden uitgevoerd in de reeks, vergelijkbaar met dit voorbeeld.  De werkelijke tijden zijn verwijderd, aangezien deze sterk variëren.  In het diagram ziet u dat elke aanroep start nadat de laatste is voltooid:

    ![Tijdgrafiek van vier netwerkaanvragen, elke aanvraag start nadat de laatste is voltooid en is van toepassing op de hele periode](media/function-concurrent/chained-network.png)

5. Bewaar en sluit de app en open deze opnieuw.

    PowerApps slaat gegevens op in de cache. Wanneer u de knop opnieuw selecteert, leidt dat daarom niet per se tot vier nieuwe aanvragen. Elke keer dat u de prestaties wilt testen, sluit u de app en opent u deze opnieuw. Als u netwerkbeperking hebt ingeschakeld, kunt u dit uitschakelen totdat u klaar bent voor een andere test.

1. Voeg een tweede besturingselement van het type **[Knop](../controls/control-button.md)** toe en stel de bijbehorende eigenschap **OnSelect** in op deze formule:

    **Concurrent(<br> &nbsp;&nbsp;&nbsp;&nbsp;ClearCollect( Product, '[SalesLT].[Product]' ),<br> &nbsp;&nbsp;&nbsp;&nbsp;ClearCollect( Customer, '[SalesLT].[Customer]' ),<br> &nbsp;&nbsp;&nbsp;&nbsp;ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' ),<br> &nbsp;&nbsp;&nbsp;&nbsp;ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' )<br> )**

    Denk erom dat u dezelfde **ClearCollect**-aanroepen hebt toegevoegd aan de eerste knop, maar deze zijn nu verpakt in een **Concurrent**-functie en van elkaar gescheiden door komma's.

2. Wis de netwerkmonitor in de browser.

1. Als u eerder netwerkbeperking gebruikte, kunt u dit weer inschakelen.

3. Houd de Alt-toets ingedrukt, selecteer de tweede knop en bekijk het netwerkverkeer.

    In de hulpprogramma's worden vier aanvragen weergegeven die gelijktijdig worden uitgevoerd, vergelijkbaar met dit voorbeeld.  Ook nu zijn de werkelijke tijden verwijderd, aangezien deze sterk variëren.  In het diagram ziet u dat alle aanroepen ongeveer tegelijkertijd beginnen en niet wachten tot de vorige is voltooid:

    ![Tijdgrafiek van vier netwerkaanvragen, die alle vier samen starten en ongeveer de helft van de hoeveelheid tijd bestrijken](media/function-concurrent/concurrent-network.png)

    Deze grafieken zijn gebaseerd op dezelfde schaal. Door **Concurrent** te gebruiken, hebt u de totale hoeveelheid tijd die deze bewerkingen duurden, gehalveerd. 

5. Bewaar en sluit de app en open deze opnieuw.

#### <a name="race-condition"></a>Racevoorwaarde

1. Voeg een verbinding naar de service [Microsoft Translator](../connections/connection-microsoft-translator.md) toe aan uw app.

2. Voeg een besturingselement van het type [**Tekstinvoer**](../controls/control-text-input.md) toe en geef dit de naam **Tekstinvoer1** als het een andere naam heeft.

3. Voeg een besturingselement van het type **Knop** toe en stel de bijbehorende eigenschap **OnSelect** in op deze formule:

    **Set( StartTime, Value(Now()) );<br> Concurrent(<br> &nbsp;&nbsp;&nbsp;&nbsp;Set(FRTrans, MicrosoftTranslator.Translate(TextInput1.Text,"fr")); Set(FRTransTime, Value(Now()) ),<br> &nbsp;&nbsp;&nbsp;&nbsp;Set(DETrans, MicrosoftTranslator.Translate(TextInput1.Text,"de")); Set(DETransTime, Value(Now()) )<br> ); <br> Collect( <br> &nbsp;&nbsp;&nbsp;&nbsp;Results, <br> &nbsp;&nbsp;&nbsp;&nbsp;{<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Input: TextInput1.Text, <br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;French: FRTrans, FrenchTime: FRTransTime-StartTime,<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;German: DETrans, GermanTime: DETransTime-StartTime,<br> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;FrenchFaster: FRTransTime < DETransTime <br> &nbsp;&nbsp;&nbsp;&nbsp;}<br> )**

4. Voeg een besturingselement van het type [**Gegevenstabel**](../controls/control-data-table.md) toe en stel de eigenschap **Items** in op **Resultaten**.

1. Selecteer op het tabblad **Eigenschappen** van het rechterdeelvenster de optie **Resultaten** om het deelvenster **Gegevens** te openen.

1. Schakel in de lijst met velden het selectievakje voor elk veld in om ze allemaal weer te geven in de gegevenstabel.

1. (optioneel) Sleep het veld **Invoer** naar de bovenkant van de lijst en sleep het veld **FrenchFaster** naar de onderkant van de lijst.

    ![Lijst met velden in de verzameling Resultaten](media/function-concurrent/field-list.png) 

6. In het besturingselement **Tekstinvoer** typt of plakt u een te vertalen woordgroep.

7. Houd de Alt-toets ingedrukt en selecteer de knop meerdere keren om de tabel te vullen.

    De tijden worden in milliseconden weergegeven.
  
    ![Weergave van de gegevenstabel met resultaten van het vertalen van de tekenreeks "Hallo wereld" in het Frans en Duits. Soms is de Franse vertaling sneller dan de Duitse en soms is het andersom.](media/function-concurrent/race-condition.png) 

    In sommige gevallen is de Franse vertaling sneller dan de Duitse vertaling, en vice versa. Beide starten op hetzelfde moment, maar om verschillende redenen, zoals netwerklatentie en verwerking aan serverzijde, wordt de een sneller dan de ander geretourneerd.

    Er zou een [racevoorwaarde](https://en.wikipedia.org/wiki/Race_condition) optreden als de app ervan afhankelijk was dat één vertaling het eerst eindigt. Gelukkig markeert PowerApps de meeste timing-afhankelijkheden die kunnen worden gedetecteerd.
