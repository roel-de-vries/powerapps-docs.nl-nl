---
title: Lijsten instellen voor integratie van SharePoint Online met PowerApps, Microsoft Flow en Power BI | Microsoft Docs
description: In deze taak gaan we SharePoint-lijsten instellen om te gebruiken als gegevensbron voor apps, stromen, rapporten en dashboards.
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/19/2017
ms.author: mblythe
ms.openlocfilehash: ad9033b51142d1bb6b014abe0cc049a0b5c27ee5
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="set-up-lists-for-sharepoint-online-integration-with-powerapps-microsoft-flow-and-power-bi"></a>Lijsten instellen voor integratie van SharePoint Online met PowerApps, Microsoft Flow en Power BI
> [!NOTE]
> Dit artikel maakt deel uit van een reeks zelfstudies over het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint Online. Lees de [inleiding tot de reeks](sharepoint-scenario-intro.md) zodat u een idee van het geheel krijgt en van de betreffende downloads.

SharePoint bevat talloze functies voor delen en samenwerken, maar we richten ons in dit scenario op één functie: [SharePoint-lijsten](https://support.office.com/article/Introduction-to-lists-0A1C3ACE-DEF0-44AF-B225-CFA8D92C52D7). Een lijst is slechts een verzameling gegevens die u kunt delen met teamleden en andere sitegebruikers. De lijsten worden gecontroleerd voor dit scenario, waarna u ze in uw eigen SharePoint Online-site kunt maken.

## <a name="step-1-understand-the-lists"></a>Stap 1: Inzicht in de lijsten
De eerste lijst is **Projectaanvragen**. Hier voegt een projectaanvrager een aanvraag toe. De projectfiatteur beoordeelt vervolgens de aanvraag en keurt deze goed of af.

| **Lijstkolom** | **Gegevenstype** | **Opmerkingen** |
| --- | --- | --- |
| Title |Eén tekstregel |Standaardkolom, gebruikt voor projectnaam |
| Beschrijving |Eén tekstregel | |
| ProjectType |Eén tekstregel |Waarden: nieuwe hardware, bijgewerkte hardware, nieuwe software, bijgewerkte software |
| RequestDate |Date | |
| Requestor |Eén tekstregel | |
| EstimatedDays |Getal |Maakt vergelijking mogelijk tussen de schatting van de aanvrager, de schatting van de projectmanager en de werkelijke schatting |
| Approved |Eén tekstregel |Waarden: in wachtrij, ja, nee |

> [!NOTE]
> We gebruiken de kolom **Id**, die wordt gegenereerd door SharePoint en standaard is verborgen. We gebruiken voor het gemak eenvoudige gegevenstypen, maar een echte app kan gebruikmaken van complexere typen, zoals **Persoon of groep** voor de kolom **Requestor**. Zie [Verbinding maken met SharePoint vanuit Microsoft PowerApps](connections/connection-sharepoint-online.md#known-issues) voor informatie over gegevenstypen die door PowerApps worden ondersteund.

De tweede lijst is **Projectdetails**. Hierin worden de details gevolgd voor alle goedgekeurde projecten, bijvoorbeeld welke projectmanager wordt toegewezen.

| **Lijstkolom** | **Gegevenstype** | **Opmerkingen** |
| --- | --- | --- |
| Title |Eén tekstregel |Standaardkolom, gebruikt voor projectnaam |
| RequestID |Getal |Komt overeen met de waarde in de lijst **Projectaanvragen**, kolom **Id** |
| ApprovedDate |Date | |
| Status |Eén tekstregel |Waarden: niet gestart, wordt verwerkt, voltooid |
| ProjectedStartDate |Date |De door de projectmanager geschatte begindatum van het project |
| ProjectedEndDate |Datum |De door de projectmanager geschatte einddatum van het project |
| ProjectedDays |Getal |Werkdagen; gewoonlijk berekend, maar komt in dit scenario niet voor |
| ActualDays |Getal |Voor voltooide projecten |
| PMAssigned |Eén tekstregel |Projectmanager |

## <a name="step-2-create-and-review-the-lists"></a>Stap 2: Lijsten maken en beoordelen
Als u wilt doorgaan met het scenario, moet u de twee SharePoint-lijsten maken en vullen met de voorbeeldgegevens. We laten zien hoe u dit doet door de lijst te maken en er voorbeeldgegevens in te plakken. Zorg ervoor dat u de Excel-bestanden uit het [downloadpakket](https://aka.ms/o4ia0f) hebt.

> [!NOTE]
> Gebruik Internet Explorer voor deze stap.

### <a name="create-the-lists"></a>De lijsten maken

1. Klik of tik in Internet Explorer, in de SharePoint-site, op **Nieuw** en vervolgens op **Lijst**.
   
    ![Nieuwe SharePoint-lijst maken](./media/sharepoint-scenario-setup/01-01-01-new-list.png)

2. Voer de naam Projectaanvragen in en klik of tik op **Maken**.
   
    ![Naam opgeven voor nieuwe lijst](./media/sharepoint-scenario-setup/01-01-02-create-list.png)
   
    De lijst **Projectaanvragen** wordt gemaakt, met het standaardveld **Title**.
   
    ![Lijst Projectaanvragen](./media/sharepoint-scenario-setup/01-01-03-initial-list.png)

### <a name="add-columns-to-the-list"></a>Kolommen aan de lijst toevoegen

1. Klik of tik op ![Pictogram Nieuw item](./media/sharepoint-scenario-setup/icon-new.png) en vervolgens op **Eén tekstregel**.
   
    ![Veld Eén tekstregel](./media/sharepoint-scenario-setup/01-01-04-add-column.png)

2. Voer de naam Beschrijving in en klik of tik op **Opslaan**.
   
3. Herhaal stap **1** en **2** voor de andere kolommen in de lijst:
   
   1. **Eén tekstregel** > 'ProjectType'
   2. **Datum** > 'RequestDate'
   3. **Eén tekstregel** > 'Requestor'
   4. **Getal** > 'EstimatedDays'
   5. **Eén tekstregel** > 'Approved'

### <a name="copy-data-into-the-list"></a>Gegevens in de lijst kopiëren
1. Klik of tik op **Snel bewerken**.
   
    ![Snel bewerken voor lijst](./media/sharepoint-scenario-setup/01-01-06-quick-edit.png)
2. Selecteer de cellen in het raster.
   
    ![Lijst met alle kolommen](./media/sharepoint-scenario-setup/01-01-07-empty-grid.png)
3. Open de werkmap project-requests.xlsx en selecteer alle gegevens (niet de koppen).
   
    ![Excel-tabel Projectaanvragen](./media/sharepoint-scenario-setup/01-01-08-excel-table.png)
4. Kopieer de gegevens en plak ze in het raster in SharePoint. Klik of tik vervolgens op **Gereed**.
   
    ![Voltooide lijst met gegevens](./media/sharepoint-scenario-setup/01-01-09-full-grid.png)
5. Voer het proces van het maken en kopiëren nogmaals uit voor de lijst Projectdetails met behulp van de werkmap project-details.xlsx. Raadpleeg de tabel Projectdetails in [Stap 1: Inzicht in de lijsten](#step-1-understand-the-lists) voor de kolomnamen en gegevenstypen.

## <a name="step-3-update-connections-to-samples---optional"></a>Stap 3: Verbindingen met voorbeelden bijwerken (optioneel)
Zoals in de inleiding tot deze reeks zelfstudies al is vermeld, zijn er twee voorbeeld-apps en een rapport in het [downloadpakket](https://aka.ms/o4ia0f) opgenomen. U kunt dit scenario voltooien zonder deze voorbeelden, maar als u de voorbeelden wilt gebruiken, moet u de verbindingen met de SharePoint-lijsten bijwerken. U werkt ze bij zodat ze gebruikmaken van *uw* lijsten als gegevensbron en niet die van ons.

### <a name="update-connections-for-the-sample-apps"></a>Verbindingen voor de voorbeeld-apps bijwerken

1. In [PowerApps Studio](https://create.powerapps.com/studio/) klikt of tikt u op **Openen** in het linkerdeelvenster. 

2. Klik of tik op **Bladeren** en open vervolgens het bestand **project-management-app.msapp** dat u hebt gedownload.

3. Klik of tik op **Toestaan**, zodat PowerApps van SharePoint gebruik kan maken.

4. Klik of tik op het lint, op het tabblad **Weergeven**, op **Gegevensbronnen**.

    ![PowerApps-gegevensbronnen](./media/sharepoint-scenario-setup/01-03-01-data-sources.png)
5. Klik of tik in het deelvenster **Gegevens** op het beletselteken (**...**) naast **Projectdetails** en vervolgens op **Verwijderen**.
   
    ![Gegevensbron Projectdetails verwijderen](./media/sharepoint-scenario-setup/01-03-02-remove.png)
6. Klik of tik op **Gegevensbron toevoegen**.
   
    ![Gegevensbron toevoegen](./media/sharepoint-scenario-setup/01-03-03-add.png)

7. We laten u twee manieren zien om verbinding te maken met de lijst, afhankelijk van of PowerApps al een SharePoint-verbinding voor u tot stand heeft gebracht. 

    * Als u al een SharePoint-verbinding ziet, klikt of tikt u op die verbinding.

        ![Bestaande verbinding](./media/sharepoint-scenario-setup/01-03-03aa-existing-connection.png)

    * Als u geen SharePoint-verbinding ziet, klikt of tikt u op **Nieuwe verbinding**.

        ![Nieuwe verbinding](./media/sharepoint-scenario-setup/01-03-03a-new-connection.png)

        Klik of tik vervolgens op **SharePoint**,en klik of tik op **Maken**.
   
        ![SharePoint-verbinding](./media/sharepoint-scenario-setup/01-03-03b-sharepoint.png)

8. Voer de URL in voor de SharePoint Online-site met de lijsten die u hebt gemaakt en klik of tik op **Start**.
   
    ![SharePoint-URL](./media/sharepoint-scenario-setup/01-03-03c-sharepoint-url.png)
9. Selecteer de lijst **Projectdetails** en klik of tik op **Verbinding maken**.
   
    ![Lijst Projectdetails](./media/sharepoint-scenario-setup/01-03-03d-project-details.png)
   
    In het deelvenster **Gegevens** ziet u nu de verbinding die u hebt gemaakt.
   
    ![Gegevensbronnen](./media/sharepoint-scenario-setup/01-03-03e-data-sources.png)

10. Klik of tik op het beletselteken (**...**) naast **Projectdetails** en vervolgens op **Vernieuwen**.
    
    ![Gegevensbron Projectdetails vernieuwen](./media/sharepoint-scenario-setup/01-03-02-remove.png)

11. Klik op ![Pictogram App uitvoeren](./media/sharepoint-scenario-setup/icon-run-arrow.png) in de rechter bovenhoek om de app uit te voeren en controleer of de verbinding naar behoren werkt.

12. Klik of tik op **Bestand** en sla vervolgens de app op in de cloud. 

12. Herhaal de stappen in deze sectie voor **project-requests-app.msapp** met behulp van de lijst **Projectaanvragen**.

### <a name="update-connections-for-the-sample-report"></a>Verbindingen voor het voorbeeldrapport bijwerken
1. Open **project-analysis.pbix** in Power BI Desktop.

2. Klik of tik op het lint, op het tabblad **Start**, op **Query's bewerken** en vervolgens op **Instellingen voor gegevensbron**.
   
    ![Query's bewerken](./media/sharepoint-scenario-setup/01-03-04-edit-queries.png)

3. Klik of tik op **Bron wijzigen**.
   
    ![Instellingen voor gegevensbron](./media/sharepoint-scenario-setup/01-03-05-settings.png)

4. Voer de URL in voor uw SharePoint Online-site, klik of tik op **OK** en vervolgens op **Sluiten**.
   
    ![URL voor SharePoint-lijst](./media/sharepoint-scenario-setup/01-03-06-list-url.png)

5. Power BI Desktop geeft onder het lint een banner weer, dus u kunt wijzigingen aanbrengen en gegevens uit de nieuwe bron halen. Klik of tik op **Wijzigingen toepassen**.
   
    ![Wijzigingen aan query's toepassen](./media/sharepoint-scenario-setup/01-03-07-apply.png)

6. Meld u aan met een Microsoft-account (het account dat u hebt gebruikt voor toegang tot SharePoint Online) en klik of tik op **Verbinding maken**.
   
    ![Verbinding maken met SharePoint Online](./media/sharepoint-scenario-setup/01-03-08-connect.png)

## <a name="next-steps"></a>Volgende stappen
De volgende stap in deze zelfstudie bestaat uit het [genereren van een app om projectaanvragen te behandelen](sharepoint-scenario-generate-app.md).

