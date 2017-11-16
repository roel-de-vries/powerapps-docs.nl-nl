---
title: Entiteitgegevens beheren | Microsoft Docs
description: Werken met gegevens in de service en Excel
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
featuredvideoid: n6RizzixvxM
courseduration: 7m
ms.service: powerapps
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: mblythe
ms.openlocfilehash: 807284f05d4233ccf9180f8648f219a4e1eee2b6
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="manage-entity-data"></a>Entiteitgegevens beheren
In dit onderwerp komt het gegevensbeheer in de Common Data Service aan de orde. We hebben het in andere onderwerpen al even gehad over het importeren en exporteren van gegevens, maar we zullen nu dieper ingaan op het werken met gegevens in Excel.

## <a name="import-data-from-excel-or-csv"></a>Gegevens importeren vanuit Excel of CSV
In dit voorbeeld gaan we gegevens vanuit Excel importeren in de entiteit Product review die we in het laatste onderwerp hebben gemaakt. U kunt ook gegevens importeren uit CSV-bestanden, een algemene indeling om gegevens door te sturen. Kijk nog even hoe de entiteit eruitziet; in dit onderwerp gaan we het hebben over het gemarkeerde gebied.

![Entiteit Product review](./media/learning-common-data-service-manage/product-review-entity.png)

Klik of tik in een entiteit op **Gegevens importeren** en ga naar het bestand vanwaaruit u wilt importeren. Klik of tik op **Toewijzing weergeven** en zorg ervoor dat de kolommen in het Excel-bestand gekoppeld zijn aan de juiste velden in de entiteit. Wanneer u tevreden bent met de toewijzingen, klikt of tikt u op **Wijzigingen opslaan**. Klik of tik op **Importeren** in het hoofdscherm voor importeren.

![Gegevens importeren uit Excel](./media/learning-common-data-service-manage/import-data.png)

## <a name="export-data-to-excel"></a>Gegevens exporteren naar Excel
Exporteer gegevens als u die wilt openen buiten de Common Data Service. Klik of tik in een entiteit op **Gegevens exporteren** en wacht totdat het zip-bestand is gegenereerd. Als u het zip-bestand opent, ziet u de geëxporteerde gegevens. 
![Gegevens exporteren naar Excel](./media/learning-common-data-service-manage/export-data.png)

## <a name="export-a-template-to-excel"></a>Een sjabloon exporteren naar Excel
Naast het downloaden van gegevens kunt u een sjabloon downloaden. Een sjabloon is een Excel-bestand met een structuur die overeenkomt met de velden van een entiteit, maar dan zonder de gegevens. Nadat u de sjabloon hebt gedownload, voert u er handmatig of via een programma gegevens in en importeert u de sjabloon weer naar de service. Klik of tik in een entiteit op **Sjabloon exporteren** en geef de gewenste velden op (in dit geval heb ik één veld geselecteerd). Klik of tik op **Exporteren naar Excel** en wacht totdat het Excel-bestand is gegenereerd. Als u het Excel-bestand opent, ziet u de geëxporteerde sjabloon met de velden die u hebt geselecteerd.

![Een sjabloon exporteren naar Excel](./media/learning-common-data-service-manage/export-template.png)

## <a name="open-and-work-with-data-in-excel"></a>Gegevens openen in Excel en ermee werken
Het laatste waarnaar we gaan kijken is de optie **Openen in Excel**. Als u de invoegtoepassing PowerApps hebt geïnstalleerd, kunt u deze optie gebruiken om uw gegevens te verkennen en bewerken in Excel. Klik in een entiteit op **Openen in Excel** en open het bestand. Nadat u bewerken hebt ingeschakeld, brengt de invoegtoepassing een verbinding tot stand met de entiteit in de service en wordt de werkmap ingevuld. U maakt bewerkingen rechtstreeks in de werkmap en u kunt rijen toevoegen en verwijderen. Klik of tik op **Publiceren** om wijzigingen op te slaan. U kunt ook gegevens vernieuwen om ervoor te zorgen dat u een actuele kopie hebt. Bovendien kunt u gegevens filteren, wat met name handig is als een entiteit veel gegevens bevat.

![Openen in Excel](./media/learning-common-data-service-manage/open-excel.png)

Hiermee wordt het onderwerp afgerond over het beheren van gegevens in de Common Data Service: importeren van, exporteren van en werken met gegevens in Excel. In het volgende onderwerp komt het beheren van gegevensbeveiliging aan de orde.

