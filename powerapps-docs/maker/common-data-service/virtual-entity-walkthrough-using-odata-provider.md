---
title: Virtuele entiteitanalyse met de OData v4-gegevensprovider in Common Data Service voor Apps | MicrosoftDocs
description: Lees hoe u de OData v4-gegevensprovider kunt gebruiken met een virtuele entiteit
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
ms.assetid: null
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="virtual-entity-walkthrough-using-the-odata-v4-data-provider"></a>Virtuele entiteitanalyse met de OData v4-gegevensprovider

Stel dat u informatie over toegangstickets wilt vanuit een externe gegevensbron binnen uw modelgestuurde app of het gebied Service van Dynamics 365 for Customer Engagement. In deze eenvoudige analyse modelleert u een virtuele entiteit met velden die zijn toegewezen aan het externe schema dat ticketgegevens ophaalt tijdens uitvoeringstijd van een OData-webservice.

## <a name="data-source-details"></a>Details van gegevensbron

Aangezien de gegevensbron die voor dit overzicht wordt gebruikt een van OData v4-webservice heeft, kunnen we gebruikmaken van de OData 4-gegevensprovider die wordt meegeleverd met uw omgeving.

URL van webservice: `http://contosowebservice.azurewebsites.net/odata/` 

> [!IMPORTANT]
> De URL van de webservice voor dit overzicht is geen werkende webservice.

Voor dit overzicht is een enkele virtuele entiteit nodig die de volgende drie velden bevat.

|Naam van extern veld |Type externe gegevens |Gegevens voor virtuele entiteit |Doel |
|---------|---------|---------|---------|
|TicketID |`Edm.Guid` |Primaire sleutel |Primaire sleutel voor de entiteit |
|Titel  |`Edm.String` |Eén tekstregel |Titel van het ticket |
|Ernst |`Edm.Int32`| Geheel getal |Getalwaarde van 0-4 die de ernst van het ticket aangeeft |

De OData-metagegevens van de entiteit Ticket voor de externe gegevensbron:

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

## <a name="create-the-data-source"></a>De gegevensbron maken

Maak de gegevensbron voor de OData v4-serviceprovider die gebruikmaakt van de OData-voorbeeldwebservice (OASIS Open Data Protocol).

1. Ga naar **Instellingen** > **Beheer** > **Bronnen voor virtuele entiteitsgegevens**
1. Selecteer **NIEUW**, selecteer **OData v4-gegevensprovider** en selecteer vervolgens **OK**.
1. Voer de volgende informatie in of selecteer deze.

    |Veld|Waarde|
    |--|--|
    |**Name**|Contoso-voorbeeldgegevensbron|
    |**URL**|`http://contosowebservice.azurewebsites.net/odata` |
    |**Time-out**|30|
    |**Inline telling retourneren**|Waar|

Laat de andere velden ongewijzigd en selecteer **OPSLAAN EN SLUITEN**.

> [!TIP]
> Controleer bij gebruik van uw eigen webservice of de URL geldig is door deze in uw webbrowser plakken. 

## <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

Een deel van de naam van een aangepaste entiteit die u maakt is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel is wat u voor deze entiteit wilt. Meer informatie: [Het voorvoegsel voor de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="create-the-virtual-entity"></a>De virtuele entiteit maken

1. Selecteer in het linkernavigatiedeelvenster van de oplossingenverkenner de optie **Entiteiten** en selecteer vervolgens **Nieuw** in het hoofdvenster.
2. Selecteer in het formulier **Entiteit: Nieuw** de optie **Virtuele entiteit** en voer de volgende gegevens in: 

    |Veld|Waarde|
    |--|--|
    |**Gegevensbron**|Contoso-voorbeeldgegevensbron|
    |**Weergavenaam**|Ticket|
    |**Meervoudsnaam**|Tickets|
    |**Name**|new_ticket|
    |**Externe naam**|Ticket|
    |**Naam van externe verzameling**|Tickets|
    |**Notities (inclusief bijlagen)**|geselecteerd|
    |**Activiteiten**|geselecteerd|

1. Selecteer naast **Gebieden waarin deze entiteit wordt weergegeven** de optie **Service** en selecteer vervolgens **Opslaan** (maar sluit het entiteitenformulier niet).
    ![Definitie van entiteit Ticket](media/ticket-entity.png)

## <a name="create-the-fields-for-the-virtual-entity"></a>De velden voor de virtuele entiteit maken

Selecteer in het linkernavigatiedeelvenster van de pagina **Entiteit: Ticket** de optie **Velden**. Als onderdeel van dit overzicht gaat u twee bestaande velden bewerken en een derde veld toevoegen.

> [!IMPORTANT]
> Externe namen zijn hoofdlettergevoelig. Raadpleeg de metagegevens van de webservice om te controleren of u de juiste naam gebruikt.
> Een Nullable-waarde Onwaar geeft aan dat het kenmerk is vereist. Houd er rekening mee dat primaire sleutelvelden altijd door het systeem zijn vereist.

1. Open het veld **new_ticketid** en wijzig het volgende kenmerk met de hier weergegeven waarde: **External Name**: TicketID  ![TicketID field](media/ticketid-field.png)
1. Kies **Opslaan en sluiten**.
1. Open het veld **new_name** en wijzig het volgende kenmerken met de hier weergegeven waarden:
    - **Weergavenaam**: Titel
    - **Externe naam**: Titel ![Titelveld](media/title-field.png)
1. Kies **Opslaan en sluiten**.
1. Selecteer **Nieuw** en klik voer op de pagina **Veld: Nieuw voor Ticket** de volgende gegevens in:

    |Veld|Waarde|
    |--|--|
    |**Weergavenaam**|Ernst|
    |**Name**|new_severity|
    |**Externe naam**|Ernst|
    |**Veldvereiste**|Onderneming vereist|
    |**Type gegevens**|Geheel getal|
    |**Minimumwaarde**|0|
    |**Maximumwaarde**|4|

  ![Veld Ernst](media/severity-field.png)
1. Kies **Opslaan en sluiten**.

## <a name="add-the-fields-to-the-main-form"></a>Het veld toevoegen aan het hoofdformulier

1. Selecteer in het venster van de entiteit Ticket de optie **Formulieren**.
1. Open het hoofdformulier, sleep het veld **Ernst** van het rechterdeelvenster naar het formulier in de sectie **Algemeen** onder het veld **Titel**. 
    ![Veld Ernst toegevoegd aan hoofdformulier](media/drop-severity-field.png)
1. Selecteer in het venster van de entiteit Ticket de optie **Opslaan en sluiten**.

## <a name="configure-the-default-view"></a>De standaardweergave configureren

1. Selecteer in het linkerdeelvenster van de oplossingenverkenner onder **Ticketentiteit** de optie **Weergaven**.
1. Open de weergave **Alle tickets**.
1. Selecteer in het deelvenster **Algemene taken** de optie **Kolommen toevoegen**.
    ![Kolommen toevoegen voor weergave](media/addcolumns.png)
1. Selecteer **Ernst** en selecteer vervolgens **OK**.
1. Selecteer in het venster **Weergave: Alle tickets** de optie **Opslaan en sluiten**.
1. Selecteer in het venster van oplossingsverkenner de optie **Alle aanpassingen publiceren**.
    ![Alle aanpassingen publiceren](media/publishall.png)
1. Sluit het venster van de oplossingsverkenner nadat alle aanpassingen zijn gepubliceerd.

## <a name="view-the-virtual-entity-in-action-with-dynamics-365-customer-engagement"></a>De virtuele entiteit in actie zien met Dynamics 365 Customer Engagement

1. Ga naar **Service** > **Extensies** > **Tickets**.
    
    ![Ticketgebied](media/ticket-area.png)

    De weergave **Alle tickets** wordt geopend. Denk eraan dat u uw browser mogelijk moet vernieuwen om de entiteit weer te geven in het gebied **Service**.

    ![Weergave voor alle tickets](media/all-tickets-view.png)
1. Open een record **Ticket** om het formulier te bekijken dat de velden **Titel** en **Ernst** bevat voor de desbetreffende record.
    ![Ticketrecord](media/ticket-record.png)

### <a name="see-also"></a>Zie ook

[De configuratie, vereisten en aanbevolen methoden van de OData v4-gegevensprovider](virtual-entity-odata-provider-requirements.md)<br />
[Virtuele entiteiten maken en bewerken die gegevens uit een externe gegevensbron bevatten](create-edit-virtual-entities.md)
