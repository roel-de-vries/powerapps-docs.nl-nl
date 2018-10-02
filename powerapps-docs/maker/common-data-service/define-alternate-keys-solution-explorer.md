---
title: Alternatieve sleutels definiëren via oplossingenverkenner | MicrosoftDocs
description: Leer hoe u alternatieve sleutels voor verwijzingen naar records opgeeft in Common Data Service voor Apps via de oplossingenverkenner
ms.custom: ''
ms.date: 05/31/2018
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
# <a name="define-alternate-keys-using-solution-explorer"></a>Alternatieve sleutels definiëren via oplossingenverkenner

De oplossingenverkenner biedt één manier om alternatieve sleutels weer te geven en te maken voor Common Data Service voor Apps.

Met de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. <br />Zie voor meer informatie: 
- [Alternatieve sleutels definiëren om te verwijzen naar records](define-alternate-keys-reference-records.md)<br />
- [Alternatieve sleutels definiëren via PowerApps-portal](define-alternate-keys-portal.md)

## <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

Een deel van de naam van een alternatieve sleutel die u maakt is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel is wat u voor deze entiteit wilt. Meer informatie: [Het voorvoegsel voor de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-alternate-keys"></a>Alternatieve sleutels weergeven

1. Vouw terwijl de oplossingenverkenner is geopend onder **Entiteiten** uit onder **Onderdelen** en selecteer vervolgens de entiteit waarin u alternatieve sleutels wilt weergeven.
2. Vouw de entiteit uit en selecteer **Sleutels**.

    ![Alternatieve sleutels weergeven](media/view-alternate-keys-solution-explorer.png)

## <a name="create-an-alternate-key"></a>Een alternatieve sleutel maken

1. Selecteer terwijl de [alternatieve sleutels worden weergegeven](#view-alternate-keys) de optie **Nieuw**.
1. Voer in het formulier de **weergavenaam** in. Het veld **Naam** wordt automatisch ingevuld op basis van de **weergavenaam**. 
2. Selecteer elk kenmerk in de lijst **Beschikbare kenmerken** en selecteer vervolgens **Toevoegen >** om het kenmerk naar de lijst **Geselecteerde kenmerken** te verplaatsen.
    ![Alternatieve sleutel maken](media/create-alternate-key-solution-explorer.png)
1. Selecteer **OK** om het formulier te sluiten.

### <a name="optional-view-the-system-job-tracking-creation-of-indexes"></a>(Optioneel) De systeemtaak voor het bijhouden van het maken van indexen weergeven
1. Nadat u een nieuwe alternatieve sleutel hebt gemaakt, wordt in de [weergave van alternatieve sleutels](#view-alternate-keys) een rij weergegeven voor de sleutel die u hebt gemaakt.
2. In de kolom **Systeemtaak** vindt u een koppeling naar de systeemtaak waarmee het maken van de indexen ter ondersteuning van de alternatieve sleutels wordt bijgehouden. 
    
    De systeemtaak heeft een naam met het patroon `Create index for {0} for entity {1}`, waarbij `0` de **weergavenaam** van de alternatieve sleutel is en `1` de naam van de entiteit.

    De koppeling naar de systeemtaak wordt niet weergegeven als de systeemtaak is voltooid. Meer informatie: [Systeemtaken bewaken en beheren](/dynamics365/customer-engagement/admin/monitor-manage-system-jobs)


## <a name="delete-an-alternate-key"></a>Een alternatieve sleutel verwijderen

Selecteer in de [weergave met alternatieve sleutels](#view-alternate-keys) de optie ![Verwijderen](media/delete.gif).

### <a name="see-also"></a>Zie ook

[Alternatieve sleutels definiëren om te verwijzen naar records](define-alternate-keys-reference-records.md)<br />
[Alternatieve sleutels definiëren via PowerApps-portal](define-alternate-keys-portal.md)<br />
[Documentatie voor ontwikkelaars: Alternatieve sleutels voor een entiteit definiëren](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)
