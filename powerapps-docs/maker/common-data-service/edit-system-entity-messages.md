---
title: Systeementiteitberichten bewerken met PowerApps | MicrosoftDocs
description: Leer hoe u systeementiteitberichten kunt bewerken
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="edit-system-entity-messages"></a>Systeementiteitsberichten bewerken

De standaardweergavenaam van sommige systeementiteiten wordt gebruikt in gebruikersinterfacetekst en foutberichten in Common Data Service voor Apps. Als u de weergavenaam wijzigt, dan moet u ook berichten bijwerken die de standaardweergavenaam gebruiken. Als u bijvoorbeeld de weergavenaam wijzigt van *Account* in *Bedrijf*, kunt u nog steeds een foutbericht met de oude naam te zien krijgen.  

U kunt systeemberichten niet bewerken via de PowerApps-portal. Hiervoor moet u de oplossingenverkenner gebruiken.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Als u in de oplossingenverkenner, onder de entiteit, een knooppunt **Berichten** ziet, dan kunt u bepaalde tekst bewerken die verwijzingen naar de oorspronkelijke entiteitsweergavenaam bevat. 

![Berichten voor entiteit](../model-driven-apps/media/entity-messages.png)

Bewerken van deze tekst is ongecompliceerd. Dubbelklik op het bericht om een formulier met drie velden te zien:  
  
|Veld|Beschrijving|  
|-----------|-----------------|  
|**Standaardweergavereeks**|Toont de oorspronkelijke tekst.|  
|**Aangepaste weergavereeks**|Bewerk deze tekst om de weergavetekenreeks te wijzigen.|  
|**Opmerking**|Optioneel. Bevat een opmerking over wat u hebt gewijzigd en waarom.|  
  
Berichttekst kan tijdelijke aanduidingen bevatten. Deze tijdelijke aanduidingen zijn getallen met haakjes aan beide zijden. Voorbeeld: `{0}`. Door deze tijdelijke aanduidingen kan tekst in het bericht worden ingevoegd. Als u berichten bewerken, zorg er dan voor dat u deze tijdelijke aanduidingen behoudt. 

Selecteer ![Opslaan](media/save-entity-icon-solution-explorer.png) om uw wijzigingen op te slaan. Selecteer **Opslaan en sluiten** om het formulier te sluiten na het opslaan.

> [!NOTE]
> Hoewel de gebruikersinterface voor het bewerken van systeementiteitsberichten veel verwijzingen naar entiteitsnamen bevat, zijn niet alle entiteitsnamen hierin opgenomen. Zie [Lokaliseerbare tekst in de standaardtaal bijwerken](../model-driven-apps/translate-localizable-text.md#updating-localizable-text-in-the-base-language) voor een bredere benadering.

## <a name="programmatically-update-entity-display-strings"></a>Tekenreeksen van entiteiten programmatisch bijwerken

Voor ontwikkelaars die met deze tekenreeksen in code willen werken, zijn de weergavetekenreeksen opgeslagen in de entiteiten [DisplayString](../../developer/common-data-service/reference/entities/displaystring.md). 

De entiteit `DisplayString` bevat niet de standaardtekenreeksen. De twee kenmerken voor deze entiteit die tekst bevat zijn [CustomDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_CustomDisplayString) en [PublishedDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_PublishedDisplayString). Standaard zijn deze kenmerkwaarden null tenzij de tekenreeks is aangepast en gepubliceerd. De `PublishedDisplayString`-waarde is alleen-lezen en heeft betrekking op de momenteel gepubliceerde `CustomDisplayString`.
 
## <a name="see-also"></a>Zie ook
[Een entiteit bewerken](edit-entities.md)<br />
[Lokaliseerbare tekst vertalen voor modelgestuurde apps](../model-driven-apps/translate-localizable-text.md)
