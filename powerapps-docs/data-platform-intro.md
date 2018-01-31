---
title: Wat zijn entiteiten? | Microsoft Docs
description: Inleiding tot entiteiten, velden, relaties en databases.
services: powerapps
documentationcenter: na
author: clwesene
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/20/2017
ms.author: kfend
ms.openlocfilehash: bbc501542e634fab925654734cf709fe87248883
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="understand-entities-in-the-common-data-service"></a>Wat zijn entiteiten in de Common Data Service?

Met de Common Data Service kunt u gegevens veilig opslaan en beheren in een set aangepaste en standaardentiteiten. Een entiteit is een set velden waarin gegevens worden opgeslagen, vergelijkbaar met een tabel in een database. Nadat uw gegevens zijn opgeslagen, kunt u Microsoft PowerApps gebruiken om uitgebreide toepassingen te bouwen die gebruikmaken van uw gegevens:

* Gegevens importeren in aangepaste of standaardentiteiten.
* Aangepaste entiteiten maken voor uw scenario en toepassing.
* Aangepaste velden toevoegen aan standaardentiteiten waar aanvullende informatie nodig is.
* Aangepaste en standaardentiteiten onderbrengen in een app die u ontwikkelt, net zo eenvoudig als met gegevens in andere bronnen.
* Gebruikmaken van de invoegtoepassingen voor productiviteit om toegang te krijgen tot uw gegevens in Microsoft Excel en Outlook.
* De gegevens binnen uw organisatie beveiligen met op rollen gebaseerde beveiliging tegen aangepaste en standaardentiteiten.
* Selectielijsten van vooraf gedefinieerde gegevens toevoegen, zoals Land, Aanhef en Valuta.
* Globale ondersteuning bieden voor uw gegevens en toepassingen met vertalingen van entiteits- en veldnamen.

Elke entiteit bevat een verzameling records die gebruikers kunnen maken, lezen, bijwerken en verwijderen. U kunt relaties tussen entiteiten maken, zodat u informatie in de ene entiteit kunt opzoeken op basis van een record in een andere entiteit. U kunt bijvoorbeeld een aangepaste entiteit maken om bij te houden welke evenementen een klant heeft bezocht. Door de Klant toe te voegen als zoekveld aan uw aangepaste entiteit, maakt u een relatie tussen de twee entiteiten, die u kunt gebruiken in uw app en rapportage.

Zie [Prijzen](pricing-billing-skus.md) voor informatie over het aanschaffen van een abonnement voor het gebruik van Common Data Service.

## <a name="why-use-entities"></a>Waarom worden entiteiten gebruikt?
Zowel aangepaste als standaardentiteiten binnen de Common Data Service bieden een veilige opslagoptie voor uw gegevens in de cloud. Met entiteiten kunt u een definitie van uw gegevens maken die is gericht op uw zakelijke activiteiten en die u binnen uw apps kunt gebruiken. Als u twijfelt over het gebruik van entiteiten, kijk dan eens naar de volgende voordelen:

* **Eenvoudig te beheren**: zowel de metagegevens als de gegevens worden opgeslagen in de cloud. U hoeft u geen zorgen te maken over de details of hoe de gegevens worden opgeslagen.
* **Eenvoudig te delen**: de gegevens kunnen makkelijk met collega's worden gedeeld, omdat PowerApps de machtigingen beheert.
* **Eenvoudig te beveiligen**: gegevens worden veilig opgeslagen, zodat gebruikers ze alleen kunnen bekijken als hun toegang wordt verleend. Met op rollen gebaseerde beveiliging kunt u de toegang tot entiteiten voor verschillende gebruikers binnen uw organisatie beheren.
* **Uitgebreide metagegevens**: gegevenstypen en relaties worden rechtstreeks in PowerApps gebruikt. Door bijvoorbeeld een veldtype-URL te definiëren worden uw gegevens als een hyperlink in uw app gepresenteerd.
* **Hulpprogramma's voor productiviteit**: entiteiten zijn beschikbaar binnen de invoegtoepassingen voor Microsoft Excel en Outlook om de productiviteit te vergroten en ervoor te zorgen dat uw gegevens toegankelijk zijn.
* **Selectielijsten**: maak een selectie uit een groot aantal standaardselectielijsten om handige vervolgkeuzelijsten op te nemen in uw entiteiten en apps.

## <a name="standard-and-custom-entities"></a>Standaard- en aangepaste entiteiten
Als u een app ontwikkelt, kunt u standaardentiteiten en aangepaste entiteiten gebruiken, of beide. Als u met een standaardentiteit in uw app een bepaald doel kunt bereiken, dan kunt u beter deze gebruiken in plaats van dat u een aangepaste entiteit maakt die hetzelfde doet. Als u het doel bereikt door enkele wijzigingen aan de standaardentiteit aan te brengen, dan kunt u aan uw behoeften voldoen door velden toe te voegen.

* Standaardentiteiten zijn standaard opgenomen in de Common Data Service. Deze zijn, overeenkomstig de aanbevolen procedures, ontworpen om de meest algemene concepten voor een organisatie te ondervangen, zoals contactpersonen, accounts en producten. Zie [Standaardentiteiten](data-platform-intro.md#standard-entities) voor een volledige lijst van entiteiten.
* U kunt de functionaliteit van de standaardentiteiten uitbreiden door een of meer aangepaste entiteiten te maken voor het opslaan van informatie die uniek is voor uw organisatie. Zie [How to create a custom entity](data-platform-create-entity.md) (Een aangepaste entiteit maken) voor meer informatie.

> [!NOTE]
> Gebruik zoveel mogelijk standaardentiteiten (eventueel met aangepaste velden). Dit zorgt ervoor dat u in de toekomst kunt profiteren van nieuwe functies of apps die gebruikmaken van deze entiteiten.


## <a name="fields"></a>Velden
Elk veld heeft een naam, een weergavenaam, een gegevenstype en wat eenvoudige validatie. Gegevenstypen zijn onder andere **tekst**, **datum** of **getal**. Validatie garandeert dat verplichte velden gegevens en records bevatten die uniek zijn als dit volgens de entiteit vereist is. Elk veld behoort tot een van de volgende drie categorieën: systeemvelden, standaardvelden of aangepaste velden.

### <a name="system-fields"></a>Systeemvelden
Alle entiteiten, of ze nu standaard of aangepast zijn, worden gemaakt met een set kant-en-klare velden die u niet kunt wijzigen, verwijderen of op een bepaalde waarde kunt instellen. Zie [System and record title fields](data-platform-create-entity.md#system-fields-and-the-record-title-field) (Systeem- en recordtitelvelden) voor meer informatie. Dit zijn de belangrijkste systeemvelden:

* **Created Record Date**: de datum en tijd waarop een record is gemaakt.
* **Created By**: de gebruiker die de record heeft gemaakt.
* **Modified Record Date**: de datum en tijd waarop een record het laatst is gewijzigd.
* **Last Modified By**: de gebruiker die de record het laatst heeft gewijzigd.

### <a name="standard-fields"></a>Standaardvelden
Elke standaardentiteit bevat een set standaardvelden die u niet kunt wijzigen of verwijderen. Zie [Standaardentiteiten](https://docs.microsoft.com/common-data-service/entity-reference/standard-entities) voor een lijst met alle entiteiten en de bijbehorende velden.

### <a name="custom-fields"></a>Aangepaste velden
U kunt aangepaste velden in een standaard- of in een aangepaste entiteit maken. Voor elk aangepast moet u de naam, de weergavenaam en het gegevenstype opgeven. Zie [Entity field data types](https://docs.microsoft.com/en-us/common-data-service/entity-reference/field-data-types) (Gegevenstypen voor entiteitsvelden) voor een volledige lijst met ondersteunde typen.

## <a name="lookup-relationships"></a>Opzoekrelaties
U kunt tussen records in entiteiten navigeren als deze een relatie hebben die gedefinieerd is als een veld van het gegevenstype **Opzoeken**. Als u een opzoekrelatie wilt maken, voegt u een veld van het gegevenstype **Opzoeken** aan de ene entiteit toe en verwijst u naar de entiteit waarin u informatie wilt zoeken. Zie [Entity relationships via lookup field](data-platform-entity-lookup.md) (Entiteitsrelaties via opzoekveld) voor meer informatie.

## <a name="standard-entities"></a>Standaardentiteiten
Zie [Standaardentiteiten](https://docs.microsoft.com/common-data-service/entity-reference/standard-entities) voor een lijst met alle entiteiten en de bijbehorende velden en een lijst met de opsommingen.

| Functionele groep | Beschrijving |
| --- | --- |
| Customer Service |De Customer Service-entiteiten beheren problemen afkomstig van uw klanten, waaronder volgen, escaleren en documenteren. |
| Foundation |De Foundation-entiteiten bevatten informatie die relevant is voor vrijwel elke andere entiteitsgroep. Deze groep bevat entiteiten als Adres en Valuta. |
| Personen, organisaties en groepen |Deze entiteiten omvatten een uitgebreide set personen en organisaties waarmee u interactie kunt aangaan, waaronder werknemers, aannemers, donoren, vrijwilligers, fans, alumni en families. |
| Aanschaffen |Met de aanschafentiteiten kunt u oplossingen voor aankopen maken. |
| Verkoop |Met de Sales-entiteiten kunt u end-to-endverkoopoplossingen maken, van het volgen van leads en verkoopkansen, het verder doorzetten met contactpersonen, het accepteren en afleveren van orders tot het verzenden van facturen. |

## <a name="get-started"></a>Aan de slag
Als u het wilt uitproberen, kunt u een app te maken met een standaardentiteit of een [aangepaste entiteit maken](data-platform-create-entity.md), en vervolgens [een app maken die gebruikmaakt van die entiteit](data-platform-create-app.md).

<!--TODO - Add Link for Standard entity app - Template? -->

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard.  We gebruiken die kennis om Common Data Model voor onze klanten te verbeteren. De entiteits- en veldnamen die u maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, zijn niet toegankelijk voor en worden niet gebruikt door Microsoft. Ook worden de gegevens niet gerepliceerd buiten de regio waarin de database is ingericht. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht veel waarde aan uw privacy, zoals beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

