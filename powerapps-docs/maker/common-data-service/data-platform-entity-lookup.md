---
title: Een relatie tussen entiteiten maken met behulp van een opzoekveld | Microsoft Docs
description: Stapsgewijze instructies voor het maken van een relatie tussen entiteiten in PowerApps met behulp van een opzoekveld.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: f1952c2349eb54f2c6348f5abc4dee9a4645348a
ms.sourcegitcommit: b3b6118790d6b7b4285dbcb5736e55f6e450125c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2018
---
# <a name="create-a-relationship-between-entities"></a>Een relatie tussen entiteiten maken
Gegevens in de ene entiteit zijn vaak gekoppeld aan gegevens in een andere entiteit. Als u bijvoorbeeld een entiteit **Docenten** en een entiteit **Klas** hebt, kan de entiteit **Klas** een opzoekrelatie met de entiteit **Docenten** hebben om te laten zien welke docent de klas lesgeeft. U kunt via een opzoekveld gegevens weergeven van de entiteit **Docenten**. Dit wordt vaak aangeduid als een opzoekveld.

## <a name="define-a-relationship"></a>Een relatie definiëren
U kunt verschillende typen relaties vanuit de ene entiteit naar de andere (of tussen een entiteit en zichzelf) creëren. Elke entiteit kan een relatie met meer dan één entiteit hebben en elke entiteit kan meer dan één relatie met een andere entiteit hebben. Dit zijn enkele algemene relatietypen:

* **Veel-op-één**: In dit type relatie kan elke record in entiteit A overeenkomen met meer dan één record in entiteit B, maar elke record in entiteit B kan overeenkomen met slechts één record in entiteit A. Een klas heeft bijvoorbeeld één klaslokaal. Dit is het meest voorkomende type relatie en wordt weergegeven in de lijst met velden als een **Zoekveld**
* **Eén-op-veel**: In dit type relatie kan elke record in entiteit B overeenkomen met meer dan één record in entiteit A, maar elke record in entiteit A kan overeenkomen met slechts één record in entiteit B. Eén docent geeft bijvoorbeeld les aan meerdere klassen.
* **Veel-op-veel**: in dit type relatie kan elke record in entiteit A overeenkomen met meer dan één record in entiteit B, en vice versa. Leerlingen wonen bijvoorbeeld veel lessen bij en bij elke les kunnen meerdere leerlingen aanwezig zijn.

## <a name="add-a-lookup-field-many-to-one-relationship"></a>Voeg een opzoekveld (veel-op-een-relatie)

Als u een opzoekrelatie wilt toevoegen aan een entiteit, maakt u een relatie op het tabblad **Relaties** tabblad en geeft u de entiteit op waarmee u een relatie wilt maken.

1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsgegevens](./media/data-platform-cds-create-entity/entitylist.png "Entiteitslijst")

2. Klik of tik op een bestaande entiteit of [Een nieuwe entiteit maken](data-platform-create-entity.md)

3. Klik op **Relaties**

4. Klik op **Relatie toevoegen**. Hiermee opent u een nieuw deelvenster waarin u de entiteit kiest waarmee u een relatie wilt maken. Selecteer de entiteit in de vervolgkeuzelijst **Gerelateerde entiteit**.

    ![Veel-op-één-relatie](./media/data-platform-cds-newrelationship/manytoone-1.png "Veel-op-één-relatie")

5. Na het selecteren van een entiteit worden de opzoekvelden weergegeven op de primaire entiteit en standaard voorzien van de naam van de entiteit (in dit voorbeeld Leslokaal), maar kunt u deze, indien nodig, wijzigen.

    ![Veel-op-één-relatie](./media/data-platform-cds-newrelationship/manytoone-2.png "Veel-op-één-relatie")

6. Klik op **Gereed** om de relatie toe te voegen aan uw entiteit en klik vervolgens op **Entiteit opslaan**.

    ![Veel-op-één-relatie](./media/data-platform-cds-newrelationship/manytoone-3.png "Veel-op-één-relatie")

## <a name="add-a-one-to-many-relationship"></a>Een één-op-veel-relatie toevoegen

Als u een één-op-veel-relatie wilt toevoegen, maakt u een relatie onder het tabblad **Relaties** en geeft u de entiteit op waarmee u een relatie wilt maken.

1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsgegevens](./media/data-platform-cds-create-entity/entitylist.png "Entiteitslijst")

2. Klik of tik op een bestaande entiteit of [Een nieuwe entiteit maken](data-platform-create-entity.md)

3. Klik op **Relaties**

4. Klik op de pijl omlaag rechts van **Relatie toevoegen**. Hierdoor krijgt u de keuze uit beide typen relaties. Klik op **Eén-op-veel**. Hiermee opent u een nieuw deelvenster waarin u de entiteit kiest waarmee u een relatie wilt maken. Selecteer de entiteit in de vervolgkeuzelijst **Gerelateerde entiteit**.

    ![Eén op-veel-relatie](./media/data-platform-cds-newrelationship/onetomany-1.png "Eén op-veel-relatie")

5. Na het selecteren van een entiteit worden de opzoekvelden weergegeven op de primaire entiteit en standaard voorzien van de naam van de entiteit (in dit voorbeeld Klas), maar kunt u deze, indien nodig, wijzigen.

    > [!NOTE]
    > In het geval van één-op-veel-relaties, wordt het opzoekveld gemaakt over de gerelateerde entiteit, niet de entiteit die u momenteel hebt geselecteerd. Als u de zoekopdracht nodig hebt voor de huidige entiteit, maakt u een veel-op-een-relatie.

    ![Eén op-veel-relatie](./media/data-platform-cds-newrelationship/onetomany-2.png "Eén op-veel-relatie")

6. Klik op **Gereed** om de relatie toe te voegen aan uw entiteit en klik vervolgens op **Entiteit opslaan**.

    ![Eén op-veel-relatie](./media/data-platform-cds-newrelationship/onetomany-3.png "Eén op-veel-relatie")

## <a name="add-a-many-to-many-relationship"></a>Een veel-op-veel-relatie toevoegen

Dit is momenteel alleen beschikbaar via het menu Geavanceerd. Klik op Geavanceerd in het linkermenu van op de PowerApps-startpagina. Zie [N:N-relaties maken](/dynamics365/customer-engagement/customize/create-and-edit-nn-many-to-many-relationships) voor meer informatie over het maken van de relatie

## <a name="use-a-lookup-field-in-an-app"></a>Een opzoekveld in een app gebruiken
Als u [automatisch een app maakt](../canvas-apps/data-platform-create-app.md) op basis van een entiteit die een opzoekveld bevat, wordt dit veld weergegeven als een samengevouwen **vervolgkeuzelijst** met gegevens uit het veld **Primaire naam** van de entiteit.

## <a name="next-steps"></a>Volgende stappen
* [Generate an app by using a Common Data Service database (Een app genereren met behulp van een Common Data Service-database)](../canvas-apps/data-platform-create-app.md)
* [Create an app from scratch using a Common Data Service database (Een volledig nieuwe app maken met behulp van een Common Data Service-database)](../canvas-apps/data-platform-create-app-scratch.md)

