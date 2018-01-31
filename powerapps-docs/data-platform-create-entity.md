---
title: Een aangepaste entiteit maken | Microsoft Docs
description: Een aangepaste entiteit maken op basis van een andere entiteit of een volledig nieuwe entiteit maken.
services: powerapps
documentationcenter: na
author: kfend
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
ms.openlocfilehash: e02a423f6a951c1c479b3941c6f361383244cafc
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="create-a-custom-entity"></a>Een aangepaste entiteit maken
U kunt een aangepaste entiteit maken om gegevens op te slaan die specifiek zijn voor uw organisatie. Vervolgens kunt u die gegevens weergeven door een app te ontwikkelen die naar de entiteit verwijst.

Er zijn twee manieren om een entiteit te maken:

* De entiteit helemaal vanaf nul maken. Standaard bevat de entiteit slechts [vier systeemvelden en een recordtitelveld](data-platform-create-entity.md#system-fields-and-the-record-title-field).
* Een entiteit maken die gebaseerd is op een andere entiteit door de velden en instellingen van die entiteit, maar niet de gegevens ervan, te kopiëren.

In beide gevallen zorgt Microsoft PowerApps automatisch voor het opslaan en beveiligen van de gegevens. Nadat u een entiteit hebt gemaakt, kunt u [een of meer velden maken of wijzigen](data-platform-manage-fields.md) en [relaties tussen entiteiten maken](data-platform-entity-lookup.md).

> [!NOTE]
> Zie de [lijst met standaardentiteiten](data-platform-intro.md#standard-entities) voordat u een entiteit maakt. Deze entiteiten betreffen typische scenario's, zoals accounts en contactpersonen. Als een van deze entiteiten in de huidige vorm of na enkele kleine aanpassingen aan uw vereisten voldoet, dan bespaart u zichzelf tijd door met die entiteit te beginnen.

## <a name="create-an-entity"></a>Een entiteit maken
1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Common Data Service** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.
2. Als u nog geen database hebt, dan moet u er een maken. Zie [Create a Common Data Service database (Een Common Data Service-database maken)](create-database.md) voor meer informatie.
3. Klik of tik in de rechterbovenhoek op **Nieuwe entiteit**.
4. Voer in het veld **De naam van de entiteit** een naam voor de entiteit in. Zorg voor een duidelijke en zinvolle naam, want u kunt de naam niet meer wijzigen nadat de entiteit is gemaakt. Wanneer u een app ontwikkelt, verwijst u in formules naar deze entiteitsnaam.
5. Geef een weergavenaam en (optioneel) een beschrijving op voor de entiteit en klik of tik op **Volgende**.
6. Optioneel: wijzig de waarde in het veld **Titel** in een waarde die relevanter is voor uw gegevens.
7. Klik of tik op **Maken** om de entiteit te maken.

Uw entiteit wordt weergegeven in de lijst met entiteiten in de database. Als u uw entiteit boven aan de lijst wilt weergeven, klikt of tikt u op de kolomkop **Type**. De entiteiten worden gesorteerd op type en alle aangepaste entiteiten worden boven de standaardentiteiten weergegeven.

## <a name="system-fields-and-the-record-title-field"></a>Systeemvelden en het recordtitelveld
Alle entiteiten hebben vijf systeemvelden. Deze velden zijn alleen-lezen. Daarom kunt u ze niet wijzigen of verwijderen en u kunt er geen waarden aan toekennen.

| Weergavenaam | Systeemveldnaam | Gegevenstype | Beschrijving |
| --- | --- | --- | --- |
| Id |Systeemveldnaam |Big Integer |De unieke identificatie van de record. |
| Created By |CreatedByUser |Tekst |De gebruiker die een record heeft gemaakt. |
| Created Record Date |CreatedOnDateTime |DateTime |De datum en tijd waarop een record is gemaakt. |
| Last modified By |LastModifiedByUser |Tekst |De gebruiker die de record het laatst heeft gewijzigd. |
| Modified Record Date |LastModifiedDateTime |DateTime |De datum en tijd waarop een record het laatst is gewijzigd. |

Wanneer u een volledig nieuwe entiteit maakt, bevat deze een aangepast veld met de naam **Titel**. Dit veld wordt ingesteld als het veld **Titel** van de record. De veldwaarde **Titel** is een gebruikersvriendelijke id van een record wanneer u die record in een app gebruikt. U kunt wijzigen welk veld het veld **Titel** wordt, maar elke entiteit moet een veld **Titel** hebben.

## <a name="next-steps"></a>Volgende stappen
* [Velden in een entiteit beheren](data-platform-manage-fields.md)
* [Relaties tussen entiteiten definiëren](data-platform-entity-lookup.md)
* [Een app genereren met behulp van een Common Data Service-database](data-platform-create-app.md)
* [Create an app from scratch using a Common Data Service database (Een volledig nieuwe app maken met behulp van een Common Data Service-database)](data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard.  We gebruiken die kennis om Common Data Model voor onze klanten te verbeteren. De entiteits- en veldnamen die u maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, zijn niet toegankelijk voor en worden niet gebruikt door Microsoft. Ook worden de gegevens niet gerepliceerd buiten de regio waarin de database is ingericht. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht veel waarde aan uw privacy, zoals beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

