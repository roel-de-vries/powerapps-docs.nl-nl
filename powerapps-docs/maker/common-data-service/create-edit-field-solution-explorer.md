---
title: Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner | MicrosoftDocs
ms.custom: ''
ms.date: 05/18/2018
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
# <a name="create-and-edit-fields-for-common-data-service-for-apps-using-powerapps-solution-explorer"></a>Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner | MicrosoftDocs

De oplossingenverkenner viedt één manier om velden te maken en te bewerken voor Common Data Service voor Apps.

Met de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. <br />Zie voor meer informatie: 
- [Velden maken en bewerken voor Common Data Service voor Apps](create-edit-fields.md)
- [Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-portal](create-edit-field-portal.md)
  
## <a name="open-solution-explorer"></a>Open de oplossingenverkenner.

Een deel van de naam van een aangepast veld dat u maakt is het aanpassingsvoorvoegsel. Dit is ingesteld op basis van de oplossingsuitgever voor de oplossing waarin u werkt. Als het aanpassingsvoorvoegsel voor u van belang is, zorg er dan voor dat u werkt in een onbeheerde oplossing waarvoor het aanpassingsvoorvoegsel is wat u voor deze entiteit wilt. Meer informatie: [Het voorvoegsel voor de oplossingsuitgever wijzigen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="view-fields"></a>Weergavevelden

Vouw terwijl de oplossingenverkenner is geopend onder **Onderdelen** **Entiteiten** uit en selecteer de entiteit waarin u het veld wilt maken of bewerken.

![Weergave van de velden van de oplossingenverkenner](media/solution-explorer-fields-view.png)

U kunt de volgende weergaven selecteren: 

 |weergave|Beschrijving|
 |--|--|
 |**Alle**| Hiermee worden alle velden voor de entiteit weergegeven|
 |**Aangepast**|Hiermee worden alleen aangepaste velden voor de entiteit weergegeven|
 |**Aanpasbaar**|Hiermee worden alleen de velden weergegeven die kunnen worden bewerkt|

## <a name="create-a-field"></a>Een veld maken

Klik tijdens het weergeven van de velden op de opdrachtbalk op **Nieuw** waarmee het nieuwe veldformulier wordt geopend.  Sommige standaardentiteiten of aangepaste entiteiten die in een beheerde oplossing zijn opgenomen, staan u mogelijk niet toe om nieuwe velden toe te voegen.

> [!NOTE]
> Voor modelgestuurde apps kunt u ook een nieuw veld maken vanuit de formuliereneditor. Klik in de formuliereneditor onder **Veldverkenner** op **Nieuw veld** om een nieuw veld te maken. Meer informatie: [Een veld toevoegen aan een formulier](../model-driven-apps/add-field-form.md)

![Formulier Nieuw veld van de oplossingenverkenner](media/solution-explorer-new-field-form.png)

U moet gegevens invoeren en standaardwaarden bevestigen die voor de volgende eigenschappen zijn ingesteld voordat u opslaat.

|Eigenschap|Beschrijving|
|--|--|
|**Weergavenaam**|De tekst die voor het veld in de gebruikersinterface moet worden weergegeven. U kunt deze wijzigen nadat u hebt opgeslagen, maar met de waarde die u invoert wordt een waarde voor het veld **Naam** gegenereerd.|
|**Veldvereiste**|Of gegevens vereist zijn in het veld om de record op te slaan. Meer informatie: [Opties voor veldvereisten](#field-requirement-options)|
|**Name**|De unieke naam voor uw omgeving. Er wordt een naam voor u gegenereerd op basis van de weergavenaam die u hebt ingevoerd, maar u kunt deze bewerken voordat u opslaat. Zodra een veld is gemaakt, kan de naam niet worden gewijzigd omdat er mogelijk naar wordt verwezen in uw toepassingen of code. De naam wordt voorafgegaan door het aanpassingsvoorvoegsel voor de uitgever van de huidige oplossing.|
|**Kan worden doorzocht**|Stel dit in op **Nee** voor velden van de entiteit die u niet gebruikt.  Als een veld doorzoekbaar is, wordt het weergegeven in **Geavanceerd zoeken** in modelgestuurde apps en is het beschikbaar bij het aanpassen van weergaven. Door de selectie ervan op te heffen worden er minder opties weergegeven aan mensen die Geavanceerd zoeken gebruiken.|
|**Veldbeveiliging**|Of de gegevens in het veld op niveau hoger dan de entiteit zijn beveiligd. Meer informatie: [Beveiliging op veldniveau voor toegangsbeheer](/dynamics365/customer-engagement/admin/field-level-security).|
|**Controle**|Of gegevens voor dit veld worden gecontroleerd wanneer de entiteit voor controle is ingeschakeld. Meer informatie: [Gegevens en gebruikersactiviteiten controleren voor beveiliging en conformiteit](/customer-engagement/admin/audit-data-user-activity)|
|**Beschrijving**|Voer instructies voor de gebruiker in en geef aan waarvoor het veld bedoeld is. Deze beschrijvingen verschijnen als knopinfo voor gebruikers in modelgestuurde apps wanneer ze hun muis boven het label van het veld houden.|
|**Wordt weergegeven in algemeen filter in interactieve ervaring**|Meer informatie: [Dashboards voor interactieve ervaring configureren](/dynamics365/customer-engagement/customize/configure-interactive-experience-dashboards) |
|**Sorteerbaar in dashboard voor interactieve ervaring**|Meer informatie: [Dashboards voor interactieve ervaring configureren](/dynamics365/customer-engagement/customize/configure-interactive-experience-dashboards)|
|**Gegevenstype**|Hiermee wordt bepaald hoe waarden worden opgeslagen en hoe deze in sommige toepassingen worden opgemaakt. Zodra een veld is opgeslagen, kunt u het gegeventype niet veranderen omdat dat van invloed kan zijn op de gegevens in uw entiteit. Meer informatie: [Veldgegevenstypen](#field-data-types)|
|**Veldtype**|Of het veld **Eenvoudig**, **Berekend** of **Samengeteld** is. Meer informatie: [Veldtype](#field-type)|
|**Indeling**|Hoe het veld wordt opgemaakt. De beschikbare opmaakopties zijn afhankelijk van het **Gegevenstype**.|

U kunt aanvullende opties instellen afhankelijk van uw keuze van **Gegevenstype**. Meer informatie: [Veldgegevenstypen](#field-data-types)

## <a name="field-requirement-options"></a>Opties voor veldvereisten

Er zijn drie opties voor veldvereisten:
- **Optioneel**: de record kan worden opgeslagen, ook als dit veld geen gegevens bevat.
- **Onderneming aangeraden**: de record kan worden opgeslagen, ook als dit veld geen gegevens bevat. Naast het veld verschijnt echter een blauw symbool om aan te geven dat het belangrijk is.
- **Onderneming vereist**: de record kan niet worden opgeslagen, ook als dit veld geen gegevens bevat.
> [!NOTE]
> Wees voorzichtig wanneer u velden maakt die bedrijven vereisten. Mensen zullen weerstand voelen tegen het gebruik van de toepassing als ze geen records kunnen opslaan door een gebrek aan juiste informatie om in een vereist veld in te voeren. Mensen kunnen onjuiste gegevens invoeren om de records gewoon op te slaan en door te gaan met hun werk. U kunt bedrijfsregels of formulierscripts gebruiken om het vereistenniveau te wijzigeren terwijl de gegevens in de record veranderen als mensen ermee werken. Meer informatie:  [Bedrijfsregels en aanbevelingen maken om logica in een formulier toe te passen](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)

## <a name="field-data-types"></a>Veldgegevenstypen

Er zijn veel verschillende veldtypen, maar u kunt slechts een aantal ervan maken. Zie voor meer informatie over alle veldtypen [Veldtypen en veldgegevenstypen](types-of-fields.md).

Wanneer u een veld maakt, biedt **Gegevenstype** de volgende opties:

|Optie|Beschrijving|
|--|--|
|**Eén tekstregel**|Dit veld kan tot 4000 tekens tekst bevatten. U kunt een maximale lengte instellen die minder is dan dit. Dit veld heeft diverse indelingopties die de presentatie van de tekst zullen wijzigen.  Meer informatie: [Opties voor één tekstregel](#single-line-of-text-options)|
|**Optieset**|Hiermee wordt een lijst met opties weergegeven waarin één optie kan worden geselecteerd. Meer informatie: [Opties voor het veld Optieset](#option-set-field-options)|
|**Optieset voor meervoudige selectie**|Hiermee wordt een lijst met opties weergegeven waarin meerdere opties kunnen worden geselecteerd. Meer informatie: [Opties voor het veld Optieset](#option-set-field-options)|
|**Twee opties**|Hiermee wordt een lijst met opties weergegeven waarin een van de twee opties kan worden geselecteerd.<br /><br /> Twee optievelden bieden geen indelingsopties op veldniveau. Maar als u er een toevoegt aan het formulier, kunt u ervoor kiezen om ze als keuzerondje, selectievakje of selectielijst weer te geven.|
|**Afbeelding**|Hiermee wordt één afbeelding per record in de toepassing weergegeven. Elke entiteit kan één afbeeldingsveld hebben. Afbeeldingsvelden hebben altijd de naam `EntityImage`.|
|**Geheel getal**|In dit veld passen gehele getallen met een waarde tussen -2.147.483.648 en 2.147.483.647.  Dit veld heeft opties die veranderen afhankelijk van hoe het veld wordt weergegeven. Meer informatie: [Opties voor geheel getal](#whole-number-options)|
|**Getal met drijvende komma**|Maximaal 5 decimale precisiepunten kunnen worden gebruikt voor waarden tussen -100.000.000.000 en -100.000.000.000 in dit veld. U kunt het precisieniveau en de minimum- en maximumwaarden opgeven. Meer informatie: [Het juiste getaltype gebruiken](types-of-fields.md#using-the-right-type-of-number)|
|**Decimaal getal**|Maximaal 10 decimale precisiepunten kunnen worden gebruikt voor waarden tussen -100.000.000.000 en -100.000.000.000 in dit veld. U kunt het precisieniveau en de minimum- en maximumwaarden opgeven. Meer informatie: [Het juiste getaltype gebruiken](types-of-fields.md#using-the-right-type-of-number)|
|**Valuta**|In dit veld passen geldwaarden tussen -922.337.203.685.477 en 922.337.203.685.477. U kunt een precisieniveau instellen of ervoor kiezen de precisie in te stellen op een specifieke valuta of één standaardprecisie die door de organisatie wordt gebruikt. Meer informatie: [Valutavelden gebruiken](types-of-fields.md#using-currency-fields)|
|**Meerdere tekstregels**|Dit veld kan tot 1.048.576 tekens tekst bevatten. U kunt de maximale lengte instellen op een lagere waarde. Als u dit veld toevoegt aan een formulier van een modelgestuurde app, kunt u de afmetingen van het veld opgeven.|
|**Datum en tijd**|Gebruik deze velden om tijdwaarden op te slaan. U kunt waarden opslaan vanaf 1/1/1753 12:00 uur. Meer informatie: [Opties voor datum en tijd](#date-and-time-options)|
|**Opzoeken**|Een veld dat toestaat een verwijzingen naar één record of een specifiek type entiteit in te stellen. Sommige systeemopzoekvelden gedragen zich anders. Meer informatie: [Verschillende typen opzoekvelden](types-of-fields.md#different-types-of-lookups)|
|**Klanten**|Een opzoekveld dat u kunt gebruiken om een klant op te geven. Dit kan een account of contactpersoon zijn.  Meer informatie: [Verschillende typen opzoekvelden](types-of-fields.md#different-types-of-lookups)|

### <a name="single-line-of-text-options"></a>Opties voor één tekstregel

Het gegevenstype voor één tekstregel heeft de volgende indelingopties:

|Opmaak|Beschrijving|
|--|--|
|**Tekst**|Een tekstwaarde die in een tekstvak met één regel moet worden weergegeven.|
|**Tekstgebied**|Een tekstwaarde die in een tekstvak met meerdere regels moet worden weergegeven. Als u meer dan 4.000 tekens nodig hebt, gebruikt u het gegevenstype **Tekst met meerdere regels**.|
|**E-mail**|Een tekstwaarde die als een e-mailadres is gevalideerd en als mailto-koppeling wordt weergegeven in het veld. |
|**URL**|Een tekstwaarde die als een URL is gevalideerd en die als een koppeling om de URL te openen wordt weergegeven.|
|**Beurssymbool**|Een tekstwaarde voor een beurssymbool waarmee een koppeling wordt weergegeven die wordt geopend om een offerte voor het aandeelbeurssymbool weer te geven. |
|**Telefoon**|Een tekstwaarde die als een telefoonnummer is gevalideerd en die als koppeling wordt weergegeven om een telefoongesprek te starten via Skype. |

U kunt ook een **Maximale lengte** instellen zodat in het systeem geen tekstwaarden worden toegestaan die langer zijn dan u opgeeft.

### <a name="option-set-field-options"></a>Opties voor het veld Optieset

Velden die een set opties bieden, kunnen hun eigen set *lokale* opties bevatten of verwijzen naar een algemene set met *algemene* opties die door meerdere velden kunnen worden gebruikt.

Het gebruik van een algemene optieset is waardevol als u erachter komt dat u dezelfde set opties voor meerdere velden maakt. Met een algemene optieset hoeft u alleen de set opties op één plaats te beheren. 

Als u het gegevenstype **Optieset voor meervoudige selectie** of **Optieset** kiest, bevat de ontwerper van de oplossingenverkenner standaard de optie voor een lokale optieset.

![Een lokale optieset configureren](media/local-option-set-solution-explorer.png)

#### <a name="configure-local-options"></a>Lokale opties configureren

[!INCLUDE [cc_configure-option-set-options-solution-explorer](../../includes/cc_configure-option-set-options-solution-explorer.md)]

#### <a name="use-existing-option-set"></a>Bestaande optieset gebruiken

Als u **Bestaande optieset gebruiken** kiest, wordt in de ontwerper een lijst van bestaande *algemene optiesets* weergegeven en worden de knoppen **Bewerken** en **Nieuw** getoond om de algemene opties te configureren die in dit veld moeten worden gebruikt.

![Een algemene optieset configureren](media/global-option-set-solution-explorer.png)

U kunt algemene optiesets ook afzonderlijk configureren. Meer informatie: [Algemene optiesets maken en bewerken voor Common Data Service voor Apps (selectielijsten)](create-edit-global-option-sets.md)

> [!NOTE]
> Als u elke optieset als een algemene optieset definieert, wordt uw lijst met algemene optiesets steeds groter en kan deze lastig te beheren zijn. Als u weet dat de set met opties slechts op één plaats wordt gebruikt, gebruikt u een lokale optieset.


### <a name="whole-number-options"></a>Opties voor geheel getal

De velden voor geheel getal bevatten de volgende opmaakmogelijkheden:

|Opmaak|Beschrijving|
|--|--|
|**Geen**|Een nummerwaarde weergegeven in een tekstvak.|
|**Duur**|Een nummerwaarde weergegeven als een vervolgkeuzelijst die tijdsintervallen bevat. Een gebruiker kan een waarde uit de lijst selecteren of een geheel getal typen dat het aantal minuten is.|
|**Tijdzone**|Een nummerwaarde weergegeven als een vervolgkeuzelijst die een lijst met tijdzones.|
|**Taal**|Een getalwaarde weergegeven als een vervolgkeuzelijst die een lijst met talen bevat die zijn ingeschakeld voor de omgeving. Als er geen verschillende talen zijn ingeschakeld, is de basistaal de enige optie. De opgeslagen waarde is de LCID-waarde (id van landinstelling) voor de taal.|

U kunt de minimaal of maximaal toegestane waarden ook beperken.

### <a name="date-and-time-options"></a>Opties voor datum en tijd

De velden voor datum en tijd bevatten de volgende opties:

|Opmaak |Beschrijving|
|--|--|
|**Datum en tijd**|Een datum- en tijdwaarde.|
|**Alleen datum**|Een datum- en tijdwaarde die alleen een datum bevat. De tijdwaarde wordt opgeslagen als 12:00 uur (00:00:00) in het systeem.|

U kunt ook specifiek **Gedrag** instellen voor de velden van datum en tijd in **Geavanceerde opties**.

- **Gebruikersinstelling**: hiermee worden waarden weergegeven die zijn geconverteerd naar de lokale tijdzone van de huidige gebruiker. Dit is de standaardinstelling voor nieuwe velden.
- **Alleen datum**: dit gedrag is beschikbaar voor het type **Alleen datum**. Hiermee worden waarden weergegeven zonder tijdzoneconversie. Gebruik dit type voor gegevens zoals verjaardagen en jubilea.
- **Tijdzone-onafhankelijke**: hiermee worden waarden weergegeven zonder tijdzoneconversie.

Meer informatie: [Gedrag en indeling van het datum- en tijdveld](behavior-format-date-time-field.md)

## <a name="field-type"></a>Veldtype

U kunt het aangepaste veld **Veldtype** instellen als **Eenvoudig**, **Berekend** of **Samengeteld**. 

### <a name="simple"></a>Vereenvoudigd

Eenvoudig betekent dat het veld geen berekend of samengeteld veld is.

### <a name="calculated"></a>Berekend

Met een berekend veld kunt u een formule invoeren om een waarde aan het veld toe te wijzen. Deze gegevenstypen kunnen op berekende velden worden ingesteld: **Valuta**, **Datum en tijd**,  **Decimaal getal**,  **Optieset voor meervoudige selectie**, **Optieset**, **Eén tekstregel**, **Twee opties** en **Geheel getal**.

Meer informatie: [Berekende velden definiëren om handmatige berekeningen te automatiseren](define-calculated-fields.md)

### <a name="rollup"></a>Samengeteld

Met een samengeteld veld kunt u aggregatiefuncties instellen die periodiek worden uitgevoerd om een getalwaarde voor het veld in te stellen. Deze gegevenstypen kunnen op berekende velden worden ingesteld: **Valuta**, **Datum en tijd**, **Decimaal getal** en **Geheel getal**.

Meer informatie: [Samengetelde velden definiëren waarmee waarden worden samengevoegd](define-rollup-fields.md)

## <a name="save-new-field"></a>Nieuw veld opslaan

Zodra u het veld hebt geconfigureerd, gebruikt u een van de drie opdrachten op de opdrachtbalk:

|Opdracht|Beschrijving|
|--|--|
|**Opslaan**|Sla de velddefinitie op en laat het formuliervenster geopend.|
|**Opslaan en sluiten**|Sla de velddefinitie op en sluit het venster.|
|**Opslaan en nieuwe maken**|Sla de velddefinitie op en open een nieuw formulier om een nieuw veld te maken.|


## <a name="edit-a-field"></a>Een veld bewerken 

Klik tijdens het [weergeven van velden](#view-fields) op het veld dat u wilt bewerken. Sommige standaardvelden of aangepaste velden die in een beheerde oplossing zijn opgenomen, staan u mogelijk niet toe om deze te bewerken.

> [!NOTE]
> U kunt bij het bewerken van een formulier voor elk veld dat aan het formulier is toegevoegd, dubbelklikken op het veld om de **Veldeigenschappen** weer te geven. Klik op het tabblad **Details** op **Bewerken**. Meer informatie: [Een veld toevoegen aan een formulier](../model-driven-apps/add-field-form.md)

Nadat u wijzigingen in een veld hebt aangebracht, moet u aanpassingen publiceren. 

- Als u uw wijzigingen voor een entiteit wilt wijzigen, selecteert u onder **Onderdelen** **Entiteiten** en selecteert u de entiteit waaraan u wijzigingen hebt aangebracht. Selecteer op de werkbalk **Acties** de optie **Publiceren**.  
  
- Als u alle wijzigingen die u in meerdere entiteiten of onderdelen hebt aangebracht, wilt publiceren, selecteert u op de werkbalk **Acties** de optie **Alle aanpassingen publiceren**.  
  
> [!NOTE]
>  Het installeren van een oplossing of publiceren van aanpassingen kan de normale werking van het systeem onderbreken. We adviseren u om het publiceren van een oplossing te plannen wanneer dit minimale gevolgen heeft voor gebruikers.  

### <a name="edit-multiple-fields"></a>Meerdere velden bewerken

Als u een of meer velden wilt bewerken, selecteert u het veld of de velden (met de toets Shift ingedrukt) die u wilt wijzigen, en selecteert u op de werkbalk **Acties** de optie **Bewerken**. 
  
Als u meerdere velden selecteert om te bewerken, wordt het dialoogvenster **Meerdere velden bewerken** weergegeven. U kunt **Veldvereiste**, **Kan worden doorzocht** en **Controle** bewerken. 

## <a name="delete-a-field"></a>Een veld verwijderen

Met de beveiligsrol van systeembeheerder kunt u alle aangepaste velden verwijderen die geen deel uitmaken van een beheerde oplossing. Wanneer u een veld verwijdert, gaan de opgeslagen gegevens in het veld verloren. De enige manier om gegevens te herstellen uit een veld dat is verwijderd, is door de database te herstellen vanuit een punt voordat het veld werd verwijderd.

> [!NOTE]
> Voordat u een aangepast veld kunt verwijderen, moet u afhankelijkheden verwijderen die in andere oplossingsonderdelen aanwezig kunnen zijn. 

1. Selecteer tijdens het [weergeven van velden](#view-fields) een aangepast veld dat in de lijst kan worden verwijderd en klik op de knop ![Verwijderen](../model-driven-apps/media/delete.gif) op de opdrachtbalk.
2. Selecteer **Verwijderen** in het dialoogvenster **Verwijdering bevestigen**.

> [!TIP]
> U kunt meerdere aangepaste velden selecteren die in één bewerking moeten worden verwijderd.

### <a name="check-field-dependencies"></a>Veldafhankelijkheden controleren 

Selecteer het veld in de lijst. Selecteer in het menu **Meer acties** **Afhankelijkheden weergeven**.

![Afhankelijkheden voor veld weergeven](media/check-field-dependencies.png)

Afhankelijkheden zijn alle gerelateerde gebruiksmogelijkheden van het veld waarmee wordt voorkomen dat het wordt verwijderd. Als het veld bijvoorbeeld in een formulier of een weergave wordt gebruikt, moet u eerst referenties naar het veld in deze oplossingsonderdelen verwijderen.  
  
Als u een opzoekveld verwijdert, wordt de 1:N-entiteitsrelatie voor dat veld automatisch verwijderd.  

## <a name="ime-mode"></a>IME-modus

Alle velden die directe tekstinvoer bieden, hebben een IME-modus. De IME (Input Method Editor) wordt gebruikt voor Oost-Aziatische talen, zoals Japans. Met IME's kan de gebruiker de duizenden verschillende tekens invoeren die in Oost-Aziatische talen worden gebruikt met een standaardtoetsenbord met 101 toetsen.


### <a name="see-also"></a>Zie ook  
[Velden maken en bewerken voor Common Data Service voor Apps](create-edit-fields.md)<br />
[Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-portal](create-edit-field-portal.md)<br />
[Typen velden en veldgegevenstypen](types-of-fields.md)<br />
[Berekende velden definiëren om handmatige berekeningen te automatiseren](define-calculated-fields.md)<br />
[Samengetelde velden definiëren voor het samenvoegen van waarden](define-rollup-fields.md)<br />
[Gedrag en indeling van het datum- en tijdveld](behavior-format-date-time-field.md)
