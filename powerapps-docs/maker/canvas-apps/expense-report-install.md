---
title: De voorbeeld-app Onkostenrapporten van PowerApps installeren en configureren | Microsoft Docs
description: Stapsgewijze instructies voor het installeren en configureren van de voorbeeld-app Onkostenrapporten van PowerApps.
documentationcenter: na
author: caburk
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: sample
ms.component: canvas
ms.date: 04/08/2018
ms.author: caburk
ms.openlocfilehash: bce21a5fe07cb5bf608c36371a7cbe45e845b2ad
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/03/2018
---
# <a name="install-and-configure-the-expense-report-powerapps-sample"></a>De voorbeeld-app Onkostenrapporten van PowerApps installeren en configureren

Stapsgewijze instructies voor het installeren en configureren van de voorbeeld-app Onkostenrapporten van PowerApps.

Geschatte tijd voor het uitvoeren van deze stappen: **10-15 minuten**

Bekijk deze video als u een demonstratie wilt zien van dit proces.

[![Video over de installatie van Onkostenrapporten](./media/expense-report-install/expense-report-install-video.png)](https://youtu.be/DOR28V5kCkw)

## <a name="expense-report-powerapps-sample-overview"></a>Overzicht van de voorbeeld-app Onkostenrapporten van PowerApps
Houd onkostenrapporten bij van indiening tot goedkeuring. Regelitems afstemmen wanneer individuele kosten toenemen en indienen voor goedkeuring indien gereed. U moet enkele instellingen opgeven voordat u met de app kunt werken.

![Openingsscherm van de PowerApp Onkosten](./media/expense-report-install/expense-report-powerapp.png)

Bekijk deze video om te zien hoe u de voorbeeld-app Onkostenrapporten van PowerApps gebruikt.

[![Video over de installatie van Onkostenrapporten](./media/expense-report-install/expense-report-demo-video.png)](https://youtu.be/h6E9cdrOvMU)

## <a name="prerequisites"></a>Vereisten

- [Meld u aan](../signup-for-powerapps.md) voor PowerApps.

## <a name="create-the-expenses-sharepoint-list"></a>De SharePoint-lijst Onkosten maken

Deze lijst bevat de onkostenrapporten.

1. Open een webbrowser en navigeer naar https://portal.office.com.
2. Meld u aan met een account die gemachtigd is om lijsten te maken.
3. Navigeer naar de siteverzameling waar u de lijst Onkosten wilt opslaan.
4. Klik op het **tandwielpictogram** rechtsboven in de webpagina.
5. Klik op **Een app toevoegen**.
6. Voer **Aangepast** in het tekstvak **Een app zoeken** in.
7. Klik op het **zoekpictogram**.
8. Klik op de app **Aangepaste lijst**.
9. Voer **Onkosten**in het tekstvak **Naam** in.

    > [!IMPORTANT]
    > Als u een andere naam voor de lijst kiest, moet u ervoor zorgen dat u deze noteert; tijdens de installatie en configuratie moet u deze naam overal vervangen door Onkosten.

10. Klik op **Maken**.

### <a name="create-cost-center-column"></a>Kolom Kostenplaats maken

1. Klik op de lijst **Onkosten**.
2. Klik op het **tandwielpictogram** rechtsboven in de webpagina.
3. Klik op **Lijstinstellingen**.
4. Klik op **Kolom maken**.
5. Voer in het tekstvak **Kolomnaam** **Kostenplaats** in.
6. Selecteer **Keuze** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
7. Voer in het tekstvak **Typ elke keuze op een nieuwe regel** de volgende waarden in, elk op een afzonderlijke regel: 
    - Microsoft
    - Contoso
8. Voer **Microsoft** in het tekstvak **Standaardwaarde** in.
9. Klik op **OK**.

### <a name="create-comments-column"></a>De kolom Opmerkingen maken

1. Klik op **Kolom maken**.
2. Voer **Opmerkingen** in het tekstvak **Kolomnaam** in.
3. Selecteer **Meerdere tekstregels** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Klik op **OK**.

### <a name="create-status-column"></a>De kolom Status maken

1. Klik op de lijst **Onkosten**.
2. Klik op het **tandwielpictogram** rechtsboven in de webpagina.
3. Klik op **Lijstinstellingen**.
4. Klik op **Kolom maken**.
5. Voer **Status** in het tekstvak **Kolomnaam** in.
6. Selecteer **Keuze** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
7. Voer in het tekstvak **Typ elke keuze op een nieuwe regel** de volgende waarden in, elk op een afzonderlijke regel: 
    - Open
    - In behandeling
    - Approved
8. Voer **Open** in het tekstvak **Standaardwaarde** in.
9. Klik op **OK**.

### <a name="create-approvername-column"></a>De kolom Naam goedkeurder maken

1. Klik op **Kolom maken**.
2. Voer **Naam goedkeurder** in het tekstvak **Kolomnaam** in.
3. Selecteer **Persoon of groep** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Ja** in de lijst met keuzerondjes **Require that this column contains information** (Informatie in deze kolom is vereist).
5. Klik op **OK**.

### <a name="create-datesubmitted-column"></a>De kolom Verzenddatum maken

1. Klik op **Kolom maken**.
2. Voer **Verzenddatum** in het tekstvak **Kolomnaam** in.
3. Selecteer **Datum en tijd** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Ja** in de lijst met keuzerondjes **Require that this column contains information** (Informatie in deze kolom is vereist).
5. Klik op **OK**.

### <a name="create-startdate-column"></a>De kolom Startdatum maken

1. Klik op **Kolom maken**.
2. Voer **Startdatum** in het tekstvak **Kolomnaam** in.
3. Selecteer **Datum en tijd** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Ja** in de lijst met keuzerondjes **Require that this column contains information** (Informatie in deze kolom is vereist).
5. Klik op **OK**.

### <a name="create-enddate-column"></a>De kolom Einddatum maken

1. Klik op **Kolom maken**.
2. Voer **Einddatum** in het tekstvak **Kolomnaam** in.
3. Selecteer **Datum en tijd** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Ja** in de lijst met keuzerondjes **Require that this column contains information** (Informatie in deze kolom is vereist).
5. Klik op **OK**.

## <a name="create-the-line-items-sharepoint-list"></a>De SharePoint-lijst Regelitems maken

In deze lijst worden de regelitems opgeslagen die zijn gekoppeld aan onkostenrapporten.

1. Navigeer naar dezelfde siteverzameling waar u de lijst Onkosten hebt gemaakt.
2. Klik op het **tandwielpictogram** rechtsboven in de webpagina.
3. Klik op **Een app toevoegen**.
4. Voer **Aangepast** in het tekstvak **Een app zoeken** in.
5. Klik op het **zoekpictogram**.
6. Klik op de app **Aangepaste lijst**.
7. Voer **Regelitems** in het tekstvak **Naam** in.

    > [!IMPORTANT] 
    > Als u een andere naam voor de lijst kiest, moet u ervoor zorgen dat u deze noteert; tijdens de installatie en configuratie moet u deze naam overal vervangen door Onkosten.

8. Klik op **Maken**.
 
### <a name="create-category-column"></a>De kolom Categorie maken

1. Klik op de lijst **Regelitems**.
2. Klik op het **tandwielpictogram** rechtsboven in de webpagina.
3. Klik op **Lijstinstellingen**.
4. Klik op **Kolom maken**.
5. Voer **Categorie** in het tekstvak **Kolomnaam** in.
6. Selecteer **Keuze** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
7. Voer in het tekstvak **Typ elke keuze op een nieuwe regel** de volgende waarden in, elk op een afzonderlijke regel: 
    - Voeding & drank
    - Transport
    - Zakelijke behoeften
8. Voer **Voeding & drank** in het tekstvak **Standaardwaarde** in.
9. Klik op **OK**.

### <a name="create-cost-column"></a>De kolom Kosten maken

1. Klik op **Kolom maken**.
2. Voer **Kosten** in het tekstvak **Kolomnaam** in.
3. Selecteer **Getal (1, 10, 100)** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Ja** in de lijst met keuzerondjes **Require that this column contains information** (Informatie in deze kolom is vereist).
5. Klik op **OK**.

### <a name="create-date-column"></a>De kolom Datum maken

1. Klik op **Kolom maken**.
2. Voer in het tekstvak **Kolomnaam** **Datum** in.
3. Selecteer **Datum en tijd** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Ja** in de lijst met keuzerondjes **Require that this column contains information** (Informatie in deze kolom is vereist).
5. Klik op **OK**.

### <a name="create-description-column"></a>De kolom Beschrijving maken

1. Klik op **Kolom maken**.
2. Voer **Beschrijving** in het tekstvak **Kolomnaam** in.
3. Selecteer **Meerdere tekstregels** in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Ja** in de lijst met keuzerondjes **Require that this column contains information** (Informatie in deze kolom is vereist).
5. Selecteer **Tekst zonder opmaak** in de lijst met keuzerondjes **Specify the type of text to allow** (Opgeven welk teksttype is toegestaan).
6. Klik op **OK**.

### <a name="create-reportid-column"></a>De kolom ReportID maken

1. Klik op **Kolom maken**.
2. Voer **ReportID** in het tekstvak **Kolomnaam** in.
3. Selecteer **Lookup (information already on this site)** (Opzoeken (informatie die al op deze site staat)) in de lijst met keuzerondjes **type of information in this column is** (type informatie in deze kolom is).
4. Selecteer **Ja** in de lijst met keuzerondjes **Require that this column contains information** (Informatie in deze kolom is vereist).
5. Selecteer in de vervolgkeuzelijst **Informatie ophalen van** de lijst **Onkosten** die u hebt gemaakt.
6. Selecteer **ID** in de vervolgkeuzelijst **In deze kolom**.
7. Klik op **OK**.

### <a name="edit-title-column"></a>De kolom Titel bewerken

1. Klik op de kolomkoppeling **Titel**.
2. Selecteer **Nee** in de lijst met keuzerondjes **Informatie in deze kolom is vereist**.
3. Klik op **OK**.

## <a name="download-the-expense-report-powerapp"></a>De PowerApp Onkostenrapporten downloaden

1.  Navigeer in een browser naar de volgende koppeling:

    http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip.

2.  Download het pakket voor Onkostenrapport PowerApps en sla dit op uw computer op.

## <a name="create-connections"></a>Verbindingen maken

1.  Navigeer in een webbrowser naar https://web.powerapps.com.
2.  Meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.
3.  Selecteer **Verbindingen** in het menu aan de linkerkant.

### <a name="create-approvals-connection"></a>Goedkeuringen-verbinding maken

1.  Klik op **+ Nieuwe verbinding**.
2.  Typ **Goedkeuringen** in het tekstvak **Zoeken** .
3.  Selecteer **Goedkeuringen** in de lijst.
4.  Klik op **Maken**.
    
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

## <a name="import-the-expense-report-powerapp"></a>De PowerApp Onkostenrapporten importeren

1.  Navigeer in een webbrowser naar https://web.powerapps.com.
2.  Meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.
3.  Selecteer **Apps** in het menu aan de linkerkant. 
4.  Klik op **Pakket importeren (preview)**.
    
    ![Het scherm Pakket importeren](./media/expense-report-install/import-package.png)

5.  Klik op de knop **Uploaden** en selecteer het PowerApp-pakket dat u in de vorige stappen hebt gedownload.
6.  Stel voor de resourcetypen **App** en **Stroom** **IMPORTINSTELLINGEN** in op **Als nieuwe maken**.
7.  Stel voor de verbindingen **SharePoint** en **Outlook** **IMPORTINSTELLINGEN** in op **Selecteren tijdens importeren**.
    
    ![Scherm met importinstellingen](./media/expense-report-install/import-settings.png)

8.  Klik op het **rode pictogram** voor de **SharePoint-verbinding**.
9.  Klik in de lijst met verbindingen op het item met uw gebruikersnaam.

    ![Scherm met importinstellingen](./media/expense-report-install/import-settings-sharepoint.png)

10. Klik op **Opslaan**.
11. Klik op het **rode pictogram** voor de **Goedkeuringsverbinding**.
12. Klik in de lijst met verbindingen op het item met uw gebruikersnaam.

    ![Scherm met importinstellingen](./media/expense-report-install/import-settings-approvals.png)

13.  Klik op **Opslaan**.
14.  Klik op het **rode pictogram** voor de **Office 365 Outlook-verbinding**.
15.  Klik in de lijst met verbindingen op het item met uw gebruikersnaam.

    ![Scherm met importinstellingen](./media/expense-report-install/import-settings-office365outlook.png)

16. Klik op **Opslaan**.

    > [!TIP] 
    > Wanneer u klaar bent, ziet het er als volgt uit:

    ![Scherm met importinstellingen](./media/expense-report-install/import-settings-done.png)

17. Klik op **Importeren** en wacht totdat het proces is voltooid.

    ![Scherm met importinstellingen](./media/expense-report-install/import-done.png)

## <a name="configure-the-powerapp-to-use-the-sharepoint-lists"></a>De PowerApp configureren voor het gebruik van de SharePoint-lijsten

1. Klik in de webbrowser op **Apps**.
2. Klik op het **beletselteken** naast de PowerApp Onkostenrapporten.
3. Klik op **Bewerken op internet**.
4. Klik op **Toestaan**.

### <a name="delete-connections"></a>Verbindingen verwijderen
1. Klik op **Weergave**.
2. Klik op **Gegevensbronnen**.
3. Klik in het deelvenster **Gegevens** op het **beletselteken** naast **Onkosten**.
4. Klik op **Verwijderen**.
5. Klik in het deelvenster **Gegevens** op het **beletselteken** naast **Regelitems**.
6. Klik op **Verwijderen**.

### <a name="expenses-list"></a>De lijst Onkosten

1. Klik op **Weergave**.
2. Klik op **Gegevensbronnen**.
3. Klik in het deelvenster **Gegevens** op **+ Gegevensbron toevoegen**.
4. Klik op **+ Nieuwe verbinding**.
5. Selecteer **SharePoint**.
6. Klik op **Maken**.
7. Selecteer in de lijst **Recente sites** de SharePoint-site waarop u de lijst Onkosten hebt gemaakt.

    > [!TIP] 
    > Als de site niet wordt weergegeven in de lijst, voert u de URL in naar de SharePoint-site in het tekstvak en klikt u op **Zoeken**.

8. Voer in het tekstvak **Zoeken** boven in de lijst **Onkosten** in.
9. Schakel het selectievakje in naast de lijst **Onkosten**.
10. Klik op **Verbinding maken**.

### <a name="lineitems-list"></a>De lijst Regelitems

1. Klik op **Weergave**.
2. Klik op **Gegevensbronnen**.
3. Klik in het deelvenster **Gegevens** op **+ Gegevensbron toevoegen**.
4. Klik op **+ Nieuwe verbinding**.
5. Selecteer **SharePoint**.
6. Klik op **Maken**.
7. Selecteer in de lijst **Recente sites** de SharePoint-site waarop u de lijst Regelitems hebt gemaakt.

    > [!TIP] 
    > Als de site niet wordt weergegeven in de lijst, voert u de URL in naar de SharePoint-site in het tekstvak en klikt u op **Zoeken**.

8. Voer in het tekstvak **Zoeken** boven in de lijst **Regelitems** in.
9. Schakel het selectievakje in naast de lijst **Regelitems**.
10. Klik op **Verbinding maken**.
11. Klik op **Bestand**.
12. Klik op **Opslaan**.
13. Klik op **Publiceren**.
14. Klik op **Deze versie publiceren**.

## <a name="modify-the-flow"></a>De stroom wijzigen

1.  Klik op **Stromen** in het menu aan de linkerkant.
2.  Als u wordt gevraagd om aan te melden, meld u aan met dezelfde referenties die u hebt gebruikt om u te registreren.
3.  Selecteer **Mijn stromen** in het menu bovenin.
4.  Klik naast de stroom **Onkosten goedkeuren** op het **potloodpictogram**.
 
    ![Het scherm Stroom bewerken](./media/expense-report-install/edit-flow.png)

5.  Vouw de actie **Items ophalen** uit. 
6.  Wijzig het **siteadres** en de **lijstnaam**, zodat deze overeenkomen met de SharePoint-lijst Onkosten die u hebt gemaakt.
    
    ![Het scherm Stroom bewerken](./media/expense-report-install/edit-flow-getitems.png)

    > [!TIP] 
    > U kunt deze kiezen in de vervolgkeuzelijsten en hoeft deze dus niet handmatig in te voeren.

7.  Vouw **Voorwaarde** uit.
8.  Vouw het gedeelte **Indien ja** uit.
9.  Vouw de actie **Change item status to Approved** (Status van item wijzigen in Goedgekeurd) uit.
10. Wijzig het **siteadres** en de **lijstnaam**, zodat deze overeenkomen met de SharePoint-lijst Onkosten die u hebt gemaakt.

    ![Het scherm Stroom bewerken](./media/expense-report-install/edit-flow-condition-ifyes.png) 

    > [!TIP] 
    > U kunt deze kiezen in de vervolgkeuzelijsten en hoeft deze dus niet handmatig in te voeren.

11. Vouw het gedeelte **Indien nee** uit.
12. Vouw de actie **Change item status to Open** (Status item wijzigen in Open) uit.
13. Wijzig het **siteadres** en de **lijstnaam**, zodat deze overeenkomen met de SharePoint-lijst Onkosten die u hebt gemaakt. 

    ![Het scherm Stroom bewerken](./media/expense-report-install/edit-flow-condition-ifno.png)

    > [!TIP] 
    > U kunt deze kiezen in de vervolgkeuzelijsten en hoeft deze dus niet handmatig in te voeren.

14. Klik op **Stroom bijwerken**.

## <a name="play-the-powerapp"></a>De PowerApp afspelen

1. Klik in de webbrowser op **Apps**.
2. Klik op het **beletselteken** naast de PowerApp Onkostenrapporten.
3. Klik op **Openen**.

Bekijk deze video om te zien hoe u de voorbeeld-app Onkostenrapporten van PowerApps gebruikt.

[![Video over de installatie van Onkostenrapporten](./media/expense-report-install/expense-report-demo-video.png)](https://youtu.be/h6E9cdrOvMU)

##<a name="next-steps"></a>Volgende stappen
- [Een SharePoint-lijstformulier aanpassen](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/customize-list-form)
- [Een besturingselement toevoegen en configureren](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/add-configure-controls)
- [Machtigingen voor een SharePoint-lijst of -bibliotheek bewerken en beheren](https://support.office.com/en-us/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)



