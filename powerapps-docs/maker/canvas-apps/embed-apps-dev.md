---
title: PowerApps integreren in websites en andere services | Microsoft Docs
description: Apps insluiten in websites en andere services.
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/20/2017
ms.author: mblythe
ms.openlocfilehash: 0f4ea37d93b20a768fa16d1dcdb41f921336f043
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="integrate-powerapps-into-websites-and-other-services"></a>PowerApps integreren in websites en andere services
De apps die u bouwt zijn vaak het best te gebruiken als ze beschikbaar zijn op de plek waar het werk wordt uitgevoerd. Met PowerApps kunt u apps insluiten in een iframe, zodat u deze apps kunt integreren in websites en andere services, zoals Power BI of SharePoint.

In dit onderwerp leert u hoe u parameters instelt om de app in te kunnen sluiten. Vervolgens gaat u de app Voorraad bestellen in een website insluiten.

![Power BI-dashboard met ingesloten app](./media/embed-apps-dev/embed-dashboard.png)

Houd rekening met de volgende beperkingen:

* Alleen PowerApps-gebruikers in dezelfde tenant hebben toegang tot de ingesloten app.
* Voor toegang tot PowerApps met behulp van Internet Explorer 11, moet u de Compatibiliteitsweergave uitschakelen.

U kunt ook PowerApps integreren in SharePoint Online (zonder iframe). Zie [Een app genereren vanuit SharePoint met behulp van PowerApps](../canvas-apps/generate-app-from-sharepoint-list-interface.md) voor meer informatie.

## <a name="set-uri-parameters-for-your-app"></a>URI-parameters instellen voor de app
Als u een app wilt insluiten, stelt u eerst de parameters in voor de URI (Uniform Resource Identifier), zodat het iframe de app kan vinden. De URI heeft de volgende indeling:

```
https://web.powerapps.com/webplayer/iframeapp?source=iframe
&appId=/providers/Microsoft.PowerApps/apps/[AppID]
```

> [!NOTE]
> Er is een regeleinde toegevoegd, zodat de URI beter op de pagina wordt weergegeven.

Het enige wat u moet doen, is [AppID] in de URI (inclusief '[' en ']') vervangen door de ID van uw app. U leert verderop hoe u aan die waarde komt. Eerst worden hier alle parameters getoond die in de URI beschikbaar zijn:

* **appID**: heeft de indeling `/providers/Microsoft.PowerApps/apps/[AppID]`. De parameter geeft de id van de uit te voeren app.
* **screenColor**: deze wordt gebruikt om de app beter te kunnen laden. Deze parameter heeft de indeling [RGBA (rode waarde, groene waarde, blauwe waarde, alfa)](../canvas-apps/functions/function-colors.md) en bepaalt de schermkleur tijdens het laden van de app. Het wordt aangeraden de schermkleur dezelfde kleur te geven als het pictogram voor de app.
* **source**: is niet van invloed op de app, maar u wordt aangeraden een beschrijvende naam toe te voegen die naar de bron van de ingesloten app verwijst.
* Ten slotte kunt u aangepaste parameters toevoegen met de functie [Param()](../canvas-apps/functions/function-param.md). Deze waarden kunnen door de app worden gebruikt. Ze worden aan het eind van de URI toegevoegd, bijvoorbeeld `[AppID]&amp;param1=value1`. Deze parameters worden alleen gelezen als de app wordt gestart. Als u ze wilt wijzigen, moet u de app opnieuw starten.

### <a name="get-the-app-id"></a>De app-id ophalen
De app-id is beschikbaar op powerapps.com. Ga voor de app die u wilt insluiten als volgt te werk:

1. Ga naar [powerapps.com](https://powerapps.microsoft.com) en klik of tik op het tabblad **Apps** op het beletselteken ( **. . .** ), vervolgens op **Details**.
   
    ![Naar de app-details](./media/embed-apps-dev/details.png)
2. Kopieer de **App ID**.
   
    ![App-id kopiëren in Details](./media/embed-apps-dev/app-id.png)
3. Vervang de `[AppID]`-waarde in de URI. De URI ziet er voor de app Voorraad bestellen als volgt uit:
   
    ```
    https://web.powerapps.com/webplayer/iframeapp?source=iframe&appId=/providers/Microsoft.PowerApps/apps/76897698-91a8-b2de-756e-fe2774f114f2
    ```

## <a name="embed-your-app-in-a-website"></a>De app insluiten in een website
Voor het insluiten van de app hoeft u nu alleen nog maar de iframe toe te voegen aan de HTML-code voor uw site (of aan elke andere service die iframes ondersteunt, zoals Power BI of SharePoint):

```
<iframe width="[W]" height="[H]" src="https://web.powerapps.com/webplayer/iframeapp?source=website&screenColor=rgba(165,34,55,1)&appId=/providers/Microsoft.PowerApps/apps/[AppID]" allow="geolocation; microphone; camera"/>
```

Geef waarden op voor de hoogte en breedte van de iframe en vervang `[AppID]` door de id van de app.

> [!NOTE]
> Neem `allow="geolocation; microphone; camera"` op in de HTML-code voor het iframe om toe te staan dat uw apps deze mogelijkheden gebruiken in Google Chrome.

In de volgende afbeelding ziet u de app Voorraad bestellen ingesloten in een voorbeeld van een Contoso-website.

![Contoso-website met ingesloten app](./media/embed-apps-dev/contoso-website.png)

Houd de volgende punten in acht wanneer u gebruikers van de app gaat verifiëren:

* Als uw website AAD (Azure Active Directory) gebruikt op basis van verificatie, is er geen aanvullende aanmelding vereist.
* Als uw website gebruikmaakt van een ander aanmeldingsproces of als de website niet geverifieerd is, zien de gebruikers een aanmeldingsprompt op de iframe. Nadat een gebruiker is aangemeld, kan de app worden uitgevoerd, mits de auteur van de app deze met de gebruiker heeft gedeeld.

Zoals u ziet, is het insluiten van apps eenvoudig en levert het u veel op. Door apps in te sluiten, kunt u ze precies op de plek krijgen waar u en uw klanten hun werk doen: onder meer op websites, in Power BI-dashboards en op SharePoint-pagina's.

