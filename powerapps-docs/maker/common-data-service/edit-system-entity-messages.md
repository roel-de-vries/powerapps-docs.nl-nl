---
title: Systeementiteitsberichten bewerken met PowerApps | MicrosoftDocs
description: Meer informatie over het bewerken van berichten van systeementiteiten
ms.custom: ''
ms.date: 05/15/2018
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
ms.assetid: 3ccbd8de-8d6f-4058-87f7-15463667cfc6
caps.latest.revision: 41
ms.author: matp
manager: kvivek
ms.openlocfilehash: 797d6855bea421abd90752dd9ae0ad73a9d92f38
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39678612"
---
# <a name="edit-system-entity-messages"></a>Berichten van systeementiteiten bewerken

De standaardweergavenaam van bepaalde systeementiteiten wordt gebruikt in tekst in de gebruikersinterface en foutberichten in Common Data Service voor Apps. Als u de weergavenaam wijzigt, moet u alle berichten die de standaardweergavenaam gebruiken, bijwerken. Als u bijvoorbeeld de weergavenaam verandert van *Account* in *Bedrijf*, kunt u nog steeds een foutbericht met de oude naam te zien krijgen.  

U kunt systeemberichten niet bewerken in de PowerApps-portal, u moet hiervoor Solution Explorer gebruiken.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

In Solution Explorer, onder de entiteit, als u een **Berichten**knooppunt ziet, kunt u bepaalde tekst bewerken waarin wordt gerefereerd aan de originele weergavenaam van de entiteit. 

![Entiteitsberichten](../model-driven-apps/media/entity-messages.png)

Het bewerken van deze tekst is eenvoudig. Dubbelklik op het bericht om een formulier weer te geven met drie velden:  
  
|Veld|Beschrijving|  
|-----------|-----------------|  
|**Standaard weergavetekenreeks**|Toont de originele tekst.|  
|**Aangepaste weergavetekenreeks**|Bewerk deze tekst om de weergavetekenreeks te wijzigen.|  
|**Opmerking**|Optioneel. Voeg een opmerking in over wat u hebt gewijzigd en waarom.|  
  
Bepaalde berichttekst kan tijdelijke aanduidingen bevatten. Deze tijdelijke aanduidingen zijn getallen met haakjes aan weerszijden. Bijvoorbeeld: `{0}`. Deze tijdelijke aanduidingen zorgen ervoor dat er tekst kan worden ingevoegd in het bericht. Als u deze berichten bewerkt, zorg er dan voor dat u deze tijdelijke aanduidingen behoudt. 

Selecteer ![Opslaan](media/save-entity-icon-solution-explorer.png) om uw wijzigingen op te slaan. Selecteer **Opslaan en sluiten** om het formulier te sluiten als u het opslaat.

> [!NOTE]
> De gebruikersinterface die wordt gebruikt bij het bewerken van berichten van systeementiteiten bevat veel maar niet alle entiteitsnamen. Zie [Lokaliseerbare tekst in de standaardtaal bijwerken](../model-driven-apps/translate-localizable-text.md#updating-localizable-text-in-the-base-language) voor een uitgebreidere aanpak

## <a name="programmatically-update-entity-display-strings"></a>Programmatisch weergavereeksen van entiteiten bewerken

Voor ontwikkelaars die zoeken naar een manier om hiermee in code te werken, de weergavereeksen zijn opgeslagen in de [DisplayString](../../developer/common-data-service/reference/entities/displaystring.md)-entiteit. 

De `DisplayString`-entiteit bevat niet de standaardweergavereeksen. De twee attributen voor deze entiteit die tekst bevatten zijn [CustomDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_CustomDisplayString) en [PublishedDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_PublishedDisplayString). Standaard zijn de waarden van deze kenmerken nul, tenzij de weergavereeks is aangepast en gepubliceerd. De `PublishedDisplayString`-waarde is alleen-lezen en geeft de huidige gepubliceerde `CustomDisplayString` weer.
 
## <a name="see-also"></a>Zie ook
[Een entiteit bewerken](edit-entities.md)<br />
[Lokaliseerbare tekst voor modelgestuurde apps vertalen](../model-driven-apps/translate-localizable-text.md)
