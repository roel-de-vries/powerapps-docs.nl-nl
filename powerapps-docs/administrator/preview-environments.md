---
title: Preview-omgevingen | Microsoft Docs
description: Krijg vroege toegang tot functies met PowerApps Preview-programma
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 08/29/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: e2c4c735827941b32ce5e019eb8d71e4328e4a7a
ms.sourcegitcommit: b8eee36e680036accb0e7d9fc7a434906af1c4d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/30/2018
ms.locfileid: "43297835"
---
# <a name="powerapps-preview-program"></a>PowerApps Preview-programma
PowerApps werkt het platform en de mogelijkheden ervan elke paar dagen of weken bij. Het PowerApps Preview-programma is een manier om vroege toegang te krijgen tot deze toekomstige functies en updates voordat deze beschikbaar zijn in andere regio's (waar klantproductie-apps zijn geïmplementeerd). 

Met het PowerApps Preview-programma kunt u:
- **Toekomstige functies uitproberen, leren en voorproeven**: veel functies worden eerst een paar dagen uitgerold in de Preview-versie om feedback te krijgen. Door deel te nemen aan het Preview-programma, krijgt u eerder informatie over nieuwe functies en kunt u feedback geven. Daarnaast kunt u snel profiteren van nieuwe functies zodra ze regio’s bereiken waar de productie-apps worden gemaakt.
- **Maak bedrijfscontinuïteit mogelijk door ervoor te zorgen dat huidige apps blijven werken** met de toekomstige updates (vNext) van PowerApps.

## <a name="what-in-powerapps-is-available-for-preview"></a>Wat is in PowerApps beschikbaar als preview?
Voor toegang tot de preview-functies van PowerApps moet u zich in een preview-omgeving bevinden. In de volgende sectie krijgt u meer informatie over de preview-omgeving.
Op dit moment wordt de Preview-versie van de volgende scenario's in PowerApps uitgerold:
1. **Apps maken**: u kunt op canvas gebaseerde apps maken met behulp van de volgende versie van PowerApps. Dit kan worden gedaan door apps te maken in een preview-omgeving. Huidige beperkingen zijn: modelgestuurde apps kunnen niet worden ingebouwd in het preview-programma - we zijn ermee bezig.
2. **Apps beheren**: u kunt apps beheren en delen met behulp van de [PowerApps-webportal][2]. Voor toegang tot de preview-functies hoeft u alleen maar in een preview-omgeving te zijn. Deze brengt u naar de preview-versie van de [webportal van PowerApps][3].
3. **Apps afspelen**: u moet de apps afspelen in een preview-omgeving met behulp van de webspeler. Als u dat doet, wordt u automatisch naar de [preview-versie van de webspeler][4] gebracht. Apps worden afgespeeld met de vNext-versie van de PowerApps-webspeler. Huidige beperkingen zijn: PowerApps Mobile voor iOS, Android en Windows zijn momenteel niet beschikbaar voor de preview-versie. Apps afspelen die zijn gemaakt in de eerste Release-omgeving werkt mogelijk niet - we zijn ermee bezig.
4. **PowerApps beheren**: beheerderservaringen zijn beschikbaar voor preview met behulp van de [preview-versie van PowerApps-beheercentrum][1]

## <a name="how-to-get-early-access-to-the-upcoming-updates"></a>Hoe krijgt u vroege toegang tot de toekomstige updates?
Alle apps en verwante resources voor PowerApps worden opgeslagen in een omgeving. Vroege toegang tot alle preview-functies is ook beschikbaar met een omgeving die is gemaakt in een regio waarin de vNext (preview) is geïmplementeerd. Op dit moment is er slechts één regio, **Preview (Verenigde Staten)**, zoals u in de onderstaande afbeelding ziet:

![](./media/preview-environment/env3-preview.png)

Selecteer de regio voor de omgeving als **Preview (Verenigde Staten)** en geef toestemming om mee te doen aan het Preview-programma om de omgeving te maken om toegang te krijgen tot de volgende versie (vNext) van PowerApps.
Alle apps en andere resources die zijn gemaakt in deze omgeving, bevinden zich op de vNext-versie van het platform (SAAS).

## <a name="how-to-learn-about-the-latest-updates"></a>Hoe krijg ik meer informatie over de nieuwste updates?
U kunt op de hoogte blijven van de nieuwe functies die beschikbaar zijn voor preview in [Wat is er nieuw in PowerApps][5]. De functies die alleen in de preview-versie beschikbaar zijn, hebben het label 'Preview'.

## <a name="key-scenarios-to-test-with-the-preview-program"></a>Belangrijke scenario's om te testen met het preview-programma
1. **Uw productie-apps valideren met de toekomstige updates voor PowerApps (vNext)**

   Mogelijk wilt controleren of uw productie-apps goed werken met de volgende geplande updates op PowerApps. U kunt de apps vanaf een productieomgeving [kopiëren][6] naar een omgeving in de First Release en de apps afspelen om de scenario's te testen. Denk erom dat alle andere benodigde bronnen, zoals CustomAPI, Flow enzovoort, ook moeten worden verplaatst. Hierbij zou alleen een ander exemplaar van deze apps en vereiste resources moeten worden gemaakt. U kunt de nieuwere updates niet alleen gaan testen met het afspelen van een app, maar ook tijdens het bewerken en beheren van de apps.
   
2. **De nieuwe functies die beschikbaar zijn in preview proberen**

   We gaan veel nieuwe functies in eerste instantie starten in de regio **Preview (Verenigde Staten)**. U kunt de nieuwe functies proberen voordat ze beschikbaar worden gesteld in de andere regio's (die mogelijk invloed hebben op uw productieomgeving).

## <a name="how-to-provide-feedback-to-the-product-team"></a>Hoe geeft u het productteam feedback?
U kunt feedback geven op het [PowerApps-forum] [ 8] en/of contact opnemen met [ondersteuning][9].

## <a name="what-are-the-known-issues-and-limitations"></a>Wat zijn de bekende problemen en beperkingen?
1. **PowerApps-portals en clients die niet beschikbaar zijn in Preview-versie** 

   Er zijn bepaalde functies, services en portals beschikbaar in de preview-versie:
   
   ![](./media/preview-environment/table.png)

2. **Toegang tot apps die in de First Release-omgeving zijn gemaakt vanuit Desktop Studio in Windows**

   Zoals eerder vermeld, is Desktop Studio in Windows niet als preview beschikbaar. Daarom is het maken of bewerken van de apps in de preview-omgeving mogelijk niet compatibel met uw Desktop Studio en ziet u het volgende foubericht:
   
   ![](./media/preview-environment/error2.jpg)

   In dat geval raden wij aan u Web Studio te gebruiken om een app te maken of bewerken in de preview-omgeving.

3. **Database kan niet worden gemaakt in de preview-regio**

   Op dit moment kunt u geen database maken met Common Data Service voor apps in een omgeving in de regio Preview (Verenigde Staten): we zijn ermee bezig.


<!--Reference links in article-->
[1]: https://preview.admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://preview.web.powerapps.com
[4]: https://preview.web.powerapps.com/webplayer
[5]: https://docs.microsoft.com/powerapps/maker/canvas-apps/release-notes
[6]: https://docs.microsoft.com/powerapps/administrator/environment-and-tenant-migration
[7]: https://preview.create.powerapps.com
[8]: https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1
[9]: https://powerapps.microsoft.com/support/

