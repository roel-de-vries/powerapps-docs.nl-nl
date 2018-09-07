---
title: Het Power BI-projectrapport insluiten in SharePoint Online | Microsoft Docs
description: In deze taak wordt het Power BI-rapport ingesloten in dezelfde SharePoint Online-site waarin onze twee lijsten worden gehost.
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
ms.openlocfilehash: 9d15001795cc33d163e85b358a52aba759c83021
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865431"
---
# <a name="embed-the-power-bi-project-report-in-sharepoint-online"></a>Het Power BI-projectrapport insluiten in SharePoint Online
> [!NOTE]
> Dit artikel maakt deel uit van een reeks zelfstudies over het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint Online. Lees de [inleiding tot de reeks](sharepoint-scenario-intro.md) zodat u een idee van het geheel krijgt en van de betreffende downloads.

We gaan het Power BI-rapport nu insluiten in dezelfde SharePoint Online-site waarin onze twee lijsten worden gehost. Power BI ondersteunt diverse benaderingen tot insluiten, waaronder rechtstreekse integratie in SharePoint-pagina's voor web- en mobiele weergaven.

Dankzij dit type insluiting sluit Power BI het rapport in als een webonderdeel, biedt het de juiste toegang voor gebruikers en kunt u van het ingesloten rapport naar het rapport op powerbi.com doorklikken. Eerst genereren we een insluitkoppeling in Power BI. Vervolgens gebruiken we die koppeling in een pagina die we maken. Bekijk [Insluiten met webonderdeel Rapport in SharePoint Online](https://docs.microsoft.com/power-bi/service-embed-report-spo) voor meer informatie over insluiten.

## <a name="step-1-generate-an-embed-link"></a>Stap 1: Een insluitkoppeling genereren
1. Meld u aan bij Power BI en klik of tik vervolgens in het linker navigatiedeelvenster op de naam van het rapport.
   
    ![Naar het rapport navigeren](./media/sharepoint-scenario-embed-report/08-01-01-reports.png)
2. Klik of tik op **Bestand** en vervolgens op **Insluiten in SharePoint Online**.
   
    ![Insluiten in SharePoint Online](./media/sharepoint-scenario-embed-report/08-01-02-embed-spo.png)
3. Kopieer de insluitkoppeling vanuit het dialoogvenster naar een bestand en klik of tik op **Sluiten**. We gebruiken de koppeling nadat we een SharePoint-pagina hebben gemaakt.
   
    ![Insluitkoppeling voor SharePoint](./media/sharepoint-scenario-embed-report/08-01-03-embed-url.png)

## <a name="step-2-embed-the-report"></a>Stap 2: Het rapport insluiten
1. Meld u aan bij SharePoint en klik of tik op **Site-inhoud**.
   
    ![SharePoint-site-inhoud](./media/sharepoint-scenario-embed-report/08-01-04-site-contents.png)
2. U kunt gewoon een rapport op de startpagina van het team insluiten, maar we laten u zien hoe u er ook een afzonderlijke pagina voor kunt maken. Klik of tik op **Nieuw** en vervolgens op **Pagina**.
   
    ![Nieuwe SharePoint-pagina](./media/sharepoint-scenario-embed-report/08-01-05-new-page.png)
3. Voer een naam in voor de pagina, bijvoorbeeld Projectanalyse.
4. Klik of tik op ![Pluspictogram](./media/sharepoint-scenario-embed-report/icon-plus.png) en vervolgens op **Power BI**.
   
    ![Pagina-onderdeel Power BI toevoegen](./media/sharepoint-scenario-embed-report/08-01-06-add-page-part.png)
5. Klik of tik op **Rapport toevoegen**.
   
    ![Rapport toevoegen](./media/sharepoint-scenario-embed-report/08-01-07-add-report.png)
6. Kopieer vanaf het rechterdeelvenster de ingesloten URL in het vak **Power BI-rapportkoppeling**. Stel zowel **Filterdeelvenster tonen** als **Navigatiemenu weergeven** in op **Aan**.
   
    ![Rapportinstellingen](./media/sharepoint-scenario-embed-report/08-01-08-report-settings.png)
7. Het rapport is nu ingesloten in de pagina. Klik op **Publiceren** om de pagina beschikbaar te maken voor iedereen met toegang tot het onderliggende rapport.
   
    ![Insluiten rapport voltooid](./media/sharepoint-scenario-embed-report/08-01-09-report-complete.png)

## <a name="step-3-grant-access-to-the-report"></a>Stap 3: Toegang verlenen tot het rapport.
Als u, zoals aangeraden, Office 365 Groepen gebruikt, controleert u of gebruikers die toegang nodig hebben, leden zijn van de groepswerkruimte in de Power BI-service. Hiermee garandeert u dat gebruikers de inhoud van die groep kunnen bekijken. Bekijk [Samenwerken in de werkruimte van uw Power BI-app](https://docs.microsoft.com/power-bi/service-collaborate-power-bi-workspace) voor meer informatie.

Hiermee hebben we een samenvatting gegeven van ons werk in Power BI voor dit scenario. U bent begonnen met het ophalen van gegevens uit de SharePoint-lijsten voor Power BI. U bent nu klaar om het Power BI-rapport weer in SharePoint in te sluiten.

## <a name="next-steps"></a>Volgende stappen
De volgende stap in deze reeks zelfstudies bestaat uit het [doorlopen van de werkstroom die we van begin tot eind hebben gemaakt](sharepoint-scenario-summary.md).

