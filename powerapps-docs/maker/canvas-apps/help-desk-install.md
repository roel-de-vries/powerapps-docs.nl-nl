---
title: De voorbeeld-app Helpdesk voor canvas-apps installeren en configureren | Microsoft Docs
description: Stapsgewijze instructies voor het in PowerApps installeren en configureren van de voorbeeld-app Helpdesk voor canvas-apps.
author: caburk
manager: kvivek
ms.service: powerapps
ms.topic: sample
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/08/2018
ms.author: caburk
ms.openlocfilehash: 3d6b418ac6738071f16ec4cf75c81c2850d67f74
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/02/2018
ms.locfileid: "39470403"
---
# <a name="install-and-configure-the-help-desk-sample-in-powerapps"></a>De voorbeeld-app Helpdesk installeren en configureren in PowerApps

Stapsgewijze instructies voor het in PowerApps installeren en configureren van de voorbeeld-app Helpdesk voor canvas-apps.

Geschatte tijd voor het uitvoeren van deze stappen: **10-15 minuten**

> [!TIP]
> Bekijk in deze [video](https://youtu.be/z4cdtD6hB_4) een demonstratie van deze procedure.

## <a name="overview-of-the-sample"></a>Overzicht van de voorbeeld-app

Helpdesk biedt een gebruiksvriendelijke ervaring om eindgebruikers te verbinden met ondersteuningsmedewerkers. Zoek snel antwoorden op uw belangrijkste vragen, houd openstaande tickets bij en controleer de details van eerdere aanvragen. U moet enkele instellingen opgeven voordat u met de app kunt werken.

![Openingsscherm van de PowerApp Helpdesk](./media/help-desk-install/Login-screen.png)

> [!TIP]
> Bekijk deze [video](https://youtu.be/sl5fXwwnvzI) om te zien hoe u de voorbeeld-app Helpdesk van PowerApp gebruikt.

## <a name="prerequisites"></a>Vereisten

- [Meld u aan](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) voor PowerApps.
- Moet een geldige SharePoint Online-licentie hebben en machtiging om lijsten te maken.

## <a name="create-the-helpdesk-sharepoint-list"></a>De SharePoint-lijst Helpdesk maken

In deze lijst worden de Helpdesk-tickets opgeslagen.

1. Open een webbrowser en navigeer naar https://portal.office.com.
2. Meld u aan met een account dat gemachtigd is om SharePoint-lijsten te maken.
3. Navigeer naar de siteverzameling waar u de Helpdesk-lijst wilt opslaan.
4. Klik op het **tandwielpictogram** rechtsboven in de webpagina.
5. Klik op **Een app toevoegen**.
6. Voer **Aangepast** in het tekstvak **Een app zoeken** in.
7. Klik op het **zoekpictogram**.
8. Klik op de app **Aangepaste lijst**.
9. Voer **Helpdesk**in het tekstvak **Naam** in.

    > [!IMPORTANT]
    > Als u een andere naam voor de lijst kiest, moet u ervoor zorgen dat u deze noteert; tijdens de installatie en configuratie moet u deze naam overal vervangen door Helpdesk.

10. Klik op **Maken**.

### <a name="create-description-column"></a>De kolom Beschrijving maken

1. Selecteer het beletselteken naast de lijst Helpdesk en klik op **Instellingen**.
2. Klik op **Kolom maken**.
3. Voer **Beschrijving** in het tekstvak **Kolomnaam** in.
4. Selecteer **Meerdere tekstregels** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
5. Selecteer **Ja** in de lijst met keuzerondjes **Require that this column contains information** (Informatie in deze kolom is vereist).
6. Selecteer **Tekst zonder opmaak** in de lijst met keuzerondjes **Specify the type of text to allow** (Opgeven welk teksttype is toegestaan).
7. Klik op **OK**.

### <a name="create-category-column"></a>De kolom Categorie maken

1. Klik op **Kolom maken**.
2. Voer **Categorie** in het tekstvak **Kolomnaam** in.
3. Selecteer **Keuze** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Voer in het tekstvak **Typ elke keuze op een nieuwe regel** de volgende waarden in, elk op een afzonderlijke regel: 
    - LAPTOP/PC-apparatuuruitgifte
    - LAPTOP/PC-softwareuitgifte
5. Selecteer **Nee** in de lijst met keuzerondjes **Unieke waarden afdwingen**.
6. Selecteer **Vervolgkeuzelijst** in de lijst met keuzerondjes **Keuzen weergeven met**.
7. Voer **LAPTOP/PC-apparatuuruitgifte** in het tekstvak **Standaardwaarde** in.
8. Klik op **OK**.

### <a name="create-percentcomplete-column"></a>Kolom Percentage voltooid maken

1. Klik op **Kolom maken**.
2. Voer **Percentage voltooid** in het tekstvak **Kolomnaam** in.
3. Selecteer **Getal (1, 10, 100)** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Nee** in de lijst met keuzerondjes **Informatie in deze kolom is vereist**.
5. Klik op **OK**.

### <a name="create-priority-column"></a>De kolom Prioriteit maken

1. Klik op **Kolom maken**.
2. Voer **Prioriteit** in het tekstvak **Kolomnaam** in.
3. Selecteer **Keuze** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Voer in het tekstvak **Typ elke keuze op een nieuwe regel** de volgende waarden in, elk op een afzonderlijke regel: 
    - HOOG
    - GEMIDDELD
    - LAAG
5. Selecteer **Nee** in de lijst met keuzerondjes **Unieke waarden afdwingen**.
6. Selecteer **Vervolgkeuzelijst** in de lijst met keuzerondjes **Keuzen weergeven met**.
7. Voer **LAAG** in het tekstvak **Standaardwaarde** in.
8. Klik op **OK**.

### <a name="create-taskstatus-column"></a>De kolom Status van taak maken

1. Klik op **Kolom maken**.
2. Voer **Status van taak** in het tekstvak **Kolomnaam** in.
3. Selecteer **Keuze** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Voer in het tekstvak **Typ elke keuze op een nieuwe regel** de volgende waarden in, elk op een afzonderlijke regel: 
    - NIET GESTART
    - WORDT UITGEVOERD
    - VOLTOOID
    - UITGESTELD
    - WACHTEN OP CSR
5. Selecteer **Nee** in de lijst met keuzerondjes **Unieke waarden afdwingen**.
6. Selecteer **Vervolgkeuzelijst** in de lijst met keuzerondjes **Keuzen weergeven met**.
7. Voer **NIET GESTART** in het tekstvak **Standaardwaarde** in.
8. Klik op **OK**.

### <a name="create-assignedto-column"></a>De kolom Toegewezen aan maken

1. Klik op **Kolom maken**.
2. Voer **Toegewezen aan** in het tekstvak **Kolomnaam** in.
3. Selecteer **Persoon of groep** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Nee** in de lijst met keuzerondjes **Informatie in deze kolom is vereist**.
5. Selecteer **NEE** in de lijst met keuzerondjes **Meerdere selecties toestaan**.
6. Klik op **OK**.

### <a name="edit-title-column"></a>De kolom Titel bewerken

1. Klik op de kolomkoppeling **Titel**.
2. Selecteer **Nee** in de lijst met keuzerondjes **Informatie in deze kolom is vereist**.
3. Klik op **OK**.

## <a name="download-the-help-desk-powerapp"></a>De PowerApp Helpdesk downloaden

1.  [Download](http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/helpdesk/docs/HelpDesk(SP_List).zip) het PowerApps-pakket en sla dit op uw computer op.

## <a name="create-connections"></a>Verbindingen maken

1.  Navigeer in een browser naar [web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2.  Meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.
3.  Selecteer **Gegevens** en vervolgens **Verbindingen** in het menu aan de linkerkant.
    
### <a name="create-office-365-outlook-connection"></a>Office 365 Outlook-verbinding maken

1.  Klik op **+ Nieuwe verbinding**.
2.  Typ **Office 365 Outlook** in het tekstvak **Zoeken**.
3.  Selecteer **Office 365 Outlook** in de lijst.
4.  Klik op **Maken**.
5.  Selecteer in het pop-upvenster het account waarmee u bent aangemeld.

### <a name="create-sharepoint-connection"></a>SharePoint-verbinding maken

1.  Klik op **+ Nieuwe verbinding**.
2.  Typ **SharePoint** in het tekstvak **Zoeken**.
3.  Selecteer **SharePoint** in de lijst.
4.  Klik op **Maken**.
5.  Selecteer in het pop-upvenster het account waarmee u bent aangemeld.

### <a name="create-office-365-users-connection"></a>De verbinding Office 365-gebruikers maken

1.  Klik op **+ Nieuwe verbinding**.
2.  Typ **Office 365-gebruikers** in het tekstvak **Zoeken**.
3.  Selecteer **Office 365-gebruikers** in de lijst.
4.  Klik op **Maken**.
5.  Selecteer in het pop-upvenster het account waarmee u bent aangemeld.

## <a name="import-the-help-desk-powerapp"></a>De PowerApp Helpdesk importeren

1. Navigeer in een webbrowser naar https://web.powerapps.com.
2. Meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.
3. Selecteer **Apps** in het menu aan de linkerkant. 
4. Klik op **Pakket importeren (preview)**.
    
   ![Het scherm Pakket importeren](./media/help-desk-install/import-package.png)

5. Klik op de knop **Uploaden** en selecteer het PowerApp-pakket dat u in de vorige stappen hebt gedownload.
6. Stel voor de resourcetypen **App** en **Stroom** **IMPORTINSTELLINGEN** in op **Als nieuwe maken**.
7. Stel voor de verbindingen **SharePoint** en **Outlook** **IMPORTINSTELLINGEN** in op **Selecteren tijdens importeren**.
    
   ![Scherm met importinstellingen](./media/help-desk-install/import-settings.png)

8. Klik op het **rode pictogram** voor de **SharePoint-verbinding**.
9. Klik in de lijst met verbindingen op het item met uw gebruikersnaam.

   ![Scherm met importinstellingen](./media/help-desk-install/import-settings-sharepoint.png)

10. Klik op **Opslaan**.
11. Klik op het **rode pictogram** voor de **Office 365 Outlook-verbinding**.
12. Klik in de lijst met verbindingen op het item met uw gebruikersnaam.

    ![Scherm met importinstellingen](./media/help-desk-install/import-settings-office365outlook.png)

13. Klik op **Opslaan**.

    > [!TIP] 
    > Wanneer u klaar bent, ziet het er als volgt uit.

    ![Scherm met importinstellingen](./media/help-desk-install/import-settings-done.png)

14. Klik op **Importeren** en wacht totdat het proces is voltooid.

    ![Scherm met importinstellingen](./media/help-desk-install/import-done.png)

## <a name="configure-the-powerapp-to-use-the-sharepoint-list"></a>De PowerApp configureren voor het gebruik van de SharePoint-lijst

1. Klik onder Volgende stappen op **App openen**.
2. Klik op **Toestaan** wanneer om toestemming wordt gevraagd.

### <a name="delete-connections"></a>Verbindingen verwijderen

1. Klik op **Weergave**.
2. Klik op **Gegevensbronnen**.
3. Klik in het deelvenster **Gegevens** op het **beletselteken** naast **Helpdesk** SharePoint-verbinding.
4. Klik op **Verwijderen**.

### <a name="helpdesk-list"></a>Helpdesk-lijst

1. Klik op **Weergave**.
2. Klik op **Gegevensbronnen**.
3. Klik in het deelvenster **Gegevens** op **+ Gegevensbron toevoegen**.
4. Selecteer **SharePoint**.
5. Klik op **Maken**.
6. Selecteer in de lijst **Recente sites** de SharePoint-site waarop u de Helpdesk-lijst hebt gemaakt.

    > [!TIP] 
    > Als de site niet wordt weergegeven in de lijst, voert u de URL in naar de SharePoint-site in het tekstvak en klikt u op **Zoeken**.

7. Voer in het tekstvak **Zoeken** boven in de lijst **Helpdesk** in.
8. Schakel het selectievakje in naast de **Helpdesk**-lijst.
9. Klik op **Verbinding maken**.

### <a name="update-admin-list"></a>De lijst met beheerders bijwerken

1. Selecteer het **aanmeldscherm**.
2. Selecteer **OnStart** in de vervolgkeuzelijst.
3. Vouw het formulevenster uit en zoek de verzameling **AdminList**.
4. Vervang <strong>user@microsoft.com</strong> door uw Helpdesk-beheerder(s).

    ![De lijst met beheerders bijwerken](./media/help-desk-install/Change-admin.png)
    
   > [!TIP]
   > Als er meerdere beheerders zijn, gebruikt u een komma om de beheerders te scheiden.  Voorbeeld: admin1@microsoft.com, admin2@microsoft.com.
   > Als u wilt controleren of de adressen in AdminList overeenkomen met de indeling die PowerApps verwacht, selecteert u Weergave > Variabelen > Algemeen > Mijn profiel en bekijkt u de verwachte e-mailadresindeling in de kolom E-mail.

5. Klik op **Bestand**.
6. Klik op **Opslaan**.
7. Klik op **Publiceren**.
8. Klik op **Deze versie publiceren**.

## <a name="modify-the-flow"></a>De stroom wijzigen

1.  Klik op **Stromen** in het menu aan de linkerkant.
2.  Als u wordt gevraagd om aan te melden, meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.
3.  Selecteer **Mijn stromen** in het menu bovenin.
4.  Klik naast de stroom **Helpdesk-stroom** op het **potloodpictogram**. 
 
    ![Het scherm Stroom bewerken](./media/help-desk-install/edit-flow.png)

5.  Vouw de actie **Items ophalen** uit. 
6.  Wijzig het **siteadres** en de **lijstnaam**, zodat deze overeenkomen met de SharePoint-lijst Helpdesk die u hebt gemaakt.
    
    ![Het scherm Stroom bewerken](./media/help-desk-install/edit-flow-getitems.png)

    > [!TIP] 
    > U kunt deze kiezen in de vervolgkeuzelijsten en hoeft deze dus niet handmatig in te voeren.

7.  Vouw **Schakelaar** uit.
8.  Vouw **NIET GESTART** uit.
9.  Vouw de actie **Case niet gestart** uit.
10. Voer in **Naar** het e-mailadres van de Helpdesk-beheerder in.

    ![Het scherm Stroom bewerken](./media/help-desk-install/edit-flow-condition-send-email.png) 

11. Klik op **Stroom bijwerken**.

## <a name="play-the-powerapp"></a>De PowerApp afspelen

1. Klik in de webbrowser op **Apps**.
2. Klik op het **beletselteken** naast de PowerApp Helpdesk.
3. Klik op **Openen**. 

> [!TIP]
> Bekijk deze [video](https://youtu.be/sl5fXwwnvzI) om te zien hoe u de voorbeeld-app Helpdesk van PowerApp gebruikt.


## <a name="next-steps"></a>Volgende stappen
- [Een SharePoint-lijstformulier aanpassen](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)
- [Een besturingselement toevoegen en configureren](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-configure-controls)
- [Machtigingen voor een SharePoint-lijst of -bibliotheek bewerken en beheren](https://support.office.com/en-us/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)
 
