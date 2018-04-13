---
title: Aangepast visueel PowerApps-element voor Power BI | Microsoft Docs
description: Procedure en beperkingen voor het insluiten van een app die gebruikmaakt van dezelfde gegevensbron en kan worden gefilterd zoals andere rapportitems in Power BI
services: powerapps
suite: powerapps
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: tutorial
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/15/2018
ms.author: mblythe
ms.openlocfilehash: a1ca27ddaff4264fe961588701859fe1ad730c42
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="powerapps-custom-visual-for-power-bi"></a>Aangepast visueel PowerApps-element voor Power BI

Power BI biedt inzicht in gegevens en maakt een betere besluitvorming mogelijk, terwijl met PowerApps iedereen apps kan bouwen en gebruiken die verbinding met zakelijke gegevens maken. U kunt met het aangepaste visuele PowerApps-element contextbewuste gegevens doorgeven aan een PowerApps-app die in realtime wordt bijgewerkt wanneer u wijzigingen in uw rapport aanbrengt. Nu kunnen uw app-gebruikers rechtstreeks vanuit hun Power BI-rapporten en dashboards zakelijke inzichten ontlenen en maatregelen nemen.

## <a name="using-the-powerapps-custom-visual"></a>Het aangepaste visuele PowerApps-element gebruiken

Bekijk de stappen die nodig zijn om het aangepaste visuele PowerApps-element in uw Power BI-rapport te gebruiken.

1. Haal het aangepaste visuele element op uit [AppSource](https://appsource.microsoft.com/product/power-bi-visuals/WA104381378?tab=Overview) of importeer deze rechtstreeks naar de Power BI-service.

    ![Aangepast visueel element in Marketplace](./media/powerapps-custom-visual/powerapps-store.png) 

1. Voeg het visuele PowerApps-element toe aan uw rapport en stel de daaraan gekoppelde gegevensvelden in.

    ![De rapportgegevens selecteren](./media/powerapps-custom-visual/add-visual-set-data.png)

1. U kunt hiervoor een bestaande app kiezen of er een maken. Als u ervoor kiest om een app te maken, kunt u kiezen in welke omgeving u deze wilt maken.

    ![Nieuwe of bestaande app](./media/powerapps-custom-visual/create-new-or-choose-app.png)

    Als u ervoor kiest om een bestaande app te gebruiken, wordt u via de visual gevraagd om de app in PowerApps te openen. De vereiste componenten in uw app worden voor het visuele element ingesteld, zodat Power BI PowerApps gegevens kan versturen.

    Als u een nieuwe app maakt, wordt in PowerApps een eenvoudige app gemaakt waarop de vereiste componenten al zijn ingesteld.

    ![Nieuwe app](./media/powerapps-custom-visual/new-app.png)

1. Nu kunt u in PowerApps Studio de gegevensvelden gebruiken die u in stap 2 hebt ingesteld. Het object `PowerBIIntegration` fungeert zoals elke andere alleen-lezen PowerApps-gegevensbron of -verzameling. U kunt met het object een besturingselement invullen, of deze toevoegen en filteren met andere gegevensbronnen.

    ![Aangepaste formule](./media/powerapps-custom-visual/custom-formula.png)

    Deze formule wordt aan de Power BI-gegevens toegevoegd met de gegevensbron van de klant: `LookUp(Customer,Customer_x0020_Name=First(PowerBIIntegration.Data).Customer_Name)`

 Het Power BI-rapport en de gestarte PowerApps Studio-instantie delen een live gegevensverbinding. Wanneer deze beide zijn geopend, kunt u de gegevens in het rapport filteren of wijzigen. De bijgewerkte gegevens ziet u onmiddellijk in uw app in PowerApps Studio weergegeven.

1. Sla, wanneer u gereed bent met het bouwen of wijzigen van uw app, de app op en publiceer deze in PowerApps om uw app in het Power BI-rapport te zien.

1. Zorg ervoor dat u, wanneer u tevreden bent met uw wijzigingen, de PowerApps-app deelt met gebruikers van uw rapport en sla het rapport vervolgens op.

1. En hiermee hebt u een rapport gemaakt waarin uw gebruikers acties kunnen uitvoeren al naar gelang zij inzichten krijgen uit uw gegevens.

    ![Het rapport bewerken](./media/powerapps-custom-visual/working-report.gif)

    Als u wijzigingen wilt aanbrengen in een app, opent u het rapport in de bewerkingsmodus moet, klikt of tikt u op **Meer opties** (**...** ) op het visuele PowerApps-element en selecteert u **Bewerken**.

    ![App bewerken](./media/powerapps-custom-visual/edit-app.png)

## <a name="limitations-of-the-powerapps-custom-visual"></a>Beperkingen van het aangepaste visuele PowerApps-element

Het aangepaste visuele PowerApps-element is beschikbaar in preview en heeft de volgende beperkingen:

- U kunt apps maken of wijzigen wanneer u het aangepaste visuele element PowerApps in Power BI Desktop, Internet Explorer of Mozilla Firefox gebruikt. Het is raadzaam dat u eerst uw rapport naar de Power BI-service publiceert. Maak vervolgens met Microsoft Edge of Google Chrome nieuwe apps en breng hieraan wijzigingen aan.
- Als u de gegevensvelden wijzigt die zijn gekoppeld aan het visuele element, moet u de app vanuit de Power BI-service bewerken door het beletselteken (...) en vervolgens de optie **Bewerken** te selecteren. Anders worden de wijzigingen niet doorgevoerd in PowerApps, zodat het gedrag van de app onvoorspelbaar wordt.
- Het aangepaste visuele PowerApps-element kan geen vernieuwing van de Power BI-rapport of de Power BI-gegevensbron activeren. Als u gegevens uit de app naar dezelfde gegevensbron als het rapport terugschrijft, worden uw wijzigingen niet onmiddellijk zichtbaar. Wijzigingen worden zichtbaar bij de volgende geplande vernieuwing.
- Met het aangepaste visuele PowerApps-element kunnen de gegevens niet worden gefilterd en kunnen geen gegevens worden teruggestuurd naar het rapport.
- U moet de PowerApps-app afzonderlijk van uw rapport delen. Meer informatie over het [delen van apps in PowerApps](share-app.md).
- De mobiele app voor Power BI biedt geen ondersteuning voor het aangepaste visuele PowerApps-element.

## <a name="next-steps"></a>Volgende stappen

* Doorloop een eenvoudige [stapsgewijze zelfstudie](embed-powerapps-powerbi.md).
* Bekijk onze [video](https://aka.ms/powerappscustomvisualvideo).