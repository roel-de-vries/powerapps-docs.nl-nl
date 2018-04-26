---
title: 'Snelstartgids: common Data Service for Apps | Microsoft Docs'
description: Snelstartgids voor het maken van een nieuwe bedrijfsregel
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: bc2822e304c3903275d0e1d4ab1d00ae2b8d8b4b
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-create-a-new-business-rule"></a>Snelstartgids: een nieuwe bedrijfsregel maken

U kunt bedrijfsregels en aanbevelingen maken voor het toepassen van logica en het uitvoeren van validaties zonder dat u daarvoor code hoeft te schrijven of plug-ins hoeft te maken.  Bedrijfsregels bieden een eenvoudige manier om snel veranderende en veelgebruikte regels te implementeren en onderhouden. 
  
 Als u voorwaarden en acties combineert, kunt u de volgende zaken doen met bedrijfsregels:  
  
-   Veldwaarden instellen  
  
-   Veldwaarden wissen  
  
-   Vereisteniveaus voor velden instellen  
  
-   Velden weergeven of verbergen  
  
-   Velden in- of uitschakelen  
  
-   Gegevens valideren en foutberichten weergeven  
  
-   Maak zakelijke aanbevelingen op basis van business intelligence.  
  
## <a name="differences-between-canvas-and-model-driven-apps"></a>Verschillen tussen canvas- en modelgestuurde apps

Voor modelgestuurde apps kunt u alle acties gebruiken die ook voor bedrijfsregels beschikbaar zijn. Voor canvas-apps zijn momenteel niet alle bedrijfsregelacties beschikbaar. De volgende acties zijn **niet** beschikbaar via canvas-apps:

-   Velden weergeven of verbergen  
  
-   Velden in- of uitschakelen  
    
-   Maak zakelijke aanbevelingen op basis van business intelligence.  

## <a name="prerequisites"></a>Vereisten
Als u dit onderwerp wilt volgen, moet u overschakelen naar een [omgeving](../canvas-apps/working-with-environments.md) waarin u entiteiten kunt maken en bewerken.

## <a name="create-a-business-rule"></a>Een bedrijfsregel maken
  
1. Meld u aan bij [PowerApps](https://web.powerapps.com) en klik of tik vervolgens op de pijl omlaag op **Gegevens** bij de linkerrand.

1. In de lijst die wordt weergegeven klikt of tikt u op **Entiteiten**.
  
1. Open de entiteit waarvoor u de bedrijfsregel wilt maken (open bijvoorbeeld de entiteit **Account**) en klik vervolgens op het tabblad **Bedrijfsregels**.  

1.  Klik op **Nieuw**.  
  
     Het venster Bedrijfsregelontwerper wordt geopend. Hierin is één voorwaarde alvast voor u gemaakt. Elke regel begint met een voorwaarde. De bedrijfsregel leidt tot één of meer acties op basis van die voorwaarde.  

    > [!TIP]
    > Als u een bestaande bedrijfsregel wilt bewerken, moet u deze eerst deactiveren. Pas daarna kan de regel worden bewerkt.  
  
1.  Voeg indien gewenst een beschrijving toe in het beschrijvingsvak in de linkerbovenhoek van het venster.  
  
1.  Stel het bereik in op basis van de volgende elementen:  
  
    |||  
    |-|-|  
    |**Als u dit item selecteert...**|**Wordt het bereik ingesteld op...**|  
    |**Entiteit**|Modelgestuurde formulieren en servers|  
    |**Alle formulieren**|Modelgestuurde formulieren|  
    |Specifiek formulier (het formulier **Account**, bijvoorbeeld)|Alleen dat modelgestuurde formulier|  

    > [!TIP]
    > Als u een canvas-app bouwt, moet u Entiteit gebruiken als bereik.
  
1. **Voeg voorwaarden toe.** Meer voorwaarden toevoegen aan uw bedrijfsregel:  
  
    1.  Sleep het onderdeel **Voorwaarde** van het tabblad **Onderdelen** naar een plusteken in de ontwerpfunctie.  
  
        ![Een voorwaarde toevoegen in een bedrijfsregel](./media/data-platform-cds-create-business-rule/add-condition-business-rule.png "Een voorwaarde toevoegen in een bedrijfsregel")  
  
    2.  Als u eigenschappen wilt instellen voor de voorwaarde, klikt u op het onderdeel **Voorwaarde** in het ontwerpfunctievenster. Stel daarna de eigenschappen in op het tabblad **Eigenschappen** aan de rechterzijde van het scherm. Wanneer u eigenschappen instelt, maakt Common Data Service onder aan het tabblad **Eigenschappen** een expressie.  
  
    3.  Als u een aanvullend component (EN of OF) wilt toevoegen aan de voorwaarde, klikt u op **Nieuw** op het tabblad **Eigenschappen** om een nieuwe regel te maken. Daarna stelt u de eigenschappen voor die regel in. In het veld **Regellogica** kunt u opgeven of de nieuwe regel als EN of OF wordt toegevoegd.  
  
        ![Een nieuwe regel toevoegen aan een voorwaarde](./media/data-platform-cds-create-business-rule/add-new-rule-condition.png "Een nieuwe regel toevoegen aan een voorwaarde")  
  
    4.  Wanneer u klaar bent met het instellen van eigenschappen voor de voorwaarde klikt u op **Toepassen**.  
  
9. **Voeg acties toe.** Een actie toevoegen:  
  
    1.  Sleep een van de actieonderdelen van het tabblad **Onderdelen** naar een plusteken naast het onderdeel **Voorwaarde**. Sleep de actie naar een plusteken naast een vinkje als u wilt dat de bedrijfsregel die actie activeert wanneer aan de voorwaarde wordt voldaan, of naar een plustaken naast een x als u wilt dat de bedrijfsregel die actie activeert als er niet aan de voorwaarde wordt voldaan.  
  
        ![Een actie verslepen naar een bedrijfsregel](./media/data-platform-cds-create-business-rule/drag-an-action-business-rule.png "Een actie verslepen naar een bedrijfsregel")  
  
    2.  Als u eigenschappen wilt instellen voor de actie, klikt u op het onderdeel **Actie** in het ontwerpfunctievenster. Stel daarna de eigenschappen in op het tabblad **Eigenschappen**.  
  
    3.  Wanneer u klaar bent met het instellen van eigenschappen klikt u op **Toepassen**.  
  
10. **Voeg een bedrijfsaanbeveling toe. (Alleen modelgestuurd)** Een bedrijfsaanbeveling toevoegen:  
  
    1.  Sleep het onderdeel **Aanbeveling** op het tabblad **Onderdelen** naar een plusteken naast een onderdeel **Voorwaarde**. Sleep het onderdeel **Aanbeveling** naar een plusteken naast een vinkje als u wilt dat de bedrijfsregel die actie activeert wanneer aan de voorwaarde wordt voldaan, of naar een plustaken naast een x als u wilt dat de bedrijfsregel die actie activeert als er niet aan de voorwaarde wordt voldaan.  
  
    2.  Als u eigenschappen wilt instellen voor de aanbeveling, klikt u op het onderdeel **Aanbeveling** in het ontwerpfunctievenster. Stel daarna de eigenschappen in op het tabblad **Eigenschappen**.  
  
    3.  Als u meer acties wilt toevoegen aan de aanbeveling, versleept u ze vanaf het tabblad **Onderdelen** en stelt u de eigenschappen voor elke actie in op het tabblad **Eigenschappen**.  
  
        > [!NOTE]
        >  Wanneer u een aanbeveling maakt, voegt Common Data Service standaard één actie toe. Als u alle acties in een aanbeveling wilt bekijken, klikt u op **Details** in het onderdeel **Aanbeveling**.  
  
    4.  Wanneer u klaar bent met het instellen van eigenschappen klikt u op **Toepassen**.  
  
11. Voor het valideren van de bedrijfsregel klikt u op **Valideren** in de actiebalk.  
  
12. Voor het opslaan van de bedrijfsregel klikt u op **Opslaan** in de actiebalk.  
  
13. Als u de bedrijfsregel wilt activeren, selecteert u deze in het Solution Explorer-venster en klikt u op **Activeren**. U kunt de bedrijfsregel niet activeren vanuit het ontwerpfunctievenster.  
  
> [!TIP]
>  Enkele tips om rekening mee te houden wanneer u in het ontwerpfunctievenster werkt aan bedrijfsregels:  
>   
> - Als u een momentopname wilt maken van alles in het venster Bedrijfsregel, klikt u op **Momentopname** op de actiebalk. Dit is bijvoorbeeld handig als u een bedrijfsregel wilt delen en de mening van een teamlid over de regel wilt verkrijgen.  
> - Gebruik het minioverzicht om snel naar verschillende onderdelen van het proces te navigeren. Dit is handig als u gebruikmaakt van een gecompliceerd proces dat niet volledig in het scherm past.  
> - Als u voorwaarden, acties en bedrijfsaanbevelingen aan uw bedrijfsregel toevoegt, bouwt Common Data Service onder aan het ontwerpfunctievenster de code voor de bedrijfsregel. Deze code heeft het kenmerk Alleen-lezen.  
  
## <a name="localize-error-messages-used-in-business-rules"></a>Foutberichten lokaliseren die in bedrijfsregels worden gebruikt  
 Als u meer dan één taal gebruikt voor uw organisatie, is het een goed idee om de foutberichten die u hebt ingesteld te lokaliseren. Elke keer dat u een bericht instelt, wordt er een label gegenereerd door het systeem. Als u de vertalingen in uw organisatie exporteert, kunt u gelokaliseerde versies van uw berichten toevoegen en de labels daarna weer importeren naar Common Data Service. Op die manier kunnen de mensen die een andere taal dan uw basistaal gebruiken de vertaalde berichten bekijken.  
  