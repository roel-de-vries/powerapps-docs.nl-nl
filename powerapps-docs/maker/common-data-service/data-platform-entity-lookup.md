---
title: Een relatie tussen entiteiten maken met behulp van een opzoekveld | Microsoft Docs
description: Stapsgewijze instructies voor het maken van een relatie tussen entiteiten in PowerApps door een opzoekveld te gebruiken.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-relationship-between-entities"></a>Een relatie tussen twee entiteiten maken
Gegevens in één entiteit zijn vaak gerelateerd aan gegevens in een andere entiteit. U kunt bijvoorbeeld de entiteit **Leraren** en de entiteit **Klas** hebben. De entiteit **Klas** kan een opzoekrelatie hebben met de entiteit **Leraren** om aan te geven welke leraar lesgeeft aan de klas. U kunt een opzoekveld gebruiken om gegevens van de entiteit **Leraren** weer te geven. Hiernaar wordt algemeen verwezen als een opzoekveld.

## <a name="define-a-relationship"></a>Een relatie definiëren
U kunt verschillende typen relaties tussen entiteiten (of tussen een entiteit en de entiteit zelf) maken. Elke entiteit kan een relatie met meer dan één entiteit hebben, en elk entiteit kan meerdere relaties met een andere entiteit hebben. Sommige vaak voorkomende relatietypen zijn:

* **Veel-op-veel** - in dit type relatie kan elke record in entiteit A met meer dan één record in entiteit B overeenkomen, maar elk record in entiteit B kan slechts met één record in entiteit A overeenkomen. Een klas heeft bijvoorbeeld één klaslokaal. Dit is het meest gebruikte relatietype en wordt in de lijst met velden weergegeven als een **Opzoekveld**
* **Eén-op-veel** - in dit type relatie kan elke record in entiteit B met meer dan één record in entiteit A overeenkomen, maar elk record in entiteit A kan slechts met één record in entiteit B overeenkomen. Eén leraar geeft bijvoorbeeld les aan meerdere klassen.
* **Veel-op-veel** - in dit type relatie kan elke record in entiteit A met meer dan één record in entiteit B overeenkomen, en omgekeerd. Leerlingen hebben bijvoorbeeld les in vele klassen en elke klas kan meerdere leerlingen hebben.

## <a name="add-a-lookup-field-many-to-one-relationship"></a>Een opzoekveld (veel-op-veel-relatie) toevoegen

Als u een opzoekrelatie aan een entiteit wilt toevoegen, maakt u een relatie onder het tabblad **Relaties** en geeft u de entiteit op waarmee u een relatie wilt maken.

1. Vouw in [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsdetails](./media/data-platform-cds-create-entity/entitylist.png "Entiteitenlijst")

2. Klik of tik op een bestaande entiteit of kies ervoor [Een nieuwe entiteit te maken](data-platform-create-entity.md)

3. Klik op **Relaties**.

4. Klik op **Relatie toevoegen**. Hiermee wordt een nieuw paneel voor u geopend waarin u de entiteit kunt kiezen waarmee u een relatie wilt maken. Selecteer de entiteit in de vervolgkeuzelijst **Gerelateerde entiteit**.

    > [!div class="mx-imgBorder"] 
    > ![Veel-op-één-relatie](./media/data-platform-cds-newrelationship/manytoone-1.png "Veel-op-één-relatie")

5. Na het selecteren van een entiteit worden de opzoekvelden in de primaire entiteit weergegeven en wordt standaard de entiteitsnaam overgenomen (in dit voorbeeld Klaslokaal), maar u kunt deze desgewenst wijzigen.

    ![Veel-op-één-relatie](./media/data-platform-cds-newrelationship/manytoone-2.png "Veel-op-één-relatie")

6. Klik op **Gereed** om de relatie aan uw entiteit toe te voegen en klik vervolgens op **Entiteit opslaan**.

    > [!div class="mx-imgBorder"] 
    > ![Veel-op-één-relatie](./media/data-platform-cds-newrelationship/manytoone-3.png "Veel-op-één-relatie")

## <a name="add-a-one-to-many-relationship"></a>Een één-op-veel-relatie toevoegen

Als u een één-op-veel-relatie wilt toevoegen, maakt u een relatie onder het tabblad **Relaties** en geeft u de entiteit op waarmee u een relatie wilt maken.

1. Vouw in [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsdetails](./media/data-platform-cds-create-entity/entitylist.png "Entiteitenlijst")

2. Klik of tik op een bestaande entiteit of kies ervoor [Een nieuwe entiteit te maken](data-platform-create-entity.md)

3. Klik op **Relaties**.

4. Klik op de pijl-omlaag rechts van **Relatie toevoegen**. U kunt dan kiezen uit beide typen relaties. Klik op **Eén-op-veel**. Hiermee wordt een nieuw paneel voor u geopend waarin u de entiteit kunt kiezen waarmee u een relatie wilt maken. Selecteer de entiteit in de vervolgkeuzelijst **Gerelateerde entiteit**.

    ![Eén-op-veel-relatie](./media/data-platform-cds-newrelationship/onetomany-1.png "Eén-op-veel-relatie")

5. Na het selecteren van een entiteit worden de opzoekvelden in de primaire entiteit weergegeven en wordt standaard de entiteitsnaam overgenomen (in dit voorbeeld Klas), maar u kunt deze desgewenst wijzigen.

    > [!NOTE]
    > In het geval van één-op-veel-relaties wordt het opzoekveld in de gerelateerde entiteit gemaakt, niet de entiteit die u momenteel hebt geselecteerd. Als u het opzoekveld in de huidige entiteit nodig hebt, maakt u een veel-op-één-relatie.

    > [!div class="mx-imgBorder"] 
    > ![Eén-op-veel-relatie](./media/data-platform-cds-newrelationship/onetomany-2.png "Eén-op-veel-relatie")

6. Klik op **Gereed** om de relatie aan uw entiteit toe te voegen en klik vervolgens op **Entiteit opslaan**.

    > [!div class="mx-imgBorder"] 
    > ![Eén-op-veel-relatie](./media/data-platform-cds-newrelationship/onetomany-3.png "Eén-op-veel-relatie")

## <a name="add-a-many-to-many-relationship"></a>Een veel-op-veel-relatie toevoegen

Momenteel is dit uitsluitend beschikbaar via het menu Geavanceerd. Klik via de PowerApps-startpagina op "Geavanceerd" in het linkermenu. Zie voor informatie over het maken van de relatie [N:N-relaties maken](/dynamics365/customer-engagement/customize/create-and-edit-nn-many-to-many-relationships)

## <a name="use-a-lookup-field-in-an-app"></a>Een opzoekveld in een app gebruiken
Als u [een app automatisch maakt](../canvas-apps/data-platform-create-app.md) vanuit een entiteit die een opzoekveld bevat, wordt deze weergegeven als een **Vervolgkeuzelijst**-besturingselement dat gegevens bevat van het veld **Primaire naam** van de entiteit.

## <a name="next-steps"></a>Volgende stappen
* [Een app genereren met behulp van een Common Data Service-database](../canvas-apps/data-platform-create-app.md)
* [Een compleet nieuwe app maken met behulp van een Common Data Service-database](../canvas-apps/data-platform-create-app-scratch.md)

