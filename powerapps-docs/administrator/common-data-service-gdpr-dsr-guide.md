---
title: DSR-handleiding voor door de klant opgestelde gegevens | Microsoft Docs
description: PowerApps DSR-handleiding voor door de klant opgestelde gegevens
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/17/2018
ms.author: paulliew
ms.openlocfilehash: cff822e24f1384833caa0baa945a7d3d07a8ee9b
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2018
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-customer-data-in-common-data-service-for-apps"></a>Reageren op DSR-aanvragen voor klantgegevens in Common Data Service for Apps

## <a name="introduction-to-dsr-requests"></a>Inleiding tot DSR-aanvragen
Als bijdrage aan onze inzet om u als partner te helpen bij de implementatie van de AVG (Algemene verordening gegevensbescherming) van de EU, hebben we deze documentatie ontwikkeld om u te helpen bij de voorbereiding. In de documentatie wordt niet alleen beschreven wat we doen om voor te bereiden op de AVG, maar worden ook voorbeelden gegeven van stappen die u vandaag nog kunt uitvoeren met Microsoft om AVG-naleving te ondersteunen bij gebruik van PowerApps, Microsoft Flow en Common Data Service (CDS) for Apps.

De AVG verleent rechten aan personen (in de verordening "betrokkenen" genoemd) om persoonsgegevens te beheren die zijn verzameld door een werkgever of een andere instantie of organisatie ("verwerkingsverantwoordelijke" of "verantwoordelijke"). Volgens de AVG zijn persoonsgegevens een breed begrip. Hieronder vallen alle gegevens die verband houden met een geïdentificeerde of identificeerbare natuurlijke persoon. De AVG verleent betrokkenen specifieke rechten voor hun persoonsgegevens. Deze rechten omvat het verkrijgen van kopieën van hun persoonsgegevens, aanvragen voor correcties in de gegevens, beperken van de verwerking van de gegevens, verwijdering van de gegevens of een elektronisch exemplaar van de gegevens zodat deze naar een andere verantwoordelijke kunnen worden verplaatst. Een formele aanvraag van een betrokkene die is onderworpen aan een verantwoordelijke om actie te ondernemen op zijn persoonsgegevens wordt een DSR-aanvraag genoemd.

In de handleiding wordt beschreven hoe producten, services en beheerprogramma's van Microsoft worden gebruikt om onze klanten te helpen bij het vinden van hun persoonsgegevens om te reageren op DSR-aanvragen. Dit betreft in het bijzonder het vinden, bekijken en reageren op persoonsgegevens in de Microsoft-cloud. Hier volgt een beknopt overzicht van de processen die in deze handleiding worden beschreven:

1. **Detecteren**: Zoek- en detectietools gebruiken om snel klantgegevens te vinden die zijn onderworpen aan een DSR-aanvraag. Zodra mogelijk responsieve documenten zijn verzameld, kunt u een of meerdere DSR-acties uitvoeren die zijn beschreven in de volgende stappen om te reageren op de aanvraag. U kunt ook besluiten dat de aanvraag niet voldoet aan de richtlijnen van uw organisatie voor reacties op DSR-aanvragen.

2. **Toegang verkrijgen**: Persoonsgegevens ophalen die zich in de Microsoft-cloud bevinden en, indien aangevraagd, een kopie van deze gegevens maken die beschikbaar is voor de betrokkene.

3. **Herstellen**: Wijzigingen aanbrengen of andere aangevraagde acties uitvoeren op de persoonsgegevens, indien van toepassing.

4. **Beperken**: De verwerking van persoonsgegevens beperken door het verwijderen van licenties voor verschillende onlineservices of het uitschakelen van de gewenste services, waar mogelijk. U kunt ook gegevens uit de Microsoft-cloud verwijderen en deze on-premises of op een andere locatie bewaren.

5. **Verwijderen**: Permanent verwijderen van persoonsgegevens die zich bevinden in de Microsoft-cloud.

6. **Exporteren**: Een elektronisch exemplaar (in een machineleesbare indeling) van persoonlijke gegevens leveren aan de betrokkene van de gegevens.

In elke sectie van deze handleiding worden de technische procedures beschreven die een organisatie kan uitvoeren om te reageren op een DSR-aanvraag voor persoonsgegevens in de Microsoft-cloud.

## <a name="common-data-service-customer-data"></a>Klantgegevens in Common Data Service

> [!IMPORTANT]
> Van toepassing op zowel Common Data Service for Apps als Common Data Service (vorige versie)

Er zijn twee versies van Common Data Services (CDS): CDS for Apps en Common Data Service (vorige versie), die beide een ander proces volgen voor persoonsgegevens.

U kunt controleren welke CDS-omgeving u gebruikt door de volgende stappen uit te voeren op de [PowerApps-website](https://web.powerapps.com):

1.  Selecteer de **omgeving** in de vervolgkeuzelijst Omgeving.
2.  Navigeer naar **Gegevens** > **Entiteiten**.

    U gebruikt CDS for Apps als de volgende entiteiten worden weergegeven:

    ![De lijst PowerApps Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-entities-list.png)

    U gebruikt de vorige versie van CDS als de volgende entiteiten worden weergegeven:

    ![De lijst PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-list.png)

Nadat u hebt vastgesteld welke CDS-omgeving u gebruikt, kunt u de betreffende secties in dit document volgen om persoonsgegevens te identificeren.

> [!NOTE]
> Het kan zijn dat sommige omgevingen zich in CDS for Apps bevinden en andere in de vorige versie van CDS. Daarom moet u de onderstaande processen herhalen voor elke omgeving in uw organisatie.

## <a name="user-personal-data-in-common-data-service-for-apps"></a>Persoonsgegevens van gebruikers in Common Data Service for Apps

### <a name="prerequisites"></a>Vereisten
Voor toegang tot CDS moet een gebruiker worden gemaakt in het Office 365-beheercentrum en moet de juiste gebruikerslicentie voor Common Data Service worden toegewezen.  Ook is een beveiligingsrol vereist voordat de gebruiker Common Data Service kan gebruiken.

Persoonsgegevens van de gebruiker worden opgeslagen in het Office 365-beheercentrum en in de gebruikersentiteit van het CDS-systeem.  Bepaalde standaardpersoonsgegevens van de gebruiker worden opgeslagen en onderhouden in het Office 365-beheercentrum (zoals de gebruikersnaam, de UserId, het telefoonnummer, het e-mailadres en het adres van de gebruiker). Deze persoonsgegevens worden gesynchroniseerd naar de gebruikersentiteit van het CDS-systeem in alle omgevingen.  Een systeembeheerder kan deze persoonsgegevens alleen bijwerken in het Office 365-beheercentrum. Deze kenmerken worden vervolgens automatisch gesynchroniseerd naar CDS for Apps. Een systeembeheerder kan ook aangepaste kenmerken maken om aanvullende persoonsgegevens vast te leggen in de gebruikersentiteit van het CDS-systeem.  Deze aangepaste kenmerken worden in CDS onderhouden en beheerd door de systeembeheerder.

Wanneer een gebruiker wordt verwijderd uit het Office 365-beheercentrum, wordt de gebruikersrecord niet automatisch verwijderd uit de gebruikersentiteit van het CDS-systeem om te voorkomen dat zakelijke toepassingen die essentieel zijn voor de activiteiten van uw organisatie worden onderbroken.  Een systeembeheerder van CDS moet actie ondernemen om persoonsgegevens te vinden en te verwijderen uit CDS met behulp van de toepassing.

Alleen gebruikers die de rol Algemeen beheerder van Office 365 en de beveiligingsrol Systeembeheerder van CDS hebben, kunnen de hieronder genoemde acties Ontdekken, Herstellen, Exporteren en Verwijderen uitvoeren.

### <a name="discover"></a>Ontdekken

Systeembeheerders kunnen meerdere CDS-instanties maken.  Deze instanties kunnen worden gebruikt voor proefversies, ontwikkeling of productiedoeleinden.   Elk van deze instanties bevat een kopie van de systeemgebruikerentiteit met eventuele aangepaste kenmerken die zijn toegevoegd door de systeembeheerder, evenals persoonsgegevens van de gebruiker die zijn gesynchroniseerd door het Office 365-beheercentrum.

Systeembeheerders kunnen een lijst met alle CDS-instanties vinden door naar het Dynamics 365-beheercentrum in het PowerApps-beheercentrum te gaan.

In het [PowerApps-beheercentrum](https://admin.powerapps.com/):

1.  Ga naar het tabblad Omgevingen.
2.  Selecteer een omgeving in de lijst met omgevingen.
3.  Klik op de koppeling Dynamics 365-beheercentrum.

    ![Omgevingsdetails van PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-environment-details.png)

    Er wordt een lijst met alle instanties weergegeven.

    ![De PowerApps-instantiekiezer](./media/common-data-service-gdpr-dsr-guide/powerapps-instance-picker.png)

Persoonsgegevens van gebruikers van CDS kunnen op de volgende locaties worden gevonden:

|Resources met persoonsgegevens | Doel | Website-toegang | Toegang op programmeerniveau
| --- | --- | --- | ---
| Entiteitsrecord | Systeemgebruikerentiteit | [PowerApps-beheercentrum](https://admin.powerapps.com) | [Via Web-API](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)
| Controlegeschiedenis | Om klanten resources te laten identificeren die gebruikers hebben gemaakt, geopend, gewijzigd of verwijderd op entiteitsniveau. | [PowerApps-beheercentrum](https://admin.powerapps.com) | [Via Web-API](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api#basic-update)

#### <a name="user"></a>User
Persoonsgegevens van een gebruiker die worden onderhouden en beheerd in het Office 365-beheercentrum, worden opgeslagen in de Azure Active Directory.  Deze persoonsgegevens worden beheerd in het Office 365-beheercentrum en automatisch gesynchroniseerd naar alle CDS-omgevingen.  Een systeembeheerder kan deze persoonsgegevens niet rechtstreeks in CDS bijwerken terwijl de gebruiker actief is. De gegevens moeten rechtstreeks in het Office 365-beheercentrum worden bijgewerkt.  Aanvullende persoonsgegevens (zoals aangepaste kenmerken) kunnen rechtstreeks aan CDS worden toegevoegd en moeten handmatig door de systeembeheerder worden onderhouden en beheerd.

Een systeembeheerder van CDS kan de gebruiker en de persoonsgegevens van een gebruiker vinden door de volgende stappen uit te voeren:

In het [PowerApps-beheercentrum](https://admin.powerapps.com/):

1.  Ga naar het tabblad Omgevingen.
2.  Selecteer een omgeving in de lijst met omgevingen.
3.  Klik op de koppeling Dynamics 365-beheercentrum.
4.  Klik op de naam van de omgeving.
5.  Klik op de knop **Openen**.
6.  Navigeer naar **Instellingen** > **Beveiliging**.
7.  Klik op **Gebruikers**.
8.  Voer de gebruiker in het invoervak **Zoeken** in.
9.  Klik op de knop **Zoeken**.
10. Dubbelklik op de gebruiker.

    ![Formulier met PowerApp-gebruikers](./media/common-data-service-gdpr-dsr-guide/powerapps-user-form.png)

#### <a name="audit-history"></a>Controlegeschiedenis
Wanneer [Controletracering is ingeschakeld](https://docs.microsoft.com/dynamics365/customer-engagement/admin/audit-data-user-activity) voor een entiteit in Common Data Service, worden persoonsgegevens geregistreerd in de controlegeschiedenis, samen met de gebeurtenissen die de gebruiker heeft uitgevoerd.

### <a name="rectify"></a>Herstellen

Als een betrokkene u heeft gevraagd de persoonsgegevens te corrigeren die zich in de gegevens van uw organisatie bevinden, moeten u en uw organisatie bepalen of de aanvraag moet worden ingewilligd.  Het corrigeren van de gegevens kan acties omvatten zoals persoonsgegevens bewerken, redigeren of verwijderen uit een document of een ander type item.

U kunt Azure Active Directory gebruiken voor het beheren van identiteiten (persoonsgegevens) van uw eindgebruikers in Common Data Service for Apps. Zakelijke klanten kunnen DSR-herstelaanvragen beheren, inclusief beperkte bewerkingsfuncties volgens de aard van een bepaalde Microsoft-service.  Als gegevensverwerker kan Microsoft door het systeem gegenereerde logboeken niet corrigeren, omdat deze feitelijke activiteiten weerspiegelen en een historisch overzicht vormen van gebeurtenissen in Microsoft-services. Zie [AVG: DSR-aanvragen](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) voor meer informatie.

Zodra de gebruikersrecord uit Azure Active Directory is verwijderd, kunnen systeembeheerders resterende persoonsgegevens van gebruikers (zoals aangepaste kenmerken die ze hebben toegevoegd) verwijderen uit alle instanties.  

### <a name="export"></a>Exporteren

#### <a name="system-user"></a>Systeemgebruiker
Persoonsgegevens van de gebruiker die zijn opgeslagen in de systeemgebruikersentiteit, kunnen naar Excel worden geëxporteerd via de lijst met gebruikers in de portal.

In het [PowerApps-beheercentrum](https://admin.powerapps.com/):

1.  Ga naar het tabblad Omgevingen.
2.  Selecteer een omgeving in de lijst met omgevingen.
3.  Klik op de koppeling Dynamics 365-beheercentrum.
4.  Klik op de naam van de omgeving.
5.  Klik op de knop Openen. Ga naar Instellingen > Beveiliging.
6.  Selecteer de weergave Ingeschakelde gebruikers.
7.  Klik op de knop Exporteren naar Excel.

#### <a name="audit-history"></a>Controlegeschiedenis
Schermafbeeldingen van de controlegeschiedenis kunnen worden vastgelegd en gekopieerd uit de toepassing door de onderstaande stappen uit te voeren.
In het [PowerApps-beheercentrum](https://admin.powerapps.com/):
1.  Ga naar het tabblad Omgevingen.
2.  Selecteer een omgeving in de lijst met omgevingen.
3.  Klik op de koppeling Dynamics 365-beheercentrum.
4.  Klik op de naam van de omgeving.
5.  Klik op de knop Openen.
6.  Navigeer naar Instellingen > Controle.

    ![Menu Controlegeschiedenis in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-menu.png)

7.  Klik op de weergave Controleoverzicht.
8.  Zoek de controlerecord van de gebruiker.

    ![Details van Controlegeschiedenis in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-audit-history-details.png)

9.  Druk op Alt-PrtScn om een schermopname te maken.
10. Bewaar de schermopname als een bestand.
11. Vervolgens kunt u het bestand naar de DSR-aanvrager verzenden.

### <a name="delete"></a>Verwijderen

#### <a name="user"></a>User
Wanneer een gebruiker wordt verwijderd uit het Office 365-beheercentrum, wordt de status van de gebruiker ingesteld op Uitgeschakeld in CDS. De persoonsgegevens van de gebruiker worden echter niet automatisch verwijderd om te voorkomen dat zakelijke toepassingen die essentieel zijn voor de activiteiten van uw organisatie worden onderbroken.
Als u de persoonsgegevens van de gebruiker uit CDS wilt verwijderen, moet de systeembeheerder de persoonsgegevens van de uitgeschakelde gebruiker handmatig verwijderen.

#### <a name="remove-user-personal-data-via-user-form"></a>Persoonsgegevens van gebruikers verwijderen via het gebruikersformulier
Wanneer de gebruikersrecord is verwijderd uit Azure Active Directory, wordt het volgende bericht weergegeven op het gebruikersformulier.
Gegevens van deze gebruiker worden niet meer beheerd door Office 365. U kunt deze record bijwerken om te reageren op DSR-aanvragen door alle persoonsgegevens die zijn gekoppeld aan deze gebruiker te verwijderen of te vervangen.

In het [PowerApps-beheercentrum](https://admin.powerapps.com/):
1.  Ga naar het tabblad Omgevingen.
2.  Selecteer een omgeving in de lijst met omgevingen.
3.  Klik op de koppeling Dynamics 365-beheercentrum.
4.  Klik op de naam van de omgeving.
5.  Klik op de knop **Openen**.
6.  Klik op **Instellingen** > **Beveiliging** > **Gebruikers**.
7.  Selecteer de weergave **Uitgeschakelde gebruikers**.
8.  Voer de gebruikersnaam in **Records zoeken** in en klik op de knop **Zoeken**.
9.  Dubbelklik op de naam van de gebruiker in de zoekresultaten.
10. Verwijder alle persoonsgegevens en klik op **Opslaan**.

#### <a name="remove-user-personal-data-via-excel-importexport"></a>Persoonsgegevens van de gebruiker verwijderen via de import/export-functie in Excel
1.  Klik op **Instellingen** > **Beveiliging** > **Gebruikers**.
2.  Selecteer de weergave **Uitgeschakelde gebruikers**.
3.  Maak een Excel-sjabloon met alle gebruikerskolommen met persoonsgegevens die u wilt bijwerken.
4.  Klik op **Bestand downloaden**.
5.  Open het gedownloade Excel-bestand, breng uw wijzigingen aan en sla het bestand op.
6.  Ga terug naar het weergavevenster Uitgeschakelde gebruikers en klik op Gegevens importeren.
7.  Kies uw bijgewerkte Excel-bestand in het dialoogvenster voor het uploaden van bestanden.
8.  Breng alle noodzakelijke wijzigingen aan in het venster Velden toewijzen.
9.  Klik op Volgende en Verzenden.

Zie [Aanvullende informatie over Excel](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/analyze-your-data-with-excel-templates) over het gebruik van Excel-sjablonen.


#### <a name="remove-audit-history-via-the-audit-summary-view-form"></a>Controlegeschiedenis via het formulier Controleoverzichtsweergave

In het [PowerApps-beheercentrum](https://admin.powerapps.com/):
1.  Ga naar het tabblad Omgevingen.
2.  Selecteer een omgeving in de lijst met omgevingen.
3.  Klik op de koppeling Dynamics 365-beheercentrum.
4.  Klik op de naam van de omgeving.
5.  Klik op de knop Openen.
6.  Klik op Instellingen > Controle.
7.  Selecteer de weergave Controleoverzicht.
8.  Zoek de wijzigingsgeschiedenis die is uitgevoerd door de gebruiker.
9.  Klik op het selectievakje in de rij(en).
10. Klik op het pictogram Wijzigingsoverzicht verwijderen.

## <a name="personal-data-stored-in-common-data-service-for-apps-databases"></a>Persoonsgegevens van gebruikers in databases van Common Data Service for Apps

### <a name="prerequisites"></a>Vereisten
Mogelijk worden persoonsgegevens van personen (zoals uw eigen klanten) bewaard in de inhoud van uw CDS-entiteiten.  

Wanneer een persoon een DSR-aanvraag voor uw organisatie verzendt, moet de CDS-systeembeheerder alle entiteiten vinden waarin in de toepassing naar de persoon wordt verwezen.  De CDS-beheerder is verantwoordelijk voor het bijhouden van een inventaris van de locaties waar persoonsgegevens worden opgeslagen in de verschillende entiteiten die u gebruikt, zodat u op DSR-aanvragen van personen kunt reageren.

Persoonsgegevens in uw materiaal kunnen vervolgens worden geëxporteerd, hersteld of verwijderd in een entiteit met behulp van de functionaliteit in het product.  

### <a name="discover"></a>Ontdekken
Wanneer een CDS-beheerder een DSR-aanvraag van een persoon ontvangt, moet de beheerder bepalen welke instanties van de omgevingen/CDS persoonsgegevens van deze persoon bevatten.  U moet beleidsregels en procedures ontwikkelen voor het onderhouden van een inventaris van omgevingen, instanties en entiteiten waar u persoonsgegevens van personen bewaart, zodat u persoonsgegevens snel kunt terugvinden.

Met de inventaris van omgevingen, instanties, entiteiten en velden waarin persoonsgegevens worden opgeslagen, kunt u de CDS-zoekmachine-engine configureren om de persoonsgegevens terug te vinden.  Een CDS-beheerder kan de zoekentiteiten en velden configureren. Zie [Zoeken op relevantie configureren](https://go.microsoft.com/fwlink/?linkid=872506) voor meer informatie.
De CDS-beheerder kan vervolgens toegang krijgen tot de CDS-omgeving en een zoekopdracht uitvoeren.

1.  Klik op het pictogram **Zoeken**.
2.  Selecteer **Zoeken op relevantie**.

    ![Het menu Zoeken op relevantie in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-menu.png)

3.  Voer de persoonsgegevens in het zoekvak in.
4.  Klik op de knop Zoeken.

    ![Resultaten voor Zoeken op relevantie in PowerApps](./media/common-data-service-gdpr-dsr-guide/powerapps-relevance-search-results.png)

Persoonsgegevens worden doorgaans opgeslagen in de voornaamste entiteiten, zoals Account, Contact, Lead, Verkoopkansen, enzovoort, maar het is uw verantwoordelijkheid om een inventaris bij te houden van de locaties waar persoonsgegevens worden opgeslagen.

### <a name="rectify"></a>Herstellen
De CDS-systeembeheerder kan persoonsgegevens van een persoon bijwerken met behulp van de lijst met resultaten voor Zoeken op relevantie.  Het kan echter ook zijn dat u deze persoonsgegevens ook in andere entiteiten hebt opgeslagen.  De CDS-systeembeheerder is verantwoordelijk voor het onderhouden van een inventaris van deze aangepaste entiteiten en het bijwerken van de persoonsgegevens.

In de resultaten voor Zoeken op relevantie:

1.  Klik op een item waarin de afzonderlijke persoonsgegevens zijn gevonden.
2.  Werk, indien van toepassing, de afzonderlijke persoonsgegevens bij.
3.  Klik op Opslaan.

    ![Details van PowerApps-accounts](./media/common-data-service-gdpr-dsr-guide/powerapps-account-details.png)

### <a name="export"></a>Exporteren
Er kan een schermopname van de gegevens worden vastgelegd en gedeeld met de DSR-aanvrager door de onderstaande stappen uit te voeren.

In het [PowerApps-beheercentrum](https://admin.powerapps.com/):
1.  Ga naar het tabblad Omgevingen.
2.  Selecteer een omgeving in de lijst met omgevingen.
3.  Klik op de koppeling Dynamics 365-beheercentrum.
4.  Klik op de naam van de omgeving.
5.  Klik op het pictogram **Zoeken**.
6.  Selecteer Zoeken op relevantie.
7.  Voer de persoonsgegevens in het zoekvak in.
8.  Klik op de knop Zoeken.
9.  Zoek het item en dubbelklik erop.
10. Druk op <alt> <PrtScn> om een schermopname te maken.
11. Bewaar de schermopname als een bestand.
12. Vervolgens kunt u het bestand naar de DSR-aanvrager verzenden.

### <a name="delete"></a>Verwijderen

De CDS-beheerder kan persoonsgegevens van een persoon verwijderen uit records waarin de gegevens zijn opgeslagen.  De CDS-beheerder kan (1) de record verwijderen waarin de persoonsgegevens zijn opgeslagen of (2) de inhoud van de persoonsgegevens uit de record verwijderen.  

> [!NOTE]
> Een CDS-beheerder kan de omgeving aanpassen om te voorkomen dat een record van een entiteit wordt verwijderd. In een dergelijke configuratie moet u de inhoud van de persoonsgegevens verwijderen uit de record in plaats van de record zelf te verwijderen.

In de resultaten voor Zoeken op relevantie:
1.  Klik op een item waarin de afzonderlijke persoonsgegevens zijn gevonden.
2.  Klik op het pictogram Verwijderen op het lint (opmerking: dit pictogram is uitgeschakeld als de record niet kan worden verwijderd).

    ![PowerApps-accounts verwijderen](./media/common-data-service-gdpr-dsr-guide/powerapps-account-delete.png)

## <a name="personal-data-stored-in-common-data-service-previous-version-databases"></a>Persoonsgegevens van gebruikers in databases van Common Data Service (vorige versie)

### <a name="prerequisites"></a>Vereisten

Mogelijk worden persoonsgegevens van personen (zoals uw eigen klanten of gebruikers) bewaard in de inhoud van uw CDS-entiteiten.  

Wanneer een persoon een DSR-aanvraag voor uw organisatie verzendt, moet de CDS-systeembeheerder alle entiteiten vinden waarin in de toepassing naar de persoon wordt verwezen.  De CDS-beheerder is verantwoordelijk voor het bijhouden van een inventaris van de locaties waar persoonsgegevens worden opgeslagen in de verschillende entiteiten die u gebruikt, zodat u op DSR-aanvragen van personen kunt reageren.

Persoonsgegevens kunnen vervolgens worden geëxporteerd, hersteld of verwijderd in een entiteit met behulp van de functionaliteit in het product.  

### <a name="discover"></a>Ontdekken
Wanneer een CDS-beheerder een DSR-aanvraag van een persoon ontvangt, moet de beheerder bepalen welke instanties van de omgevingen/CDS persoonsgegevens van deze persoon bevatten.  U moet beleidsregels en procedures ontwikkelen voor het onderhouden van een inventaris van omgevingen, instanties en entiteiten waar u persoonsgegevens van personen bewaart, zodat u persoonsgegevens snel kunt terugvinden.

Persoonsgegevens van personen kunnen zich op de volgende locaties bevinden:

|Resources met persoonsgegevens | Doel | Website-toegang |    Toegang op programmeerniveau
| --- | --- | --- | ---
|Entiteitsrecords | Voor het vastleggen van zakelijke transacties in respectieve bedrijfsentiteiten. | PowerApps-ontwikkelaarsportal |    Nee

#### <a name="entity-records"></a>Entiteitsrecords
Afzonderlijke persoonsgegevens kunnen worden opgeslagen in elke bedrijfsentiteit.
Deze versie van Common Data Service heeft een eigen databaseschema en infrastructuur.  Deze versie bevat eigen entiteiten en het beheer van deze entiteiten wordt beheerd via de [PowerApps-website](http://web.powerapps.com/).

Een lijst van uw entiteiten bekijken:

1.  Selecteer de omgeving.

    ![PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities.png)

2.  Navigeer naar het tabblad **Gegevens** > **Entiteiten**.
3.  Selecteer de entiteit, bijvoorbeeld Accountentiteit.

    ![De lijst PowerApps Legacy Entities](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-entities-details-list.png)

4.  Klik op de entiteit.
5.  Klik op het tabblad **Gegevens**. Er wordt een lijst met records voor de entiteit weergegeven.

    ![PowerApps Legacy-accountgegevens](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

6.  Klik op het pictogram **Gegevens exporteren**.
7.  Open het Excel-werkblad zodra het exporteren is voltooid.
8.  Klik op het vak Bewerken inschakelen.
9.  Klik op het pictogram Zoeken en vinden.
10. Voer de persoonsgegevens in waarnaar u wilt zoeken.
Persoonsgegevens worden doorgaans opgeslagen in de voornaamste entiteiten, zoals Account, Contact, Lead, Verkoopkansen, Werknemer, enzovoort, maar het is uw verantwoordelijkheid om een inventaris bij te houden van de locaties waar persoonsgegevens worden opgeslagen.
11. **Herhaal de bovenstaande stappen voor elke bedrijfsentiteit voor het detecteren van de afzonderlijke persoonsgegevens** aan de hand van de inventaris van entiteiten waarin persoonsgegevens worden opgeslagen.

### <a name="rectify"></a>Herstellen
Als een betrokkene u heeft gevraagd de persoonsgegevens te corrigeren die zich in de gegevens van uw organisatie bevinden, moeten u en uw organisatie bepalen of de aanvraag moet worden ingewilligd.  Het corrigeren van de gegevens kan acties omvatten zoals persoonsgegevens bewerken, redigeren of verwijderen uit een document of een ander type item.

U kunt Azure Active Directory gebruiken voor het beheren van identiteiten (persoonsgegevens) van uw eindgebruikers in Common Data Service for Apps. Zakelijke klanten kunnen DSR-herstelaanvragen beheren, inclusief beperkte bewerkingsfuncties volgens de aard van een bepaalde Microsoft-service.  Als gegevensverwerker kan Microsoft door het systeem gegenereerde logboeken niet corrigeren, omdat deze feitelijke activiteiten weerspiegelen en een historisch overzicht vormen van gebeurtenissen in Microsoft-services.  

Zie [AVG: DSR-aanvragen](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) voor meer informatie.

Om persoonsgegevens te herstellen in de CDS-omgeving, kunt u de entiteitsgegevens exporteren naar een Excel-werkblad, de gegevens bijwerken en de wijzigingen vervolgens weer in de database importeren.
De CDS-beheerder is verantwoordelijk voor het identificeren van alle entiteiten waarin de afzonderlijke persoonsgegevens worden opgeslagen en het herhalen van de onderstaande stappen voor elk van deze entiteiten.

Op de [PowerApps-website](http://web.powerapps.com/):

1.  Klik op **Gegevens** > **Entiteiten**.
2.  Klik op de entiteit, bijvoorbeeld Account.
3.  Klik op de optie **Gegevens**.
4.  Klik op het pictogram **Gegevens exporteren**.
5.  Klik op het pictogram **Openen in Excel** (nadat de export is uitgevoerd).
6.  **Schakel bewerken** in het Excel-werkblad in en werk de persoonsgegevens bij.
7.  **Sla** uw bijgewerkte werkblad op (gebruik **Opslaan als**, zodat u weet waar het bestand zich bevindt).

    ![PowerApps Legacy-accountgegevens](./media/common-data-service-gdpr-dsr-guide/powerapps-legacy-account-data.png)

8.  Breng de gewenste wijzigingen in de persoonsgegevens aan.
9.  Sla de updates op.
10. Op Gegevens > Entiteiten > Accountformulier klikt u op het pictogram Gegevens importeren.
11. Klik op het vak Zoeken.
12. Kies het bestand met de updates.
13. Klik op het vak Openen.
14. Klik op de knop Importeren.

### <a name="export"></a>Exporteren

U kunt persoonsgegevens van elke entiteit in een Excel-werkblad weergeven en exporteren.

Op de [PowerApps-website](http://web.powerapps.com/):

1.  Navigeer naar **Gegevens** > **Entiteiten**.
2.  Selecteer de **entiteit** die u wilt weergeven en waarvan u de gegevens wilt exporteren.
3.  Klik op de optie **Gegevens**.
4.  Klik op het pictogram **Gegevens exporteren**. Deze exportbewerking wordt op de achtergrond uitgevoerd en u krijgt een melding zodra de bewerking is voltooid.
5. Als u de geëxporteerde gegevens wilt weergeven, klikt u op het pictogram Openen in Excel.

### <a name="delete"></a>Verwijderen
U kunt persoonsgegevens die zijn opgeslagen in entiteiten verwijderen met de functionaliteit voor het exporteren/importeren van gegevens.

De CDS-beheerder is verantwoordelijk voor het identificeren van alle entiteiten waarin de afzonderlijke persoonsgegevens worden opgeslagen en het herhalen van de volgende stappen voor elk van de entiteiten.

Op de [PowerApps-website](http://web.powerapps.com/):

1.  Klik op **Gegevens** > **Entiteiten**.
2.  Schuif naar beneden naar de lijst **Entiteit** en zoek de entiteit waarvan u de persoonsgegevens wilt verwijderen.
3.  Klik op de entiteit.
4.  Klik op de optie **Gegevens**.
5.  Klik op het pictogram **Gegevens exporteren**.
6.  Klik op het pictogram **Openen in Excel** (nadat de export is uitgevoerd).
7.  **Schakel bewerken** in het Excel-werkblad in.
8.  **Sla** uw bijgewerkte werkblad op (gebruik Opslaan als, zodat u weet waar het bestand zich bevindt).
9.  Verwijder de rij(en) met de persoonsgegevensrecords die u wilt verwijderen.
10. Sla de updates op.
11. Klik op het formulier **Entiteiten** op het pictogram **Gegevens importeren**.
12. Klik op het vak **Zoeken**.
13. Kies het bestand met de updates.
14. Klik op het vak **Openen**.
15. Klik op de knop Importeren.
