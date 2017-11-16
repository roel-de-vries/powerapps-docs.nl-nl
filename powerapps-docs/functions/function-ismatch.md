---
title: De functie IsMatch | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis, voor de functie IsMatch in PowerApps
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
ms.date: 02/05/2017
ms.author: gregli
ms.openlocfilehash: b15a394db060617aeae8324094a70aa8cadf6755
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="ismatch-function-in-powerapps"></a>De functie IsMatch in PowerApps
Test of een teksttekenreeks overeenkomt met een patroon.

## <a name="description"></a>Beschrijving
De functie **IsMatch** test of een teksttekenreeks overeenkomt met een patroon dat kan bestaan uit gewone tekens, vooraf gedefinieerde patronen of een [reguliere expressie](#regular-expressions).  

Gebruik **IsMatch** om te valideren wat een gebruiker in een besturingselement voor **[tekstinvoer](../controls/control-text-input.md)** heeft getypt. U kunt bijvoorbeeld controleren of de gebruiker een geldig e-mailadres heeft ingevoerd voordat het resultaat in uw gegevensbron wordt opgeslagen. Voeg andere besturingselementen toe die de gebruiker vragen om de gegevens te corrigeren als de invoer niet met uw criteria overeenkomt.

**IsMatch** voert standaard een hoofdlettergevoelige overeenkomst voor de hele teksttekenreeks uit. U kunt dit gedrag wijzigen door een of meer [**MatchOptions**](#match-options) op te geven.

**IsMatch** retourneert *true* als de teksttekenreeks overeenkomt met het patroon, of *false* als dat niet het geval is.

## <a name="patterns"></a>Patronen
De sleutel voor het gebruik van **IsMatch** ligt in de beschrijving van het patroon voor de overeenkomst. U beschrijft het patroon in een teksttekenreeks als een combinatie van:

* Gewone tekens, zoals **"abc"** of **"123"**.
* Vooraf gedefinieerde patronen, zoals **Letter**, **MultipleDigits** of **E-mail**. (De enum **Match** definieert deze patronen.)
* Codes van reguliere expressies, zoals **"\d+\s+\d+"** of **"[a-z]+"**.

Combineer deze elementen door de [samenvoegingsoperator **&** voor tekenreeksen](operators.md) te gebruiken. **"abc" & Digit & "\s+"** is bijvoorbeeld een geldig patroon dat de tekens "a", "b" en "c", gevolgd door een cijfer van 0 tot 9, gevolgd door minimaal een spatie, zoekt.

### <a name="ordinary-characters"></a>Gewone tekens
De eenvoudigste patroon is een opeenvolging van gewone tekens die precies overeen moeten komen.

De tekenreeks "Hallo" komt bijvoorbeeld exact overeen met het patroon **"Hallo"**. Niet meer en niet minder. De tekenreeks "hallo!" komt niet met het patroon overeen vanwege het uitroepteken aan het einde. Ook komt de kleine letter "h" niet overeen. (Zie [MatchOptions](#match-options) voor manieren om dit gedrag te wijzigen.)

In de patroontaal zijn bepaalde tekens voor speciale doeleinden gereserveerd. Als u deze tekens wilt gebruiken, moet u ofwel een **\\** (backslash) voor het teken plaatsen om aan te geven dat het teken letterlijk moet worden genomen, ofwel een van de vooraf gedefinieerde patronen gebruiken. Deze tabel bevat de speciale tekens:

| Speciaal teken | Beschrijving |
| --- | --- |
| **,** |punt |
| **?** |vraagteken |
| **&#42;** |sterretje |
| **\+** |plus |
| **( )** |haakjes |
| **[ ]** |blokhaken |
| **{ }** |accolades |
| **^** |dakje |
| **$** |dollarteken |
| **&#124;** |verticale streep |
| **\\** |backslash |

U kunt bijvoorbeeld "Hallo?" vinden door het patroon **"Hallo\\?"** te gebruiken met een backslash vóór het vraagteken.

### <a name="predefined-patterns"></a>Vooraf gedefinieerde patronen
Vooraf gedefinieerde patronen bieden een eenvoudige manier om een reeks tekens of een opeenvolging van meerdere tekens te vinden. Gebruik de [samenvoegingsoperator **&** voor tekenreeksen](operators.md) om uw eigen teksttekenreeks te combineren met leden van de enum **Match**:

| Match-enum | Beschrijving | Reguliere expressie |
| --- | --- | --- |
| **Alle** |Komt overeen met een willekeurig teken. |**,** |
| **Komma** |Komt overeen met een komma. |**,** |
| **Cijfer** |Komt overeen met één cijfer ("0" tot en met "9"). |**\\d** |
| **E-mail** |Komt overeen met een e-mailadres dat een apenstaartje ("@") en een domeinnaam met een punt (".") bevat. |**.+@.+\\.[^\\.]{2,}** |
| **Afbreekstreepje** |Komt overeen met een afbreekstreepje. |**\\-** |
| **LeftParen** |Komt overeen met een haakje openen "(". |**\\(** |
| **Letter** |Komt overeen met een letter. |**\\p{L}** |
| **MultipleDigits** |Komt overeen met een of meer cijfers. |**\\d+** |
| **MultipleLetters** |Komt overeen met een of meer letters. |**\\p{L}+** |
| **MultipleNonSpaces** |Komt overeen met een of meer tekens die geen witruimte (spatie, tab, nieuwe regel) toevoegen. |**\\S+** |
| **MultipleSpaces** |Komt overeen met een of meer tekens die witruimte (spatie, tab, nieuwe regel) toevoegen. |**\\s+** |
| **NonSpace** |Komt overeen met één teken dat geen witruimte toevoegt. |**\\S** |
| **OptionalDigits** |Komt overeen met nul, een of meer cijfers. |**\\d** |
| **OptionalLetters** |Komt overeen met nul, een of meer letters. |**\\p{L}** |
| **OptionalNonSpaces** |Komt overeen met nul, een of meer tekens die geen witruimte toevoegen. |**\\S** |
| **OptionalSpaces** |Komt overeen met nul, een of meer tekens die witruimte toevoegen. |**\\s** |
| **Period** |Komt overeen met een punt ("."). |**\\.** |
| **RightParen** |Komt overeen met een haakje sluiten ")". |**\\)** |
| **Space** |Komt overeen met een teken dat witruimte toevoegt. |**\\s** |

Het patroon **"A" & MultipleDigits** zal bijvoorbeeld overeenkomen met de letter "A", gevolgd door een of meer cijfers.  

### <a name="regular-expressions"></a>Reguliere expressies
Het patroon dat door **IsMatch** wordt gebruikt, is een *reguliere expressie*. De gewone tekens en vooraf gedefinieerde patronen die hierboven worden beschreven, helpen bij het opbouwen van reguliere expressies.  

Reguliere expressies zijn heel krachtig en beschikbaar in veel programmeertalen. Ze worden voor veel verschillende doeleinden gebruikt. Dit artikel kan niet alle aspecten van reguliere expressies beschrijven, maar er is op het internet een schat aan informatie en zelfstudies gepubliceerd om u te helpen.  

Reguliere expressies hebben verschillende dialecten en PowerApps maakt gebruik van een variant van het JavaScript-dialect. Raadpleeg [regular expression syntax (syntaxis van reguliere expressie)](http://msdn.microsoft.com/library/1400241x.aspx) voor meer informatie.

In de **Match**-enumtabel hierboven breidt elke enum zich uit in een reguliere expressie. De teksttekenreeks in de kolom "Reguliere expressie" definieert die expressie.

## <a name="match-options"></a>Overeenkomstopties
U kunt het gedrag van **IsMatch** wijzigen door een of meer opties te specificeren. U kunt deze combineren door de samenvoegingsoperator voor tekenreeksen (**&amp;**) te gebruiken.  

**IsMatch** test standaard op een volledige overeenkomst van de gehele teksttekenreeks.

| MatchOptions-enum | Beschrijving | Gevolgen voor de reguliere expressie |
| --- | --- | --- |
| **BeginsWith** |Het patroon moet overeenkomen vanaf het begin van de tekst. |Voegt een **^** toe aan het begin van de reguliere expressie. |
| **Complete** |Standaard.  Het patroon moet met de volledige tekst overeenkomen, vanaf het begin tot einde. |Voegt een **^** aan het begin en **$** aan het einde van de reguliere expressie toe. |
| **Contains** |Het patroon moet ergens in de tekst worden weergegeven, maar hoeft niet aan het begin of einde te staan. |Wijzigt de reguliere expressie niet. |
| **EndsWith** |Het patroon moet overeenkomen met het einde van de tekst. |Voegt een **$** toe aan het einde van de reguliere expressie. |
| **IgnoreCase** |Behandelt de overeenkomst van letters op een niet-hoofdlettergevoelige manier. De overeenkomst is standaard hoofdlettergevoelig. |Wijzigt de reguliere expressie niet. |
| **Multiline** |Komt overeen over meerdere regels. |Wijzigt de reguliere expressie niet. |

## <a name="syntax"></a>Syntaxis
**IsMatch**( *Text*, *Pattern* [, *Options* ] )

* *Text* – vereist.  De teksttekenreeks die moet worden getest.
* *Pattern* – vereist.  Het patroon dat moet worden getest als teksttekenreeks.  Voeg vooraf gedefinieerde patronen die de **Match**-enum definieert samen of geef een reguliere expressie op.
* *Options* – optioneel.  Een teksttekenreekscombinatie van **MatchOptions**-enumwaarden.  Standaard wordt **MatchOptions.Complete** gebruikt.

## <a name="examples"></a>Voorbeelden
### <a name="ordinary-characters"></a>Gewone tekens
Stel dat uw app een besturingselement **Tekstinvoer** bevat met de naam **TextInput1**.  De gebruiker voert in dit besturingselement waarden in die in een database moeten worden opgeslagen.   

De gebruiker typt **Hallo wereld** in **TextInput1**.

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **IsMatch( TextInput1.Text, "Hallo wereld" )** |Test of de invoer van de gebruiker exact overeenkomt met de tekenreeks "Hallo wereld" |**true** |
| **IsMatch( TextInput1.Text, "Tot ziens" )** |Test of de invoer van de gebruiker exact overeenkomt met de tekenreeks "Tot ziens" |**false** |
| **IsMatch( TextInput1.Text, "hallo", Contains )** |Test of de invoer van de gebruiker het woord "hallo" (hoofdlettergevoelig) bevat. |**false** |
| **IsMatch( TextInput1.Text, "hallo", Contains & IgnoreCase )** |Test of de invoer van de gebruiker het woord "hallo" (niet-hoofdlettergevoelig) bevat. |**true** |

### <a name="predefined-patterns"></a>Vooraf gedefinieerde patronen
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **IsMatch( "123-45-7890", Digit & Digit & Digit & Hyphen & Digit & Digit & Hyphen & Digit & Digit & Digit & Digit & Digit )** |Komt overeen met een burgerservicenummer van de Verenigde Staten |**true** |
| **IsMatch( "joan@contoso.com", E-mail )** |Komt overeen met een e-mailadres |**true** |
| **IsMatch( "123.456", MultipleDigits & Period & OptionalDigits )** |Komt overeen met een opeenvolging van cijfers, een punt en vervolgens nul of meer cijfers. |**true** |
| **IsMatch( "123", MultipleDigits & Period & OptionalDigits )** |Komt overeen met een opeenvolging van cijfers, een punt en vervolgens nul of meer cijfers. Er staat geen punt in de tekst. Daarom is er geen overeenkomst met dit patroon. |**false** |

### <a name="regular-expressions"></a>Reguliere expressies
| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **IsMatch( "986", "\d+" )** |Komt overeen met een geheel getal dat groter is dan nul. |**true** |
| **IsMatch( "1.02", "\d+(\.\d\d)?" )** |Komt overeen met een positief bedrag. Als de invoer een decimaalteken bevat, moet de invoer ook 2 numerieke tekens na het decimaalteken bevatten. 3,00 is bijvoorbeeld geldig, maar 3,1 is dat niet. |**true** |
| **IsMatch( "-4.95", "(-)?\d+(\.\d\d)?" )** |Komt overeen met een positief of negatief bedrag. Als de invoer een decimaalteken bevat, moet de invoer ook 2 numerieke tekens na het decimaalteken bevatten. |**true** |
| **IsMatch( "111-11-1111", "\d{3}-\d{2}-\d{4}" )** |Komt overeen met een burgerservicenummer van de Verenigde Staten.  Valideert de indeling, het type en de lengte van het opgegeven invoerveld. De tekenreeks die overeen moet komen, moet bestaan uit 3 numerieke tekens met daar achter een streepje, daarna 2 numerieke tekens met daar achter een streepje en vervolgens 4 numerieke tekens. |**true** |
| **IsMatch( "111-111-111", "\d{3}-\d{2}-\d{4}" )** |Hetzelfde als het vorige voorbeeld, maar een van de afbreekstreepjes in de invoer valt buiten het bereik. |**false** |
| **IsMatch( "weakpassword", "(?!^[0-9]\*$)(?!^[a-zA-Z]\*$)([a-zA-Z0-9]{8,10})" )** |Valideert een sterk wachtwoord, dat uit 8, 9 of 10 tekens moet bestaan en daarnaast minimaal één cijfer en minimaal een letter moet bevatten. De tekenreeks mag geen speciale tekens bevatten. |**false** |
| **IsMatch( "http://microsoft.com", "(ht&#124;f)tp(s?)\:\/\/\[0-9a-zA-Z\]([-.\w]\*[0-9a-zA-Z])\*(:(0-9)\*)\*(\/?)([a-zA-Z0-9\-\.\?\,\'\/\\\+&amp;%\$#_]\*)?" )** |Valideert een http-, https- of ftp-URL. |**true** |

