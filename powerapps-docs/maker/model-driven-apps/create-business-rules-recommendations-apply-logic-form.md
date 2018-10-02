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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="tutorial-create-business-rules-and-recommendations-to-apply-logic-in-a-model-driven-app-form"></a>Zelfstudie: Bedrijfsregels en aanbevelingen maken om logica in een formulier voor modelgestuurde apps toe te passen

In deze zelfstudie leert u hoe u bedrijfsregels en aanbevelingen maakt om formulierlogica toe te passen zonder JavaScript-code te schrijven of invoegtoepassingen te maken. De bedrijfsregels bieden een eenvoudige interface om snelveranderende en veelgebruikte regels te implementeren en te onderhouden. Ze kunnen worden toegepast op hoofdformulieren en formulieren voor snelle invoer en werken in PowerApps-apps, Dynamics 365 Customer Engagement-webapps, Dynamics 365 for tablets en Dynamics 365 for Outlook (online of offline).  
  
 Door voorwaarden en acties te combineren kunt u het volgende doen met bedrijfsregels:  
  
-   Veldwaarden instellen  
  
-   Veldwaarden wissen  
  
-   Veldvereistenniveaus instellen  
  
-   Velden weergeven of verbergen  
  
-   Velden inschakelen of uitschakelen  
  
-   Gegevens valideren en foutberichten weergeven  
  
-   Bedrijfsaanbevelingen maken op basis van bedrijfsinformatie.  
  
## <a name="create-a-business-rule-or-business-recommendation"></a>Een bedrijfsregel of bedrijfsaanbeveling maken
  
1. Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).  
  
2.  Open de entiteit die u voor de bedrijfsregel (bijvoorbeeld **Account**) wilt maken en dubbelklik op **Bedrijfsregels**.  
  
 ![Een bedrijfsregel maken in de standaardoplossing](media/create-business-rule-the-default-solution.png "Een bedrijfsregel maken in de standaardoplossing")  
  
3.  Selecteer **Nieuw**.  
  
     Het ontwerpvenster Bedrijfsregel wordt geopend met één voorwaarde die al voor u is gemaakt. Elke regel start aan een voorwaarde. De bedrijfsregel bestaat uit een of meer acties die op deze voorwaarde zijn gebaseerd.  
  
 ![Ontwerpvenster bedrijfsregels](media/business-rules-design-window.png "Ontwerpvenster bedrijfsregels")  
  
   > [!TIP]
> Als u een bestaande bedrijfsregel wilt wijzigen, moet u deze deactiveren voordat u deze kunt bewerken.

4.  Voeg eventueel een beschrijving toe in het veld Beschrijving in de linkerbovenhoek van het venster.  
  
5.  Voer het bereik in, op basis van het volgende opties:  
  
    |||  
    |-|-|  
    |**Als u dit item selecteert...**|**Wordt het bereik ingesteld op...**|  
    |**Entiteit**|Alle formulieren en server|  
    |**Alle formulieren**|Alle formulieren|  
    |Bepaald formulier (bijvoorbeeld **Account** )|Alleen dat formulier|  
  
6. **Voorwaarde toevoegen.** Meer voowaarden aan uw bedrijfsregel toevoegen:  
  
    1.  Sleep het onderdeel **Voorwaarde** van het tabblad **Onderdelen**naar een plusteken in de ontwerper.  
  
        ![Een voorwaarde aan een bedrijfsregel toevoegen](media/add-condition-business-rule.png "Een voorwaarde aan een bedrijfsregel toevoegen")  
  
    2.  Als u eigenschappen voor de voorwaarde wilt instellen, klikt u op het onderdeel **Voorwaarde** in het onttwerpvenster en stelt u eigenschappen in op het tabblad **Eigenschappen** aan de rechterkant van het venster. Als u eigenschappen instelt, wordt er een expressie onder aan het tabblad **Eigenschappen** gemaakt.  
  
    3.  Als u een extra component (EN of OF) aan de voorwaarde wilt toevoegen, klikt u op **Nieuw** in het tabblad **Eigenschappen** om een nieuwe regel te maken en stelt u de eigenschappen voor deze regel in. In het veld **Regellogica** kunt u opgeven of u de nieuwe regel wilt toevoegen als EN of OF.  
  
        ![Een nieuwe regel toevoegen aan een voorwaarde](media/add-new-rule-condition.png "Een nieuwe regel toevoegen aan een voorwaarde")  
  
    4.  Als u de eigenschappen voor de voorwaarde hebt ingesteld, klikt u op **Toepassen**.  
  
7. **Acties toevoegen.** Een actie toevoegen:  
  
    1.  Sleep een van de actie-onderdelen van het tabblad **Onderdelen** naar een plusteken naast **Voorwaarde**. Sleep de actie naar een plusteken naast een vinkje als u wilt dat de bedrijfsregel die actie uitvoert wanneer aan de voorwaarde is voldaan. Of naar een plusteken naast een x als u wilt dat de bedrijfsregel actie onderneemt als niet aan de voorwaarde wordt voldaan.  
  
        ![Sleep een actie naar een bedrijfsregel](media/drag-an-action-business-rule.png "Sleep een actie naar een bedrijfsregel")  
  
    2.  Als u eigenschappen voor de actie wilt instellen, klikt u op het onderdeel **Actie** in het onttwerpvenster en stelt u eigenschappen in op het tabblad **Eigenschappen**.  
  
    3.  Als u de eigenschappen hebt ingesteld, klikt u op **Toepassen**.  
  
8. **Bedrijfsaanbeveling toevoegen.** Een bedrijfsaanbeveling toevoegen:  
  
    1.  Sleep het onderdeel **Aanbeveling** van het tabblad **Onderdelen** naar een plusteken naast een onderdeel **Voorwaarde**. Sleep onderdeel **Aanbeveling** naar een plusteken naast een vinkje als u wilt dat de bedrijfsregel die actie uitvoert wanneer aan de voorwaarde is voldaan. Of naar een plusteken naast een x als u wilt dat de bedrijfsregel actie onderneemt als niet aan de voorwaarde wordt voldaan.  
  
    2.  Als u eigenschappen voor de aanbeveling wilt instellen, klikt u op het onderdeel **Aanbeveling** in het onttwerpvenster en stelt u eigenschappen in op het tabblad **Eigenschappen**.  
  
    3.  Om meer acties aan de aanbeveling toe te voegen, sleept u deze van het tabblad **Onderdelen**, en stelt u vervolgens eigenschappen in voor elke actie in het tabblad **Eigenschappen**.  
  
        > [!NOTE]
        >  Als u een aanbeveling hebt gemaakt, wordt standaard één actie toegevoegd. Als u alle acties in een aanbeveling wilt zien, klikt u op **Details** in het onderdeel **Aanbeveling**.  
  
    4.  Als u de eigenschappen hebt ingesteld, klikt u op **Toepassen**.  
  
9. Als u de bedrijfsregel wilt valideren, klikt u op **Valideren** op de actiebalk.  
  
10. Als u de bedrijfsregel wilt opslaan, klikt u op **Opslaan** op de actiebalk.  
  
11. Om de bedrijfsregel te activeren, selecteert u deze in het venster Oplossingenverkenner en klikt u vervolgens op **Activeren**. U kunt de bedrijfsregel niet uit het ontwerpvenster activeren.  
  
> [!TIP]
>  Hier volgt een aantal tips om rekening mee te houden terwijl u in het ontwerpervenster aan bedrijfsregels werkt:  
>   
> - Als u een momentopname van alles in het venster Bedrijfsregels wilt maken, klikt u op de actiebalk op **Momentopname**. Dit is bijvoorbeeld nuttig als u de opmerkingen op de bedrijfsregel van een teamlid wilt delen en ontvangen.  
> - Met de minikaart navigeert u snel naar de verschillende onderdelen van het proces. Dit is handig als u een gecompliceerd proces hebt dat van het scherm schuift.  
> - Als u voorwaarden, acties en bedrijfsaanbevelingen toevoegt aan uw bedrijfsregel, wordt er code voor de bedrijfsregel gemaakt en deze wordt onder in het ontwerpervenster weergegeven. Deze code is alleen lezen.  
  
<a name="BKMK_LocalizingErrorMessages"></a>   
## <a name="localize-error-messages-used-in-business-rules"></a>Foutberichten die in bedrijfsregels worden gebruikt lokaliseren  
 Als u meer dan één taal hebt voor uw organisatie, dan wilt u foutberichten lokaliseren die u hebt ingesteld. Telkens wanneer u een bericht instelt, wordt een label een door het systeem gemaakt. Als u in uw organisatie de vertalingen exporteert, dan kunt u gelokaliseerde versies van uw berichten toevoegen en vervolgens deze labels weer importeren in het systeem, zodat de gebruikers die andere talen dan uw standaardtaal gebruiken de vertaalde berichten kunnen zien.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Een aangepaste bedrijfslogica maken door middel van processen](guide-staff-through-common-tasks-processes.md)   
 [Een nieuw bedrijfsprocesstroom maken](/flow/create-business-process-flow)   

