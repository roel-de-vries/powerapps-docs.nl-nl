---
title: Wat is het Common Data Model? | Microsoft Docs
description: Common Data Model is een gestandaardiseerde, modulaire, uitbreidbare verzameling gegevensschema's die door Microsoft is gepubliceerd en waarmee u eenvoudiger gegevens kunt samenstellen, gebruiken en analyseren.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 07/24/2018
ms.author: robruc
ms.openlocfilehash: 1469646301c273067ad035428f03c452ae223604
ms.sourcegitcommit: abe4d4728db7f56088f618af5b820af78e7099c9
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2018
ms.locfileid: "39331989"
---
# <a name="what-is-the-common-data-model"></a>Wat is het Common Data Model?

Als u ooit te maken hebt gehad met gegevens die *bijna* hetzelfde zijn of die met elkaar *moeten* worden gebruikt en u vervolgens veel tijd hebt besteed aan het transformeren van velden en tabellen zodat deze in combinatie met andere gegevens kunnen worden gebruikt, weet u er alles van: met gemeenschappelijke gegevenselementen bespaart u zichzelf veel moeite, stroomlijnt u toekomstige ontwikkeling en maakt u snellere analyses mogelijk. Het Common Data Model (CDM) biedt deze mogelijkheden en nog meer.

Het **Common Data Model (CDM)** is een gestandaardiseerde, modulaire, uitbreidbare verzameling gegevensschema's die door Microsoft is gepubliceerd en waarmee u eenvoudiger gegevens kunt samenstellen, gebruiken en analyseren. Deze verzameling van vooraf gedefinieerde schema's, die bestaan uit *entiteiten*, *kenmerken*, *semantische metagegevens* en *relaties*, staan voor gemeenschappelijke concepten en activiteiten, zoals Account en Campagne, zodat u eenvoudiger gegevens kunt samenstellen, samenvoegen en analyseren. Meer informatie: [CDM-opslagplaats op GitHub](https://aka.ms/cdmrepo)

![Common Data Model](media/cdm-entities.png)

Meer informatie: [CDM-overzicht](https://aka.ms/cdmposter)

## <a name="why-use-the-common-data-model"></a>Waarom zou ik het Common Data Model gebruiken?

Met het CDM wordt het gegevensbeheer en de toepassingsontwikkeling vereenvoudigd doordat gegevens in een bekende vorm worden samengevoegd en doordat structurele en semantische consistentie wordt toegepast voor meerdere toepassingen en implementaties. Met andere woorden, wanneer uw gegevens in het CDM zijn opgenomen, kunt u deze in veel verschillende toepassingen gebruiken, het maken of gebruiken van andere toepassingen stroomlijnen zodat hierin die bestaande gegevens kunnen worden gebruikt en eenvoudig rapporten voor elk van die toepassingen (of alle) maken. Daarnaast kunnen gegevensintegrators die gegevens uit verschillende systemen leveren zich richten op het implementeren van de gegevens in het CDM en hoeven ze niet voor elke toepassing een nieuw model te maken.

Stel dat u over drie bedrijfstoepassingen beschikt; een app voor materialen, een app voor de productie en een app voor de verkoop. Vaak wordt elke toepassing afzonderlijk gemaakt, met verschillende structuren die staan voor een entiteit, zoals *Account*, die vrijwel identiek zijn (maar niet helemaal). Met het CDM kunt u de gegevens samenstellen in een standaardopmaak (met behulp van de CDM-entiteiten, -kenmerken en -relaties) en vervolgens kan elk van deze drie apps dezelfde gegevens als uitgangspunt gebruiken. Elke app kan natuurlijk eigen aanvullende gegevens en schema's bevatten, op basis van de functionaliteit van elke app. Maar als het gaat om het ontwikkelen, kunnen de standaardgegevenselementen snel, correct en gemakkelijk door de toepassingen en rapporten worden opgehaald.

En als ik een vierde app wil maken? Uw gegevens zijn gereed, in het CDM-schema, zodat u zich bij het ontwikkelen kunt richten op de bedrijfslogica, en niet op gegevensvraagstukken en tijdrovende transformaties.

Met andere woorden, het CDM heeft het volgende te bieden voor uw gegevens:

-   **Structurele en semantische consistentie** tussen toepassingen en implementaties.

-   **Vereenvoudigde integratie en ondubbelzinnigheid van gegevens** die zijn verzameld uit onder meer processen, digitale interacties, producttelemetrie en interactie tussen personen.

-   **Een gemeenschappelijke vorm** waarin door gegevensintegraties **bestaande bedrijfsgegevens kunnen worden gecombineerd met andere bronnen** en die gegevens als geheel kunnen worden gebruikt om nieuwe toepassingen te ontwikkelen of inzichten op te doen.

-   **Mogelijkheid om het schema en de CDM-entiteiten uit te breiden** om het Common Data Model af te stemmen op uw organisatie.

U kunt met het CDM nieuwe gegevensopslagplaatsen maken die overeenkomen met het schema en ook uw bestaande gegevens transformeren in het Common Data Model-schema. In ieder geval zorgt de standaardisering voor een efficiënte werkwijze, waarmee u de verwerking en bewerking van gegevens versnelt en stroomlijnt.

## <a name="who-uses-the-common-data-model"></a>Wie gebruikt het Common Data Model?

Het CDM wordt gebruikt door verschillende klanten, partners en producten. Hierbij is het doel altijd hetzelfde: de gegevens samenbrengen in een bekende vorm op basis van semantiek.

-   **Ontwikkelaars van toepassingen**: of deze gebruikers nu gebruikmaken van platforms op basis van code of van een platform met weinig of geen code, zoals PowerApps, ze moeten gegevens voor hun toepassingen opslaan en beheren.

-   **Gegevensintegrators**: deze gebruikers zijn verantwoordelijk voor het leveren van gegevens uit een aantal systemen zodat deze door toepassingen kunnen worden gebruikt.

In het verleden was het ontwikkelen van een toepassing nauw verweven met gegevensintegratie, maar met het CDM en de platforms die dit ondersteunen kunnen beide onafhankelijk plaatsvinden.

## <a name="common-data-model-in-action"></a>Common Data Model in actie

Microsoft en haar partners gebruiken het CDM voor hun eigen toepassingen en producten, en ontwikkelen aanvullende services en producten op basis van CDM-schema's. In de volgende voorbeelden ziet u hoe organisaties het CDM toepassen:

-   **Common Data Service (CDS) for Apps** die ondersteuning biedt voor Dynamics en PowerApps, slaat gegevens op in overeenstemming met de CDM-definitie. In feite zijn veel van de oorspronkelijke bedrijfsentiteiten die zijn opgenomen in het CDM afkomstig uit Dynamics-producten zoals Dynamics 365 for Sales en Dynamics 365 for Marketing.

-   **Verticale markten**, zoals de gezondheidszorg, werken nauw samen met Microsoft om het CDM uit te breiden naar hun specifieke bedrijfsconcepten, zoals *Patiënt* en *Zorgverzekering*, zodat ze de gegevens kunnen delen en services kunnen ontwikkelen. Op die manier kunnen partners eenvoudig gegevens uitwisselen, apps en services maken die onderling kunnen worden gebruikt en snelle analyses uitvoeren die eenvoudig kunnen worden gedeeld.

## <a name="next-step"></a>Volgende stap

[Het Common Data Model gebruiken](use-common-data-model.md): in dit onderwerp wordt het CDM in detail beschreven en worden scenario's besproken voor het maken van nieuwe gegevens in het CDM of het transformeren van uw bestaande gegevens naar het CDM.