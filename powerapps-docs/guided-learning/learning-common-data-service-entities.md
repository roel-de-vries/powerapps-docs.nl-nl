---
title: Over Common Data Service-entiteiten | Microsoft Docs
description: "Entiteiten definiëren en gebruiken die worden toegewezen aan uw zakelijke gegevens en processen"
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: JJa6n_YaD-w
courseduration: 8m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: 3239a2c90edcd4274f9fabbbb47bd110c3ebcee6
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="understand-entities"></a>Entiteiten begrijpen
In het eerste onderwerp van deze sectie hebben we u laten kennismaken met Common Data Service, die een gemeenschappelijk gegevensmodel bevat. Het model bevat op zijn beurt entiteiten. Entiteiten zijn blokken gedeelde gegevens die kunnen worden gewijzigd, opgeslagen, opgehaald en waarmee kan worden gecommuniceerd. In dit onderwerp leert u meer over entiteiten, velden en gegevenstypen.

## <a name="standard-entities"></a>Standaardentiteiten
Het algemene gegevensmodel bevat een reeks standaardentiteiten die betrekking hebben op een scala van algemene bedrijfsbehoeften. Sommige van deze standaardentiteiten worden hieronder weergegeven.

![Standaardentiteiten van Common Data Service](./media/learning-common-data-service-entities/standard-entities.png)

De entiteiten zijn ingedeeld in categorieën zodat u gemakkelijk kunt zien welke goed samenwerken in een oplossing.

| Functionele groep | Beschrijving |
| --- | --- |
| Customer Service |De Customer Service-entiteiten beheren problemen afkomstig van uw klanten, waaronder volgen, escaleren en documenteren. |
| Foundation |De Foundation-entiteiten bevatten informatie die relevant is voor vrijwel elke andere entiteitsgroep. Deze groep bevat entiteiten als Adres en Valuta. |
| Personen, organisaties en groepen |Deze entiteiten omvatten een uitgebreide set personen en organisaties waarmee u interactie kunt aangaan, waaronder werknemers, aannemers, donoren, vrijwilligers, fans, alumni en families. |
| Aanschaffen |Met de aanschafentiteiten kunt u oplossingen voor aankopen maken. |
| Verkoop |Met de Sales-entiteiten kunt u end-to-endverkoopoplossingen maken, van het volgen van leads en verkoopkansen, het verder doorzetten met contactpersonen, het accepteren en afleveren van orders tot het verzenden van facturen. |

## <a name="fields-and-data-types"></a>Velden en gegevenstypen
Elke entiteit bevat een set standaardvelden die u niet kunt wijzigen of verwijderen. Sommige van deze velden, zoals **Contactpersoon-id**, zijn specifiek voor een entiteit. Andere, zoals **Created on date time**, gelden voor alle entiteiten. U kunt standaardentiteiten uitbreiden door velden toe te voegen. Klik of tik op **Veld toevoegen** en geef de eigenschappen van het nieuwe veld op.

![Velden en gegevenstypen voor entiteit Contact](./media/learning-common-data-service-entities/contact-entity-fields.png)

Als u een entiteit nodig hebt die volledig anders is (en waar uitbreiding van een standaardentiteit niet voldoende is), maakt u een aangepaste entiteit. Dat gaan we in het volgende onderwerp behandelen.

De velden in een entiteit hebben elk een gegevenstype, zoals Nummer. De aanwezigheid van verschillende gegevenstypen, in plaats van één algemeen gegevenstype, is nuttig omdat u hiermee allerlei dingen met uw apps kunt doen. Wanneer u bijvoorbeeld een veld van het type Nummer hebt, kunnen uw apps een schuifregelaar gebruiken wanneer een gebruiker dat veld bewerkt. U kunt kiezen uit een ruim aanbod van gegevenstypen. De volgende lijst bevat enkele representatieve voorbeelden daarvan:

* Basistypen, zoals Tekst en Nummer
* Complexere typen, zoals E-mail en Telefoon
* Speciale typen, zoals Opzoeken (voor het maken van relaties) en Selectielijst (voor een vaste set waarden voor een veld)  

## <a name="working-with-entities"></a>Werken met entiteiten
Wanneer u een entiteit opent, ziet u veel informatie en verschillende acties die u kunt uitvoeren. We kijken kort naar de tabbladen die beschikbaar zijn en naar de acties die u kunt uitvoeren om entiteitgegevens te beheren.

![Tabbladen voor entiteiten](./media/learning-common-data-service-entities/entity-tabs.png)

* **Velden**: velden en gegevenstypen bekijken, velden toevoegen – onderwerpen die we eerder hebben besproken.
* **Sleutel**: het veld dat elke rij in een entiteit identificeert, zoals Contactpersoon-id voor de entiteit Contact.
* **Relaties**: verbindingen tussen gerelateerde entiteiten zoals Product en Productcategorie. Daarvan geven we een voorbeeld in het volgende onderwerp.
* **Veldgroepen**: gebruikt om verschillende bewerkingen te beheren, zoals aangeven welke velden automatisch worden weergegeven wanneer u een app-scherm maakt in PowerApps.
* **Gegevens**: door voorbeeldgegevens en uw eigen gegevens bladeren nadat deze zijn geïmporteerd.

![Entiteitacties](./media/learning-common-data-service-entities/entity-actions.png)

* **Openen in Excel**: als u de invoegtoepassing PowerApps hebt geïnstalleerd, kunt u deze optie gebruiken om uw gegevens te verkennen en bewerken in Excel.
* **Gegevens importeren**: gegevens vanuit Excel en CSV-bestanden importeren.
* **Gegevens exporteren**: gegevens exporteren naar een Excel-bestand.
* **Sjabloon exporteren**: de structuur van een entiteit exporteren naar een Excel-bestand zodat u het bestand kunt vullen met gegevens en het bestand weer terug in de entiteit kunt importeren.
* **Instellingen** en **Verwijderen**: niet beschikbaar voor standaardentiteiten.

## <a name="connecting-to-a-standard-entity-in-powerapps-studio"></a>Verbinding maken met een standaardentiteit in PowerApps Studio
Nu u weet wat entiteiten zijn, gaan we bekijken hoe we verbinding kunnen maken met de entiteit Contact in PowerApps Studio. Klik of tik op **Nieuw** en klik of tik onder **Common Data Service** op **Telefoonindeling**. Links ziet u beschikbare gegevensverbindingen en rechts ziet u de lijst met entiteiten. Probeer zelf verbinding te maken en genereer een app vanuit de entiteit.

![Verbinding maken met entiteit in PowerApps Studio](./media/learning-common-data-service-entities/connect-to-standard-entity.png)

In het volgende onderwerp leert u aangepaste entiteiten te maken, evenals relaties tussen entiteiten.

