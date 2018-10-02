---
title: Veel-op-veel-entiteitsrelaties maken in Common Data Service voor Apps met de PowerApps-portal | MicrosoftDocs
description: Veel-op-een-relaties maken
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-many-to-many-entity-relationships-in-common-data-service-for-apps-using-powerapps-portal"></a>Veel-op-veel-entiteitsrelaties maken in Common Data Service voor Apps met de PowerApps-portal

De [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) biedt een eenvoudige manier om Veel-op-veel-entiteitsrelaties te maken en te bewerken voor Common Data Service for Apps.

Met de portal wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. Zie voor meer informatie: 
- [N:N-entiteitsrelaties (veel-op-veel) maken](create-edit-nn-relationships.md)
- [N:N-entiteitsrelaties (veel-op-veel) maken in Common Data Service voor Apps met de oplossingenverkenner](create-edit-nn-relationships-solution-explorer.md)

## <a name="view-many-to-many-entity-relationships"></a>Veel-op-veel-entiteitsrelaties weergeven

1. Selecteer via de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de ontwerpmodus **Modelgestuurd** of **Canvas**.
2. Selecteer **Gegevens** > **Entiteiten** en selecteer de entiteit met de relaties die u wilt weergeven.
3. U kunt terwijl het tabblad **Relaties** is geselecteerd de volgende weergaven selecteren: 

 |weergave|Beschrijving|
 |--|--|
 |**Alle**| Hiermee worden alle relaties voor de entiteit weergegeven|
 |**Aangepast**|Hiermee worden alleen aangepaste relaties voor de entiteit weergegeven|
 |**Standaard**|Hiermee worden alleen de standaardrelaties voor de entiteit weergegeven|
<!-- TODO: What is the actual difference between All and Default? -->

![Entiteitsrelaties voor account](media/view-account-relationships-portal.png)

Veel-op-veel-relaties hebben een **Relatietype** van **Veel-op-veel**.

> [!NOTE]
> De entiteit die u weergeeft, heeft mogelijk geen **Veel-op-veel**-relaties.

## <a name="create-relationships"></a>Relaties maken

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-many-to-many-entity-relationships) op de opdrachtbalk **Relatie toevoegen** en kies **Veel-op-veel**.

![Het type relatie selecteren](media/add-relationship-menu-portal.png)

Kies in het paneel **Veel-op-veel** de entiteit die u wilt relateren aan de huidige entiteit.

![Het paneel Veel-op-veel waarin de accountentiteit is geselecteerd](media/many-to-many-panel-1.png)

Selecteer **Meer opties** om de velden **Relatienaam** en **Entiteitsnaam voor relatie** weer te geven

![Het paneel Veel-op-veel waarin Meer opties is geselecteerd](media/many-to-many-panel-2.png)

De waarden voor deze velden worden voor u gegenereerd op basis van de gekozen entiteiten.

> [!NOTE]
> Als u meerdere **Veel-op-veel**-relaties met dezelfde twee entiteiten maakt, moet u de gegenereerde velden **Naam van relatie** en **Entiteitsnaam voor relatie** bewerken zodat ze uniek zijn.

Selecteer **OK** om het paneel **Veel-op-veel** te sluiten. De relatie wordt gemaakt als u de wijzigingen in de entiteit opslaat. 

Zodra deze zijn opgeslagen, kan er niets meer worden gewijzigd met de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Als u eigenschappen van de relatie voor modelgestuurde apps wilt bewerken, gebruikt u de [oplossingenverkenner](create-edit-nn-relationships-solution-explorer.md).

## <a name="delete-relationships"></a>Relaties verwijderen

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-many-to-many-entity-relationships) de relatie die u wilt verwijderen.

![Entiteitsrelatie verwijderen](media/delete-entity-relationship-portal.png)

U kunt de opdracht **Relatie verwijderen** van de opdrachtbalk of via het rijcontextmenu gebruiken wanneer u klikt de drie puntjes (**...**) selecteert.

Als de veel-op-veel-relatie wordt verwijderd, wordt de gemaakte relatie-entiteit verwijderd. Alle entiteiten die gegevens verbinden met de relatie gaan verloren.

### <a name="see-also"></a>Zie ook

[N:N-entiteitsrelaties (veel-op-veel) maken](create-edit-nn-relationships.md)<br />
[N:N-entiteitsrelaties (veel-op-veel) maken in Common Data Service voor Apps met de oplossingenverkenner](create-edit-nn-relationships-solution-explorer.md)
