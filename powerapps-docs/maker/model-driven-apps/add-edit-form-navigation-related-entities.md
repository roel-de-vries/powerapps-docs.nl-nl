---
title: Formuliernavigatie voor modelgestuurde apps toevoegen voor gerelateerde entiteiten in PowerApps | MicrosoftDocs
descriptoin: Learn how to add form navigation for related entities
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: b4098c96-bce1-4f57-804f-8694e6254e81
caps.latest.revision: 15
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="add-model-driven-app-form-navigation-for-related-entities"></a>Formuliernavigatie voor modelgestuurde apps toevoegen voor gerelateerde entiteiten

In dit onderwerp gebruikt u het navigatiedeelvenster voor een formulier om koppelingen toe te voegen aan gerelateerde entiteiten. Als een appgebruiker in een record op een van deze koppelingen klikt, wordt de gekoppelde weergave voor de entiteit weergegeven.   
  
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](../model-driven-apps/media/model-driven-switch.png)

    > [!IMPORTANT]
    > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**. 
  
3.  In de lijst opent u een formulier van het type **Hoofd** om dit te bewerken.  
  
4.  Als u een koppeling wilt toevoegen aan een gerelateerde entiteit, klikt u op het tabblad **Start** in de groep **Selecteren** op **Navigatie**.  
  
     Het deelvenster **Relatieverkenner** wordt geopend aan de rechterkant van de formuliereneditor.  
  
5.  Selecteer in het deelvenster **Relatieverkenner**, in de lijst **Filteren**, een van de volgende opties:  
  
    - **Beschikbare relaties**. Geeft alle entiteiten weer die kunnen worden gerelateerd aan de entiteit waaraan het formulier is gekoppeld.  
  
    - **1:N-relaties**. Geeft entiteiten weer die kunnen worden gerelateerd in een 1:N-relatie aan de entiteit waaraan het formulier is gekoppeld.  
  
    - **N:N-relaties**. Geeft entiteiten weer die kunnen worden gerelateerd in een N:N-relatie aan de entiteit waaraan het formulier is gekoppeld.  
  
    > [!NOTE]
    >  Als er geen gerelateerde entiteiten worden weergegeven in het deelvenster **Relatieverkenner**, kunt u op dit formulier geen enkel verband leggen met een gerelateerde entiteit.  
  
6.  Selecteer de gerelateerde entiteit waarmee u een koppeling wilt maken, sleep deze naar het navigatiedeelvenster en zet de entiteit vervolgens neer waar u deze wilt weergeven.  
  
    > [!TIP]
    >  U kunt ook een nieuwe relatie maken door op **Nieuwe 1:N** of **Nieuwe N:N** te klikken of tikken in het deelvenster **Relatieverkenner**.   
  
7. Als u de eigenschappen voor deze of een andere gerelateerde entiteitskoppeling wilt bewerken in het navigatiedeelvenster, selecteert u de koppeling en klikt u op het tabblad **Start** op **Eigenschappen wijzigen**.  
  
8. Typ een nieuw weergavelabel op het tabblad **Weergeven** van het dialoogvenster **Relatie-eigenschappen**.  
  
9. Klik op tik op het tabblad **Naam** op **Bewerken** om de details weer te geven of te bewerken die aan de relatierecord zijn gekoppeld.  
  
10. Kies **OK**.  
  
11. Vooraf bekijken hoe het hoofdformulier wordt weergegeven en hoe gebeurtenissen werken:  
  
    1.  Klik op het tabblad **Start** op **Voorbeeld** en selecteer vervolgens **Formulier maken**, **Formulier bijwerken** of **Alleen-lezen formulier**.  
  
    2.  Als u het formulier **Voorbeeld** wilt sluiten, klikt u in het menu **Bestand** op **Sluiten**.  
  
12. Klik op **Opslaan en sluiten** als u klaar bent met het bewerken van het formulier en het wilt sluiten.  
  
13. Als de aanpassingen zijn voltooid, publiceert u deze:  
  
    -   Als u aanpassingen voor alleen het onderdeel dat u momenteel bewerkt wilt publiceren, klikt of tikt u in het navigatiedeelvenster op de entiteit waaraan u hebt gewerkt en klikt of tikt u op **Publiceren**.  
  
    -   Als u aanpassingen wilt publiceren voor alle niet-gepubliceerde onderdelen tegelijk, kiest u in het navigatiedeelvenster **Entiteiten** en kiest u vervolgens op de opdrachtbalk **Alle aanpassingen publiceren**.  
  
> [!NOTE]
> Het installeren van een oplossing of publiceren van aanpassingen kan de normale werking van het systeem onderbreken. We adviseren u om het importeren van een oplossing te plannen wanneer dit minimale gevolgen heeft voor gebruikers.
  
## <a name="next-steps"></a>Volgende stappen  
 [Entiteitsrelaties maken en bewerken voor Common Data Service voor Apps](../common-data-service/create-edit-entity-relationships.md)
