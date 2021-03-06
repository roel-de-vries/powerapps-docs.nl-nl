---
title: Een PowerBI-rapport maken | Microsoft Docs
description: Maak vanuit PowerBI Desktop verbinding met uw gegevens via de connector Common Data Service voor Apps.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-power-bi-report"></a>Een Power BI-rapport maken
Met Common Data Service voor Apps kunt u met behulp van Power BI Desktop rechtstreeks verbinding maken met uw gegevens om rapporten te maken en deze te publiceren in Power BI. Vanuit Power BI kunnen rapporten worden gebruikt in dashboards, worden gedeeld met andere gebruikers en platformonafhankelijk worden geopend in mobiele Power BI-apps.

![Power BI Desktop](./media/data-platform-cds-powerbi-connector/PBIDesktop.png "Power BI Desktop")

## <a name="prerequisites"></a>Vereisten

Als u Power BI wilt gebruiken met Common Data Service voor Apps, hebt u het volgende nodig:

* Download en installeer Power BI Desktop. Dit is een gratis toepassing die wordt uitgevoerd op uw lokale computer. U kunt Power BI Desktop [hier](https://powerbi.microsoft.com/desktop/) downloaden.
* De omgeving van Common Data Service voor Apps met makermachtigingen voor toegang tot de portal en leesmachtigingen voor toegang tot gegevens in entiteiten.

## <a name="finding-your-common-data-service-for-apps-environment-url"></a>De URL voor de omgeving van Common Data Service voor Apps vinden

1. Open [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) en selecteer de omgeving waarmee u verbinding wilt maken. Klik op het **instellingentandwiel** in de rechterbovenhoek en klik op **Geavanceerde aanpassingen**.

    ![Omgeving van CDS voor Apps](./media/data-platform-cds-powerbi-connector/CDSEnv1.png "Omgeving van CDS voor Apps")

2. Klik op **Resources** in het gedeelte Ontwikkelaarsresources om een nieuw tabblad te openen.

    ![Omgeving van CDS voor Apps](./media/data-platform-cds-powerbi-connector/CDSEnv2.png "Omgeving van CDS voor Apps")

3. Kopieer de hoofdmap van de URL naar het nieuwe tabblad. Dit is de unieke URL voor uw omgeving. De URL heeft de indeling **https://yourenvironmentid.crm.dynamics.com/**. Kopieer de rest van de URL niet. Bewaar deze op een handige locatie, zodat u deze kunt gebruiken wanneer u uw PowerBI-rapport gaat maken.

    > [!div class="mx-imgBorder"] 
    > ![Omgeving van CDS voor Apps](./media/data-platform-cds-powerbi-connector/CDSEnv3.png "Omgeving van CDS voor Apps")

## <a name="connecting-to-common-data-service-for-apps-from-power-bi-desktop"></a>Verbinding met Common Data Service voor Apps maken vanuit Power BI Desktop

1. Start **Power BI Desktop**. Als dit de eerste keer is, wordt mogelijk een welkomstscherm weergegeven of wordt u direct naar een leeg canvas geleid. Hoe dan ook, klik op **Gegevens ophalen** en selecteer **Meer** om de volledige lijst met beschikbare gegevensbronnen voor Power BI Desktop te openen.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport1.png "Power BI Desktop")

2. Klik op **Onlineservices** en **Common Data Service voor Apps (bèta)** in de lijst met connectors. Klik op **Verbinding maken**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport2.png "Power BI Desktop")

3. Plak de **URL van de omgeving voor Common Data Service voor Apps** in het veld **Server-URL** en klik op **OK**. Als dit de eerste keer is, wordt u gevraagd om u aan te melden met dezelfde referenties die u ook gebruikt om verbinding te maken met PowerApps en Common Data Service voor Apps.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport3.png "Power BI Desktop")

4. In de navigator ziet u alle entiteiten die beschikbaar zijn voor uw omgeving gegroepeerd in drie mappen. Vouw de map **Common Data Model** uit.

    * Common Data Model: dit zijn standaardentiteiten die veel worden gebruikt en beschikbaar zijn in alle omgevingen als onderdeel van het Common Data Model.
    * Aangepaste entiteiten: dit zijn entiteiten die u hebt gemaakt of geïmporteerd in uw omgeving.
    * Systeem: bevat alle entiteiten in uw omgeving, inclusief de entiteiten Common Data Model en Aangepast.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport4.png "Power BI Desktop")

5. Selecteer de entiteit **Account** om in het rechterdeelvenster een voorbeeld van uw gegevens te zien en klik op **Laden**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport5.png "Power BI Desktop")

6. Uw entiteit wordt nu in het rapport geladen en u kunt beginnen met het maken van rapporten. U kunt dit proces ook herhalen om extra entiteiten toe te voegen.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport6.png "Power BI Desktop")

7. Klik op het veld **Naam** in het deelvenster Veld om een nieuwe visualisatie toe te voegen aan uw rapportcanvas. U kunt dit proces nu herhalen en visualisaties wijzigen om uw rapport te maken.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport7.png "Power BI Desktop")


## <a name="using-option-sets"></a>Optiesets gebruiken

Optiesets worden gebruikt in entiteiten om een gebruiker een vervolgkeuzelijst met waarden te bieden in apps en stromen. Wanneer u de Power BI-connector gebruikt, worden optiesetvelden weergegeven als twee kolommen om zowel de unieke waarde als de weergavewaarde te tonen.

Een voorbeeld: als u een optieset voor uw entiteit hebt met de naam ApprovalStatus, ziet u twee velden in Power BI:

* ApprovalStatus: hier wordt een uniek geheel getal weergegeven voor elk item in de optieset. Dit is handig wanneer u filters toepast zodat toekomstige wijzigingen in de weergavenaam hierop geen invloed hebben.
* ApprovalStatus_display: hier wordt de beschrijvende weergavenaam van het item weergegeven. Dit veld wordt doorgaans gebruikt bij het weergeven van de optie in een tabel of diagram.

    |ApproalStatus|ApprovalStatus_Display|
    |---------|---------|
    1|Verzonden
    2|Wordt geëvalueerd
    3|Goedgekeurd
    4|Afgewezen

## <a name="navigating-relationships"></a>Door relaties navigeren

Voor relaties in Common Data Service voor Apps moet u in PowerBI Desktop een relatie tussen de twee entiteiten instellen in een GUID-veld. Dit is een door het systeem gegenereerde unieke id die ervoor zorgt dat er relaties worden gemaakt voor de te maken records waarbij mogelijk dubbelzinnigheid of duplicatie met andere velden bestaat. Meer informatie over het beheren van relaties in Power BI Desktop vindt u [hier](https://docs.microsoft.com/power-bi/desktop-create-and-manage-relationships).

Hoewel sommige relaties automatisch kunnen worden gemaakt, kunt u nog steeds controleren of de juiste relaties tot stand worden gebracht wanneer u uw rapport maakt:

* Het zoekveld voor de entiteit bevat de GUID van de record in de gerelateerde entiteit.
* De gerelateerde entiteit heeft een veld met de indeling '[[EntityName]]id' die de GUID bevat, bijvoorbeeld Accountid of MyCustomEntityid
* Met de functie Relaties beheren van PowerBI Desktop maakt u een nieuwe relatie tussen uw zoekveld en het id-veld van de gerelateerde entiteit.


## <a name="next-steps"></a>Volgende stappen
* [Velden in een entiteit beheren](data-platform-manage-fields.md)
* [Relaties tussen entiteiten definiëren](data-platform-entity-lookup.md)


