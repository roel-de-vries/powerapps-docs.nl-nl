---
title: De functie Choices | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis, voor de functie Choices in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/15/2018
ms.author: gregli
ms.openlocfilehash: 8f0985203017ec21d49fa98be870208c6ecf3ea5
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39022166"
---
# <a name="choices-function-in-powerapps"></a>De functie Choices in PowerApps
Hiermee wordt een tabel met de mogelijke waarden van een opzoekkolom geretourneerd.

## <a name="description"></a>Beschrijving
Met de functie **Choices** wordt een tabel met de mogelijke waarden van een opzoekkolom geretourneerd.  

Gebruik de functie **Choices** voor een lijst met keuzes waaruit de gebruiker kan kiezen. Deze functie wordt doorgaans gebruikt met het besturingselement [**Keuzelijst met invoervak**](../controls/control-combo-box.md) in bewerkingsformulieren.

In het geval van een zoekopdracht komt de tabel die met **Choices** wordt geretourneerd overeen met de externe tabel die is gekoppeld aan de zoekopdracht. Als u **Choices** gebruikt, hoeft u de externe tabel niet toe te voegen als een extra gegevensbron. Met **Choices** worden alle kolommen van de externe tabel geretourneerd.

Omdat met **Choices** een tabel wordt geretourneerd, kunt u [ **Filter**](function-filter-lookup.md), [**Sort**](function-sort.md), [**AddColumns**](function-table-shaping.md) en alle andere functies om tabellen te bewerken, gebruiken om de tabel te filteren, sorteren en vorm te geven. 

Op dit moment kunt u [Choices](../delegation-overview.md) niet **delegeren**. Als deze beperking een probleem vormt in uw app, kunt u de externe entiteit toevoegen als een gegevensbron en deze rechtstreeks gebruiken. 

Voor **Choices** is niet vereist dat kolomnamen tekenreeksen zijn en tussen dubbele aanhalingstekens staan, in tegenstelling tot de functies [**ShowColumns**](function-table-shaping.md), [**Search**](function-filter-lookup.md) en andere tabelfuncties. Geef de formule op alsof u rechtstreeks naar de kolom verwijst.

Kolomverwijzingen moet rechtstreeks naar de gegevensbron zijn. Als de gegevensbron bijvoorbeeld **Accounts** is en de zoekopdracht is **SLA**, dan is de kolomverwijzing **Accounts.SLA**. De verwijzing niet kan worden doorgeven aan een functie, een variabele of een besturingselement. Als in dit voorbeeld **Accounts** wordt doorgevoerd naar een **Gallery**-besturingselement, gebruikt u de formule **Gallery.Selected.SLA** om te verwijzen naar de SLA voor het geselecteerde account. Deze verwijzing wordt echter doorgegeven via een besturingselement en kan daardoor niet worden doorgegeven aan de functie **Columns**: u moet nog steeds **Accounts.SLA** gebruiken.

Op dit moment kunt u opzoekkolommen alleen gebruiken met SharePoint en Common Data Service voor apps.

## <a name="syntax"></a>Syntaxis
**Choices**( *column-reference* )

* *column-reference*: vereist.  Een opzoekkolom van een gegevensbron. Zet de naam van de kolom niet tussen dubbele aanhalingstekens. De verwijzing moet rechtstreeks naar de kolom van de gegevensbron zijn en moet niet via een functie of een besturingselement gaan.

## <a name="examples"></a>Voorbeelden

#### <a name="choices-for-a-lookup"></a>Opties voor een zoekopdracht

1. [Maak een database](../../../administrator/create-database.md) in Common Data Service voor apps en selecteer het vak **Voorbeeld-apps en gegevens insluiten**.

    Er worden veel entiteiten gemaakt, zoals **Accounts**.

    **Opmerking**: namen van entiteiten zijn in enkelvoud op web.powerapps.com en in meervoud in PowerApps Studio.

    ![Een gedeeltelijke lijst van de velden uit de entiteit Account in Commmon Data Service voor apps, die 'primaire contactpersoon' markeren is een opzoekveld](media/function-choices/entity-account.png)

    De entiteit **Accounts** heeft een kolom met de naam **Primair contactpersoon**; dit is een zoekopdracht naar de entiteit **Contactpersonen**.  

    ![Een gedeeltelijke lijst van de velden uit de entiteit Contact in Commmon Data Service](media/function-choices/entity-contact.png)

    Voor elk account wordt een contactpersoon aangewezen als de primaire contactpersoon, of de primaire contactpersoon is *leeg*.

2. [Genereer een app](../data-platform-create-app.md) op basis van de entiteit **Accounts**.

3. Schuif in de lijst met schermen en besturingselementen aan de linkerkant omlaag tot **EditScreen1** wordt weergegeven en selecteer vervolgens **EditForm1** daar net onder.

    ![Selecteer in de linkernavigatiebalk EditForm1 op EditScreen1](media/function-choices/select-editform.png)

4. Selecteer op het tabblad **Eigenschappen** van het rechterdeelvenster de optie **Accounts**.

    ![Selecteer Accounts om het deelvenster Gegevens te openen](media/function-choices/open-data-pane.png)

5. Schuif in het deelvenster **Gegevens** omlaag naar de lijst met velden.

    ![Selecteer Accounts om het deelvenster Gegevens te openen](media/function-choices/field-list.png)

6. Zoek het selectievakje **Primaire contactpersoon** en schakel dit in als het is uitgeschakeld.

7. (optioneel) Sleep het veld **Primaire contactpersoon** van de onderkant naar de bovenkant van de lijst met velden.

8. Selecteer in de kaart voor **Primaire contactpersoon** het besturingselement **Keuzelijst met invoervak**.

    De eigenschap **Items** van dat besturingselement is ingesteld op een van twee formules die zijn gebaseerd op de status van het selectievakje **Weergavenamen van kolom gebruiken** in de geavanceerde instellingen.

   - Als het selectievakje is ingeschakeld, wordt de eigenschap ingesteld op deze formule:<br>**Choices( Accounts.'Primary Contact' )**
   - Als het selectievakje is uitgeschakeld, wordt de eigenschap ingesteld op deze formule:<br>**Choices( Accounts.primarycontactid )**

     ![Een canvasscherm met een formulierbesturingselement. Het besturingselement **Keuzelijst met invoervak** binnen de kaart **Primaire contactpersoon** is geselecteerd en de eigenschap Items met de formule Choices( Accounts.'Primary Contact' ) wordt weergegeven](media/function-choices/accounts-primary-contact.png)

9. Selecteer op het tabblad **Start** de optie **Nieuw scherm**  en selecteer vervolgens **Leeg**.

10. Selecteer **Gegevenstabel** op het tabblad **Invoegen**.

11. Stel de eigenschap **Items** van het besturingselement **Gegevenstabel** in op een van deze waarden:

     - Als het selectievakje **Weergavenamen van kolom gebruiken** in de geavanceerde instellingen is ingeschakeld, gebruikt u deze formule:<br>**Choices( Accounts.'Primary Contact' )**
     - Gebruik anders deze formule:<br>**Choices( Accounts.primarycontactid )**

12. Open het deelvenster **Gegevens** en schakel vervolgens de selectievakjes in voor **firstname**, **lastname** of elk ander veld dat u wilt weergeven.

     ![Een canvasscherm met een besturingselement van het type gegevenstabel. De eigenschap Items is ingesteld op de formule Choices( Accounts.'Primary Contact' ) en de tabel toont de kolommen firstname en lastname voor de eerste set records uit de entiteit Contactpersonen](media/function-choices/full-accounts-pc.png)