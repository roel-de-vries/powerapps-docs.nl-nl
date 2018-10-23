---
title: Prestaties van canvas-apps optimaliseren | Microsoft Docs
description: Volg de aanbevolen procedures in dit onderwerp om de prestaties van canvas-apps die u in PowerApps maakt te verbeteren.
author: yingchin
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/31/2018
ms.author: yingchin
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0fa6a8f741ed0e771eeefbbee82a23e876363e55
ms.sourcegitcommit: 469be99b762cd62289a98f058c498ac25ff8801b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44327709"
---
# <a name="optimize-canvas-app-performance-in-powerapps"></a>Prestaties van canvas-apps optimaliseren in PowerApps
Microsoft werkt hard aan het verbeteren van de prestaties van alle apps die worden uitgevoerd op het PowerApps-platform. Maar u kunt de aanbevolen procedures in dit onderwerp volgen om de prestaties te verbeteren van apps die u maakt.

Wanneer een gebruiker een app opent, doorloopt de app de volgende uitvoeringsfasen voordat de gebruikersinterface wordt weergegeven: 
1. **De gebruiker wordt geverifieerd**: vraagt de gebruiker, als die persoon de app nog niet eerder heeft geopend, zich aan te melden met referenties voor de verbindingen die de app nodig heeft. Als dezelfde gebruiker de app opnieuw opent, wordt die persoon mogelijk opnieuw gevraagd om aan te melden, afhankelijk van het beveiligingsbeleid van de organisatie. 
2. **Metagegevens worden opgehaald**: er worden metagegevens opgehaald, zoals de versie van het PowerApps-platform waarop de app wordt uitgevoerd en de bronnen waaruit gegevens moeten worden opgehaald. 
3. **De app wordt geinitialiseerd**: alle taken die zijn opgegeven in de eigenschap **OnStart** worden uitgevoerd. 
4. **Schermen worden weergegeven**: het eerste scherm wordt weergegeven met besturingselementen die de app heeft gevuld met gegevens. Als de gebruiker andere schermen opent, worden deze door de app weergegeven met behulp van hetzelfde proces.  

## <a name="limit-data-connections"></a>Gegevensverbindingen beperken 
**Maak niet verbinding met meer dan 30 gegevensbronnen van dezelfde app**. Apps vragen nieuwe gebruikers om zich aan te melden bij elke connector. Elke extra connector vergroot daarmee de hoeveelheid tijd die de app nodig heeft om te starten. Als een app wordt uitgevoerd, vereist elke connector CPU-resources, geheugen en netwerkbandbreedte wanneer de app gegevens van die bron aanvraagt. 

U kunt de prestaties van uw app snel meten door Ontwikkelhulpprogramma's in te schakelen in [Microsoft Edge](https://docs.microsoft.com/microsoft-edge/devtools-guide/network) of [Google Chrome](https://developers.google.com/web/tools/chrome-devtools/network-performance/) tijdens het uitvoeren van de app. Het kan langer dan 15 seconden duren voordat uw app gegevens retourneert als deze app regelmatig gegevens opvraagt bij meer dan 30 gegevensbronnen, zoals Common Data Service voor apps, Azure SQL, SharePoint en Excel in OneDrive.  

## <a name="limit-the-number-of-controls"></a>Het aantal besturingselementen beperken 
**Voeg niet meer dan 500 besturingselementen toe aan dezelfde app**. PowerApps genereert een HTML-DOM om elk besturingselement te renderen. Hoe meer besturingselementen u toevoegt, hoe meer generatietijd PowerApps nodig heeft. 

Soms kunt u hetzelfde resultaat bereiken en de app sneller laten starten als u een galerie gebruikt in plaats van afzonderlijke besturingselementen. Bovendien kunt u minder besturingselementen op hetzelfde scherm weergeven. Sommige besturingselementen (zoals PDF-viewer, gegevenstabel en keuzelijst met invoervak) halen grote uitvoeringsscripts binnen en hebben meer tijd nodig voor renderen. 

## <a name="optimize-the-onstart-function"></a>De functie OnStart optimaliseren
Gebruik de functie [**ClearCollect**](functions/function-clear-collect-clearcollect.md) om gegevens in de lokale cache te plaatsen als deze niet wijzigt tijdens de sessie van de gebruiker. Gebruik ook de functie [**Gelijktijdige**](functions/function-concurrent.md) om gegevensbronnen tegelijkertijd te laden.

Zoals u in [dit naslagonderwerp](functions/function-concurrent.md) kunt lezen, kunt u **Gelijktijdig** gebruiken om de hoeveelheid tijd die een app nodig heeft om gegevens te laden te halveren.

Zonder de functie **Gelijktijdig** laadt deze formule elk van de vier tabellen een voor een:

    ClearCollect( Product, '[SalesLT].[Product]' );
    ClearCollect( Customer, '[SalesLT].[Customer]' );
    ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' );
    ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' )

U kunt dit gedrag bevestigen in de Ontwikkelhulpprogramma's voor uw browser:

![Seriële ClearCollect](./media/performance-tips/perfconcurrent1.png)
    
U kunt dezelfde formule insluiten in de functie **Gelijktijdig** om de totale tijd die de bewerking nodig heeft, te verlagen:

    Concurrent( 
        ClearCollect( Product, '[SalesLT].[Product]' );
        ClearCollect( Customer, '[SalesLT].[Customer]' );
        ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' );
        ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' ))
        
Met deze wijziging haalt de app de tabellen parallel op: 

![Parallele ClearCollect](./media/performance-tips/perfconcurrent2.png)  

## <a name="cache-lookup-data"></a>Opzoekgegevens in de cache plaatsen
Gebruik de functie **Instellen** om gegevens van opzoektabellen in de lokale cache te plaatsen om te voorkomen dat herhaaldelijk gegevens uit de bron worden opgehaald. Deze techniek optimaliseert de prestatie als de gegevens waarschijnlijk niet wijzigen tijdens een sessie. Zoals in dit voorbeeld worden de gegevens eenmaal uit de bron opgehaald. Daarna wordt er lokaal naar verwezen totdat de gebruiker de app sluit. 

    Set(CustomerOrder, Lookup(Order, id = “123-45-6789”));
    Set(CustomerName, CustomerOrder.Name);
    Set(CustomerAddress, CustomerOrder.Address);
    Set(CustomerEmail, CustomerOrder.Email);
    Set(CustomerPhone, CustomerOrder.Phone);

Contactgegevens veranderen niet regelmatig, net als standaardwaarden en gebruikersinformatie. U kunt deze techniek dus in het algemeen ook gebruiken met de functies **Standaard** en **Gebruiker**. 

## <a name="avoid-controls-dependency-between-screens"></a>Afhankelijkheid van besturingselementen tussen schermen voorkomen
Als de waarde van een besturingselement afhankelijk is van de waarde van een besturingselement in een ander scherm, beheert u de gegevens met behulp van een variabele, een verzameling of een verwijzing van de gegevensbron.

## <a name="use-global-variables"></a>Globale variabelen gebruiken
Om de app-status door te geven van het ene scherm naar het andere, maakt of wijzigt u een globale variabele door de functie [**Instellen**](functions/function-set.md) te gebruiken in plaats van de functies **Navigeren** en **UpdateContext** te gebruiken.

## <a name="use-delegation"></a>Delegering gebruiken
Gebruik waar mogelijk functies die gegevensverwerking delegeren naar de gegevensbron in plaats van gegevens op te halen naar het lokale apparaat voor verwerking. Als een app gegevens lokaal moet verwerken, vereist de bewerking veel meer verwerkingskracht, geheugen en netwerkbandbreedte, met name als de gegevensset groot is.

Zoals u in [deze lijst](delegation-list.md) ziet, ondersteunen verschillende gegevensbronnen delegering van verschillende functies:

![Delegering gebruiken](./media/performance-tips/perfdelegation1.png)

SharePoint-lijsten bieden bijvoorbeeld ondersteuning voor delegering van de functie [**Filteren**](functions/function-filter-lookup.md), maar niet de functie [**Zoeken**](functions/function-filter-lookup.md). Daarom moet u **Filteren** gebruiken in plaats van **Zoeken** om items in een galerie te vinden als de SharePoint-lijst meer dan 500 items bevat. Zie voor meer tips [Werken met grote SharePoint-lijsten in PowerApps](https://powerapps.microsoft.com/blog/powerapps-now-supports-working-with-more-than-256-items-in-sharepoint-lists/) (blogbericht). 

## <a name="use-delayed-load"></a>Uitgestelde belasting gebruiken
Schakel de [experimentele functie](working-with-experimental.md) voor Uitgestelde belasting in als uw app meer dan tien schermen, geen regels en veel besturingselementen heeft die op meerdere schermen staan en die rechtstreeks zijn gekoppeld aan de gegevensbron. Als u dit type app bouwt en deze functie niet inschakelt, kan dat tot slechtere app-prestaties leiden. De besturingselementen in alle schermen moeten namelijk worden gevuld, zelfs op schermen die niet zijn geopend. Alle schermen van de app moeten ook worden bijgewerkt wanneer de gegevensbron wijzigt, zoals wanneer de gebruiker een record toevoegt.

## <a name="working-with-large-data-sets"></a>Werken met grote gegevenssets
Gebruik gegevensbronnen en formules die kunnen worden gedelegeerd om ervoor te zorgen dat uw apps goed blijven werken terwijl gebruikers toegang hebben tot alle gegevens die ze nodig hebben. Zo voorkomt u ook dat u de gegevensrijlimiet van 2000 bereikt voor niet-delegeerbare query's. In het geval van kolommen met gegevensrecords waarin gebruikers gegevens kunnen zoeken, filteren of sorteren, zijn deze indexen met kolommen goed ontworpen zoals in deze docs voor [SQL Server](https://docs.microsoft.com/sql/relational-databases/sql-server-index-design-guide?view=sql-server-2017) en [SharePoint](https://support.office.com/article/Add-an-index-to-a-SharePoint-column-f3f00554-b7dc-44d1-a2ed-d477eac463b0) wordt beschreven.  

## <a name="republish-apps-regularly"></a>Apps regelmatig opnieuw publiceren
[Publiceer uw apps opnieuw](https://powerapps.microsoft.com/blog/republish-your-apps-to-get-performance-improvements-and-additional-features/) (blogbericht) om verbeterde prestaties te krijgen en extra functies van het PowerApps-platform.
