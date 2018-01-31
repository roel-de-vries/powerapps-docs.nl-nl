---
title: Entiteitsrelaties via opzoekveld | Microsoft Docs
description: "Creëer een relatie tussen entiteiten met behulp van een opzoekveld."
services: powerapps
documentationcenter: na
author: kfend
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/09/2016
ms.author: kfend
ms.openlocfilehash: 21f33f8810b545b11f611b86261227c9443be5de
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="build-a-relationship-between-entities"></a>Relatie tussen entiteiten maken
Gegevens in de ene entiteit zijn vaak gekoppeld aan gegevens in een andere entiteit. Als u bijvoorbeeld een entiteit **Klanten** en een entiteit **Orders** hebt, kan de entiteit **Orders** een opzoekrelatie met de entiteit **Klanten** hebben om te laten zien welke klant de bestelling heeft geplaatst. U kunt een opzoekveld gebruiken om gegevens uit de entiteit **Klanten** weer te geven voor de klant die de bestelling heeft geplaatst. Zie het Engelstalige artikel [Entity relationships and lookup fields](https://docs.microsoft.com/en-us/common-data-service/entity-reference/relationships) (Entiteitsrelaties en opzoekvelden) voor meer informatie.

## <a name="define-a-relationship"></a>Een relatie definiëren
U kunt verschillende typen relaties vanuit de ene entiteit naar de andere (of tussen een entiteit en zichzelf) creëren. Elke entiteit kan een relatie met meer dan één entiteit hebben en elke entiteit kan meer dan één relatie met een andere entiteit hebben. Dit zijn enkele algemene relatietypen:

* **Normaal**: dit type relatie bestaat tussen twee entiteiten.
* **Zelf**: dit type relatie bestaat tussen een entiteit en zichzelf.
* **Een-op-een**: in dit type relatie kan elke record in entiteit A overeenkomen met slechts één record in entiteit B, en vice versa. De huidige versie van Common Data Service ondersteunt dit type relatie niet voor aangepaste entiteiten.
* **Een-op-veel**: In dit type relatie kan elke record in entiteit A overeenkomen met meer dan één record in entiteit B, maar elke record in entiteit B kan overeenkomen met slechts één record in entiteit A.
* **Veel-op-veel**: in dit type relatie kan elke record in entiteit A overeenkomen met meer dan één record in entiteit B, en vice versa. De huidige versie van Common Data Service biedt geen ondersteuning voor dit type relatie.

## <a name="add-a-lookup-relation"></a>Een opzoekrelatie toevoegen
Als u een opzoekrelatie wilt toevoegen aan een entiteit, maakt u een relatie op het tabblad **Relaties** tabblad en geeft u de entiteit op waarmee u een relatie wilt maken.

1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Common Data Service** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.
2. Klik of tik in de lijst met entiteiten op een entiteit om de velden ervan weer te geven. U kunt de lijst filteren door een of meer tekens in het zoekvak boven de lijst te typen.
3. Klik of tik boven in het scherm op **Relaties**. Op dit tabblad ziet u alle relaties voor de entiteit. Klik op **Nieuwe relatie**.
4. Geef op de pagina **Relatie maken** de gerelateerde entiteit op waarmee u een relatie wilt maken, en geef vervolgens de naam en de weergavenaam van de relatie op.
5. Klik of tik op **Save** om de wijzigingen doorvoeren. Er wordt automatisch een zoekveld met dezelfde naam gemaakt.

## <a name="use-a-lookup-field-in-an-app"></a>Een opzoekveld in een app gebruiken
Als u [automatisch een app maakt](data-platform-create-app.md) op basis van een entiteit die een opzoekveld bevat, wordt dit veld weergegeven als een samengevouwen **vervolgkeuzelijst** met gegevens uit het **primaire sleutel**veld van de entiteit waarnaar wordt verwezen. Als u twee velden wilt zien in de vervolgkeuzelijst wanneer deze wordt uitgevouwen, moet u de velden PrimaryId en een tweede veld van uw keuze toevoegen aan de **Standaardopzoek**veldgroep van de gerelateerde entiteit van de opzoekrelatie.

## <a name="delete-a-record-with-a-lookup-relation"></a>Een record met een opzoekrelatie verwijderen
Als entiteit A een opzoekveld naar entiteit B heeft:

* U kunt elke record in entiteit A zonder enige beperking verwijderen.
* Als een record in entiteit B overeenkomt met een of meer records in entiteit A, moet u alle overeenkomende records in entiteit A verwijderen voordat u de record in entiteit B kunt verwijderen.

> [!NOTE]
> Als entiteit B een standaardentiteit is met een bovenliggende relatie met entiteit A en u een record verwijdert uit entiteit A, worden ook alle overeenkomende records uit entiteit B verwijderd.

Zie [Velden beheren](data-platform-manage-fields.md) voor informatie over het verwijderen van een veld.

## <a name="next-steps"></a>Volgende stappen
* [Generate an app by using a Common Data Service database (Een app genereren met behulp van een Common Data Service-database)](data-platform-create-app.md)
* [Create an app from scratch using a Common Data Service database (Een volledig nieuwe app maken met behulp van een Common Data Service-database)](data-platform-create-app-scratch.md)

