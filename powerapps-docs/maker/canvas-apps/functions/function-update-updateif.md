---
title: Functies Update en UpdateIf | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functies Update en UpdateIf in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: 3046aa93941a07d44345e09b442cb57b623946c3
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31834339"
---
# <a name="update-and-updateif-functions-in-powerapps"></a>De functies Update en UpdateIf in PowerApps
Werken [records](../working-with-tables.md#records) in een [gegevensbron](../working-with-data-sources.md) bij.

## <a name="description"></a>Beschrijving
### <a name="update-function"></a>De functie Update
Gebruik de functie **Update** om een hele record in een gegevensbron te vervangen. De functies **UpdateIf** en **[Patch](function-patch.md)** wijzigen daarentegen een of meer waarden in een record, waarbij de andere waarden ongewijzigd blijven.

Voor een [verzameling](../working-with-data-sources.md#collections) moet de hele record overeenkomen. Verzamelingen staan dubbele records toe, waardoor mogelijk meerdere records overeenkomen. U kunt het argument **All** gebruiken om alle exemplaren van een record bij te werken. Anders wordt slechts één exemplaar van de record bijgewerkt.

Als in de gegevensbron de waarde van een kolom automatisch wordt gegenereerd, moet de waarde van die [kolom](../working-with-tables.md#columns) automatisch opnieuw worden bevestigd.

### <a name="updateif-function"></a>De functie UpdateIf
Gebruik de functie **UpdateIf** om een of meer waarden te wijzigen in een of meer records die voldoen aan een of meer voorwaarden. De voorwaarde kan elke formule zijn die resulteert in **true** of **false** en kan verwijzen naar kolommen in de gegevensbron, waarbij de naam van de kolom wordt gebruikt. De functie evalueert de voorwaarde voor elke record en wijzigt elk record die het resultaat **true** oplevert.  

Als u een wijziging wilt opgeven, gebruikt u een wijzigingsrecord die nieuwe eigenschapswaarden bevat. Als u deze wijzigingsrecord inline opgeeft tussen accolades, kunnen eigenschapsformules verwijzen naar eigenschappen van de record die wordt gewijzigd. U kunt dit gedrag gebruiken om records te wijzigen op basis van een formule.

Net als **UpdateIf** kunt u ook de functie **[Patch](function-patch.md)** gebruiken om specifieke kolommen in een record te wijzigen zonder dat dit van invloed is op andere kolommen.

**Update** en **UpdateIf** retourneren de gewijzigde gegevensbron als een [tabel](../working-with-tables.md). U moet beide functies gebruiken in een [gedragsformule](../working-with-formulas-in-depth.md).

### <a name="delegation"></a>Delegering
[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>Syntaxis
**Update**( *DataSource*, *OldRecord*, *NewRecord* [, **All** ] )

* *DataSource* - vereist. De gegevensbron met de records die u wilt vervangen.
* *OldRecord* - vereist. De record die moet worden vervangen.
* *NewRecord* - vereist. De vervangende record. Dit is geen wijzigingsrecord. De hele record wordt vervangen en ontbrekende eigenschappen bevatten *leeg*.
* **All** - optioneel. In een verzameling kan een record meerdere keren voorkomen. U kunt het argument **All** toevoegen als u alle exemplaren van de record wilt vervangen.

**UpdateIf**( *DataSource*, *Condition1*, *ChangeRecord1* [, *Condition2*, *ChangeRecord2*, ... ] )

* *DataSource* - vereist. De gegevensbron met de record of records die u wilt wijzigen.
* *Condition(s)* - vereist. Een formule die evalueert als **true** voor de records die u wilt wijzigen.  U kunt kolomnamen uit de *Gegevensbron* gebruiken in de formule.  
* *ChangeRecord(s)* - vereist.  Voor elke overeenkomstige voorwaarde moet een wijzigingsrecord worden toegevoegd met nieuwe eigenschapswaarden die moeten worden toegepast op records in de *DataSource* die voldoen aan de voorwaarde. Als u de record inline opgeeft tussen accolades, kunnen eigenschapswaarden van de bestaande record in de eigenschapsformules worden gebruikt.

## <a name="examples"></a>Voorbeelden
In deze voorbeelden vervangt of wijzigt u records in een gegevensbron genaamd **IJs** die begint met de gegevens in deze tabel:

![](media/function-update-updateif/icecream.png)

| Formule | Beschrijving | Resultaat |
| --- | --- | --- |
| **Update(&nbsp;IJs,<br>First(&nbsp;Filter(&nbsp;IJs,&nbsp;Smaak="Chocolade"&nbsp;)&nbsp;), {&nbsp;ID:&nbsp;1,&nbsp;Smaak:&nbsp;"Pure&nbsp;chocolade",&nbsp;Aantal:150&nbsp;} )** |Vervangt een record uit de gegevensbron. |<style> img { max-width: none } </style> ![](media/function-update-updateif/icecream-mint.png)<br><br>De gegevensbron **IJs** is gewijzigd. |
| **UpdateIf(&nbsp;IJs, Aantal > 175 {&nbsp;Aantal:&nbsp;Aantal&nbsp;+&nbsp;10&nbsp;} )** |Hiermee wijzigt u records waarvan **Aantal** groter is dan **175**.  Het veld **Aantal** wordt met 10 verhoogd en er worden geen andere velden gewijzigd. |![](media/function-update-updateif/icecream-mint-plus10.png)<br><br>De gegevensbron **IJs** is gewijzigd. |
| **Update(&nbsp;IJs,<br>First(&nbsp;Filter(&nbsp;IJs, Smaak="Aardbeien"&nbsp;)&nbsp;),<br>{&nbsp;ID:&nbsp;3, Smaak:&nbsp;"Aardbeiensorbet"} )** |Vervangt een record uit de gegevensbron. De eigenschap **Aantal** is niet opgegeven in de vervangende record, zodat deze eigenschap *leeg* is in het resultaat. |![](media/function-update-updateif/icecream-mint-swirl.png)<br><br>De gegevensbron **IJs** is gewijzigd. |
| **UpdateIf(&nbsp;IJs, true, {&nbsp;Aantal:&nbsp;0&nbsp;} )** |Hiermee stelt u de waarde van de eigenschap **Aantal** voor alle records in de gegevensbron in op 0. |![ ](./media/function-update-updateif/icecream-mint-zero.png)<br> <br>De gegevensbron **IJs** is gewijzigd. |

### <a name="step-by-step"></a>Stap voor stap
1. Importeer of maak een verzameling met de naam **Inventaris** en geef deze weer in een galerie, zoals wordt beschreven in [Gegevens weergeven in een galerie](../show-images-text-gallery-sort-filter.md).
2. Noem de galerie **Productgalerie**.
3. Voeg een schuifregelaar genaamd **VerkochteEenheden** toe en stel de eigenschap **Max** in op deze expressie:<br>**Productgalerie.Selected.EenhedenOpVoorraad**
4. Voeg een knop toe en stel de eigenschap **[OnSelect](../controls/properties-core.md)** ervan in op deze formule:<br>**UpdateIf(Inventaris, Productnaam = Productgalerie.Selected.Productnaam, {EenhedenOpVoorraad:EenhedenOpVoorraad.VerkochteEenheden.Value})**
5. Druk op F5, selecteer een product in de galerie, geef een waarde op met behulp van de schuifregelaar en selecteer vervolgens de knop.
   
    Het aantal eenheden op voorraad voor het opgegeven product wordt verlaagd met het opgegeven aantal.

