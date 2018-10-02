---
title: Algemene optiesets maken en bewerken voor Common Data Service voor Apps met de oplossingenverkenner | MicrosoftDocs
ms.custom: ''
ms.date: 05/26/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-global-option-sets-for-common-data-service-for-apps-using-solution-explorer"></a>Algemene optiesets maken en bewerken voor Common Data Service voor Apps met de oplossingenverkenner

De oplossingenverkenner biedt één manier om algemene optiesets voor Common Data Service voor Apps te maken en te bewerken met Common Data Service voor Apps.

Met de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. <br />Zie voor meer informatie: 
- [Algemene optiesets maken en bewerken voor Common Data Service voor Apps](create-edit-global-option-sets.md)
- [Een optieset maken](custom-picklists.md)

## <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

Een deel van de naam van een algemene optieset die u maakt, is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel is wat u voor deze algemene optieset wilt. Meer informatie: [Het voorvoegsel voor de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-global-option-sets"></a>Algemene optiesets weergeven

Selecteer terwijl de oplossingenverkenner is geopend onder **Onderdelen** de optie **Optiesets**.

![Algemene optiesets weergeven](media/view-global-option-sets-solution-explorer.png)

> [!NOTE]
> Sommige algemene optiesets van het systeem kunnen niet worden aangepast. Deze opties kunnen veranderen tijdens updates of nieuwe versies, dus wij adviseren u dat u ze niet gebruikt tenzij u zeker weet dat uw vereisten op één lijn zijn met de manier waarop CDS voor Apps deze waarden gebruikt.

## <a name="create-a-global-option-set"></a>Een algemene optieset maken

> [!NOTE]
> U hoeft geen algemene optieset te maken voordat u deze in een aangepast veld gebruikt. Als u een nieuw optiesetveld maakt, hebt u de mogelijkheid een nieuwe algemene optieset te maken of een bestaande te gebruiken. Zie [Opties voor het veld Optieset](create-edit-field-solution-explorer.md#option-set-field-options)

Klik tijdens het weergeven van de algemene optiesets op **Nieuw** om een formulier te openen om de algemene optieset te definiëren.

![Algemene optieset maken](media/create-global-option-set-solution-explorer.png)

Typ een **Weergavenaam** die zichtbaar is voor personen met de rol van systeembeheerder of systeemaanpasser die deze algemene optieset kiezen bij het definiëren van nieuwe velden kiezen waarin deze wordt gebruikt. Deze naam is niet zichtbaar voor personen die uw apps gebruiken.

De veldwaarde **Naam** wordt voor u gegenereerd op basis van de **Weergavenaam** die u invoert. De veldwaarde omvat het aanpassingsvoorvoegsel van de oplossingsuitgever in de context van de oplossing waarin u werkt. U kunt het gegenereerde gedeelte van de veldwaarde **Naam** wijzigen voordat u opslaat.

Typ een **Beschrijving** voor de algemene optieset. 

> [!TIP]
> Gebruik de **Beschrijving** om het doel van deze algemene optieset uit te leggen. Deze waarde is niet zichtbaar voor gebruikers van de toepassing. Het is voor andere mensen met de rol van systeembeheerder of systeemaanpasser die willen weten waarom deze bepaalde algemene optieset is gemaakt.

### <a name="configure-options"></a>Opties configureren

[!INCLUDE [cc_configure-option-set-options-solution-explorer](../../includes/cc_configure-option-set-options-solution-explorer.md)]

## <a name="edit-a-global-option-set"></a>Een algemene optieset bewerken

Selecteer tijdens het weergeven van algemene optiesets de optieset die u wilt bewerken om het paneel te openen om deze te bewerken.

U mag niet de veldwaarde **Naam** of de aan een optie toegewezen nummer**Waarde** wijzigen, maar verder kunt u alle mogelijke wijzigingen aanbrengen bij het maken van de algemene optieset.

[!INCLUDE [cc_remove-option-warning](../../includes/cc_remove-option-warning.md)]

## <a name="delete-a-global-option-set"></a>Een algemene optieset verwijderen

Als u een algemene optieset wilt verwijderen, selecteert u tijdens het weergeven van de lijst ![Opdracht Verwijderen](media/delete.gif) op de opdrachtbalk.

> [!IMPORTANT]
> Als de algemene optieset door een veld is gebruikt, kunt u deze pas verwijderen als dit veld wordt verwijderd.
  
### <a name="see-also"></a>Zie ook
 
[Algemene optiesets maken en bewerken voor Common Data Service voor Apps](create-edit-global-option-sets.md)<br />
[Een optieset maken](custom-picklists.md)<br />
[Velden maken en bewerken](create-edit-fields.md)<br />
[Ontwikkelaarsdocumentatie: Algemene optiesets aanpassen](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)
