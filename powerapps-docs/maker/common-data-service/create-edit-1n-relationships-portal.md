---
title: Eén-op-veel- of veel-op-één-entiteitsrelaties maken en bewerken met de PowerApps-portal | MicrosoftDocs
description: Meer informatie over het maken van één-op-veel- of veel-op-één-entiteitsrelaties met de PowerApps-portal
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
# <a name="create-and-edit-one-to-many-or-many-to-one-entity-relationships-using-powerapps-portal"></a>Eén-op-veel- of veel-op-één-entiteitsrelaties maken en bewerken met de PowerApps-portal

De [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) biedt een eenvoudige manier om 1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) te maken en te bewerken voor Common Data Service for Apps.

Met de portal wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. Zie voor meer informatie: 
- [1:N- (één-op-veel) of N:1-relaties (veel-op-één) maken en bewerken](create-edit-1n-relationships.md)
- [1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken met de oplossingenverkenner](create-edit-1n-relationships-solution-explorer.md).

## <a name="view-entity-relationships"></a>Entiteitsrelaties weergeven

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

## <a name="create-relationships"></a>Relaties maken

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-entity-relationships) op de opdrachtbalk **Relatie toevoegen** en kies **Veel-op-één** of **Eén-op-veel**.

![Het type relatie selecteren](media/add-relationship-menu-portal.png)

> [!NOTE]
> Raadpleeg voor informatie over **Veel-op-veel**-relaties [N:N-relaties (veel-op-veel) maken](create-edit-nn-relationships.md)

<!-- This may change going forward, but this is the way it is now. #2534972 -->
> [!Important]
> De portal gebruikt andere terminologie dan de oplossingenverkenner. De termen zijn omgekeerd. **Gerelateerde entiteit** van de oplossingenverkenner is **Primaire entiteit** in de portal. Zo ook is **Primaire entiteit** van de oplossingenverkenner **Gerelateerde entiteit** in de portal.

Afhankelijk van uw keuze ziet u een van de twee onderstaande mogelijkheden:

<!-- These are the correct screenshots from the UI as of 6/11/18 -->
|Type|Deelvenster|
|--|--|
|**Eén-op-veel**|![Deelvenster Veel-op-één-relatie](media/many-to-one-relationship-panel.png)|
|**Eén-op-veel**|![Deelvenster Eén-op-veel-relatie](media/one-to-many-relationship-panel.png)|

Kies **Gerelateerde entiteit** of **Primaire entiteit** voor de relatie die u tussen de twee entiteiten wilt maken. 

> [!NOTE]
> Met beide opties wordt een opzoekveld gemaakt in de *primaire* entiteit.

Nadat u de entiteit hebt geselecteerd, kunt u de details van de relatie bewerken. In dit voorbeeld kunnen er meerdere entiteitsrecords voor contactpersonen aan één account worden gekoppeld.

<!-- These are the correct screenshots from the UI as of 6/11/18 -->
![Eén-op-veel-relatie van account en contactpersoon](media/One-to-many-account-contact.png)

U kunt de opgegeven standaardwaarden bewerken voordat u opslaat. Selecteer **Meer opties** om de waarden van **Relatienaam** en **Beschrijving opzoekveld** weer te geven

|Veld|Beschrijving|
|--|--|
|**Weergavenaam van opzoekveld**|De lokaliseerbare tekst voor het opzoekveld dat in de gerelateerde entiteit wordt gemaakt.<br />Dit kan later worden bewerkt.|
|**Opzoekveldnaam**|De naam voor het opzoekveld dat in de gerelateerde entiteit wordt gemaakt.|
|**Relatienaam**|De naam voor de relatie die wordt gemaakt.|
|**Beschrijving opzoekveld**|De beschrijving voor het opzoekveld. In modelgestuurde apps wordt dit als knopinfo weergegeven als mensen hun muis boven het veld houden. <br />Dit kan later worden bewerkt.|

U kunt doorgaan met het bewerken van de entiteit. Selecteer **Entiteit opslaan** om de relatie te maken die u hebt geconfigureerd.

## <a name="edit-relationships"></a>Relaties bewerken

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-entity-relationships) de relatie die u wilt bewerken.

> [!NOTE]
> Elke relatie kan in de primaire entiteit of de gerelateerde entiteit worden gevonden als een **Veel-op-één**- of **Eén-op-veel**-relatie. Hoewel de relatie op beide plaatsen kan worden bewerkt, is het dezelfde relatie.
>
> Uitgevers van een beheerde oplossing kunnen voorkomen dat sommige aanpassingen van relaties worden gemaakt die deel uitmaken van hun oplossing.

De enige velden die u kunt bewerken, zijn **Weergavenaam opzoekveld** en **Beschrijving opzoekveld**. U kunt deze velden ook bewerken in de eigenschappen van het opzoekveld in de gerelateerde entiteit. Meer informatie: [Een veld bewerken](create-edit-field-portal.md#edit-a-field)

## <a name="delete-relationships"></a>Relaties verwijderen

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-entity-relationships) de relatie die u wilt verwijderen.

![Entiteitsrelatie verwijderen](media/delete-entity-relationship-portal.png)

U kunt de opdracht **Relatie verwijderen** van de opdrachtbalk of via het rijcontextmenu gebruiken wanneer u klikt op de drie puntjes (**...**).

Als de relatie wordt verwijderd, wordt het opzoekveld in de gerelateerde entiteit verwijderd.

> [!NOTE]
> U kunt geen relatie verwijderen die afhankelijkheden bevat. Als u bijvoorbeeld het opzoekveld hebt toegevoegd aan een formulier voor de gerelateerde entiteit, moet u het veld uit het formulier verwijderen voordat u de relatie verwijdert.

### <a name="see-also"></a>Zie ook

[Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)<br />
[1:N- (één-op-veel) of N:1-relaties (veel-op-één) maken en bewerken](create-edit-1n-relationships.md)<br />
[1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken met de oplossingenverkenner](create-edit-1n-relationships-solution-explorer.md)<br />
[Een veld bewerken](create-edit-field-portal.md#edit-a-field)
