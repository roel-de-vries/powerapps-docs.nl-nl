---
title: Overzicht van de verbinding met Office 365-gebruikers | Microsoft Docs
description: Informatie over hoe u verbinding kunt maken met Office 365-gebruikers, enkele voorbeelden doorlopen en alle functies weergeven
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 06/07/2016
ms.author: lanced
ms.openlocfilehash: 679d9b905aa1b7d7b1b731de400e6e133787769b
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37897105"
---
# <a name="connect-to-office-365-users-connection-from-powerapps"></a>Verbinding maken met een Office 365-gebruikersverbinding vanuit PowerApps
![Office 365-gebruikers](./media/connection-office365-users/office365icon.png)

Met Office 365-gebruikers kunt u met uw Office 365-account toegang krijgen tot de gebruikersprofielen in uw organisatie. U kunt verschillende acties uitvoeren, zoals uw profiel, het profiel van een gebruiker, de manager van een gebruiker of de direct ondergeschikten van een gebruiker ophalen.

U kunt deze gegevens in een label in uw app weergeven. U kunt één functie weergeven, meerdere functies weergeven en zelfs verschillende functies combineren. Zo kunt u een expressie maken waarin de gebruikersnaam en het telefoonnummer worden gecombineerd en deze gegevens vervolgens in uw app weergeven.

In dit onderwerp wordt beschreven hoe u Office 365-gebruikers als verbinding kunt toevoegen, Office 365-gebruikers als gegevensbron aan uw app kunt toevoegen en tabelgegevens in een galeriebesturingselement kunt gebruiken.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="add-a-connection"></a>Een verbinding toevoegen
1. [Voeg een gegevensverbinding toe](../add-data-connection.md) en selecteer **Office 365-gebruikers**:  

    ![Verbinding maken met Office 365](./media/connection-office365-users/add-office.png)
2. Selecteer **Connect** en als u wordt gevraagd om aan te melden, voert u uw werkaccount in.

De verbinding met Office 365-gebruikers is gemaakt en aan uw app toegevoegd. U kunt de verbinding nu gebruiken.

## <a name="use-the-connection-in-your-app"></a>De verbinding in uw app gebruiken
### <a name="show-information-about-the-current-user"></a>Gegevens over de huidige gebruiker weergeven
1. Selecteer **Label** in het menu **Insert**.
2. Stel de bijbehorende eigenschap **[Text](../controls/properties-core.md)** op de functiebalk in op een van de volgende formules:

    `Office365Users.MyProfile().Department`  
    `Office365Users.MyProfile().DisplayName`  
    `Office365Users.MyProfile().GivenName`  
    `Office365Users.MyProfile().Id`  
    `Office365Users.MyProfile().JobTitle`  
    `Office365Users.MyProfile().Mail`  
    `Office365Users.MyProfile().MailNickname`  
    `Office365Users.MyProfile().Surname`  
    `Office365Users.MyProfile().TelephoneNumber`  
    `Office365Users.MyProfile().UserPrincipalName`  
    `Office365Users.MyProfile().AccountEnabled`  

In het label worden de gegevens weergegeven die u over de huidige gebruiker hebt ingevoerd.

### <a name="show-information-about-another-user"></a>Gegevens over een andere gebruiker weergeven
1. Selecteer **Text** in het menu **Insert** en selecteer vervolgens **Text input**. Wijzig de naam in **InfoAbout**:  

    ![Naam van besturingselement wijzigen](./media/connection-office365-users/renameinfoabout.png)
2. Typ of plak in **InfoAbout** een e-mailadres of gebruiker in uw organisatie. Typ bijvoorbeeld *UwNaam*@*UwBedrijf.com*.
3. Voeg een besturingselement van het type **Label** (via het menu **Invoegen**) toe en stel de bijbehorende eigenschap **[Text](../controls/properties-core.md)** in op een van de volgende formules:

   * Gegevens over een andere gebruiker weergeven:  

       `Office365Users.UserProfile(InfoAbout.Text).Department`  
       `Office365Users.UserProfile(InfoAbout.Text).DisplayName`  
       `Office365Users.UserProfile(InfoAbout.Text).GivenName`  
       `Office365Users.UserProfile(InfoAbout.Text).Id`  
       `Office365Users.UserProfile(InfoAbout.Text).JobTitle`  
       `Office365Users.UserProfile(InfoAbout.Text).Mail`  
       `Office365Users.UserProfile(InfoAbout.Text).MailNickname`  
       `Office365Users.UserProfile(InfoAbout.Text).Surname`  
       `Office365Users.UserProfile(InfoAbout.Text).TelephoneNumber`  
       `Office365Users.UserProfile(InfoAbout.Text).UserPrincipalName`  
       `Office365Users.UserProfile(InfoAbout.Text).AccountEnabled`  
   * Gegevens over de manager van een andere gebruiker weergeven:  

       `Office365Users.Manager(InfoAbout.Text).Department`  
       `Office365Users.Manager(InfoAbout.Text).DisplayName`  
       `Office365Users.Manager(InfoAbout.Text).GivenName`  
       `Office365Users.Manager(InfoAbout.Text).Id`  
       `Office365Users.Manager(InfoAbout.Text).JobTitle`  
       `Office365Users.Manager(InfoAbout.Text).Mail`  
       `Office365Users.Manager(InfoAbout.Text).MailNickname`  
       `Office365Users.Manager(InfoAbout.Text).Surname`  
       `Office365Users.Manager(InfoAbout.Text).TelephoneNumber`  
       `Office365Users.Manager(InfoAbout.Text).UserPrincipalName`  
       `Office365Users.Manager(InfoAbout.Text).AccountEnabled`  

In het label worden de gegevens weergegeven die u hebt ingevoerd over de opgegeven gebruiker of over de manager van die gebruiker.

> [!NOTE]
> Als u een app op basis van een entiteit in Common Data Service ontwikkelt, kunt u een gebruiker opgeven op basis van de id in plaats van het e-mailadres.

U kunt bijvoorbeeld [automatisch een app maken](../data-platform-create-app.md), een scherm toevoegen met een besturingselement van het type **Label** en de eigenschap **Text** van het besturingselement instellen op deze formule:
<br>**Office365Users.UserProfile(BrowseGallery1.Selected.CreatedByUser).DisplayName**

Als u een contactpersoon maakt en deze contactpersoon in het zoekscherm van de app selecteert, wordt uw weergavenaam in het besturingselement **Label** weergegeven.

### <a name="show-the-direct-reports-of-another-user"></a>De direct ondergeschikten van een andere gebruiker weergeven
1. Voeg een besturingselement van het type **Text input** toe (via het menu **Insert** > **Text**) en wijzig de naam in **InfoAbout**.
2. Voer het e-mailadres van een gebruiker in uw organisatie in **InfoAbout** in. Voer bijvoorbeeld *Naam VanUwManager*@*UwBedrijf.com* in.
3. Voer een galerie van het type **With text** (via het menu **Insert** > **Gallery**) toe en stel de bijbehorende eigenschap **[Items](../controls/properties-core.md)** in op de volgende formule:

    `Office365Users.DirectReports(InfoAbout.Text)`

    In de galerie worden de gegevens weergegeven over de direct ondergeschikten van de gebruiker die u hebt ingevoerd.

    Als u de galerie selecteert, ziet u in het deelvenster aan de rechterkant de opties voor de galerie.
4. Selecteer **JobTitle** in de tweede lijst. Selecteer **DisplayName** in de derde lijst. De galerie wordt bijgewerkt met deze waarden.  

> [!NOTE]
> Het eerste vak is eigenlijk een afbeeldingsbesturingselement. Als u geen afbeelding hebt, kunt u het afbeeldingsbesturingselement verwijderen en in plaats daarvan een label toevoegen. [Een besturingselement toevoegen en configureren](../add-configure-controls.md) is een goede informatiebron.

### <a name="search-for-users"></a>Gebruikers zoeken
1. Voeg een besturingselement van het type **Text input** toe (via het menu **Insert** > **Text**) en wijzig de naam in **SearchTerm**. Voer de naam in die u wilt zoeken. Voer bijvoorbeeld uw voornaam in.
2. Voer een galerie van het type **With text** (via het menu **Insert** > **Gallery**) toe en stel de bijbehorende eigenschap **[Items](../controls/properties-core.md)** in op de volgende formule:

    `Office365Users.SearchUser({searchTerm: SearchTerm.Text})`

    In de galerie worden de gebruikers weergegeven van wie de naam de zoektekst bevat die u hebt ingevoerd.

    Als u de galerie selecteert, ziet u in het deelvenster aan de rechterkant de opties voor de galerie.
3. Selecteer **Mail** in de tweede lijst. Selecteer **DisplayName** in de derde lijst.

    Het tweede en derde label in de galerie worden bijgewerkt.

## <a name="view-the-available-functions"></a>De beschikbare functies weergeven
Deze verbinding bevat de volgende functies:

| Functienaam | Beschrijving |
| --- | --- |
| [MyProfile](connection-office365-users.md#myprofile) |Het profiel voor de huidige gebruiker ophalen |
| [UserProfile](connection-office365-users.md#userprofile) |Een specifiek gebruikersprofiel ophalen |
| [Manager](connection-office365-users.md#manager) |Het gebruikersprofiel voor de manager van de opgegeven gebruiker ophalen |
| [DirectReports](connection-office365-users.md#directreports) |De direct ondergeschikten voor de opgegeven gebruiker retourneren |
| [SearchUser](connection-office365-users.md#searchuser) |De zoekresultaten van gebruikersprofielen ophalen |

### <a name="myprofile"></a>MyProfile
Mijn profiel ophalen: het profiel voor de huidige gebruiker ophalen.

#### <a name="input-properties"></a>Invoereigenschappen
Geen.

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Type | Beschrijving |
| --- | --- | --- |
| Department |Tekenreeks |De afdeling van de gebruiker. |
| DisplayName |Tekenreeks |De weergavenaam van de gebruiker. |
| GivenName |Tekenreeks |De voornaam van de gebruiker. |
| Id |Tekenreeks |Gebruikers-id |
| JobTitle |Tekenreeks |De functie van de gebruiker. |
| Mail |Tekenreeks |De e-mail-id van de gebruiker. |
| MailNickname |Tekenreeks |De bijnaam van de gebruiker. |
| Surname |Tekenreeks |De achternaam van de gebruiker. |
| TelephoneNumber |Tekenreeks |Het telefoonnummer van de gebruiker. |
| UserPrincipalName |Tekenreeks |De principal-naam van de gebruiker. |
| AccountEnabled |Booleaanse waarde |De markering Account ingeschakeld. |

### <a name="userprofile"></a>UserProfile
Gebruikersprofiel ophalen: een specifiek gebruikersprofiel ophalen.

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| Id |Tekenreeks |Ja |De principal-naam of e-mail-id van de gebruiker |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Type | Beschrijving |
| --- | --- | --- |
| Department |Tekenreeks |De afdeling van de gebruiker. |
| DisplayName |Tekenreeks |De weergavenaam van de gebruiker. |
| GivenName |Tekenreeks |De voornaam van de gebruiker. |
| Id |Tekenreeks |Gebruikers-id |
| JobTitle |Tekenreeks |De functie van de gebruiker. |
| Mail |Tekenreeks |De e-mail-id van de gebruiker. |
| MailNickname |Tekenreeks |De bijnaam van de gebruiker. |
| Surname |Tekenreeks |De achternaam van de gebruiker. |
| TelephoneNumber |Tekenreeks |Het telefoonnummer van de gebruiker. |
| UserPrincipalName |Tekenreeks |De principal-naam van de gebruiker. |
| AccountEnabled |Booleaanse waarde |De markering Account ingeschakeld. |

### <a name="manager"></a>Manager
Manager ophalen: het gebruikersprofiel voor de manager van de opgegeven gebruiker ophalen

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| Id |Tekenreeks |Ja |De principal-naam of e-mail-id van de gebruiker |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Type | Beschrijving |
| --- | --- | --- |
| Department |Tekenreeks |De afdeling van de gebruiker. |
| DisplayName |Tekenreeks |De weergavenaam van de gebruiker. |
| GivenName |Tekenreeks |De voornaam van de gebruiker. |
| Id |Tekenreeks |Gebruikers-id |
| JobTitle |Tekenreeks |De functie van de gebruiker. |
| Mail |Tekenreeks |De e-mail-id van de gebruiker. |
| MailNickname |Tekenreeks |De bijnaam van de gebruiker. |
| Surname |Tekenreeks |De achternaam van de gebruiker. |
| TelephoneNumber |Tekenreeks |Het telefoonnummer van de gebruiker. |
| UserPrincipalName |Tekenreeks |De principal-naam van de gebruiker. |
| AccountEnabled |Booleaanse waarde |De markering Account ingeschakeld. |

### <a name="directreports"></a>DirectReports
Directe ondergeschikten ophalen: direct ondergeschikten ophalen

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| Id |Tekenreeks |Ja |De principal-naam of e-mail-id van de gebruiker |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Type | Beschrijving |
| --- | --- | --- |
| Department |Tekenreeks |De afdeling van de gebruiker. |
| DisplayName |Tekenreeks |De weergavenaam van de gebruiker. |
| GivenName |Tekenreeks |De voornaam van de gebruiker. |
| Id |Tekenreeks |Gebruikers-id |
| JobTitle |Tekenreeks |De functie van de gebruiker. |
| Mail |Tekenreeks |De e-mail-id van de gebruiker. |
| MailNickname |Tekenreeks |De bijnaam van de gebruiker. |
| Surname |Tekenreeks |De achternaam van de gebruiker. |
| TelephoneNumber |Tekenreeks |Het telefoonnummer van de gebruiker. |
| UserPrincipalName |Tekenreeks |De principal-naam van de gebruiker. |
| AccountEnabled |Booleaanse waarde |De markering Account ingeschakeld. |

### <a name="searchuser"></a>SearchUser
Gebruikers zoeken: de zoekresultaten van gebruikersprofielen ophalen

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| searchTerm |Tekenreeks |Nee |Zoekreeks Van toepassing op: weergavenaam, voornaam, achternaam, e-mail, bijnaam e-mail en principal-naam van gebruiker |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Type | Beschrijving |
| --- | --- | --- |
| Department |Tekenreeks |De afdeling van de gebruiker. |
| DisplayName |Tekenreeks |De weergavenaam van de gebruiker. |
| GivenName |Tekenreeks |De voornaam van de gebruiker. |
| Id |Tekenreeks |Gebruikers-id |
| JobTitle |Tekenreeks |De functie van de gebruiker. |
| Mail |Tekenreeks |De e-mail-id van de gebruiker. |
| MailNickname |Tekenreeks |De bijnaam van de gebruiker. |
| Surname |Tekenreeks |De achternaam van de gebruiker. |
| TelephoneNumber |Tekenreeks |Het telefoonnummer van de gebruiker. |
| UserPrincipalName |Tekenreeks |De principal-naam van de gebruiker. |
| AccountEnabled |Booleaanse waarde |De markering Account ingeschakeld. |

## <a name="helpful-links"></a>Nuttige koppelingen
* Bekijk alle [beschikbare verbindingen](../connections-list.md).
* Meer informatie over het [toevoegen van verbindingen](../add-manage-connections.md) aan uw apps.

