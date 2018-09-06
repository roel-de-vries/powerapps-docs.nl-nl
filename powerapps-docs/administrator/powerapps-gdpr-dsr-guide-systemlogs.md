---
title: Reageren op verzoeken van betrokkenen voor door het systeem gegenereerde logboeken in PowerApps, Microsoft Flow en Common Data Service (CDS) for Apps | Microsoft Docs
description: Overzicht van hoe te reageren op verzoeken van betrokkenen voor door het systeem gegenereerde logboeken in PowerApps, Microsoft Flow en Common Data Service (CDS) for Apps
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: d2edace99a540fae449efb6d5d9badf5251cb33c
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864874"
---
# <a name="responding-to-dsr-requests-for-system-generated-logs-in-powerapps-microsoft-flow-and-common-data-service-for-apps"></a>Reageren op DSR-verzoeken voor door het systeem gegenereerde logboeken in PowerApps, Microsoft Flow en Common Data Service for Apps
Microsoft biedt u de mogelijkheid om door het systeem gegenereerde logboeken te openen, te exporteren en te verwijderen. Deze logboeken kunnen onder de brede definitie van *persoonsgegevens* van de algemene verordening gegevensbescherming (AVG) van de EU (Europese Unie) worden beschouwd als persoonlijk. Voorbeelden van door het systeem gegenereerde logboeken die als persoonlijk kunnen worden beschouwd onder de AVG zijn:
* Gebruiksgegevens over producten en services, zoals activiteitenlogboeken van gebruikers
* Zoekaanvragen en querygegevens van gebruikers
* Gegevens die zijn gegenereerd door producten en services als een product van systeemfunctionaliteit en interactie door gebruikers of andere systemen

Denk erom dat de mogelijkheid om gegevens in door het systeem gegenereerde logboeken te beperken of rectificeren niet wordt ondersteund. Gegevens in door het systeem gegenereerde logboeken vormen feitelijke acties die zijn uitgevoerd binnen de Microsoft-cloud. Diagnostische gegevens&mdash;waaronder wijzigingen aan dergelijke gegevens&mdash;zouden het historisch overzicht van acties in gevaar brengen, en fraude en beveiligingsrisico's vergroten.

## <a name="prerequisites"></a>Vereisten
Dit artikel is gericht op het reageren op aanvragen van betrokkenen voor door het systeem gegenereerde logboeken in beheerde en onbeheerde tenants. Als u wilt bepalen of u al dan niet lid bent van een beheerde of onbeheerde tenant, raadpleegt u het onderstaande gedeelte **Tenanttype bepalen**.

## <a name="accessing-and-exporting-system-generated-logs-for-managed-tenants"></a>Door het systeem gegenereerde logboeken voor beheerde tenants openen en exporteren
Beheerders hebben toegang tot door het systeem gegenereerde logboeken die zijn gekoppeld aan het gebruik door een gebruiker van PowerApps, Microsoft Flow en CDS (Common Data Service) for Apps-services en -toepassingen.

U kunt door het systeem gegenereerde logboeken als volgt openen en exporteren:

1. Ga naar de [Microsoft Service Trust-portal](https://servicetrust.microsoft.com/) en meld u aan met de referenties van een globale Office 365-beheerder.

2. Selecteer in de vervolgkeuzelijst **Privacy** bovenaan de pagina **DSR**.

3. Selecteer op de pagina **DSR** onder **Door het systeem gegenereerde logboeken** de optie **Gegevenslogboek exporteren**. Het venster Gegevenslogboek exporteren wordt weergegeven. Hier ziet u een overzicht van gegevensexportaanvragen die zijn ingediend door uw organisatie.

4. Klik op **Gegevensexportaanvraag maken** om een nieuwe aanvraag voor een gebruiker te maken.

    Nadat u een nieuwe aanvraag hebt gemaakt, wordt de aanvraag weergegeven op de pagina **Gegevenslogboekexport**, waar u de status ervan kunt volgen. Nadat een aanvraag is voltooid, kunt u op een koppeling klikken voor toegang tot de door het systeem gegenereerde logboeken, die binnen 30 dagen na het maken van de aanvraag worden geëxporteerd naar de Azure-opslaglocatie van uw organisatie. De gegevens worden opgeslagen in algemene, door machine leesbare bestandsindelingen als XML, CSV of JSON. Als u geen Azure-account en Azure-opslaglocatie hebt, moet u een Azure-account en/of Azure-opslaglocatie voor uw organisatie maken. Het hulpprogramma Gegevenslogboekexport kan dan de door het systeem gegenereerde logboeken exporteren. Zie voor meer informatie [Inleiding tot Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction).

De volgende tabel geeft een overzicht van hoe u door het systeem gegenereerde logboeken voor beheerde tenants opent en exporteert:

| Vraag | Antwoord |
| --- | --- |
| Hoelang duurt het voordat het Microsoft-hulpprogramma Gegevenslogboekexport een aanvraag heeft voltooid? |    Dit is afhankelijk van verschillende factoren. In de meeste gevallen duurt het een of twee dagen, maar het kan tot wel 30 dagen duren.
| Welke indeling heeft de uitvoer? | De uitvoer heeft de vorm van gestructureerde, door machine leesbare bestanden, zoals XML, CSV of JSON.
| Wie heeft toegang tot het hulpprogramma Gegevenslogboekexport om aanvragen voor door het systeem gegenereerde logboeken in te dienen? | Globale Office 365-beheerders hebben toegang tot het hulpprogramma AVG-logboekbeheer.
| Welke gegevens retourneert het hulpprogramma Gegevenslogboekexport? | Het hulpprogramma Gegevenslogboekexport retourneert door het systeem gegenereerde logboeken die door Microsoft worden opgeslagen. Geëxporteerde gegevens omvatten alle verschillende Microsoft-services zoals Office 365, Azure, Dynamics, PowerApps, Microsoft Flow en CDS for Apps.
| Hoe worden gegevens naar de gebruiker geretourneerd? |   Gegevens worden geëxporteerd naar de Azure-opslaglocatie van uw organisatie. Het is aan beheerders in uw organisatie om te bepalen hoe ze deze gegevens weergeven of retourneren aan gebruikers.
| Hoe zien gegevens in door het systeem gegenereerde logboeken eruit? |  Voorbeeld van een door het systeem gegenereerd logboekrecord in JSON-indeling: <br> [{ <br>"DateTime": "2017-04- 28T12:09:29-07:00",  <br> "AppName": "SharePoint", <br> "Action": "OpenFile", "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" <br>}]

> [!NOTE]
>  Voor beveiligings- en auditdoeleinden is het met sommige functies niet mogelijk om door het systeem gegenereerde logboeken te exporteren of te verwijderen. Dit is om de integriteit van persoonsgegevens te behouden.
>
>

## <a name="deleting-system-generated-logs-for-managed-tenants"></a>Door het systeem gegenereerde logboeken voor beheerde tenants verwijderen
Als u door het systeem gegenereerde logboeken wilt verwijderen die zijn verkregen via een toegangsaanvraag, moet u de gebruiker verwijderen uit de service en zijn of haar Azure Active Directory-account permanent verwijderen. Zie voor instructies over hoe u een gebruiker permanent verwijdert de sectie **Een gebruiker verwijderen** in de *documentatie Azure DSR AGV* die is te vinden in de [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/GDPRDSR). Het is belangrijk dat u weet dat het permanent verwijderen van een gebruikersaccount onomkeerbaar is als dit proces eenmaal is gestart.

Wanneer u een gebruikersaccount permanent verwijdert, worden de gegevens van de gebruiker binnen 30 dagen verwijderd uit door het systeem gegenereerde logboeken voor PowerApps-, Microsoft Flow- en CDS for Apps-services.


## <a name="accessing-and-exporting-system-generated-logs-for-unmanaged-tenants"></a>Door het systeem gegenereerde logboeken voor onbeheerde tenants openen en exporteren

Gebruikers hebben toegang tot door het systeem gegenereerde logboeken die zijn gekoppeld aan hun gebruik van PowerApps, Microsoft Flow en CDS for Apps-services en -toepassingen (Common Data Service).

U kunt door het systeem gegenereerde logboeken als volgt openen en exporteren:
1. Ga naar de [portal voor privacy op school en het werk](https://go.microsoft.com/fwlink/?linkid=873123).
1. Op de pagina **Mijn gegevensaanvragen** kan een gebruiker een gegevensexport aanvragen door op de knop **Nieuw exportverzoek** te klikken.
1. Wanneer u op deze knop klikt, wordt u gevraagd uw aanvraag te bevestigen. Klik op **Ja** om door te gaan.
1. Het kan tot 1 maand duren voordat nieuwe exportverzoeken zijn voltooid. Gedurende deze periode wordt de status **In uitvoering** weergegeven.
1. Zodra de aanvraag is voltooid, wordt de kolom **Datum voltooid** ingevuld en krijgt u een koppeling naar uw **door het systeem gegenereerde** logboeken.
1. Klik op deze koppeling om uw gegevens te downloaden. U kunt een teksteditor gebruiken om deze gegevens te bekijken.
1. Let er ook op dat de **vervaldatum** voor deze inhoud wordt ingevuld in de kolom Vervaldatum. U hebt tot en met dit moment de tijd om uw door het systeem gegenereerde logboeken op te halen.

De volgende tabel geeft een overzicht van hoe u door het systeem gegenereerde logboeken voor onbeheerde tenants opent en exporteert:

| Vraag | Antwoord |
| --- | --- |
| Hoelang duurt het voordat het Microsoft-hulpprogramma Gegevenslogboekexport een aanvraag heeft voltooid? |    Dit is afhankelijk van verschillende factoren. In de meeste gevallen duurt het een of twee dagen, maar het kan tot wel 30 dagen duren.
| Welke indeling heeft de uitvoer? | De uitvoer heeft de vorm van gestructureerde, door machine leesbare bestanden, zoals XML, CSV of JSON.
| Wie heeft toegang tot het hulpprogramma Gegevenslogboekexport om aanvragen voor door het systeem gegenereerde logboeken in te dienen? | Gebruikers die lid zijn van een onbeheerde tenant hebben toegang tot het indienen van aanvragen.
| Welke gegevens retourneert het hulpprogramma Gegevensexport? | Het hulpprogramma Gegevensexport retourneert door het systeem gegenereerde logboeken die door Microsoft worden opgeslagen. Geëxporteerde gegevens omvatten alle verschillende Microsoft-services zoals Office 365, Azure, Dynamics, PowerApps, Microsoft Flow en CDS for Apps.
| Hoe worden gegevens naar de gebruiker geretourneerd? |   Gegevens worden geëxporteerd naar een Microsoft-website waar de gebruiker die de aanvraag van een betrokkene heeft ingediend, een beveiligde koppeling krijgt.
| Hoe zien gegevens in door het systeem gegenereerde logboeken eruit? |  Voorbeeld van een door het systeem gegenereerd logboekrecord in JSON-indeling: <br> [{ <br>"DateTime": "2017-04- 28T12:09:29-07:00",  <br> "AppName": "SharePoint", <br> "Action": "OpenFile", "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" <br>}]

> [!NOTE]
>  Voor beveiligings- en auditdoeleinden is het met sommige functies niet mogelijk om door het systeem gegenereerde logboeken te exporteren of te verwijderen. Dit is om de integriteit van persoonsgegevens te behouden.
>
>

## <a name="deleting-system-generated-logs-for-unmanaged-tenants"></a>Door het systeem gegenereerde logboeken voor onbeheerde tenants verwijderen
Als u door het systeem gegenereerde logboeken wilt verwijderen die via een toegangsaanvraag zijn opgehaald, moet u uw account sluiten. Hiermee worden binnen dertig dagen al uw door het systeem gegenereerde logboeken en uw gegevens in PowerApps, Microsoft Flow en CDS voor Apps-services verwijderd.

U kunt door het systeem gegenereerde logboeken als volgt verwijderen:
1. Ga naar de [portal voor privacy op school en het werk](https://go.microsoft.com/fwlink/?linkid=873123).
1. Op de pagina **Mijn gegevensaanvragen** kunnen gebruikers een aanvraag indienen voor het verwijderen van hun gegevens door op de knop **Account sluiten** te klikken.
1. Wanneer u op deze knop klikt, wordt u gevraagd uw aanvraag te bevestigen. Klik op **Ja** om door te gaan.
1. Zodra het account is gesloten, hebt u geen toegang meer tot PowerApps, Microsoft Flow en CDS.

## <a name="determining-tenant-type"></a>Het tenanttype bepalen
Als u wilt bepalen of u een gebruiker van een beheerde of onbeheerde tenant bent, voert u de volgende acties uit:
1. Open de volgende URL in een browser en zorg ervoor dat u uw e-mailadres in de URL vervangt:[ https://login.windows.net/common/userrealm/name@contoso.com?api-version=2.1](https://login.windows.net/common/userrealm/name@contoso.com?api-version=2.1).

2. Als u lid bent van een **onbeheerde tenant**, ziet u een `"IsViral": true` in het antwoord.
  ```
      {
      ...
      "Login": "name@unmanagedcontoso.com",
      "DomainName": "unmanagedcontoso.com",
      "IsViral": **true**,
      ...
      }
  ```

3. Anders maakt u deel uit van een beheerde tenant.
