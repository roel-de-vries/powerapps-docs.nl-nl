---
title: Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-portal | MicrosoftDocs
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
# <a name="create-and-edit-fields-for-common-data-service-for-apps-using-powerapps-portal"></a>Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-portal

De [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) biedt een eenvoudige manier om entiteitsvelden te maken en te bewerken voor Common Data Service voor Apps.

Met de portal wordt de configuratie van de meest gebruikte opties ingeschakeld, maar bepaalde opties kunnen alleen worden ingesteld met oplossingenverkenner. <br />Zie voor meer informatie: 
- [Velden maken en bewerken voor Common Data Service voor Apps](create-edit-fields.md)
- [Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner | MicrosoftDocs](create-edit-field-solution-explorer.md)

## <a name="view-fields"></a>Weergavevelden

1. Selecteer via de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de ontwerpmodus **Modelgestuurd** of **Canvas**.
2. Selecteer **Gegevens** > **Entiteiten** en selecteer de entiteit met de velden die u wilt weergeven.
3. U kunt terwijl het tabblad **Velden** is geselecteerd de volgende weergaven selecteren: 

 |weergave|Beschrijving|
 |--|--|
 |**Alle**| Hiermee worden alle velden voor de entiteit weergegeven|
 |**Aangepast**|Hiermee worden alleen aangepaste velden voor de entiteit weergegeven|
 |**Standaard**|Hiermee worden alleen de standaardvelden voor de entiteit weergegeven|
<!-- TODO: What is the actual difference between All and Default? -->

## <a name="create-a-field"></a>Een veld maken

Klik tijdens het weergeven van velden op de opdrachtbalk op **Veld toevoegen** in het paneel **Veldeigenschappen**.

![Veldeigenschappen](media/field-properties.png)


Aanvankelijk zijn er slechts drie veldeigenschappen beschikbaar:

 |Eigenschap|Beschrijving|
 |--|--|
 |**Weergavenaam**|De tekst die voor het veld in de gebruikersinterface moet worden weergegeven.|
 |**Name**|De unieke naam voor uw omgeving. Er wordt een naam voor u gegenereerd op basis van de weergavenaam die u hebt ingevoerd, maar u kunt deze bewerken voordat u opslaat. Zodra een veld is gemaakt, kan de naam niet worden gewijzigd omdat er mogelijk naar wordt verwezen in uw toepassingen of code. De naam wordt voorafgegaan door het aanpassingsvoorvoegsel voor uw **CDS-standaarduitgever**.|
 |**Gegevenstype**|Hiermee wordt bepaald hoe waarden worden opgeslagen en hoe deze in sommige toepassingen worden opgemaakt. Zodra een veld is opgeslagen, kunt u het gegeventype niet veranderen omdat dat van invloed kan zijn op de gegevens in uw entiteit.|

U kunt aanvullende opties instellen afhankelijk van uw keuze van **Gegevenstype**.

## <a name="field-data-types"></a>Veldgegevenstypen

Er zijn veel verschillende veldtypen, maar u kunt slechts een aantal ervan maken. Zie voor meer informatie over alle veldtypen [Veldtypen en veldgegevenstypen](types-of-fields.md).

Wanneer u een veld maakt, biedt **Gegevenstype** de volgende opties:

### <a name="text"></a>Tekst 

De standaardtekstvelden kunnen maximaal 4.000 tekens bevatten. De standaard [Maximale lengte](#max-length) is ingesteld op een lagere waarde die u kunt aanpassen.

|Gegevenstype|Beschrijving|
|--|--|
|**Tekst**|Een tekstwaarde die in een tekstvak met één regel moet worden weergegeven.|
|**Tekstgebied**|Een tekstwaarde die in een tekstvak met meerdere regels moet worden weergegeven. Als u meer dan 4.000 tekens nodig hebt, gebruikt u het gegevenstype [Tekst met meerdere regels](#multi-line-field).|
|**E-mail**|Een tekstwaarde die als een e-mailadres is gevalideerd en als mailto-koppeling wordt weergegeven in het veld. |
|**URL**|Een tekstwaarde die als een URL is gevalideerd en die als een koppeling om de URL te openen wordt weergegeven.|
|**Beurssymbool**|Een tekstwaarde voor een beurssymbool waarmee een koppeling wordt weergegeven die wordt geopend om een offerte voor het aandeelbeurssymbool weer te geven. |
|**Telefoon**|Een tekstwaarde die als een telefoonnummer is gevalideerd en die als koppeling wordt weergegeven om een telefoongesprek te starten via Skype. |

#### <a name="max-length"></a>Max. lengte

Velden die tekst bevatten, hebben een absoluut maximum afhankelijk van het type. Met de optie **Max. lengte** wordt een waarde ingesteld die lager is dan het maximum dat specifiek geldt voor uw omgeving. U kunt deze maximale lengte vergroten, maar u dient deze niet in te korten als u gegevens hebt in het systeem die de lagere waarde overschrijden.

### <a name="whole-number"></a>Geheel getal

Deze velden bevatten gegevens als een getal, maar bevatten verschillende presentatie- en validatieopties.

|Gegevenstype|Beschrijving|
|--|--|
|**Geheel getal**|Een nummerwaarde weergegeven in een tekstvak.|
|**Duur**|Een nummerwaarde weergegeven als een vervolgkeuzelijst die tijdsintervallen bevat. Een gebruiker kan een waarde uit de lijst selecteren of een geheel getal typen dat het aantal minuten is.|
|**Tijdzone**|Een nummerwaarde weergegeven als een vervolgkeuzelijst die een lijst met tijdzones.|
|**Taal**|Een getalwaarde weergegeven als een vervolgkeuzelijst die een lijst met talen bevat die zijn ingeschakeld voor de omgeving. Als er geen verschillende talen zijn ingeschakeld, is de basistaal de enige optie. De opgeslagen waarde is de LCID-waarde (id van landinstelling) voor de taal.|


### <a name="date-time"></a>Datum/tijd

Gebruik deze velden om tijdwaarden op te slaan. U kunt waarden opslaan vanaf 1/1/1753 12:00 uur.

|Gegevenstype|Beschrijving|
|--|--|
|**Datum en tijd**|Een datum- en tijdwaarde.|
|**Alleen datum**|Een datum- en tijdwaarde die alleen een datum bevat. De tijdwaarde wordt opgeslagen als 12:00 uur (00:00:00) in het systeem.|

U kunt ook specifiek **Gedrag** instellen voor de velden van datum en tijd in **Geavanceerde opties**.

- **Gebruikersinstelling**: hiermee worden waarden weergegeven die zijn geconverteerd naar de lokale tijdzone van de huidige gebruiker. Dit is de standaardinstelling voor nieuwe velden.
- **Alleen datum**: dit gedrag is beschikbaar voor het type **Alleen datum**. Hiermee worden waarden weergegeven zonder tijdzoneconversie. Gebruik dit type voor gegevens zoals verjaardagen en jubilea.
- **Tijdzone-onafhankelijke**: hiermee worden waarden weergegeven zonder tijdzoneconversie.

Meer informatie: [Gedrag en indeling van het datum- en tijdveld](behavior-format-date-time-field.md)

### <a name="other-data-types"></a>Overige gegevenstypen

|Gegevenstype|Beschrijving|
|--|--|
|**Valuta**|Een geldwaarde voor elke valuta die voor de omgeving is geconfigureerd. U kunt een precisieniveau instellen of ervoor kiezen de precisie in te stellen op een specifieke valuta of één standaardprecisie die door de organisatie wordt gebruikt. Meer informatie: [Valuatavelden gebruiken](types-of-fields.md#using-currency-fields)|
|**Decimaal getal**| Een decimale waarde met een maximale decimale nauwkeurigheid van 10 plaatsen achter de komma. Meer informatie: [Het juiste getaltype gebruiken](types-of-fields.md#using-the-right-type-of-number)|
|**Getal met drijvende komma**|Een getal met drijvende komma met een maximale nauwkeurigheid van 5 plaatsen. Meer informatie: [Het juiste getaltype gebruiken](types-of-fields.md#using-the-right-type-of-number)|
|**Afbeelding**|Hiermee wordt één afbeelding per record in de toepassing weergegeven. Elke entiteit kan één afbeeldingsveld hebben. **Naam** die u invoert bij het maken van een afbeeldingsveld wordt genegeerd. Afbeeldingsvelden hebben altijd de naam.|
|**Optieset voor meervoudige selectie**|Hiermee wordt een lijst met opties weergegeven waarin meerdere opties kunnen worden geselecteerd.|
|<a name="multi-line-field"></a> **Tekst van meerdere regels**|Een tekstwaarde die in een tekstvak met meerdere regels moet worden weergegeven. Beperkt tot maximaal 1.048.576 tekens. U kunt ook een lagere [Max. lengte](#max-length) instellen. |
|**Optieset**|Hiermee wordt een lijst met opties weergegeven waarin slechts één optie kan worden geselecteerd.|
|**Twee opties**|Hiermee worden twee opties weergegeven waarbij slechts één optie kan worden geselecteerd. U kiest welke labels voor elke optie worden weergegeven. De standaardwaarden zijn **Ja** en **Nee**.|

## <a name="save-new-field"></a>Nieuw veld opslaan

Zodra u de eigenschappen **Weergavenaam**, **Naam** en **Gegevenstype** hebt ingesteld, kunt u klikken op **Gereed** om het paneel **Veldeigenschappen** te sluiten. 

U kunt doorgaan om de entiteit te bewerken en extra velden toe te voegen of terugkeren en dit veld verder bewerken. De velden worden pas gemaakt als u klikt op **Entiteit opslaan** om alle wijzigingen in de entiteit op te slaan.

![Knop Entiteit opslaan](media/save-entity-button.png)

U kunt ook klikken op **Verwijderen** om de wijzigingen te verwijderen die u hebt gemaakt.
 
## <a name="edit-a-field"></a>Een veld bewerken

Selecteer tijdens het weergeven van velden het veld dat u wilt bewerken. U kunt de **Weergavenaam** wijzigen, maar u kunt **Naam** en **Gegevenstype** niet wijzigen als u wijzigingen in de entiteit hebt opgeslagen om het veld toe te voegen.

### <a name="general-properties"></a>Algemene eigenschappen
Elk veld heeft de volgende eigenschappen die u kunt wijzigen:

|Eigenschap|Beschrijving|
|--|--|
|**Vereist**|Als dit wordt geselecteerd, kan een record niet zonder gegevens in dit veld worden opgeslagen.|
|**Kan worden doorzocht**|Hef de selectie hiervan op voor velden van de entiteit die u niet gebruikt.  Als een veld doorzoekbaar is, wordt het weergegeven in **Geavanceerd zoeken** en is het beschikbaar bij het aanpassen van weergaven. Door de selectie ervan op te heffen worden er minder opties weergegeven aan mensen die Geavanceerd zoeken gebruiken.|
|**Beschrijving**|Gevonden in **Geavanceerde opties**. Voer instructies voor de gebruiker in en geef aan waarvoor het veld bedoeld is. Deze beschrijvingen verschijnen als knopinfo voor gebruikers in modelgestuurde apps wanneer ze hun muis boven het label van het veld houden.|

> [!NOTE]
> **Velden vereist maken**: wees voorzichtig wanneer u velden vereist maakt. Mensen zullen weerstand voelen tegen het gebruik van de toepassing als ze geen records kunnen opslaan door een gebrek aan juiste informatie om in een vereist veld in te voeren. Mensen kunnen onjuiste gegevens invoeren om de records gewoon op te slaan en door te gaan met hun werk.
>
>**Vereiste dynamisch instellen**: in modelgestuurde apps kunt u bedrijfsregels of formulierscripts gebruiken om het vereistenniveau te wijzigeren als de gegevens in de record veranderen wanneer mensen ermee werken. Meer informatie: [Bedrijfsregels en aanbevelingen maken om logica in een formulier toe te passen](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)
>
>**Beschikbaarheid van Geavanceerd zoeken**: Geavanceerd zoeken is momenteel alleen beschikbaar voor modelgestuurde apps met de webclient. De geavanceerde zoekfunctie is momenteel niet beschikbaar in de Unified Interface-clients.

## <a name="calculated-or-rollup"></a>Berekend of samengeteld

U kunt een aangepast veld instellen als **Berekend** of **Samentellen**. Naar velden die niet worden berekend of samengetelde velden wordt ook soms verwezen als *eenvoudig*e velden.

### <a name="calculated"></a>Berekend

Met een berekend veld kunt u een formule invoeren om een waarde aan het veld toe te wijzen. Deze gegevenstypen kunnen op berekende velden worden ingesteld: **Valuta**, **Datum en tijd**, **Aleen datum**, **Decimaal getal**, **Duur**, **E-mail**, **Taal**, **Optieset voor meervoudige selectie**, **Optieset**, **Tekst**, **Tekstgebied**, **Beurssymbool**, **Tijdzone**, **Twee opties**, **URL**, en **Geheel getal**.

Meer informatie: [Berekende velden definiëren om handmatige berekeningen te automatiseren](define-calculated-fields.md)

### <a name="rollup"></a>Samentellen

Met een samengeteld veld kunt u aggregatiefuncties instellen die periodiek worden uitgevoerd om een getalwaarde voor het veld in te stellen. Deze gegevenstypen kunnen op berekende velden worden ingesteld: **Valuta**, **Datum en tijd**, **Alleen datum**, **Decimaal getal**, **Duur**, **Taal**, **Timezone** en **Geheel getal**.

Meer informatie: [Samengetelde velden definiëren waarmee waarden worden samengevoegd](define-rollup-fields.md)

## <a name="number-field-options"></a>Opties voor getalvelden

Elk type getalveld heeft absolute minimum- en maximumwaarden. U kunt de juiste **Minimumwaarde** en **Maximumwaarde** binnen deze absolute waarden instellen. Doe dit om CDS voor Apps de waarden te laten valideren voor de gegevens die u in het veld wilt opslaan.

Voor de gegevenstypen **Getal met drijvende komma** en **Decimaal getal** kunt u een aantal **Decimale posities** opgeven.


## <a name="option-set-field-options"></a>Opties voor het veld Optieset

Velden die een set opties bieden, kunnen hun eigen set *lokale* opties bevatten of verwijzen naar een algemene set met *algemene* opties die door meerdere velden kunnen worden gebruikt.

Het gebruik van een algemene optieset is waardevol als u erachter komt dat u dezelfde set opties voor meerdere velden maakt. Met een algemene optieset hoeft u alleen de set opties op één plaats te beheren. 

Als u het gegevenstype **Optieset voor meervoudige selectie** of **Optieset** kiest, geeft de ontwerpfunctie een set met beschikbare algemene optiesets weer waaruit u een keuze kunt maken en wordt de mogelijkheid geboden om een **Nieuwe optieset** te maken.

![Optiesettype kiezen](media/option-set-options.png)

Als u **Nieuwe optieset** kiest, moet standaard een nieuwe algemene optieset worden gemaakt.

> [!NOTE]
> Terwijl u bewerkingsopties bewerkt voor een nieuwe algemene optieset, zijn de waarden voor **Weergavenaam** en **Naam** voor de algemene optieset in plaats van voor het veld. De standaardwaarden komen overeen met de veldwaarden, maar u kunt deze wijzigen terwijl u de algemene optieset bewerkt zodat deze afwijkt van het veld dat u momenteel maakt.

Als u een lokale optieset wilt maken, moet u klikken op **Meer weergeven** en **Lokale optieset** kiezen.

![Lokale optieset](media/local-option-set.png)

> [!NOTE]
> Als u elke optieset als een algemene optieset definieert, wordt uw lijst met algemene optiesets steeds groter en kan deze lastig te beheren zijn. Als u weet dat de set met opties slechts op één plaats wordt gebruikt, gebruikt u een lokale optieset.

[!INCLUDE [cc_remove-option-warning](../../includes/cc_remove-option-warning.md)]

## <a name="delete-a-field"></a>Een veld verwijderen

Met de beveiligsrol van systeembeheerder kunt u alle aangepaste velden verwijderen die geen deel uitmaken van een beheerde oplossing. Wanneer u een veld verwijdert, gaan de opgeslagen gegevens in het veld verloren. De enige manier om gegevens te herstellen uit een veld dat is verwijderd, is door de database te herstellen vanuit een punt voordat het veld werd verwijderd.

> [!NOTE]
> Voordat u een aangepast veld kunt verwijderen, moet u afhankelijkheden verwijderen die in andere oplossingsonderdelen aanwezig kunnen zijn. 

Als u tijdens het [weergeven van velden](#view-fields) een aangepast veld selecteert dat in de lijst kan worden verwijderd, wordt de opdracht **Veld verwijderen** weergegeven en ingeschakeld.

![Een veld verwijderen met de portal](media/delete-field-portal.png)

Gebruik de opdracht **Veld verwijderen** om het veld te verwijderen. Nadat het veld is verwijderd, moet u de wijzigingen in de entiteit opslaan.

![Entiteit opslaan na het verwijderen van een veld](media/delete-field-portal-save-entity.png)

> [!NOTE]
> Als u een foutbericht krijgt met betrekking tot afhankelijkheden, moet u oplossingenverkenner gebruiken om afhankelijkheden te detecteren. Meer informatie: [Veldafhankelijkheden controleren](create-edit-field-solution-explorer.md#check-field-dependencies)

## <a name="ime-mode"></a>IME-modus

Alle velden die directe tekstinvoer bieden, hebben een IME-modus. De IME (Input Method Editor) wordt gebruikt voor Oost-Aziatische talen, zoals Japans. Met IME's kan de gebruiker de duizenden verschillende tekens invoeren die in Oost-Aziatische talen worden gebruikt met een standaardtoetsenbord met 101 toetsen.



### <a name="see-also"></a>Zie ook  
[Velden maken en bewerken voor Common Data Service voor Apps](create-edit-fields.md)<br />
[Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner | MicrosoftDocs](create-edit-field-solution-explorer.md)<br />
[Typen velden en veldgegevenstypen](types-of-fields.md)<br />
[Berekende velden definiëren om handmatige berekeningen te automatiseren](define-calculated-fields.md)<br />
[Samengetelde velden definiëren voor het samenvoegen van waarden](define-rollup-fields.md)<br />
[Gedrag en indeling van het datum- en tijdveld](behavior-format-date-time-field.md)
