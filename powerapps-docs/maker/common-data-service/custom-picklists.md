---
title: Een optieset maken | Microsoft Docs
description: Stapsgewijze instructies voor het maken van een optieset.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: 188add46a8e52cfeb75ef1bb670ca3b457963024
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34168591"
---
# <a name="create-an-option-set"></a>Een optieset maken

Met optiesets kunt u vervolgkeuzelijsten van vaste waarden voor een gebruiker in uw app opnemen voor gegevensconsistentie. Deze worden in andere toepassingen soms aangeduid als selectielijsten of keuzevelden. Net als bij entiteiten zijn er behalve standaard optiesets ook mogelijkheden om aangepaste optiesets te maken die u kunt gebruiken in uw app.

Optiesets kunnen op twee manieren worden gemaakt: vanuit de lijst met optiesets in de portal of rechtstreeks in een entiteit tijdens het maken van een veld. Zie voor meer informatie over het maken van een entiteit [Een entiteit maken](data-platform-create-entity.md).

## <a name="creating-an-option-set-while-adding-a-field"></a>Een optieset maken tijdens het toevoegen van een veld.

1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsgegevens](./media/data-platform-cds-create-entity/entitylist.png "Entiteitslijst")

2. Klik of tik op een bestaande entiteit of [Een nieuwe entiteit maken](data-platform-create-entity.md)

3. Voeg een nieuw veld toe aan uw entiteit door te klikken op **Veld toevoegen**.

4. Voer in het deelvenster Nieuw veld de **Weergavenaam** voor het veld in. De **Naam** worden automatisch ingevuld en wordt gebruikt als unieke naam voor het veld. De **Weergavenaam** wordt gebruikt wanneer dit veld aan uw gebruikers wordt gepresenteerd. De **Naam** wordt gebruikt bij het bouwen van uw app, in expressies en formules.

    ![Nieuw veld](./media/data-platform-cds-create-entity/newfieldpanel.png "deelvenster Nieuw veld")

5. Klik op de vervolgkeuzelijst **Gegevenstype** en selecteer **Optieset** of **Optieset voor meervoudige selectie**.

6. Klik op de vervolgkeuzelijst **Optieset** en selecteer **Nieuwe optieset**

    > [!NOTE]
    > Als een bestaande optieset kan worden gebruikt voor uw entiteit, kunt u deze in deze lijst selecteren zonder dat u een nieuwe maakt.

    ![Lijst met optiesets](./media/data-platform-cds-newoptionset/fieldpanel-1.png "Lijst met optiesets")

7. Er wordt een nieuw deelvenster geopend voor het maken van de optieset, de **Weergavenaam** en **Naam** krijgen standaard een naam die is gebaseerd op het veld, maar deze kunnen naar wens worden gewijzigd. Klik op **Nieuw item toevoegen** om te beginnen met het maken van uw lijst met opties. Herhaal deze stap tot alle items zijn gemaakt.

    ![Nieuwe optieset](./media/data-platform-cds-newoptionset/field-optionsetpanel.png "Nieuwe optieset")

8. Wanneer u uw items hebt ingevoerd, klikt u op **Opslaan** om de optieset te maken.

    ![Nieuwe optieset](./media/data-platform-cds-newoptionset/field-optionsetpanel-values.png "Nieuwe optie is ingesteld")

9. Klik op **Gereed** om het deelvenster Veld te sluiten en klik vervolgens op **Entiteit opslaan** om uw entiteit in Common Data Service op te slaan.

    > [!NOTE]
    > U kunt een van uw items als **standaard** selecteren voor dit veld, zodat het standaard wordt geselecteerd wanneer gebruikers in uw entiteit nieuwe records maken.

    ![Nieuw veld](./media/data-platform-cds-newoptionset/fieldpanel-2.png "Deelvenster Nieuw veld")

## <a name="creating-an-option-set-from-the-option-set-list"></a>Een optieset maken vanuit de lijst met optiesets

1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Gegevens** uit en klik of tik op **Optiesets** in het linkernavigatiedeelvenster.

    ![Optiesets](./media/data-platform-cds-newoptionset/optionsetlist.png "Lijst met optiesets")

2. Klik op **Nieuwe optieset**

3. Er wordt een nieuw deelvenster geopend om de optieset te maken. Voer de **Weergavenaam** en **Naam** in. Klik op **Nieuw item toevoegen** om te beginnen met het maken van uw lijst met opties. Herhaal deze stap totdat alle items zijn gemaakt.

    ![Een optieset maken](./media/data-platform-cds-newoptionset/optionset-create.png "Een optieset maken")

4. Wanneer u uw items hebt ingevoerd, klikt u op **Opslaan** om de optieset te maken.

    ![Nieuwe optieset](./media/data-platform-cds-newoptionset/optionset-create-values.png "Nieuwe optieset")

5. U kunt nu deze optieset gebruiken door een nieuw veld te maken voor een entiteit.

## <a name="global-and-local-option-sets"></a>Globale en lokale optiesets

Standaard worden optiesets gemaakt als globale optiesets, waardoor ze kunnen worden hergebruikt voor meerdere entiteiten. Onder de optie **Meer weergeven** kunt u er bij het maken van een nieuwe optieset voor kiezen om een optieset **Lokaal** te maken. Deze optie is alleen beschikbaar wanneer u een optieset maakt tijdens het toevoegen van een veld en niet via de lijst met optiesets. Lokale optiesets kunnen alleen worden gebruikt door de entiteit en het veld waarvoor deze zijn gemaakt, en kunnen niet worden hergebruikt voor andere entiteiten. Deze aanpak wordt alleen aanbevolen voor gevorderde gebruikers die specifiek een lokale optieset nodig hebben.

> [!IMPORTANT]
> Zodra een optieset als lokaal of globaal is gemaakt, kan dit niet worden gewijzigd.