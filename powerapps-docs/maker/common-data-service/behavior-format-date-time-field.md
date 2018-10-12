---
title: Gedrag en notatie van het veld Datum en tijd in Common Data Service For Apps | MicrosoftDocs
ms.custom: ''
ms.date: 05/25/2018
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
ms.assetid: 73d691c7-344e-4c96-8979-c661c290bf81
caps.latest.revision: 47
ms.author: matp
manager: kvivek
ms.openlocfilehash: 2f62f2433fe959e3713df544628db186b801731e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680476"
---
# <a name="behavior-and-format-of-the-date-and-time-field"></a>Gedrag en indeling van het veld Datum en tijd

In de Common Data Service for Apps wordt het gegevenstype Datum en tijd gebruikt in veel velden voor standaardentiteiten. Afhankelijk van wat voor soort datum het veld vertegenwoordigt, kunt u verschillende typen veldgedrag kiezen: **Gebruikersinstelling**, **Alleen datum** of **Tijdzone-onafhankelijk**.  
  
<a name="Behavior"></a>   

## <a name="date-and-time-field-behavior-and-format"></a>Gedrag en notatie van het veld Datum en tijd  

De volgende tabel bevat informatie over het gedrag en de notatie van het veld Datum en tijd.  
  
|Gedrag|Notatie|Beschrijving|  
|--------------|------------|-------------------------------|  
|**Gebruikersinstelling** |**Alleen datum**<br />- of -<br />**Datum en tijd**|Dit is het standaardgedrag van aangepaste datum- en tijdvelden.<br /><br />De veldwaarden worden weergegeven in de lokale tijd van de huidige gebruiker.<br />Deze waarden worden in webservices geretourneerd met behulp van een algemene UTC-tijdzonenotatie.<br /><br />U kunt deze één keer wijzigen als u het standaardgedrag selecteert. Meer informatie [Gedrag van gebruikersinstelling wijzigen](#change-user-local-behavior)|  
|**Alleen datum**|**Alleen datum**|Geen tijdzoneconversie.<br /><br />Het tijdgedeelte van de waarde is altijd 12:00 uur.<br />Het datumgedeelte van de waarde wordt opgeslagen en opgehaald zoals opgegeven in de gebruikersinterface en webservices.|  
|**Time-Zone Independent**|**Alleen datum**<br />- of -<br />**Datum en tijd**|Geen tijdzoneconversie.<br /><br />De datum- en tijdwaarden worden opgeslagen en opgehaald zoals opgegeven in de gebruikersinterface en webservices.|  

## <a name="change-user-local-behavior"></a>Het gedrag van de gebruikersinstelling wijzigen:

Tenzij de uitgever van een beheerde oplossing dit verhindert, kunt u het gedrag van bestaande aangepaste datumvelden wijzigen van **Gebruikersinstelling** in **Alleen datum** of **Tijdzone-onafhankelijk**. Dit is een eenmalige wijziging.

Het wijzigen van het veldgedrag heeft invloed op de veldwaarden die zijn toegevoegd of gewijzigd nadat het veldgedrag is gewijzigd. De bestaande veldwaarden blijven in de database in de UTC-tijdzonenotatie. Als u het gedrag van de bestaande veldwaarden wilt wijzigen van UTC in Alleen datum, hebt u mogelijk de hulp van een ontwikkelaar nodig om dit programmatisch te doen. Meer informatie: [Gedrag van bestaande datum- en tijdwaarden in de database converteren](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute#convert-behavior-of-existing-date-and-time-values-in-the-database). 

> [!WARNING]
> Voordat u het gedrag van een bestaand datum- en tijdveld wijzigt, moet u alle afhankelijkheden van het veld, zoals bedrijfsregels, werkstromen, berekende velden en samengetelde velden, nagaan om te controleren of er geen problemen zijn ontstaan als gevolg van het wijzigen van het gedrag. Nadat u het gedrag van een datum- en tijdveld hebt gewijzigd, moet u elke bedrijfsregel, werkstroom, berekend en samengeteld veld openen afhankelijk van het veld dat u hebt gewijzigd, de informatie controleren en opslaan, om ervoor te zorgen dat het meest recente gedrag en de meest recente waarde van het datum- en tijdveld worden gebruikt. 

### <a name="change-behavior-during-a-solution-import"></a>Gedrag wijzigen tijdens het importeren van een oplossing

Wanneer u een oplossing importeert die een Datum-veld bevat met behulp van het gedrag **Gebruikersinstelling**, hebt u mogelijk de optie om het gedrag te wijzigen in **Alleen datum** of **Tijdzone-onafhankelijk**.  

### <a name="prevent-changing-behavior"></a>Voorkomen dat gedrag wordt gewijzigd

Als u een aangepast datumveld distribueert in een beheerde oplossing, kunt u voorkomen dat mensen die uw oplossing gebruiken het gedrag wijzigen door de beheerde eigenschap **CanChangeDateTimeBehavior** in te stellen op **False**. Meer informatie: [Beheerde veldeigenschappen](set-managed-properties-metadata.md#field-managed-properties)
  
## <a name="use-cases"></a>Use cases

Bestudeer de volgende use cases voor het gedrag **Alleen datum** en het gedrag **Tijdzone-onafhankelijk**.

### <a name="date-only-scenario-birthdays-and-anniversaries"></a>Scenario met Alleen datum: verjaardagen en jubilea

Het gedrag Alleen datum is geschikt voor die gevallen waarin informatie over de dag en de tijdzone niet is vereist, zoals verjaardagen of jubilea. Met deze selectie zien alle app-gebruikers overal ter wereld exact dezelfde datumwaarde.  
  
### <a name="time-zone-independent-scenario-hotel-check-in"></a>Tijdzone-onafhankelijk scenario: inchecken in een hotel

U kunt dit gedrag gebruiken wanneer informatie over de tijdzone niet is vereist, zoals het tijdstip waarop in een hotel moet worden ingecheckt. Met deze selectie zien alle app-gebruikers overal ter wereld exact dezelfde datum- en tijdwaarde.  


## <a name="date-and-time-query-operators-not-supported-for-date-only-behavior"></a>Queryoperators voor datum en tijd worden niet ondersteund voor het gedrag Alleen datum  

De volgende aan datum en tijd verwante queryoperators zijn ongeldig voor het gedrag **Alleen datum**. Er wordt een uitzonderingsfout met betrekking tot een ongeldige operator gegenereerd wanneer een van deze operators in de query wordt gebruikt.  
  
- Ouder dan X minuten  
- Ouder dan X uur  
- Afgelopen X uur  
- Volgende X uur  

  
### <a name="see-also"></a>Zie ook

[Velden maken en bewerken](create-edit-fields.md)<br />
[Berekende velden definiëren om handmatige berekeningen te automatiseren](define-calculated-fields.md)<br />
[Beheerde veldeigenschappen](set-managed-properties-metadata.md#field-managed-properties)<br />
[Beheerde eigenschappen](solutions-overview.md#managed-properties)

