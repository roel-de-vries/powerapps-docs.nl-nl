---
title: Alternatieve sleutels definiëren via PowerApps-portal | MicrosoftDocs
description: Leer hoe u alternatieve sleutels definieert via PowerApps-portal
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
# <a name="define-alternate-keys-using-powerapps-portal"></a>Alternatieve sleutels definiëren via PowerApps-portal

De [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) biedt een eenvoudige manier om alternatieve sleutels voor entiteiten weer te geven en te maken voor Common Data Service voor Apps.

Met de portal wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. <br />Zie voor meer informatie: 
- [Alternatieve sleutels definiëren om te verwijzen naar records](define-alternate-keys-reference-records.md)
- [Alternatieve sleutels definiëren via oplossingenverkenner](define-alternate-keys-solution-explorer.md)

## <a name="view-alternate-keys"></a>Alternatieve sleutels weergeven

1. Selecteer via de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de ontwerpmodus **Modelgestuurd** of **Canvas**.
2. Selecteer **Gegevens** > **Entiteiten** en selecteer de entiteit die u wilt weergeven.
3. Selecteer **Sleutels** om een lijst met gedefinieerde alternatieve sleutels te bekijken.

    ![Alternatieve sleutels weergeven](media/view-alternate-keys-portal.png)

## <a name="create-an-alternate-key"></a>Een alternatieve sleutel maken

1. Selecteer terwijl de [alternatieve sleutels worden weergegeven](#view-alternate-keys) de optie **Sleutel toevoegen**.
2. Gebruik het deelvenster om een **weergavenaam** te selecteren en kies de velden om de alternatieve sleutel te maken.

    Het veld **Naam** wordt ingevuld op basis van de weergavenaam.

    ![Voorbeelddefinitie van alternatieve sleutel](media/alternate-key-account-number-sic-code.png)

1. Selecteer **Gereed** om het deelvenster te sluiten.
2. Klik op **Entiteit opslaan** om de alternatieve sleutel te maken.

> [!NOTE]
> De alternatieve sleutel is niet onmiddellijk beschikbaar. Er wordt een systeemtaak uitgevoerd wanneer u de entiteit opslaat om database-indexen te maken ter ondersteuning van de alternatieve sleutel.

## <a name="delete-an-alternate-key"></a>Een alternatieve sleutel verwijderen

Selecteer tijdens het [weergeven van alternatieve sleutels](#view-alternate-keys) de sleutel die u wilt verwijderen en kies **Sleutel verwijderen** op de opdrachtbalk.

### <a name="see-also"></a>Zie ook

[Alternatieve sleutels definiëren om te verwijzen naar records](define-alternate-keys-reference-records.md)<br />
[Alternatieve sleutels definiëren via oplossingenverkenner](define-alternate-keys-solution-explorer.md)<br />
[Documentatie voor ontwikkelaars: Alternatieve sleutels voor een entiteit definiëren](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)
