---
title: Een sessie-id of een canvas-app-id ophalen | Microsoft Docs
description: Informatie over het ophalen van een sessie-id of een canvas-app-id voor het oplossen van problemen in PowerApps
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/18/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 67cfe4ac6c53797e6a18a68d3fbcf29b088f3da8
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42848650"
---
# <a name="get-a-session-id-or-a-canvas-app-id"></a>Een sessie-id of een canvas-app-id ophalen
Als er een probleem is met een canvas-app die is gemaakt in PowerApps, kan Microsoft het probleem veel efficiënter oplossen als u beschikt over een sessie-id, een app-id of beide id's.

## <a name="get-the-session-id"></a>De sessie-id ophalen

### <a name="when-editing-an-app"></a>Tijdens het bewerken van een app
1. Selecteer **Bestand** in de linkerbovenhoek.

1. Selecteer **Account**.

1. Selecteer **Sessiegegevens** onder **Diagnostische gegevens**.

    ![Een sessie-id ophalen vanuit PowerApps Studio](media/get-sessionid/studio.png)

### <a name="when-running-an-app-in-a-browser"></a>Tijdens het uitvoeren van een app in een browser
1. Selecteer het tandwielpictogram in de rechterbovenhoek.

1. Selecteer **Sessiegegevens**.

    ![Een sessie-id ophalen vanuit een browser](media/get-sessionid/browser.png)

### <a name="when-running-an-app-on-a-phone-or-a-tablet"></a>Tijdens het uitvoeren van een app op een telefoon of tablet
1. Swipe naar rechts.

1. Tik op **Sessiegegevens**.

    ![Een sessie-id ophalen vanuit een browser](media/get-sessionid/mobile.png)

### <a name="when-running-an-embedded-app-or-form"></a>Tijdens het uitvoeren van een ingesloten app of formulier
1. Voer een van deze stappen uit:

    - Klik met de rechtermuisknop op de app of het formulier terwijl u de Alt-toets ingedrukt houdt.
    - Druk gedurende 1-2 seconden met twee vingers op de app of het formulier en laat dan los.

1. Selecteer **Sessiegegevens**.

    ![Een sessie-id ophalen vanuit een ingesloten app](media/get-sessionid/embedded.png)

## <a name="get-an-app-id"></a>Een app-id ophalen
1. [Meld u aan bij PowerApps](https://powerapps.microsoft.com).

1. Selecteer **Apps** aan de linkerkant.

1. Selecteer het weglatingsteken ( **...** ) voor de app met het probleem en selecteer vervolgens **Details**.

    ![Naar de app-details](./media/get-sessionid/details.png)

    U ziet de app-id aan de onderkant van het deelvenster **Details** voor die app.

    ![App-id kopiëren in Details](./media/get-sessionid/app-id.png)
