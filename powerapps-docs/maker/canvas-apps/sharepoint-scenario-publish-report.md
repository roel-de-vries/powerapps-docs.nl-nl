---
title: Het Power BI-projectrapport publiceren en een dashboard maken | Microsoft Docs
description: In deze taak wordt de gegevensset gepubliceerd en aan de Power BI-service gerapporteerd. Vervolgens wordt een dashboard gemaakt op basis van het rapport.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/30/2018
ms.author: mblythe
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f5a39ec04015fe360bc550d9ea4f708d887ba34c
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833869"
---
# <a name="publish-the-power-bi-project-report-and-create-a-dashboard"></a>Het Power BI-projectrapport publiceren en een dashboard maken
> [!NOTE]
> Dit artikel maakt deel uit van een reeks zelfstudies over het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint Online. Lees de [inleiding tot de reeks](sharepoint-scenario-intro.md) zodat u een idee van het geheel krijgt en van de betreffende downloads.

In deze taak wordt de gegevensset gepubliceerd en aan de Power BI-service gerapporteerd. Vervolgens wordt een dashboard gemaakt op basis van het rapport. In veel gevallen bevat een rapport een groot aantal visualisaties; slechts een subset wordt in een dashboard gebruikt. In dit geval voegen we vier visualisaties aan het dashboard toe.

## <a name="step-1-publish-the-dataset-and-report"></a>Stap 1: De gegevensset en het rapport publiceren
1. Klik of tik in Power BI Desktop, op het tabblad **Start**, op **Publiceren**.
   
    ![Gegevensset en rapport publiceren](./media/sharepoint-scenario-publish-report/06-01-01-publish.png)
2. Als u nog niet bent aangemeld bij de Power BI-service, voert u een account in en klikt of tikt u op **Aanmelden**.
   
    ![Aanmelden bij het account](./media/sharepoint-scenario-publish-report/06-01-02-account.png)
3. Voer een wachtwoord in en klik of tik op **Aanmelden**.
   
    ![Accountwachtwoord invoeren](./media/sharepoint-scenario-publish-report/06-01-03-password.png)
4. Kies een doel voor het rapport en klik of tik op **Selecteren**. U wordt aangeraden het rapport te publiceren op een groepswerkruimte om de toegang tot het rapport in SharePoint te vereenvoudigen. Hier publiceren we het rapport op de groepswerkruimte **Projectbeheer**. Bekijk [Samenwerken in de werkruimte van uw Power BI-app](https://docs.microsoft.com/power-bi/service-collaborate-power-bi-workspace) voor meer informatie.
   
    ![Doelwerkruimte](./media/sharepoint-scenario-publish-report/06-01-04-workspace.png)
5. Als het rapport is gepubliceerd, klikt of tikt u op **Open 'project-analysis.pbx' in Power BI**.
   
    ![Publiceren geslaagd](./media/sharepoint-scenario-publish-report/06-01-05-open-report.png)
6. Het rapport wordt in een browser geladen. Klik of tik op het menu linksboven **(a)** om het linker navigatiedeelvenster uit te breiden.
   
    ![Rapporteren in Power BI-service](./media/sharepoint-scenario-publish-report/06-01-06-service-report.png)
   
    U ziet dat er tijdens het publiceren een gegevensset **(d)** en een rapport **(c)** zijn geüpload. Dashboards worden in de service gemaakt, niet in Power BI Desktop. Deze werkruimte bevat nog geen dashboards **(b)**. We gaan er zo een maken.

## <a name="step-2-configure-credentials-for-refresh"></a>Stap 2: Referenties voor vernieuwen configureren
1. Klik of tik in de service op ![tandwielpictogram](./media/sharepoint-scenario-publish-report/icon-gear.png) rechtsboven en vervolgens op **Instellingen**.
2. Klik of tik op **Gegevenssets** en vervolgens op **project-analysis**.
   
    ![Gegevensset project-analysis](./media/sharepoint-scenario-publish-report/06-01-07-dataset.png)
3. Vouw **Gegevensbronreferenties** uit en klik of tik op **Referenties bewerken**.
   
    ![Gegevensbronreferenties bewerken](./media/sharepoint-scenario-publish-report/06-01-08-credentials.png)
4. Selecteer **OAuth2** als verificatiemethode en klik of tik op **Aanmelden**.
   
    ![Aanmelden bij SharePoint](./media/sharepoint-scenario-publish-report/06-01-09-sign-in.png)
5. Meld u aan bij een account met machtigingen voor de SharePoint-lijsten. U kunt het account ook selecteren.
   
    ![Aangemeld bij Office 365](./media/sharepoint-scenario-publish-report/06-01-10-account.png)
   
    Als het proces is voltooid, krijgt u het volgende bericht in de service.
   
    ![Gegevensbron bijgewerkt](./media/sharepoint-scenario-publish-report/06-01-11-updated.png)

## <a name="step-3-create-a-dashboard"></a>Stap 3: Dashboard maken

1. Klik of tik onder **RAPPORTEN** op **project-analysis** om terug te gaan naar uw rapport.

1. Klik of tik op de grafiek linksboven en klik of tik vervolgens op ![Speldpictogram](./media/sharepoint-scenario-publish-report/icon-pin.png).
   
    ![Grafiek vastmaken](./media/sharepoint-scenario-publish-report/06-01-12-pin-projected.png)
2. Voer een naam in voor het dashboard waaraan u wilt vastmaken en klik of tik op **Vastmaken**.
   
    ![Grafiek vastmaken aan dashboard](./media/sharepoint-scenario-publish-report/06-01-13-pin-new.png)
3. Klik of tik op de grafiek rechtsboven en klik of tik vervolgens op ![Speldpictogram](./media/sharepoint-scenario-publish-report/icon-pin.png).
   
    ![Grafiek vastmaken](./media/sharepoint-scenario-publish-report/06-01-14-pin-variance.png)
4. Selecteer het bestaande dashboard en klik of tik op **Vastmaken**.
   
    ![Grafiek vastmaken aan bestaand dashboard](./media/sharepoint-scenario-publish-report/06-01-15-pin-existing.png)

5. Herhaal deze vastmaakprocedure voor de andere twee visualisaties.

6. Klik of tik in het linker navigatiedeelvenster op de naam van het dashboard.
   
    ![Nieuw dashboard in sitenavigatie](./media/sharepoint-scenario-publish-report/06-01-16-dashboard-menu.png)

7. Bekijk het dashboard. Als u op een tegel klikt, gaat u terug naar het rapport.
   
    ![Voltooid dashboard](./media/sharepoint-scenario-publish-report/06-01-17-dashboard-completed.png)

Dit geeft het grootste deel van het werk in Power BI in het kort weer. Gefeliciteerd, als dit uw eerste kennismaking was met het maken van rapporten en dashboards. Als u hier al ervaring mee hebt, hebt u het hopelijk snel kunnen doorlopen. We gaan nu waarschuwingen toevoegen, zodat we zeker weten dat het dashboard onze aandacht krijgt, mocht dat nodig zijn.

## <a name="next-steps"></a>Volgende stappen
De volgende stap in deze reeks zelfstudies bestaat uit het [instellen van gegevensmeldingen voor het Power BI-projectrapport](sharepoint-scenario-alerts-flow.md).

