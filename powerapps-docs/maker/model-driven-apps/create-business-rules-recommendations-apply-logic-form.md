---
title: Bedrijfsregels en aanbevelingen voor modelgestuurde apps maken | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 00e62904-2ce9-4730-a113-02b1fedbf22e
caps.latest.revision: 31
author: Mattp123
ms.author: matp
manager: kvivek
tags:
- PowerApps maker portal impact
ms.openlocfilehash: c1a132648a63845c42cde8a80636d0e87e10a328
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677140"
---
# <a name="tutorial-create-business-rules-and-recommendations-to-apply-logic-in-a-model-driven-app-form"></a>Zelfstudie: Bedrijfsregels en aanbevelingen maken om logica toe te passen in een modelgestuurde-appformulier

In deze zelfstudie leert u hoe u bedrijfsregels en aanbevelingen maakt om formulierlogica toe te passen zonder JavaScript-code te schrijven of invoegtoepassingen te maken.  Bedrijfsregels bieden een eenvoudige manier om snel veranderende en veelgebruikte regels te implementeren en onderhouden. Ze kunnen worden toegepast op hoofdformulieren en formulieren voor snelle invoer, en ze werken in PowerApps-apps, Dynamics 365 Customer Engagement-web-apps, Dynamics 365 voor tablets en Dynamics 365 voor Outlook (online en offline).  
  
 Als u voorwaarden en acties combineert, kunt u de volgende zaken doen met bedrijfsregels:  
  
-   Veldwaarden instellen  
  
-   Veldwaarden wissen  
  
-   Vereisteniveaus voor velden instellen  
  
-   Velden weergeven of verbergen  
  
-   Velden in- of uitschakelen  
  
-   Gegevens valideren en foutberichten weergeven  
  
-   Maak zakelijke aanbevelingen op basis van business intelligence.  
  
## <a name="create-a-business-rule-or-business-recommendation"></a>Een bedrijfsregel of bedrijfsaanbeveling maken
  
1. Open [Solution Explorer](advanced-navigation.md#solution-explorer).  
  
2.  Open de entiteit waarvoor u de bedrijfsregel wilt maken (open bijvoorbeeld de entiteit **Account**) en dubbelklik vervolgens op **Bedrijfsregels**.  
  
 ![Een bedrijfsregel maken in de standaardoplossing](media/create-business-rule-the-default-solution.png "Een bedrijfsregel maken in de standaardoplossing")  
  
3.  Selecteer **Nieuw**.  
  
     Het venster Bedrijfsregelontwerper wordt geopend. Hierin is één voorwaarde alvast voor u gemaakt. Elke regel begint met een voorwaarde. De bedrijfsregel leidt tot één of meer acties op basis van die voorwaarde.  
  
 ![Venster Bedrijfsregels ontwerpen](media/business-rules-design-window.png "Venster Bedrijfsregels ontwerpen")  
  
   > [!TIP]
> Als u een bestaande bedrijfsregel wilt bewerken, moet u deze eerst deactiveren. Pas daarna kan de regel worden bewerkt.

4.  Voeg indien gewenst een beschrijving toe in het beschrijvingsvak in de linkerbovenhoek van het venster.  
  
5.  Stel het bereik in op basis van de volgende elementen:  
  
    |||  
    |-|-|  
    |**Als u dit item selecteert...**|**Wordt het bereik ingesteld op...**|  
    |**Entiteit**|Alle formulieren en server|  
    |**Alle formulieren**|Alle formulieren|  
    |Specifiek formulier (het formulier **Account**, bijvoorbeeld)|Alleen dat formulier|  
  
6. **Voeg voorwaarden toe.** Meer voorwaarden toevoegen aan uw bedrijfsregel:  
  
    1.  Sleep het onderdeel **Voorwaarde** van het tabblad **Onderdelen** naar een plusteken in de ontwerpfunctie.  
  
        ![Een voorwaarde toevoegen in een bedrijfsregel](media/add-condition-business-rule.png "Een voorwaarde toevoegen in een bedrijfsregel")  
  
    2.  Als u eigenschappen wilt instellen voor de voorwaarde, klikt u op het onderdeel **Voorwaarde** in het ontwerpfunctievenster. Stel daarna de eigenschappen in op het tabblad **Eigenschappen** aan de rechterzijde van het scherm. Wanneer u eigenschappen instelt, wordt onderaan het tabblad **Eigenschappen** een expressie gemaakt.  
  
    3.  Als u een aanvullend component (EN of OF) wilt toevoegen aan de voorwaarde, klikt u op **Nieuw** op het tabblad **Eigenschappen** om een nieuwe regel te maken. Daarna stelt u de eigenschappen voor die regel in. In het veld **Regellogica** kunt u opgeven of de nieuwe regel als EN of OF wordt toegevoegd.  
  
        ![Een nieuwe regel toevoegen aan een voorwaarde](media/add-new-rule-condition.png "Een nieuwe regel toevoegen aan een voorwaarde")  
  
    4.  Wanneer u klaar bent met het instellen van eigenschappen voor de voorwaarde klikt u op **Toepassen**.  
  
7. **Voeg acties toe.** Een actie toevoegen:  
  
    1.  Sleep een van de actieonderdelen van het tabblad **Onderdelen** naar een plusteken naast het onderdeel **Voorwaarde**. Sleep de actie naar een plusteken naast een vinkje als u wilt dat de bedrijfsregel die actie activeert wanneer aan de voorwaarde wordt voldaan, of naar een plustaken naast een x als u wilt dat de bedrijfsregel die actie activeert als er niet aan de voorwaarde wordt voldaan.  
  
        ![Een actie verslepen naar een bedrijfsregel](media/drag-an-action-business-rule.png "Een actie verslepen naar een bedrijfsregel")  
  
    2.  Als u eigenschappen wilt instellen voor de actie, klikt u op het onderdeel **Actie** in het ontwerpfunctievenster. Stel daarna de eigenschappen in op het tabblad **Eigenschappen**.  
  
    3.  Wanneer u klaar bent met het instellen van eigenschappen klikt u op **Toepassen**.  
  
8. **Voeg een bedrijfsaanbeveling toe.** Een bedrijfsaanbeveling toevoegen:  
  
    1.  Sleep het onderdeel **Aanbeveling** op het tabblad **Onderdelen** naar een plusteken naast een onderdeel **Voorwaarde**. Sleep het onderdeel **Aanbeveling** naar een plusteken naast een vinkje als u wilt dat de bedrijfsregel die actie activeert wanneer aan de voorwaarde wordt voldaan, of naar een plustaken naast een x als u wilt dat de bedrijfsregel die actie activeert als er niet aan de voorwaarde wordt voldaan.  
  
    2.  Als u eigenschappen wilt instellen voor de aanbeveling, klikt u op het onderdeel **Aanbeveling** in het ontwerpfunctievenster. Stel daarna de eigenschappen in op het tabblad **Eigenschappen**.  
  
    3.  Als u meer acties wilt toevoegen aan de aanbeveling, versleept u ze vanaf het tabblad **Onderdelen** en stelt u de eigenschappen voor elke actie in op het tabblad **Eigenschappen**.  
  
        > [!NOTE]
        >  Wanneer u een aanbeveling maakt, wordt standaard één actie toegevoegd. Als u alle acties in een aanbeveling wilt bekijken, klikt u op **Details** in het onderdeel **Aanbeveling**.  
  
    4.  Wanneer u klaar bent met het instellen van eigenschappen klikt u op **Toepassen**.  
  
9. Voor het valideren van de bedrijfsregel klikt u op **Valideren** in de actiebalk.  
  
10. Voor het opslaan van de bedrijfsregel klikt u op **Opslaan** in de actiebalk.  
  
11. Als u de bedrijfsregel wilt activeren, selecteert u deze in het Solution Explorer-venster en klikt u op **Activeren**. U kunt de bedrijfsregel niet activeren vanuit het ontwerpfunctievenster.  
  
> [!TIP]
>  Enkele tips om rekening mee te houden wanneer u in het ontwerpfunctievenster werkt aan bedrijfsregels:  
>   
> - Als u een momentopname wilt maken van alles in het venster Bedrijfsregel, klikt u op **Momentopname** op de actiebalk. Dit is bijvoorbeeld handig als u een bedrijfsregel wilt delen en de mening van een teamlid over de regel wilt verkrijgen.  
> - Gebruik het minioverzicht om snel naar verschillende onderdelen van het proces te navigeren. Dit is handig als u gebruikmaakt van een gecompliceerd proces dat niet volledig in het scherm past.  
> - Als u voorwaarden, acties en bedrijfsaanbevelingen aan uw bedrijfsregel toevoegt, wordt onder in het ontwerpvenster de code voor de bedrijfsregel gebouwd en weergegeven. Deze code heeft het kenmerk Alleen-lezen.  
  
<a name="BKMK_LocalizingErrorMessages"></a>   
## <a name="localize-error-messages-used-in-business-rules"></a>Foutberichten lokaliseren die in bedrijfsregels worden gebruikt  
 Als u meer dan één taal gebruikt voor uw organisatie, is het een goed idee om de foutberichten die u hebt ingesteld te lokaliseren. Elke keer dat u een bericht instelt, wordt er een label gegenereerd door het systeem. Als u de vertalingen in uw organisatie exporteert, kunt u gelokaliseerde versies van uw berichten toevoegen en de labels daarna weer importeren in het systeem. Op die manier kunnen de mensen die een andere taal dan uw basistaal gebruiken de vertaalde berichten bekijken.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Aangepaste bedrijfslogica maken met processen](guide-staff-through-common-tasks-processes.md)   
 [Een bedrijfsprocesstroom maken](/flow/create-business-process-flow)   

