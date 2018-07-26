---
title: Wat is Common Data Service for Apps? | Microsoft Docs
description: Inleiding tot Common Data Service (CDS) voor apps, entiteiten en logica aan de serverzijde.
author: clwesene
manager: kfile
ms.service: powerapps
ms.topic: overview
ms.component: cds
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: 6a8bc8f24ce0f772f5c98852838095f233c4317f
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218068"
---
# <a name="what-is-common-data-service-for-apps"></a>Wat is Common Data Service for Apps?
Met Common Data Service (CDS) voor apps kunt u veilig gegevens die door zakelijke toepassingen worden gebruikt, opslaan en beheren. De gegevens in CDS voor apps worden opgeslagen in een set entiteiten. Een *entiteit* is een set records waarin gegevens worden opgeslagen, vergelijkbaar met de manier waarop met een tabel gegevens in een database worden opgeslagen. CDS voor apps bevat een basisset met standaardentiteiten die voor de gebruikelijke scenario's, maar u kunt ook aangepaste entiteiten maken die specifiek voor uw organisatie zijn en deze invullen met gegevens met behulp van Power Query. App-makers kunnen vervolgens PowerApps gebruiken om uitgebreide toepassingen te bouwen aan de hand van deze gegevens.

![Schermafbeelding van een overzicht van het Platform voor zakelijke toepassingen.](./media/data-platform-cds-intro/platform.png "Platform-overzicht")

Zie [Prijzen](../../administrator/pricing-billing-skus.md) voor informatie over het aanschaffen van een abonnement voor het gebruik van CDS voor apps.

## <a name="why-use-common-data-service-for-apps"></a>Waarom Common Data Service for Apps gebruiken?
Standaardentiteiten en aangepaste entiteiten binnen CDS voor apps bieden een veilige opslagoptie voor uw gegevens in de cloud. Met entiteiten kunt u een definitie van de gegevens van uw organisatie maken die is gericht op uw zakelijke activiteiten en die u binnen apps kunt gebruiken. Als u twijfelt over het gebruik van entiteiten, kijk dan eens naar de volgende voordelen:

* **Eenvoudig te beheren** &ndash; zowel de metagegevens als de gegevens worden opgeslagen in de cloud. U hoeft u geen zorgen te maken over de details of hoe de gegevens worden opgeslagen.
* **Eenvoudig te beveiligen** &ndash; gegevens worden veilig opgeslagen, zodat gebruikers ze alleen kunnen bekijken als hun toegang wordt verleend. Met op rollen gebaseerde beveiliging kunt u de toegang tot entiteiten voor verschillende gebruikers binnen uw organisatie beheren.
* **Toegang tot uw Dynamics 365 gegevens** &ndash; gegevens in uw Dynamics 365-toepassingen worden ook opgeslagen in de Common Data Service for Apps, zodat u snel apps kunt bouwen die gebruikmaken van uw Dynamics 365-gegevens en uw apps uitbreiden met PowerApps.
* **Uitgebreide metagegevens** &ndash; gegevenstypen en relaties worden rechtstreeks in PowerApps gebruikt.
* **Logica en validatie** &ndash; definieer berekende velden, bedrijfsregels, werkstromen en zakelijke processtromen om de kwaliteit van de gegevens te waarborgen en bedrijfsprocessen te bevorderen.
* **Hulpprogramma's voor productiviteit** &ndash; entiteiten zijn beschikbaar binnen de invoegtoepassingen voor Microsoft Excel om de productiviteit te vergroten en ervoor te zorgen dat uw gegevens toegankelijk zijn.

## <a name="dynamics-365-and-the-common-data-service-for-apps"></a>Dynamics 365 en de Common Data Service for Apps

Dynamics 365-toepassingen, zoals Dynamics 365 for Sales, Service of Talent, gebruiken de Common Data Service for Apps ook om de gegevens die worden gebruikt door de toepassingen op te slaan en te beveiligen. Zo kunt u apps bouwen met behulp van PowerApps en de Common Data Service for Apps rechtstreeks op basis van uw zakelijke kerngegevens die al worden gebruikt in Dynamics 365 zonder de noodzaak tot integratie.

* **Apps bouwen aan de hand van uw Dynamics 365-gegevens** &ndash; bouw snel apps aan de hand van uw bedrijfsgegevens binnen PowerApps of met behulp van de Pro Developer-SDK.
* **Herbruikbare bedrijfslogica en regels beheren** &ndash; bedrijfsregels en logica die al zijn gedefinieerd in uw Dynamics 365-entiteiten, worden toegepast op uw PowerApps om gegevensconsistentie te garanderen, ongeacht hoe uw gebruikers de gegevens benaderen of via welke app.
* **Herbruikbare vaardigheden in Dynamics 365 en PowerApps** &ndash; gebruikers die eerder in PowerApps of Dynamics 365 vaardigheden hebben geleerd, kunnen deze vaardigheden nu aanwenden in het nieuwe Common Data Service for Apps-platform. Het maken van entiteiten, formulieren, grafieken is nu heel gangbaar in uw toepassingen.

    > [!NOTE]
    > Dynamics 365 for Finance and Operations vereist momenteel de configuratie van de Data Integrator om uw bedrijfsgegevens van Finance and Operations beschikbaar te stellen in de Common Data Service for Apps.

## <a name="integrating-data-into-the-common-data-service"></a>Gegevens integreren in de Common Data Service

Om een app te bouwen, worden doorgaans gegevens uit meer dan één bron gebruikt. Dit kan soms op toepassingsniveau worden gedaan, maar er zijn ook gevallen waarbij u door deze gegevens in een algemeen archief te integreren eenvoudiger apps kunt bouwen. U hoeft dan maar één set met logica te onderhouden en te bewerken. Met de Common Data Service for Apps kunnen gegevens uit meerdere bronnen worden geïntegreerd in één archief, dat dan kan worden gebruikt in PowerApps, Flow en Power BI samen met de gegevens die al beschikbaar zijn via de Dynamics 365-toepassingen.

* **Geplande integratie met andere systemen** &ndash; gegevens die in een andere toepassing worden bewaard, kunnen regelmatig worden gesynchroniseerd met de Common Data Service for Apps zodat u andere toepassingsgegevens in PowerApps kunt benutten.
* **Gegevens transformeren en importeren met behulp van PowerQuery** &ndash; het transformeren van gegevens bij het importeren in de algemene Common Data Service kan vanaf veel online gegevensbronnen worden gedaan via PowerQuery, een algemeen hulpprogramma dat wordt gebruikt in Excel en Power BI.
* **Eenmalige import gegevens** &ndash; eenvoudige import en export van Excel- en CSV-bestanden kan worden gebruikt voor een eenmalige of incidentele import van gegevens in de Common Data Service for Apps.


## <a name="interacting-with-entities"></a>Interactie met entiteiten
Als u een app ontwikkelt, kunt u standaardentiteiten en aangepaste entiteiten gebruiken, of beide. Standaardentiteiten zijn standaard opgenomen in CDS for Apps. Deze zijn ontworpen conform de best practices om de meest algemene concepten en scenario's binnen een organisatie te ondervangen.

![Schermopname van een lijst met entiteiten. ](./media/data-platform-cds-intro/entitylist.png "Lijst met entiteiten")

Zie [Referentie voor entiteiten](https://docs.microsoft.com/powerapps/developer/common-data-service/reference/about-entity-reference) voor een volledige lijst met entiteiten.

U kunt de functionaliteit van de standaardentiteiten uitbreiden door een of meer aangepaste entiteiten te maken voor het opslaan van informatie die uniek is voor uw organisatie. Zie [How to create a custom entity](create-custom-entity.md) (Een aangepaste entiteit maken) voor meer informatie.

## <a name="logic-and-validation"></a>Logica en validatie
Entiteiten in CDS voor apps kunnen gebruikmaken van uitgebreide logica en validatie aan de serverzijde om gegevenskwaliteit te waarborgen en herhalende code terug te brengen in elke app die gegevens binnen een entiteit maakt en gebruikt.

* **Bedrijfsregels** worden gebruikt voor het valideren van gegevens in meerdere velden en entiteiten en bieden waarschuwings- en foutberichten, ongeacht de app die wordt gebruikt voor het maken van de gegevens. Zie [Een bedrijfsregel maken](./data-platform-create-business-rule.md) voor meer informatie.
* **Zakelijke processtromen** bieden gebruikers begeleiding in het consistent invoeren van gegevens en het steeds weer volgen van dezelfde stappen. Zakelijke processtromen worden momenteel alleen ondersteund voor modelgestuurde apps. Zie [Overzicht zakelijke processtromen](/dynamics365/customer-engagement/customize/business-process-flows-overview) voor meer informatie.
* Via **werkstromen** kunt u bedrijfsprocessen automatiseren zonder gebruikersinteractie. Zie [Overzicht van werkstromen](/dynamics365/customer-engagement/customize/workflow-processes) voor meer informatie.
* **Bedrijfslogica met code** biedt ondersteuning voor geavanceerde scenario's van ontwikkelaars bij het rechtstreeks uitbreiden van de toepassing via code. Zie [Bedrijfslogica toepassen met code](../../developer/common-data-service/apply-business-logic-with-code.md) voor meer informatie.

## <a name="developer-capabilities"></a>Mogelijkheden voor ontwikkelaars
Naast de functies die beschikbaar zijn via de [PowerApps](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-portal, bevat CDS for Apps ook functies voor ontwikkelaars om programmatisch toegang te krijgen tot metagegevens en gegevens voor het maken van entiteiten en zakelijke logica, evenals interactie met gegevens. Zie [Overzicht van Common Data Service for Apps voor ontwikkelaars](../../developer/common-data-service/overview.md) voor meer informatie

## <a name="next-steps"></a>Volgende stappen
U gaat als volgt aan de slag met behulp van CDS voor apps:
* [Maak een app met behulp van een Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md).
* [Maak een aangepaste entiteit](create-custom-entity.md) en [maak daarna een app die gebruikmaakt van die entiteit](../canvas-apps/data-platform-create-app.md).
* [Gebruik Power Query](./data-platform-cds-newentity-pq.md) om verbinding te maken met een online- of on-premises gegevensbron en importeer de gegevens rechtstreeks in CDS voor apps.

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard. We gebruiken die kennis om Common Data Model voor onze klanten te verbeteren. De entiteits- en veldnamen die door app-makers worden gemaakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, zijn niet toegankelijk voor en worden niet gebruikt door Microsoft. Ook worden de gegevens niet gerepliceerd buiten de regio waarin de database is ingericht. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht veel waarde aan uw privacy, zoals beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).
