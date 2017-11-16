---
title: Tekst weergeven en de datum- of tijdnotatie instellen | Microsoft Docs
description: Datums en tijden toevoegen en instellen met PowerApps
services: 
suite: powerapps
documentationcenter: 
author: AFTOwen
manager: anneta
editor: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2016
ms.author: anneta
ms.openlocfilehash: 0fcfb90de55c0504a7a7ff5e7d75cd782b8f56e6
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="show-text-and-format-dates-and-times-in-powerapps"></a>Tekst weergeven en de datum- en tijdnotatie instellen in PowerApps
Voeg datums en tijden toe en pas de notatie aan aan het gewenste detailniveau of uw taalgebied. Bereken de tijd tussen twee datums of geef een bepaalde datum op en bereken wat de datum een bepaalde periode voor of na die datum is. Converteer datums van of naar afzonderlijke waarden voor dagen, maanden en jaren en converteer tijden van of naar afzonderlijke waarden voor uren, minuten en seconden.

Voeg bijvoorbeeld gebruikersgegevens toe over aandelentransacties of cliëntvergaderingen of gegevens uit een andere app die in PowerApps is gemaakt. Als deze gegevens tijden bevatten die tot de milliseconde nauwkeurig zijn, kunt u deze voor het gemak afronden naar de dichtstbijzijnde minuut. Bereken het aantal dagen tot een belangrijke mijlpaal. Als u plannen iedere vijf dagen vergaderingen met klanten wilt inplannen, kunnen deze datums automatisch worden berekend. Als de datum 10 mei 1985 is opgeslagen in afzonderlijke velden voor dag, maand en jaar, kunt u deze samenbrengen tot één waarde. Of, als uw app deze waarden apart beheert, kunt u elke datum ook in aparte waarden opsplitsen.

**Vereisten**

* [Registreer u](signup-for-powerapps.md) voor PowerApps, [installeer](http://aka.ms/powerappsinstall) het, open het en meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.
* Maak een app of open een bestaande app in PowerApps.
* Lees hoe u [een besturingselement kunt configureren](add-configure-controls.md) in PowerApps.

## <a name="show-text-in-a-label-control"></a>Tekst in een besturingselement Label weergeven
Geef tekst weer in een besturingselement **[Label](controls/control-text-box.md)** door de waarde van de eigenschap **[Text](controls/properties-core.md)** van dit besturingselement in te stellen. Stel deze eigenschap in door rechtstreeks in het besturingselement te typen of een expressie in de formulebalk te typen.

* Als u rechtstreeks in het besturingselement typt, wordt exact weergegeven wat u typt.
* Als u een expressie in de formulebalk typt, toont het besturingselement het resultaat van de expressie.

Hieronder ziet u een aantal voorbeelden:

1. Voeg een besturingselement **[Label](controls/control-text-box.md)** met de naam **ShowText** toe en stel de eigenschap **[Text](controls/properties-core.md)** in op deze formule:
   <br>**Now()**
   
    Als uw computer is ingesteld op de landinstelling "en-us", worden de huidige datum en tijd weergegeven volgens de volgende notatie:  <br>*mm/dd/jjjj uu:mm AM/PM*
   
    Als uw computer is ingesteld op een landinstelling als "fr-fr", worden de huidige datum en tijd weergegeven volgens de volgende notatie:  <br>*dd/mm/jjjj uu:mm AM/PM*
2. Stel de eigenschap **[Text](controls/properties-core.md)** van **ShowText** in op deze formule:
   <br>**DateDiff(Today(), DateValue("01/01/2020"))**
   
    ![Aantal dagen tussen vandaag en 1 jan. 2020](./media/show-text-dates-times/date-diff-text.png)
   
    Het besturingselement toont het aantal dagen tussen vandaag en 1 januari 2020, met behulp van deze functies:
   
   * **DateDiff**, welke het aantal dagen, kwartalen of jaren tussen twee datums berekent.
   * **Today**, welke de huidige dag omzet naar een waarde.
   * **DateValue**, welke een letterlijke tekenreeks, zoals wordt weergegeven tussen dubbele aanhalingstekens, converteert naar een waarde waarmee berekeningen kunnen worden uitgevoerd.
3. Voeg een besturingselement voor **[Tekstinvoer](controls/control-text-input.md)** toe met de naam **BirthDate** en plaats deze onder **ShowText**.
4. Voor **BirthDate** voert u de maand en dag van uw geboortedatum in (bijvoorbeeld **05/18**).
5. Stel de eigenschap **[Text](controls/properties-core.md)** van **ShowText** in op deze formule:
   <br>**DateDiff(Today(), DateValue(BirthDate.Text))**
   
    ![Aantal dagen tussen vandaag en uw verjaardag](./media/show-text-dates-times/birth-diff.png)
   
    **ShowText** geeft het aantal dagen weer tussen vandaag en de datum die u invoert als **BirthDate**. Als uw verjaardag dit jaar al geweest is, toont **ShowText** een negatieve waarde.

## <a name="format-dates-and-times-by-using-datetimevalue"></a>Indeling datums en tijden instellen via DateTimeValue
Converteer datums en tijden van tekenreeksen naar waarden, die u op verschillende manieren kunt indelen en in berekeningen kunt gebruiken. Geef de indeling op met behulp van ingebouwde of aangepaste opties.

> [!NOTE]
> De functies **[DateTimeValue](functions/function-datevalue-timevalue.md)** en **[DateValue](functions/function-datevalue-timevalue.md)** kunnen datums in een van de volgende indelingen converteren naar waarden:  
> 
> * MM/DD/JJJJ  
> * DD/MM/JJJJ  
> * DD mnd JJJJ  
> * Maand DD, JJJJ  
> 
> 

1. Voeg een besturingselement voor **[Tekstinvoer](controls/control-text-input.md)** toe met de naam **ArrivalDateTime** en voer een datum en tijd in volgens de volgende notatie:
   <br>**5/10/85 6:15 AM**
2. Voeg een besturingselement **[Label](controls/control-text-box.md)** met de naam **ShowDate** toe en stel de eigenschap **[Text](controls/properties-core.md)** in op deze formule:
   <br>**DateTimeValue(ArrivalDateTime.Text)**
   
    ![Een datum/tijd converteren van tekst naar een waarde](./media/show-text-dates-times/date-value.png)
   
    **ShowDate** bevat dezelfde informatie die u hebt getypt, maar de tekst is geconverteerd naar een waarde en de indeling is gewijzigd. Nu wordt het jaartal bijvoorbeeld weergegeven met vier cijfers, in plaats van twee.
3. Stel de eigenschap **[Text](controls/properties-core.md)** van **ShowDate** in op deze formule:
   <br>**DateTimeValue(ArrivalDateTime.Text, "fr")**
   
    ![Een datum/tijd-waarde weergeven in een Franse notatie](./media/show-text-dates-times/date-value-fr.png)
   
    Met **ShowDate** wordt de dag vóór de maand getoond, zoals een Franse gebruiker verwacht.
   
   > [!TIP]
   > Voor een lijst met andere landinstellingen in Intellisense verwijdert u het aanhalingsteken sluiten en de code **fr** uit de formule, maar laat u het aanhalingsteken openen staan:
   > 
   > ![Een lijst met landinstellingen weergeven](./media/show-text-dates-times/locale-list.png)
   > 
   > 
4. Stel de eigenschap **[Text](controls/properties-core.md)** van **ShowDate** in op deze formule, om een van de verschillende ingebouwde notaties te gebruiken:
   <br>**Text(DateTimeValue(ArrivalDateTime.Text), DateTimeFormat.LongDateTime)**
   
    ![Een datum/tijd-waarde weergeven in een Franse notatie](./media/show-text-dates-times/long-date-time.png)
   
    **ShowDate** toont de dag van de week, de datum en de tijd.
   
   > [!TIP]
   > De parameter **DateTimeFormat** biedt ondersteuning voor diverse ingebouwde notaties. Als u die lijst wilt weergeven, verwijdert u **LongDateTime** uit de formule.
   > 
   > 
5. Om een aangepaste notatie te gebruiken, stelt u de eigenschap **[Text](controls/properties-core.md)** van **ShowDate** in op deze formule:
   <br>**Text(DateTimeValue(ArrivalDateTime.Text), "mm/dd/yyyy hh:mm:ss.fff AM/PM")**
   
    ![Een datum/tijd-waarde weergeven in een Franse notatie](./media/show-text-dates-times/format-milliseconds.png)
   
    **ShowDate** toont nu de datum/tijd-waarde in de indeling die u hebt opgegeven, inclusief milliseconden.
   
   > [!TIP]
   > Als u de tijd wilt afronden naar de dichtstbijzijnde tiende of honderdste van een seconde, voert u in de formule **hh:mm:ss.f** of **hh:mm:ss.ff** in.
   > 
   > 

## <a name="format-a-date-by-using-datevalue"></a>Een datum opmaken met behulp van DateValue
1. Voeg een besturingselement voor **[Tekstinvoer](controls/control-text-input.md)** toe met de naam **ArrivalDate** en typ hier een datum in (bijvoorbeeld **5/10/85**).
2. Voeg een besturingselement **[Label](controls/control-text-box.md)** met de naam **FormatDate** toe en stel de eigenschap **[Text](controls/properties-core.md)** in op deze formule:
   <br>**DateValue(ArrivalDate.Text)**
   
    **FormatDate** toont de datum die u hebt getypt, alleen wordt het jaartal met vier cijfers weergegeven.
3. Stel de eigenschap **[Text](controls/properties-core.md)** van **FormatDate** in op deze formule:
   <br>**DateValue(ArrivalDate.Text, "fr")**
   
    Met **FormatDate** wordt de dag vóór de maand getoond, zoals een Franse gebruiker verwacht.
4. Stel de eigenschap **[Text](controls/properties-core.md)** van **FormatDate** in op deze formule, om een van de verschillende ingebouwde notaties te gebruiken:
   <br>**Text(DateValue(ArrivalDate.Text), DateTimeFormat.LongDate)**
   
    **FormatDate** toont de dag van de week, de maand, de dag en het jaar.
5. Om een aangepaste notatie te gebruiken, stelt u de eigenschap **[Text](controls/properties-core.md)** van **FormatDate** in op deze formule:
   <br>**Text(DateValue(ArrivalDate.Text), "yy/mm/dd")**
   
    **FormatDate** toont de datum volgens de notatie die u hebt opgegeven.

## <a name="format-a-time-using-datetimevalue"></a>Een tijdsnotatie instellen met DateTimeValue
1. Voeg een besturingselement voor **[Tekstinvoer](controls/control-text-input.md)** toe met de naam **ArrivalTime** en voer daar vervolgens **6:15 AM** in.
2. Voeg een besturingselement **[Label](controls/control-text-box.md)** toe met de naam **ShowTime**.
3. Stel de eigenschap **[Text](controls/properties-core.md)** van **ShowTime** in op deze formule, om een van de verschillende ingebouwde notaties te gebruiken:
   <br>**Text(DateTimeValue(ArrivalTime.Text), DateTimeFormat.LongTime)**
   
    **ShowTime** toont de tijd die u hebt opgegeven, inclusief seconden.
4. Om een aangepaste notatie te gebruiken, stelt u de eigenschap **[Text](controls/properties-core.md)** van **ShowTime** in op deze formule:
   <br>**Text(DateTimeValue(ArrivalTime.Text), "hh:mm:ss.fff AM/PM")**
   
    **ShowTime** toont de tijd die u hebt opgegeven, inclusief seconden en milliseconden.
   
   > [!TIP]
   > Als u de tijd wilt afronden naar de dichtstbijzijnde tiende of honderdste van een seconde, voert u in de formule **hh:mm:ss.f** of **hh:mm:ss.ff** in.
   > 
   > 

## <a name="show-the-time-between-dates"></a>De tijd tussen datums weergeven
1. Voeg twee besturingselementen voor **[Tekstinvoer](controls/control-text-input.md)** in met de namen **Start** en **End**.
2. Voer **1/4/2015** in bij **Start** en **1/1/2016** bij **End**.
3. Voeg een besturingselement **[Label](controls/control-text-box.md)** met de naam **DateDiff** toe en stel de eigenschap **[Text](controls/properties-core.md)** in op deze formule:
   <br>**DateDiff(DateValue(Start.Text), DateValue(End.Text))**
   
    ![Vergelijk twee datums](./media/show-text-dates-times/date-diff.png)
   
    **DateDiff** geeft **275** weer, het aantal dagen tussen 1 april 2015 en 1 januari 2016.
4. Stel de eigenschap **[Text](controls/properties-core.md)** van **DateDiff** in op deze formule:  <br>**DateDiff(DateValue(Start.Text), DateValue(End.Text), Months)**
   
    **DateDiff** geeft **9** weer, het aantal maanden tussen 1 april 2015 en 1 januari 2016. Vervang **Months** door **Quarters** of **Years** om de tijd in die eenheden te tonen.

## <a name="identify-a-date-before-or-after-another-date"></a>Een datum vóór of na een andere datum bepalen
1. Voeg een besturingselement voor **[Tekstinvoer](controls/control-text-input.md)** toe met de naam **Start** en voer daar **5/10/1985** in.
2. Voeg een besturingselement **[Label](controls/control-text-box.md)** met de naam **DateAdd** toe en stel de eigenschap **[Text](controls/properties-core.md)** in op deze formule:
   <br>**DateAdd(DateValue(Start.Text), 3)**
   
    ![Drie dagen toevoegen](./media/show-text-dates-times/date-add.png)
   
    **DateAdd** geeft **5/13/1985** weer, dat is drie dagen na de datum die is ingevuld voor **Start**.
3. Stel de eigenschap **[Text](controls/properties-core.md)** van **DateAdd** in op deze formule:
   <br>**DateAdd(DateValue(Start.Text), -3)**
   
    ![Drie dagen aftrekken](./media/show-text-dates-times/date-subtract.png)
   
    **DateAdd** geeft **5/7/1985** weer, dat is drie dagen voor de datum die is ingevuld voor **Start**.
4. Stel de eigenschap **[Text](controls/properties-core.md)** van **DateAdd** in op deze formule:
   <br>**DateAdd(DateValue(Start.Text), 3, Months)**
   
    ![Drie maanden toevoegen](./media/show-text-dates-times/date-add-months.png)
   
    Het label geeft **8/10/1985** weer, dat is drie maanden na de datum die is ingevuld voor **Start**. Vervang **Months** door **Quarters** of **Years** om een datum te bepalen die het opgegeven aantal kwartalen of jaren vóór of na de datum ligt die is opgegeven voor **Start**.

## <a name="calculate-dates-based-on-years-months-and-days"></a>Datums berekenen op basis van jaren, maanden en dagen
1. Voeg driemaal het besturingselement **[Vervolgkeuzelijst](controls/control-drop-down.md)** toe, met de namen **Jaar**, **Maand** en **Dag**.
2. Stel de eigenschap **[Items](controls/properties-core.md)** van **Jaar** in op deze formule:
   <br>**Table({Year:"2014"}, {Year:"2015"}, {Year:"2016"})**
3. Stel de eigenschap **[Items](controls/properties-core.md)** van **Maand** in op deze formule:
   <br>**Table({Month:"1"}, {Month:"2"}, {Month:"3"}, {Month:"4"}, {Month:"5"}, {Month:"6"}, {Month:"7"}, {Month:"8"}, {Month:"9"}, {Month:"10"}, {Month:"11"}, {Month:"12"})**
4. Stel de eigenschap **[Items](controls/properties-core.md)** van **Dag** in op deze formule:
   <br>**Table({Day:"1"}, {Day:"2"}, {Day:"3"}, {Day:"4"}, {Day:"5"}, {Day:"6"}, {Day:"7"}, {Day:"8"}, {Day:"9"}, {Day:"10"}, {Day:"11"}, {Day:"12"}, {Day:"13"}, {Day:"14"}, {Day:"15"}, {Day:"16"}, {Day:"17"}, {Day:"18"}, {Day:"19"}, {Day:"20"}, {Day:"21"}, {Day:"22"}, {Day:"23"}, {Day:"24"}, {Day:"25"}, {Day:"26"}, {Day:"27"}, {Day:"28"}, {Day:"29"}, {Day:"30"}, {Day:"31"})**
5. Voeg een besturingselement van het type **[Label](controls/control-text-box.md)** toe en stel de eigenschap **[Text](controls/properties-core.md)** in op deze formule:
   <br>**Text(Date(Value(Year.Selected.Value), Value(Month.Selected.Value), Value(Day.Selected.Value)), DateTimeFormat.LongDate)**
   
    Standaard wordt **Woensdag 1 januari 2014** weergegeven. Selecteer verschillende waarden in de **[Vervolgkeuzelijst](controls/control-drop-down.md)**-besturingselementen om de datum in het besturingselement **[Label](controls/control-text-box.md)** te wijzigen.

U dient wellicht gegevens die u niet verwachtte te converteren. Als u het besturingselement **[Tekstinvoer](controls/control-text-input.md)** gebruikt, in plaats van het besturingselement **[vervolgkeuzelijst](controls/control-drop-down.md)** kan een gebruiker een onjuiste datum invoeren, zoals 45 mei. De functie **[Date](functions/function-date-time.md)** verwerkt afwijkende gegevens als volgt:

* Als de waarde voor een jaar tussen de 0 t/m 1899 ligt, voegt de functie die waarde toe aan 1900 om het jaartal te berekenen.
* Als de waarde voor een jaar tussen de 1900 t/m 9999 ligt, gebruikt de functie die waarde als het jaartal.
* Als de waarde voor een jaar kleiner is dan 0 of 10000 of groter is, geeft de functie een foutmelding.
* Als de waarde voor een maand groter is dan 12, telt de functie dat aantal maanden op bij de eerste maand van het opgegeven jaar.
* Als de waarde voor maanden kleiner is dan 1, trekt de functie dat aantal maanden plus 1 af van de eerste maand van het opgegeven jaar.
* Als de waarde voor een dag groter is dan het aantal dagen in de opgegeven maand, voegt de functie de hoeveelheid dagen toe aan de eerste dag van de maand en retourneert deze de overeenkomstige datum van de volgende maand.
* Als de waarde voor dagen kleiner is dan 1, trekt de functie dat aantal dagen plus 1 af van de eerste dag van de opgegeven maand.

## <a name="calculate-times-based-on-hours-minutes-and-seconds"></a>Berekenen op basis van uren, minuten en seconden
1. Voeg twee **Vervolgkeuzelijsten** toe met de namen **Uur** en **Minuut**.
2. Stel de eigenschap **[Items](controls/properties-core.md)** van **Uur** in op deze formule:
   <br>**Table({Hour:"9"}, {Hour:"10"}, {Hour:"11"}, {Hour:"12"}, {Hour:"13"}, {Hour:"14"}, {Hour:"15"}, {Hour:"16"}, {Hour:"17"})**
3. Stel de eigenschap **[Items](controls/properties-core.md)** van **Minuut** in op deze formule:
   <br>**Table({Minute:"0"}, {Minute:"15"}, {Minute:"30"}, {Minute:"45"})**
4. Voeg een besturingselement van het type **[Label](controls/control-text-box.md)** toe en stel de eigenschap **[Text](controls/properties-core.md)** in op deze formule:  
   <br>**Text(Time(Value(Hour.Selected.Value), Value(Minute.Selected.Value), 0), DateTimeFormat.ShortTime)**
5. Selecteer **15** voor **Uur** en **45** voor **Minuut**.
   
    In het besturingselement **[Label](controls/control-text-box.md)** wordt **15:45 uur** weergegeven.
   
    U kunt items toevoegen aan **Uur** en **Minuut**, zodat gebruikers uit een groter aantal uren en een nauwkeuriger aantal minuten kunnen kiezen. U kunt ook een derde **[Vervolgkeuzelijst](controls/control-drop-down.md)** toevoegen, zodat gebruikers seconden kunnen opgeven. Als u een derde lijst wilt toevoegen, stelt u de eigenschap **[Text](controls/properties-core.md)** van het besturingselement **[Label](controls/control-text-box.md)** in op de volgende expressie:<br>**Text(Time(Value(Hour.Selected.Value), Value(Minute.Selected.Value), Value(Second.Selected.Value)), DateTimeFormat.LongTime)**

