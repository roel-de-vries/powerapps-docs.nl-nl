---
title: Functies, signalen en opsommingen | Microsoft Docs
description: Verwijzingsgegevens voor functies, signalen en opsommingen in PowerApps.
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/28/2017
ms.author: gregli
ms.openlocfilehash: 3ceb9eae42e88e7cfb78492f9e58812481a0881d
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2018
---
# <a name="formula-reference-for-powerapps"></a>Formuleverwijzingen voor PowerApps
Formules combineren veel elementen.  Hieronder worden vermeld:

* **Functies** hebben parameters, voeren bewerkingen uit en retourneren een waarde. Bijvoorbeeld: **Sqrt(25)** retourneert **5**. Functies zijn gemodelleerd naar Microsoft Excel-functies.  Sommige functies hebben neveneffecten, zoals **Formulier verzenden**, die alleen geschikt zijn bij [gedragsformules](working-with-formulas-in-depth.md) zoals **Button.OnSelect**.
* **Signalen** retourneren informatie over de omgeving. Bijvoorbeeld: **[Locatie](functions/signals.md)** retourneert de huidige GPS-coördinaten van het apparaat. Signalen hebben geen parameters of neveneffecten.
* **Opsommingen** retourneren een vooraf gedefinieerde constante waarde. Bijvoorbeeld: **[Kleur](functions/function-colors.md)** is een opsomming met vooraf gedefinieerde waarden voor **Color.Red**, **Color.Blue**, enzovoort.  Algemene opsommingen zijn hier opgenomen. Functiespecifieke opsommingen worden beschreven bij de functie zelf.
* **Operators met een naam**, zoals **[ThisItem](functions/operators.md#thisitem-operator)** en **[Parent](functions/operators.md#parent-operator)**, bieden toegang tot de gegevens in een container.

Andere elementen zijn:

* [Alle operators](functions/operators.md)
* [Besturingselementen en hun eigenschappen](reference-properties.md)

## <a name="a"></a>A
**[Abs](functions/function-numericals.md)**: absolute waarde van een getal.  

**[Acceleration](functions/signals.md)**: leest de versnellingssensor in uw apparaat.

**[Boogcos](functions/function-trig.md)**: retourneert de arccosinus van een getal in radialen.

**[Boogcot](functions/function-trig.md)**: retourneert de boogcotangens van een getal in radialen.

**[AddColumns](functions/function-table-shaping.md)**: retourneert een tabel met toegevoegde [kolommen](working-with-tables.md#columns).

**[En](functions/function-logicals.md)**: Booleaanse logica EN.  Retourneert **waar** als alle argumenten **waar** zijn.  U kunt ook de operator [**&&** gebruiken](functions/operators.md).

**[App](functions/signals.md)**: retourneert informatie over de app die op dat moment wordt uitgevoerd (bijvoorbeeld welke scherm op dat moment wordt weergegeven).

**[Boogsin](functions/function-trig.md)**: retourneert de arcsinus van een getal in radialen.

**[Atan](functions/function-trig.md)**: retourneert de boogtangens van een getal in radialen.

**[Atan2](functions/function-trig.md)**: retourneert de boogtangens op basis van (*x*, *y*) in radialen.

**[Gemiddelde](functions/function-aggregates.md)**: berekent het gemiddelde van een tabelexpressie of een set argumenten.

## <a name="b"></a>B
**[Terug](functions/function-navigate.md)**: geeft het vorige scherm weer.  

**[Leeg](functions/function-isblank-isempty.md)**: retourneert een *lege* waarde die kan worden gebruikt om een NULL-waarde in een gegevensbron in te voegen.

## <a name="c"></a>C
**[Agenda](functions/function-clock-calendar.md)**: haalt informatie op over de agenda voor de huidige landinstelling.

**[Char](functions/function-char.md)**: vertaalt een tekencode naar een tekenreeks.

**[Wissen](functions/function-clear-collect-clearcollect.md)**: verwijdert alle gegevens van een [verzameling](working-with-data-sources.md#collections).

**[ClearCollect](functions/function-clear-collect-clearcollect.md)**: verwijdert alle gegevens van een verzameling en voegt vervolgens een set [records](working-with-tables.md#records) toe.

**[Clock](functions/function-clock-calendar.md)**: haalt informatie op over de klok voor de huidige landinstelling.

**[Coalesce](functions/function-isblank-isempty.md)** – Vervangt *lege* waarden en laat niet-*lege* waarden ongewijzigd.

**[Collect](functions/function-clear-collect-clearcollect.md)**: maakt een verzameling of voegt gegevens toe aan een gegevensbron.

**[Kleur](functions/function-colors.md)**: stelt een eigenschap in op een ingebouwde kleurwaarde.

**[ColorFade](functions/function-colors.md)**: vervaagt een kleurwaarde.

**[ColorValue](functions/function-colors.md)**: vertaalt de naam van een CSS-kleur of een hex-code naar een kleurwaarde.  

**[Kompas](functions/signals.md)**: retourneert de koptekst van uw kompas.

**[Concat](functions/function-concatenate.md)**: voegt tekenreeksen in een gegevensbron samen.  

**[Samenvoegen](functions/function-concatenate.md)**: voegt tekenreeksen samen.

**[Connection](functions/signals.md)**: retourneert informatie over uw netwerkverbinding.

**[Aantal](functions/function-table-counts.md)**: telt tabelrecords die getallen bevatten.

**[Cos](functions/function-trig.md)**: retourneert de cosinus van een hoek aangeduid in radialen.

**[Cot](functions/function-trig.md)**: retourneert de cotangens van een hoek aangeduid in radialen.

**[Aantalarg](functions/function-table-counts.md)**: telt tabelrecords die niet [leeg](functions/function-isblank-isempty.md) zijn.

**[Aantal.als](functions/function-table-counts.md)**: telt tabelrecords die voldoen aan een voorwaarde.  

**[CountRows](functions/function-table-counts.md)**: telt tabelrecords.   

## <a name="d"></a>D
**[DataSourceInfo](functions/function-datasourceinfo.md)**: biedt informatie over een gegevensbron.

**[Datum](functions/function-date-time.md)**: retourneert een datum/tijd-waarde op basis van de waarden voor **Jaar**, **Maand** en **Dag**.  

**[DateAdd](functions/function-dateadd-datediff.md)**: voegt dagen, maanden, kwartalen of jaren toe aan een datum/tijd-waarde.

**[DateDiff](functions/function-dateadd-datediff.md)**: trekt twee datumwaarden af en geeft het resultaat weer in dagen, maanden, kwartalen of jaren.

**[DateTimeValue](functions/function-datevalue-timevalue.md)**: converteert een tekenreeks met datum en tijd naar een datum/tijd-waarde.

**[DateValue](functions/function-datevalue-timevalue.md)**: converteert een tekenreeks met alleen een datum naar een datum/tijd-waarde.

**[Dag](functions/function-datetime-parts.md)**: haalt het daggedeelte op uit een datum/tijd-waarde.  

**[Defaults](functions/function-defaults.md)**: retourneert de standaardwaarden voor een gegevensbron.

**[Degrees](functions/function-trig.md)**: converteert radialen naar graden.

**[Disable](functions/function-enable-disable.md)**: schakelt een signaal uit, zoals **[Location](functions/signals.md)** voor het lezen van de GPS.

**[Distinct](functions/function-distinct.md)**: geeft een overzicht van de records in een tabel en verwijdert dubbele gegevens.  

**[Downloaden](functions/function-param.md)**: downloadt een bestand van internet naar het lokale apparaat.

**[DropColumns](functions/function-table-shaping.md)**: retourneert een tabel waarin een of meer kolommen zijn verwijderd.

## <a name="e"></a>E
**[EditForm](functions/function-form.md)**: stelt een besturingselement voor formulieren opnieuw in om een item te bewerken.

**[Inschakelen](functions/function-enable-disable.md)**: schakelt een signaal in, zoals **[Locatie](functions/signals.md)** voor het lezen van de GPS.

**[EndsWith](functions/function-startswith.md)** – Controleert of een tekenreeks eindigt met een andere tekenreeks.

**[Fouten](functions/function-errors.md)**: biedt foutinformatie voor eerdere wijzigingen in een gegevensbron.

**[EncodeUrl](functions/function-encode-decode.md)**: codeert speciale tekens met behulp van URL-codering.

**[Afsluiten](functions/function-exit.md)**: sluit de app die op dat moment wordt uitgevoerd.

**[Exp](functions/function-numericals.md)**: retourneert *e* tot een macht verheven.

## <a name="f"></a>F
**[Filteren](functions/function-filter-lookup.md)**: retourneert een gefilterde tabel op basis van een of meer criteria.

**[Find](functions/function-find.md)**: controleert of een tekenreeks binnen een andere wordt weergegeven en retourneert de locatie.

**[Eerste](functions/function-first-last.md)**: retourneert de eerste record van een tabel.

**[FirstN](functions/function-first-last.md)**: retourneert de eerste set records (N-records) van een tabel.

**[ForAll](functions/function-forall.md)**: berekent waarden en voert acties uit voor alle records van een tabel.

## <a name="g"></a>G
**[GroupBy](functions/function-groupby.md)**: retourneert een tabel met de records gegroepeerd.

## <a name="h"></a>H
**[HashTags](functions/function-hashtags.md)**: pakt de hashtags (#strings) van een tekenreeks uit.

**[Uur](functions/function-datetime-parts.md)**: retourneert het uurgedeelte van een datum/tijd-waarde.

## <a name="i"></a>I
**[If](functions/function-if.md)**: retourneert één waarde als een voorwaarde waar is en een andere waarde niet waar is. 

**[IfError](functions/function-iferror.md)**: hiermee worden fouten gedetecteerd en wordt er een alternatieve waarde opgegeven of actie ondernomen. 

**[IsBlank](functions/function-isblank-isempty.md)**:controleert op een waarde [leeg](functions/function-isblank-isempty.md).

**[IsEmpty](functions/function-isblank-isempty.md)**: controleert op een lege tabel.

**[IsMatch](functions/function-ismatch.md)**: controleert een tekenreeks met een patroon.  Reguliere expressies kunnen worden gebruikt.

**[IsNumeric](functions/function-isnumeric.md)**: controleert op een numerieke waarde.

**[IsVandaag](functions/function-now-today-istoday.md)**: controleert of een datum/tijd-waarde vandaag is.

## <a name="l"></a>L
**[Language](functions/function-language.md)**: retourneert de taalcode voor de huidige gebruiker.

**[Laatste](functions/function-first-last.md)**: retourneert de laatste record van een tabel.

**[LastN](functions/function-first-last.md)**: retourneert de laatste set records (N-records) van een tabel.

**[Start](functions/function-param.md)**: start een webadres of een app.

**[Links](functions/function-left-mid-right.md)**: retourneert het meest linkse gedeelte van een tekenreeks.

**[Len](functions/function-len.md)**: retourneert de lengte van een tekenreeks.

**[Ln](functions/function-numericals.md)**: retourneert het natuurlijke logboek.

**[LoadData](functions/function-savedata-loaddata.md)**: laadt een verzameling uit PowerApps-privéopslag.

**[Locatie](functions/signals.md)**: retourneert uw locatie als een kaartcoördinaat via GPS (Global Positioning System) en andere informatie.

**[LookUp](functions/function-filter-lookup.md)**: zoekt een enkele record in een tabel op basis van een of meer criteria.

**[Kleine letters](functions/function-lower-upper-proper.md)**: converteert letters in een tekenreeks met tekst naar kleine letters.

## <a name="m"></a>M
**[Max](functions/function-aggregates.md)**: maximumwaarde van een tabelexpressie of een set argumenten.

**[Mid](functions/function-left-mid-right.md)**: retourneert het middelste gedeelte van een tekenreeks.

**[Min](functions/function-aggregates.md)**: minimumwaarde van een tabelexpressie of een set argumenten.

**[Minuut](functions/function-datetime-parts.md)**: haalt het minuutgedeelte op uit een datum/tijd-waarde.  

**[Mod](functions/function-mod.md)**: retourneert het restgetal nadat een deeltal is gedeeld door een deler.

**[Dag](functions/function-datetime-parts.md)**: haalt het maandgedeelte op uit een datum/tijd-waarde.

## <a name="n"></a>N
**[Navigeren](functions/function-navigate.md)**: wijzigt welke scherm wordt weergegeven.

**[NewForm](functions/function-form.md)**: stelt een besturingselement voor formulieren opnieuw in om een item te maken.

**[Niet](functions/function-logicals.md)**: Booleaanse logica NIET.  Retourneert **waar** als het bijbehorende argument **onwaar** is, en retourneert **onwaar** als het bijbehorende argument **waar**.  U kunt ook de operator [**!** gebruiken](functions/operators.md).

**[Nu](functions/function-now-today-istoday.md)**: retourneert de huidige datum/tijd-waarde.

## <a name="o"></a>O
**[Of](functions/function-logicals.md)**: Booleaanse logica OF.  Retourneert **waar** als alle bijbehorende argumenten **waar** zijn.  U kunt ook de operator [**||** gebruiken](functions/operators.md).

## <a name="p"></a>P
**[Parameter](functions/function-param.md)**: biedt toegang tot parameters die zijn doorgegeven aan de app toen de gebruiker deze opende.

**[Bovenliggende](functions/operators.md#parent-operator)**: biedt toegang tot de eigenschappen van een containerbesturingselement.

**[Patch](functions/function-patch.md)**: wijzigt of maakt een record in een gegevensbron of voegt records buiten een gegevensbron samen.

**[Pi](functions/function-trig.md)**: retourneer het getal &pi;.

**[Platte tekst](functions/function-encode-decode.md)**: verwijdert HTML- en XML-tags uit een tekenreeks.

**[Macht](functions/function-numericals.md)**: retourneert een getal dat tot een macht is verheven.  U kunt ook de operator [**^** gebruiken](functions/operators.md).

**[Beginletters](functions/function-lower-upper-proper.md)**: converteert de eerste letter van elk woord in een tekenreeks naar hoofdletters, en de rest naar kleine letters.

## <a name="r"></a>R
**[Radialen](functions/function-trig.md)**: converteert graden naar radialen.

**[Rand](functions/function-rand.md)**: retourneert een pseudo-willekeurig getal.

**[Vernieuwen](functions/function-refresh.md)**: vernieuwt de records van een gegevensbron.

**[Verwijderen](functions/function-remove-removeif.md)**: verwijder een of meer specifieke records uit een gegevensbron.

**[RemoveIf](functions/function-remove-removeif.md)**: verwijdert records uit een gegevensbron op basis van een voorwaarde.

**[RenameColumns](functions/function-table-shaping.md)**: wijzigt de namen van de kolommen in een tabel.

**[Vervangen](functions/function-replace-substitute.md)**: vervangt een gedeelte van een tekenreeks door een andere tekenreeks, op basis van de startpositie van de tekenreeks.

**[Opnieuw instellen](functions/function-reset.md)**: hiermee stelt u een invoer-besturingselement in op de standaardwaarde en worden gebruikerswijzigingen genegeerd.

**[ResetForm](functions/function-form.md)**: stelt een besturingselement voor formulieren opnieuw in om een bestaand item te bewerken.

**[Terugkeren](functions/function-revert.md)**: laadt fouten in de records van een gegevensbron opnieuw en wist ze.

**[RGBA](functions/function-colors.md)**: retourneert een kleurwaarde voor een set rode, groene en blauwe onderdelen, en alfaonderdelen.

**[Rechts](functions/function-left-mid-right.md)**: retourneert het meest rechtse gedeelte van een tekenreeks.

**[Round](functions/function-round.md)**: rondt af naar het dichtstbijzijnde getal.

**[RoundDown](functions/function-round.md)**: rondt af naar het grootste vorige getal.

**[Afronden.naar.boven](functions/function-round.md)**: rondt af naar het kleinste volgende getal.

## <a name="s"></a>S
**[SaveData](functions/function-savedata-loaddata.md)**: slaat een verzameling op in PowerApps-privéopslag.

**[Zoeken](functions/function-filter-lookup.md)**: zoekt records in een tabel met een tekenreeks in een van de kolommen.  

**[Second](functions/function-datetime-parts.md)**: haalt het secondegedeelte op uit een datum/tijd-waarde.

**[Instellen](functions/function-set.md)**: stelt de waarde van een globale variabele in.

**[ShowColumns](functions/function-table-shaping.md)**: retourneert een tabel met alleen geselecteerde kolommen.

**[ShowError](functions/function-showerror.md)**: hiermee wordt een foutbericht weergegeven aan de gebruiker.

**[Shuffle](functions/function-shuffle.md)**: plaatst de records in een tabel in een willekeurige volgorde.

**[Sin](functions/function-trig.md)**: retourneert de sinus van een hoek aangeduid in radialen.

**[Sorteren](functions/function-sort.md)**: retourneert een gesorteerde tabel op basis van een formule.

**[SortByColumns](functions/function-sort.md)**: retourneert een gesorteerde tabel op basis van een of meer kolommen.

**[Split](functions/function-split.md)**: splitst een teksttekenreeks in een tabel met subtekenreeksen.

**[Sqrt](functions/function-numericals.md)**: retourneert de vierkantswortel van een getal.

**[StartsWith](functions/function-startswith.md)**: controleert of een tekenreeks begint met een andere tekenreeks.

**[StDevP](functions/function-aggregates.md)**: retourneert de standaardafwijking van de argumenten.  

**[Substitute](functions/function-replace-substitute.md)**: vervangt een gedeelte van een tekenreeks door een andere tekenreeks, door overeenkomstige tekenreeksen.

**[SubmitForm](functions/function-form.md)**: slaat het item in een formulierbesturingselement op in de gegevensbron.

**[Sum](functions/function-aggregates.md)**: berekent de som van een tabelexpressie of een set argumenten.  

**[Omzetten](functions/function-if.md)**: komt overeen met een set waarden en evalueert vervolgens een bijbehorende formule.

## <a name="t"></a>T
**[Tabel](functions/function-table.md)**: maakt een tijdelijke tabel.  

**[Tan](functions/function-trig.md)**: retourneert de tangens van een hoek aangeduid in radialen.

**[Tekst](functions/function-text.md)**: maakt een getal op als een tekenreeks om weer te geven.

**[ThisItem](functions/operators.md#thisitem-operator)**: retourneert, in een galerie of formulier, de gegevens voor het huidige item uit de container.

**[Tijd](functions/function-date-time.md)**: retourneert een datum/tijd-waarde, op basis van de waarden voor **uur**, **minuut** en **seconde**.  

**[TimeValue](functions/function-datevalue-timevalue.md)**: converteert een tekenreeks met alleen een tijd naar een datum/tijd-waarde.

**[TimeZoneOffset](functions/function-dateadd-datediff.md)**: retourneert het verschil tussen UTC en de lokale tijd van de gebruiker in minuten.

**[Today](functions/function-now-today-istoday.md)**: retourneert de huidige datum/tijd-waarde.

**[Trim](functions/function-trim.md)**: verwijdert extra spaties bij de uiteinden en in het middengedeelte van een tekenreeks.

**[Einden.Knippen](functions/function-trim.md)**: verwijdert alleen extra spaties bij de uiteinden van een tekenreeks.

## <a name="u"></a>U
**[GroepOpheffen](functions/function-groupby.md)**: verwijdert een groepering.

**[Update](functions/function-update-updateif.md)**: vervangt een record in een gegevensbron.

**[UpdateContext](functions/function-updatecontext.md)**: stelt de waarde van een of meer [contextvariabelen](working-with-variables.md#create-a-context-variable) van het huidige scherm in.

**[UpdateIf](functions/function-update-updateif.md)**: wijzigt een set records in een gegevensbron op basis van een voorwaarde.

**[Hoofdletters](functions/function-lower-upper-proper.md)**: converteert letters in een tekenreeks met tekst naar hoofdletters.

**[Gebruiker](functions/function-user.md)**: retourneert informatie over de huidige gebruiker.

## <a name="v"></a>V
**[Valideren](functions/function-validate.md)**: controleert of de waarde van één kolom of een volledige gegevensrecord geldig is voor een gegevensbron.

**[Waarde](functions/function-value.md)**: converteert een tekenreeks naar een getal.

**[VarP](functions/function-aggregates.md)**: retourneert de variantie van de bijbehorende argumenten.  

**[ViewForm](functions/function-form.md)**: stelt een besturingselement voor formulieren opnieuw in om een bestaand item weer te geven.

## <a name="w"></a>W
**[Weekdag](functions/function-datetime-parts.md)**: haalt het weekgedeelte op uit een datum/tijd-waarde.

## <a name="y"></a>Y
**[Jaar](functions/function-datetime-parts.md)**: haalt het jaargedeelte op uit een datum/tijd-waarde.  

