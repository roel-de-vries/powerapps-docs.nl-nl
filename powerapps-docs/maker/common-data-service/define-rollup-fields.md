---
title: Samengetelde velden definiëren met PowerApps | Microsoft Docs
description: Ontdek hoe u samengetelde velden definieert
ms.custom: ''
ms.date: 05/23/2018
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
ms.assetid: ff0504a1-01bd-4f9b-b884-7f84911d86c3
caps.latest.revision: 58
ms.author: matp
manager: kvivek
ms.openlocfilehash: c76162747ac2bda27c46895290e5943b7f46739f
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674431"
---
# <a name="define-rollup-fields-that-aggregate-values"></a>Samengetelde velden voor het aggregeren van waarden definiëren

Met samengetelde velden kunnen gebruikers inzicht krijgen in gegevens. Belangrijke metrische bedrijfsgegevens worden hiermee namelijk bewaakt. Een samengeteld veld bevat een geaggregeerde waarde, berekend op basis van de records de zijn gerelateerd aan een opgegeven record. Deze omvatten bijvoorbeeld reguliere entiteiten en activiteitsentiteiten, zoals e-mails en afspraken.

In complexere scenario's kunt u gegevens aggregeren op basis van de recordhiërarchie. Als beheerder of aanpasser kunt u de samengetelde velden definiëren met de aanpassingshulpprogramma's in PowerApps. U hoeft hiervoor geen code te schrijven.  
  
<a name="BKMK_benefitsandcapabilities"></a> 
 
## <a name="rollup-fields-benefits-and-capabilities"></a>De voordelen en mogelijkheden van samengetelde velden  

De voordelen en mogelijkheden van samengetelde velden zijn:  
  
- Het bewerken van de visuals is eenvoudig. U kunt samengetelde velden maken via de veldeditor, net als bij het maken van een regulier veld.  
- Ruime keuze aan aggregatiefuncties. U kunt gegevens aggregeren met de volgende functie: `SUM`, `COUNT`, `MIN`, `MAX` en `AVG`.  
- Volledige filterondersteuning bij aggregatie. U kunt verschillende filters instellen voor de bron- of gerelateerde entiteit en tegelijkertijd meerdere voorwaarden instellen.  
- Naadloze integratie met de gebruikersinterface. U kunt de samengetelde velden gebruiken in formulieren, weergaven, diagrammen en rapporten.  
- Samengetelde velden zijn oplossingsonderdelen. U kunt samengetelde velden eenvoudig als onderdeel gebruiken in meerdere omgevingen en ze in oplossingen distribueren.  
- Samengetelde velden en berekende velden vullen elkaar aan. U kunt een samengeteld veld gebruiken als onderdeel van het berekende veld en andersom.  
- U kunt samengetelde velden configureren voor het gebruik van aangepaste besturingselementen.  
  
 Enkele voorbeelden van samengetelde velden:  
  
- Totale geschatte omzet van de openstaande kansen van een account  
- Totale geschatte omzet van de openstaande kansen bij alle accounts in een hiërarchie  
- Totale geschatte omzet van een kans, inclusief de onderliggende kansen  
- Totale geschatte waarde van de gekwalificeerde leads die via een campagne zijn gegenereerd  
- Het aantal openstaande cases met hoge prioriteit uit alle accounts in een hiërarchie  
- Vroegste tijdstip waarop alle openstaande cases met een hoge prioriteit van een account zijn gemaakt  
  
Met elk samengeteld veld worden er twee accessoirevelden gemaakt, met het achtervoegselpatroon *&lt;fieldname&gt;*`_date` en *&lt;fieldname&gt;*`_state`. Het veld `_date` bevat de DateTime-gegevens en het veld `_state` bevat gegevens over gehele getallen. Het veld `_state` bevat de volgende waarden:  
  
|Waarde|Status|Beschrijving|  
|-|-|-|  
|0|NotCalculated|De veldwaarde moet nog worden berekend.|  
|1|Berekend|De veldwaarde is berekend op de meest recente bijwerktijd, zichtbaar in het veld _date.|  
|2|OverflowError|De berekening van de veldwaarde heeft geresulteerd in een overloopfout.|  
|3|OtherError|De berekening van de veldwaarde is mislukt vanwege een interne fout. Als u de berekeningstaak opnieuw uitvoert, wordt de fout waarschijnlijk opgelost.|  
|4|RetryLimitExceeded|Het berekenen van de veldwaarde is mislukt omdat het maximale aantal nieuwe pogingen voor het berekenen van de waarde is overschreden. Dit is veroorzaakt door een groot aantal conflicten met gelijktijdigheid en vergrendeling.|  
|5|HierarchicalRecursionLimitReached|Het berekenen van de veldwaarde is mislukt omdat de maximale hiërarchiedieptelimiet van de berekening is bereikt.|  
|6|LoopDetected|Het berekenen van de veldwaarde is mislukt omdat er een recursieve lus is gedetecteerd in de hiërarchie van de record.|  
  
<a name="BKMK_calculations"></a>  
 
## <a name="rollup-calculations"></a>Samentelberekeningen  

Samentellingen worden berekend tijdens geplande systeemtaken die asynchroon op de achtergrond worden uitgevoerd. U moet beheerder zijn om de samenteltaken te kunnen bekijken en beheren. 

### <a name="view-rollup-jobs"></a>Samenteltaken bekijken

Samenteltaken bekijken:

1. Tijdens het bekijken van de **Common Data Service-standaardoplossing** bewerkt u de URL, verwijdert u alles dat achter `dynamics.com` staat en vernieuwt u de pagina.
2. In het gedeelte **Instellingen** selecteert u **Systeem** > **Systeemtaken**.<br />![Navigeren naar de systeemtaken](media/navigate-system-jobs.png)
1. In de weergaveselectie kiest u **Terugkerende systeemtaken**.
2. Als u snel een relevante taak wilt vinden, kunt u filteren op het type systeemtaak: **Samengeteld veld massaal berekenen** of **Samengeteld veld berekenen**.
 
### <a name="mass-calculate-rollup-field"></a>Samengeteld veld massaal berekenen

**Samengeteld veld massaal berekenen** is een terugkerende taak, gemaakt per samengeteld veld. Deze taak wordt één keer uitgevoerd, nadat u een samengeteld veld hebt gemaakt of bijgewerkt. Met de taak wordt de waarde van het opgegeven samengetelde veld opnieuw berekend voor alle bestaande records die dit veld bevatten. Standaard wordt de taak 12 uur nadat u een veld hebt gemaakt of bijgewerkt, uitgevoerd. Wanneer de taak is voltooid, wordt er automatisch een nieuwe taak gepland voor over ongeveer tien jaar. Als het veld wordt bewerkt, wordt de taak binnen 12 uur na het bijwerken opnieuw uitgevoerd. De vertraging van 12 uur is nodig om er zeker van te zijn dat **Samengeteld veld massaal berekenen** wordt uitgevoerd tijdens de niet-operationele tijd van de omgeving. Het wordt aanbevolen om een beheerder de begintijd van de taak **Samengeteld veld massaal berekenen** te laten bepalen nadat het samengetelde veld is gemaakt of bewerkt. Dit dient zodanig te gebeuren dat de taak wordt uitgevoerd tijdens de niet-operationele periode van de dag. De taak kan bijvoorbeeld om middernacht worden uitgevoerd om er zeker van te zijn dat de samengetelde velden efficiënt worden verwerkt.  

### <a name="calculate-rollup-field"></a>Samengeteld veld berekenen 

**Samengeteld veld berekenen** is een terugkerende taak waarmee incrementele berekeningen worden uitgevoerd voor alle samengetelde velden in de bestaande records van een opgegeven entiteit. De taak **Samengeteld veld berekenen** bestaat slechts één keer per entiteit. 'Incrementele berekeningen' houdt in dat met de taak **Samengeteld veld berekenen** de records worden verwerkt die zijn gemaakt, bijgewerkt of verwijderd ná de uitvoering van de laatste **Samengeteld veld massaal berekenen**-taak. Standaard wordt de taak maximaal eens per uur opnieuw uitgevoerd. De taak wordt automatisch gemaakt wanneer het eerste samengetelde veld wordt gemaakt in een entiteit. De taak wordt verwijderd nadat het laatste samengetelde veld is verwijderd.  

## <a name="online-recalculation-option"></a>Optie voor onlineherberekening
Als u de muisaanwijzer op het samengetelde veld in het formulier houdt, ziet u wanneer de laatste samentelling is uitgevoerd. U kunt de samentelwaarde vernieuwen door het pictogram Vernieuwen naast het veld te selecteren, zoals hieronder wordt weergegeven:  

![Samengeteld veld in het accountformulier](media/rollup-field-on-account-form.png)
  

Er zijn enkele overwegingen waarmee u rekening moet houden bij het gebruik van de optie voor onlineherberekeningen (handmatig vernieuwen in het formulier):  
  
- U moet beschikken over schrijfbevoegdheden in de entiteit en over schrijftoegangsrechten in de bronrecords waarvoor u de vernieuwing aanvraagt. Als u bijvoorbeeld de geschatte omzet berekent van de openstaande kansen van een account, hebt u geen schrijfbevoegdheden nodig bij de kansentiteit, maar wel voor de accountentiteit.  
- Deze optie is alleen beschikbaar in de onlinemodus. U kunt deze niet gebruiken wanneer u offline werkt.  
- Het maximale aantal records tijdens de samentelvernieuwing is 50.000. Bij een hiërarchische samentelling is dit van toepassing op alle gerelateerde records in de gehele hiërarchie. Als de limiet wordt overschreden, ziet u een foutbericht: *Berekeningen kunnen niet online worden uitgevoerd omdat de berekeningslimiet van 50.000 gerelateerde records is bereikt.* Deze limiet is niet van toepassing als het samentellen automatisch opnieuw wordt uitgevoerd via de systeemtaken.  
- De maximale hiërarchiediepte is 10 voor de bronrecord. Als de limiet wordt overschreden, ziet u een foutbericht: *Berekeningen kunnen niet online worden uitgevoerd omdat de hiërarchiedieptelimiet van 10 voor de bronrecord is bereikt.* Deze limiet is niet van toepassing als het samentellen automatisch opnieuw wordt uitgevoerd via de systeemtaken.  

## <a name="modify-rollup-job-recurrence"></a>Terugkeerpatroon van samenteltaken bewerken

Als systeembeheerder kunt u het terugkeerpatroon van samenteltaken bewerken, uitstellen, onderbreken of hervatten. Samenteltaken kunnen echter niet worden geannuleerd of verwijderd. 

Als u het terugkeerpatroon wilt onderbreken, uitstellen, hervatten of bewerken, bekijkt u de systeemtaken. Zie [Samenteltaken bekijken](#view-rollup-jobs) voor meer informatie 

Kies op de navigatiebalk **Acties** en selecteer de actie die u wilt uitvoeren. 

Voor de taak **Samengeteld veld massaal berekenen** zijn de beschikbare opties: **Hervatten**, **Uitstellen** en **Onderbreken**. 

Voor de taak **Samengeteld veld berekenen** zijn de beschikbare opties: **Terugkeerpatroon aanpassen**, **Hervatten**, **Uitstellen** en **Onderbreken**.  
  
<a name="BKMK_businessscenarios"></a>  
 
## <a name="examples"></a>Voorbeelden 

Laten we enkele voorbeelden van samengetelde velden bekijken. Wij verzamelen gegevens voor een record uit de gerelateerde records mét en zonder gebruik van een hiërarchie. We aggregeren ook gegevens voor een record uit gerelateerde activiteiten en activiteiten die indirect zijn gerelateerd aan een record. Hiervoor wordt gebruikgemaakt van de ActivityParty-entiteit. In elk voorbeeld wordt het samengetelde veld gedefinieerd via de veldeditor. Als u de veldeditor wilt openen, opent u Solution Explorer en vouwt u **Onderdelen** > **Entiteiten** uit. Selecteer de gewenste entiteit en selecteer **Velden**. Kies **Nieuw**. Geef in de editor de vereiste informatie voor het veld op, inclusief het **veldtype** en het **gegevenstype**. Bij **Veldtype** selecteert u **Samengeteld** nadat u het gegevenstype hebt geselecteerd. De gegevenstypen omvatten decimale en gehele getallen, valuta's en datum/tijd. Kies de knop **Bewerken** naast het **veldtype**. U gaat dan naar de definitie-editor voor samengetelde velden. De definitie van een samengeteld veld bestaat uit drie gedeelten: **Bronentiteit**, **Gerelateerde entiteit** en **Aggregatie**.  
  
-   In het gedeelte **Bronentiteit** geeft u op voor welke entiteit het samengetelde veld is gedefinieerd en of u aggregatie uitvoert op basis van een hiërarchie. U kunt filters met meerdere voorwaarden toevoegen om op te geven welke velden in de hiërarchie u wilt gebruiken voor de samentelling.  
  
-   In het gedeelte **Gerelateerd entiteit** geeft u de entiteit op waarvoor u aggregeert. Dit gedeelte is optioneel als u ervoor kiest om op basis van de bronentiteit een samentelling uit te voeren in de hiërarchie. U kunt filters met meerdere voorwaarden toevoegen om op te geven welke gerelateerde records in de berekening moeten worden gebruikt. U kunt bijvoorbeeld de omzet van de openstaande kansen optellen bij de jaarlijkse omzet als deze groter is dan $ 1000.  
  
-   In het gedeelte **Aggregatie** kunt u opgeven welk metrisch gegeven u wilt berekenen. U kunt kiezen uit de beschikbare aggregatiefuncties, zoals SUM, COUNT, MIN, MAX en AVG.  
  
### <a name="aggregate-data-for-a-record-from-related-records"></a>Geaggregeerde gegevens van een record, op basis van gerelateerde records  

In dit voorbeeld wordt geen hiërarchie gebruikt. De totale geschatte omzet wordt berekend voor een account op basis van de gerelateerde openstaande kansen.  

![De geschatte omzet voor een account aggregeren](media/rollup-field-no-hierarchy.png)
  
### <a name="aggregate-data-for-a-record-from-the-child-records-over-the-hierarchy"></a>Geaggregeerde gegevens van een record op basis van de onderliggende records (via de hiërarchie) 
 
In dit voorbeeld wordt de totale geschatte omzet van een kans berekend via de hiërarchie (inclusief de onderliggende kansen).  
  
![Geaggregeerde geschatte omzet, kanshiërarchie](media/rollup-field-hierarchy-self.png)
  
### <a name="aggregate-data-for-a-record-from-the-related-records-over-the-hierarchy"></a>Geaggregeerde gegevens van een record op basis van de gerelateerde records (via de hiërarchie)

In dit voorbeeld wordt de totale geschatte omzet van openstaande kansen berekend voor alle accounts, via de hiërarchie.  
  
![Geaggregeerde geschatte omzet op basis van de accounthiërarchie](media/rollup-field-hierarchy.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities"></a>Geaggregeerde gegevens van een record, op basis van alle gerelateerde activiteiten
  
In dit voorbeeld wordt de totale bestede tijd berekend en wordt berekend hoeveel tijd er in totaal is gefactureerd voor alle activiteiten die aan een account zijn gerelateerd. Het kan gaan om tijd die aan de telefoon, aan afspraken of aan aangepaste activiteiten is besteed.  
  
In oudere versies was het mogelijk om een samengeteld veld te definiëren voor individuele activiteiten, zoals telefoongesprekken voeren, faxen verzenden of afspraken bijwonen. Om echter de resultaten te bereiken zoals in het onderstaande voorbeeld is te zien, moest met de berekende velden een totaal worden berekend. U kunt dit nu allemaal in één stap doen door één samengeteld veld te definiëren voor de entiteit Activiteit.  
  
![Samentelling voor alle activiteiten van een account](media/rollup-enhancements-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities-and-activities-indirectly-related-via-the-activity-party-entity"></a>Gegevens aggregeren voor een record uit alle gerelateerde activiteiten en activiteiten die indirect zijn gerelateerd, via de ActivityParty-entiteit  

In dit voorbeeld wordt geteld hoeveel e-mails er in totaal naar een account zijn verzonden. Hierbij wordt het account vermeld in het veld Aan of in het veld Cc. Hiervoor wordt in de definitie van het samengetelde veld het **type deelname** in **FILTERS** ingesteld op de entiteit Betrokkene bij de activiteit. Als u geen filters gebruikt, worden alle beschikbare deelnametypen voor een activiteit gebruikt in de berekening. 
 
Voor meer informatie over de entiteit Betrokkene bij de activiteit en de deelnametypen die beschikbaar zijn voor een bepaalde activiteit ziet u [ActivityParty-entiteit](/dynamics365/customer-engagement/developer/activityparty-entity).

  
![Gerelateerde activiteiten samentellen en de betrokkene bij de activiteit](media/rollup-enhancements-indirect-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-related-records-using-the-avg-operator"></a>Geaggregeerde gegevens van een record, op basis van de AVG-operator

In dit voorbeeld wordt de gemiddelde geschatte omzet van alle kansen berekend die zijn gerelateerd aan een account.  
  
![Gemiddelde geschatte omzet in Dynamics 365](media/rollup-enhancements-average.PNG)  
  
In het volgende voorbeeld ziet u hoe u de gemiddelde geschatte omzet van gerelateerde kansen berekent in een hiërarchie van accounts. Op elk niveau in de hiërarchie is een gemiddelde geschatte omzet te zien.  
  
![Gemiddelde geschatte omzet in Dynamics 365](media/cust-rollup-enhancements-avg-over-hierarchy.png)  
  
<a name="BKMK_considerations"></a> 

## <a name="rollup-field-considerations"></a>Overwegingen bij samengetelde velden 

U moet rekening houden met bepaalde voorwaarden en beperkingen bij het werken met samengetelde velden:  
  
- U kunt maximaal 100 samengetelde velden definiëren voor de organisatie en maximaal 10 samengetelde velden per entiteit.  
- Werkstromen kunnen niet worden geactiveerd door updates in samengetelde velden.  
- Bij de voorwaarde Wachten in een werkstroom kan geen gebruik worden gemaakt van een samengeteld veld.  
- Er wordt geen ondersteuning geboden voor het samentellen van samengetelde velden.  
- Bij een samentelling kan niet worden verwezen naar een berekend veld waarin een ander berekend veld wordt gebruikt, zelfs niet als alle velden van het andere berekende veld zich in de huidige entiteit bevinden.  
- Bij de samentelling mogen er alleen filters worden toegepast op de bronentiteit of op gerelateerde entiteiten, eenvoudige velden en niet-complexe berekende velden.  
- U kunt alleen voor gerelateerde entiteiten met een 1:N-relatie een samentelling uitvoeren. Het is niet mogelijk om een samentelling uit te voeren bij een N:N-relatie.  
- Er kan bij de entiteit Activiteit of de entiteit Betrokkene bij de activiteit geen samentelling worden uitgevoerd als er sprake is van een 1:N-relatie.  
- Bij bedrijfsregels, werkstromen en berekende velden wordt altijd de laatst berekende waarde van het samengetelde veld gebruikt.  
- Een samengeteld veld wordt geaggregeerd in de context van de systeemgebruiker. Alle gebruikers zien dezelfde waarde van het samengetelde veld. U kunt de zichtbaarheid van het samengetelde veld beheren met beveiliging op veldniveau (FLS), door te beperken wie er toegang heeft tot het samengetelde veld. Meer informatie over [beveiliging op veldniveau om toegang te beheren](/dynamics365/customer-engagement/admin/field-level-security). 

### <a name="precision-rounding"></a>Afrondingsprecisie
 
Als de precisie van het geaggregeerde veld groter is dan de precisie van het samengetelde veld, wordt de precisie van het geaggregeerde veld omlaag afgerond naar de precisie van het samengetelde veld. Dit gebeurt vóórdat de aggregatie wordt uitgevoerd. Bekijk dit specifieke voorbeeld om beter inzicht te krijgen in hoe dit werkt. Stel dat het samengetelde veld in de accountentiteit (voor het berekenen van de totale geschatte omzet van de gerelateerde kansen) een precisie heeft van twee cijfers achter de komma. Het Geschatte omzet-veld in de kansentiteit is het geaggregeerde veld, met een precisie van vier cijfers achter de komma. In ons voorbeeld heeft het account twee gerelateerde kansen. De geaggregeerde som van de geschatte omzet wordt als volgt berekend:  
  
1. Geschatte omzet van de eerste kans: $ 1000,0041  
1. Geschatte omzet van de tweede kans: $ 2000,0044  
1. Geaggregeerde som van de geschatte omzet: $ 1000,00 + $ 2000,00 = $3000,00

Zoals u ziet, wordt in het geaggregeerde veld afgerond naar twee cijfers achter de komma vóórdat er aggregatie plaatsvindt.  
  
### <a name="different-behavior-from-associated-grids"></a>Verschillend gedrag van gekoppelde rasters
 
Bepaalde entiteitformulieren, zoals Account of Contactpersoon, bevatten standaard de bijbehorende rasters. Een accountformulier bevat bijvoorbeeld Contactpersonen, Cases, Kansen en andere rasters. Enkele van de records die worden weergegeven in rasters van accountformulieren zijn rechtstreeks gerelateerd aan het accountrecord. Andere zijn indirect gerelateerd, namelijk via de relatie met andere records. Ter vergelijking: bij aggregatie voor een samengeteld veld wordt alleen gebruikgemaakt van de directe relaties die expliciet zijn vermeld in de definitie van het samengetelde veld. Andere relaties worden niet in overweging genomen. Bekijk het volgende voorbeeld ter illustratie van het verschil in gedrag.  
  
1. Account A1 heeft een primaire contactpersoon, P1. Case C1 wordt gekoppeld aan account A1 (het C1-klantveld is A1). Case C2 wordt gekoppeld aan contactpersoon P1 (C2-klantveld is P1).  
1. Het raster **Cases** in het **account**formulier voor het record A1 bevat twee cases, C1 en C2.  
1. Het samengetelde veld in de accountentiteit (met de naam Totale aantal cases) wordt gebruikt om te tellen hoeveel cases er aan het account zijn gekoppeld.  
1. In de definitie van het samengetelde veld van het account worden de cases opgegeven die een klantrelatie hebben met het account. Na de aggregatie is het totale aantal cases gelijk aan 1 (case C1). Case C2 is niet opgenomen in het totaal omdat deze rechtstreeks is gerelateerd aan de contactpersoon (niet het account) en niet expliciet kan worden vermeld in de definitie van het samengetelde veld van het account. Als gevolg komt het totale aantal cases dat is geretourneerd door de samentelbewerking niet overeen met het aantal cases dat wordt weergegeven in het raster **Cases**.  
  
### <a name="see-also"></a>Zie ook  

[Velden maken en bewerken](create-edit-fields.md)<br />
[Berekende velden definiëren](define-calculated-fields.md)<br />
[Gedrag en indeling van het veld Datum en tijd](behavior-format-date-time-field.md)<br />
[Hiërarchisch gerelateerde gegevens definiëren en er query's op uitvoeren](define-query-hierarchical-data.md)<br />
[Video: samengetelde en berekende velden](http://www.youtube.com/watch?v=RoahCH1p3T8&list=PLC3591A8FE4ADBE07&index=8)<br />
[Video: Power BI gebruiken](http://www.youtube.com/watch?v=PkQe4BFlBS8&list=PLC3591A8FE4ADBE07&index=3)
