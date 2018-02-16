---
title: Gegevensmeldingen instellen voor het Power BI-dashboard | Microsoft Docs
description: In deze taak voegen we een waarschuwing toe in Power BI, zodat we een melding krijgen als het te lang duurt voordat projecten die in de wacht staan, worden goedgekeurd. We voegen ook een stroom toe die reageert als er een waarschuwing optreedt.
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
ms.date: 06/12/2017
ms.author: mblythe
ms.openlocfilehash: 6696f03be879e1c6f764cc444aa874e0b4a73905
ms.sourcegitcommit: e827813cd898ca9a1046b5952ea5e32ce2989a65
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2018
---
# <a name="set-up-data-alerts-for-the-power-bi-dashboard"></a>Gegevensmeldingen instellen voor het Power BI-dashboard
> [!NOTE]
> Dit artikel maakt deel uit van een reeks zelfstudies over het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint Online. Lees de [inleiding tot de reeks](sharepoint-scenario-intro.md) zodat u een idee van het geheel krijgt en van de betreffende downloads.

In deze taak voegen we een waarschuwing toe in Power BI, zodat we een melding krijgen als het te lang duurt voordat projecten die in de wacht staan, worden goedgekeurd. We voegen ook een stroom toe die reageert als er een waarschuwing optreedt. Zie [Data alerts in Power BI service](https://docs.microsoft.com/power-bi/service-set-data-alerts) (Gegevensmeldingen in de Power BI-service) voor meer informatie over waarschuwingen.

## <a name="step-1-create-an-alert"></a>Stap 1: Een waarschuwing maken
1. Open in de Power BI-service het dashboard dat u in de laatste taak hebt gemaakt.
2. Klik of tik op de kaart met het getal op het beletselteken (**...**).
   
    ![Kaart met maximaal aantal dagen wachtend op goedkeuring](./media/sharepoint-scenario-alerts-flow/07-01-01-tile-ellipsis.png)
3. Klik of tik op ![Belpictogram](./media/sharepoint-scenario-alerts-flow/icon-bell.png).
   
    ![Tegelmenu](./media/sharepoint-scenario-alerts-flow/07-01-02-tile-bell.png)
4. Klik of tik in het rechterdeelvenster op **Waarschuwingsregel toevoegen**.
   
    ![Waarschuwingsregel toevoegen](./media/sharepoint-scenario-alerts-flow/07-01-03-add-alert.png)
5. Bekijk de beschikbare opties voor waarschuwingen, zoals hoe vaak een waarschuwing moet worden uitgevoerd. Voer de waarde 25 in voor **Drempelwaarde** en klik of tik op **Opslaan en sluiten**.
   
    ![Waarschuwingsdrempel instellen en opslaan](./media/sharepoint-scenario-alerts-flow/07-01-04-save-alert.png)

Er volgt niet meteen een waarschuwing, ook al is 56 meer dan de drempelwaarde van 25. Er volgt een waarschuwing als er gegevens worden bijgewerkt. Dat gebeurt als we [het scenario van begin tot eind doorlopen](sharepoint-scenario-summary.md).

Als er een waarschuwing wordt gegeven, wordt er een e-mail verzonden naar de maker van de waarschuwing, en in de volgende stap zien we hoe we extra e-mails kunnen verzenden met Microsoft Flow.

## <a name="step-2-create-a-flow-that-responds-to-the-alert"></a>Stap 2: Een stroom maken die op de waarschuwing reageert
1. Meld u aan bij flow.microsoft.com, klik of tik op **Services** en vervolgens op **Power BI**.
   
    ![Power BI in Microsoft Flow](./media/sharepoint-scenario-alerts-flow/07-01-05-power-bi.png)
2. Klik of tik op **Een e-mail verzenden naar een doelgroep wanneer een waarschuwing met betrekking tot Power BI-gegevens wordt geactiveerd**.
   
    ![E-mail verzenden als er een Power BI-gegevensmelding wordt geactiveerd](./media/sharepoint-scenario-alerts-flow/07-01-06-alert-flow.png)
3. Klik of tik op **Deze sjabloon gebruiken**.
4. Als u nog niet bent aangemeld, meldt u zich aan bij Outlook en Power BI en klikt of tikt u op **Doorgaan**.
   
    ![Aanmelden en doorgaan](./media/sharepoint-scenario-alerts-flow/07-01-08-continue.png)
5. Selecteer in de vervolgkeuzelijst **Waarschuwings-id** de optie **Waarschuwing voor maximum aantal dagen wachtend op goedkeuring**.
   
    ![Een waarschuwing als trigger opgeven](./media/sharepoint-scenario-alerts-flow/07-01-09-choose-alert.png)
6. Voer in het vak **Aan** een geldig e-mailadres in.
   
    ![Opgeven aan wie de e-mail wordt verzonden](./media/sharepoint-scenario-alerts-flow/07-01-10-choose-email.png)
7. Klik of tik op **Bewerken** om andere velden te zien die u kunt bijwerken.
   
    ![Waarschuwings-e-mail bewerken](./media/sharepoint-scenario-alerts-flow/07-01-11-email-full.png)
8. Klik rechtsboven in het scherm op **Stroom maken** en vervolgens op **Gereed**.
   
    ![Knop Gereed](./media/sharepoint-scenario-alerts-flow/07-01-12-done.png)

Deze stroom wordt uitgevoerd als we [het scenario van begin tot eind doorlopen](sharepoint-scenario-summary.md). We gaan nu naar de laatste taak in dit scenario: een Power BI-rapport insluiten in SharePoint.

## <a name="next-steps"></a>Volgende stappen
De volgende stap in deze reeks zelfstudies bestaat uit het [insluiten van een projectrapport in SharePoint Online](sharepoint-scenario-embed-report.md).

