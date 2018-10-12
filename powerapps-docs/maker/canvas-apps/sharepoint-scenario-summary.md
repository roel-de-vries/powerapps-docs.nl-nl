---
title: Totaaloverzicht van het SharePoint Online-integratiescenario | Microsoft Docs
description: Loop van begin tot eind het scenario door dat we in deze reeks zelfstudies hebben gebouwd.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/12/2017
ms.author: mblythe
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: df3c186bb41621e7ec6087a9da55fc037e286b1a
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850185"
---
# <a name="walk-end-to-end-through-the-completed-sharepoint-online-integration-scenario"></a>Het voltooide SharePoint Online-integratiescenario van begin tot eind doorlopen
> [!NOTE]
> Dit artikel maakt deel uit van een reeks zelfstudies over het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint Online. Lees de [inleiding tot de reeks](sharepoint-scenario-intro.md) zodat u een idee van het geheel krijgt en van de betreffende downloads.

In deze reeks zelfstudies hebben we heel veel stof behandeld, van het bouwen van canvas-apps en stromen tot het maken van rapporten en het insluiten ervan in SharePoint. Hopelijk hebt u veel geleerd en genoeg ervaring opgedaan om deze technologieën te kunnen integreren, zodat u canvas-apps, stromen en rapporten in SharePoint kunt integreren op basis van uw eigen behoeften. Voordat we de reeks besluiten, willen we het scenario nog eens van begin tot eind doorlopen en zien hoe alle onderdelen met elkaar samenwerken.

## <a name="step-1-add-a-project-to-the-project-requests-list"></a>Stap 1: Een project toevoegen aan de lijst Projectaanvragen
1. Klik of tik in de lijst **Projectaanvragen** op **Alle items** en vervolgens op **App Projectaanvragen**.
   
    ![Weergave app Projectaanvragen](./media/sharepoint-scenario-summary/09-00-01-view-app.png)
2. Klik op **Openen**. Hiermee wordt de app in een nieuw browsertabblad geopend.
   
    ![App Projectaanvragen openen](./media/sharepoint-scenario-summary/09-00-02-open-app.png)
3. Klik of tik in de app op ![Pictogram Item toevoegen](./media/sharepoint-scenario-summary/icon-add-item.png) om een nieuw item te maken.
4. Vul het formulier in met de volgende waarden:
   
   * **Title** = "Mobiele apparaten voor ontwerpteam"

   * **Approved** = "In wachtrij"

   * **Description** = "Het ontwerpteam gebruikt nu apparaten die door Contoso worden geleverd"

   * **EstimatedDays** = "30"

   * **ProjectType** = "Nieuwe hardware"

   * **RequestDate** = "01-03-2017"

   * **Requestor** = "Elsje Quint"
     
     ![Bewerkingsformulier Projectaanvragen](./media/sharepoint-scenario-summary/09-01-01-app-new.png)
5. Klik of tik op ![Pictogram Vinkje](./media/sharepoint-scenario-summary/icon-check-mark.png)en sluit het browsertabblad.
6. Ga terug naar de lijst **Projectaanvragen**, klik of tik op **App Projectaanvragen** en vervolgens op **Alle items**.
   
    ![Alle items bekijken](./media/sharepoint-scenario-summary/09-01-01a-view-all.png)
7. Controleer de nieuwe vermelding in de lijst.
   
    ![SharePoint-lijst met nieuwe vermelding](./media/sharepoint-scenario-summary/09-01-02-list-new.png)

## <a name="step-2-approve-the-project"></a>Stap 2: Het project goedkeuren
1. Wanneer u het item in stap 1 toevoegt, moet de stroom worden uitgevoerd en moet deze een goedkeurings-e-mail verzenden. Controleer het postvak van het e-mailaccount van de fiatteur.
   
    ![E-mail voor goedkeuring van aanvraag](./media/sharepoint-scenario-summary/09-02-01-allan-email.png)
2. Klik op **Goedkeuren**. De stroom voert een ander proces uit en u krijgt feedback via e-mail, zoals hieronder weergegeven.
   
    ![Actie voltooid](./media/sharepoint-scenario-summary/09-02-01a-action-complete.png)
3. Controleer het postvak van het e-mailaccount van de aanvrager. U zou een goedkeurings-e-mail moeten zien.
   
    ![Goedkeurings-e-mail aan aanvrager](./media/sharepoint-scenario-summary/09-02-02-megan-email.png)
4. Controleer de bijgewerkte vermelding in de lijst.
   
    ![SharePoint-lijst met bijgewerkte vermelding](./media/sharepoint-scenario-summary/09-02-03-yes.png)

## <a name="step-3-assign-a-manager-to-the-project"></a>Stap 3: Een manager aan het project toewijzen
1. Eerst kijken we naar de lijst **Projectdetails** in SharePoint. Het nieuwe project heeft de waarde **Unassigned** in de kolom **PMAssigned**.
   
    ![Niet-toegewezen item in SharePoint-lijst](./media/sharepoint-scenario-summary/09-03-01-unassigned.png)
2. Klik of tik in de SharePoint-site, in het linker navigatiedeelvenster, op **App Projectbeheer**.
3. Klik of tik in het eerste scherm op **Manager toewijzen**.
   
    ![Manager toewijzen aan project](./media/sharepoint-scenario-summary/09-03-02-intro-screen.png)
4. In het scherm **Manager toewijzen** ziet u de twee niet-toegewezen projecten uit de lijst. Selecteer het project **Mobiele apparaten voor ontwerpteam**.
   
    ![Niet-toegewezen project in app geselecteerd](./media/sharepoint-scenario-summary/09-03-03-selected.png)
5. Voer in de tekstinvoer naast **Manager** 'Femke van Nuil' in en klik op **OK**.
   
    De wijziging wordt in de lijst doorgevoerd en de galerie wordt vernieuwd, dus alleen het resterende niet-toegewezen project wordt nog weergegeven.
   
    ![Aan project toegewezen manager](./media/sharepoint-scenario-summary/09-03-04-updated.png)
6. Sluit de app en ga terug naar de SharePoint-lijst. U ziet dat de projectvermelding nu wordt bijgewerkt met de naam van de projectmanager.
   
    ![Toegewezen item in SharePoint-lijst](./media/sharepoint-scenario-summary/09-03-05-assigned.png)

## <a name="step-4-add-time-estimates-for-the-project"></a>Stap 4: Geschatte tijden voor project toevoegen
1. Klik of tik op ![Pictogram Terug](./media/sharepoint-scenario-summary/icon-back.png) om naar het eerste scherm terug te gaan en klik of tik vervolgens op **Details bijwerken**.
   
    ![Projectdetails bijwerken](./media/sharepoint-scenario-summary/09-04-00-intro-screen.png)
2. Voer in het scherm **Projecten weergeven** 'Mobiel' in het zoekvak in.
   
    ![Zoeken in app](./media/sharepoint-scenario-summary/09-04-01-search-mobile.png)
3. Klik op ![Pijlpictogram Details](./media/sharepoint-scenario-summary/icon-details-arrow.png) voor het item **Mobiele apparaten voor ontwerpteam**.
   
    ![Bij te werken project selecteren](./media/sharepoint-scenario-summary/09-04-02-select-project.png)
4. Stel in het scherm **Details bijwerken** de volgende waarden in:
   
   * Het veld **Status** = "Not started"

   * Het veld **ProjectedStartDate** = "3/6/2017"

   * Het veld **ProjectedEndDate** = "3/24/2017"

   * Het veld **ProjectedDays** = "15"
     
     ![Projectdetails bijwerken](./media/sharepoint-scenario-summary/09-04-03-update.png)
5. Klik of tik op ![Pictogram Vinkje](./media/sharepoint-scenario-summary/icon-check-mark.png) om de wijziging op de SharePoint-lijst toe te passen.
6. Sluit de app en ga terug naar de lijst. De projectvermelding wordt bijgewerkt met de wijzigingen voor de datum en de dag.
   
   ![Bijgewerkte details in SharePoint-lijst](./media/sharepoint-scenario-summary/09-04-04-updated-list.png)

## <a name="step-5-review-report-data-for-existing-projects"></a>Stap 5: Rapportgegevens voor bestaande projecten controleren
1. Klik of tik in SharePoint Online op **Site-inhoud** en vervolgens op **Sitepagina's**.
2. Open de pagina **Projectanalyse** die we eerder hebben gemaakt.
   
    ![Ingesloten rapport met projectanalyse](./media/sharepoint-scenario-summary/09-05-01-report-complete.png)
3. Controleer de visualisatie met de afwijkingen.
   
    ![Diagram met afwijkingen](./media/sharepoint-scenario-summary/09-05-02-chart-variance.png)
   
    Zoals al opgemerkt bij het maken van deze visualisatie, komen er veel meer afwijkingen voor bij projecten die door Quentin van Groesen zijn uitgevoerd dan bij degene die door Femke van Nuil zijn uitgevoerd.
4. Zoom in op de visualisatie en u ziet dat veel afwijkingen afkomstig zijn van twee projecten die veel langer duurden dan beoogd.
   
    ![Diagram met details van afwijkingen](./media/sharepoint-scenario-summary/09-05-03-chart-variance-drill.png)
5. Bekijk de tabel waarin staat aangegeven hoe lang het duurt voor goedgekeurde projecten de status van beoogde begindatum hebben gekregen.
   
    ![Tabel met verschillen tussen begindatums](./media/sharepoint-scenario-summary/09-05-04-chart-diff-completed.png)
   
    Zoals opgemerkt bij het maken van de visualisatie, duurde het voor de projecten waaraan Quentin van Groesen is toegewezen langer voordat eraan werd begonnen, waarbij twee projecten eruit springen.

## <a name="step-6-respond-to-pending-project-delays"></a>Stap 6: Reageren op wachtende projectvertragingen
1. Klik of tik in de Power BI-service op de gegevensset **project-analysis** en vervolgens op **NU VERNIEUWEN**. Door te vernieuwen wordt de waarschuwing geactiveerd die we hebben ingesteld voor wachtende projecten.
   
    ![Gegevensset nu vernieuwen](./media/sharepoint-scenario-summary/09-06-01-refresh.png)
2. Na het vernieuwen wordt in het **meldingencentrum** rechtsboven een pictogram voor een nieuwe melding weergegeven.
   
    ![Meldingencentrum van Power BI](./media/sharepoint-scenario-summary/09-06-02-alert.png)
   
    Dit kan enige tijd duren, dus kom hier later terug als u het niet meteen ziet.
3. Open het meldingencentrum om de details van de waarschuwing te bekijken.
   
    ![Melding voor gegevenswaarschuwing](./media/sharepoint-scenario-summary/09-06-03-notification.png)
4. Controleer het postvak van de persoon die de waarschuwing heeft gemaakt (in dit geval Ilene de Crom).
   
    ![E-mailwaarschuwing van Power BI](./media/sharepoint-scenario-summary/09-06-04-email-powerbi.png)
5. Controleer het postvak van de persoon die u aan de stroom met gegevenswaarschuwingen hebt toegevoegd (in dit geval Arnaud Schoonen).
   
    ![E-mailwaarschuwing van Microsoft Flow](./media/sharepoint-scenario-summary/09-06-05-email-flow.png)
6. U hebt nu de informatie over wachtende projecten en kunt dus teruggaan en de projecten goedkeuren die uw aandacht vroegen.

Hiermee zijn we aan het eind gekomen van ons totaaloverzicht en deze reeks zelfstudies. U wordt aangeraden de volgende sites te bestuderen:

* [PowerApps](http://www.powerapps.com/)
* [Microsoft Flow](http://flow.microsoft.com)
* [Power BI](http://www.powerbi.com)
* [Power Users Community](https://powerusers.microsoft.com/)
* [SharePoint](http://sharepoint.microsoft.com)
* [Microsoft Tech Community](https://techcommunity.microsoft.com/)

Laat ons via de opmerkingen weten of u feedback hebt over deze reeks, suggesties voor aanvullingen of ideeën over extra inhoud waardoor u met de hier behandelde technologieën kunt leren werken.

