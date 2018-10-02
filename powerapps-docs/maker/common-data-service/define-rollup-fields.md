---
title: Samenvoegvelden definiëren met PowerApps | MicrosoftDocs
description: Samenvoegvelden definiëren
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="define-rollup-fields-that-aggregate-values"></a>Samengetelde velden definiëren voor het samenvoegen van waarden

Samengetelde velden, of samenvoegvelden, helpen u inzicht te krijgen in gegevens door belangrijke bedrijfsmetrische gegevens te bewaken. Een samengeteld veld bevat een samengevoegde waarde die is berekend aan de hand van een opgegeven record. Hierbij gaat het om reguliere entiteiten en activiteitsentiteiten, zoals e-mailberichten en afspraken.

In meer complexe scenario's kunt u gegevens samenvoegen uit de hiërarchie van records. Als beheerder of aanpasser kunt u samengetelde velden definiëren met behulp van de aanpassingshulpmiddelen in PowerApps, zonder dat een ontwikkelaar code hoeft te schrijven.  
  
<a name="BKMK_benefitsandcapabilities"></a> 
 
## <a name="rollup-fields-benefits-and-capabilities"></a>Voordelen en mogelijkheden van samengetelde velden  

De voordelen en mogelijkheden van samengetelde omvatten het volgende:  
  
- Visuele bewerking is gemakkelijk. U kunt samengetelde velden maken met de Veldeditor, zoals u dat ook doet met een gewoon veld.  
- Brede selectie van statistische functies. U kunt gegevens samenvoegen met de volgende functies: `SUM`, `COUNT`, `MIN`, `MAX` en `AVG`.  
- Volledige filterondersteuning voor samenvoeging. U kunt diverse filters voor de bronentiteit of gerelateerde entiteit instellen tijdens het instellen van meerdere voorwaarden.  
- Naadloze integratie met de gebruikersinterface. U kunt de samengetelde velden opnemen in formulieren, weergaven, grafieken en rapporten.  
- Samengetelde velden zijn oplossingsonderdelen. U kunt de samengetelde velden gemakkelijk als onderdelen transporteren tussen omgevingen en ze distribueren in oplossingen.  
- Samengetelde velden en de berekende velden zijn complementair aan elkaar. U kunt een samengeteld veld gebruiken als onderdeel van het berekende veld en omgekeerd.  
- U kunt samengetelde velden configureren om aangepaste besturingselementen te gebruiken.  
  
 Dit zijn enkele voorbeelden van samengetelde velden:  
  
- Totale geschatte omzet van open verkoopkansen van een account  
- Totale geschatte omzet van open verkoopkansen over alle accounts in een hiërarchie  
- Totale geschatte omzet van een verkoopkans inclusief onderliggende verkoopkansen  
- Totale geschatte waarde van gekwalificeerde potentiële klanten die door een campagne worden gegenereerd  
- Een aantal geopende aanvragen met hoge prioriteit over alle accounts in een hiërarchie  
- De vroegste tijd waarop alle open aanvragen met hoge prioriteit voor een account zijn gemaakt  
  
Elk samengeteld veld maakt twee bijbehorende velden met het achtervoegselpatroon *&lt;veldnaam&gt;*`_date` en *&lt;veldnaam&gt;*`_state`. Het veld `_date` bevat datum- en tijdgegevens en het veld `_state` bevat een geheel getal. Het veld `_state` heeft de volgende waarden:  
  
|Waarde|Status|Beschrijving|  
|-|-|-|  
|0|NotCalculated|De veldwaarde moet nog worden berekend.|  
|1|Calculated|De veldwaarde is berekend op basis van de laatste updatetijd in het veld _date.|  
|2|OverflowError|De veldwaardeberekening resulteerde in een overflowfout.|  
|3|OtherError|De berekening van de veldwaarde is mislukt vanwege een interne fout. De volgende uitvoering van de berekeningstaak lost het waarschijnlijk op.|  
|4|RetryLimitExceeded|De veldwaardeberekening is mislukt omdat het maximumaantal pogingen om de waarde te berekenen is overschreden vanwege een groot aantal gelijktijdigheids- en vergrendelingsconflicten.|  
|5|HierarchicalRecursionLimitReached|De veldwaardeberekening is mislukt omdat de maximumlimiet van de hiërarchiediepte voor de berekening is bereikt.|  
|6|LoopDetected|De veldwaardeberekening is mislukt omdat een recursieve lus in de hiërarchie van de record werd gedetecteerd.|  
  
<a name="BKMK_calculations"></a>  
 
## <a name="rollup-calculations"></a>Samengetelde berekeningen  

De rollups worden berekend door geplande systeemtaken die asynchroon op de achtergrond worden uitgevoerd. U moet een beheerder te zijn om de rolluptaken te bekijken en beheren. 

### <a name="view-rollup-jobs"></a>Samenteltaken weergeven

U geeft samenteltaken als volgt weer:

1. In de weergave van de **Common Data Services-standaardoplossing** kunt u de URL bewerken door alles na `dynamics.com` te verwijderen. Vernieuw vervolgens de pagina.
2. Selecteer in het gebied **Instellingen** de optie **Systeem** > **Systeemtaken**.<br />![Navigeren naar systeemtaken](media/navigate-system-jobs.png)
1. In de weergaveselector kiest u **Terugkerende systeemtaken**.
2. Als u een relevante taak snel wilt vinden, kunt u filteren op het systeemtaaktype: **Samengeteld veld massaal berekenen** of **Samengeteld veld berekenen**.
 
### <a name="mass-calculate-rollup-field"></a>Samengeteld veld massaal berekenen

**Samengeteld veld massaal berekenen** is een terugkerende taak die per samengeteld veld wordt gemaakt. De taak wordt eenmaal uitgevoerd nadat u een samengeteld veld hebt gemaakt of bijgewerkt. De taak berekent de waarde van het opgegeven samengetelde veld in alle bestaande records die dit veld bevatten. Standaard wordt de taak 12 uur nadat u een veld hebt gemaakt of bijgewerkt, uitgevoerd. Nadat de taak is voltooid, wordt deze automatisch gepland om in de verre toekomst te worden uitgevoerd, ongeveer over 10 jaar. Als het veld wordt gewijzigd, wordt de taak opnieuw ingesteld en 12 uur na de update weer uitgevoerd. De vertraging van 12 uur is nodig om te garanderen dat **Samengeteld veld massaal berekenen** tijdens de niet-operationele uren van de omgeving wordt uitgevoerd. Het is aan te raden dat een beheerder de starttijd van een taak **Samengeteld veld massaal berekenen** aanpast nadat het samengetelde veld is gemaakt of gewijzigd, zodat de taak tijdens niet-operationele uren wordt uitgevoerd. Een goede manier is bijvoorbeeld om de taak om middernacht uit te voeren, om efficiënte verwerking van de samengetelde velden te garanderen.  

### <a name="calculate-rollup-field"></a>Samengeteld veld berekenen 

**Samengeteld veld berekenen** is een terugkerende taak die incrementele berekeningen uitvoert van alle samengetelde velden in de bestaande records voor een opgegeven entiteit. Er is maar één taak **Samengeteld veld berekenen** per entiteit. De incrementele berekeningen betekenen dat de taak **Samengeteld veld berekenen** de records verwerkt die zijn gemaakt, bijgewerkt of verwijderd nadat de laatste taak **Samengeteld veld massaal berekenen** is uitgevoerd. De instelling van het standaard maximale terugkeerpatroon is één uur. De taak wordt automatisch gemaakt als het eerste samengetelde veld voor een entiteit wordt gemaakt en wordt verwijderd wanneer het laatste samengetelde veld wordt verwijderd.  

## <a name="online-recalculation-option"></a>Optie voor onlineherberekening
Als u de aanwijzer boven het samengetelde veld in het formulier houdt, ziet u de tijd van de laatste rollup en kunt u de rollupwaarde vernieuwen door het pictogram Vernieuwen te kiezen naast het veld, zoals hieronder:  

![Samengeteld veld in het accountformulier](media/rollup-field-on-account-form.png)
  

Er is een aantal aanvullende overwegingen waarmee u rekening moet houden als u de optie voor online herberekening gebruikt (handmatig vernieuwen in het formulier):  
  
- U moet beschikken over schrijfbevoegdheden voor de entiteit en schrijftoegangsrechten voor de bronrecord waarvoor u de vernieuwing aanvraagt. Als u bijvoorbeeld de geschatte omzet van de open verkoopkansen van een account berekent, hoeft u geen schrijfbevoegdheden voor de verkoopkansentiteit te hebben, alleen voor de accountentiteit.  
- Deze optie is alleen beschikbaar in de online modus. U kunt deze niet gebruiken terwijl u offline werkt.  
- Het maximumaantal records tijdens de rollupvernieuwing is beperkt tot 50.000. In het geval van een hiërarchische rollup geldt dit voor de verwante records in de hiërarchie. Als de limiet wordt overschreden, wordt het foutbericht *Berekeningen kunnen niet online worden uitgevoerd omdat de berekeningslimiet van 50.000 gerelateerde records is bereikt* weergegeven. Deze limiet is niet van toepassing wanneer de rollup automatisch door de systeemtaken wordt berekend.  
- De maximale hiërarchiediepte is beperkt tot 10 voor de bronrecord. Als de limiet wordt overschreden, ziet u het foutbericht *Berekeningen kunnen niet online worden uitgevoerd omdat de hiërarchiedieptelimiet van 10 voor de bronrecord is bereikt.* Deze limiet is niet van toepassing wanneer de rollup automatisch door de systeemtaken wordt berekend.  

## <a name="modify-rollup-job-recurrence"></a>Terugkeerpatroon van rolluptaak wijzigen

Als systeembeheerder kunt u het terugkeerpatroon van de rolluptaak wijzigen, uitstellen, onderbreken of de rolluptaak hervatten. U kunt een rolluptaak echter niet annuleren of verwijderen. 

Als u het terugkeerpatroon wilt onderbreken, uitstellen, hervatten of wijzigen, moet u de systeemtaken weergeven. Meer informatie [Samenteltaken weergeven](#view-rollup-jobs) 

Kies op de navigatiebalk **Acties** en selecteer de actie u wilt. 

Voor de taak **Samengeteld veld massaal berekenen** zijn de beschikbare opties **Hervatten**, **Uitstellen** en **Onderbreken**. 

Voor de taak **Samengeteld veld berekenen** zijn de beschikbare opties **Terugkeer aanpassen**, **Hervatten**, **Uitstellen** en **Onderbreken**.  
  
<a name="BKMK_businessscenarios"></a>  
 
## <a name="examples"></a>Voorbeelden 

Bekijk de volgende voorbeelden van samengetelde velden. We voegen gegevens samen voor een record vanuit de gerelateerde records, met en zonder een hiërarchie te gebruiken. We voegen ook gegevens samen voor een record uit gerelateerde activiteiten en activiteiten die indirect aan een record gerelateerd zijn via de entiteit Betrokkene bij activiteit. In elk voorbeeld wordt het samengetelde veld gedefinieerd met de Veldeditor. Als u de veldeditor wilt openen, opent u de oplossingenverkenner en vouwt u **Onderdelen** > **Entiteiten** uit. Selecteer de gewenste entiteit en selecteer **Velden**. Kies **Nieuw**. Geef in de editor de vereiste gegevens voor het veld op, inclusief het **Veldtype** en het **Gegevenstype**. Selecteer in het **Veldtype** **Rollup** nadat u het gegevenstype hebt geselecteerd. De gegevenstypen omvatten decimale of gehele getallen, valuta en datum/tijd. Kies de knop **Bewerken** naast het **Veldtype**. Hiermee komt u bij de editor voor de definitie van het samengetelde veld. De definitie van het samengetelde veld bestaat uit drie gedeelten: **Bronentiteit**, **Gerelateerde entiteit** en **Samenvoeging**.  
  
-   In de sectie **Bronentiteit** geeft u de entiteit op waarvoor het samengetelde veld wordt gedefinieerd en of u samenvoegt via een hiërarchie. U kunt filters met meerdere voorwaarden toevoegen om de records in de hiërarchie op te geven die u voor de rollup wilt gebruiken.  
  
-   In de sectie **Gerelateerde entiteit** geeft u de entiteit op waarover u samenvoegt. Deze sectie is optioneel wanneer u ervoor kiest de rollup uit te voeren via de hiërarchie van de bronentiteit. U kunt filters met meerdere voorwaarden toevoegen om op te geven welke gerelateerde records in de berekening moeten worden gebruikt. U neemt bijvoorbeeld de omzet op van de open verkoopkansen met een jaarlijkse omzet van meer dan $ 1000.  
  
-   In de sectie **Statistisch** geeft u de metrische gegevens op die u wilt berekenen. U kunt beschikbare samenvoegingsfuncties, zoals SOM, TELLING, MIN, MAX of GEM kiezen.  
  
### <a name="aggregate-data-for-a-record-from-related-records"></a>Samenvoegingsgegevens voor een record vanuit gerelateerde records  

In dit voorbeeld wordt geen hiërarchie gebruikt. De totale geschatte omzet wordt berekend voor een account, vanuit de verwante open verkoopkansen.  

![Samenvoegen van de geschatte omzet voor een account](media/rollup-field-no-hierarchy.png)
  
### <a name="aggregate-data-for-a-record-from-the-child-records-over-the-hierarchy"></a>Samengevoegde gegevens voor een record uit de onderliggende records, via de hiërarchie 
 
In dit voorbeeld wordt de totale geschatte omzet van een verkoopkans berekend, inclusief de onderliggende verkoopkansen, via de hiërarchie.  
  
![Samenvoegen van de geschatte omzet, verkoopkanshiërarchie](media/rollup-field-hierarchy-self.png)
  
### <a name="aggregate-data-for-a-record-from-the-related-records-over-the-hierarchy"></a>Samengevoegde gegevens voor een record uit de verwante records, via de hiërarchie

In dit voorbeeld wordt de totale geschatte omzet van open verkoopkansen berekend over alle accounts, via de hiërarchie.  
  
![Samenvoegen van de geschatte omzet voor een accounthiërarchie](media/rollup-field-hierarchy.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities"></a>Samenvoegingsgegevens voor een record vanuit alle gerelateerde activiteiten
  
In dit voorbeeld berekenen we de totale bestede en gefactureerde tijd van alle activiteiten die aan een account zijn gerelateerd. Dit kan tijd omvatten aan de telefoon, afspraken of aangepaste activiteiten.  
  
In eerdere versies kon u een samengeteld veld definiëren voor een afzonderlijke activiteit, zoals een telefoongesprek, fax of afspraak. Maar om het resultaat van het hieronder aangegeven voorbeeld te bereiken moest u de gegevens optellen met behulp van de berekende velden. Nu kunt u het allemaal in één stap doen door één samengeteld veld te definiëren voor de activiteitentiteit.  
  
![Alle activiteiten voor een account samenstellen](media/rollup-enhancements-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-all-related-activities-and-activities-indirectly-related-via-the-activity-party-entity"></a>Gegevens voor een record samenvoegen uit alle gerelateerde activiteiten en activiteiten die indirect gerelateerd zijn via de entiteit Betrokkene bij activiteit.  

In dit voorbeeld tellen we het totale aantal e-mails dat naar een account is verzonden, waarbij het account wordt genoemd op de regel "Aan geadresseerde" of "Cc geadresseerde" van de e-mail. Dit wordt gedaan door **Deelnemertype** op te geven in **FILTERS** voor de entiteit Betrokkene bij activiteit in de definitie van het samengetelde veld. Als u geen filtering gebruikt, worden alle beschikbare deelnemertypen voor een activiteit in de berekening gebruikt. 
 
Voor meer informatie over de entiteit Betrokkene bij activiteit en beschikbare deelnemertypen voor een bepaalde activiteit raadpleegt u [Entiteit Betrokkene bij activiteit](/dynamics365/customer-engagement/developer/activityparty-entity).

  
![Gerelateerde activiteiten en betrokkenen samentellen](media/rollup-enhancements-indirect-activities.png)  
  
### <a name="aggregate-data-for-a-record-from-related-records-using-the-avg-operator"></a>Samenvoegingsgegevens voor een record vanuit gerelateerde records met behulp van de operator GEM

In dit voorbeeld berekenen we een gemiddelde geschatte omzet van alle verkoopkansen die zijn gerelateerd aan een account.  
  
![De gemiddelde geschatte omzet in Dynamics 365](media/rollup-enhancements-average.PNG)  
  
Het volgende voorbeeld toont hoe u een gemiddelde geschatte omzet berekent van gerelateerde verkoopkansen in een hiërarchie van accounts. Een gemiddelde geschatte omzet kan op elk niveau van de hiërarchie worden gezien.  
  
![De gemiddelde geschatte omzet in Dynamics 365](media/cust-rollup-enhancements-avg-over-hierarchy.png)  
  
<a name="BKMK_considerations"></a> 

## <a name="rollup-field-considerations"></a>Overwegingen bij samengetelde velden 

U moet van bepaalde condities en beperkingen op de hoogte zijn wanneer u werkt met samengetelde velden:  
  
- U kunt maximaal 100 samengetelde velden voor de organisatie definiëren en maximaal 10 samengetelde velden per entiteit.  
- Een werkstroom kan niet worden geactiveerd door de updates van samengetelde velden.  
- Een werkstroomwachtvoorwaarde kan geen samengeteld veld gebruiken.  
- Een rollup over het samengetelde veld wordt niet ondersteund.  
- Een samengeteld veld kan niet verwijzen naar berekend veld dat gebruikmaakt van een ander berekend veld, zelfs als alle velden van het andere berekende veld deel uitmaken van de huidige entiteit.  
- De rollup kan alleen filters toepassen op de bronentiteit of verwante entiteiten, eenvoudige velden of niet-complexe berekende velden.  
- Een rollup kan alleen worden uitgevoerd over gerelateerde entiteiten met de 1:N-relatie. Een rollup kan niet worden uitgevoerd over de N:N-relaties.  
- Een rollup kan niet worden uitgevoerd over de 1: N-relatie voor de activiteitentiteit of de Betrokkene bij activiteit-entiteit.  
- De bedrijfsregels, werkstromen of berekende velden gebruiken altijd de laatste berekende waarde van het samengetelde veld.  
- Een samengeteld veld wordt samengevoegd onder de systeemgebruikerscontext. Alle gebruikers kunnen dezelfde waarde van het samengetelde veld zien. U kunt de zichtbaarheid van het samengetelde veld controleren met de veldniveaubeveiliging (FLS), door te beperken wie toegang tot het samengetelde veld kunnen krijgen. Meer informatie [Beveiliging op veldniveau voor toegangsbeheer](/dynamics365/customer-engagement/admin/field-level-security). 

### <a name="precision-rounding"></a>Precisieafronding
 
Als de precisie van het statistische veld groter is dan de precisie van het samengetelde veld, wordt de statistische veldprecisie naar beneden afgerond op de precisie van het samengetelde veld, voordat de samenvoeging wordt uitgevoerd. Om dit gedrag te illustreren, bekijkt u een voorbeeld. Stel dat het samengetelde veld van de accountentiteit, voor het berekenen van de totale geschatte omzet van de verwante verkoopkansen, een precisie van twee decimalen heeft. Het veld Gesch. omzet van de verkoopkansentiteit is het samengevoegde veld met een precisie van vier decimalen. In ons voorbeeld heeft de account twee verwante verkoopkansen. De samengevoegde som van de geschatte omzet wordt berekend als volgt:  
  
1. Gesch. omzet voor de eerste verkoopkans: $ 1000,0041  
1. Gesch. omzet voor de tweede verkoopkans: $ 2000,0044  
1. Samengevoegde som van Gesch. Omzet: $1000,00 + $2000,00 = $3000,00

Zoals u ziet, wordt de precisieafronding op twee decimalen in het statistische veld uitgevoerd voordat de samenvoeging wordt uitgevoerd.  
  
### <a name="different-behavior-from-associated-grids"></a>Verschillend gedrag van gekoppelde rasters
 
Bepaalde entiteitformulieren zoals Account of Contactpersoon bevatten standaard de gekoppelde rasters. Een accountformulier bevat bijvoorbeeld contactpersonen, aanvragen, verkoopkansen en andere rasters. Sommige records die in accountformulierrasters worden weergegeven, zijn direct gerelateerd aan de accountrecord; andere indirect, via de relaties met andere records. De samenvoeging van het samengetelde veld gebruikt daarentegen alleen directe relaties die expliciet zijn gedefinieerd in de definitie van het samengetelde veld. Geen andere relaties worden beschouwd. Het volgende voorbeeld illustreert het verschil in gedrag.  
  
1. Het account A1 heeft een primaire contactpersoon P1. Aanvraag C1 is gekoppeld aan account A1 (C1.veld Klant = A1) en aanvraag C2 is gekoppeld aan contactpersoon P1 (C2.veld Klant = P1).  
1. Het raster **Aanvragen** op het formulier **Account** voor record A1 toont twee aanvragen, C1 en C2.  
1. Het samengetelde veld in de accountentiteit, genaamd Totaal aantal aanvragen, wordt gebruikt om de aanvragen te tellen die aan het account zijn gekoppeld.  
1. In de definitie van het samengetelde accountveld, geven we de aanvragen op die de klantrelatie met het account hebben. Na samenvoeging is Totaal aantal aanvragen gelijk aan 1 (aanvraag C1). Aanvraag C2 is niet opgenomen in het totaal, want is direct gekoppeld aan de contactpersonen, niet aan het account, en kan niet expliciet worden gedefinieerd in de definitie van het samengetelde accountveld. Hierdoor komt het totale aantal door de rollup-bewerking geretourneerde aanvragen niet overeen met het aantal aanvragen dat wordt weergegeven in het raster **Aanvragen**.  
  
### <a name="see-also"></a>Zie ook  

[Velden maken en bewerken](create-edit-fields.md)<br />
[Berekende velden definiëren](define-calculated-fields.md)<br />
[Gedrag en indeling van het datum- en tijdveld](behavior-format-date-time-field.md)<br />
[Hiërarchische gegevens definiëren en opvragen](define-query-hierarchical-data.md)<br />
[Video: Samengetelde en berekende velden](http://www.youtube.com/watch?v=RoahCH1p3T8&list=PLC3591A8FE4ADBE07&index=8)<br />
[Video: Power BI gebruiken](http://www.youtube.com/watch?v=PkQe4BFlBS8&list=PLC3591A8FE4ADBE07&index=3)
