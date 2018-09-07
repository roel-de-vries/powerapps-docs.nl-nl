---
title: Functies Acos, Acot, Asin, Atan, Atan2, Cos, Cot, Degrees, Pi, Radians, Sin en Tan | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Abs en Sqrt in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/13/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6eab89f436bc00ae0c447494607b5c1bb0cec875
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833108"
---
# <a name="acos-acot-asin-atan-atan2-cos-cot-degrees-pi-radians-sin-and-tan-functions-in-powerapps"></a>De functies Acos, Acot, Asin, Atan, Atan2, Cos, Cot, Degrees, Pi, Radians, Sin en Tan in PowerApps
Hiermee berekent u trigonometrische waarden.

## <a name="description"></a>Beschrijving
### <a name="primary-functions"></a>Primaire functies
De functie **Cos** retourneert de cosinus van het argument, een hoek aangeduid in radialen.

De functie **Cot** retourneert de cotangens van het argument, een hoek aangeduid in radialen.

De functie **Sin** retourneert de sinus van het argument, een hoek aangeduid in radialen.

De functie **Tan** retourneert de tangens van het argument, een hoek aangeduid in radialen.

### <a name="inverse-functions"></a>Inverse functies
De functie **Acos** retourneert de arccosinus of inverse cosinus van het argument. De arccosinus is de hoek waarvan de cosinus het argument is.  De geretourneerde hoek wordt uitgedrukt in radialen in het bereik tussen 0 (nul) en &pi;.

De functie **Acot** retourneert de hoofdwaarde van de arccotangens of inverse cotangens van het argument.  De geretourneerde hoek wordt uitgedrukt in radialen in het bereik tussen 0 (nul) en &pi;.

De functie **Asin** retourneert de arcsinus of inverse sinus van het argument. De arcsinus is de hoek waarvan de cosinus het argument is.  De geretourneerde hoek wordt uitgedrukt in radialen in het bereik -&pi;/2 tot &pi; /2.

De functie **Atan** retourneert de arctangens of inverse tangens van het argument. De arctangens is de hoek waarvan de tangens het argument is. De geretourneerde hoek wordt uitgedrukt in radialen in het bereik -&pi;/2 tot &pi; /2.

De functie **Atan2** functie retourneert de arctangens of inverse tangens van de opgegeven *x*- en *y*-coördinaten als argumenten. De arctangens is de hoek tussen de *x*-as en een lijn regel die de oorsprong (0, 0) bevat en een punt met de coördinaten (*x*, *y*). De hoek wordt uitgedrukt in radialen tussen -&pi; en &pi;, met uitzondering van -&pi;.  Een positief resultaat staat voor een hoek tegen de klok in vanaf de *x*-as. Een negatief resultaat staat voor een hoek met de klok mee.  **Atan2(&nbsp;*a*,&nbsp;*b*&nbsp;)** is gelijk aan **Atan(&nbsp;*b*/*a*&nbsp;)**, behalve dat ***a*** bij de functie **Atan2** gelijk kan zijn aan 0 (nul).

### <a name="helper-functions"></a>Ondersteunende functies
De functie **Degrees** converteert radialen naar graden.  &pi; radialen is gelijk aan 180 graden.

De functie **Pi** retourneert het transcendentale getal &pi;, dat begint met 3,141592...

De functie **Radians** converteert graden naar radialen.  

### <a name="notes"></a>Opmerkingen
Als u één getal doorgeeft aan deze functies, is de resulterende waarde één resultaat.  Als u een [tabel](../working-with-tables.md) met één kolom doorgeeft die getallen bevat, is de geretourneerde waarde een tabel met één kolom met resultaten (één resultaat voor elke record in de tabel voor het argument). Als u een tabel met meerdere kolommen hebt, kunt u deze omvormen tot een tabel met één kolom, zoals in [working with tables (werken met tabellen)](../working-with-tables.md) is beschreven.  

Als een argument tot een niet-gedefinieerde waarde zou leiden, is het resultaat *leeg*.  Dit kan bijvoorbeeld gebeuren wanneer inverse functies worden gebruikt met argumenten die buiten het bereik liggen.

## <a name="syntax"></a>Syntaxis
### <a name="primary-functions"></a>Primaire functies
**Cos**( *Radialen* )<br>**Cot**( *Radialen* )<br>**Sin**( *Radialen* )<br>**Tan**( *Radialen* )

* *Radians* - vereist. De hoek waarop de bewerking wordt toegepast.

**Cos**( *TabelMetEénKolom* )<br>**Cot**( *TabelMetEénKolom* )<br>**Sin**( *TabelMetEénKolom* )<br>**Tan**( *TabelMetEénKolom* )

* *TabelMetEénKolom* - vereist. Een tabel met één kolom met hoeken waarop de bewerking wordt toegepast.

### <a name="inverse-functions"></a>Inverse functies
**Acos**( *Getal* )<br>**Acot**( *Getal* )<br>**Asin**( *Getal* )<br>**Atan**( *Getal* )

* *Getal* - vereist. Getal om bewerking op uit te voeren.

**Acos**( *TabelMetEénKolom* )<br>**Acot**( *TabelMetEénKolom* )<br>**Asin**( *TabelMetEénKolom* )<br>**Atan**( *TabelMetEénKolom* )

* *TabelMetEénKolom* - vereist. Een tabel met één kolom die getallen bevat om bewerkingen op uit te voeren.

**Atan2**( *X*, *Y* )

* *X* - vereist.  Coördinaat van de *X*-as.
* *Y* - vereist.  Coördinaat van de *Y*-as.

### <a name="helper-functions"></a>Ondersteunende functies
**Degrees**( *Radialen* )

* *Radians* - vereist.  De hoek in radialen die moet worden omgezet in graden.

**Pi**()

**Radians**( *Graden* )

* *Degrees* - vereist.  De hoek in graden die moet worden omgezet in radialen.

## <a name="examples"></a>Voorbeelden
### <a name="single-number"></a>Eén getal

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Cos(&nbsp;1,047197&nbsp;)** |Retourneert de cosinus van 1,047197 radialen of 60 graden. |0,5 |
| **Cot(&nbsp;Pi()/4&nbsp;)** |Retourneert de cotangens van 0,785398... radialen of 45 graden. |1 |
| **Sin(&nbsp;Pi()/2&nbsp;)** |Retourneert de sinus van 1,570796... radialen of 90 graden. |1 |
| **Tan(&nbsp;Radians(60)&nbsp;)** |Retourneert de tangens van 1,047197... radialen of 60 graden. |1,732050... |
| **Acos(&nbsp;0,5&nbsp;)** |Retourneert de arccosinus van 0,5 in radialen. |1,047197... |
| **Acot(&nbsp;1&nbsp;)** |Retourneert de arccotangens van 1 in radialen. |0,785398... |
| **Asin(&nbsp;1&nbsp;)** |Retourneert de arcsinus van 1 in radialen. |1,570796... |
| **Atan(&nbsp;1,732050&nbsp;)** |Retourneert de arctangens van 1,732050 in radialen. |1,047197... |
| **Atan2(&nbsp;5,&nbsp;3&nbsp;)** |Retourneert de arctangens van de hoek van de *x*-as met de lijn die de oorsprong (0,0) en de coördinaat (5,3) bevat, wat ongeveer 31 graden is. |0,540419... |
| **Atan2(&nbsp;4,&nbsp;4&nbsp;)** |Retourneert de arctangens van de hoek van de *x*-as met de lijn die de oorsprong (0,0) en de coördinaat (4,4) bevat, wat precies &pi;/4 radialen of 45 graden is. |0,785398... |
| **Degrees(&nbsp;1,047197&nbsp;)** |Retourneert het equivalente aantal graden voor 1,047197 radialen. |60 |
| **Pi()** |Retourneert het transcendente getal &pi;. |3,141592... |
| **Radians(&nbsp;15&nbsp;)** |Retourneert het equivalente aantal radialen voor 15 graden. |0,261799... |

### <a name="single-column-table"></a>Tabel met één kolom
In de voorbeelden in deze sectie wordt een [gegevensbron](../working-with-data-sources.md) met de naam **Waardetabel** gebruikt die de volgende gegevens bevat.  De laatste record in de tabel is &pi;/2 radialen of 90 graden.

![](media/function-trig/values.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Cos(&nbsp;Waardetabel&nbsp;)** |Retourneert de cosinus van elk getal in de tabel. |<style> img { max-width: none } </style> ![](media/function-trig/values-cos.png) |
| **Cot(&nbsp;Waardetabel&nbsp;)** |Retourneert de cotangens van elk getal in de tabel. |<style> img { max-width: none } </style> ![](media/function-trig/values-cot.png) |
| **Sin(&nbsp;Waardetabel&nbsp;)** |Retourneert de sinus van elk getal in de tabel. |<style> img { max-width: none } </style> ![](media/function-trig/values-sin.png) |
| **Tan(&nbsp;Waardetabel&nbsp;)** |Retourneert de tangens van elk getal in de tabel. |<style> img { max-width: none } </style> ![](media/function-trig/values-tan.png) |
| **Acos(&nbsp;Waardetabel&nbsp;)** |Retourneert de arccosinus van elk getal in de tabel. |<style> img { max-width: none } </style> ![](media/function-trig/values-acos.png) |
| **Acot(&nbsp;Waardetabel&nbsp;)** |Retourneert de arccotangens van elk getal in de tabel. |<style> img { max-width: none } </style> ![](media/function-trig/values-acot.png) |
| **Asin(&nbsp;Waardetabel&nbsp;)** |Retourneert de arcsinus van elk getal in de tabel. |<style> img { max-width: none } </style> ![](media/function-trig/values-asin.png) |
| **Atan(&nbsp;Waardetabel&nbsp;)** |Retourneert de arctangens van elk getal in de tabel. |<style> img { max-width: none } </style> ![](media/function-trig/values-atan.png) |
| **Degrees(&nbsp;Waardetabel&nbsp;)** |Retourneert het equivalente aantal graden voor elk getal in de tabel, ervan uitgaande dat de hoeken in radialen zijn. |<style> img { max-width: none } </style> ![](media/function-trig/values-degrees.png) |
| **Radians(&nbsp;Waardetabel&nbsp;)** |Retourneert het equivalente aantal radialen voor elk getal in de tabel, ervan uitgaande dat de hoeken in graden zijn. |<style> img { max-width: none } </style> ![](media/function-trig/values-radians.png) |

