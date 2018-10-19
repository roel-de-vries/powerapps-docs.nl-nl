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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-an-option-set"></a>Een optieset maken

Met optiesets kunt u vervolgkeuzelijstlijsten met waarden voor een gebruiker opnemen in uw app om gegevensconsistentie te waarborgen. Hiernaar wordt ook wel verwezen als selectielijsten of keuzevelden in andere toepassingen. Vergelijkbaar met entiteiten zijn er standaardoptiesets en hebt u de mogelijkheid om aangepaste optiesets te maken die u in uw app kunt gebruiken.

Optiesets kunnen op twee manieren worden gemaakt: via de lijst met optiesets in de portal ofwel rechtstreeks in een entiteit tijdens het maken van een veld. Zie voor meer informatie over het maken van een entiteit [Een entiteit maken](data-platform-create-entity.md).

## <a name="creating-an-option-set-while-adding-a-field"></a>Een optieset maken tijdens het toevoegen van een veld.

1. Vouw in [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster.

    ![Entiteitsdetails](./media/data-platform-cds-create-entity/entitylist.png "Entiteitenlijst")

2. Klik of tik op een bestaande entiteit of kies ervoor [Een nieuwe entiteit te maken](data-platform-create-entity.md)

3. Voeg een nieuw veld aan uw entiteit toe door op **Veld toevoegen** te klikken.

4. Voer in het nieuwe veldpaneel de **Weergavenaam** voor uw veld in. De **Naam** wordt automatisch ingevuld en wordt gebruikt als de unieke naam voor uw veld. De **Weergavenaam** wordt gebruikt wanneer dit veld aan uw gebruikers wordt gepresenteerd. De **Naam** wordt gebruikt bij het bouwen van uw app, in expressies en formules.

    > [!div class="mx-imgBorder"] 
    > ![Nieuw veld](./media/data-platform-cds-create-entity/newfieldpanel.png "Paneel Nieuw veld")

5. Klik op de vervolgkeuzelijst **Gegevenstype** en selecteer **Optieset** of **Optieset voor meervoudige selectie**.

6. Klik op de vervolgkeuzelijst **Optieset** en selecteer **Nieuwe optieset**

    > [!NOTE]
    > Als een bestaande optieset voor uw entiteit kan worden gebruikt, kunt u deze in de lijst selecteren zonder een nieuwe te maken.

    ![Optiesetlijst](./media/data-platform-cds-newoptionset/fieldpanel-1.png "Optiesetlijst")

7. Een nieuw paneel wordt geopend waarin u de optieset kunt maken. **Weergavenaam** en **Naam** worden standaard overgenomen van de naam van het veld, maar kan zo nodig worden gewijzigd. Klik op **Nieuw item toevoegen** om met het maken van uw lijst met opties te starten. Herhaal deze stap totdat al uw items zijn gemaakt.

    > [!div class="mx-imgBorder"] 
    > ![Nieuwe optieset](./media/data-platform-cds-newoptionset/field-optionsetpanel.png "Nieuwe optieset")

8. Zodra u uw items hebt ingevoerd, klikt u op **Opslaan** om uw optieset te maken.

    > [!div class="mx-imgBorder"] 
    > ![Nieuwe optieset](./media/data-platform-cds-newoptionset/field-optionsetpanel-values.png "Nieuwe optieset")

9. Klik op **Gereed** om het veldpaneel wilt sluiten en vervolgens op **Entiteit opslaan** om uw entiteit op te slaan voor de Common Data Service.

    > [!NOTE]
    > U kunt een van uw items als de **Standaard** voor dit veld selecteren, en het wordt standaard geselecteerd wanneer gebruikers nieuwe records in uw entiteit maken.

    > [!div class="mx-imgBorder"] 
    > ![Nieuw veld](./media/data-platform-cds-newoptionset/fieldpanel-2.png "Paneel Nieuw veld")

## <a name="creating-an-option-set-from-the-option-set-list"></a>Een optieset maken via de optiesetlijst

1. Vouw in [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de sectie **Gegevens** uit en klik of tik op **Optiesets** in het linkernavigatiedeelvenster.

    > [!div class="mx-imgBorder"] 
    > ![Optiesets](./media/data-platform-cds-newoptionset/optionsetlist.png "Optiesetlijst")

2. Klik op **Nieuwe optieset**

3. Een nieuw paneel wordt geopend waarin u de optieset kunt maken. Voer de **Weergavenaam** en **Naam** in. Klik op **Nieuw item toevoegen** om met het maken van uw lijst met opties te starten. Herhaal deze stap totdat al uw items zijn gemaakt.

    > [!div class="mx-imgBorder"] 
    > ![Optieset maken](./media/data-platform-cds-newoptionset/optionset-create.png "Optieset maken")

4. Zodra u uw items hebt ingevoerd, klikt u op **Opslaan** om uw optieset te maken.

    > [!div class="mx-imgBorder"] 
    > ![Nieuwe optieset](./media/data-platform-cds-newoptionset/optionset-create-values.png "Nieuwe optieset")

5. U kunt nu deze optieset gebruiken door een nieuw veld in een entiteit te maken.

## <a name="global-and-local-option-sets"></a>Algemene en lokale optiesets

Optiesets worden standaard gemaakt als algemene optiesets waarmee ze voor meerdere entiteiten kunnen worden hergebruikt. Onder de optie **Meer weergeven** kunt u bij het maken van een nieuwe optieset een optieset **Lokaal** maken. Deze optie is alleen beschikbaar wanneer u een optieset maakt bij het toevoegen van een veld, en niet via de optiesetlijst. Lokale optiesets kunnen alleen worden gebruikt door de entiteit en het veld waarvoor ze zijn gemaakt, en kunnen niet in andere entiteiten worden hergebruikt. Deze benadering wordt alleen aangeraden voor gevorderde gebruikers die specifiek een lokale optieset nodig hebben.

> [!IMPORTANT]
> Zodra een optieset als lokaal of algemeen is gemaakt, kan dit niet meer worden gewijzigd.
