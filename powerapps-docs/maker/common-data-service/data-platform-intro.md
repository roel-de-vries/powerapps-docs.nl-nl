---
title: Wat is Common Data Service voor Apps? | Microsoft Docs
description: 'Inleiding op Common Data Service (CDS) voor Apps, entiteiten en serverlogica.'
author: clwesene
manager: kfile
ms.service: powerapps
ms.topic: overview
ms.component: cds
ms.date: 05/01/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="what-is-common-data-service-for-apps"></a>Wat is Common Data Service voor Apps?
Met Common Data Service (CDS) voor Apps kunt u veilig gegevens opslaan en beheren die door zakelijke toepassingen worden gebruikt. Gegevens in CDS voor Apps worden opgeslagen in een set entiteiten. Een *entiteit* is een set records waarin gegevens worden opgeslagen, vergelijkbaar met de manier waarop met een tabel gegevens in een database worden opgeslagen. CDS voor Apps bevat een basisset met standaardentiteiten voor de gebruikelijke scenario's, maar u kunt ook aangepaste entiteiten maken die specifiek voor uw organisatie zijn en deze vullen met gegevens met behulp van Power Query. Makers van apps kunnen vervolgens PowerApps gebruiken om uitgebreide toepassingen te bouwen aan de hand van deze gegevens.

![Schermafbeelding met overzicht van het Business Application Platform.](./media/data-platform-cds-intro/platform.png "Platform-overzicht")

Zie [Prijsgegevens](../../administrator/pricing-billing-skus.md) voor informatie over het aanschaffen van een abonnement om CDS voor Apps te gebruiken.

## <a name="why-use-common-data-service-for-apps"></a>Waarom Common Data Service voor Apps gebruiken?
Standaardentiteiten en aangepaste entiteiten binnen CDS voor Apps bieden een veilige opslagoptie voor uw gegevens in de cloud. Met entiteiten kunt u een definitie van de gegevens van uw organisatie maken die is gericht op uw zakelijke activiteiten en die u binnen apps kunt gebruiken. Als u twijfelt over het gebruik van entiteiten, kijk dan eens naar de volgende voordelen:

* **Eenvoudig te beheren** &ndash; zowel de metagegevens als de gegevens die worden opgeslagen in de cloud. U hoeft u geen zorgen te maken over de details of hoe de gegevens worden opgeslagen.
* **Eenvoudig te beveiligen** &ndash; gegevens worden veilig opgeslagen, zodat gebruikers ze alleen kunnen bekijken als u ze toegang verleent. Met op rollen gebaseerde beveiliging kunt u de toegang tot entiteiten voor verschillende gebruikers binnen uw organisatie beheren.
* **Toegang tot uw Dynamics 365-gegevens** &ndash; gegevens in uw Dynamics 365-toepassingen worden ook opgeslagen in Common Data Service voor Apps, zodat u snel apps kunt bouwen die gebruikmaken van uw Dynamics 365-gegevens en uw apps uitbreiden met PowerApps.
* **Uitgebreide metagegevens** &ndash; gegevenstypen en relaties worden rechtstreeks in PowerApps gebruikt.
* **Logica en validatie** &ndash; definieer berekende velden, bedrijfsregels, werkstromen en bedrijfsprocesstromen om de kwaliteit van gegevens te waarborgen en bedrijfsprocessen te bevorderen.
* **Hulpprogramma's voor productiviteit** &ndash; entiteiten zijn beschikbaar binnen de invoegtoepassingen voor Microsoft Excel om de productiviteit te vergroten en ervoor te zorgen dat uw gegevens toegankelijk zijn.

## <a name="dynamics-365-and-the-common-data-service-for-apps"></a>Dynamics 365 en Common Data Service voor Apps

Dynamics 365-toepassingen, zoals Dynamics 365 for Sales, Service of Talent, gebruiken Common Data Service voor Apps ook om gegevens die worden gebruikt door de toepassingen op te slaan en te beveiligen. Zo kunt u met PowerApps en Common Data Service voor Apps direct apps bouwen op basis van uw zakelijke kerngegevens die al worden gebruikt in Dynamics 365 en hoeft u geen integratie uit te voeren.

* **Apps bouwen aan de hand van uw Dynamics 365-gegevens** &ndash; bouw snel apps aan de hand van uw bedrijfsgegevens in PowerApps of met behulp van de Pro Developer-SDK.
* **Herbruikbare bedrijfslogica en regels beheren** &ndash; bedrijfsregels en logica die al zijn gedefinieerd in uw Dynamics 365-entiteiten, worden toegepast op uw PowerApps om gegevensconsistentie te garanderen, ongeacht hoe uw gebruikers de gegevens benaderen of via welke app.
* **Herbruikbare vaardigheden in Dynamics 365 en PowerApps** &ndash; gebruikers die eerder in PowerApps of Dynamics 365 vaardigheden hebben geleerd, kunnen deze vaardigheden nu aanwenden in het nieuwe Common Data Service voor Apps-platform. Het maken van entiteiten, formulieren, grafieken en dergelijke gebeurt nu op dezelfde manier in uw toepassingen.

    > [!NOTE]
    > Dynamics 365 for Finance and Operations vereist momenteel de configuratie van Data Integrator om uw bedrijfsgegevens van Finance and Operations beschikbaar te stellen in Common Data Service voor Apps.

## <a name="integrating-data-into-the-common-data-service"></a>Gegevens integreren in Common Data Service

Om een app te bouwen, worden doorgaans gegevens uit meer dan één bron gebruikt. Dit kan soms op toepassingsniveau worden gedaan, maar er zijn ook gevallen waarbij u door deze gegevens in een algemeen archief te integreren eenvoudiger apps kunt bouwen. U hoeft dan maar één set met logica te onderhouden en te bewerken. Met Common Data Service voor Apps kunnen gegevens uit meerdere bronnen worden geïntegreerd in één archief, dat dan in PowerApps, Flow en Power BI kan worden gebruikt met de gegevens die al beschikbaar zijn via de Dynamics 365-toepassingen.

* **Geplande integratie met andere systemen** &ndash; gegevens die in een andere toepassing worden bewaard, kunnen regelmatig worden gesynchroniseerd met Common Data Service voor Apps, zodat u andere toepassingsgegevens in PowerApps kunt benutten.
* **Gegevens transformeren en importeren met behulp van PowerQuery** &ndash; het transformeren van gegevens bij het importeren in Common Data Service kan vanaf veel onlinegegevensbronnen worden gedaan via PowerQuery, een algemeen hulpprogramma dat wordt gebruikt in Excel en Power BI.
* **Eenmalige import gegevens** &ndash; eenvoudige import en export van Excel- en CSV-bestanden kan worden gebruikt voor een eenmalige of incidentele import van gegevens in Common Data Service voor Apps.

Zie [Gegevens aan een entiteit toevoegen in Common Data Service voor Apps met behulp van Power Query](data-platform-cds-newentity-pq.md) voor meer informatie over het integreren van gegevens in Common Data Service.

## <a name="interacting-with-entities"></a>Interactie met entiteiten
Als u een app ontwikkelt, kunt u standaardentiteiten en/of aangepaste entiteiten gebruiken. Standaardentiteiten zijn standaard opgenomen in CDS voor Apps. Deze zijn ontworpen conform de best practices om de meest algemene concepten en scenario's binnen een organisatie te ondervangen.

![Schermafbeelding van een lijst met entiteiten.](./media/data-platform-cds-intro/entitylist.png "Lijst met entiteiten")

Zie [Entiteitsverwijzing](https://docs.microsoft.com/powerapps/developer/common-data-service/reference/about-entity-reference) voor een volledige lijst met entiteiten.

U kunt de functionaliteit van de standaardentiteiten uitbreiden door een of meer aangepaste entiteiten te maken voor het opslaan van informatie die uniek is voor uw organisatie. Zie [Een aangepaste entiteit maken](create-custom-entity.md) voor meer informatie.

## <a name="logic-and-validation"></a>Logica en validatie
Entiteiten in CDS voor Apps kunnen gebruikmaken van uitgebreide serverlogica en -validatie om gegevenskwaliteit te waarborgen en herhalende code te beperken in elke app waarin gegevens in een entiteit worden gemaakt en gebruikt.

* **Bedrijfsregels** worden gebruikt voor het valideren van gegevens in meerdere velden en entiteiten, en bieden waarschuwings- en foutberichten, ongeacht de app die wordt gebruikt voor het maken van de gegevens. Zie [Een bedrijfsregel maken](./data-platform-create-business-rule.md) voor meer informatie.
* **Bedrijfsprocesstromen** bieden gebruikers begeleiding bij het consistent invoeren van gegevens en het steeds weer volgen van dezelfde stappen. Bedrijfsprocesstromen worden momenteel alleen ondersteund voor modelgestuurde apps. Zie [Overzicht van bedrijfsprocesstromen](/dynamics365/customer-engagement/customize/business-process-flows-overview) voor meer informatie.
* Via **werkstromen** kunt u bedrijfsprocessen automatiseren zonder gebruikersinteractie. Zie [Overzicht van werkstromen](/dynamics365/customer-engagement/customize/workflow-processes) voor meer informatie.
* **Bedrijfslogica met code** biedt ondersteuning voor geavanceerde scenario's van ontwikkelaars bij het rechtstreeks uitbreiden van de toepassing via code. Zie [Bedrijfslogica toepassen met code](../../developer/common-data-service/apply-business-logic-with-code.md) voor meer informatie.

## <a name="developer-capabilities"></a>Mogelijkheden voor ontwikkelaars
Naast de functies die beschikbaar zijn via de [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-portal, bevat CDS voor Apps ook functies voor ontwikkelaars om programmatisch toegang te krijgen tot metagegevens en gegevens voor het maken van entiteiten en zakelijke logica, evenals interactie met gegevens. Zie [Overzicht van Common Data Service voor Apps voor ontwikkelaars](../../developer/common-data-service/overview.md) voor meer informatie

## <a name="next-steps"></a>Volgende stappen
U gaat als volgt aan de slag met behulp van CDS voor Apps:
* [Maak een app met behulp van een Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md).
* [Maak een aangepaste entiteit](create-custom-entity.md) en [maak een app die gebruikmaakt van die entiteit](../canvas-apps/data-platform-create-app.md).
* [Gebruik Power Query](./data-platform-cds-newentity-pq.md) om verbinding te maken met een online- of on-premises gegevensbron en importeer de gegevens rechtstreeks in CDS voor Apps.

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard. We gebruiken deze informatie om het algemene gegevensmodel voor onze klanten te verbeteren. De entiteits- en veldnamen die de app Creators maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, worden door Microsoft niet geopend of gebruikt en worden niet buiten de regio gerepliceerd waarin de database wordt geleverd. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht aan de bescherming van uw privacy, zoals nader wordt beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).
