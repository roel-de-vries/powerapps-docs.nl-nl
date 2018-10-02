---
title: '1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken met de oplossingenverkenner | MicrosoftDocs'
description: Meer informatie over het maken van één-op-veel- of veel-op-één-entiteitsrelaties met de PowerApps-oplossingenverkenner
ms.custom: ''
ms.date: 05/27/2018
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

# <a name="create-and-edit-1n-one-to-many-or-n1-many-to-one-entity-relationships-using-solution-explorer"></a>1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken met de oplossingenverkenner 

De oplossingenverkenner biedt één manier om 1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) te maken en te bewerken voor Common Data Service voor Apps.

Met de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. Zie voor meer informatie: 
- [Maak 1:N (een-op-veel) of N:1 (veel-op-een) relaties](create-edit-1n-relationships.md)
- [1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken in de PowerApps-portal](create-edit-1n-relationships-portal.md)
  
## <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

Een deel van de naam van een aangepaste relatie die u maakt is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel is wat u voor deze entiteit wilt. Meer informatie: [Het voorvoegsel voor de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entity-relationships"></a>Entiteitsrelaties weergeven

Vouw in de oplossingenverkenner **Entiteiten** uit en selecteer een entiteit. Selecteer binnen die entiteit **1:N-relaties** of **N:1-relaties**.

![Entiteitsrelaties weergeven](media/view-1n-entity-relationships-solution-explorer.png)

## <a name="create-relationships"></a>Relaties maken

Selecteer tijdens [het weergeven van entiteitsrelaties](#view-entity-relationships) **Nieuwe één-op-veel-relatie** of **Nieuwe veel-op-één-relatie** op de opdrachtbalk.

> [!NOTE]
> Als de opdrachten niet beschikbaar zijn, komt de entiteit niet in aanmerking om een aangepaste relatie te maken.

Met beide opties wordt een formulier geopend zoals het volgende. Het verschil is of het veld **Primaire entiteit** of **Gerelateerde entiteit** wordt ingesteld.

![Formulier Nieuwe Eén-op-veel-relatie](media/new-1n-entity-relationship-form-solution-explorer.png)

- Met **1:N-relatie** wordt de **Primaire entiteit** ingesteld op de huidige entiteit
- Met **N:1-relatie** wordt de **Gerelateerde entiteit** ingesteld op de huidige entiteit

De volgende velden moeten worden ingesteld om de entiteitsrelatie te kunnen opslaan:

|Vereist veld|Beschrijving|
|--|--|
|**Primaire entiteit**|Deze entiteit is het doeltype voor het opzoekveld dat in de gerelateerde entiteit wordt gemaakt.|
|**Gerelateerde entiteit**|Aan deze entiteit wordt een opzoekveld toegevoegd om de entiteitsrecords te koppelen aan de record van de primaire entiteit.|
|**Name**|De naam van de relatie. Er wordt een waarde gegenereerd op basis van de waarden voor primaire en gerelateerde entiteit. Dit veld wordt voorafgegaan door het aanpassingsvoorvoegsel van de oplossingsuitgever.|
|**Weergavenaam opzoekveld**|De lokaliseerbare tekst voor het opzoekveld dat voor de gerelateerde entiteit wordt gemaakt. Dit is meestal hetzelfde is als de weergavenaam voor de primaire entiteit. <br /> Dit kan later worden gewijzigd.|
|**Opzoekveldnaam**|De naam van het opzoekveld dat in de gerelateerde entiteit wordt gemaakt. Er wordt een waarde gegenereerd op basis van de **Weergavenaam opzoekveld**. Dit veld wordt voorafgegaan door het aanpassingsvoorvoegsel van de oplossingsuitgever.|

U kunt klikken op de ![knop Entiteitsrelatie opslaan](media/save-entity-icon-solution-explorer.png) om de entiteit op te slaan en verder te gaan met bewerken. Meer informatie: [Relaties bewerken](#edit-relationships)

> [!NOTE]
> Als de waarden van **Naam** of **Opzoekveldnaam** al in het systeem bestaan, ontvangt u een foutbericht wanneer u opslaat. Bewerk de waarden zodat deze uniek zijn en probeer het opnieuw.

## <a name="edit-relationships"></a>Relaties bewerken

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-entity-relationships) de entiteit die u wilt bewerken. De volgende entiteitsrelatie-eigenschappen kunnen worden bewerkt nadat de relatie is gemaakt.

> [!NOTE]
> Uitgevers van een beheerde oplossing kunnen voorkomen dat sommige aanpassingen van relaties worden gemaakt die deel uitmaken van hun oplossing.

### <a name="entity-relationship-properties"></a>Eigenschappen van entiteitsrelaties

Deze eigenschappen hebben betrekking op de relatie.

|Veld|Beschrijving|
|--|--|
|**Kan worden doorzocht**|Of deze relatie in Geavanceerd zoeken zichtbaar moet zijn in modelgestuurde apps. Selecteer **Nee** als dit een relatie is die niet van belang is voor uw bedrijf.|
|**Hiërarchisch**|Deze optie wordt alleen ingeschakeld voor zelfreferentiële relaties. Of rekening moet worden gehouden met de entiteit om een hiërarchie voor de entiteit te definiëren.<br />**Belangrijk**: zodra u deze samengetelde velden voor eigenschappen instelt, kunnen processen en weergaven zo worden geconfigureerd dat ze afhankelijk zijn van deze eigenschap. Als u deze waarde later wijzigt, werken deze mogelijkheden die afhankelijk zijn van de hiërarchie niet. <br />Meer informatie: [Hiërarchisch gerelateerde gegevens definiëren en opvragen](define-query-hierarchical-data.md)|

### <a name="lookup-field"></a>Opzoekveld

Dit zijn de eigenschappen van het opzoekveld dat in de gerelateerde entiteit is gemaakt. De eigenschappen kunnen hier worden bewerkt of door het opzoekveld rechtstreeks te bewerken. Sommige veldeigenschappen zijn niet bewerkbaar vanuit de relatie. Meer informatie: [Een veld bewerken](create-edit-field-solution-explorer.md#edit-a-field)

|Veld|Beschrijving|
|--|--|
|**Weergavenaam**|De lokaliseerbare tekst voor het opzoekveld dat voor de gerelateerde entiteit wordt gemaakt.|
|**Veldvereiste**|Of het veld gegevens moet hebben voordat een formulier in een modelgestuurde app kan worden opgeslagen. Meer informatie: [Opties voor veldvereisten](create-edit-field-solution-explorer.md#field-requirement-options)|
|**Beschrijving**|Voer instructies voor de gebruiker in en geef aan waarvoor het veld bedoeld is. Deze beschrijvingen verschijnen als knopinfo voor gebruikers in modelgestuurde apps wanneer ze hun muis boven het label van het veld houden.|

### <a name="navigation-pane-item-for-primary-entity"></a>Navigatiedeelvensteritem voor primaire entiteit

U kunt navigeren vanuit de primaire entiteit om gerelateerde records te bekijken. Deze gegevens worden gebruikt door modelgestuurde apps om te controleren hoe de records van de gerelateerde entiteit worden weergegeven. Deze instellingen kunnen ook worden bewerkt met de formuliereneditor.

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

### <a name="relationship-behavior"></a>Relatiegedrag

Dit is waar u standaardgedragingen voor gerelateerde entiteiten kunt definiëren. Deze informatie is belangrijk omdat het u helpt gegevensintegriteit te waarborgen en u er bedrijfsprocessen voor uw bedrijf mee kunt automatiseren.

Laten we een voorbeeld bekijken.  
  
Stel dat u een nieuwe verkoper hebt en u die verkoper een aantal bestaande verkoopkansen wilt toewijzen dat momenteel aan een andere verkoper is toegewezen. Aan elk verkoopkansrecord kan een bepaald aantal taakactiviteiten worden gekoppeld. U kunt de actieve verkoopkansen die u zoekt gemakkelijk opnieuw toewijzen aan de nieuwe verkoper. Maar wat moet er met de taakactiviteiten gebeuren die aan de kansen zijn gerelateerd? Wilt u elke taak openen en besluiten of die ook aan de nieuwe verkoper moet worden toegewezen? Waarschijnlijk niet. In plaats daarvan kunt u de relatie automatisch bepaalde standaardregels laten instellen. Deze regels zijn alleen van toepassing op taakrecords die aan de verkoopkansen zijn gekoppeld die u opnieuw toewijst. U hebt de volgende opties:  
  
- Alle actieve taken opnieuw toewijzen.  
- Alle taken opnieuw toewijzen. 
- Geen taken opnieuw toewijzen.  
- Alle huidig toegewezen taken opnieuw toewijzen aan de vorige eigenaar van de verkoopkans.  
  
Met de relatie kan worden bepaald hoe bewerkingen op een record voor de trapsgewijze ordening van de primaire entiteitrecord naar verwante entiteitsrecords omlaag worden uitgevoerd.   

Er zijn verschillende soorten gedragingen die kunnen worden toegepast bij bepaalde acties.

#### <a name="behaviors"></a>Gedragingen

Dit zijn de beschikbare gedragingen die moeten worden geconfigureerd.

|Gedrag|Beschrijving|
|--|--|
|**Actieve items trapsgewijs ordenen**|De actie op alle actieve gerelateerde entiteitsrecords uitvoeren.|
|**Alle items trapsgewijs ordenen**|De actie op alle gerelateerde entiteitsrecords uitvoeren.|
|**Geen items trapsgewijs ordenen**|Niets doen.|
|**Koppeling verwijderen**|Verwijder de opzoekwaarde voor alle gerelateerde records.|
|**Beperken**|Voorkom dat de primaire entiteit wordt verwijderd wanneer er gerelateerde records bestaan.|
|**Items waarvan gebruiker eigenaar is trapsgewijs ordenen**|De actie op alle verwante entiteitsrecords uitvoeren waarvan de eigenaar dezelfde is als die van de primaire entiteitrecord.|

#### <a name="actions"></a>Acties

Dit zijn de acties die bepaalde gedragingen kunnen activeren:

|Veld|Beschrijving|Opties|
|--|--|--|
|**Toewijzen**|Wat moet er gebeuren als de primaire entiteit aan iemand anders wordt toegewezen?|Alle it. trapsgewijs<br />Act. it. trapsgewijs<br />Gebruiker-eigenaar trapsgewijs<br />Geen it. trapsgewijs|
|**Nieuw bovenliggend element maken**|Wat moet er gebeuren als de opzoekwaarde van een gerelateerde entiteit in een bovenliggende relatie wordt veranderd?<br />Meer informatie: [Bovenliggende entiteitsrelaties](#parental-entity-relationships)|Alle it. trapsgewijs<br />Act. it. trapsgewijs<br />Gebruiker-eigenaar trapsgewijs<br />Geen it. trapsgewijs|
|**Delen**|Wat moet er gebeuren als de primaire entiteitrecord wordt gedeeld?|Alle it. trapsgewijs<br />Act. it. trapsgewijs<br />Gebruiker-eigenaar trapsgewijs<br />Geen it. trapsgewijs|
|**Verwijderen**|Wat moet er gebeuren als de primaire entiteit wordt verwijderd?|Alle it. trapsgewijs<br />koppeling verwijderen<br />Beperken|
|**Delen opheffen**|Wat moet er gebeuren als het delen van een primaire entiteit ongedaan wordt gemaakt?|Alle it. trapsgewijs<br />Act. it. trapsgewijs<br />Gebruiker-eigenaar trapsgewijs<br />Geen it. trapsgewijs|
|**Samenvoegen**|Wat moet er gebeuren als een primaire entiteit wordt samengevoegd?|Alle it. trapsgewijs<br />Geen it. trapsgewijs|
|**Samenvouwweergave**|Wat is het gewenste gedrag van de samenvouwweergave die aan deze relatie is gekoppeld? |Alle it. trapsgewijs<br />Act. it. trapsgewijs<br />Gebruiker-eigenaar trapsgewijs<br />Geen it. trapsgewijs|

<!-- TODO: I find no official docs related to rollup views, but plenty of hits online: https://www.google.com/search?q=Dynamics+365++%27rollup+view%27 -->



#### <a name="type-of-behavior-options"></a>Opties voor type gedrag

Gebruik het veld **Type gedrag** om te kiezen tussen een set standaardgedragingen en of u ze onafhankelijk wilt configureren. 

|Optie|Beschrijving|
|--|--|
|**Bovenliggend**|**Toewijzen**: Alle items trapsgewijs ordenen<br />**Nieuw bovenliggend element**: Alle items trapsgewijs ordenen<br />**Delen**: Alle items trapsgewijs ordenen<br />**Verwijderen**: Alle items trapsgewijs ordenen<br />**Delen ongedaan maken**: Alle items trapsgewijs ordenen<br />**Samenvoegen**: Alle items trapsgewijs ordenen<br />**Samenvouwweergave**: Geen items trapsgewijs ordenen \| Alle items trapsgewijs ordenen<br />|
|**Referentieel**|**Toewijzen**: Geen items trapsgewijs ordenen<br />**Nieuw bovenliggend element**: Geen items trapsgewijs ordenen<br />**Delen**: Geen items trapsgewijs ordenen<br />**Verwijderen**: Koppeling verwijderen<br />**Delen ongedaan maken**: Geen items trapsgewijs ordenen<br />**Samenvoegen**: Alle items trapsgewijs ordenen<br />**Samenvouwweergave**: Geen items trapsgewijs ordenen \| Alle items trapsgewijs ordenen<br />|
|**Referentieel, verwijderen beperken**|**Toewijzen**: Geen items trapsgewijs ordenen<br />**Nieuw bovenliggend element**: Geen items trapsgewijs ordenen<br />**Delen**: Geen items trapsgewijs ordenen<br />**Verwijderen**: Beperken<br />**Delen ongedaan maken**: Geen items trapsgewijs ordenen<br />**Samenvoegen**: Alle items trapsgewijs ordenen<br />**Samenvouwweergave**: Geen items trapsgewijs ordenen \| Alle items trapsgewijs ordenen<br />|
|**Configureerbare trapsgewijze ordening**|U kunt het gewenste gedrag configureren voor elke bewerking, afhankelijk van de beschikbare opties|

> [!NOTE]
> Mogelijk kunt u de optie **Bovenliggend** niet kiezen als een van de entiteiten al deelneemt aan een bovenliggende entiteitsrelatie. Meer informatie: [Bovenliggende entiteitsrelaties](#parental-entity-relationships)
> 
> Als u **Configureerbare trapsgewijze ordening** gebruikt om de gedragingen voor de acties zodanig in te stellen dat deze overeenkomen met de gedragingen voor de acties die aan een ander **Type gedrag** zijn gekoppeld, wordt bij het opslaan van de relatie **Type gedrag** automatisch ingesteld op het overeenkomstige type.  



## <a name="delete-relationships"></a>Relaties verwijderen

Selecteer tijdens het [weergeven van entiteitsrelaties](#view-entity-relationships) de entiteitsrelatie die u wilt verwijderen en kik op de opdracht ![Verwijderen](media/delete.gif).

Als de relatie wordt verwijderd, wordt het opzoekveld in de gerelateerde entiteit verwijderd.

> [!NOTE]
> U kunt geen relatie verwijderen die afhankelijkheden bevat. Als u bijvoorbeeld het opzoekveld hebt toegevoegd aan een formulier voor de gerelateerde entiteit, moet u het veld uit het formulier verwijderen voordat u de relatie verwijdert.

## <a name="parental-entity-relationships"></a>Bovenliggende entiteitsrelaties

Elk paar entiteiten dat in aanmerking komt voor een 1:N-relatie kan meerdere onderlinge 1:N-relaties hebben. Toch kan gewoonlijk slechts één van deze relaties als een bovenliggende entiteitsrelatie worden beschouwd.

Een bovenliggende entiteitsrelatie is elke 1:N-entiteitsrelatie waarbij een van de trapsgewijze opties in de kolom **Bovenliggend** van de volgende tabel true is.

|Actie|bovenliggend|Not Parental|  
|------------|--------------|------------------|  
|**Toewijzen**|Alle it. trapsgewijs<br />Gebruiker-eigenaar trapsgewijs<br />Act. it. trapsgewijs|Geen it. trapsgewijs|  
|**Verwijderen**|Alle it. trapsgewijs|RemoveLink<br />Beperken|  
|**Nieuw bovenliggend element maken**|Alle it. trapsgewijs<br />Gebruiker-eigenaar trapsgewijs<br />Act. it. trapsgewijs|Geen it. trapsgewijs|  
|**Delen**|Alle it. trapsgewijs<br />Gebruiker-eigenaar trapsgewijs<br />Act. it. trapsgewijs|Geen it. trapsgewijs|  
|**Delen opheffen**|Alle it. trapsgewijs<br />Gebruiker-eigenaar trapsgewijs<br />Act. it. trapsgewijs|Geen it. trapsgewijs|  

Als u bijvoorbeeld een nieuwe aangepaste entiteit maakt en een 1:N-entiteitsrelatie toevoegt met de accountentiteit waarbij uw aangepaste entiteit de gerelateerde entiteit is, kunt u de acties voor die entiteitsrelatie configureren voor het gebruik van opties in de kolom **Bovenliggend**. Als u later nog een 1:N-entiteitsrelatie toevoegt met uw aangepaste entiteit als verwijzende entiteit kunt u alleen de acties configureren om de opties in de kolom **Niet bovenliggend** te gebruiken.

Meestal betekent dit dat voor elk entiteitpaar er slechts één bovenliggende relatie is. Er zijn enkele situaties waarbij het opzoekveld in de gerelateerde entiteit een relatie aan meer dan één entiteitstype kan toestaan.

Als bijvoorbeeld een entiteit een opzoekveld Klant heeft dat naar een contactpersoon- of accountentiteit kan verwijzen. Er zijn twee afzonderlijke bovenliggende 1:N-entiteitsrelaties.

Elke activiteitsentiteit heeft een soortgelijke set bovenliggende entiteitsrelaties voor entiteiten die kunnen worden gekoppeld met het opzoekveld Betreft.

<a name="BKMK_RelationshipBehaviorLimitations"></a>   

### <a name="limitations-on-behaviors-you-can-set"></a>De beperkingen voor gedrag dat u kunt instellen
  
Vanwege bovenliggende relaties zijn er enkele beperkingen waarmee u rekening moet houden als u entiteitsrelaties definieert.  
  
- Een aangepaste entiteit kan niet de primaire entiteit zijn in een relatie met een gerelateerde systeementiteit die trapsgewijs is geordend. Dit betekent dat u geen relatie kunt hebben met een actie die is ingesteld op **Alle items trapsgewijs rangschikken**, **Actieve items trapsgewijs rangschikken** of **Gebruiker-eigenaar trapsgewijs rangschikken** tussen een primaire aangepaste entiteit en een gerelateerde systeementiteit.  
- Nieuwe relaties kunnen geen acties hebben die zijn ingesteld op **Alle items trapsgewijs**, **Actieve items trapsgewijs** of **Gebruiker-eigenaar trapsgewijs** als de gerelateerde entiteit in die relatie al bestaat als een gerelateerde entiteit in een andere relatie met acties die zijn ingesteld op **Alle items trapsgewijs**, **Actieve items trapsgewijs** of **Gebruiker-eigenaar trapsgewijs**. Op deze manier worden relaties voorkomen die relaties veroorzaken met meerdere bovenliggende elementen.  

### <a name="see-also"></a>Zie ook

[Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md)<br />
[1:N- (één-op-veel) of N:1-relaties (veel-op-één) maken en bewerken](create-edit-1n-relationships.md)<br />
[1:N- (één-op-veel) of N:1-entiteitsrelaties (veel-op-één) maken en bewerken in de PowerApps-portal](create-edit-1n-relationships-portal.md)<br />
[Maak N:N-relaties (veel-op-veel)](create-edit-nn-relationships.md)

