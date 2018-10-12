---
title: Informatie over overdracht in een canvas-app | Microsoft Docs
description: Gebruik overdracht om grote gegevenssets efficiënt te verwerken in een canvas-app.
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/05/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0ac78340f344ce42fd68d18940b1aaca41412a96
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42829746"
---
# <a name="understand-delegation-in-a-canvas-app"></a>Informatie over overdracht in een canvas-app
PowerApps bevat een krachtige set functies voor het filteren, sorteren en structureren van gegevenstabellen in een canvas-app: **[Filter](functions/function-filter-lookup.md)**, **[Sort](functions/function-sort.md)** en **[AddColumns](functions/function-table-shaping.md)** om er maar een paar te noemen. Met behulp van deze functies kunt u uw gebruikers gerichte toegang bieden tot de informatie die zij nodig hebben. Voor lezers met een databaseachtergrond is het gebruiken van deze functies vergelijkbare met het schrijven van een databasequery.

Het geheim voor het maken van efficiënte apps is de hoeveelheid gegevens te minimaliseren die moeten worden overgebracht naar een apparaat. Misschien zijn er slechts enkele records uit de totale hoeveelheid van miljoenen records nodig of kan één cumulatieve waarde duizenden records vertegenwoordigen. Het kan ook voldoende zijn om alleen de eerste set records op te halen en de rest pas als de gebruiker daar om vraagt. Een goede focus kan betekenen dat uw app aanzienlijk minder verwerkingskracht, geheugen en netwerkbandbreedte nodig heeft. Het resultaat hiervan is dat de responstijden voor uw gebruikers laag zijn, zelfs op telefoons die zijn verbonden via een mobiel netwerk. 

*Delegering* is waar de expressiviteit van PowerApps-formules en de behoefte om zo min mogelijk gegevens via het netwerk te verplaatsen bij elkaar komen. Kortom, PowerApps delegeert de verwerking van gegevens aan de gegevensbron, in plaats van de gegevens voor lokale verwerking naar de app te verplaatsen.

Waar het ingewikkeld wordt, en wat de bestaansreden is voor dit artikel, is dat niet alles dat kan worden uitgedrukt in een PowerApps-formule aan iedere gegevensbron kan worden gedelegeerd. De PowerApps-taal imiteert de formuletaal van Excel, die is ontworpen op basis van volledige en directe toegang tot een complete werkmap in het geheugen, met een grote verscheidenheid aan functies voor het manipuleren van numerieke waarden en tekst. Als gevolg hiervan is de PowerApps-taal veel uitgebreider dan de meeste gegevensbronnen aankunnen, met inbegrip van krachtige database-engines zoals SQL Server.

**Het werken met grote gegevenssets vereist gegevensbronnen en formules die kunnen worden gedelegeerd.**  Dit is de enige manier om ervoor te zorgen dat uw app goed blijft presteren en gebruikers toegang hebben tot alle informatie die zij nodig hebben. Neem de delegeringswaarschuwingen in acht die aangeven waar delegering niet mogelijk is. Als u werkt met kleine gegevenssets (minder dan 500 records), kunt u elke gegevensbron en formule gebruiken aangezien de app gegevens lokaal kan verwerken als de formule niet kan worden gedelegeerd. 

> [!NOTE]
> Delegeringswaarschuwingen werden eerder in PowerApps gemarkeerd als ‘blauwe stip’-suggesties, maar delegeringssuggesties zijn nu opnieuw geclassificeerd als waarschuwingen. Als de gegevens in uw gegevensbron meer dan 500 records beslaan en een functie niet kan worden gedelegeerd, kan PowerApps mogelijk niet alle gegevens ophalen en heeft uw app mogelijk onjuiste resultaten. Delegeringswaarschuwingen helpen u bij het beheren van uw app, zodat deze de juiste resultaten heeft.

## <a name="delegable-data-sources"></a>Delegeerbare gegevensbronnen
Zie dit [overzicht](delegation-list.md) voor een volledige lijst van de gegevensbronnen die delegering ondersteunen en in welke mate.

Het is wel zo dat er regelmatig ondersteuning voor delegering wordt toegevoegd aan bestaande gegevensbronnen, plus dat er steeds meer gegevensbronnen bijkomen.

Er is geen delegering nodig voor geïmporteerde Excel-werkmappen (via de gegevensbron 'Statische gegevens toevoegen aan uw app'), verzamelingen en tabellen die zijn opgeslagen in contextvariabelen. Al deze gegevens zijn al aanwezig in het geheugen en de PowerApps-taal kan maximaal worden toegepast.

## <a name="delegable-functions"></a>Delegeerbare functies
De volgende stap is om alleen de formules te gebruiken die kunnen worden gedelegeerd. Hier worden alle formule-elementen beschreven die kunnen worden gedelegeerd. Elke gegevensbron is echter anders en niet alle gegevensbronnen ondersteunen al deze elementen. Controleer op delegeringswaarschuwingen in uw specifieke formule.

Deze lijsten worden trouwens regelmatig bijgewerkt. We zijn bezig om voor meer functies en operatoren ondersteuning voor delegering aan te bieden.

### <a name="filter-functions"></a>Filterfuncties
**[Filter](functions/function-filter-lookup.md)**, **[Search](functions/function-filter-lookup.md)** en **[LookUp](functions/function-filter-lookup.md)** kunnen worden gedelegeerd.  

Binnen de functies **Filter** en **LookUp** kunt u deze gebruiken met kolommen van de tabel om de juiste records te selecteren:

* **[And](functions/function-logicals.md)** (inclusief **[&&](functions/operators.md)**), **[Or](functions/function-logicals.md)** (inclusief **[||](functions/operators.md)**), **[Not](functions/function-logicals.md)** (inclusief **[!](functions/operators.md)**)
* **[In](functions/operators.md)**
* **[=](functions/operators.md)**, **[<>](functions/operators.md)**, **[>=](functions/operators.md)**, **[<=](functions/operators.md)**, **[>](functions/operators.md)**, **[<](functions/operators.md)**
* **[+](functions/operators.md)**, **[-](functions/operators.md)**
* **[TrimEnds](functions/function-trim.md)**
* **[IsBlank](functions/function-isblank-isempty.md)**
* **[StartsWith](functions/function-startswith.md)**
* Constante waarden die hetzelfde zijn voor alle records, zoals de eigenschappen van besturingselementen en [globale en contextvariabelen](working-with-variables.md).

U kunt ook elementen van uw formule gebruiken die evalueren tot een constante waarde voor alle records. **Left (Language(), 2)** is bijvoorbeeld niet afhankelijk van een kolom van de record en retourneert dus voor alle records dezelfde waarde. Het is in feite een constante. Het gebruik van contextvariabelen, verzamelingen en signalen is mogelijk niet constant en daarom kunnen **Filter** en **LookUp** niet worden gedelegeerd.  

De vorige lijst bevat deze belangrijke items niet:

* **[If](functions/function-if.md)**
* **[*](functions/operators.md)**, **[/](functions/operators.md)**, **[Mod](functions/function-mod.md)**
* **[Concatenate](functions/function-concatenate.md)** (inclusief **[&](functions/operators.md)**)
* **[ExactIn](functions/operators.md)**
* Functies voor tekenreeksmanipulatie: **[Lower](functions/function-lower-upper-proper.md)**, **[Upper](functions/function-lower-upper-proper.md)**, **[Left](functions/function-left-mid-right.md)**, **[Mid](functions/function-left-mid-right.md)**, **[Len](functions/function-left-mid-right.md)**, ...
* Signalen: **[Location](functions/signals.md)**, **[Acceleration](functions/signals.md)**, **[Compass](functions/signals.md)**, ...
* Vluchtige functies: **[Now](functions/function-now-today-istoday.md)**, **[Today](functions/function-now-today-istoday.md)**, **[Rand](functions/function-rand.md)**, ...
* [Verzamelingen](working-with-variables.md)

### <a name="sorting-functions"></a>Sorteerfuncties
**[Sort](functions/function-sort.md)** en **[SortByColumns](functions/function-sort.md)** kunnen worden gedelegeerd.

Bij **Sort** kan de formule alleen bestaan uit de naam van één kolom. Bovendien kan de formule geen andere operatoren of functies bevatten.

### <a name="aggregate-functions"></a>Statistische functies
**[Sum](functions/function-aggregates.md)**, **[Average](functions/function-aggregates.md)**, **[Min](functions/function-aggregates.md)** en **[Max](functions/function-aggregates.md)** kunnen worden gedelegeerd. Op dit moment wordt deze delegering maar door een beperkt aantal gegevensbronnen ondersteund. Bekijk de [delegeringslijst](delegation-list.md) voor informatie.

Optelfuncties, zoals **[CountRows](functions/function-table-counts.md)**, **[CountA](functions/function-table-counts.md)** en **[Count](functions/function-table-counts.md)**, kunnen niet worden gedelegeerd.

Andere statistische functies, zoals **[StdevP](functions/function-aggregates.md)** en **[VarP ](functions/function-aggregates.md)**, kunnen niet worden gedelegeerd.

## <a name="non-delegable-functions"></a>Niet-delegeerbare functies
Alle andere functies bieden geen ondersteuning voor delegeringen, waaronder deze belangrijke functies:

* Tabel aanpassen: **[AddColumns](functions/function-table-shaping.md)**, **[DropColumns](functions/function-table-shaping.md)**, **[ShowColumns](functions/function-table-shaping.md)**, ...
* **[First](functions/function-first-last.md)**, **[FirstN](functions/function-first-last.md)**, **[Last](functions/function-first-last.md)**, **[LastN](functions/function-first-last.md)**
* **[Choices](functions/function-choices.md)**
* **[Concat](functions/function-concatenate.md)**
* **[Collect](functions/function-clear-collect-clearcollect.md)**, **[ClearCollect](functions/function-clear-collect-clearcollect.md)**
* **[CountIf](functions/function-table-counts.md)**, **[RemoveIf](functions/function-remove-removeif.md)**, **[UpdateIf](functions/function-update-updateif.md)**
* **[GroupBy](functions/function-groupby.md)**, **[Ungroup](functions/function-groupby.md)**

Een veelgebruikte methode is om **AddColumns** en **LookUp** te gebruiken om gegevens uit de ene tabel samen te voegen in een andere tabel, iets wat in databasejargon een 'join' wordt genoemd.  Bijvoorbeeld:

**AddColumns( Producten, "Naam leverancier", LookUp( Leveranciers, Suppliers.ID = Product.SupplierID ).Name )**

Hoewel **Producten** en **Leveranciers** delegeerbare gegevensbronnen kunnen zijn en **LookUp** een delegeerbare functie is, geldt dat niet voor de functie **AddColumns**.  Het resultaat van de gehele formule wordt dan ook beperkt tot het eerste deel van de gegevensbron **Producten**.  

Omdat de functie **LookUp** en de bijbehorende gegevensbron delegeerbaar zijn, kan er overal in de gegevensbron een overeenkomst worden gevonden voor **Leveranciers**, zelfs als het een grote gegevensbron is. Een mogelijk nadeel is dat **LookUp** voor elk van de eerste records in **Producten** afzonderlijke aanroepen naar de gegevensbron gebruikt, waardoor er nogal wat ruis op het netwerk wordt veroorzaakt. Als de gegevensbron **Leveranciers** niet zo groot is en niet regelmatig verandert, zou u de gegevensbron bij het starten van de app met een aanroep van **Collect** kunnen cachen in de app. U gebruikt hiervoor [**OnVisible**](controls/control-screen.md) op het openingsscherm en voert dan **LookUp** uit op de gegevensbron in de cache.  

## <a name="non-delegable-limits"></a>Limiet voor delegering
Formules die kunnen niet worden gedelegeerd, worden lokaal verwerkt. Op deze manier is het mogelijk om alle functionaliteit van de formuletaal van PowerApps te benutten. Hier zit echter wel een nadeel aan, namelijk dat alle gegevens eerst moeten worden overgebracht naar het apparaat. Dit kan betekenen dat er een grote hoeveelheid gegevens via het netwerk moet worden opgehaald. Dat kan even duren, waardoor het kan lijken dat uw app traag is of misschien zelfs is vastgelopen.

Om dit te voorkomen, is er in PowerApps standaard een limiet ingesteld voor de hoeveelheid gegevens die lokaal kan worden verwerkt: 500 records.  We hebben dit aantal gekozen omdat u dan nog steeds volledige toegang hebt tot kleine gegevenssets, terwijl u het gebruik van grote gegevenssets kunt verfijnen door deelresultaten weer te geven.

Uiteraard moet hier voorzichtig mee worden omgegaan, omdat het verwarrend kan zijn voor gebruikers. Laten we als voorbeeld de functie **Filter** nemen met een selectieformule die niet kan worden gedelegeerd, met een gegevensbron die een miljoen records bevat. Omdat het filteren lokaal plaatsvindt, worden alleen de eerste 500 records gescand. Als de gewenste record 501 is, of 500.001, wordt de record niet geretourneerd door **Filter**.

Statistische functies kunnen ook leiden tot verwarring. Stel dat **Average** wordt toegepast op een kolom uit diezelfde gegevensbron met een miljoen records. **Average** kan nog niet worden gedelegeerd en daarom wordt alleen het gemiddelde van de eerste 500 records geretourneerd. Als u niet voorzichtig bent, kan een deelresultaat onterecht als een volledig resultaat worden geïnterpreteerd door een gebruiker van uw app.

## <a name="changing-the-limit"></a>De limiet wijzigen
500 is het standaard aantal records, maar u kunt dit aantal wijzigen voor een volledige app:

1. Selecteer op het tabblad **Bestand** de optie **App-instellingen**.
2. Onder **Experimentele functies** wijzigt u de instelling **Gegevensrijlimiet voor niet-delegeerbare query's** van 1 in 2000.

In sommige gevallen weet u dat 2000 (of 1000 of 1500) voldoende is voor uw scenario. U kunt dit aantal vergroten voor uw scenario. Doe dit wel altijd zorgvuldig. Als u dit aantal vergroot, kunnen de prestaties van de app verslechteren, vooral bij brede tabellen met veel kolommen. U kunt het beste zo veel mogelijk delegeren.

Als u er zeker van wilt zijn dat uw app naar grote gegevenssets kan schalen, stelt u de instelling in op 1. Voor alles wat niet kan worden gedelegeerd, wordt één record geretourneerd. Dit kunt u eenvoudig detecteren tijdens het testen van uw app. Op die manier komt u niet voor verrassingen te staan wanneer u een concept-app in productie wilt nemen.

## <a name="delegation-warnings"></a>Delegeringswaarschuwingen
Om het eenvoudiger te maken om te zien wat wel en wat niet wordt gedelegeerd, geeft PowerApps een waarschuwing (gele driehoek) wanneer u een formule maakt die iets bevat wat niet kan worden gedelegeerd.

Delegeringswaarschuwingen worden alleen weergegeven in formules die worden toegepast op delegeerbare gegevensbronnen. Als u geen waarschuwing ziet en u denkt dat de formule niet correct wordt gedelegeerd, controleert u het type van de gegevensbron in de lijst met [delegeerbare gegevensbronnen](delegation-overview.md#delegable-data-sources) eerder in dit onderwerp.

## <a name="examples"></a>Voorbeelden
In dit voorbeeld genereert u automatisch een app met drie schermen op basis van een SQL Server-tabel met de naam **[dbo].[Fruit]**. Voor informatie over het genereren van de app, kunt u vergelijkbare principes toepassen op het [onderwerp over Common Data Service voor apps](data-platform-create-app.md) met SQL Server.

![App met drie schermen](./media/delegation-overview/products-afd.png)

De eigenschap **Items** van de galerie is ingesteld op een formule die de functies **SortByColumns** en **Search** bevat, die beide kunnen worden gedelegeerd.

Typ **Apple** in het zoekvak.

Bewegende stippen worden tijdelijk weergegeven aan de bovenkant van het scherm als de app communiceert met SQL Server om de zoekopdracht te verwerken. Alle records die voldoen aan de zoekcriteria worden weergegeven, zelfs als de gegevensbron miljoenen records bevat.

![Besturingselement voor invoer van zoektekst](./media/delegation-overview/products-apple.png)

De zoekresultaten bevatten **Apples**, **Crab apples** en **Pineapple** omdat de functie **Zoeken** overal in een tekstkolom zoekt. Als u alleen records wilt vinden die de zoekterm aan het begin van de naam van de vrucht bevatten, kunt u een andere delegeerbare functie, **Filter**, gebruiken met een complexere zoekterm. (Verwijder omwille van de eenvoud de aanroep **SortByColumns**.)

![De aanroep SortByColumns verwijderen](./media/delegation-overview/products-apple-delegationwarning.png)

De nieuwe resultaten bevatten **Apples** , maar niet **Crab apples** of **Pineapple**.  Er wordt echter een gele driehoek weergegeven naast de galerie (en in de schermminiatuur als op de linkernavigatiebalk miniaturen worden weergegeven). Er wordt ook een blauwe golvende lijn weergegeven onder een deel van de formule. Al deze elementen geven een waarschuwing aan. Als u de muisaanwijzer op de gele driehoek naast de galerie plaatst, wordt dit bericht weergegeven:

![Beweeg de muisaanwijzer over de delegeringswaarschuwing](./media/delegation-overview/products-apple-yellowwarning.png)

SQL Server is een delegeerbare gegevensbron en **Filter** is een delegeerbare functie. **Mid** en **Len** kunnen echter niet worden gedelegeerd naar een gegevensbron.

Maar het heeft wel gewerkt, toch? In zekere zin wel. En daarom is dit een waarschuwing, en geen rode, golvende lijn.

- Als de tabel minder dan 500 records bevat, werkte de formule perfect. Alle records zijn dan overgebracht naar het apparaat en **Filter** is lokaal toegepast.
- Als de tabel meer dan 500 records bevat, geeft de formule niet als resultaat record 501 of hoger, ook niet als deze voldoet aan de criteria.
