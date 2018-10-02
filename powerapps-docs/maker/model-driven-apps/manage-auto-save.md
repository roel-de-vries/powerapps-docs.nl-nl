---
title: Automatisch opslaan in een modelgestuurde app uitschakelen met PowerApps | MicrosoftDocs
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
author: Mattp123
ms.assetid: 2e7f75dd-7a3f-4716-b995-b626929c0501
caps.latest.revision: 14
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="disable-auto-save-in-a-model-driven-app"></a>Automatisch opslaan in een modelgestuurde app uitschakelen

Automatisch opslaan stelt appgebruikers in staat zich op hun werk te richten zonder dat het opslaan van gegevens in het formulier nodig is. De meeste mensen zullen het waarderen dat ze niet handmatig hun gegevens hoeven op te slaan wanneer ze een veld bijwerken, maar sommige organisaties hebben misschien aanpassingen die met handmatig opslaan in het achterhoofd zijn ontworpen. Voor deze organisaties zijn er opties om te beheren van hoe automatisch opslaan wordt toegepast.  
  
<a name="BKMK_HowAutoSaveWorks"></a>   

## <a name="how-auto-save-works"></a>Hoe automatisch opslaan werkt  
 Standaard wordt bij alle hoofdformulieren voor [Bijgewerkte entiteiten](create-design-forms.md#updated-versus-classic-entities) automatisch opslaan ingeschakeld. Nadat een record is gemaakt (eerst opgeslagen), worden wijzigingen aan een formulier dertig seconden nadat de wijziging is ingevoerd automatisch opgeslagen. Als er geen wijzigingen in het formulier worden gemaakt, wordt er niets automatisch opgeslagen zolang het formulier nog is geopend. Als een wijziging wordt aangebracht, begint de teller voor de 30-secondeperiode weer opnieuw. Het veld dat iemand momenteel bewerkt is niet opgenomen in automatisch opslaan. Als iemand anders hetzelfde veld heeft bijgewerkt terwijl u het aan bewerken bent, worden die wijzigingen teruggezet en weergegeven in het formulier wanneer het formulier automatisch wordt opgeslagen.  
  
 Als automatisch opslaan is ingeschakeld, verschijnt de knop Opslaan alleen als u de record voor het eerst opslaat. Nadat de record is gemaakt, wordt de knop Opslaan in de opdrachtbalk niet weergegeven, maar u kunt een knop ![Knop Automatisch opslaan](media/auto-save-icon.png "Knop Automatisch opslaan") in de rechterbenedenhoek zien die wordt weergegeven als er onopgeslagen wijzigingen zijn. Dit besturingselement wordt ook weergegeven als automatisch opslaan is uitgeschakeld.  
  
 U kunt deze knop selecteren om de record op te slaan en gegevens in het formulier direct te vernieuwen. Wanneer automatisch opslaan is ingeschakeld, wordt de record opgeslagen wanneer u ervan weg navigeert of wanneer u een apart venster sluit waarin een record weergegeven. De knop **Opslaan en sluiten** is niet nodig, die wordt weergegeven in formulieren voor entiteiten die niet worden bijgewerkt.  
  
<a name="BKMK_AutoSave"></a>   
## <a name="should-you-disable-auto-save"></a>Moet u automatisch opslaan uitschakelen?  
 Als u invoegtoepassingen, workflows of formulierscripts hebt die uitgevoerd worden wanneer een record wordt opgeslagen, kunnen deze worden uitgevoerd wanneer automatisch opslaan in werking treedt. Dit kan leiden tot ongewenste gedragingen als deze uitbreidingen niet zijn ontworpen om te werken met automatisch opslaan. De invoegtoepassingen, workflows, en de formulierscripts moeten zijn ontworpen om bepaalde wijzigingen te zoeken en niet elke keer dat er iets wordt opgeslagen worden uitgevoerd, of u automatisch opslaan nu wel of niet hebt ingeschakeld.  
  
 Als u de controle voor een entiteit hebt geconfigureerd, wordt elk opslaan afgehandeld als een afzonderlijke update. Als iemand een formulier met onopgeslagen wijzigingen meer dan een halve minuut bekijkt, ziet u een extra waarde mits die persoon meer gegevens heeft toegevoegd nadat automatisch opslaan is uitgevoerd. Als u rapporten hebt die afhankelijk zijn van datacontrole en elke individuele opslagopdracht als een individuele aanpassing aan het bestand behandelen, dan kan het aantal aanpassingen stijgen. Als u deze benadering gebruikt, moet u er rekening mee houden dat het gedrag van individuele gebruikers onbetrouwbare resultaten oplevert, of u automatisch opslaan nu wel of niet hebt ingeschakeld.  
  
<a name="BKMK_DisableAutoSaveOrg"></a>   
## <a name="disable-auto-save-for-the-organization"></a>Automatisch opslaan uitschakelen voor een organisatie  
 Als u vaststelt dat automatisch opslaan problemen met extensies veroorzaakt, kunt u de functie voor uw organisatie uitschakelen. Er bestaat geen optie om automatisch opslaan voor afzonderlijke entiteiten of formulieren uit te schakelen.  
  
1. Ga naar **[Instellingen](advanced-navigation.md#settings)** > **Beheer**.  
  
2.  Kies **Systeeminstellingen**.  
  
3.  Voor de optie **Automatisch opslaan voor alle formulieren inschakelen** selecteert u **Nee**.  
  
<a name="BKMK_DisalbleAutoSaveForm"></a>   
## <a name="disable-auto-save-for-a-form"></a>Automatisch opslaan voor een formulier uitschakelen  
 Als u automatisch opslaan voor specifieke entiteitformulieren wilt uitschakelen, kunt u code aan the gebeurtenis `OnSave` in een entiteit toevoegen.  
  
> [!NOTE]
>  Automatisch opslaan wordt voor het formulier uitgeschakeld, maar de gegevens worden alsnog opgeslagen wanneer de knop ![Automatisch opslaan](media/auto-save-icon.png "Automatisch opslaan") in de rechterbenedenhoek wordt geselecteerd. Als u bij een formulier probeert weg te gaan of een formulier probeert te sluiten waarin gegevens zijn gewijzigd, wordt gevraagd of de wijzigingen moeten worden opgeslagen voordat de gebruiker bij het formulier weg kan gaan of het formulier kan sluiten.  
  
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](../model-driven-apps/media/model-driven-switch.png)

2.  Vouw **Gegevens** uit, selecteer **Entiteiten**, selecteer de gewenste entiteit en selecteer het tabblad **Formulieren**.  
  
3.  Open het formulier dat u wilt bewerken.  
  
4.  Maak een JavaScript-webresource en voeg deze toe aan het formulier:  
  
    1.  Kies in de formuliereneditor in de groep **Formulier** de optie **Formuliereigenschappen**.  
  
    2.  Kies op het tabblad **Gebeurtenissen** onder **Formulierbibliotheken** de optie **Toevoegen**.  
  
    3.  Selecteer in het dialoogvenster **Record opzoeken** de optie **Nieuw**.  
  
    4.  Voer de volgende gegevens in het webresourceformulier in:  
  
        |||  
        |-|-|  
        |**Naam**|preventAutoSave|  
        |**Weergavenaam**|Automatisch opslaan verhinderen|  
        |**Type**|Script (JScript)|  
  
    5.  Kies naast het veld **Type** de optie **Teksteditor**.  
  
    6.  Plak de volgende code in het veld **Bron**:  
  
        ```javascript  
        function preventAutoSave(econtext) {  
            var eventArgs = econtext.getEventArgs();  
            if (eventArgs.getSaveMode() == 70 || eventArgs.getSaveMode() == 2) {  
                eventArgs.preventDefault();  
            }  
        }  
  
        ```  
  
    7.  Kies **OK** om de teksteditor te sluiten.  
  
    8.  Kies **Opslaan** om de webresource op te slaan en vervolgens het webresourcevenster te sluiten.  
  
    9. In het dialoogvenster **Record opzoeken** kunt de nieuwe webresource die u hebt gemaakt selecteren. Kies **Toevoegen** om het dialoogvenster te sluiten.  
  
5.  Configureer de gebeurtenis OnSave:  
  
    1.  Stel in het venster **Formuliereigenschappen** in de sectie **Gebeurtenis-handlers** **Gebeurtenis** in op **OnSave**.  
  
    2.  Selecteer **Toevoegen**.  
  
    3.  Stel in het venster **Handlereigenschappen** de **Bibliotheek** in op de webresource die u in de vorige stap hebt toegevoegd.  
  
    4.  Typ ‘`preventAutoSave`’ in het veld **Functie**. De invoer is hoofdlettergevoelig. Voer geen aanhalingstekens in.  
  
    5.  Zorg ervoor dat **Ingeschakeld** is aangevinkt.  
  
    6.  Vink **Geef uitvoercontext als eerste parameter door** aan.  
  
        > [!IMPORTANT]
        >  Als u dit niet doet, werkt het script niet.  
  
         Het dialoogvenster **Handlereigenschappen** moet er als volgt uitzien: Het aanpassingsvoorvoegsel: "new_" kan verschillen op basis van het aanpassingsvoorvoegsel dat voor de standaarduitgever is ingesteld voor uw organisatie.  
  
 ![OnSave-gebeurtenishandler om autosave in Dynamics 365 te voorkomen](media/prevent-auto-save-script.png "OnSave-gebeurtenishandler om autosave in Dynamics 365 te voorkomen")  
  
    7.  Selecteer **OK** om het dialoogvenster **Handlereigenschappen** te sluiten.  
  
    8.  Als er andere gebeurtenis-handlers voor de gebeurtenis `OnSave` bestaan, gebruikt u de groene pijlen om die naar boven te verplaatsen.  
  
6. Selecteer **OK** om het dialoogvenster **Formuliereigenschappen** te sluiten.  
  
7. Selecteer **Opslaan en sluiten** om het formulier te sluiten.  
  
8. Selecteer in de oplossingsverkenner de optie **Alle aanpassingen publiceren**.  
  
 Nadat u dit script op de gebeurtenis `OnSave` hebt toegepast, wordt het bericht **niet-opgeslagen wijzigingen** in de hoek rechtsonder in het formulier weergeven wanneer iemand het veld aanpast, net als wanneer automatisch opslaan is uitgeschakeld. Maar dit bericht verdwijnt pas als iemand de knop ![Automatisch opslaan](media/auto-save-icon.png "Automatisch opslaan") ernaast selecteert.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Formulieren maken en ontwerpen](create-design-forms.md)      

 
