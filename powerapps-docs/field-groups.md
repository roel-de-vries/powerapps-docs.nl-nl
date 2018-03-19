---
title: Veldgroepen gebruiken om een app te maken | Microsoft Docs
description: Gebruik veldgroepen om het maken van apps te standaardiseren in databases.
services: powerapps
documentationcenter: na
author: aneesmsft
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/11/2017
ms.author: aneesa
ms.openlocfilehash: d791d04965873c133be85013feb181dc5a1e1bad
ms.sourcegitcommit: 397a968f57ce5aaaf2b86e804dfedda8cf34f307
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2018
---
# <a name="use-field-groups"></a>Veldgroepen gebruiken
Veldgroepen bieden een manier om een of meer velden van een entiteit te groeperen. Met veldgroepen wordt het maken en onderhouden van apps sneller en eenvoudiger. Een veldgroep bevat een of meer velden, en een veld kan in een willekeurig aantal veldgroepen worden weergegeven. Een veld kan niet meer dan één keer voorkomen in een veldgroep.

Veldgroepen zijn opgeslagen op een entiteit en worden gedeeld met alle apps die dezelfde entiteit gebruiken. Op elk willekeurig moment kan het zijn dat veel verschillende apps gebruikmaken van dezelfde entiteit en veldgroepen van deze entiteit. Deze centralisatie en het delen van veldgroepen helpt bij het afdwingen van consistentie, omdat in een veldgroep altijd dezelfde velden worden weergegeven, waar deze ook wordt gebruikt. Dit maakt onderhoud gemakkelijk, omdat een wijziging in een veldgroep automatisch wordt weerspiegeld op alle plekken waar deze veldgroep wordt gebruikt. Het maken en aanpassen van apps verloopt sneller met behulp van veldgroepen, omdat de auteur van een toepassing met groepen velden werkt in plaats van met afzonderlijke velden.

## <a name="default-field-groups"></a>Standaardveldgroep
Common Data Service omvat verschillende standaardveldgroepen op entiteiten. Deze veldgroepen worden op verschillende locaties gebruikt om het maken en aanpassen van apps sneller en eenvoudiger te laten verlopen.

| Standaardnaam van veldgroep | Beschrijving |
| --- | --- |
| DefaultList |Wordt gebruikt om een lijst met records in een tabelindeling weer te geven. |
| DefaultCard |Wordt gebruikt om een lijst met records in een kaartindeling weer te geven. |
| DefaultDetails |Wordt gebruikt om de details van een enkele record in Weergeven en bewerken weer te geven. |
| DefaultLookup |Wordt gebruikt om een zoekopdracht om een record te selecteren weer te geven. |

## <a name="view-a-field-group"></a>Een veldgroep weergeven
1. Meld u aan bij [powerapps.com](https://web.powerapps.com).
2. Als u toegang hebt tot meer dan één omgeving, controleert u of u de juiste omgeving hebt geselecteerd met behulp van de omgevingskiezer in de bovenste balk.
3. Vouw de sectie **Common Data Service** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.
4. Klik of tik in de lijst met entiteiten op de entiteit waarvan u de veldgroep wilt bekijken.
5. Klik of tik in de koptekst boven de lijst met velden op **Veldgroepen**. U ziet nu alle veldgroepen die momenteel bestaan voor de entiteit.
6. Klik of tik in de lijst met veldgroepen op de veldgroepen waarvan u de details wilt bekijken.
7. In de details van de veldgroep ziet u twee lijsten naast elkaar. De ene lijst heet **Entiteitsvelden**. Hierin worden alle velden voor de entiteit vermeld. De andere lijst heet **Velden van de veldgroep**. Hierin worden de velden van de veldgroep vermeld.

## <a name="modify-a-field-group"></a>Een veldgroep wijzigen
1. Geeft de veldgroep weer die u wilt wijzigen.
2. Dubbelklik op een veldnaam in de lijst **Entiteitsvelden** om een veld toe te voegen. U kunt velden ook uit de lijst **Entiteitsvelden** slepen en neerzetten in de lijst **Velden van de veldgroep**.
3. Klik in de lijst  **Velden van de veldgroep** op de **X** naast een veldnaam om een veldgroep te verwijderen.
4. Klik of tik op de knop **Opslaan**.

> [!NOTE]
> Het wijzigen van veldgroepen voor [standaardentiteiten](guided-learning/manage-data.yml#step-2) wordt momenteel niet ondersteund, maar u kunt veldgroepen wijzigen voor aangepaste entiteiten.*

## <a name="creating-a-field-group"></a>Een veldgroep maken
Standaardveldgroepen worden automatisch gemaakt als u een entiteit maakt. Het maken van extra veldgroepen wordt momenteel niet ondersteund.

## <a name="delete-a-field-group"></a>Een veldgroep verwijderen
Het verwijderen van een veldgroep wordt momenteel niet ondersteund.

## <a name="view-and-edit-field-group-data-in-microsoft-excel"></a>Gegevens van veldgroepen weergeven en bewerken in Microsoft Excel
1. Geef de veldgroepen weer voor de entiteit waarvan u de gegevens wilt controleren.
2. Naast elke veldgroep ziet u een Excel-pictogram. Het Excel-pictogram is alleen ingeschakeld als de veldgroep daadwerkelijk velden bevat.
3. Klik op het Excel-pictogram voor de veldgroep die u wilt openen in Excel. Er wordt een werkmap gegenereerd die een lijst met entiteitsvelden, de Excel-invoegtoepassing en een verwijzing naar uw omgeving bevat.
4. Open de gegenereerde werkmap die wordt geleverd met behulp van de browser.
5. Nadat de werkmap is geopend, schakelt u bewerken in. De gegevens worden vervolgens met de Excel-invoegtoepassing in de werkmap gelezen. Zie [Entiteitsgegevens openen in Excel](data-platform-interactive-excel.md) voor meer informatie.

## <a name="field-group-usage"></a>Veldgroepen gebruiken
Met de standaardveldgroepen verloopt het maken en aanpassen van toepassingen sneller. Een aantal locaties waar u momenteel actieve veldgroepen kunt bekijken:

* **Besturingselement Formulier voor entiteit**: het besturingselement Formulier voor entiteit maakt gebruik van de standaardveldgroepen om dynamische formulieren weer te geven waarmee u sneller apps kunt maken en consistentie kunt afdwingen, en waarmee onderhoud eenvoudiger verloopt. Zie [Het besturingselement Formulier voor entiteit gebruiken](entity-form-control.md) voor meer informatie.
* **Besturingselement voor zoeken**: als een van de velden die u toevoegt op het scherm, verwijst naar een andere gekoppelde entiteit, wordt het veld weergegeven als een besturingselement voor zoeken (selectielijst). Wanneer een gebruiker op het opzoekbesturingselement klikt om een record te selecteren uit de gekoppelde entiteit, wordt met behulp van de groep **DefaultLookup** in de gekoppelde entiteit bepaald welke velden worden weergegeven. Alleen de eerste twee velden van de veldgroep **DefaultLookup** worden gebruikt.
* **Een app maken**: wanneer u een app genereert met behulp van de optie voor het maken van apps uit gegevens, worden automatisch de schermen gemaakt van de entiteiten die u selecteert. Het besturingselement **Formulier weergeven** op het scherm **Weergeven** en het besturingselement **Formulier bewerken** op het scherm **Bewerken** maken gebruik van de groep velden **DefaultDetails** om te bepalen welke velden standaard worden toegevoegd aan deze schermen.

