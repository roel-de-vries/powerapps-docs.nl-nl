---
title: Reageren op aanvragen van betrokkenen voor Common Data Service (CDS) for Apps-klantgegevens | Microsoft Docs
description: Overzicht van hoe te reageren op aanvragen van betrokkenen voor Common Data Service (CDS) for Apps-klantgegevens
author: jamesol-msft
ms.reviewer: paulliew
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 04/23/2018
ms.author: jamesol
ms.openlocfilehash: b550d5fe7e36c36177fff017adcf9d9034c93dd4
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218045"
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-common-data-service-for-apps-customer-data"></a>Reageren op aanvragen van betrokkenen voor CDS for Apps-klantgegevens (Common Data Service)

## <a name="introduction-to-dsr-requests"></a>Inleiding tot DSR-aanvragen
De AVG (algemene verordening gegevensbescherming) van de EU (Europese Unie) verleent rechten aan personen (in de verordening *betrokkenen* genoemd) om de persoonsgegevens te beheren die zijn verzameld door een werkgever of een andere instantie of organisatie (*gegevensverwerker* of *verwerker*). Volgens de AVG zijn persoonsgegevens een breed begrip. Hieronder vallen alle gegevens die verband houden met een geïdentificeerde of identificeerbare natuurlijke persoon. De AVG biedt betrokkenen het recht om het volgende te doen, wanneer dit betrekking heeft op hun persoonsgegevens:

* Kopieën opvragen
* Correcties aanvragen
* Verwerking beperken
* Gegevens verwijderen
* Gegevens in digitale vorm ontvangen, zodat ze aan een andere verwerker kunnen worden overgedragen

Een formele aanvraag van een betrokkene aan een verwerker om actie te ondernemen met betrekking tot zijn of haar persoonsgegevens wordt een aanvraag van de betrokkene genoemd.

In dit artikel wordt beschreven hoe Microsoft zich voorbereidt op de AVG, en het bevat ook voorbeelden van stappen die u kunt uitvoeren om AVG-naleving te ondersteunen bij gebruik van PowerApps, Microsoft Flow en Common Data Service (CDS) for Apps. U leert hoe u producten, services en beheerprogramma's van Microsoft kunt gebruiken om onze klanten te helpen bij het vinden van persoonsgegevens in de Microsoft-cloud als reactie op aanvragen van betrokkenen.

In dit artikel komen de volgende acties aan bod:

* **Detecteren**: zoek- en detectieprogramma's gebruiken om sneller klantgegevens met betrekking tot een DSR-aanvraag te vinden. Zodra mogelijk responsieve documenten zijn verzameld, kunt u een of meer van de volgende acties uitvoeren om op de aanvraag te reageren. U kunt ook besluiten dat de aanvraag niet voldoet aan de richtlijnen van uw organisatie voor reacties op DSR-aanvragen.

* **Toegang verkrijgen**: persoonsgegevens ophalen die zich in de Microsoft-cloud bevinden en, indien aangevraagd, voor de betrokkene een kopie maken van deze gegevens.

* **Herstellen**: wijzigingen aanbrengen of andere aangevraagde acties voor de persoonsgegevens uitvoeren, indien van toepassing.

* **Beperken**: de verwerking van persoonsgegevens beperken door, waar mogelijk, licenties voor verschillende onlineservices te verwijderen of de gewenste services uit te schakelen. U kunt ook gegevens uit de Microsoft-cloud verwijderen en deze on-premises of op een andere locatie bewaren.

* **Verwijderen**: permanent verwijderen van persoonsgegevens die zich bevinden in de Microsoft-cloud.

* **Exporteren**: een elektronisch exemplaar (in een machineleesbare indeling) van persoonsgegevens leveren aan de betrokkene.

## <a name="cds-for-apps-customer-data"></a>Klantgegevens voor CDS voor Apps

> [!IMPORTANT]
> Van toepassing op zowel CDS for Apps en de vorige versie van Common Data Service

CDS for Apps en de vorige versie van CDS (Common Data Service) hebben verschillende processen voor interactie met persoonsgegevens.

U kunt achterhalen welk type CDS-omgeving u gebruikt door u aan te melden bij [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) en deze stappen te volgen:

1. Selecteer uw omgeving in de vervolgkeuzelijst **Omgeving**.
2. Klik of tik in het navigatievenster op **Gegevens** om de sectie uit te vouwen en klik of tik op **Entiteiten**.

    Uw omgeving is CDS for Apps als de volgende entiteiten worden vermeld:

    ![De lijst PowerApps Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-entities-list.png)

    Uw omgeving is de vorige versie van CDS als de volgende entiteiten worden vermeld:

    ![De lijst PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-list.png)

Nadat u hebt bepaald welke type CDS-omgeving u hebt, volgt u de stappen in de volgende secties om uw persoonsgegevens te achterhalen.

> [!NOTE]
> Het kan zijn dat sommige omgevingen zich in CDS for Apps bevinden en andere in de vorige versie van CDS. Daarom moet u de onderstaande processen herhalen voor elke omgeving in uw organisatie.

## <a name="user-personal-data-in-cds-for-apps"></a>Persoonsgegevens van gebruiker in CDS for Apps

### <a name="prerequisites"></a>Vereisten
U moet gebruikers in het Office 365-beheercentrum maken en hun een juiste gebruikerslicentie en gebruikersrol toewijzen voordat ze CDS for Apps kunnen openen en gebruiken.

Standaardpersoonsgegevens van de gebruiker (zoals gebruikersnaam, gebruikers-id, telefoonnummer, e-mailadres en adres van de gebruiker) worden opgeslagen en onderhouden in het Office 365-beheercentrum. Systeembeheerders kunnen deze persoonsgegevens alleen bijwerken in het Office 365-beheercentrum. De gegevens worden dan automatisch in alle omgevingen gesynchroniseerd naar de entiteit Gebruiker in het CDS for Apps-systeem. Systeembeheerders kunnen ook aangepaste kenmerken maken om aanvullende persoonsgegevens vast te leggen in de entiteit Gebruiker van het CDS for Apps-systeem. Daarna kunnen systeembeheerders deze kenmerken handmatig onderhouden en beheren.

Om te vermijden dat zakelijke toepassingen die essentieel zijn voor de activiteiten van uw organisatie worden onderbroken, worden gebruikersrecords niet automatisch verwijderd uit de entiteit Gebruiker van het CDS for Apps-systeem wanneer een gebruiker wordt verwijderd uit het Office 365-beheercentrum. De status van de gebruiker wordt in CDS for Apps ingesteld op Uitgeschakeld, maar een CDS for Apps-systeembeheerder moet de persoonsgegevens uit CDS for Apps in de toepassing vinden en verwijderen.

Alleen Office 365-hoofdbeheerders en CDS-systeembeheerder kunnen de hieronder genoemde acties Ontdekken, Herstellen, Exporteren en Verwijderen uitvoeren.

### <a name="discover"></a>Ontdekken
Systeembeheerders kunnen meerdere CDS for Apps-instanties maken. Deze instanties kunnen worden gebruikt voor proefversies, ontwikkeling of productiedoeleinden. Elk van deze instanties bevat een kopie van de entiteit Gebruiker van het systeem met eventuele aangepaste kenmerken die zijn toegevoegd door de systeembeheerder, evenals persoonsgegevens van de gebruiker die zijn gesynchroniseerd vanuit het Office 365-beheercentrum.

Systeembeheerders kunnen een lijst met alle CDS for Apps-instanties vinden door naar het Dynamics 365-beheercentrum in het PowerApps-beheercentrum te gaan.

In het [PowerApps-beheercentrum](https://admin.powerapps.com/) gaat u als volgt te werk:

1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en selecteer een omgeving in de lijst.

3.  Klik of tik op **Dynamics 365-beheercentrum**.

    ![Omgevingsdetails van PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-environment-details.png)

    Er wordt een lijst met alle instanties weergegeven.

    ![De PowerApps-instantiekiezer](./media/common-data-service-gdpr-dsr-guide/powerapps-instance-picker.png)

U vindt persoonsgegevens uit CDS for Apps-gebruikers in de volgende bronnen:

|Bron | Doel | Website-toegang | Toegang op programmeerniveau
| --- | --- | --- | ---
| Entiteitsrecord | Dit is de entiteit Gebruiker van het systeem, waarin persoonsgegevens van een gebruiker worden opgeslagen. | [PowerApps-beheercentrum](https://admin.powerapps.com) | Via de [Web-API](https://docs.microsoft.com/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)
| Controlegeschiedenis | Biedt klanten de mogelijkheid om resources te identificeren die gebruikers op entiteitsniveau hebben gemaakt, geopend, gewijzigd of verwijderd. | [PowerApps-beheercentrum](https://admin.powerapps.com) | Via de [Web-API](https://docs.microsoft.com/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)

#### <a name="user"></a>User
Persoonsgegevens van een gebruiker worden opgeslagen in de Azure Active Directory. Ze worden automatisch gesynchroniseerd naar alle CDS for Apps-omgevingen. Systeembeheerders kunnen deze persoonsgegevens niet rechtstreeks in CDS for Apps bijwerken wanneer de gebruiker actief is &mdash; ze moeten de gegevens in het Office 365-beheercentrum bijwerken. Systeembeheerders kunnen persoonsgegevens (bijvoorbeeld aangepaste kenmerken) rechtstreeks aan CDS for Apps toevoegen, maar ze moeten deze gegevens handmatig beheren.

Om een gebruiker en zijn of haar persoonsgegevens te zoeken, gaat u naar het [PowerApps-beheercentrum](https://admin.powerapps.com/) en doet u het volgende:

1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en selecteer een omgeving in de lijst.

2. Klik of tik op **Dynamics 365-beheercentrum**, selecteer een omgeving in de lijst en klik of tik op **Openen**.

3. Ga naar **Instellingen** > **Beveiliging** > **Gebruikers**.

4. Voer de naam van de gebruiker in het **zoekvak** in en klik of tik op **Zoeken**.

5. Dubbelklik of dubbeltik op de naam van de gebruiker als u de persoonsgegevens van die gebruiker wilt bekijken.

    ![Formulier met PowerApp-gebruikers](./media/common-data-service-gdpr-dsr-guide/powerapps-user-form.png)

#### <a name="audit-history"></a>Controlegeschiedenis
Wanneer [Controletracering](https://docs.microsoft.com/dynamics365/customer-engagement/admin/audit-data-user-activity) is ingeschakeld voor een entiteit in CDS for Apps, worden de persoonsgegevens van een gebruiker, samen met de gebeurtenissen die de gebruiker heeft uitgevoerd, geregistreerd in de controlegeschiedenis.

### <a name="rectify"></a>Corrigeren
Als een betrokkene u vraagt de persoonsgegevens te corrigeren die zich in de gegevens van uw organisatie bevinden, moeten u en uw organisatie bepalen of de aanvraag moet worden ingewilligd. Het corrigeren van gegevens kan het bewerken of redigeren van persoonsgegevens omvatten of het verwijderen van persoonsgegevens uit een document of een ander type item.

U kunt Azure Active Directory gebruiken om de identiteiten (persoonsgegevens) van uw gebruikers in CDS For Apps te beheren. Zakelijke klanten kunnen correctieaanvragen van betrokkenen beheren met de beperkte bewerkingsfuncties binnen een bepaalde Microsoft-service. Als gegevensverwerker kan Microsoft door het systeem gegenereerde logboeken niet corrigeren, omdat deze feitelijke activiteiten weerspiegelen en een historisch overzicht vormen van gebeurtenissen in Microsoft-services. Zie [AVG: aanvragen van betrokkenen](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) voor meer informatie.

Zodra een gebruikersrecord uit Azure Active Directory is verwijderd, kunnen systeembeheerders resterende persoonsgegevens van die gebruikers (zoals aangepaste kenmerken) verwijderen uit alle instanties.  

### <a name="export"></a>Exporteren

#### <a name="system-user"></a>Systeemgebruiker
Vanuit de gebruikerslijst in het beheercentrum kunt u de persoonsgegevens van een gebruiker die zijn opgeslagen in de entiteit Gebruiker van het systeem exporteren naar Excel.

In het [PowerApps-beheercentrum](https://admin.powerapps.com/) gaat u als volgt te werk:

1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en selecteer een omgeving in de lijst.

2. Klik of tik op **Dynamics 365-beheercentrum**, selecteer een omgeving in de lijst en klik of tik op **Openen**.

3. Ga naar **Instellingen** > **Beveiliging** en selecteer **Ingeschakelde gebruikersweergave**.

4. Klik op **Exporteren naar Excel**.

#### <a name="audit-history"></a>Controlegeschiedenis
In het beheercentrum kunt u schermopnamen maken van de controlegeschiedenis.

In het [PowerApps-beheercentrum](https://admin.powerapps.com/) gaat u als volgt te werk:

1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en selecteer een omgeving in de lijst.

2. Klik of tik op **Dynamics 365-beheercentrum**, selecteer een omgeving in de lijst en klik of tik op **Openen**.

3. Ga naar **Instellingen** > **Controleren** en selecteer **Overzichtsweergave van controles**.

    ![Menu Controlegeschiedenis in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-menu.png)

4. Zoek de controlerecord van de gebruiker en druk op Alt+PrtScn om de schermopname te maken.

    ![Details van Controlegeschiedenis in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-details.png)

5. Sla de schermopname op in een bestand, dat u vervolgens naar de aanvrager kunt verzenden.

### <a name="delete"></a>Verwijderen

#### <a name="user"></a>User
Om te vermijden dat zakelijke toepassingen die essentieel zijn voor de activiteiten van uw organisatie worden onderbroken, worden gebruikersrecords niet automatisch verwijderd uit de entiteit Gebruiker van het CDS for Apps-systeem wanneer een gebruiker wordt verwijderd uit het Office 365-beheercentrum. De status van de gebruiker wordt in CDS for Apps ingesteld op Uitgeschakeld, maar een CDS for Apps-systeembeheerder moet de persoonsgegevens uit CDS for Apps in de toepassing vinden en verwijderen.

#### <a name="remove-a-users-personal-data-from-the-users-summary-page"></a>Persoonsgegevens van een gebruiker verwijderen uit de overzichtspagina van de gebruiker
Wanneer een gebruikersrecord is verwijderd uit Azure Active Directory, wordt het volgende bericht weergegeven op de overzichtspagina van de gebruiker:

*Gegevens van deze gebruiker worden niet meer beheerd door Office 365. U kunt deze record bijwerken om te reageren op aanvragen van betrokkenen door alle persoonsgegevens die zijn gekoppeld aan deze gebruiker te verwijderen of te vervangen.*

In het [PowerApps-beheercentrum](https://admin.powerapps.com/) gaat u als volgt te werk:

1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en selecteer een omgeving in de lijst.

2. Klik of tik op **Dynamics 365-beheercentrum**, selecteer een omgeving in de lijst en klik of tik op **Openen**.

3. Ga naar **Instellingen** > **Beveiliging** > **Gebruikers** en selecteer **Uitgeschakelde gebruikersweergave**.

4. Voer de naam van de gebruiker in het **zoekvak** in en klik of tik op **Zoeken**.

9. Dubbelklik op de naam van de gebruiker in de lijst met zoekresultaten.

10. Verwijder alle persoonsgegevens op de overzichtspagina van de gebruiker en klik of tik op **Opslaan**.

#### <a name="remove-a-users-personal-data-by-using-excel"></a>Persoonsgegevens van een gebruiker verwijderen met behulp van Excel
In het [PowerApps-beheercentrum](https://admin.powerapps.com/) gaat u als volgt te werk:

1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en selecteer een omgeving in de lijst.

2. Klik of tik op **Dynamics 365-beheercentrum**, selecteer een omgeving in de lijst en klik of tik op **Openen**.

3. Ga naar **Instellingen** > **Beveiliging** > **Gebruikers** en selecteer **Uitgeschakelde gebruikersweergave**.

4. Maak en download een Excel-sjabloonbestand van de persoonsgegevens van de gebruiker. Zie [Een nieuwe Excel-sjabloon maken](https://docs.microsoft.com/dynamics365/customer-engagement/admin/analyze-your-data-with-excel-templates#create-a-new-excel-template) voor stapsgewijze instructies.

8. Open het gedownloade Excel-sjabloonbestand, verwijder de persoonsgegevens van de gebruiker en sla het bestand op.

9. Ga terug naar de pagina **Uitgeschakelde gebruikersweergave** en klik of tik op **Gegevens importeren**.

10. Selecteer het Excel-sjabloonbestand in het dialoogvenster **Gegevensbestand uploaden** in het dialoogvenster. Breng de nodige wijzigingen aan in het venster **Velden toewijzen**.

12. Klik of tik op **Volgende** en klik of tik **Indienen**.

#### <a name="remove-audit-history-from-the-audit-summary-view-page"></a>Controlegeschiedenis verwijderen van de pagina Overzichtsweergave van controles
In het [PowerApps-beheercentrum](https://admin.powerapps.com/) gaat u als volgt te werk:

1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en selecteer een omgeving in de lijst.

2. Klik of tik op **Dynamics 365-beheercentrum**, selecteer een omgeving in de lijst en klik of tik op **Openen**.

3. Ga naar **Instellingen** > **Controleren** en selecteer **Overzichtsweergave van controles**.

4. Zoek de wijzigingsgeschiedenis van de gebruiker, klik of tik op het selectievakje naast de rij(en) en klik of tik op **Wijzigingsgeschiedenis verwijderen**.

## <a name="personal-data-stored-in-databases-of-cds-for-apps"></a>Persoonsgegevens die zijn opgeslagen in de databases van CDS for Apps

### <a name="prerequisites"></a>Vereisten
Mogelijk worden persoonsgegevens van personen (zoals uw eigen klanten) opgeslagen in uw CDS for Apps-entiteiten.  

CDS-systeembeheerders moeten een inventarisatie bijhouden van waar persoonsgegevens zijn opgeslagen in verschillende entiteiten voor elke persoon, zodat hij of zij die gegevens kan vinden in geval van een aanvraag van een betrokkene.  

Persoonsgegevens kunnen vervolgens met behulp van een productfunctie worden geëxporteerd, gecorrigeerd of in een entiteit worden verwijderd.  

### <a name="discover"></a>Ontdekken
Wanneer een CDS-systeembeheerder een aanvraag van een persoon ontvangt, moet de beheerder bepalen welke omgevingen/CDS-instanties persoonsgegevens van deze persoon bevatten. Persoonsgegevens worden gewoonlijk opgeslagen in hoofdentiteiten (bijvoorbeeld Account, Contactpersoon, Potentiële klanten, Verkoopkans enzovoort), maar het is uw verantwoordelijkheid om beleidsmaatregelen en procedures te ontwikkelen voor het onderhouden van een inventaris van waar u de persoonsgegevens van elke persoon opslaat, zodat u kunt reageren op aanvragen van betrokkenen.

Met een inventaris kunnen CDS-systeembeheerders de zoekentiteiten en -velden configureren en vervolgens de CDS for Apps-omgeving openen om persoonsgegevens te detecteren. Zie [Zoeken op relevantie configureren](https://go.microsoft.com/fwlink/?linkid=872506) voor meer informatie.

In het [PowerApps-beheercentrum](https://admin.powerapps.com/) gaat u als volgt te werk:

1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en selecteer een omgeving in de lijst.

2. Klik of tik op **Dynamics 365-beheercentrum**, selecteer een omgeving in de lijst, klik of tik op de zoekknop en vervolgens op **Zoeken op relevantie**.

    ![Het menu Zoeken op relevantie in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3. Voer de persoonsgegevens van de persoon in het zoekvak in en klik of tik op **Zoeken**.

    ![Resultaten voor Zoeken op relevantie in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

### <a name="rectify"></a>Corrigeren
De CDS-systeembeheerder kan de persoonsgegevens van een persoon bijwerken met behulp van de lijst met resultaten voor Zoeken op relevantie. De persoonsgegevens van een persoon kunnen echter ook zijn opgeslagen in andere aangepaste entiteiten. CDS-systeembeheerders moeten een inventaris van deze aangepaste entiteiten bijhouden en de nodige updates doorvoeren in de persoonsgegevens van een persoon.

Ga als volgt te werk in de resultaten voor Zoeken op relevantie:

1. Klik of tik op een item dat de persoonsgegevens van een persoon bevat.

2. Werk de persoonsgegevens van de persoon waar nodig bij en klik of tik op **Opslaan**.

    ![Details van PowerApps-accounts](./media/common-data-service-gdpr-dsr-guide/powerapps-account-details.png)

### <a name="export"></a>Exporteren
U kunt een schermopname van de gegevens maken en deze delen met de aanvrager.

In het [PowerApps-beheercentrum](https://admin.powerapps.com/) gaat u als volgt te werk:

1. Klik of tik in het navigatiedeelvenster op **Omgevingen** en selecteer een omgeving in de lijst.

2. Klik of tik op **Dynamics 365-beheercentrum**, selecteer een omgeving in de lijst, klik of tik op de zoekknop en vervolgens op **Zoeken op relevantie**.

    ![Het menu Zoeken op relevantie in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3. Voer de persoonsgegevens van de persoon in het zoekvak in en klik of tik op **Zoeken**.

    ![Resultaten voor Zoeken op relevantie in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

4. Dubbelklik in de lijst met zoekresultaten op het item.

5. Druk op Alt-PrtScn om de schermopname te maken.

6. Sla de schermopname op in een bestand, dat u vervolgens naar de aanvrager kunt verzenden.

### <a name="delete"></a>Verwijderen
CDS-beheerders kunnen persoonsgegevens van een persoon verwijderen uit records waarin de gegevens zijn opgeslagen.  De CDS-systeembeheerder kan de record verwijderen waarin de persoonsgegevens zijn opgeslagen of de inhoud van de persoonsgegevens uit de record verwijderen.  

> [!NOTE]
> CDS-beheerders kunnen een omgeving aanpassen om te voorkomen dat een record uit een entiteit wordt verwijderd. Als een omgeving op deze manier is geconfigureerd, moet u de inhoud van de persoonsgegevens uit de record verwijderen in plaats van de record te verwijderen.

Ga als volgt te werk in de resultaten voor Zoeken op relevantie:

1. Klik of tik op een item dat de persoonsgegevens van een persoon bevat.

2. Tik of klik in het lint op **Verwijderen**. (De optie **Verwijderen** is uitgeschakeld als de record niet kan worden verwijderd).

    ![PowerApps-accounts verwijderen](./media/common-data-service-gdpr-dsr-guide/powerapps-account-delete.png)

## <a name="personal-data-stored-in-databases-of-the-previous-version-of-cds"></a>Persoonsgegevens die zijn opgeslagen in databases van vorige versies van CDS

### <a name="prerequisites"></a>Vereisten
Mogelijk worden persoonsgegevens van personen (zoals uw eigen klanten) opgeslagen in uw CDS-entiteiten.  

CDS-systeembeheerders moeten een inventarisatie bijhouden van waar persoonsgegevens zijn opgeslagen in verschillende entiteiten voor elke persoon, zodat hij of zij die gegevens kan vinden in geval van een aanvraag van een betrokkene.  

Persoonsgegevens kunnen vervolgens met behulp van een productfunctie worden geëxporteerd, gecorrigeerd of in een entiteit worden verwijderd.  

### <a name="discover"></a>Ontdekken
Wanneer een CDS-systeembeheerder een aanvraag van een persoon ontvangt, moet de beheerder bepalen welke omgevingen/CDS-instanties persoonsgegevens van deze persoon bevatten. Persoonsgegevens worden gewoonlijk opgeslagen in hoofdentiteiten (bijvoorbeeld Account, Contactpersoon, Potentiële klanten, Verkoopkans enzovoort), maar het is uw verantwoordelijkheid om beleidsmaatregelen en procedures te ontwikkelen voor het onderhouden van een inventaris van waar u de persoonsgegevens van elke persoon opslaat, zodat u kunt reageren op aanvragen van betrokkenen.

U vindt de persoonsgegevens van gebruikers van de vorige versie van CDS in de volgende bronnen:

|Bron | Doel | Website-toegang |  Toegang op programmeerniveau
| --- | --- | --- | ---
|Entiteitsrecords | Voor het vastleggen van zakelijke transacties in de respectieve bedrijfsentiteit. | [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) |    Nee

#### <a name="entity-records"></a>Entiteitsrecords
Persoonsgegevens van een persoon kunnen worden opgeslagen in elke bedrijfsentiteit.

Deze versie van CDS heeft een eigen databaseschema en infrastructuur. Deze versie van CDS heeft eigen entiteiten en u beheert deze entiteiten in [PowerApps](http://web.powerapps.com/).

Ga als volgt te werk om een lijst van uw entiteiten te bekijken:

1. Selecteer uw omgeving in de vervolgkeuzelijst **Omgeving**.

2. Klik of tik in het navigatievenster op **Gegevens** om de sectie uit te vouwen en klik of tik op **Entiteiten**.

    ![PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

3. Klik of tik in de lijst met entiteiten op een entiteit (bijvoorbeeld, de entiteit Account), zoals hieronder wordt weergegeven.

    ![De lijst PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

4. Klik of tik op het tabblad **Gegevens**. Er wordt een lijst met records voor de entiteit weergegeven.

    ![PowerApps Legacy-accountgegevens](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

5. Klik of tik op **Gegevens exporteren**.

6. Wanneer de export is voltooid, klikt of tikt u op **Openen in Excel** en vervolgens op **Bewerken inschakelen**.

7. Klik of tik op de zoekknop, voer de persoonsgegevens van de persoon in het zoekvak in en klik of tik op **Zoeken**.

8. Herhaal de bovenstaande stappen aan de hand van uw inventarislijst voor elke bedrijfsentiteit om de persoonsgegevens van alle personen te detecteren.

### <a name="rectify"></a>Corrigeren
Als een betrokkene u vraagt de persoonsgegevens te corrigeren die zich in de gegevens van uw organisatie bevinden, moeten u en uw organisatie bepalen of de aanvraag moet worden ingewilligd. Het corrigeren van gegevens kan het bewerken of redigeren van persoonsgegevens omvatten of het verwijderen van persoonsgegevens uit een document of een ander type item.

U kunt Azure Active Directory gebruiken om de identiteiten (persoonsgegevens) van uw gebruikers in de vorige versie van CDS te beheren. Zakelijke klanten kunnen correctieaanvragen van betrokkenen beheren met de beperkte bewerkingsfuncties binnen een bepaalde Microsoft-service. Als gegevensverwerker kan Microsoft door het systeem gegenereerde logboeken niet corrigeren, omdat deze feitelijke activiteiten weerspiegelen en een historisch overzicht vormen van gebeurtenissen in Microsoft-services. Zie [AVG: aanvragen van betrokkenen](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) voor meer informatie.

Om persoonsgegevens in de CDS-omgeving te corrigeren, kunt u de entiteitsgegevens exporteren naar een Excel-spreadsheet, de gegevens daar bijwerken en de wijzigingen weer in de database importeren.

CDS-systeembeheerders moeten alle entiteiten kunnen identificeren die persoonsgegevens van een persoon bevatten en moeten de volgende stappen kunnen uitvoeren voor elk van de entiteiten.

Ga in [PowerApps](http://web.powerapps.com/) als volgt te werk:

1. Klik of tik in het navigatievenster op **Gegevens** om de sectie uit te vouwen en klik of tik op **Entiteiten**.

    ![PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. Klik of tik in de lijst met entiteiten op een entiteit (bijvoorbeeld, de entiteit Account), zoals hieronder wordt weergegeven.

    ![De lijst PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. Klik of tik op het tabblad **Gegevens**. Er wordt een lijst met records voor de entiteit weergegeven.

    ![PowerApps Legacy-accountgegevens](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. Klik of tik op **Gegevens exporteren**.

5. Wanneer de export is voltooid, klikt of tikt u op **Openen in Excel** en vervolgens op **Bewerken inschakelen**.

6. Tik of klik in de menubalk op **Bestand**, klik of tik op **Opslaan als** en selecteer de locatie waar u het bestand wilt opslaan.

7. Breng de gewenste wijzigingen aan in de persoonsgegevens en sla de spreadsheet op.

10. Ga in PowerApps terug naar het tabblad **Gegevens** van de entiteit en klik of tik op **Gegevens importeren**.

11. Klik op **Zoeken** en selecteer en open de Excel-spreadsheet die u zojuist hebt bijgewerkt.

12. Klik op **Importeren**.

### <a name="export"></a>Exporteren
U kunt persoonsgegevens vanuit elke entiteit in een Excel-werkblad exporteren en weergeven.

Ga in [PowerApps](http://web.powerapps.com/) als volgt te werk:

1. Klik of tik in het navigatievenster op **Gegevens** om de sectie uit te vouwen en klik of tik op **Entiteiten**.

    ![PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. Klik of tik in de lijst met entiteiten op de entiteit die u wilt exporteren en weergeven (bijvoorbeeld de entiteit Account), zoals hieronder wordt weergegeven.

    ![De lijst PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. Klik of tik op het tabblad **Gegevens**. Er wordt een lijst met records voor de entiteit weergegeven.

    ![PowerApps Legacy-accountgegevens](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. Klik of tik op **Gegevens exporteren**.

    De exportbewerking wordt op de achtergrond uitgevoerd en u krijgt een melding zodra de bewerking is voltooid.

5. Klik of tik op **Openen in Excel** als u de geëxporteerde gegevens wilt weergeven.

### <a name="delete"></a>Verwijderen
Met de functie Exporteren/importeren kunt u persoonsgegevens verwijderen die zijn opgeslagen in entiteiten.

CDS-systeembeheerders moeten alle entiteiten kunnen identificeren die persoonsgegevens van een persoon bevatten en moeten de volgende stappen kunnen uitvoeren voor elk van de entiteiten.

Ga in [PowerApps](http://web.powerapps.com/) als volgt te werk:

1. Klik of tik in het navigatievenster op **Gegevens** om de sectie uit te vouwen en klik of tik op **Entiteiten**.

    ![PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2. Klik of tik in de lijst met entiteiten op de entiteit waaruit u persoonsgegevens wilt verwijderen (bijvoorbeeld de entiteit Account), zoals hieronder wordt weergegeven.

    ![De lijst PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

3. Klik of tik op het tabblad **Gegevens**. Er wordt een lijst met records voor de entiteit weergegeven.

    ![PowerApps Legacy-accountgegevens](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

4. Klik of tik op **Gegevens exporteren**.

5. Wanneer de export is voltooid, klikt of tikt u op **Openen in Excel** en vervolgens op **Bewerken inschakelen**.

6. Tik of klik in de menubalk op **Bestand**, klik of tik op **Opslaan als** en selecteer de locatie waar u het bestand wilt opslaan.

7. Verwijder de gewenste rijen die persoonsgegevens bevatten en sla het werkblad op.

10. Ga in PowerApps terug naar het tabblad **Gegevens** van de entiteit en klik of tik op **Gegevens importeren**.

11. Klik op **Zoeken** en selecteer en open de Excel-spreadsheet die u zojuist hebt bijgewerkt.

12. Klik op **Importeren**.