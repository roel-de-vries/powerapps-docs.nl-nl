---
title: Een bedrijfsregel maken in Common Data Service voor Apps | Microsoft Docs
description: Stapsgewijze instructies voor het maken van een bedrijfsregel in Common Data Service (CDS) voor Apps.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-business-rule-for-an-entity"></a>Een bedrijfsregel maken voor een entiteit

U kunt bedrijfsregels en aanbevelingen maken om logica en validaties toe te passen zonder code te schrijven of invoegtoepassingen te maken. Bedrijfsregels bieden een eenvoudige interface om snelveranderende en veelgebruikte regels te implementeren en te onderhouden. 
  
Door voorwaarden en acties te combineren kunt u het volgende doen met bedrijfsregels:  
  
* Veldwaarden instellen  
* Veldwaarden wissen  
* Veldvereistenniveaus instellen  
* Velden weergeven of verbergen  
* Velden inschakelen of uitschakelen  
* Gegevens valideren en foutberichten weergeven  
* Bedrijfsaanbevelingen maken op basis van bedrijfsinformatie.  
  
## <a name="differences-between-canvas-and-model-driven-apps"></a>Verschillen tussen canvasapps en modelgestuurde apps

Modelgestuurde apps kunnen alle acties gebruiken die beschikbaar zijn voor bedrijfsregels, maar momenteel zijn niet alle bedrijfsregelacties beschikbaar in canvasapps. De volgende acties zijn **niet** beschikbaar in canvasapps:

* Velden weergeven of verbergen  
* Velden inschakelen of uitschakelen  
* Bedrijfsaanbevelingen maken op basis van bedrijfsinformatie.  

## <a name="prerequisites"></a>Vereisten
Als u dit onderwerp wilt volgen, moet u overschakelen naar een [omgeving](../canvas-apps/working-with-environments.md) waarin u entiteiten kunt maken en bewerken.

## <a name="create-a-business-rule"></a>Een bedrijfsregel maken
  
1. Meld u aan bij [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) en klik of tik vervolgens op de pijl-omlaag voor **Gegevens** nabij de linkerrand.

2. Klik of tik in de lijst die verschijnt op **Entiteiten**.
  
3. Open de entiteit waarvoor u de bedrijfsregel wilt maken (open bijvoorbeeld de entiteit **Account**) en klik vervolgens op het tabblad **Bedrijfsregels**.  

4. Klik op **Nieuw**.  
  
    Het ontwerpvenster Bedrijfsregel wordt geopend met één voorwaarde die al voor u is gemaakt. Elke regel start aan een voorwaarde. De bedrijfsregel bestaat uit een of meer acties die op deze voorwaarde zijn gebaseerd.  

    > [!TIP]
    > Als u een bestaande bedrijfsregel wilt wijzigen, moet u deze deactiveren voordat u deze kunt bewerken.  
  
5. Voeg eventueel een beschrijving toe in het veld Beschrijving in de linkerbovenhoek van het venster.
  
6. Voer het bereik in, op basis van het volgende opties:  
  
    |||  
    |-|-|  
    |**Als u dit item selecteert...**|**Wordt het bereik ingesteld op...**|  
    |**Entiteit**|Modelgestuurde formulieren en server|  
    |**Alle formulieren**|Modelgestuurde formulieren|  
    |Bepaald formulier (bijvoorbeeld **Account** )|Alleen dat modelgestuurde formulier|  

    > [!TIP]
    > Als u een canvasapp maakt, moet u entiteit als het bereik gebruiken.
  
7. **Voorwaarde toevoegen.** Meer voowaarden aan uw bedrijfsregel toevoegen:  
  
    1. Sleep het onderdeel **Voorwaarde** van het tabblad **Onderdelen**naar een plusteken in de ontwerper.  
  
        ![Een voorwaarde aan een bedrijfsregel toevoegen](./media/data-platform-cds-create-business-rule/add-condition-business-rule.png "Een voorwaarde aan een bedrijfsregel toevoegen")  
  
    2. Als u eigenschappen voor de voorwaarde wilt instellen, klikt u op het onderdeel **Voorwaarde** in het onttwerpvenster en stelt u eigenschappen in op het tabblad **Eigenschappen** aan de rechterkant van het venster. Als u eigenschappen instelt, wordt in Common Data Service een expressie gemaakt onder aan het tabblad **Eigenschappen**.  
  
    3. Als u een extra component (EN of OF) aan de voorwaarde wilt toevoegen, klikt u op **Nieuw** in het tabblad **Eigenschappen** om een nieuwe regel te maken en stelt u de eigenschappen voor deze regel in. In het veld **Regellogica** kunt u opgeven of u de nieuwe regel wilt toevoegen als EN of OF.  
  
        ![Een nieuwe regel toevoegen aan een voorwaarde](./media/data-platform-cds-create-business-rule/add-new-rule-condition.png "Een nieuwe regel toevoegen aan een voorwaarde")  
  
    4. Als u de eigenschappen voor de voorwaarde hebt ingesteld, klikt u op **Toepassen**.  
  
8. **Acties toevoegen.** Een actie toevoegen:  
  
    1. Sleep een van de actie-onderdelen van het tabblad **Onderdelen** naar een plusteken naast **Voorwaarde**. Sleep de actie naar een plusteken naast een vinkje als u wilt dat de bedrijfsregel die actie uitvoert wanneer aan de voorwaarde is voldaan. Of naar een plusteken naast een x als u wilt dat de bedrijfsregel actie onderneemt als niet aan de voorwaarde wordt voldaan.
  
        ![Sleep een actie naar een bedrijfsregel](./media/data-platform-cds-create-business-rule/drag-an-action-business-rule.png "Sleep een actie naar een bedrijfsregel")  
  
    2. Als u eigenschappen voor de actie wilt instellen, klikt u op het onderdeel **Actie** in het onttwerpvenster en stelt u eigenschappen in op het tabblad **Eigenschappen**.  
  
    3. Als u de eigenschappen hebt ingesteld, klikt u op **Toepassen**.  
  
9. **Een bedrijfsaanbeveling toevoegen. (alleen modelgestuurd)** Een bedrijfsaanbeveling toevoegen:  
  
    1. Sleep het onderdeel **Aanbeveling** van het tabblad **Onderdelen** naar een plusteken naast een onderdeel **Voorwaarde**. Sleep onderdeel **Aanbeveling** naar een plusteken naast een vinkje als u wilt dat de bedrijfsregel die actie uitvoert wanneer aan de voorwaarde is voldaan. Of naar een plusteken naast een x als u wilt dat de bedrijfsregel actie onderneemt als niet aan de voorwaarde wordt voldaan.  
  
    2. Als u eigenschappen voor de aanbeveling wilt instellen, klikt u op het onderdeel **Aanbeveling** in het onttwerpvenster en stelt u eigenschappen in op het tabblad **Eigenschappen**.  
  
    3. Om meer acties aan de aanbeveling toe te voegen, sleept u deze van het tabblad **Onderdelen**, en stelt u vervolgens eigenschappen in voor elke actie in het tabblad **Eigenschappen**.  
  
        > [!NOTE]
        >  Als u een aanbeveling maakt, wordt in Common Data Service standaard één actie toegevoegd. Als u alle acties in een aanbeveling wilt zien, klikt u op **Details** in het onderdeel **Aanbeveling**.  
  
    4. Als u de eigenschappen hebt ingesteld, klikt u op **Toepassen**.  
  
10. Als u de bedrijfsregel wilt valideren, klikt u op **Valideren** op de actiebalk.  
  
11. Als u de bedrijfsregel wilt opslaan, klikt u op **Opslaan** op de actiebalk.  
12. Om de bedrijfsregel te activeren, selecteert u deze in het venster Oplossingenverkenner en klikt u vervolgens op **Activeren**. U kunt de bedrijfsregel niet uit het ontwerpvenster activeren.  
  
    > [!TIP]
    >  Hier volgt een aantal tips om rekening mee te houden terwijl u in het ontwerpervenster aan bedrijfsregels werkt:  
    >   
    > - Als u een momentopname van alles in het venster Bedrijfsregels wilt maken, klikt u op de actiebalk op **Momentopname**. Dit is bijvoorbeeld nuttig als u de opmerkingen op de bedrijfsregel van een teamlid wilt delen en ontvangen.  
    > - Met de minikaart navigeert u snel naar de verschillende onderdelen van het proces. Dit is handig als u een gecompliceerd proces hebt dat van het scherm schuift.  
    > - Als u voorwaarden, acties en bedrijfsaanbevelingen toevoegt aan uw bedrijfsregel, wordt in Common Data Service de code voor de bedrijfsregel onder aan de ontwerper gemaakt. Deze code is alleen-lezen.  
  
## <a name="localize-error-messages-used-in-business-rules"></a>Foutberichten die in bedrijfsregels worden gebruikt lokaliseren  
 Als u meer dan één taal hebt voor uw organisatie, dan wilt u foutberichten lokaliseren die u hebt ingesteld. Telkens wanneer u een bericht instelt, wordt een label een door het systeem gemaakt. Als u in uw organisatie de vertalingen exporteert, dan kunt u gelokaliseerde versies van uw berichten toevoegen en vervolgens deze labels weer importeren in Common Data Service, zodat de gebruikers die andere talen dan uw standaardtaal gebruiken, de vertaalde berichten kunnen zien.  
  
