---
title: Common Data Service-beveiliging | Microsoft Docs
description: Op rollen gebaseerde beveiliging gebruiken om toegang tot entiteiten te beheren
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: uwm8ghMUCeI
courseduration: 8m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: d557f7a8a276c89910713bcd5a19d0908d1c52f0
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="common-data-service-security"></a>Common Data Service-beveiliging
In dit onderwerp komt de beveiliging in de Common Data Service aan de orde. De service werkt met een systeem op basis van rollen om gebruikers toegang tot gegevens te verlenen. Het beveiligingsmodel is hiërarchisch van opzet, waarbij elk niveau een ander toegangsniveau vertegenwoordigt. Het laagste niveau heeft betrekking op afzonderlijke machtigingen voor maken, lezen, bijwerken en verwijderen voor één entiteit. Een verzameling van deze machtigingen op entiteitsniveau vormt een machtigingenset. Een of meer machtigingensets kunnen vervolgens worden gebruikt door een rol. Een rol bevindt zich op het hoogste niveau, en omvat alle machtigingen die een gebruiker of een groep gebruikers nodig heeft.

## <a name="understanding-roles-and-permission-sets"></a>Uitleg over rollen en machtigingensets
In deze cursus hebben we het vooral gehad over powerapps.com en PowerApps Studio. In dit onderwerp gaan we naar het beheercentrum van PowerApps. Als u klikt op een omgeving in het beheercenter, ziet u onder **Beveiliging** tabbladen voor **omgevingsrollen** (die we in een vorige onderwerp hebben bekeken), **gebruikersrollen** en **machtigingensets**. Standaard zijn er twee gebruikersrollen:

* **Database-eigenaar** is een beheerdersrol met volledige toegang tot alle entiteiten.
* **Organisatiegebruiker** is de standaardrol die wordt toegewezen aan alle gebruikers. Deze rol biedt alle gebruikers toegang tot entiteiten die openbare gegevens bevatten.

![Gebruikersrollen van het beheercentrum](./media/learning-common-data-service-security/user-roles.png)

Standaard zijn er zijn twee machtigingensets voor elke entiteit 

* **Onderhouden** biedt volledige controle: maken, lezen, bijwerken en verwijderen van machtigingen.
* **Weergeven** biedt alleen-lezentoegang.

De volgende afbeelding laat de standaardmachtigingensets voor de entiteit Account zien. 

![Machtigingensets voor het beheercentrum](./media/learning-common-data-service-security/permission-sets.png)

In de video kunt u zien hoe u extra rollen en machtigingensets maakt zodat u afzonderlijke toegang voor uw apps kunt inschakelen. We maken een machtigingenset **Productoverzicht bijhouden** die volledige toegang biedt tot de aangepaste entiteit die we in een eerder onderwerp hebben gemaakt. We maken ook een **ReviewApp-eigenaar**-rol waaraan we de machtigingenset toewijzen.  

## <a name="restrict-access-to-a-database"></a>Toegang tot een database beperken
Toen we in een eerder onderwerp een database maakten, hielden we ons aan de standaardinstelling van open toegang tot de database. Als u de toegang wilt wijzigen, opent u het tabblad **Database**, klikt u op **Toegang beperken** en bevestigt u dat u de wijziging wilt doorvoeren.

![Toegang tot de database beperken](./media/learning-common-data-service-security/restrict-access.png)

In de beperkte modus moeten aan iedere gebruiker een of meer rollen zijn toegewezen. Een rol kan worden ingesteld voor een bepaalde positie binnen uw bedrijf en worden toegewezen aan iedere persoon die deze positie bekleedt. Gebruikers kunnen ook automatisch worden toegevoegd aan een rol die is gebaseerd op de Azure Active Directory-groepen waartoe ze behoren.

## <a name="wrapping-it-up"></a>Ter afsluiting
Beveiliging kan een complex onderwerp zijn, maar houd gewoon de hiërarchie van machtigingen in gedachten. Het begint allemaal met het maken, lezen, bijwerken en verwijderen van machtigingen voor een entiteit, die machtigingensets kunnen vormen, die vervolgens worden toegewezen aan rollen. Het is een flexibel systeem waarmee u toegang tot gegevens vrij nauwkeurig kunt beheren. 

Daarmee zijn we aan het eind gekomen van de sectie over Common Data Service en tevens aan het eind van deze cursus voor Gestuurd leren. We hopen dat u plezier hebt beleefd aan de cursus en dat u er veel van hebt opgestoken. Laat het ons weten als u bepaalde feedback hebt en kom gerust weer eens kijken omdat we materiaal blijven toevoegen. Raadpleeg de [documentatie bij PowerApps](https://powerapps.microsoft.com/tutorials/getting-started/) als u nu meer gedetailleerde informatie wilt. 

