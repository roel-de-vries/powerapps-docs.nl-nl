---
title: De functie Taal | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Taal in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/16/2016
ms.author: gregli
ms.openlocfilehash: ec12bef225c59474fbc15a3ab0556694d206edd3
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="language-function-in-powerapps"></a>De functie Taal in PowerApps
Retourneert de taalcode van de huidige gebruiker.

## <a name="description"></a>Beschrijving
De functie **Taal** retourneert de taal, het script en de regio van de huidige gebruiker als een taalcode.

Gebruik de taalinformatie om uw app aan te passen op basis van landinstellingen.  Als u bijvoorbeeld een app maakt die in Italië en Frankrijk zal worden gebruikt, kunt u **Taal** gebruiken om automatisch Italiaanse en Franse tekenreeksen weer te geven voor uw gebruikers op deze verschillende locaties. 

### <a name="language-tags"></a>Taalcodes
Een *taalcode* kan een van de volgende drie indelingen hebben:

| Retourwaarde | Beschrijving |
| --- | --- |
| **"*lg&#8209;RE*"** |*lg* is de afkorting van twee tekens voor de taal en *RE* is de afkorting van twee tekens voor de regio.  Dit is het meest voorkomende retourtype.  Zo wordt "en-GB" geretourneerd voor het Verenigd Koninkrijk. |
| **"*lg*"** |*lg* is de afkorting van twee tekens voor de taal.  Dit is de indeling die wordt gebruikt als PowerApps wel informatie over de taal, maar geen informatie voor de specifieke regio heeft. |
| **"*lg&#8209;scrp&#8209;RE*"** |*lg* is de afkorting van twee tekens voor de taal, *scrp* is de afkorting van vier tekens voor het schrift en *RE* is de afkorting van twee tekens voor de regio. |

PowerApps gebruikt de [IETF BCP-47-taalcode](https://tools.ietf.org/html/bcp47)-indeling.  

Typ **Waarde ( "1", )** in de formulebalk of in de geavanceerde weergave en schuif door de lijst met aanbevolen landinstellingen voor het tweede argument om de lijst met ondersteunde taalcodes weer te geven.  

De functies **[Tekst](function-text.md)** en **[Waarde](function-value.md)** gebruiken ook taalcodes.  Gebruik deze functies om op een wereldbewuste manier te vertalen naar en van teksttekenreeksen.  U kunt alleen het taalgedeelte van de code gebruiken als u een taalcode aan deze functies doorgeeft en de regio daarbij geen verschil zou maken.

## <a name="syntax"></a>Syntaxis
**Language**()

## <a name="examples"></a>Voorbeelden
### <a name="users-locale"></a>De landinstellingen van de gebruiker
Er wordt vanuit gegaan dat het hostbesturingssysteem en/of de browser de standaardlandinstelling voor de locatie gebruiken.

| Formule | Locatie | Retourwaarde |
| --- | --- | --- |
| **Language()** |Lissabon, Portugal |"pt-PT" |
| **Language()** |Rio de Janeiro, Brazilië |"pt-BR" |
| **Language()** |Atlanta, VS |"en-US" |
| **Language()** |Manchester, Verenigd Koninkrijk |"en-GB" |
| **Language()** |Parijs, Frankrijk |"fr-FR" |
| **Language()** |Roseau, Dominica |"en" |
| **Language()** |Belgrado, Servië |"sr-cyrl-RS" of "sr-latn-RS", afhankelijk van de systeeminstellingen van de gebruiker |

### <a name="localization-table"></a>Lokalisatietabel
Een eenvoudige lokalisatiemethode is om een Excel-werkblad te maken waarin een door de auteur gedefinieerde **Tekst-ID** wordt toegewezen aan een vertaalde tekst voor de taal van de gebruiker.  Hoewel u een verzameling of willekeurige andere gegevensbron voor deze tabel kunt gebruiken, kiezen we voor Excel omdat vertalers die indeling eenvoudig kunnen bewerken en buiten de app kunnen beheren.

1. Maak de volgende tabel in Excel: 
   
    ![](media/function-language/loc-table.png)
   
    De invoer met *leeg* voor de kolom **Taal** zal standaard worden gebruikt als er geen specifieke teksttekenreeks voor een bepaalde taal is gevonden. Deze invoer moet achter alle andere invoeren voor bepaalde **Tekst-ID** worden weergegeven.
   
    We moeten voor ons doel alleen naar de taal van de landinstelling kijken, niet naar de regio.  Als regionale overwegingen belangrijk waren geweest, hadden we de volledige taalcodewaarde in de bovenstaande tabel kunnen opnemen. 
2. Gebruik de opdracht **Tabel** op het lint **Invoegen** om er een juiste Excel-tabel van te maken.  Deze heeft standaard de naam **Tabel1**, maar u kunt hem via het lint **Hulpmiddelen voor tabellen/Ontwerp** en het tekstvak **Tabelnaam:** uiterst links een willekeurige naam geven.
3. Sla het Excel-bestand op naar uw lokale bestandssysteem.   
4. Klik of tik in het rechterdeelvenster op het tabblad **Gegevensbronnen** in PowerApps en klik of tik vervolgens op **Gegevensbron toevoegen**.
5. Klik of tik op **Statische gegevens toevoegen aan uw app**, klik of tik op het Excel-bestand dat u hebt opgeslagen en klik of tik vervolgens op **Openen**.
6. Selecteer de tabel die u hebt gemaakt en klik of tik vervolgens op **Verbinden**.

Gebruik in uw app de volgende formule op de plaats waar u anders de tekst **"Hallo"** zou hebben gebruikt:

* **LookUp( Table1, TextID = "Hello" && (LanguageTag = Left( Language(), 2 ) || IsBlank( LanguageTag ))).LocalizedText**  

Deze formule zal de juiste waarde voor **LocalizedText** voor de taal van de gebruiker opzoeken. Als deze niet wordt gevonden, zal hij terugvallen op de *lege* standaardversie. 

Wees u ervan bewust dat vertaalde tekenreeksen in andere talen aanzienlijk langer kunnen zijn dan in uw eigen taal.  De labels en andere elementen waarin de tekenreeksen in uw gebruikersinterface worden weergegeven, moeten daarom in veel gevallen breder zijn, zodat er ruimte is voor langere teksten.

### <a name="translation-service"></a>Vertaalservice
U kunt tekst op verzoek vertalen via een vertaalservice, zoals de service Microsoft Translator:  

1. Klik of tik in het rechterdeelvenster op het tabblad **Gegevensbronnen** in PowerApps en klik of tik vervolgens op **Gegevensbron toevoegen**.
2. Klik of tik op **Microsoft Translator**.

Gebruik in uw app de volgende formule op de plaats waar u anders de tekst **"Hallo"** zou hebben gebruikt:

* **MicrosoftTranslator.Translate( "Hallo", Language() )**

De Microsoft Translator-service gebruikt dezelfde taalcodes die de functie **Taal** retourneert.

Deze methode heeft wat nadelen ten opzichte van het vorige voorbeeld, dat een vooraf vertaalde tabel met teksttekenreeksen gebruikte:

* De vertaling neemt tijd in beslag en vereist een aanroep van een service via het netwerk.  Dit resulteert ook in een vertraging waarmee de vertaalde tekst in uw app wordt weergegeven. 
* De vertaling zal mechanisch zijn en is mogelijk niet wat u verwacht of de beste keus voor de situatie in uw app.

