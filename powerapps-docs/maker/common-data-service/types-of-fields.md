---
title: Veldgegevenstypen in Common Data Service voor Apps | MicrosoftDocs
description: Informatie over de verschillende veldgegevenstypen die beschikbaar zijn voor de app
keywords: ''
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 734b4ffa-5543-4f88-8517-299589f433f7
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="types-of-fields"></a>Veldtypen

Welke namen voor typen worden gebruikt, is afhankelijk van de gebruikte ontwerper. In de [PowerApps-portal](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) wordt gebruikgemaakt van een conventie waarbij de wijze waarop de gegevens zijn opgemaakt, is inbegrepen. In oplossingenverkenners wordt een naam gebruikt die is afgestemd op het databasegegevenstype. De volgende tabel bevat het overeenkomstige API-type `AttributeTypeDisplayName`.

|Portalgegevenstype |Type oplossingenverkenner| API-type|
|--|--|--|
|**Groot geheel getal**|**Tijdstempel**|`BigIntType`|
|**Valuta**|**Valuta**|`MoneyType`|
|**Klanten**|**Klanten**|`CustomerType`|
|**Datum en tijd**|**Datum en tijd**<br />*Datum en tijd*|`DateTimeType`|
|**Alleen datum**|**Datum en tijd**<br />*Alleen datum*|`DateTimeType`|
|**Decimaal getal**|**Decimaal getal**|`DecimalType`|
|**Duur**|**Geheel getal**<br />*Duur*|`IntegerType`|
|**E-mail**|**Eén tekstregel**<br />*E-mail*|`StringType`|
|**Getal met drijvende komma**|**Getal met drijvende komma**|`DoubleType`|
|**Afbeelding**|**Afbeelding**|`ImageType`|
|**Taal**|**Geheel getal**<br />*Taal*|`IntegerType`|
|**Opzoeken**|**Opzoeken**|`LookupType`|
|**Optieset voor meervoudige selectie**|**Optieset voor meervoudige selectie**|`MultiSelectPicklistType`|
|**Tekst van meerdere regels**|**Meerdere tekstregels**|`MemoType`|
|**Optieset**|**Optieset**|`PicklistType`|
|**Eigenaar**|**Eigenaar**|`OwnerType`|
|**Telefoon**|**Eén tekstregel**<br />*Telefoon*|`StringType`|
|**Reden van status**|**Reden van status**|`StatusType`|
|**Status**|**Status**|`StateType`|
|**Tekstgebied**|**Eén tekstregel**<br />*Tekstgebied*|`StringType`|
|**Tekst**|**Eén tekstregel**<br />*Tekst*|`StringType`|
|**Beurssymbool**|**Eén tekstregel**<br />Beurssymbool|`StringType`|
|**Tijdzone**|**Geheel getal**<br />*Tijdzone*|`IntegerType`|
|**Twee opties**|**Twee opties**|`BooleanType`|
|**Unieke id**|**Unieke id** of **Primaire sleutel**|`UniqueidentifierType`|
|**URL**|**Eén tekstregel**<br />*URL*|`StringType`|
|**Geheel getal**|**Geheel getal**<br />*Geen*|`IntegerType`|

Zie voor meer beschrijvingen voor alle typen die u kunt toevoegen of bewerken het onderwerp voor de betreffende ontwerper:
 - [Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-portal: Veldgegevenstypen](create-edit-field-portal.md#field-data-types)
 - [Velden maken en bewerken voor Common Data Service voor Apps met de PowerApps-oplossingenverkenner: Veldgegevenstypen](create-edit-field-solution-explorer.md#field-data-types)

Zie [Kenmerkmetagegevens](/powerapps/developer/common-data-service/entity-attribute-metadata) voor meer informatie over hoe veldgegevenstypen worden gedefinieerd in de API

## <a name="field-types-used-by-the-system"></a>Veldtypen die door het systeem worden gebruikt

Enkele velden die door het systeem worden gebruikt, kunt u niet toevoegen via de ontwerper.

|Type|Beschrijving|
|--|--|
|**Groot geheel getal** of **Tijdstempel**|Gebruikt door het systeem om een versienummer vast te leggen en updates voor een entiteit te beheren.|
|**Klanten**|Een opzoekveld dat u kunt gebruiken om een klant op te geven. Dit kan een account of contactpersoon zijn.<br />**Notitie**: dit kenmerk kan worden toegevoegd via de ontwerper van de oplossingenverkenner.|
|**Eigenaar**|Een systeemopzoekveld dat naar gebruikers of teams verwijst die de eigenaar zijn van een entiteitsrecord dat hen is toegewezen.|
|**Reden van status**|Een systeemveld dat opties heeft die aanvullende details over het veld Status te bieden. Elke optie is gekoppeld aan een van de beschikbare Statusopties. U kunt de opties toevoegen en bewerken. <br /><br /> U kunt ook aangepaste statusovergangen opnemen om te bepalen welke statusopties beschikbaar zijn voor bepaalde entiteiten. Meer informatie: [Statusredenovergangen definiëren voor aangepaste entiteiten](define-status-reason-transitions.md)|
|**Status**|Een systeemveld dat opties heeft die meestal met actieve en niet-actieve status overeenkomen. Sommige Systeemkenmerken bevatten extra opties, maar alle aangepaste kenmerken hebben alleen de statusopties **Actief** en **Inactief**.  |
|**Unieke id**|Een systeemveld slaat een Globally Unique Identifier (GUID)-waarde op voor elke record.|

  
## <a name="multiselect-option-set"></a>Optieset voor meervoudige selectie

U kunt formulieren (hoofdformulier, formulier voor snel maken en formulier voor snelle weergave) en e-mailsjablonen aanpassen door velden met meerdere selectiemogelijkheden toe te voegen. Wanneer u een veld met een optieset voor meervoudige selectie toevoegt, kunt u meerdere waarden opgeven die gebruikers kunnen selecteren. Wanneer gebruikers het formulier invullen, kunnen zij één, meerdere of alle waarden selecteren die worden weergegeven in een vervolgkeuzelijst.

Als een organisatie bijvoorbeeld in meerdere regio's of landen actief is, kunt u meerdere locaties of landen opnemen in een veld "Actief in". Een gebruiker kan vervolgens één of meer locaties in de lijst met beschikbare waarden selecteren.

Optie voor meervoudige selectie is alleen beschikbaar in alleen-lezen rasters, bewerkbare rasters en formulieren. Optie voor meervoudige selectie wordt niet ondersteund in: 
- Werkstromen, acties, dialoogvensters, rollups, grafieken en berekende velden.
- Rapporten, SLA en routeringregel.

Velden voor multi-selectie worden ondersteund in de volgende typen van formulieren:

|Formuliertype|Beschikbaarheid|
|--|--|
|**Turboformulier**|Ja|
|**Formulier Vernieuwen**|Alleen-lezen (het veld is beschikbaar maar kan niet worden bewerkt)|
|**Oud formulier**|No|
|**Formulier Bulkbewerking**|No|

U kunt algemene optiesets gebruiken die in uw organisatie zijn gedefinieerd om waarden te configureren voor de optiesets voor meervoudige selectie.


<a name="BKMK_UsingTheRightTypeOfNumber"></a>
  
## <a name="using-the-right-type-of-number"></a>Het juiste type nummer gebruiken

Wanneer u het juiste soort getalveld kiest om te gebruiken, zou de keuze om het type **Geheel getal** of **Valuta** te gebruiken vrij ongecompliceerd moeten zijn. Over de keuze tussen het gebruik van **Zwevend punt** of **Decimaal** moet beter worden nagedacht.  
  
De decimale getallen wordt precies zoals opgegeven opgeslagen in de database. Drijvendekommaaantallen slaan een uiterst precieze benadering van de waarde op. Waarom zou u een uiterst precieze benadering kiezen als u ook de exacte waarde kunt hebben? Het antwoord is dat u verschillende systeemprestaties krijgt.  
  
Gebruik decimalen als u rapporten moet opgeven die zeer exacte berekeningen vereisen, of als u doorgaans query's gebruikt die waarden zoeken die wel of niet gelijk zijn aan een andere waarde.  
  
Gebruik drijvendekommagetallen als u gegevens opslaat die delen of waarden vormen waar u doorgaans aan twijfelt als u ze met een andere waarde vergelijkt groter dan of minder dan operators. In de meeste gevallen zijn is het verschil tussen decimaal en drijvend niet merkbaar. Tenzij u de meest exact mogelijke berekeningen vereist, moeten de drijvendekommagetallen voor u werken.  
  
<a name="BKMK_UsingCurrencyFields"></a>
 
## <a name="using-currency-fields"></a>Het gebruik van valutavelden

Met valutavelden kan een organisatie meerdere valuta's configureren die kunnen worden gebruikt voor records in de organisatie. Wanneer organisaties meerdere valuta's hebben, willen ze meestal berekeningen berekeningen kunnen uitvoeren om waarden op te geven met hun basisvaluta. Als u een valutaveld toevoegt aan een entiteit die niet andere valutavelden heeft, worden er twee extra velden toegevoegd:  
  
- Een opzoekveld dat **Valuta** heet dat u op elke actieve valuta kunt instellen die voor uw organisatie is geconfigureerd. U kunt meerdere actieve valuta's voor uw organisatie configureren in **Instellingen** > **Ondernemingsbeheer** > **Valuta**. U kunt daar de valuta en een wisselkoers opgeven met de basisvaluta die voor uw organisatie is ingesteld. Als u meerdere actieve valuta's hebt, kunt u het valutaveld toevoegen aan het formulier en mensen toestaan op te geven welke valuta moet worden toegepast op geldwaarden voor deze record. Hierdoor wordt het valutasymbool dat voor de valutavelden in het formulier wordt weergegeven gewijzigd.  
  
  Personen kunnen ook hun persoonlijke opties wijzigen om een basisvaluta te selecteren voor de records die zij maken.
  
- Een decimaal veld dat **Wisselkoers** heet dat de wisselkoers voor een geselecteerde valuta biedt die aan de entiteit is gekoppeld ten opzichte van de basisvaluta. Als dit veld aan het formulier is toegevoegd, kunnen gebruikers de waarde zien maar zij kunnen deze niet bewerken. De wisselkoers wordt met de valuta opgeslagen.  
  
Voor elk valutaveld dat u toevoegt, wordt een ander valutaveld toegevoegd met het voorvoegsel `_Base`. Dit veld slaat de berekening van de waarde van het valutaveld dat u hebt toegevoegd en de basisvaluta op. Nogmaals, als dit veld aan het formulier is toegevoegd, kan het niet worden bewerkt.  
  
Als u een valutaveld configureert, kunt u de precisiewaarde kiezen. Er zijn drie opties, zoals wordt aangegeven in de volgende tabel.  
  
|Optie|Beschrijving|  
|------------|-----------------|  
|Decimale nauwkeurigheid prijs|Dit is één organisatieprecisie die wordt gebruikt voor prijzen in **Instellingen** > **Beheer** > **Systeeminstellingen** > **tabblad Algemeen**.|  
|Nauwkeurigheid van valuta|Met deze optie wordt de precisie toegepast die is bepaald voor de valuta in de record.|  
|Specifieke precisiewaarden|Met deze instellingen kunt u een specifiek ingestelde precisie opgeven met waarden tussen 0 en 4.|  
  
<a name="BKMK_DifferentTypesOfLookups"></a> 
  
## <a name="different-types-of-lookups"></a>Verschillende typen zoekopdrachten  

Als u een nieuw opzoekveld maakt, maakt u een nieuwe Veel-op-een (N:1)-entiteitsrelatie tussen de entiteit waarmee u werkt en het **Type Doelrecord** dat is gedefinieerd voor de zoekopdracht. Er zijn extra configuratieopties voor deze relatie die worden beschreven in [Relaties tussen entiteiten maken en bewerken](create-edit-entity-relationships.md). Maar alle aangepaste zoekopdrachten kunnen alleen een verwijzing naar één record voor één doelrecordtype toestaan.  
  
U moet er echter rekening mee houden dat niet elke zoekopdracht zich op deze manier gedraagt. Er zijn verschillende typen systeemzoekopdrachten zoals hier aangegeven.  
  
|Opzoektype|Beschrijving|  
|-----------------|-----------------|  
|**Vereenvoudigd**|Staat één verwijzing naar een specifieke entiteit toe. Alle aangepaste zoekopdrachten zijn dit type.|  
|**Klant**|Staat één verwijzing naar ofwel een account- ofwel een contactpersoonrecord toe.|  
|**Eigenaar**|Staat één verwijzing naar ofwel een team- ofwel een gebruikersrecord toe. Alle entiteiten die eigendom zijn van een team of een gebruiker hebben een van deze zoekopdrachten.|  
|**PartyList**|Staat meerdere referenties naar meerdere entiteiten toe. Deze zoekopdrachten bevinden zich in de velden **Aan** en **CC** van de E-mailentiteit. Ze worden ook gebruikt in de entiteiten Telefoon en Afspraak.|  
|**Met betrekking tot**|Staat één referenties naar meerdere entiteiten toe. Deze zoekopdrachten bevinden zich in het betreffende veld dat in activiteiten wordt gebruikt.|  

<a name="BKMK_ImageFields"></a>

## <a name="image-fields"></a>Afbeeldingsvelden  

Gebruik afbeeldingsvelden om één afbeelding per record in de toepassing weer te geven. Elke entiteit kan één afbeeldingsveld hebben. U kunt een afbeeldingsveld toevoegen aan aangepaste entiteiten, maar niet aan standaardentiteiten. Voor sommige standaardentiteiten zijn afbeeldingsvelden gedefinieerd.
  
Hoewel een entiteit een afbeeldingsveld heeft, is er een extra stap nodig om die afbeelding in een modelgestuurde app weer te geven. De veldwaarden **Primaire afbeelding** in de entiteitsdefinitie zijn **[Geen]** of **Entiteitsafbeelding**. Selecteer **Entiteitsafbeelding** om de afbeelding in de toepassing weer te geven.  
  
Als afbeeldingweergave voor een entiteit is ingeschakeld, geven alle records die geen afbeelding hebben een tijdelijke afbeeldingsaanduiding weer. Bijvoorbeeld:

![Tijdelijke afbeeldingsaanduiding](../common-data-service/media/lead-entity-form.PNG)
  
Mensen kunnen de standaardafbeelding kiezen om een afbeelding vanaf hun computer te uploaden. Afbeeldingen moeten kleiner dan 5120 KB zijn en moeten een van de volgende indelingen hebben:  
  
- jpg
- JPEG
- GIF
- TIF
- TIFF
- BMP
- PNG
  
Wanneer de afbeelding wordt geüpload, zal deze worden geconverteerd naar een .jpg-indeling en alle gedownloade afbeeldingen zullen ook deze indeling gebruiken. Als een animated .gif wordt geüpload, wordt alleen de eerste frame opgeslagen.  
  
Wanneer een afbeelding wordt geüpload, wordt de grootte aangepast tot een maximale grootte van 144 pixels bij 144 pixels. Mensen moeten de grootte van de afbeelding wijzigen of de afbeeldingen bijsnijden alsvorens ze te uploaden zodat ze goed worden weergegeven met deze grootte. Alle afbeeldingen worden zo bijgesneden dat ze vierkant zijn. Als beide kanten van een afbeelding kleiner dan 144 pixels zijn, wordt de afbeelding zo bijgesneden dat deze vierkant is met de afmetingen van de kleine kant.  

Meer informatie voor ontwikkelaars die met afbeeldingsgegevens werken:
- [Metagegevens entiteit > Entiteitsafbeeldingen](/powerapps/developer/common-data-service/entity-metadata#entity-images)
- [Ontwikkelaarshandleiding voor Dynamics 365 Customer Engagement: Afbeeldingskenmerken](/dynamics365/customer-engagement/developer/image-attributes)
