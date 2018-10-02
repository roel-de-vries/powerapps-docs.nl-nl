---
title: 'N:N-entiteitsrelaties (veel-op-veel) maken in Common Data Service voor Apps met de oplossingenverkenner | MicrosoftDocs'
description: Veel-op-een-relaties maken
ms.custom: ''
ms.date: 05/29/2018
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

# <a name="create-nn-many-to-many-entity-relationships-in-common-data-service-for-apps-using-solution-explorer"></a>N:N-entiteitsrelaties (veel-op-veel) maken in Common Data Service voor Apps met de oplossingenverkenner

De oplossingenverkenner biedt één manier om N:N-relaties (veel-op-veel) te maken en te bewerken voor Common Data Service voor Apps.

Met de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. Zie voor meer informatie:
- [Overzicht van het maken van veel-op-veel-entiteitsrelaties (N:N)](create-edit-nn-relationships.md)
- [Veel-op-veel-entiteitsrelaties maken in Common Data Service voor Apps met de PowerApps-portal](create-edit-nn-relationships-portal.md)

  
## <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

Een deel van de naam van een aangepaste relatie die u maakt is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel is wat u voor deze entiteit wilt. Meer informatie: [Het voorvoegsel voor de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entity-relationships"></a>Entiteitsrelaties weergeven

Vouw in de oplossingenverkenner **Entiteiten** uit en selecteer een entiteit. Selecteer binnen deze entiteit **N:N-relaties**.

![N:N-entiteitsrelaties weergeven](media/view-nn-entity-relationships-solution-explorer.png)

## <a name="create-relationships"></a>Relaties maken

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-entity-relationships) **Nieuwe veel-op-veel-relatie** op de opdrachtbalk.

> [!NOTE]
> Als de opdracht niet beschikbaar is, komt de entiteit niet in aanmerking om een aangepaste relatie te maken.

![Formulier Nieuwe veel-op-veel-relatie](media/new-nn-entity-relationship-form-solution-explorer.png)

Kies in de groep **Andere entiteit** in het veld **Entiteitsnaam** de entiteit waarmee u de relatie wilt maken. Hiermee worden de velden **Naam** en **Entiteitsnaam voor relatie** in de groep **Relatiedefinitie** ingevuld.

U kunt klikken op de ![knop Entiteitsrelatie opslaan](media/save-entity-icon-solution-explorer.png) om de entiteit op te slaan en verder te gaan met bewerken. Meer informatie: [Relaties bewerken](#edit-relationships)

> [!NOTE]
> Als de waarden van **Naam** of **Entiteitsnaam voor relatie** al in het systeem bestaan, ontvangt u een foutbericht wanneer u opslaat. Bewerk de waarden zodat deze uniek zijn en probeer het opnieuw.

## <a name="edit-relationships"></a>Relaties bewerken

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-entity-relationships) de entiteit die u wilt bewerken. 

> [!NOTE]
> De uitgever van een beheerde oplossing kunnen voorkomen dat aanpassingen van relaties worden gemaakt die deel uitmaken van hun oplossing.

De volgende entiteitsrelatie-eigenschappen kunnen worden bewerkt nadat de relatie is gemaakt.

> [!IMPORTANT]
> Nadat u deze eigenschappen hebt bewerkt, moet u aanpassingen publiceren voordat ze in modelgestuurde apps van kracht worden.

### <a name="edit-display-options"></a>Weergaveopties bewerken

Voor zowel **Huidige entiteit** als **Andere entiteit** kunt u de velden voor weergaveopties bewerken waarmee wordt bepaald hoe de gerelateerde entiteiten voor modelgestuurde apps worden weergegeven.

|Veld|Beschrijving|
|--|--|
|**Weergaveoptie**|Hoe de lijst met gerelateerde entiteiten moet worden weergegeven. Meer informatie: [Weergaveopties](#display-options)|
|**Aangepast label**|Geef de lokaliseerbare tekst op die moet worden gebruikt in plaats van de meervoudsnaam wanneer u **Aangepast label gebruiken** als **Weergaveoptie** selecteert.|
|**Weergavegebied**|Selecteer een van de beschikbare groeperingen om deze lijst weer te geven. De beschikbare opties zijn: **Details** (voor de groep *Algemeen* ), **Marketing**, **Verkoop** en **Service**. |
|**Weergavevolgorde**|Hiermee wordt bepaald waar het navigatie-item wordt opgenomen binnen het geselecteerde weergavegebied. Het bereik van toegestane getallen begint bij 10.000. Navigatiedeelvensteritems met een lagere waarde worden weergegeven boven andere relaties met een hogere waarde.|

<!-- TODO: Not sure whether Display Area or Display Order are still used anymore. Might only be used in the Outlook client?-->

#### <a name="display-options"></a>Weergaveopties

Dit zijn de beschikbare weergaveopties:

|Optie|Beschrijving|
|--|--|
|**Niet weergeven**|Geef de gerelateerde entiteiten voor deze relatie niet weer.|
|**Aangepast label gebruiken**|Als deze optie wordt gekozen, wordt het veld **Aangepast label** ingeschakeld zodat u de lokaliseerbare tekst kunt opgeven die in plaats van de meervoudsnaam moet worden gebruikt.|
|**Meervoudsnaam gebruiken**|Gebruik de meervoudsweergavenaam die voor de gerelateerde entiteit is gedefinieerd.|

### <a name="searchable"></a>Kan worden doorzocht

U kunt de relatie van **Geavanceerd zoeken** in modelgestuurde apps verbergen door het veld **Kan worden doorzocht** op **Nee** in te stellen.

## <a name="delete-relationships"></a>Relaties verwijderen

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-entity-relationships) de entiteitsrelatie die u wilt verwijderen en kik op de opdracht ![Verwijderen](media/delete.gif).

Als de relatie wordt verwijderd, wordt de gemaakte relatie-entiteit verwijderd. Alle entiteiten die gegevens verbinden met de relatie gaan verloren.

### <a name="see-also"></a>Zie ook

[Overzicht van het maken van veel-op-veel-entiteitsrelaties (N:N)](create-edit-nn-relationships.md)<br />
[Veel-op-veel-entiteitsrelaties maken in Common Data Service voor Apps met de PowerApps-portal](create-edit-nn-relationships-portal.md)<br />
[1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken](create-edit-1n-relationships.md)
