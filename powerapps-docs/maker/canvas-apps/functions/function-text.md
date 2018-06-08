---
title: De functie Tekst | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Tekst in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2016
ms.author: gregli
ms.openlocfilehash: a63a972e7af3c821d2441519c2a887bbe110faac
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31838942"
---
# <a name="text-function-in-powerapps"></a>De functie Tekst in PowerApps
Maakt een numerieke of datum/tijd-waarde op voor weergave als een teksttekenreeks.

## <a name="description"></a>Beschrijving
De functie **Tekst** maakt een getal of een datum/tijd-waarde op op basis van een van deze typen argumenten:

* Een vooraf gedefinieerde datum/tijd-indeling, die u opgeeft met behulp van de opsomming **DatumTijdNotatie**.  Voor datums en tijden heeft deze methode de voorkeur omdat het resultaat automatisch wordt aangepast aan de taal en locatie van de gebruiker.
* Een aangepaste notatie, een tekenreeks met tijdelijke aanduidingen die beschrijven hoe u het getal of de waarde voor datum/tijd kunt opmaken. Tijdelijke aanduidingen definiëren hoeveel getallen moeten worden weergegeven, of groeperingsscheidingstekens moeten worden gebruikt en hoe de naam van een maand moet worden weergegeven. PowerApps ondersteunt een subset van de tijdelijke aanduidingen die door Microsoft Excel worden ondersteund.

Zie [working with dates and times (werken met datums en tijden)](../show-text-dates-times.md) voor meer informatie.

### <a name="predefined-datetime-formats"></a> Vooraf gedefinieerde datum-/tijdnotaties
| Vooraf gedefinieerde notatie | Beschrijving |
| --- | --- |
| **DatumTijdNotatie.LangeDatum** |Jaar, maand, dag van de maand en dag van de week, voluit geschreven. De namen van de maand en dag van de week worden niet afgekort. |
| **DatumTijdNotatie.LangeDatumTijd** |Jaar, maand, dag van de maand en dag van de week, voluit geschreven, plus aanduiding van uur (12-uurs notatie), minuten, seconden en AM/PM-aanduiding. De namen van de maand en dag van de week worden niet afgekort. |
| **DatumTijdNotatie.LangeDatumTijd24** |Jaar, maand, dag van de maand en dag van de week, voluit geschreven, plus aanduiding van uur (24-uurs notatie), minuten en seconden. De namen van de maand en dag van de week worden niet afgekort. |
| **DatumTijdNotatie.LangeTijd** |Uur (12-uurs notatie), minuten, seconden en AM/PM-aanduiding. Hetzelfde als KorteTijd. |
| **DatumTijdNotatie.LangeTijd24** |Uur (24-uurs notatie), minuten en seconden. Hetzelfde als KorteTijd24. |
| **DatumTijdNotatie.KorteDatum** |Jaar in vier cijfers met maand in twee cijfers en dag van de maand. |
| **DatumTijdNotatie.KorteDatumTijd** |Jaar in vier cijfers met maand in twee cijfers en dag van de maand, plus uur (12-uurs notatie), minuten, seconden en AM/PM-aanduiding. |
| **DatumTijdNotatie.KorteDatumTijd24** |Jaar in vier cijfers met maand in twee cijfers en dag van de maand, plus uur (24-uurs notatie), minuten en seconden. |
| **DatumTijdNotatie.KorteTijd** |Uur (12-uurs notatie), minuten, seconden en AM/PM-aanduiding.  Hetzelfde als LangeTijd. |
| **DatumTijdNotatie.KorteTijd24** |Uur (24-uurs notatie), minuten en seconden.  Hetzelfde als LangeTijd24. |
| **DatumTijdNotatie.UTC** |De waarde voor datum/tijd wordt geconverteerd naar UTC op basis van de tijdzone van de huidige gebruiker en ingedeeld volgens de ISO 8601-norm. |

### <a name="number-placeholders"></a>Tijdelijke aanduidingen voor getallen
| Tijdelijke aanduiding | Beschrijving |
| --- | --- |
| **0** (*nul*) |Geeft extra nullen weer als een getal minder cijfers heeft dan er nullen in de notatie zijn. Gebruik bijvoorbeeld de indeling **#,00** als u **8,9** wilt weergeven als **8,90**. |
| **#** |Volgt dezelfde regels als de **0** (nul). **Tekst** zal echter geen extra nullen retourneren als het getal links of rechts van het decimaalteken minder cijfers heeft dan er #-symbolen zijn in de notatie. Bijvoorbeeld **8,9** wordt weergegeven als de aangepaste notatie **#,##** is en het op te maken getal **8,9** is. |
| **,** (*komma*) |De decimaalkomma wordt weergegeven in een getal.  Is afhankelijk van de taal van de aangepaste notatie. Zie [global apps (wereldwijde apps)](#global-apps) voor meer informatie. |
| **.** (*punt*) |Geeft het groeperingsscheidingsteken in een getal weer. Wordt vaak gebruikt voor duizendtallen. **Tekst** scheidt groepen door punten als de notatie een punt tussen hekjes (**#**) of tussen nullen bevat.  Is afhankelijk van de taal van de aangepaste notatie. Zie [global apps (wereldwijde apps)](#global-apps) voor meer informatie. |

Als in een getal rechts van het decimaalteken meer cijfers voorkomen dan er tijdelijke aanduidingen in de notatie zijn, wordt het getal afgerond naar net zoveel decimaaltekens als het aantal tijdelijke aanduidingen. Als er links van het decimaalteken meer cijfers voorkomen dan er tijdelijke aanduidingen zijn, worden de extra cijfers weergegeven. Als in de notatie alleen hekjes (#) links van het decimaalteken voorkomen, beginnen getallen die kleiner zijn dan 1 met een decimaalteken (bijvoorbeeld **,47**).

### <a name="date-and-time-placeholders"></a>Tijdelijke aanduidingen voor datum en tijd
| Tijdelijke aanduiding | Beschrijving |
| --- | --- |
| **m** |De maand wordt weergegeven als een getal zonder voorloopnul. |
| **mm** |De maand wordt weergegeven als een getal met een voorloopnul wanneer dat nodig is. |
| **mmm** |De maand wordt weergegeven als een afkorting (**jan** tot **dec**). |
| **mmmm** |De maand wordt weergegeven als een volledige naam (**januari** tot **december**). |
| **d** |Geeft de dag weer als een getal zonder voorloopnul. |
| **dd** |Geeft de dag weer als een getal zonder voorloopnul wanneer dat nodig is. |
| **ddd** |Geeft de dag weer als een afkorting (**zo** tot **za**). |
| **dddd** |Geeft de dag weer als een volledige naam (**zondag** tot **zaterdag**). |
| **jj** |Geeft het jaar weer als een getal van twee cijfers. |
| **jjjj** |Geeft het jaar weer als een getal van vier cijfers. |
| **h** |Geeft het uur weer als een getal zonder voorloopnul. |
| **hh** |Geeft het uur weer als een getal met een voorloopnul wanneer dat nodig is. Als de notatie **AM** of **PM** bevat, wordt het uur weergegeven op basis van de 12-uurs notatie. Anders wordt het weergegeven uur gebaseerd op de 24-uurs notatie. |
| **m** |Geeft de minuut weer als een getal zonder voorloopnul.  > [!NOTE]
> De code **m** of **mm** moet direct na de code **h** of **hh** worden weergegeven of direct voor de code **ss**. Anders retourneert **Tekst** de maand in plaats van minuten. |
| **mm** |Geeft de minuut weer als een getal met een voorloopnul wanneer dat nodig is. > [!NOTE]
> De tijdelijke aanduiding **m** of **mm** moet direct na de tijdelijke aanduiding **h** of **hh** verschijnen of direct voor de tijdelijke aanduiding **ss**. Anders retourneert **Tekst** de maand in plaats van minuten. |
| **s** |Geeft de seconde weer als een getal zonder voorloopnul. |
| **ss** |Geeft de seconde weer als een getal met een voorloopnul wanneer dat nodig is. |
| **f** |Geeft de fracties van seconden weer. |
| **AM/PM**, **am/pm**, **A/P**, **a/p** |Geeft het uur weer op basis van een 12-uurs notatie. **Tekst** retourneert "AM", "am", "A" of "a" voor tijden van middernacht tot het middaguur en "PM", "pm", "P" of "p" voor tijden van het middaguur tot middernacht |

### <a name="literal-placeholders"></a>Letterlijke tijdelijke aanduidingen
U kunt al deze tekens in de tekenreeks voor uw notatie opnemen.  Ze zullen als zodanig worden weergegeven in het resultaat van **Tekst**. Andere tekens zijn gereserveerd voor toekomstige tijdelijke aanduidingen. Die tekens mag u bijgevolg niet gebruiken.

| Teken | Beschrijving |
| --- | --- |
| Elk valutasymbool |Euroteken, dollarteken, centteken, enzovoort. |
| **+** |Plusteken |
| **(** |Haakje openen |
| **:** |Dubbele punt |
| **^** |Accent circonflexe (caret-teken) |
| **'** |Apostrof |
| **{** |Accolade links |
| **<** |Kleiner-dan-teken |
| **=** |Gelijkteken |
| **-** |Minteken |
| **/** |Schuine streep |
| **)** |Haakje sluiten |
| **&** |En-teken |
| **~** |Tilde |
| **}** |Accolade rechts |
| **>** |Groter-dan-teken |
| &nbsp; |Spatie |

## <a name="global-apps"></a>Wereldwijde apps
De functie **Tekst** is locatiebewust.  Voor een groot aantal talen kan deze functie de juiste notatie van datums, tijden, valuta's en getallen gebruiken.  Hiervoor heeft de functie twee soorten informatie nodig:

* **De taal van de aangepaste notatie:** voor auteurs, hoe moet een aangepaste notatie worden geïnterpreteerd?  De scheidingstekens (**,** en **.**) hebben in verschillende talen een andere betekenis.  Dit kan worden opgelost met een speciale tijdelijke aanduiding die een taalcode bevat.  Of zelfs nog gemakkelijker: de [vooraf gedefinieerde notaties voor datum/tijd](#predefined-datetime-formats) zijn taalneutraal.
* **De taal van het resultaat:** voor gebruikers, welke taal moet worden gebruikt in het resultaat van de functie?  Namen voor maanden en werkdagen moeten in de juiste taal zijn gesteld voor de gebruiker van de app.  Dit kan worden opgelost met een optionele derde argument voor de functie **Tekst**. 

Voor beide mogelijkheden wordt de taal opgegeven met een [taalcode](function-language.md#language-tags).  Voor een overzicht van de ondersteunde talen typt u **Tekst( 1234, "", )** in de formulebalk of de geavanceerde weergave en bladert u door de lijst met landinstellingen die voor het derde argument worden voorgesteld.

#### <a name="custom-format-language-placeholder"></a>Tijdelijke aanduiding voor taal in aangepaste notatie
Geef de taal als volgt in de aangepaste notatie op:

| Tijdelijke aanduiding | Beschrijving |
| --- | --- |
| **[$-*Taalcode*]** |*Taalcode* is een taalcode die door de functie **Taal** wordt geretourneerd.  Deze code kan de vorm hebben van alleen de taal, zoals **[$en]** voor Engels, maar ook de regio kan erin worden opgenomen, zoals **[$-en-GB]** als u bijvoorbeeld Brits-Engels wilt opgeven. |

De tijdelijke aanduiding voor de taal kan overal in de aangepaste notatie voorkomen, maar wel slechts één keer.

Als u bij het schrijven van een formule geen tijdelijke aanduiding voor een taal opgeeft en de notatietekenreeks is globaal gezien niet eenduidig, voegt het bewerkingsprogramma automatisch de taalcode van uw huidige taal toe.  

Er wordt bijvoorbeeld uitgegaan van **[$-en-US]** als deze tijdelijke aanduiding niet aanwezig is wanneer uw app wordt uitgevoerd. 

> [!NOTE]
> In een toekomstige versie zal de syntaxis van deze tijdelijke aanduiding mogelijk worden gewijzigd om verwarring te voorkomen met een vergelijkbare, maar andere, tijdelijke aanduiding die door Excel wordt ondersteund.

#### <a name="result-language-tag"></a>Taalcode resultaat
In het resultaat van **Tekst** verschijnen vertaalde tekenreeksen voor maand, weekdag, AM/PM-aanwijzingen, evenals de juiste groeperings- en decimaalscheidingstekens.

Standaard gebruikt **Tekst** de taal van de gebruiker die de app uitvoert.  De functie **Taal** retourneert de taalcode voor de huidige gebruiker.  U kunt deze standaardwaarde onderdrukken door een taalcode op te geven voor het optionele derde argument voor **Tekst**.

## <a name="syntax"></a>Syntaxis
**Tekst**( *Getal*, *DatumTijdNotatieOpsomming* [, *ResultaatTaalcode* ] )

* *Getal* is vereist. Het getal of de datum/tijd-waarde die moet worden opgemaakt.
* *DatumTijdNotatie* - vereist.  Een lid van de opsomming **DatumTijdNotatie**.
* *ResultaatTaalcode* - optioneel.  De te gebruiken taalcode voor de resultaattekst.  Standaard wordt de taal van de huidige gebruiker gebruikt.

**Tekst**( *Getal*, *AangepasteNotatie* [, *ResultaatTaalcode* ] )

* *Getal* is vereist. Het getal of de datum/tijd-waarde die moet worden opgemaakt.
* *AangepasteNotatie* - vereist. Een of meer tijdelijke aanduidingen tussen dubbele aanhalingstekens.
* *ResultaatTaalcode* - optioneel.  De te gebruiken taalcode voor de resultaattekst.  Standaard wordt de taal van de huidige gebruiker gebruikt.

## <a name="examples"></a>Voorbeelden
De gebruiker die deze formules uitvoert, bevindt zich in de Verenigde Staten en Engels is geselecteerd als taal.  De functie **Taal** retourneert "en-US".

### <a name="number"></a>Getal
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Tekst(&nbsp;1234,59,&nbsp;"####,#"&nbsp;)** |Maakt het getal op met één decimaalpositie. |"1234,6" |
| **Tekst(&nbsp;8,9,&nbsp;"#,000"&nbsp;)** |Vult het decimaalgedeelte van het getal op met volgnullen, indien nodig. |"8,900" |
| **Tekst(&nbsp;0,631,&nbsp;"0,#"&nbsp;)** |Vult het hele gedeelte van het getal op met volgnullen, indien nodig. |"0,6" |
| **Tekst(&nbsp;12,&nbsp;"#,0#"&nbsp;)**<br>**Tekst(&nbsp;1234,568,&nbsp;"#,0#"&nbsp;)** |Vult het decimale gedeelte van het getal op met nullen voor één decimaalpositie en voegt een tweede decimaalpositie toe, als deze is opgegeven. |"12,0"<br>"1234,57" |
| **Tekst(&nbsp;12000,&nbsp;"€ #,###"&nbsp;)**<br>**Tekst(&nbsp;1200000,&nbsp;"€&nbsp;#.###"&nbsp;)** |Plaatst om de drie cijfers een scheidingsteken voor duizendtallen en voegt een valutasymbool toe. |"€&nbsp;12.000"<br>"€&nbsp;1.200.000" |

### <a name="datetime"></a>Datum/tijd
* Om **2:37:47 PM** op **maandag 23 november 2015**
* Verenigde Staten, Pacific Time Zone (UTC-8)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Tekst( Nu(), DatumTijdNotatie.LangeDatum )** |Wordt opgemaakt als een tekenreeks met lange datum, in de taal en met de landinstellingen van de huidige gebruiker. |"Maandag 23 november 2015" |
| **Tekst( Nu(), DatumTijdNotatie.LangeDatumTijd )** |Wordt opgemaakt als een tekenreeks met lange datum en tijd in de taal en landinstellingen van de huidige gebruiker, met een 12-uurs notatie. |"Maandag 23 november 2015 2:37:47 PM" |
| **Tekst( Nu(), DatumTijdNotatie.LangeTijd24 )** |Wordt opgemaakt als een tekenreeks met lange tijd, met een 24-uurs notatie. |"14:37:47" |
| **Tekst( Nu(), DatumTijdNotatie.KorteDatum )** |Wordt opgemaakt als een tekenreeks met korte datum, in de taal en met de landinstellingen van de huidige gebruiker. |"23-11-2015" |
| **Tekst( Nu(), "d-mmm-jj" )** |Wordt opgemaakt met tekens als tijdelijke aanduiding: <ul><li>**d** voor de dag van de maand, met één cijfer of twee cijfers<li>**-** als een letterlijk teken, dat naar het resultaat wordt gekopieerd<li>**mmm** voor een maandafkorting van drie letters<li>**-** als nog een letterlijk teken dat naar het resultaat wordt gekopieerd<li>**jj** voor een jaarafkorting van twee cijfers</ul> |"23-nov-15" |

### <a name="global-apps"></a>Wereldwijde apps
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Tekst( 1234567,89, "[$-en-US]$ #.###" )** |Interpreteert **.** als een groeperingsscheidingsteken dat om de drie tekens moet worden geplaatst en **$** als het valutasymbool. Aangezien er geen decimalen moeten worden weergegeven, wordt de waarde naar boven afgerond op het eerstvolgende hogere gehele getal. In dit geval is **[$-en-US]** optioneel, omdat dit de standaardinstelling is. |"$ 1.234.568" |
| **Tekst( 1234567,89, "[$-es-ES]&euro; #,###" )** |Interpreteert **,** als decimaalteken en **&euro;** als valutasymbool.  Omdat **[$-fr-FR]** alleen bepaalt hoe de notatietekenreeks wordt geïnterpreteerd, wordt in het resultaat gebruikgemaakt van de tekens uit de standaardtaalcode "en-US": **.** (punt) als decimaalteken en **$** als valutasymbool. |"$ 1234567.89" |
| **Tekst( 1234567,89, "[$-es-ES]&euro; #,###", "es-ES" )** |Interpreteert **,** als decimaalteken.  De taalcode van het resultaat is ingesteld op "fr-FR" waardoor de **,** (komma) wordt gebruikt als decimaalteken en **&euro;** als valutasymbool. |"&euro; 1234567,89" |
| **Tekst( Datum(2016,1,31), "dddd mmmm d" )** |Retourneert de dag van de week, maand en dag van de maand in de taal van de huidige gebruiker. Omdat geen van de tijdelijke aanduidingen taalafhankelijk is, is er geen taalcode voor de opmaak van tekst nodig. |"Zaterdag 31 januari" |
| **Tekst( Datum(2016,1,31), "dddd mmmm d", "es-ES" )** |Retourneert de dag van de week, maand en dag van de maand in de taal "es-ES". |"domingo enero 31" |

