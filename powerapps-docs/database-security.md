---
title: Databasebeveiliging configureren | Microsoft Docs
description: In dit onderwerp wordt uitgelegd hoe u databasebeveiliging kunt configureren.
services: powerapps
documentationcenter: na
author: maertenm
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/08/2017
ms.author: kfend
ms.openlocfilehash: a8c13158ab2c3f152aa99357684c818f48e637ae
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="configure-database-security"></a>Databasebeveiliging configureren
Common Data Service gebruikt een op rollen gebaseerd beveiligingsmodel om de toegang tot de database te beveiligen. In dit onderwerp wordt uitgelegd hoe u de beveiligingsartefacten maakt die u nodig hebt om een app te beveiligen. De gebruikersrollen bepalen de runtime-toegang tot gegevens en staan los van de omgevingsrollen voor omgevingsbeheerders en omgevingsmakers. Zie [Environments overview](environments-overview.md) (Overzicht van omgevingen) voor een overzicht van omgevingen.

Het is belangrijk dat u begrijpt op welk niveau gebruikers van de app toegang nodig hebben tot deze entiteiten. Common Data Service ondersteunt het maken, lezen, bijwerken en verwijderen van machtigingen voor entiteiten.

* **Maken**: een gebruiker kan nieuwe vermeldingen maken in de entiteit.
* **Lezen**: een gebruiker kan bestaande vermeldingen in de entiteit bekijken en zoeken.
* **Bijwerken**: een gebruiker kan een bestaande vermelding in de entiteit bijwerken of wijzigen.
* **Verwijderen**: een gebruiker kan een bestaande vermelding in de entiteit verwijderen.

De twee machtigingsniveaus die meestal worden gebruikt, zijn alleen-lezentoegang en volledige toegang. Common Data Service omvat machtigingensets op deze twee machtigingsniveaus voor alle entiteiten. De sets met weergavemachtigingen bieden leestoegang tot een entiteit. De sets met onderhoudsmachtigingen bieden volledige toegang tot een entiteit.

Het beveiligingsmodel maakt toewijzing van elke combinatie van machtigingen aan een gebruikersrol mogelijk. Rollen beschikken over de verschillende gecombineerde machtigingen die via machtigingensets aan de rollen zijn toegewezen. Daarom hebben de leden van een rol toegang tot alle gegevens waartoe de machtigingensets die in de rol zijn opgenomen toegang geven. Zie [Beveiligingsmodel](https://docs.microsoft.com/en-us/common-data-service/entity-reference/security-model) voor meer informatie over het beveiligingsmodel van Common Data Service.

## <a name="identify-the-entities"></a>Entiteiten identificeren
U kunt alleen de juiste besturingselementen voor toegang voor een app configureren als u weet welke entiteiten in de app worden gebruikt. Volg deze stappen voor een overzicht van entiteiten die in een app worden gebruikt.

1. Open de app in Microsoft PowerApps Studio.
2. Klik of tik op **Gegevensbronnen** op het tabblad **Inhoud**. In het rechterdeelvenster wordt de lijst met gegevensbronnen weergegeven.

## <a name="configure-security"></a>Beveiliging configureren
Wanneer u een nieuwe entiteit maakt, moet u ook een nieuwe machtigingenset maken of een bestaande machtigingenset bewerken om toegang tot de gegevens van de entiteit in te stellen. Wanneer u een app maakt, is het raadzaam om ook een machtigingenset te maken die toegang biedt tot alle entiteiten die nodig zijn voor het uitvoeren van de app. Beveiliging wordt beheerd in het beheercentrum.

1. Open het [beheercentrum](https://admin.powerapps.com).
2. Klik of tik op de omgeving met de database.
3. Klik of tik op **Beveiliging**. U kunt de beveiliging van uw database configureren op de tabbladen **Machtigingensets** en **Gebruikersrollen**.

## <a name="create-a-permission-set"></a>Een machtigingenset maken
Als u een nieuwe app toegankelijk wilt maken, moet u eerst een nieuwe machtigingenset maken.

1. Klik of tik op **Machtigingensets**.
2. Klik of tik op **Nieuwe machtigingenset** om een machtigingenset te maken.
3. Voer een naam en een beschrijving in voor de machtigingenset en tik of klik op **Maken**. De nieuwe machtigingenset wordt weergegeven in de lijst met machtigingensets.
4. Klik of tik op de machtigingenset die u zojuist hebt gemaakt.
5. Klik of tik op het tabblad **Entiteiten**. Het tabblad **Entiteiten** bevat een lijst met alle entiteiten in de database. Schakel voor elke entiteit die in uw app wordt gebruikt het selectievakje in om de machtiging toe te staan.
6. Klik of tik op **Opslaan**.

## <a name="create-a-policy-technical-preview"></a>Een beleid maken (Technical Preview)
Als u de toegang tot de records in een entiteit wilt toestaan of beperken, moet u eerst een beleid maken.

1. Klik of tik op **Beleid**.
2. Klik of tik op **Nieuw beleid**.
3. Voer een naam en beschrijving voor het beleid in.
4. Selecteer het type beleid dat u wilt maken. Als u een beleid voor selectielijsten wilt maken, geeft u de te gebruiken selectielijst op.
5. Selecteer de operator die moet worden gebruikt.
6. Selecteer de waarde waarmee het beleid moet worden gecontroleerd.
7. Klik of tik op **Maken**.

## <a name="assign-a-policy-technical-preview"></a>Een beleid toewijzen (Technical Preview)
Als u een beleid wilt toepassen, moet u het beleid aan een gegevensentiteit in een machtigingenset toewijzen.

1. Klik of tik op **Machtigingensets**.
2. Klik of tik op de machtigingenset waaraan u beleid wilt toewijzen.
3. Klik of tik op de knop **Bewerken** voor de entiteit waaraan u beleid wilt toewijzen.
4. Vouw de sectie **Beleidstoewijzing** uit.
5. Selecteer de gegevensbewerkingen waarop beleid moet worden toegepast (**Maken**, **Lezen**, **Bijwerken** of **Verwijderen**).
6. Selecteer het entiteitveld waarop het beleid wordt gebaseerd.
7. Selecteer het toe te wijzen beleid.
8. Klik of tik op **Toewijzen**.
9. Klik of tik op **Opslaan**.

## <a name="create-and-assign-a-role"></a>Een rol maken en toewijzen
Nadat de juiste machtigingen zijn opgenomen in een machtigingenset, kunt u een rol maken die kan worden toegewezen aan gebruikers.

1. Klik of tik op **Gebruikersrollen**.
2. Klik of tik op **Nieuwe rol**.
3. Voer een naam en beschrijving voor de rol in en klik of tik op **Maken**. De nieuwe rol wordt weergegeven in de lijst **Gebruikersrollen**.
4. Klik of tik op de rol die u zojuist hebt gemaakt.
5. Klik of tik op het tabblad **Machtigingensets**.
6. Voer de naam in van de machtigingenset die u eerder hebt gemaakt. In de vervolgkeuzelijst die wordt weergegeven terwijl u typt, klikt of tikt u op de machtigingenset om deze aan de rol toe te voegen. Herhaal deze stap voor elke andere machtigingenset die u wilt gebruiken voor de rol.
7. Klik of tik op het tabblad **Gebruikers** voor de rol.
8. Voer de naam of het e-mailadres in van de gebruikers of groepen die u aan de rol wilt toevoegen. In de vervolgkeuzelijst die wordt weergegeven terwijl u typt, klikt of tikt u op de gebruiker. Gebruikers en groepen waaraan de rol wordt toegewezen, worden aan de lijst toegevoegd.
9. Klik of tik op **Opslaan**.

De gebruikers of groepen met deze rol hebben nu toegang tot de gegevens waartoe ze via een van de machtigingensets die aan de rol is gekoppeld toegang hebben. Gebruikers kunnen de gegevens in de database gebruiken als ze beschikken over een beveiligingsrol en toegang hebben tot een PowerApps-app die gebruikmaakt van de gegevens.

## <a name="edit-permission-sets-and-roles"></a>Machtigingensets en rollen bewerken
Als u rollen en machtigingensets wilt bewerken nadat ze zijn gemaakt, klikt u op de knop **Bewerken**.

Gebruik de knop **Verwijderen** om een rol of machtigingenset te verwijderen.

## <a name="out-of-box-security-roles"></a>Ingebouwde beveiligingsrollen
Er zijn twee ingebouwde beveiligingsrollen:

* **Database-eigenaar**: deze rol is bedoeld voor gebruikers met een beheerfunctie. De maker van de omgeving wordt automatisch aan deze rol toegewezen. Gebruikers met deze rol hebben altijd volledige toegang tot alle entiteiten in de database. Ze hebben ook volledige toegang tot nieuwe entiteiten die worden toegevoegd. Gebruikers met deze rol kunnen ook entiteitenschema's in de database maken en bewerken. U hoeft geen machtigingensets toe te voegen aan deze rol. U hoeft geen gebruikers toe te wijzen aan deze rol.
* **Organisatiegebruiker**: dit is de rol die standaard wordt toegewezen aan alle gebruikers. Deze rol is bedoeld om alle gebruikers toegang te geven tot de entiteiten die openbare gegevens bevatten. Als een app wordt gedeeld in de beperkte modus, moeten entiteiten die in de app worden gebruikt in deze rol zijn opgenomen. U hoeft deze rol niet toe te wijzen, omdat deze al aan iedereen in uw organisatie is toegewezen. U hoeft alleen de machtigingensets toe te voegen die u aan de hele organisatie wilt verlenen.

