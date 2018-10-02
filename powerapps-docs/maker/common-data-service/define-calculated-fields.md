---
title: Berekende velden in PowerApps definiëren | MicrosoftDocs
description: Berekende velden definiëren
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
ms.assetid: 6d58a297-2ddf-4236-be3a-47249b49d5fa
caps.latest.revision: 67
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-calculated-fields-to-automate-manual-calculations"></a>Berekende velden definiëren om handmatige berekeningen te automatiseren

Met berekende velden kunt u handmatige berekeningen automatiseren die in uw bedrijfsprocessen worden gebruikt. 

Een verkoper wil bijvoorbeeld weten wat de gewogen opbrengst van een verkoopkans is, die wordt gebaseerd op de geschatte opbrengst van een verkoopkans, vermenigvuldigd met de waarschijnlijkheid. Of, zij willen automatisch een korting toepassen als een order groter is dan $500. Een berekend veld kan waarden bevatten die het resultaat zijn van simpele berekeningen of voorwaardelijke bewerkingen, zoals groter dan, Als-Anders, enzovoort. U kunt dit alles doen met PowerApps, zonder code te hoeven schrijven.  
  
## <a name="capabilities"></a>Mogelijkheden
  
- Berekende velden gebruiken de velden uit de huidige entiteit of verwante bovenliggende entiteiten.  
- De expressieondersteuning is beschikbaar voor de huidige entiteitvelden en velden voor gerelateerde bovenliggende entiteiten in de secties **Voorwaarde** en de secties **Actie**. Tot de ingebouwde functies behoren:  
 **ADDHOURS**, **ADDDAYS**, **ADDWEEKS**, **ADDMONTHS**, **ADDYEARS**, **SUBTRACTHOURS**, **SUBTRACTDAYS**, **SUBTRACTWEEKS**, **SUBTRACTMONTHS**, **SUBTRACTYEARS**, **DIFFINDAYS**, **DIFFINHOURS**, **DIFFINMINUTES**, **DIFFINMONTHS**, **DIFFINWEEKS**, **DIFFINYEARS**, **CONCAT**, **TRIMLEFT** en **TRIMRIGHT**.  
- Een uitgebreide ondersteuning voor voorwaardelijke opmaak voorziet in vertakking en meerdere voorwaarden. De logische bewerkingen omvatten de operatoren **AND** en **OR**.  
- De visuele bewerkingsmogelijkheden omvatten een moderne gebruikersinterface en IntelliSense in de sectie **ACTIE**. 
- Een naadloze integratie van de berekende velden met de formulieren, weergaven, diagrammen en rapporten is beschikbaar in realtime.  
- U kunt berekende velden configureren om aangepaste besturingselementen te gebruiken.  
  
  
## <a name="scenarios"></a>Scenario's
  
- **Gewogen omzet**: geschatte omzet die wordt vermenigvuldigd met waarschijnlijkheid  
- **Nettowaarde**: activa min passiva voor een bepaalde account  
- **Arbeidskosten**: basiswisselkoers tot 40 uur, plus extra overuren  
- **Contactpersoonnummer**: telefoonnummer voor een verkoopkans gebaseerd op account of contactpersoon  
- **Leadscore**: enkel veld dat inzicht biedt in de kwaliteit van een specifieke potentiële klant  
- **Opvolgen voor**: vervolgactie voor een activiteit na een opgegeven aantal dagen op basis van prioriteit  
  
> [!IMPORTANT]
>  Als u een berekend veld wilt maken, moet u de bevoegdheid Schrijven hebben voor de entiteit [Veldbeveiligingsprofiel](/powerapps/developer/common-data-service/reference/entities/fieldsecurityprofile). Als het berekende veld de beveiligde velden in een berekening gebruikt, kunt u overwegen het berekende veld eveneens te beveiligen om te verhinderen dat gebruikers toegang krijgen tot gegevens waarvoor zij onvoldoende bevoegdheden hebben. De editor voor berekende velden geeft u een waarschuwing als u een berekend veld maakt waarbij beveiligde velden in een berekening worden gebruikt, met de suggestie om het berekende veld te beveiligen. Meer informatie: [Beveiliging op veldniveau voor toegangsbeheer](/dynamics365/customer-engagement/admin/field-level-security).  

## <a name="create-a-calculated-field"></a>Een berekend veld maken

Gebruik de veldeditor om een berekend veld op te geven. In dit voorbeeld gebruiken we [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), maar de stappen komen overeen voor de oplossingenverkenner. Meer informatie: [Velden maken en bewerken](create-edit-fields.md)
  
1. Open [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
1. Vouw **Gegevens** > **Entiteiten** uit.  
1. Selecteer de gewenste entiteit en kies **Velden**. Kies **Veld toevoegen**.  
1. Geef de vereiste gegevens voor het veld op, inclusief de waarden voor **Weergavenaam**, **Naam** en **Gegevenstype**. 
1. Als het gegevenstype een van de typen is die berekende velden ondersteunen, kunt u van het veld een berekend veld maken door **Toevoegen** > **Berekening** te selecteren.

    ![Veld berekend maken](media/make-field-calculated-maker.png)

    Dit zijn de veldtypen die berekeningen ondersteunen:
    - Tekst
    - Optieset  
    - Twee opties  
    - Geheel getal  
    - Decimaal getal  
    - Valuta  
    - Datum/tijd

1. Als u **Berekening** selecteert, moet u de wijzigingen in de entiteit opslaan. Klik op **Opslaan** in het dialoogvenster **Wijzigingen in behandeling** om door te gaan.
1. De editor voor het definiëren van berekende velden wordt geopend. Hierin is het nieuwe berekende veld gemaakt, maar er is geen formule ingesteld. De definitie van het berekende veld bestaat uit twee secties: **VOORWAARDE** en **ACTIE**.  
  ![Formulier voor nieuwe veldberekening](media/empty-field-calculation.png)
- In de sectie **Voorwaarde** kunt u een entiteit, veld, operator, type en waarde opgeven. In de vervolgkeuzelijst voor **Entiteit** kunt u voor een huidige entiteit of gerelateerde entiteit kiezen. In de vervolgkeuzelijst **Veld** kunt u alle beschikbare velden voor de entiteit selecteren. Afhankelijk van de operator die u gebruikt, moet u mogelijk het type en de waarde opgeven. U kunt meerdere voorwaarden opgeven met de operatoren `AND` en `OR`.  
- In de sectie **Actie** geeft u de formule op voor het berekende veld.  
  
> [!NOTE]
>  U kunt gegevens vanuit Records opzoeken gebruiken binnen uw actie. U moet eerst het Opzoekveld selecteren en vervolgens een punt invoeren. Daarna kunt u een van de velden selecteren die beschikbaar zijn voor de gerelateerde entiteit. In het geval van *`<LookupFieldName>.<RelatedFieldName>`* kunt u bijvoorbeeld `ParentAccountId.AccountNumber` selecteren.  
>   
>  Denk eraan dat de beveiliging op veldniveau voor de verwante entiteit wordt genegeerd, dus als er gegevens in het worden vereist veld zijn waarin wij hebben voorgesteld ook uw beveiligen berekend veld.  


<a name="BusinessScenarios"></a> 
  
## <a name="examples"></a>Voorbeelden  

We gaan nu eens nader naar voorbeelden van berekende velden kijken. 
  
### <a name="weighted-revenue-of-opportunity"></a>Gewogen omzet van verkoopkans

In dit voorbeeld gebruiken we de velden van de entiteit verkoopkans om de gewogen omzet te berekenen op basis van de waarschijnlijkheid van de verkoopkans. In de veldeditor voor een entiteit Verkoopkans maken we een veld met de naam **Gewogen omzet** en geven we het veldtype op als **Berekend** en het gegevenstype als **Valuta**.

In de editor voor het definiëren van het berekende veld, in de sectie **Voorwaarde**, geven we de verkoopkans de Status = Open. Bij de **ACTIE** berekent de formule de gewogen geschatte omzet op basis van de geschatte omzet van de verkoopkans vermenigvuldigd met de waarschijnlijkheid van de verkoopkans.  In de volgende schermafbeeldingen wordt stap voor stap weergegeven hoe u het berekende veld **Gewogen omzet** definieert.  
  
#### <a name="set-the-condition-on-the-opportunities"></a>Stel de voorwaarde in voor de verkoopkansen:
  
![Gewogen omzet instellen in Dynamics 365](media/calc-field-open-opportunity.png)  
  
#### <a name="provide-the-formula-for-the-weighted-revenue"></a>Verstrek de formule voor de gewogen omzet: 
  
![Geschatte waarde Gewogen omzet in Dynamics 365 instellen](media/calc-field-open-opportunities-3.png)  
  
#### <a name="altogether"></a>Totaal:
  
![Gewogen omzet voor gesch. omzet in Dynamics 365](media/calculated-field-open-opportunity.png)  
  
### <a name="follow-up-date-of-opportunity"></a>Opvolgingsdatum voor verkoopkans 
 
In dit voorbeeld gebruiken we de velden van de oorspronkelijke potentiële klant van een verkoopkans om de juiste datum te berekenen wanneer u de verkoopkans wilt opvolgen. 

In de veldeditor voor een entiteit Verkoopkans maken we een veld met de naam **Opvolgingsdatum** en geven we het veldtype op als **Berekend** en het gegevenstype als **Datum en tijd**.  

In de editor voor het definiëren van het berekende veld, in de sectie **Voorwaarde**, geven we twee voorwaarden op: het tijdsbestek voor aankoop en de geschatte waarde van de potentiële klant. 

Bij **ACTIE** geven we twee formules op:
 - Om de verkoopkans een week na de directe verkoopkans op te volgen.
 - Om de verkoopkans over een maand op te volgen, als de verkoopkans waarschijnlijk niet direct wordt gerealiseerd. 

In de volgende schermafbeeldingen wordt stap voor stap weergegeven hoe u het berekende veld **Opvolgingsdatum** definieert.  
  
#### <a name="set-the-two-conditions-on-the-originating-lead"></a>Stel de twee voorwaarden in op de oorspronkelijke potentiële klant:
  
![Opvolgingsdatum voor een verkoopkans in Dynamics 365](media/calc-field-follow-update-2.PNG)  
  
![Opvolgingsdatum voor een verkoopkans in Dynamics 365](media/calc-field-follow-update-3.PNG)  
  
#### <a name="provide-the-formula-to-follow-up-in-one-week"></a>Verstrek de formule om over één week op te volgen:
  
![Opvolgingsdatum voor een verkoopkans in Dynamics 365](media/calc-field-follow-update-4.PNG)  
  
#### <a name="provide-the-formula-to-follow-up-in-one-month"></a>Verstrek de formule om over één maand op te volgen:
  
![Opvolgingsdatum in Dynamics 365 instellen](media/calc-field-follow-update-5.PNG)  
  
#### <a name="altogether"></a>Totaal:
  
 ![Opvolgingsdatum Als-Dan en Anders in Dynamics 365 instellen](media/calc-field-follow-update-6.PNG)  
  
### <a name="days-from-a-record-creation"></a>Dagen vanaf het maken van een record 
 
In dit voorbeeld gebruiken we de functie **DIFFINDAYS** om het verschil in dagen vanaf het moment waarop de record werd gemaakt tot de huidige datum te berekenen. 

Maak een nieuw veld van het type Geheel getal met de naam **Berekend verschil in dagen**.
  
#### <a name="provide-the-formula-for-computing-the-difference-in-days"></a>Verstrek de formule voor het berekenen van het verschil in dagen
  
![Berekend veld, DIFFINDAYS-functie](media/custom-calc-field-diff-days.png)  
  
#### <a name="altogether"></a>Totaal:
  
![Verschil in dagen sinds maken van records](media/calc-field-diff-days-complete.png)  
  
<a name="Syntax"></a> 
  
## <a name="functions-syntax"></a>Functiesyntaxis  

De volgende tabel bevat informatie over de syntaxis voor de functies in de sectie **ACTIE** van het berekende veld bestaat.  
  
> [!TIP]
>  De functienamen zijn opgegeven in hoofdletters.  
  
|Functiesyntaxis|Beschrijving|Retourtype|  
|---------------------|-----------------|-----------------|  
|**ADDDAYS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd plus het opgegeven aantal dagen.|Datum en tijd|  
|**ADDHOURS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd plus het opgegeven aantal uren.|Datum en tijd|  
|**ADDMONTHS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd plus het opgegeven aantal maanden.|Datum en tijd|  
|**ADDWEEKS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd plus het opgegeven aantal weken.|Datum en tijd|  
|**ADDYEARS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd plus het opgegeven aantal jaren.|Datum en tijd|  
|**SUBTRACTDAYS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd min het opgegeven aantal dagen.|Datum en tijd|  
|**SUBTRACTHOURS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd min het opgegeven aantal uren.|Datum en tijd|  
|**SUBTRACTMONTHS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd min het opgegeven aantal maanden.|Datum en tijd|  
|**SUBTRACTWEEKS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd min het opgegeven aantal weken.|Datum en tijd|  
|**SUBTRACTYEARS** (geheel getal, datum en tijd)|Retourneert een nieuwe datum en tijd die gelijk zijn aan de opgegeven datum en tijd min het opgegeven aantal jaren.|Datum en tijd|  
|**DIFFINDAYS** (datum en tijd, datum en tijd)|Retourneert het verschil in dagen tussen twee velden **Datum en tijd**. Als beide datums en tijden op dezelfde dag vallen, is het verschil nul.|Geheel getal|  
|**DIFFINHOURS** (datum en tijd, datum en tijd)|Retourneert het verschil in uren tussen twee velden **Datum en tijd**.|Geheel getal|  
|**DIFFINMINUTES** (datum en tijd, datum en tijd)|Retourneert het verschil in minuten tussen twee velden **Datum en tijd**.|Geheel getal|  
|**DIFFINMONTHS** (datum en tijd, datum en tijd)|Retourneert het verschil in maanden tussen twee velden **Datum en tijd**. Als beide datums en tijden in dezelfde maand vallen, is het verschil nul.|Geheel getal|  
|**DIFFINWEEKS** (datum en tijd, datum en tijd)|Retourneert het verschil in weken tussen twee velden **Datum en tijd**. Als beide datums en tijden in dezelfde week vallen, is het verschil nul.|Geheel getal|  
|**DIFFINYEARS** (datum en tijd, datum en tijd)|Retourneert het verschil in jaren tussen twee velden **Datum en tijd**. Als beide datums en tijden in hetzelfde jaar vallen, is het verschil nul.|Geheel getal|  
|**CONCAT** (één tekstregel, één tekstregel, ... één tekstregel)|Retourneert een tekenreeks die het resultaat is van het aaneenschakelen van twee of meer tekenreeksen.|Tekenreeks|  
|**TRIMLEFT** (één tekstregel, geheel getal)|Retourneert een tekenreeks met een kopie van een opgegeven tekenreeks zonder de eerste N tekens.|Tekenreeks|  
|**TRIMRIGHT** (één tekstregel, geheel getal)|Retourneert een tekenreeks met een kopie van een opgegeven tekenreeks zonder de laatste N tekens.|Tekenreeks|  
  
> [!NOTE]
>  Alle DIFF-functies vereisen dat het eerste veld **Datum en tijd** en het tweede veld **Datum en tijd** hetzelfde gedrag hebben: **Gebruikersinstelling**, **Alleen datum** of **Tijdzone-onafhankelijk**. Als het gedrag van het tweede veld niet overeenkomt met het gedrag van het eerste veld, wordt het foutbericht weergegeven dat het tweede veld niet kan worden gebruikt in de huidige functie. Meer informatie: [Gedrag en indeling van het datum- en tijdveld](behavior-format-date-time-field.md).  
  
> [!NOTE]
>  U kunt geen datum, zoals 01/01/2015, als de datumwaarde invoeren in een berekend veld. Datum en de datumtijdwaarden kunnen alleen worden ingesteld of vergeleken met behulp van andere datumtijdvelden.  
  
In de functie **CONCAT** kunt u letterlijke tekenreeksen gebruiken als enkele tekstregels, entiteitsvelden die één tekstregel bevatten, of een combinatie van beide. Bijvoorbeeld: **CONCAT** (Achternaam, Voornaam, "is een manager."). Als een letterlijke tekenreeks aanhalingstekens bevat, moet elk aanhalingsteken als volgt vooraf worden gegaan door een omgekeerde schuine streep (\\): `This string contains the \"quotation marks.\"` Op deze manier worden de aanhalingstekens binnen de tekenreeks niet behandeld als speciale tekens die de tekenreeksen scheiden.  
  
De volgende voorbeelden tonen hoe u de functies **TRIMLEFT** en **TRIMRIGHT** gebruikt. Ze bevatten de aanvankelijke tekenreeksen en de resulterende tekenreeksen, die door de functies **TRIMLEFT** en **TRIMRIGHT** worden geretourneerd:  
  
**TRIMLEFT** ("RXX10-3456789", 3), retourneert de tekenreeks `10-3456789`    
**TRIMRIGHT** ("20-3456789RXX", 3), retourneert de tekenreeks `20-3456789` 
  
<a name="Considerations"></a> 
  
## <a name="considerations"></a>Overwegingen 
 
U moet zich bewust zijn van bepaalde voorwaarden en beperkingen bij het werken met berekende velden:  
  
- Opgeslagen query's, diagrammen en visualisaties kunnen maximaal 10 unieke berekende velden bevatten.  
- De berekende veldwaarden worden niet weergegeven in de offlinemodus van Outlook Client in de tegelweergaven of in entiteithoofdformulieren.  
- Er kunnen maximaal 5 geketende berekende velden worden gebruikt.  
- Een berekend veld kan niet naar zichzelf verwijzen of cyclische ketens bevatten.  
- Als u een van de voorwaardenoperatoren in een meervoudige voorwaardencomponent wijzigt, worden alle voorwaardenoperatoren op basis van die voorwaarde bijgewerkt. Als u bijvoorbeeld in de component `IF (x > 50) OR (y ==10) OR (z < 5)` de operator `OR` verandert in de operator `AND`, worden alle `OR`-operatoren in de clausule `AND`-operatoren.  
- U kunt toegang krijgen tot bovenliggende velden via het opzoekveld voor de bovenliggende entiteit, bijvoorbeeld *`<LookupFieldName>.<FieldName>`*. Dit is niet mogelijk met opzoekvelden voor meerdere entiteiten, zoals Klant die Account of Contactpersoon kan zijn. Sommige entiteiten bevatten echter afzonderlijke opzoekvelden voor een specifieke entiteit, zoals `ParentAccountid.`*`<FieldName>`* of `ParentContactid.`*`<FieldName>`*.  
- Sorteren is uitgeschakeld voor:  
  - Een berekend veld dat een veld van een bovenliggende record bevat.  
  - Een berekend veld dat een logisch veld bevat (bijvoorbeeld een adresveld)
  - Een berekend veld dat een ander berekend veld bevat.  
- Berekende velden kunnen slechts twee entiteiten omvatten.  
  - Een berekend veld kan een veld van een andere entiteit bevatten (dat twee entiteiten omvat - huidige entiteit en bovenliggende record).  
  - Een berekend veld kan geen berekend veld van een andere entiteit bevatten die ook een ander veld van een andere entiteit bevat (drie entiteiten):   
    (Huidige entiteit) Berekend veld &larr; (Bovenliggende record) Berekend veld 1 &larr; (Bovenliggende record) Berekend veld 2.  
- U kunt geen werkstromen of plug-ins activeren voor berekende velden.  
- U kunt geen bestaand eenvoudig veld in een berekend veld wijzigen. Als uw huidige toepassing gebruikmaakt van JavaScript of plug-ins om een veld te berekenen, kunt u de functie voor berekende velden niet gebruiken zonder een nieuw veld te maken.  
- De regels voor duplicatendetectie worden niet geactiveerd op berekende velden.  
- Een samengeteld veld kan niet verwijzen naar berekend veld dat gebruikmaakt van een ander berekend veld, zelfs als alle velden van het andere berekende veld deel uitmaken van de huidige entiteit.  
  
### <a name="see-also"></a>Zie ook
 
[Velden maken en bewerken](create-edit-fields.md)<br />
[Samengetelde velden definiëren voor het samenvoegen van waarden](define-rollup-fields.md)<br />
[Video: Samengetelde en berekende velden](http://go.microsoft.com/fwlink/p/?LinkId=517727)
