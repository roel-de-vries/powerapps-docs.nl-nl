---
title: Gedrag en indeling van het veld Datum en tijd in Common Data Service voor Apps | MicrosoftDocs
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="behavior-and-format-of-the-date-and-time-field"></a>Gedrag en indeling van het datum- en tijdveld

In Common Data Service voor Apps wordt het gegevenstype Datum en tijd in veel standaardentiteitsvelden gebruikt. Afhankelijk van het datumtype dat met het veld wordt vertegenwoordigd, kunt u verschillende veldgedragingen kiezen: **Gebruikersinstelling**, **Alleen datum** of **Tijdzone-onafhankelijk**.  
  
<a name="Behavior"></a>   

## <a name="date-and-time-field-behavior-and-format"></a>Gedrag en indeling van datum- en tijdveld  

De volgende tabel bevat informatie over het gedrag en de indeling van het datum- en tijdveld.  
  
|Gedrag|Opmaak|Beschrijving|  
|--------------|------------|-------------------------------|  
|**Gebruikersinstelling** |**Alleen datum**<br />- of -<br />**Datum en tijd**|Dit is het standaardgedrag van aangepaste datum- en tijdvelden.<br /><br />De veldwaarden worden weergegeven in de lokale tijd van de huidige gebruiker.<br />In webservices worden deze waarden geretourneerd volgens een algemene UTC-tijdzone.<br /><br />U kunt deze tijd wijzigen als u het standaardgedrag selecteert. Meer informatie [Gedrag van gebruikersinstelling wijzigen](#change-user-local-behavior)|  
|**Alleen datum**|**Alleen datum**|Geen tijdzoneconversie<br /><br />Het tijdgedeelte van de waarde is altijd 12:00AM.<br />Het datumgedeelte van de waarde wordt opgeslagen en opgehaald zoals is opgegeven in de gebruikersinterface en webservices.|  
|**Tijdzone-onafhankelijk**|**Alleen datum**<br />- of -<br />**Datum en tijd**|Geen tijdzoneconversie<br /><br />De datum- en tijdwaarden worden opgeslagen en opgehaald zoals is opgegeven in de gebruikersinterface en webservices.|  

## <a name="change-user-local-behavior"></a>Gedrag van gebruikersinstelling wijzigen:

Tenzij de uitgever van een beheerde oplossing dit verhindert, kunt u het gedrag van bestaande aangepaste datumvelden veranderen van **Gebruikersinstelling** in **Alleen datum** of **Tijdzone-onafhankelijk**. Dit is een eenmalige wijziging.

Als het veldgedrag wordt gewijzigd, veranderen de veldwaarden die worden toegevoegd of gewijzigd na aanpassing van het veldgedrag. De bestaande veldwaarden blijven in de database in de UTC-tijdzone-indeling. Als u het gedrag van de bestaande veldwaarden wilt wijzigen van UTC in Alleen datum, hebt u mogelijk hulp nodig van een ontwikkelaar om het programmatisch te doen. Meer informatie:  [Het gedrag van bestaande datum- en tijdwaarden in de database converteren](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute#convert-behavior-of-existing-date-and-time-values-in-the-database). 

> [!WARNING]
> Voordat u het gedrag van een bestaand datum- en tijdveld gaat wijzigen, dient u alle afhankelijkheden van het veld, zoals bedrijfsregels, werkstromen en berekende of samengetelde velden, te bekijken om er zeker van te zijn dat er geen problemen optreden ten gevolge van het wijzigen van het gedrag. Nadat u het gedrag van een datum- en tijdveld hebt gewijzigd, dient u minimaal elke record voor een bedrijfsregel, werkstroom, berekend veld of samengeteld veld die afhankelijk is van het gewijzigde veld te openen, de informatie te bekijken en deze op te slaan om er zeker van te zijn dat het meest recente gedrag van het datum- en tijdveld en de meest recente kenmerkwaarde worden gebruikt. 

### <a name="change-behavior-during-a-solution-import"></a>Het gedrag tijdens het importeren van een oplossing wijzigen

Wanneer u een oplossing importeert die een datumveld met het gedrag **Gebruikersinstelling** bevat, kunt u de mogelijkheid hebben om het gedrag te wijzigen in **Alleen datum** of **Tijdzone-onafhankelijk**.  

### <a name="prevent-changing-behavior"></a>Wijziging van gedrag voorkomen

Als u een aangepast datumveld in een beheerde oplossing distribueert, kunt u voorkomen dat personen die uw oplossing gebruiken het gedrag wijzigen door de beheerde eigenschap **CanChangeDateTimeBehavior** in te stellen op **Onwaar**. Meer informatie: [Beheerde eigenschappen voor velden](set-managed-properties-metadata.md#field-managed-properties)
  
## <a name="use-cases"></a>Gebruiksgevallen

Bekijk de volgende gebruiksgevallen voor de gedragingen **Alleen datum** en **Tijdzone-onafhankelijk**.

### <a name="date-only-scenario-birthdays-and-anniversaries"></a>Scenario van Alleen datum: verjaardagen en jubilea

Het gedrag Alleen datum is geschikt voor gevallen waarin informatie over de tijd van de dag en de tijdzone niet nodig zijn, zoals verjaardagen en jubilea. Met deze selectie krijgen alle appgebruikers over de hele wereld exact dezelfde datumwaarde te zien.  
  
### <a name="time-zone-independent-scenario-hotel-check-in"></a>Scenario van Tijdzone-onafhankelijk: inchecken in hotel

U kunt dit gedrag gebruiken als tijdzonegegevens niet nodig zijn, zoals de inchecktijd van het hotel. Met deze selectie krijgen alle appgebruikers over de hele wereld exact dezelfde datum- en tijdwaarde te zien.  


## <a name="date-and-time-query-operators-not-supported-for-date-only-behavior"></a>Queryoperators voor datum en tijd worden niet ondersteund voor het gedrag Alleen datum  

De volgende aan datum en tijd gerelateerde queryoperators zijn ongeldig voor het gedrag **Alleen datum**. Er treedt een fout door een uitzondering vanwege een ongeldige operator op als een van deze operators wordt gebruikt in de query.  
  
- Ouder dan X minuten  
- Ouder dan X uur  
- Laatste X uren  
- Volgende X uren  

  
### <a name="see-also"></a>Zie ook

[Velden maken en bewerken](create-edit-fields.md)<br />
[Berekende velden definiëren om handmatige berekeningen te automatiseren](define-calculated-fields.md)<br />
[Beheerde eigenschappen voor velden](set-managed-properties-metadata.md#field-managed-properties)<br />
[Beheerde eigenschappen](solutions-overview.md#managed-properties)

