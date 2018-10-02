---
title: Een aangepaste entiteit verwijderen | Microsoft Docs
description: Stapsgewijze instructies voor het verwijderen van een aangepaste entiteit en het wissen van alle gegevens in PowerApps
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

# <a name="delete-a-custom-entity"></a>Een aangepaste entiteit verwijderen
U kunt aangepaste entiteiten verwijderen, maar u kunt geen standaardentiteiten verwijderen.

1. Vouw in [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsdetails](./media/data-platform-cds-create-entity/entitylist.png "Entiteitenlijst")

2. In de lijst met entiteiten klikt of tikt u op de te verwijderen entiteit en vervolgens klikt of tikt u op de optie **Entiteit verwijderen** via de opdrachtbalk.

3. In het dialoogvenster dat wordt geopend klikt of tikt u op **Verwijderen** om de entiteit te verwijderen.

>[!NOTE]
>Als u een entiteit verwijdert, worden zowel de entiteitdefinitie als alle gegevens die de entiteit bevat verwijderd. Entiteiten en de gegevens in de entiteiten kunnen niet worden hersteld als deze worden verwijderd.

>[!NOTE]
>U kunt een app of stroom afbreken als u een entiteit verwijdert die in die app wordt gebruikt.

>[!NOTE]
>Als entiteit A [opzoekvelden](data-platform-entity-lookup.md) heeft voor entiteit B, moet u mogelijk eerst entiteit B verwijderen voordat u entiteit A kunt verwijderen.

