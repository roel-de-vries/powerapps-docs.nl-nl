---
title: Snelstartgids voor het maken van een aangepaste entiteit | Microsoft Docs
description: Snelstartgids voor het maken van een aangepaste entiteit op basis van een andere entiteit of een volledig nieuwe entiteit maken.
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: e22a18bacb258ca46c8f36d647f9ebcc45282929
ms.sourcegitcommit: d7ed5144f96d1ecc17084c30ed0e2ba3c6b03c26
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/19/2018
---
# <a name="quickstart-create-a-custom-entity"></a>Snelstartgids: Een aangepaste entiteit maken
U kunt een aangepaste entiteit maken om gegevens op te slaan die specifiek zijn voor uw organisatie. Vervolgens kunt u die gegevens weergeven door een app te ontwikkelen die naar de entiteit verwijst. Nadat u een entiteit hebt gemaakt, kunt u [een of meer velden maken of wijzigen](data-platform-manage-fields.md) en [relaties tussen entiteiten maken](data-platform-entity-lookup.md).

In deze instructies wordt beschreven hoe u handmatig een aangepaste entiteit kunt maken. U kunt ook via Power Query een entiteit maken die is gebaseerd op bestaande gegevens. Zie [Nieuwe entiteit met Power Query maken](data-platform-cds-newentity-pq.md) voor meer informatie

> [!NOTE]
> Zie de [Referentie entiteit](../../developer/common-data-service/reference/about-entity-reference.md) voordat u een entiteit maakt. Deze entiteiten betreffen typische scenario's, zoals accounts en contactpersonen. Als een van deze entiteiten in de huidige vorm of na enkele kleine aanpassingen aan uw vereisten voldoet, dan bespaart u zichzelf tijd door met die entiteit te beginnen.

## <a name="create-an-entity"></a>Een entiteit maken
1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsgegevens](./media/data-platform-cds-create-entity/entitylist.png "Entiteitslijst")

2. Tik of klik in de opdrachtbalk **Nieuwe entiteit**.
3. Voer in het veld **Weergavenaam** een eenvoudig herkenbare naam in waarmee u in de toekomst naar deze entiteit kunt verwijzen. Deze naam wordt ook gebruikt in formulieren, diagrammen en andere objecten die zijn gemaakt met deze entiteit. Hier ziet u twee andere velden die ook worden gevuld:

    * Weergavenaam in meervoud: dit wordt gebruikt bij het communiceren met deze entiteit vanuit PowerApps of Flow en wordt gebruikt als naam van de entiteit via de WebAPI van Common Data Service. De naam in meervoud wordt automatisch gegenereerd, maar kan worden gewijzigd.
    * Naam: dit is de unieke naam van de entiteit; de naam mag geen speciale tekens of spaties bevatten en moet uniek zijn. De naam bevat ook een voorvoegsel dat is ingesteld toen uw omgeving werd gemaakt. Dit wordt gebruikt om ervoor te zorgen dat de entiteiten die u maakt, kunnen worden geëxporteerd en geïmporteerd naar andere omgevingen zonder conflicten met andere entiteitsnamen. Dit voorvoegsel kan worden gewijzigd door het voorvoegsel van de uitgever van de Common Data Service-standaardoplossing bij te werken.

    > [!NOTE]
    > De velden **Weergavenaam** kunnen op elk gewenst moment worden bijgewerkt zodat deze anders worden weergegeven in uw apps. Het veld **Naam** kan niet worden gewijzigd nadat de entiteit is opgeslagen, aangezien dit kan leiden tot het verbreken van een bestaande app.

    ![Nieuwe entiteit](./media/data-platform-cds-create-entity/newentitypanel.png "deelvenster Nieuwe entiteit")

4. Klik op **Volgende** om naar de detailpagina voor Entiteit te gaan. Elke entiteit wordt standaard gestart met één veld, Primaire naam. Dit veld wordt gebruikt wanneer zoekacties zijn gemaakt op basis van deze entiteit. Deze dient doorgaans te worden gebruikt voor het opslaan van de naam of primaire beschrijving van de gegevens die in de entiteit worden opgeslagen.

    > [!NOTE]
    > De naam en de weergavenaam van het veld **Primaire naam** kunnen worden bijgewerkt voordat u de entiteit voor de eerste keer opslaat. Als u dit veld bijvoorbeeld 'Studentnaam' wilt noemen in plaats van 'Primaire naam'

    ![Details entiteit](./media/data-platform-cds-create-entity/newentitydetails.png "Details nieuwe entiteit")

5. Optioneel: voeg een nieuw veld toe aan uw entiteit door te klikken op **Veld toevoegen**. Voer in het deelvenster Nieuw veld de **Weergavenaam** voor uw veld in en selecteer het type gegevens. Zie [Manage fields in an entity](data-platform-manage-fields.md) (Velden in een entiteit beheren) voor meer informatie.

    ![Nieuw veld](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Deelvenster Nieuw veld")


6. Klik op **Gereed** om het veld toe te voegen en herhaal stap 5 om extra velden toe te voegen.
7. Klik op **Entiteit opslaan**om uw entiteit op te slaan en om deze beschikbaar te maken voor gebruik in apps.

    Uw entiteit wordt weergegeven in de lijst met entiteiten in de database. Als u entiteiten wilt zien die u hebt gemaakt, kunt u het filter in de opdrachtbalk wijzigen van Standaard in Aangepast

## <a name="system-fields"></a>Systeemvelden
Alle entiteiten hebben systeemvelden. Deze velden zijn alleen-lezen. Daarom kunt u ze niet wijzigen of verwijderen en u kunt er geen waarden aan toekennen. Standaard worden systeemvelden niet weergegeven in de lijst met velden, hoewel ze zich wel op de entiteit bevinden. Voor een overzicht van alle velden kunt u het filter in de opdrachtbalk wijzigen van **Standaard** naar **Alle**.

Zie [Metagegevens van entiteiten](../../developer/common-data-service/entity-metadata.md) voor meer informatie over de metagegevens die zijn gerelateerd aan een entiteit

## <a name="next-steps"></a>Volgende stappen
* [Velden in een entiteit beheren](data-platform-manage-fields.md)
* [Relaties tussen entiteiten definiëren](data-platform-entity-lookup.md)
* [Een app genereren met behulp van een Common Data Service-database](../canvas-apps/data-platform-create-app.md)
* [Create an app from scratch using a Common Data Service database (Een volledig nieuwe app maken met behulp van een Common Data Service-database)](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard.  We gebruiken die kennis om Common Data Model voor onze klanten te verbeteren. De entiteits- en veldnamen die u maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, zijn niet toegankelijk voor en worden niet gebruikt door Microsoft. Ook worden de gegevens niet gerepliceerd buiten de regio waarin de database is ingericht. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht veel waarde aan uw privacy, zoals beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

