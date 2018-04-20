---
title: Common Data Service for apps | Microsoft Docs
description: Inleiding tot Common Data Service for Apps, entiteiten en logica aan de serverzijde.
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
ms.openlocfilehash: 939be0cc43e03836d97049addcff27a8e4b063a0
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2018
---
# <a name="common-data-service-for-apps"></a>Common Data Service for Apps

Met de Common Data Service kunt u veilig gegevens opslaan en beheren die worden gebruikt in apps die u hebt ontwikkeld of in apps van Microsoft en app-providers. De gegevens in Common Data Service worden opgeslagen in een set standaardentiteiten en aangepaste entiteiten. Een entiteit is een set velden waarin gegevens worden opgeslagen, vergelijkbaar met een tabel in een database. Nadat uw gegevens zijn opgeslagen, kunt u Microsoft PowerApps gebruiken om uitgebreide toepassingen te bouwen die gebruikmaken van uw gegevens:

* U kunt gebruikmaken van standaardentiteiten of aangepaste entiteiten maken ter ondersteuning van uw scenario en toepassing.
* Rechtstreeks PowerApps en stromen maken voor Common Data Service.
* Voeg aangepaste velden en relaties toe aan standaardentiteiten waarbij aanvullende informatie nodig is.
* Maak berekende en getotaliseerde velden voor uw entiteiten om te voorzien in consistente berekeningen in alle apps en analyses.
* Definieer bedrijfsregels om voor gegevenskwaliteit binnen entiteiten te zorgen, ongeacht met welke app u uw gegevens opent of bewerkt.
* Maak werkstromen en gebruik een integratie met Microsoft Flow om aanvullende acties en bedrijfsprocessen te bevorderen op basis van uw gegevens.
* Aangepaste en standaardentiteiten onderbrengen in een app die u ontwikkelt, net zo eenvoudig als met gegevens in andere bronnen.
* Maak verbinding met uw gegevens uit Microsoft Excel met invoegtoepassingen voor productiviteit van Common Data Service.
* Importeer en synchroniseer uw gegevens eenvoudig met Power Query.
* De gegevens binnen uw organisatie beveiligen met op rollen gebaseerde beveiliging tegen aangepaste en standaardentiteiten.
* Bied globale ondersteuning voor uw gegevens en toepassingen door gebruik te maken van vertalingen van entiteits- en veldnamen in de taal van uw gebruikers.

Elke entiteit bevat een reeks records die gebruikers kunnen maken, lezen, bijwerken en verwijderen, afhankelijk van hun machtigingen. U kunt relaties tussen entiteiten maken, zodat u informatie in de ene entiteit kunt opzoeken op basis van een record in een andere entiteit. U kunt bijvoorbeeld een aangepaste entiteit maken om bij te houden welke evenementen een klant heeft bezocht. Door de Klant toe te voegen als zoekveld aan uw aangepaste entiteit, maakt u een relatie tussen de twee entiteiten, die u kunt gebruiken in uw app en rapportage.

Zie [Prijzen](../../administrator/pricing-billing-skus.md) voor informatie over het aanschaffen van een abonnement voor het gebruik van Common Data Service.

## <a name="why-use-the-common-data-service-for-apps"></a>Waarom Common Data Service for Apps gebruiken?
Zowel aangepaste als standaardentiteiten binnen de Common Data Service bieden een veilige opslagoptie voor uw gegevens in de cloud. Met entiteiten kunt u een definitie van uw gegevens maken die is gericht op uw zakelijke activiteiten en die u binnen uw apps kunt gebruiken. Als u twijfelt over het gebruik van entiteiten, kijk dan eens naar de volgende voordelen:

* **Eenvoudig te beheren**: zowel de metagegevens als de gegevens worden opgeslagen in de cloud. U hoeft u geen zorgen te maken over de details of hoe de gegevens worden opgeslagen.
* **Eenvoudig te delen**: de gegevens kunnen makkelijk met collega's worden gedeeld, omdat PowerApps de machtigingen beheert.
* **Eenvoudig te beveiligen**: gegevens worden veilig opgeslagen, zodat gebruikers ze alleen kunnen bekijken als hun toegang wordt verleend. Met op rollen gebaseerde beveiliging kunt u de toegang tot entiteiten voor verschillende gebruikers binnen uw organisatie beheren.
* **Uitgebreide metagegevens**: gegevenstypen en relaties worden rechtstreeks in PowerApps gebruikt. Door bijvoorbeeld een veldtype-URL te definiëren worden uw gegevens als een hyperlink in uw app gepresenteerd.
* **Logica en validatie**: definieer berekende velden, bedrijfsregels, werkstromen en zakelijke processtromen om de kwaliteit van de gegevens te waarborgen en bedrijfsprocessen te bevorderen.
* **Hulpprogramma's voor productiviteit**: entiteiten zijn beschikbaar binnen de invoegtoepassingen voor Microsoft Excel om de productiviteit te vergroten en ervoor te zorgen dat uw gegevens toegankelijk zijn.

Als u een app ontwikkelt, kunt u standaardentiteiten en aangepaste entiteiten gebruiken, of beide. Als u met een standaardentiteit in uw app een bepaald doel kunt bereiken, dan kunt u beter deze gebruiken in plaats van dat u een aangepaste entiteit maakt die hetzelfde doet. Als u het doel bereikt door enkele wijzigingen aan de standaardentiteit aan te brengen, dan kunt u aan uw behoeften voldoen door velden toe te voegen.

* Standaardentiteiten zijn standaard opgenomen in de Common Data Service. Deze zijn, overeenkomstig de aanbevolen procedures, ontworpen om de meest algemene concepten voor een organisatie te ondervangen, zoals contactpersonen, accounts en producten. Zie [Standaardentiteiten](data-platform-intro.md#standard-entities) voor een volledige lijst van entiteiten.
* U kunt de functionaliteit van de standaardentiteiten uitbreiden door een of meer aangepaste entiteiten te maken voor het opslaan van informatie die uniek is voor uw organisatie. Zie [How to create a custom entity](create-custom-entity.md) (Een aangepaste entiteit maken) voor meer informatie.

> [!NOTE]
> Gebruik zoveel mogelijk standaardentiteiten (eventueel met aangepaste velden). Dit zorgt ervoor dat u in de toekomst kunt profiteren van nieuwe functies of apps die gebruikmaken van deze entiteiten.

## <a name="interacting-with-entities"></a>Interactie met entiteiten

Wanneer u een standaardentiteit gebruikt of een aangepaste entiteit maakt, zijn er in elk van beide meerdere elementen beschikbaar en kunnen verschillende acties worden uitgevoerd. Op basis van hoe eenvoudig of geavanceerd uw bedrijfsscenario is, kan worden bepaald welke functies u moet gebruiken. Als u de entiteiten wilt bekijken die beschikbaar zijn in uw omgeving, meldt u zich aan bij [PowerApps](https://web.powerapps.com) en klikt u in het menu links op Gegevens en vervolgens op Entiteiten.

![Entiteitsgegevens](./media/data-platform-cds-intro/entitylist.png "Entiteitsgegevens")

* Met elk **veld** kunt u een stukje informatie definiëren dat u wilt verzamelen en het gegevenstype of de indeling waarmee u dit wilt weergeven. Velden zijn vergelijkbaar met kolommen in databases of Excel.
* Via alternatieve **sleutels** kunt u efficiënt en nauwkeurig zoeken en communiceren met records in de entiteit wanneer niet de standaard unieke id wordt gebruikt. Dit is belangrijk wanneer u een bedrijfssleutel gebruikt of een integratie uitvoert met een extern systeem.
* Elke entiteit kan meerdere **relaties** hebben met andere entiteiten ter ondersteuning van zoekopdrachten en query's binnen verschillende entiteiten. Relaties kunnen zo worden gemaakt dat deze ondersteuning bieden voor veel-op-een-relaties, een-op-veel-relaties en veel-op-veel-relaties.
* Via **Weergaven** kan elke entiteit op verschillende manieren worden gepresenteerd, inclusief welke velden worden weergegeven, het filteren en sorteren van de gegevens. Deze presentaties worden opgeslagen als weergaven en kunnen in verschillende apps worden gebruikt. Mogelijk wilt u bijvoorbeeld alleen actieve accounts in uw app bekijken. Hiervoor gebruikt u een weergave die vooraf zo is gefilterd dat alleen actieve accounts worden weergegeven, om te voorkomen dat u dit filter bij elke gebruikte app opnieuw moet instellen.
* **Bedrijfsregels** kunnen worden gebruikt voor het valideren van de gegevens die in entiteiten worden gemaakt en bijgewerkt om gegevenskwaliteit te waarborgen. Elke bedrijfsregel kan gegevens valideren op meerdere velden en entiteiten en waarschuwings- en foutberichten oproepen, ongeacht de app die wordt gebruikt voor het maken van de gegevens.
* **Gegevens** die zijn opgeslagen in Common Data Service, zijn beschikbaar via de PowerApps-portal, PowerApps, Microsoft Excel en web-API's voor ontwikkelaars.

### <a name="system-fields"></a>Systeemvelden
Alle entiteiten, of ze nu standaard of aangepast zijn, worden gemaakt met een set kant-en-klare velden die u niet kunt wijzigen, verwijderen of op een bepaalde waarde kunt instellen. Dit zijn de belangrijkste systeemvelden:

## <a name="logic-and-validation"></a>Logica en validatie

Entiteiten in Common Data Service kunnen gebruikmaken van uitgebreide logica en validatie aan de serverzijde om gegevenskwaliteit te waarborgen en herhalende code terug te brengen bij het maken van apps en gebruiken van gegevens in de entiteit.

* **Bedrijfsregels** kunnen gegevens valideren op meerdere velden en entiteiten en waarschuwings- en foutberichten oproepen, ongeacht de app die wordt gebruikt voor het maken van de gegevens. Zie [Een bedrijfsregel maken](./data-platform-create-business-rule.md) voor meer informatie.
* **Zakelijke processtromen** bieden gebruikers begeleiding in het consistent invoeren van gegevens en het steeds weer volgen van dezelfde stappen. Zakelijke processtromen worden momenteel alleen ondersteund voor modelgestuurde apps. Zie [Overzicht zakelijke processtromen](/dynamics365/customer-engagement/customize/business-process-flows-overview) voor meer informatie.
* Via **Werkstromen** kunt u bedrijfsprocessen automatiseren zonder interactie met de gebruiker. Zie [Overzicht van werkstromen](/dynamics365/customer-engagement/customize/workflow-processes) voor meer informatie.
* **Bedrijfslogica met code** ondersteunt meer geavanceerde scenario's van ontwikkelaars bij het rechtstreeks uitbreiden van hun toepassing via code. Zie [Bedrijfslogica toepassen met code](../../developer/common-data-service/apply-business-logic-with-code.md) voor meer informatie.

## <a name="getting-data-into-the-common-data-service"></a>Gegevens ophalen in Common Data Service

Er zijn verschillende manieren om te beginnen met het ophalen van gegevens in Common Data Service:

* Maak een PowerApp of stroom om gegevens te maken.
* Gebruik Power Query om verbinding te maken met een online- of on-premises gegevensbron en deze rechtstreeks in Common Data Service te importeren. Met Power Query kunt u de entiteiten tevens maken tijdens het importeren op basis van het schema van de bron evenals transformaties uitvoeren op uw gegevens tijdens het importeren. Zie [Gegevens aan een entiteit in Common Data Service toevoegen met Power Query](./data-platform-cds-newentity-pq.md) voor meer informatie.

## <a name="developer-capabilities"></a>Mogelijkheden voor ontwikkelaars

Naast de functies die beschikbaar zijn via de [PowerApps](https://web.powerapps.com)-portal, bevat Common Data Service ook functies voor ontwikkelaars om programmatisch toegang te krijgen tot metagegevens en gegevens voor het maken van entiteiten en zakelijke logica, evenals interactie met gegevens. Zie [Overzicht van Common Data Service for Apps voor ontwikkelaars](../../developer/common-data-service/overview.md) voor meer informatie

## <a name="get-started"></a>Aan de slag
Als u het wilt uitproberen, kunt u een app te maken met een standaardentiteit of een [aangepaste entiteit maken](create-custom-entity.md), en vervolgens [een app maken die gebruikmaakt van die entiteit](../canvas-apps/data-platform-create-app.md).

## <a name="privacy-notice"></a>Privacyverklaring
Met Common Data Model van Microsoft PowerApps worden aangepaste entiteits- en veldnamen in onze diagnostische systemen verzameld en bewaard.  We gebruiken die kennis om Common Data Model voor onze klanten te verbeteren. De entiteits- en veldnamen die u maakt, geven ons inzicht in veelgebruikte scenario's binnen de Microsoft PowerApps-community. Met behulp daarvan kunnen we bepalen wat er ontbreekt bij de standaardentiteiten van de service, zoals schema's voor organisaties. De gegevens in de databasetabellen die aan deze entiteiten zijn gekoppeld, zijn niet toegankelijk voor en worden niet gebruikt door Microsoft. Ook worden de gegevens niet gerepliceerd buiten de regio waarin de database is ingericht. De aangepaste entiteits- en veldnamen worden echter mogelijk wel gerepliceerd in andere regio's. Ze worden verwijderd in overeenstemming met ons bewaarbeleid voor gegevens. Microsoft hecht veel waarde aan uw privacy, zoals beschreven in ons [Vertrouwenscentrum](https://www.microsoft.com/trustcenter/Privacy/default.aspx).

