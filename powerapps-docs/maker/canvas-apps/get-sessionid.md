---
title: Een sessie-id of een app-id ophalen | Microsoft Docs
description: Lees hoe u een sessie-id of een app-id ophaalt voor het oplossen van problemen in PowerApps
author: AFTOwen
ms.service: powerapps
ms.topic: conceptual
ms.component: canvas
ms.date: 06/18/2018
ms.author: anneta, brimcg
ms.openlocfilehash: add591d1bf565f3ad89e0138257fdf365d6add8e
ms.sourcegitcommit: 1126caa4c7516cd4dffcff7e0c3eca440a333a58
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/21/2018
ms.locfileid: "36304679"
---
# <a name="get-a-session-id-or-an-app-id"></a>Een sessie-id of een app-id ophalen
Als er een probleem is met een app die is gemaakt in PowerApps, kan Microsoft het probleem veel efficiënter oplossen als u beschikt over een sessie-id, een app-id of beide id's.

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
