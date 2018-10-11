---
title: Overzicht van virtuele entiteiten met de OData-gegevensprovider in Common Data Service voor apps | MicrosoftDocs
description: Informatie over het gebruik van de OData v4-gegevensprovider met een virtuele entiteit
ms.custom: ''
ms.date: 06/04/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: ''
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: ebdd8f80aad2d353d017626b7c403da93803c19b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675412"
---
# <a name="virtual-entity-walkthrough-using-the-odata-v4-data-provider"></a>Overzicht van virtuele entiteiten met de OData v4-gegevensprovider

Stel dat u toegang wilt tot ticketinformatie van een externe gegevensbron binnen uw modelgestuurde app of het servicegebied van Dynamics 365 for Customer Engagement. In dit eenvoudige scenario modelleert u een virtuele entiteit met velden die zijn toegewezen aan het externe schema dat kaartgegevens van een OData-webservice ophaalt tijdens runtime.

## <a name="data-source-details"></a>Details van gegevensbron

Omdat de gegevensbron die voor dit scenario wordt gebruikt een OData v4-webservice heeft, kunnen we de OData v4-gegevensprovider gebruiken die bij uw omgeving is geleverd.

URL webservice: `http://contosowebservice.azurewebsites.net/odata/` 

> [!IMPORTANT]
> De URL van de webservice die voor dit scenario wordt gebruikt, is geen functionerende webservice.

Voor dit scenario hebben we een enkele virtuele entiteit met de volgende drie velden nodig.

|Externe veldnaam |Extern gegevenstype |Gegevenstype virtuele entiteit |Doel |
|---------|---------|---------|---------|
|TicketID |`Edm.Guid` |Primaire sleutel |Primaire sleutel voor de entiteit |
|Title  |`Edm.String` |Eén tekstregel |Titel van het ticket |
|Ernst |`Edm.Int32`| Geheel getal |Numerieke waarde van 0 tot 4 die de ernst van het ticket aangeeft |

De OData-metagegevens van de externe brongegevens van de ticketentiteit:

```xml
<EntityType Name="Ticket">
  <Key>
    <PropertyRef Name="TicketID" />
  </Key>
  <Property Name="TicketID" Nullable="false" Type="Edm.Guid" />
  <Property Name="Title" Type="Edm.String" />
  <Property Name="Severity" Nullable="false" Type="Edm.Int32" />
</EntityType>
```

## <a name="create-the-data-source"></a>Gegevensbron maken

Maak de gegevensbron voor de OData v4-gegevensprovider die gebruikmaakt van de OASIS OData-voorbeeldwebservice (Open Data Protocol).

1. Ga naar **Instellingen** > **Beheer** > **Gegevensbronnen voor virtuele entiteit**.
1. Selecteer **NIEUW**, selecteer **OData v4-gegevensprovider** en selecteer vervolgens **OK**.
1. Typ of selecteer de volgende informatie.

    |Veld|Waarde|
    |--|--|
    |**Naam**|Contoso-voorbeeldgegevensbron|
    |**URL**|`http://contosowebservice.azurewebsites.net/odata` |
    |**Time-out**|30|
    |**Inline aantal retourneren**|Waar|

Laat de andere velden zoals ze zijn en selecteer **OPSLAAN EN SLUITEN**.

> [!TIP]
> Wanneer u uw eigen webservice gebruikt, moet u controleren of de URL geldig is door deze in uw webbrowser te plakken. 

## <a name="open-solution-explorer"></a>Solution Explorer openen

Een deel van de naam van elke aangepaste entiteit die u maakt, is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de uitgever van de oplossing waarin u werkt. Als u geïnteresseerd bent in het aanpassingsvoorvoegsel, moet u ervoor zorgen dat u in een niet-beheerde oplossing werkt waarbij het aanpassingsvoorvoegsel het voorvoegsel is dat u voor deze entiteit wilt gebruiken. Meer informatie: [Het publicatievoorvoegsel van de oplossing wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="create-the-virtual-entity"></a>De virtuele entiteit maken

1. Selecteer in het linkernavigatiedeelvenster van Solution Explorer de optie **Entiteiten** en selecteer tenslotte **Nieuw** in het hoofddeelvenster.
2. Selecteer in het formulier **Entiteit: nieuw** de optie **Virtuele entiteit** en geef de volgende informatie op: 

    |Veld|Waarde|
    |--|--|
    |**Gegevensbron**|Contoso-voorbeeldgegevensbron|
    |**Weergavenaam**|Ticket|
    |**Naam in meervoud**|Tickets|
    |**Naam**|new_ticket|
    |**Externe naam**|Ticket|
    |**Naam van externe verzameling**|Tickets|
    |**Opmerkingen (inclusief bijlagen)**|geselecteerd|
    |**Activiteiten**|geselecteerd|

1. Selecteer naast **Gebieden waarin deze entiteit wordt weergegeven** de optie **Service** en selecteer vervolgens **Opslaan** (maar sluit het entiteitsformulier niet).
    ![Definitie van ticketentiteit](media/ticket-entity.png)

## <a name="create-the-fields-for-the-virtual-entity"></a>De velden voor de virtuele entiteit maken

Selecteer in het linkernavigatievenster van de pagina **Entiteit: ticket** de optie **Velden**. Als onderdeel van dit scenario bewerkt u twee bestaande velden en voegt u een derde veld toe.

> [!IMPORTANT]
> Externe namen zijn hoofdlettergevoelig. Raadpleeg de metagegevens van de webservice om ervoor te zorgen dat u de juiste naam gebruikt.
> Een nullable-waarde Onwaar geeft aan dat het kenmerk vereist is. Merk op dat primaire-sleutelvelden altijd door het systeem worden vereist.

1. Open het veld **new_ticketid** en wijzig het volgende kenmerk met de hier aangegeven waarde: **Externe naam**: TicketID ![Veld TicketID](media/ticketid-field.png)
1. Selecteer **Opslaan en sluiten**.
1. Open het veld **new_name** en wijzig de waarden van de volgende kenmerken in de hier aangegeven waarden:
    - **Weergavenaam**: Titel
    - **Externe naam**: Titel ![Veld Titel](media/title-field.png)
1. Selecteer **Opslaan en sluiten**.
1. Selecteer **Nieuw** en voer op de pagina **Veld: Nieuw voor ticket** de volgende informatie in:

    |Veld|Waarde|
    |--|--|
    |**Weergavenaam**|Ernst|
    |**Naam**|new_severity|
    |**Externe naam**|Ernst|
    |**Veldvereiste**|Onderneming vereist|
    |**Gegevenstype**|Geheel getal|
    |**Minimumwaarde**|0|
    |**Maximumwaarde**|4|

  ![Veld Ernst](media/severity-field.png)
1. Selecteer **Opslaan en sluiten**.

## <a name="add-the-fields-to-the-main-form"></a>De velden toevoegen aan het hoofdformulier

1. Selecteer in het venster van de ticketentiteit **Formulieren**.
1. Open het hoofdformulier, sleep het veld **Ernst** van het rechterdeelvenster naar het gedeelte **Algemeen** onder het veld **Titel** in het formulier. 
    ![Veld Ernst toegevoegd aan het hoofdformulier](media/drop-severity-field.png)
1. Selecteer in het venster van de ticketentiteit **Opslaan en sluiten**.

## <a name="configure-the-default-view"></a>De standaardweergave configureren

1. Selecteer in het linkerdeelvenster van de Solution Explorer onder de **Ticketentiteit** de optie **Weergaven**.
1. Open de weergave **Alle tickets**.
1. Selecteer in het deelvenster **Algemene taken** de optie **Kolommen toevoegen**.
    ![Kolommen voor weergave toevoegen](media/addcolumns.png)
1. Selecteer **Ernst** en selecteer vervolgens **OK**.
1. Selecteer in het venster **Weergave: alle tickets** de optie **Opslaan en sluiten**.
1. Selecteer in het venster Solution Explorer **Alle aanpassingen publiceren**.
    ![Alle aanpassingen publiceren](media/publishall.png)
1. Nadat alle aanpassingen zijn gepubliceerd, sluit u het venster Solution Explorer.

## <a name="view-the-virtual-entity-in-action-with-dynamics-365-customer-engagement"></a>De virtuele entiteit in actie zien met Dynamics 365 Customer Engagement

1. Ga naar **Service** > **Extensies** > **Tickets**.
    
    ![Ticketgebied](media/ticket-area.png)

    De weergave **Alle tickets** wordt weergegeven. U moet mogelijk uw browser vernieuwen om de entiteit in het gedeelte **Service** te zien.

    ![Weergave Alle tickets](media/all-tickets-view.png)
1. Open een **Ticket**record om het formulier te bekijken dat de velden **Titel** en **Ernst** voor de betreffende record bevat.
    ![Ticketrecord](media/ticket-record.png)

### <a name="see-also"></a>Zie ook

[Configuratie, vereisten en aanbevolen procedures voor OData v4-gegevensprovider](virtual-entity-odata-provider-requirements.md)<br />
[Virtuele entiteiten maken en bewerken die gegevens uit een externe gegevensbron bevatten](create-edit-virtual-entities.md)
