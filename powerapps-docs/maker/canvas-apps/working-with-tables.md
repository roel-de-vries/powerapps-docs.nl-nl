---
title: Over tabellen | Microsoft Docs
description: Naslaginformatie voor het werken met tabellen, kolommen en records
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: 42a7c0db6aaf46d8cdbd112cf72c6f95f58dc9ec
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="understand-tables-and-records-in-powerapps"></a>Over tabellen en records in PowerApps
U kunt een app maken die toegang heeft tot informatie in Microsoft Excel, SharePoint, SQL Server en enkele andere bronnen die gegevens opslaan in records en tabellen. Om zo efficiënt mogelijk met dit soort gegevens te werken, moet u de concepten doornemen die ten grondslag liggen aan deze structuren.

* Een record bevat een of meer informatiecategorieën over een persoon, een plaats of een ding. Een record kan bijvoorbeeld de naam, het e-mailadres en het telefoonnummer van één klant bevatten. Andere hulpprogramma's verwijzen naar een record als een 'rij' of een 'item'.
* Een tabel bevat een of meer records met dezelfde informatiecategorieën. Een tabel kan bijvoorbeeld de namen, de e-mailadressen en de telefoonnummers van 50 klanten bevatten.

In uw app gebruikt u [formules](working-with-formulas.md) om records en tabellen te maken, bij te werken en te bewerken. U zult waarschijnlijk gegevens lezen en schrijven naar een externe [gegevensbron](working-with-data-sources.md). Dit is een uitgebreide tabel. Bovendien maakt u een of meer interne tabellen. Deze worden [verzamelingen](working-with-data-sources.md#collections) genoemd.

Net zoals een formule in Excel een of meer celverwijzingen als argumenten heeft, kunt u verschillende formules maken die de naam van een tabel als een argument hebben. Sommige formules in PowerApps retourneren een tabel die de andere argumenten die u opgeeft, weerspiegelen. U maakt bijvoorbeeld een formule:

* om een record in een tabel bij te werken door deze tabel op te geven als een van meerdere argumenten voor de functie **[Patch](functions/function-patch.md)**
* om kolommen in een tabel toe te voegen, te verwijderen en de naam te wijzigen door deze tabel op te geven als een argument voor de functie **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)** of **[RenameColumns](functions/function-table-shaping.md)**. Geen van deze functies wijzigt de oorspronkelijke tabel. In plaats daarvan retourneert de functie een andere tabel op basis van de andere argumenten die u hebt opgegeven.

## <a name="elements-of-a-table"></a>Elementen van een tabel
![](media/working-with-tables/elements-of-a-table.png)

### <a name="records"></a>Records
Elke record bevat ten minste één informatiecategorie voor een persoon, een plaats of een ding. In het bovenstaande voorbeeld ziet u een record voor elk product (**Chocolade**, **Brood** en **Water**) en een kolom voor elke informatiecategorie (**Prijs**, **Hoeveelheid in voorraad** en **Hoeveelheid in bestelling**).

In een formule kunt u naar een record zelf verwijzen, buiten de context van een tabel, met behulp van accolades. Deze record **{Naam: "Aardbeien", Prijs: 7,99}** is bijvoorbeeld niet gekoppeld aan een tabel.

### <a name="fields"></a>Velden
Een veld is een individueel gedeelte met informatie in een record. U kunt een dergelijk veld visualiseren als een waarde in een kolom voor een bepaalde record.

Net als met een besturingselement verwijst u naar een veld van een record met behulp van de **.** [operator](functions/operators.md) op de record.  **First(Products).Name** retourneert bijvoorbeeld het veld **Naam** voor de eerste record in de tabel **Producten**.

Een veld kan een andere record of tabel bevatten, zoals het voorbeeld voor de functie **[GroupBy](functions/function-groupby.md)** weergeeft. U kunt zoveel niveaus van records en tabellen nesten als u wilt.

### <a name="columns"></a>Kolommen
Een kolom verwijst naar hetzelfde veld voor een of meer records in een tabel. In het bovenstaande voorbeeld heeft elk product een prijsveld en die prijs bevindt zich in dezelfde kolom voor alle producten.  De bovenstaande tabel heeft vier kolommen. Deze zijn bovenaan horizontaal weergegeven:

* **Naam**
* **Prijs**
* **Hoeveelheid in voorraad**
* **Hoeveelheid in bestelling**

De naam van de kolom geeft de velden in die kolom weer.

Alle waarden in een kolom zijn van hetzelfde gegevenstype. In het bovenstaande voorbeeld bevat de kolom 'Hoeveelheid in voorraad' altijd een getal en kan deze geen tekenreeks, zoals '12 eenheden', bevatten voor één record.  De waarde van een willekeurig veld kan tevens *leeg* zijn.  

In andere hulpprogramma's hebt u kolommen mogelijk 'velden' genoemd.

> [!NOTE]
> Kolomnamen met spaties in gegevensbronnen van Excel of SharePoint worden in PowerApps vervangen door **‘\_x0020\_’**. **'Kolom twaalf'** in SharePoint of Excel wordt bijvoorbeeld weergegeven als **'Kolom_x0020_twaalf'** in PowerApps wanneer de naam wordt weergegeven in de gegevensindeling of wordt gebruikt in een formule.

### <a name="table"></a>Tabel
Een tabel bestaat uit een of meer records, elk met meerdere velden met consistente namen tussen de records.

Een tabel die in een gegevensbron of een verzameling is opgeslagen, heeft een naam. Deze gebruikt u om naar de tabel te verwijzen en deze door te geven aan functies die tabellen als argumenten hebben.  Tabellen kunnen ook het resultaat zijn van een functie of een formule.

U kunt een tabel in een formule uitdrukken met behulp van de functie **[Table](functions/function-table.md)** met een set records, die u tussen accolades zet, zoals in het volgende voorbeeld:

**Tabel( { Waarde: "Aardbeien"}, { Waarde: "Vanille" } )**

U kunt ook een tabel met één kolom definiëren met vierkante haken.  U kunt het bovenstaande ook als volgt opschrijven:

**[ "Aardbeien", "Vanille" ]**

## <a name="table-formulas"></a>Tabelformules
In Excel en PowerApps gebruikt u formules om getallen en tekstreeksen op vergelijkbare wijze te bewerken:

* Typ in Excel een waarde, zoals **42** in cel **A1**. Typ vervolgens een formule, zoals **A1+2** in een andere cel om de waarde **44** weer te geven.
* In PowerApps stelt u de eigenschap **[Default](controls/properties-core.md)** van **Slider1** in op **42** en stelt u de eigenschap **[Text](controls/properties-core.md)** van een label in op **Slider1.Value + 2** om de waarde **44** weer te geven.

In beide gevallen wordt de berekende waarde automatisch gewijzigd als u de waarden van de argumenten wijzigt (bijvoorbeeld het getal in cel **A1** of de waarde van **Slider1**).

Op vergelijkbare wijze kunt u formules gebruiken om gegevens in tabellen en records te openen en te bewerken. U kunt namen van tabellen gebruiken als argumenten in sommige formules, zoals **Min(Catalog, Price)** om de laagste waarde in de kolom **Prijs** van de tabel **Catalogus** weer te geven. Andere formules bieden hele tabellen als retourwaarden, zoals **RenameColumns(Catalogus, "Prijs", "Kosten")**, die alle records uit de tabel **Catalogus** retourneert, maar de naam van de kolom **Prijs** in **Kosten** wijzigt.

Net zoals met getallen worden formules die betrekking hebben op tabellen en records automatisch opnieuw berekend als de onderliggende tabel of record wordt gewijzigd. Als de kosten van een product in de tabel **Catalogus** onder het vorige minimum worden verlaagd, wordt de geretourneerde waarde van de formule **[Min](functions/function-aggregates.md)** automatisch gewijzigd, zodat deze hiermee overeenkomt.

Hieronder volgen een aantal eenvoudige voorbeelden.

1. Voeg een besturingselement **Tekstgalerie** toe en stel de eigenschap **[Items](controls/properties-core.md)** in op de naam van een tabel.
   
    Standaard toont de galerie tekst van een tijdelijke aanduiding uit een tabel met de naam **TextualGallerySample**. De eigenschap **[Items](controls/properties-core.md)** van de galerie wordt automatisch ingesteld op die tabel.
   
    > [!NOTE]
> Sommige besturingselementen zijn anders gerangschikt en vergroot voor illustratiedoeleinden.
   
    ![](media/working-with-tables/gallery-items.png)
2. In plaats van de eigenschap **[Items](controls/properties-core.md)** in te stellen op de naam van een tabel, stelt u deze in op een formule met de naam van de tabel als een argument, zoals in het volgende voorbeeld:<br>
   **Sort(TextualGallerySample, Heading, Descending)**
   
    Deze formule omvat de functie **[Sort](functions/function-sort.md)**, waarbij de naam van een tabel als het eerste argument en de naam van een kolom in die tabel als tweede argument worden genomen. De functie ondersteunt ook een optioneel derde argument waarin wordt bepaald dat u de gegevens in aflopende volgorde wilt sorteren.
   
    ![](media/working-with-tables/gallery-items-sort.png)
3. Stel de eigenschap **[Items](controls/properties-core.md)** in op een formule die de formule van de vorige stap als een argument neemt en een tabel retourneert, zoals in het volgende voorbeeld:<br>
   **FirstN(Sort(TextualGallerySample, Heading, Descending), 2)**
   
    In deze formule gebruikt u de functie **[FirstN](functions/function-first-last.md)** om een bepaald aantal records in een tabel weer te geven. U gebruikt de functie **[Sort](functions/function-sort.md)** als het eerste argument voor **[FirstN](functions/function-first-last.md)** en een getal (in dit geval **2**) als het tweede argument, dat aangeeft hoeveel records er worden weergegeven.
   
    De gehele formule retourneert een tabel met de eerste twee records van de tabel **TextualGallerySample** gesorteerd op de kolom **Kop** in aflopende volgorde.
   
    ![](media/working-with-tables/gallery-items-sort-firstn.png)

### <a name="table-functions-and-control-properties"></a>Tabelfuncties en besturingselementeigenschappen
Veel functies in PowerApps nemen de naam van een tabel als een argument, maken een tweede tabel met dezelfde gegevens, bewerken de nieuwe tabel op basis van de andere argumenten en retourneren vervolgens het resultaat. Deze functies wijzigen de oorspronkelijke tabel niet, zelfs als deze een gegevensbron is.

* **[Sorteren](functions/function-sort.md)**, **[Filteren](functions/function-filter-lookup.md)**: sorteert en filtert records.
* **[FirstN](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**: retourneert de eerste N- of de laatste N-records van de tabel.
* **[Abs](functions/function-numericals.md)**, **[Wortel](functions/function-numericals.md)**, **[Afronden](functions/function-round.md)**, **[Afronden.naar.boven](functions/function-round.md)**, **[Afronden.naar.beneden](functions/function-round.md)**: rekenkundige bewerkingen op elke record van een tabel met één kolom. Dit resulteert in een tabel met één kolom met resultaten.
* **[Links](functions/function-left-mid-right.md)**, **[Midden](functions/function-left-mid-right.md)**, **[Rechts](functions/function-left-mid-right.md)**, **[Vervangen](functions/function-replace-substitute.md)**, **[Substitueren](functions/function-replace-substitute.md)**, **[Spaties.wissen](functions/function-trim.md)**, **[Kleine letters](functions/function-lower-upper-proper.md)**, **[Hoofdletters](functions/function-lower-upper-proper.md)**, **[Juiste](functions/function-lower-upper-proper.md)**: tekenreeksbewerkingen op elke record van een tabel met één kolom. Dit resulteert in een tabel met één kolom met tekenreeksen.
* **[Len](functions/function-len.md)**: voor een kolom met tekenreeksen, retourneert een tabel met één kolom die de lengte van elke tekenreeks bevat.
* **[Samenvoegen](functions/function-concatenate.md)**: voegt meerdere kolommen van tekenreeksen samen. Dit resulteert in een tabel met één kolom met tekenreeksen.
* **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)**, **[RenameColumns](functions/function-table-shaping.md)**, **[ShowColumns](functions/function-table-shaping.md)**: kolombewerking van de tabel. Dit resulteert in een nieuwe tabel met andere kolommen.
* **[Afzonderlijk](functions/function-distinct.md)**: verwijdert dubbele records.
* **[Shuffle](functions/function-shuffle.md)**: plaatst de records in een willekeurige volgorde.
* **[HashTags](functions/function-hashtags.md)**: zoekt naar hashtags in een tekenreeks.
* **[Fouten](functions/function-errors.md)**: geeft foutinformatie wanneer u met een gegevensbron werkt.

U kunt een functie uitvoeren op een tabel die uit meerdere kolommen bestaat, zelfs als de functie één kolom als argument vereist. Als u één kolom uit een tabel met meerdere kolommen wilt halen, gebruikt u de functie **[ShowColumns](functions/function-table-shaping.md)** als een argument voor de functie die u wilt gebruiken, zoals in het volgende voorbeeld:<br>**Kleine letters( ShowColumns( Producten, "Naam" ) )**

Deze formule maakt een tabel met één kolom die alle gegevens van de kolom **Naam** van de tabel **Producten** bevat, maar converteert hoofdletters in kleine letters. Als u een tabel als argument voor de functie **[AddColumns](functions/function-table-shaping.md)**, **[RenameColumns](functions/function-table-shaping.md)** of **[DropColumns](functions/function-table-shaping.md)** opgeeft, kunt u de tabel een geheel nieuwe vorm geven.

Als u een gegevensbron als argument voor een van deze functies opgeeft, worden de records van die gegevensbron gewijzigd en wordt doorgaans de nieuwe waarde van de gegevensbron als een tabel geretourneerd.

* **[Verzamelen](functions/function-clear-collect-clearcollect.md)**, **[Wissen](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**: hiermee maakt, wist en voegt u toe aan een verzameling.
* **[Bijwerken](functions/function-update-updateif.md)**, **[UpdateIf](functions/function-update-updateif.md)**: werkt records bij die overeenkomen met een of meer criteria die u hebt opgegeven.
* **[Verwijderen](functions/function-remove-removeif.md)**, **[RemoveIf](functions/function-remove-removeif.md)**: verwijdert records die overeenkomen met een of meer criteria die u hebt opgegeven.

De volgende besturingselementen hebben eigenschappen die tabellen zijn:

* **Items**: is van toepassing op galerieën en keuzelijsten. Tabel om in de galerie weer te geven.
* **SelectedItems**: is van toepassing op keuzelijsten. Tabel van de items die de gebruiker heeft geselecteerd.

## <a name="record-formulas"></a>Recordformules
U kunt ook een formule maken die gegevens voor een afzonderlijke record berekent, een afzonderlijke record als een argument neemt en een afzonderlijke record als een retourwaarde geeft. We gaan terug naar het bovenstaande galerievoorbeeld. We gebruiken de eigenschap **Gallery1.Selected** om informatie weer te geven van de record die de gebruiker in die galerie selecteert.

1. Voeg een knop toe en stel de eigenschap **[BijSelecteren](controls/properties-core.md)** ervan in op deze formule:<br>
    **Verzamelen( SelectedRecord, Gallery1.Selected)**

2. Als de knop niet is geselecteerd, klikt u hierop om deze te selecteren. Klik hier opnieuw op om de formule uit te voeren.

3. Selecteer **Verzamelingen** in het menu **Bestand**.

![](media/working-with-tables/selected-collection.png)

Deze formule retourneert een record met de gegevens van de record die momenteel in de galerie is geselecteerd en ook elk besturingselement in die galerie. De record bevat bijvoorbeeld zowel een kolom **Body**, die overeenkomt met de kolom **Body** in de oorspronkelijke tabel als een kolom **Body1**, die het label aanduidt waarin de gegevens van die kolom worden weergegeven. Selecteer het tabelpictogram in de kolom **Body1** om die gegevens te bekijken.

Nu u de geselecteerde record hebt, kunt u hieruit afzonderlijke velden halen met de **.** .

1. Druk op Esc om terug te keren naar de standaardwerkruimte en voeg vervolgens een label toe onder de galerie.

2. Stel de eigenschap **[Text](controls/properties-core.md)** van het label in op deze formule:<br>
    **Gallery.Selected.Heading**
   
    ![](media/working-with-tables/gallery-selected.png)

U hebt de eigenschap **Selected** genomen, die een record is, en de eigenschap **Heading** uitgepakt.  

U kunt ook een record gebruiken als een container voor algemeen gebruik voor verwante naamwaarden.

* Als u een formule maakt rond de functies **[UpdateContext](functions/function-updatecontext.md)** en **[Navigate](functions/function-navigate.md)**, moet u een record gebruiken om de [contextvariabelen](working-with-variables.md#create-a-context-variable) te verzamelen die u wilt bijwerken.
* Gebruik de eigenschap **[Updates](controls/control-form-detail.md)** op een besturingselement **[Bewerkingsformulier](controls/control-form-detail.md)** om de wijzigingen te verzamelen die door de gebruiker op een formulier zijn aangebracht.
* Gebruik de functie **[Patch](functions/function-patch.md)** om een gegevensbron bij te werken, maar ook om records samen te voegen.

In dergelijke gevallen is de record nooit een deel van een tabel geweest.

### <a name="record-functions-and-control-properties"></a>Recordfuncties en besturingselementeigenschappen
Functies die records retourneren:

* **[FirstN](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**: retourneert de eerste of de laatste record of records van de tabel.
* **[Opzoeken](functions/function-filter-lookup.md)**: retourneert de eerste record van een tabel die overeenkomt met een of meer criteria.
* **[Patch](functions/function-patch.md)**: werkt een gegevensbron bij of voegt records samen.
* **[Standaarden](functions/function-defaults.md)**: retourneert de standaardwaarden voor een gegevensbron.

Eigenschappen die records retourneren:

* **Geselecteerd**: is van toepassing op galerieën en keuzelijsten. Retourneert de huidige geselecteerde record.
* **Updates**: is van toepassing op galerieën.  Verzamelt alle wijzigingen die een gebruiker op een formulier voor gegevensinvoer maakt.
* **[Update](functions/function-update-updateif.md)**: is van toepassing op besturingselementen voor de invoer, zoals besturingselementen voor tekstinvoer en schuifregelaars. Hiermee worden afzonderlijke eigenschappen ingesteld voor de galerie om te verzamelen.

## <a name="record-scope"></a>Recordbereik
Sommige functies worden uitgevoerd door een formule te evalueren voor alle records van een tabel afzonderlijk.  Het resultaat van de formule wordt op verschillende manieren gebruikt:  

* **Filter**, **Opzoeken**: formule bepaalt of de record moet worden opgenomen in de uitvoer.
* **Sorteren**: formule geeft de waarde waarop de records moeten worden gesorteerd.
* **Samenvoegen**: formule bepaalt de tekenreeksen die moeten worden samengevoegd.
* **ForAll**: formule kan elke waarde retourneren, mogelijk met een neveneffect.
* **Afzonderlijk**: formule retourneert een waarde die wordt gebruikt om dubbele records te identificeren.  
* **AddColumns**: formule geeft de waarde van het toegevoegde veld.
* **Gemiddelde**, **Max**, **Min**, **Som**, **StdevP**, **VarP**: formule geeft de waarde om samen te voegen.

In deze formules kunt u verwijzen naar de velden van de record die wordt verwerkt.  Elk van deze functies maakt een 'recordbereik' waarin de formule wordt geëvalueerd, waarbij de velden van de record beschikbaar zijn als id's op het hoogste niveau.  U kunt in de hele app ook naar eigenschappen van besturingselementen en andere waarden verwijzen.

Neem bijvoorbeeld een tabel met **Producten**:

![](media/working-with-tables/requested.png)

Als u wilt bepalen of er meer naar een van deze producten is gevraagd dan er beschikbaar is:

**Filter( Producten, 'Gevraagde hoeveelheid' > 'Beschikbare hoeveelheid' )**

Het eerste argument om te **Filteren** is de tabel met records waarop de bewerking wordt toegepast en het tweede argument is een formule.  **Filter** maakt een recordbereik voor het evalueren van deze formule waarin de velden van elke record beschikbaar zijn. Dat zijn in dit geval **Product**, **Gevraagde hoeveelheid** en **Beschikbare hoeveelheid**.  Het resultaat van de vergelijking bepaalt of elke record moet worden opgenomen in het resultaat van de functie:

![](media/working-with-tables/needed.png)

Met betrekking tot dit voorbeeld kunnen we berekenen hoeveel we van elk product moeten bestellen:

**AddColumns( Filter( Producten, 'Gevraagde hoeveelheid' > 'Beschikbare hoeveelheid' ), "Te bestellen hoeveelheid", 'Gevraagde hoeveelheid' - 'Beschikbare hoeveelheid' )**

Hier voegen we een berekende kolom toe aan het resultaat.  **AddColumns** heeft zijn eigen recordbereik dat wordt gebruikt om het verschil te berekenen tussen wat er is gevraagd en wat er beschikbaar is.

![](media/working-with-tables/toorder.png)

Ten slotte kunnen we de resultaattabel beperken tot alleen de gewenste kolommen:

**ShowColumns( AddColumns( Filter( Producten, 'Gevraagde hoeveelheid' > 'Beschikbare hoeveelheid' ), "Te bestellen hoeveelheid", 'Gevraagde hoeveelheid' - 'Beschikbare hoeveelheid' ), "Product", "Te bestellen hoeveelheid" )**

![](media/working-with-tables/toorderonly.png)

Houd er rekening mee dat we in het bovenstaande voorbeeld op sommige plekken dubbele aanhalingstekens (") hebben gebruikt en op andere plekken enkele aanhalingstekens (').  Enkele aanhalingstekens zijn vereist wanneer u verwijst naar de waarde van een object, zoals een veld of tabel, waarin de naam van het object een spatie bevat.  Dubbele aanhalingstekens worden gebruikt wanneer er niet naar de waarde van een object wordt verwezen, maar wanneer erover wordt gepraat, met name in situaties waarin het object nog niet bestaat, zoals het geval is met **AddColumns**.  

### <a name="disambiguation"></a>Ondubbelzinnigheid
Veldnamen waarbij het recordbereik is toegevoegd, overschrijven dezelfde namen elders in de app.  Als dit gebeurt, kunt u nog steeds toegang krijgen tot waarden buiten het recordbereik met de operator voor ondubbelzinnigheid [**@**](functions/operators.md):

* Als u toegang wilt krijgen tot waarden van geneste recordbereiken, gebruikt u de operator **@** met de naam van de tabel die wordt bewerkt met behulp van het patroon ***Tabel *[@* Veldnaam*]**.  
* Als u toegang wilt krijgen tot globale waarden, zoals gegevensbronnen, verzamelingen en contextvariabelen, gebruikt u het patroon **[@*Objectnaam*]** (zonder een tabelaanduiding).

Als de tabel die wordt bewerkt een expressie is, zoals een **Filter( *tabel*, ... )**, kan de operator voor ondubbelzinnigheid niet worden gebruikt.  Alleen het binnenste recordbereik kan velden openen vanuit deze tabelexpressie door de operator voor ondubbelzinnigheid niet te gebruiken.

Stelt u zich bijvoorbeeld een verzameling **X** voor:

![](media/working-with-tables/X.png)

U kunt deze verzameling maken met **ClearCollect( X, \[1, 2\] )**.

En een andere verzameling **Y**:

![](media/working-with-tables/Y.png)

U kunt deze verzameling maken met **ClearCollect( Y, ["A", "B"] )**.

Definieer daarnaast een contextvariabele met de naam **Waarde** met deze formule: **UpdateContext( {Waarde: "!"} )**

Laten we alles combineren.  In deze context produceert de volgende formule:

* **Groep opheffen( ForAll( X, ForAll( Y, Y[@Value] & Tekst( X[@Value] ) & [@Value] ) ), "Waarde" )**

de volgende tabel:

![](media/working-with-tables/XY.png)

Wat is hier aan de hand?  De buitenste functie **ForAll** definieert een recordbereik voor **X**, waardoor er toegang tot het veld **Waarde** van elke record mogelijk is, terwijl deze wordt verwerkt.  Met behulp van het woord **Waarde** of met **X[@Value]** kan deze worden geopend.

De binnenste functie **ForAll** definieert een ander recordbereik voor **Y**.  Deze tabel heeft ook een veld **Waarde** gedefinieerd, dus als u **Waarde** hier gebruikt, verwijst deze naar het veld in de record van **Y** en niet meer naar dat van **X**.  Als u toegang tot het veld **Waarde** van **X** wilt krijgen, moet u de langere versie met de operator voor ondubbelzinnigheid gebruiken.

Aangezien **Y** het binnenste recordbereik is, vereist toegang tot de velden van deze tabel geen ondubbelzinnigheid, zodat we de volgende formule met hetzelfde resultaat kunnen gebruiken:

* **Groep opheffen( ForAll( X, ForAll( Y, Waarde & Tekst( X[@Value] ) & [@Value] ) ), "Waarde" )**

Alle recordbereiken **ForAll** overschrijven het globale bereik.  De contextvariabele **Waarde** die we hebben gedefinieerd, is niet beschikbaar op naam zonder de operator voor ondubbelzinnigheid.   Als u toegang tot deze waarde wilt krijgen, moet u **[@Value]** gebruiken.

**Groep opheffen** effent het resultaat, omdat geneste functies **ForAll** resulteren in een geneste resultaattabel.

## <a name="inline-syntax"></a>Inlinesyntaxis
### <a name="records"></a>Records
U drukt records uit met behulp van accolades die veldwaarden met een naam bevatten.  U kunt bijvoorbeeld de eerste record in de tabel aan het begin van dit onderwerp uitdrukken met de volgende formule:

**{ Naam: "Chocolade", Prijs: 3,95, 'Hoeveelheid in voorraad': 12, 'Hoeveelheid in bestelling': 10 }**

U kunt ook formules in andere formules insluiten, zoals het onderstaande voorbeeld weergeeft:

**{ Naam: First(Products).Name, Prijs: First(Products).Price * 1,095 }**

U kunt records nesten door accolades te nesten, zoals het volgende voorbeeld weergeeft:

**{ 'Hoeveelheid': { 'In voorraad': ThisItem.QuantOnHand, 'InBestelling': ThisItem.QuantOnOrder } }**

Sluit elke kolomnaam die een speciaal teken bevat, zoals een spatie of een dubbele punt, in met enkele aanhalingstekens.  Als u een enkel aanhalingsteken in een kolomnaam wilt gebruiken, moet u deze verdubbelen.

Houd er rekening mee dat de waarde in de kolom **Prijs** geen valutasymbool bevat, zoals een dollarteken. Die opmaak wordt toegepast wanneer de waarde wordt weergegeven.  

### <a name="tables"></a>Tabellen
U kunt een tabel maken met de functie **[Table](functions/function-table.md)** en een set records. U kunt de tabel aan het begin van dit onderwerp uitdrukken met de volgende formule:

**Tabel( { Naam: "Chocolade", Prijs: 3,95, 'Hoeveelheid in voorraad': 12, 'Hoeveelheid in bestelling': 10 },<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ Naam: "Brood", Prijs: 4,95, 'Hoeveelheid in voorraad': 34, 'Hoeveelheid in bestelling': 0 },<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ Naam: "Water", Prijs: 4,95, 'Hoeveelheid in voorraad': 10, 'Hoeveelheid in bestelling': 0 } )**

U kunt ook tabellen nesten:

**Tabel( { Naam: "Chocolade",<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;'Hoeveelheid geschiedenis': Tabel( { Kwartaal: "Q1", In voorraad: 10, InBestelling: 10 },<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{ Kwartaal: "Q2", In voorraad: 18, InBestelling: 0 } ) } )**

### <a name="value-tables"></a>Waardetabellen
U kunt tabellen met één kolom maken door waarden op te geven tussen vierkante haken. De resulterende tabel heeft één kolom met de naam **Waarde**.

Bijvoorbeeld, **[ 1, 2, 3, 4 ]** is gelijk aan **Tabel( { Waarde: 1 }, { Waarde: 2 }, { Waarde: 3 }, { Waarde: 4 } )** en retourneert de volgende tabel:

![](media/working-with-tables/inline-table.png)

