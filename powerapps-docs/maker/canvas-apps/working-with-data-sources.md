---
title: Gegevensbronnen begrijpen | Microsoft Docs
description: Referentie-informatie voor het werken met verbindingen en gegevensbronnen in Microsoft PowerApps.
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 03/08/2017
ms.author: gregli
ms.openlocfilehash: 5e9b9ec980e6dd4aeacfef42b40fe7f52c19d558
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="understand-data-sources-in-powerapps"></a>Gegevensbronnen begrijpen in PowerApps
Voor de meeste PowerApps-apps wordt externe informatie gebruikt die is opgeslagen in cloudservices. Deze worden **Gegevensbronnen** genoemd. Een veel voorkomend voorbeeld is bijvoorbeeld een tabel in een Excel-bestand die is opgeslagen in OneDrive voor Bedrijven. Apps krijgen toegang tot deze gegevensbronnen via **Verbindingen**.

In dit artikel worden de verschillende soorten gegevensbronnen besproken en het werken met gegevensbronnen van tabellen.

Het is gemakkelijk om een app te maken die basale lees- en schrijfactiviteiten naar een gegevensbron kan uitvoeren. Maar soms wilt u meer controle over hoe gegevens in en uit uw app stromen.  In dit artikel wordt beschreven hoe de functies **[Patch](functions/function-patch.md)**, **[DataSourceInfo](functions/function-datasourceinfo.md)**, **[Validate](functions/function-validate.md)** en **[Errors](functions/function-errors.md)** u meer controle bieden.

## <a name="kinds-of-data-sources"></a>Soorten gegevensbronnen
Gegevensbronnen kunnen worden verbonden met een cloudservice of lokaal in een app staan.

### <a name="connected-data-sources"></a>Verbonden gegevensbronnen
De meestvoorkomende gegevensbron is een **tabel**, die u kunt gebruiken om informatie op te halen en op te slaan. U kunt **verbindingen** met gegevensbronnen gebruiken om gegevens te lezen en schrijven in Microsoft Excel-werkmappen, SharePoint-lijsten, SQL-tabellen en nog veel meer. U kunt de gegevens vervolgens opslaan in cloudservices zoals OneDrive voor Bedrijven, DropBox, SQL Server, enzovoort.

Voorbeelden van andere gegevensbronnen zijn e-mail, agenda's, Twitter en meldingen. Deze gegevensbronnen worden hier echter niet behandeld.

### <a name="local-data-sources"></a>Lokale gegevensbronnen
Met de besturingselementen **[Galerie](controls/control-gallery.md)**, **[Formulier weergeven](controls/control-form-detail.md)** en **[Formulier bewerken](controls/control-form-detail.md)** kunt u eenvoudig een app maken die gegevens leest uit en schrijft naar een gegevensbron.  Lees het artikel [Gegevensformulieren begrijpen](working-with-forms.md) om aan de slag te gaan.  

Als u PowerApps vraagt een app van gegevens te maken, worden deze besturingselementen gebruikt. Achter de schermen maakt de app gebruik van een interne tabel voor het opslaan en manipuleren van de gegevens die afkomstig zijn uit de gegevensbron.

Een speciaal soort gegevensbron is de [Verzameling](working-with-data-sources.md#collections). Deze staat lokaal in de app en wordt niet ondersteund door een verbinding met een service in de cloud. Daarom kunnen de gegevens niet worden gedeeld met apparaten voor dezelfde gebruiker of tussen gebruikers. Verzamelingen kunnen worden geladen en lokaal opgeslagen.

### <a name="kinds-of-tables"></a>Soorten tabellen
Tabellen die intern in een PowerApps-app staan zijn vaste waarden, net zoals een getal of een tekenreeks een waarde is. Interne tabellen worden niet overal opgeslagen maar zijn alleen aanwezig in het geheugen van uw app. U kunt de structuur en gegevens van een tabel niet rechtstreeks wijzigen. U kunt in plaats daarvan een nieuwe tabel maken via een formule: u gebruikt die formule om een aangepaste kopie van de oorspronkelijke tabel te maken.

Externe tabellen worden opgeslagen in een gegevensbron om later op te halen en te delen.  PowerApps bevat "verbindingen" om opgeslagen gegevens te lezen en te schrijven.  Binnen een verbinding kunt u meerdere tabellen met gegevens openen.  U selecteert welke tabellen u wilt gebruiken in uw app en elke tabel wordt een afzonderlijke *gegevensbron*.  

Voor meer informatie leest u [Werken met tabellen](working-with-tables.md), dat verder ingaat op interne tabellen, maar het is ook van toepassing op externe tabellen die zich in een cloudservice bevinden.

## <a name="working-with-tables"></a>Werken met tabellen
U kunt gegevensbronnen van tabellen op dezelfde manier gebruiken als u een interne PowerApps-tabel.  Net als een interne tabel heeft elke gegevensbron [records](working-with-tables.md#records), [kolommen](working-with-tables.md#columns) en eigenschappen die u in formules kunt gebruiken. Daarnaast:

* De gegevensbron bevat dezelfde kolomnamen en gegevenstypen als de onderliggende tabel in de verbinding.
  
    > [!NOTE]
> Kolomnamen met spaties in gegevensbronnen van Excel of SharePoint worden in PowerApps vervangen door **‘\_x0020\_’**. **'Kolom twaalf'** in SharePoint of Excel wordt bijvoorbeeld weergegeven als **'Kolom_x0020_twaalf'** in PowerApps wanneer de naam wordt weergegeven in de gegevensindeling of wordt gebruikt in een formule.
* De gegevensbron wordt automatisch uit de service geladen wanneer de app wordt geladen.  U kunt de gegevens geforceerd vernieuwen met behulp van de functie **[Refresh](functions/function-refresh.md)**.
* Wanneer gebruikers een app uitvoeren, kunnen zij records maken, wijzigen en verwijderen, en die wijzigingen terugkoppelen naar de onderliggende tabel in de service.
  * Records kunnen worden gemaakt met de functies **[Patch](functions/function-patch.md)** en **[Collect](functions/function-clear-collect-clearcollect.md)**.  
  * Records kunnen worden gewijzigd met de functies **[Patch](functions/function-patch.md)**, **[Update](functions/function-update-updateif.md)** en **[UpdateIf](functions/function-update-updateif.md)**.
  * Records kunnen worden verwijderd met de functies **[Remove](functions/function-remove-removeif.md)** en **[RemoveIf](functions/function-remove-removeif.md)**.
  * Fouten die optreden bij het werken met een gegevensbron zijn beschikbaar via de functie **[Errors](functions/function-errors.md)**.
* De functies **[DataSourceInfo](functions/function-datasourceinfo.md)**, **[Defaults](functions/function-defaults.md)** en **[Validate](functions/function-validate.md)** bevatten informatie over de gegevensbron die u kunt gebruiken voor het optimaliseren van de gebruikerservaring.

### <a name="creating-data-sources"></a>Gegevensbronnen maken
PowerApps kan niet worden gebruikt om een verbonden gegevensbron te maken of de structuur te wijzigen. De gegevensbron moet al ergens in een service bestaan. Bijvoorbeeld, voor het maken van een tabel in een Excel-werkmap die is opgeslagen op OneDrive, moet u eerst Excel Online op OneDrive gebruiken om een werkmap te maken. Vervolgens maakt u er een verbinding naartoe vanuit uw app.  

Gegevensbronnen voor verzamelingen *kunnen* echter worden gemaakt en gewijzigd in een app, maar deze gegevensbronnen zijn alleen tijdelijk.

### <a name="display-one-or-more-records"></a>Een of meer records weergeven
![](media/working-with-data-sources/reading-from-a-datasource.png) Het bovenstaande diagram toont de informatiestroom wanneer een app de gegevens in een gegevensbron leest:

* De informatie wordt opgeslagen en gedeeld via een opslagservice (in dit geval een SharePoint-lijst van een Office 365-site).
* Via een verbinding wordt deze informatie beschikbaar voor de app.  De verbinding zorgt voor verificatie van de gebruiker voor toegang tot de gegevens.
* Wanneer de app wordt gestart of de functie **[Refresh](functions/function-refresh.md)** wordt gebruikt, worden er gegevens opgehaald vanuit de verbinding naar een gegevensbron voor lokaal gebruik in de app.
* Formules worden gebruikt om de informatie te lezen en weer te geven in de besturingselementen die de gebruiker kan zien. U kunt de records van een gegevensbron weergeven met behulp van een galerie op een scherm en de eigenschap **[Items](controls/properties-core.md)** te verbinden met de gegevensbron: **Gallery.Items = DataSource**.  U kunt besturingselementen binnen de galerie en aan de galerie verbinden met behulp van de eigenschap **[Default](controls/properties-core.md)** van het besturingselement.  
* De gegevensbron is ook een tabel.  U kunt dus de functies **[Filter](functions/function-filter-lookup.md)**, **[Sort](functions/function-sort.md)**, **[AddColumns](functions/function-table-shaping.md)** en andere functies gebruiken om de gegevensbron te verfijnen en te verbeteren voordat u deze als geheel gebruikt.  U kunt ook de functies **[Lookup](functions/function-filter-lookup.md)**, **[First](functions/function-first-last.md)**, **[Last](functions/function-first-last.md)** en andere functies gebruiken om te werken met afzonderlijke records.

### <a name="modify-a-record"></a>Een record wijzigen
In de vorige sectie hebt u gezien hoe u een gegevensbron moet lezen.  Houd er rekening mee dat de pijlen in het bovenstaande diagram één richting hebben.  Wijzigingen aan een gegevensbron worden niet via dezelfde formules tegengehouden waarmee de gegevens zijn opgehaald.  In plaats daarvan worden nieuwe formules gebruikt.  Vaak wordt een andere scherm gebruikt voor het bewerken van een record dan voor het zoeken naar records, met name op een mobiel apparaat.

Voor het wijzigen van een bestaande record van een gegevensbron, moet de record oorspronkelijk afkomstig zijn van de gegevensbron.  De record kan door een galerie, [contextvariabele](working-with-variables.md#create-a-context-variable) en een willekeurig aantal formules zijn gegaan, maar de oorsprong moet kunnen worden teruggeleid naar de gegevensbron.  Dit is belangrijk omdat er meer informatie wordt verzonden met de record waarmee deze kan worden aangeduid, wat ervoor zorgt dat u de juiste record wijzigt.    

![](media/working-with-data-sources/writing-to-a-datasource.png) Het bovenstaande diagram toont de informatiestroom voor het bijwerken van een gegevensbron:

* Een besturingselement **[Formulier bewerken](controls/control-form-detail.md)** biedt een container voor invoerkaarten, die bestaan uit besturingselementen voor gebruikersinvoer, zoals een besturingselement voor tekstinvoer of een schuifregelaar.  De eigenschappen **[DataSource](controls/control-form-detail.md)** en **[Item](controls/control-form-detail.md)** worden gebruikt voor identificatie van de record om deze te kunnen bewerken.
* Elke invoerkaart bevat een eigenschap **[Standaard](controls/properties-core.md)** die meestal is ingesteld op het veld van de record **ThisItem** van het formulier.  De besturingselementen in de invoerkaart halen vervolgens hun invoerwaarden uit **[Standaard](controls/properties-core.md)**.  Normaal gesproken hoeft u dit niet te wijzigen.
* Elk invoerkaart toont een eigenschap **[Update](controls/control-card.md)**.  Deze eigenschap wijst de invoer van de gebruiker toe aan een bepaald veld van de record voor terugschrijven naar de gegevensbron.  Normaal gesproken hoeft u dit niet te wijzigen.
* Een knop of een afbeeldingsbesturingselement op het scherm stelt de gebruiker in staat om de wijzigingen op te slaan in de record.  De formule **[OnSelect](controls/properties-core.md)** van het besturingselement zorgt ervoor dat de functie **[SubmitForm](functions/function-form.md)** dit uitvoert.  **[SubmitForm](functions/function-form.md)** leest alle **[Update](controls/control-card.md)**-eigenschappen van de kaarten en gebruikt dit voor terugschrijven naar de gegevensbron.
* Soms zullen er problemen optreden.  Een netwerkverbinding kan niet actief zijn of er wordt door de service een validatiecontrole uitgevoerd waar de app niets van wist.  De eigenschappen **Fout** en **[ErrorKind](controls/control-form-detail.md)** van het formulierbesturingselement stellen deze informatie beschikbaar zodat u deze aan de gebruiker kunt weergeven.  

Voor gedetailleerdere controle over het proces kunt u ook de functies **[Invullen](functions/function-patch.md)** en **[Fouten](functions/function-errors.md)** gebruiken.  Het besturingselement **[Formulier bewerken](controls/control-form-detail.md)** toont een **[Updates](controls/control-form-detail.md)**-eigenschap zodat u de waarden van de velden in het formulier kunt lezen.  U kunt deze eigenschap ook gebruiken om een aangepaste connector voor een verbinding aan te roepen, waarbij u volledig buiten de functies **Patch** en **SubmitForm** om werkt.

### <a name="validation"></a>Validatie
Voordat u een wijziging aanbrengt aan een record, moet de app eerst al het mogelijke doen om ervoor te zorgen dat de wijziging kan worden geaccepteerd.  Hiervoor zijn twee redenen:

* *Onmiddellijke feedback aan de gebruiker*.  Het beste moment om een probleem te verhelpen is wanneer het gebeurt, wanneer het nog vers in het geheugen van de gebruiker ligt.  Bij letterlijk elke tik of toetsaanslag kan er rode tekst worden weergegeven die een probleem identificeert met de plaatsing.
* *Minder netwerkverkeer en minder gebruikerslatentie*.  Meer problemen gedetecteerd in de app betekent minder conversaties via het netwerk voor het detecteren en oplossen van problemen.  Elke conversatie kost tijd waarin de gebruiker moet wachten voordat hij verder kan.

PowerApps biedt twee hulpprogramma's voor validatie:

* De gegevensbron kunt informatie bieden over wat wel en niet geldig is.  Getallen kunnen bijvoorbeeld minimale en maximale waarden hebben en er kunnen een of meer vermeldingen zijn vereist.  U kunt toegang krijgen tot deze gegevens met de functie **[DataSourceInfo](functions/function-datasourceinfo.md)**.  
* De functie **[Validate](functions/function-validate.md)** maakt gebruikt van deze informatie om de waarde van één kolom of een hele record te controleren.

### <a name="error-handling"></a>Foutafhandeling
Geweldig, u hebt uw record gevalideerd.  Tijd om die record met **[Patch](functions/function-patch.md)** bij te werken.

Maar helaas is er nog steeds mogelijk een probleem.  Het netwerk is niet beschikbaar, validatie van de service is mislukt, of de gebruiker heeft niet de juiste machtigingen: een aantal mogelijke fouten die uw app kan tegenkomen.  De app moet op de juiste wijze op situaties reageren, feedback geven aan de gebruiker en hem de mogelijkheid geven om het op te lossen.  

Wanneer er fouten optreden met een gegevensbron, registreert uw app automatisch de gegevens van de fout en maakt deze beschikbaar via de functie **[Errors](functions/function-errors.md)**.  Fouten worden gekoppeld aan de records waarbij problemen zijn opgetreden.  Als het probleem iets is dat kan worden opgelost door de gebruiker, zoals een validatieprobleem, kan de gebruiker de record opnieuw verzenden en worden de fouten gewist.

Als er een fout optreedt bij het maken van een record met **[Patch](functions/function-patch.md)** of **[Collect](functions/function-clear-collect-clearcollect.md)** is er geen record waarmee fouten kunnen worden gekoppeld.  In dit geval wordt *leeg* geretourneerd door **[Patch](functions/function-patch.md)** en kan worden gebruikt als het record-argument voor **[Errors](functions/function-errors.md)**.  Fouten bij het maken worden met de volgende bewerking gewist.

De functie **[Errors](functions/function-errors.md)** retourneert een tabel met gegevens van de fout.  Deze informatie kan bestaan uit de kolomgegevens indien de fout kan worden toegekend aan een bepaalde kolom.  Gebruik foutberichten op kolomniveau in labelbesturingselementen die zich bevinden vlak bij waar de kolom zich op het scherm Bewerken bevindt.  Gebruik foutberichten op record-niveau waar de **Kolom** in de fouttabel *leeg* is, en zich op een locatie dicht bij de knop **Opslaan** voor de hele record bevindt.  

### <a name="working-with-large-data-sources"></a>Werken met grote gegevensbronnen
Wanneer u rapporten maakt van grote hoeveelheden gegevensbronnen (wel miljoenen records), dan wilt u netwerkverkeer zoveel mogelijk minimaliseren. Stel dat u wilt een rapport wilt over alle klanten die een StatusCode 'Platina' hebben in de stad New York. En dat uw klantentabel miljoenen records bevat.

U wilt die miljoenen klanten **zeker niet** in uw app laden en vervolgens kiezen welke u wilt. U wilt dat deze selectie in de cloudservice gebeurt waar de tabel wordt opgeslagen, en alleen de gekozen records via het netwerk verzenden.

U kunt veel, maar niet alle, functies voor het kiezen van records *delegeren*. Dit betekent dat deze worden uitgevoerd in de cloudservice. U kunt leren hoe u dit doe door te lezen over [Delegering](delegation-overview.md).

## <a name="collections"></a>Verzamelingen
Verzamelingen zijn een speciaal soort gegevensbron.  Deze staan lokaal in de app en worden niet ondersteund door een verbinding met een service in de cloud. Daarom kunnen de gegevens niet worden gedeeld met apparaten voor dezelfde gebruiker of tussen gebruikers.  Zij werken net als elke andere gegevensbron, met enkele uitzonderingen:

* Verzamelingen kunnen dynamisch worden gemaakt met de functie **[Collect](functions/function-clear-collect-clearcollect.md)**.  Deze hoeven niet van te voren tot stand te worden gebracht op de manier zoals bij gegevensbronnen op basis van een verbinding.
* De kolommen van een verzameling kunnen op elk moment worden gewijzigd met behulp van de functie **[Collect](functions/function-clear-collect-clearcollect.md)**.
* Verzamelingen staan het bestaan van dubbele records toe.  Er kan meer dan één exemplaar van dezelfde record bestaan in een verzameling.  Functies zoals **[Remove](functions/function-remove-removeif.md)** worden uitgevoerd op de eerste overeenkomst die ze vinden, tenzij het argument **Alle** wordt opgegeven.
* U kunt de functies **[SaveData](functions/function-savedata-loaddata.md)** en **[LoadData](functions/function-savedata-loaddata.md)** gebruiken om een kopie van de verzameling op te slaan en opnieuw te laden.  De informatie wordt opgeslagen op een persoonlijke locatie die niet toegankelijk is voor andere gebruikers, apps of apparaten.
* U kunt de besturingselementen **[Exporteren](controls/control-export-import.md)** en **[Importeren](controls/control-export-import.md)** gebruiken om een kopie van de verzameling naar een bestand waarmee de gebruiker kan communiceren op te slaan en opnieuw te laden.  

Zie voor meer informatie over werken met een verzameling als een gegevensbron [Een verzameling maken en bijwerken](create-update-collection.md).

Verzamelingen worden vaak gebruikt voor het opslaan van de algemene status van de app.  Zie [Werken met variabelen](working-with-variables.md) voor de opties die beschikbaar zijn voor het beheren van de status.

