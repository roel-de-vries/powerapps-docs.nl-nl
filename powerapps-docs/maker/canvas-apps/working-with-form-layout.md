---
title: De indeling van een gegevensformulier begrijpen | Microsoft Docs
description: Overzichtelijke formulieren maken met behulp van rijen en kolommen.
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/17/2017
ms.author: gregli
ms.openlocfilehash: 79b14972d5900b7a84e7634eb57fac24e243bd46
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="understand-data-form-layout-in-microsoft-powerapps"></a>De indeling van een gegevensformulier begrijpen in Microsoft PowerApps
Met PowerApps kunt u gemakkelijk formulieren maken die er mooi uitzien en efficiënt te gebruiken zijn. Neem bijvoorbeeld dit eenvoudige verkooporderformulier:

![Voorbeeld van verkooporderformulier](./media/working-with-form-layout/sales-order.png)

In deze zelfstudie nemen we de stappen door die nodig zijn om dit formulier te maken. We kijken ook naar een paar geavanceerde onderwerpen, zoals het dynamisch schalen van velden om de beschikbare ruimte te vullen.

## <a name="before-you-start"></a>Voordat u begint
Als u niet vertrouwd bent met PowerApps (of apps alleen automatisch hebt gegenereerd), moet u [ een volledig nieuwe app bouwen](get-started-create-from-blank.md) voordat u in dit onderwerp duikt. Door een volledig nieuwe app te bouwen raakt u vertrouwd met vereiste concepten, zoals het toevoegen van gegevensbronnen en besturingselementen, die in dit onderwerp worden genoemd, maar niet verder uitgelegd.

## <a name="add-a-gallery"></a>Een galerie toevoegen
1. Maak een volledig nieuwe tablet-app.
   
    Alles wat in dit onderwerp wordt besproken, geldt ook voor de telefoonindeling, maar telefoon-apps hebben vaak maar één verticale kolom.
2. Voeg de entiteit **Sales order** in de [Common Data Service](../common-data-service/data-platform-intro.md) toe als gegevensbron voor de app.
   
    Buiten deze zelfstudie kunt u elke gegevensbron gebruiken, met inbegrip van de SharePoint-lijsten en Excel-tabellen.
3. Voeg een verticaal besturingselement **Galerie** toe en stel de eigenschap **Items** in op **'Verkooporder'**.
   
    (optioneel) Wijzig de **Lay-out** van de galerie om alleen de **Titel en subtitel** weer te geven zodat deze overeenkomen met de voorbeelden in deze zelfstudie.
   
    ![Lijst met verkooporders](./media/working-with-form-layout/gallery-layout.png)
4. Tik of klik in de galerie op **SO004**.
   
    ![Lijst met verkooporders](./media/working-with-form-layout/sales-order-gallery-screen.png)
   
    Dit record wordt weergegeven in het formulier dat u bouwt door stappen verderop in dit onderwerp te volgen.

## <a name="add-a-title-bar"></a>Titelbalk toevoegen
1. Voeg een leeg scherm toe waar u het formulier moet plaatsen.
   
    Buiten deze zelfstudie kunt u de besturingselementen **Galerie** en **[Formulier bewerken](controls/control-form-detail.md)** op hetzelfde scherm plaatsen, maar u hebt meer werkruimte als u ze op afzonderlijke schermen plaatst.
2. Voeg een **[Label](controls/control-text-box.md)**besturingselement toe bovenaan het nieuwe scherm en stel de eigenschap **Text** in op deze expressie:
   <br>**"Verkooporder " & Gallery1.Selected.SalesOrderId**
   
    Het label toont het ordernummer van het record dat u hebt geselecteerd in de galerie.
3. (optioneel) Maakt het label als volgt op:
   
    1. Stel de eigenschap **Align** in op **Center**.
   
    2. Stel de eigenschap **Size** in op **20**.
   
    3. Stel de eigenschap **Fill** in op **Navy**.
   
    4. Stel de eigenschap **Color** in op **White**.
   
    5. Stel de eigenschap **Width** in op **Parent.Width**.
   
    6. Stel de eigenschappen **X** en **Y**in op **0**.
      
      ![Titelbalk](./media/working-with-form-layout/title-bar.png)

## <a name="add-a-form"></a>Een formulier toevoegen
1. Voeg een besturingselement **Formulier bewerken** toe, verplaats het en wijzig de grootte tot het het volledige scherm onder het label vult.
   
    In de volgende stap maakt u verbinding tussen het besturingselement en de gegevensbron **Verkooporder** met behulp van het rechterdeelvenster, niet de formulebalk. Als u de formulebalk gebruikt, worden standaard geen velden weergegeven in het formulier. U kunt altijd alle gewenste velden weergeven door een of meer selectievakjes in het rechterdeelvenster te selecteren.
2. Klik of tik in het rechterdeelvenster op de Pijl-omlaag naast **Geen gegevensbron geselecteerd** en klik of tik vervolgens op **Verkooporder**.
   
    Een standaardreeks velden uit de gegevensbron **Verkooporder** wordt weergegeven in een eenvoudige indeling met drie kolommen. Veel zijn er echter leeg, en het kan even duren voor ze op hun uiteindelijke posities staan.  
3. Stel de eigenschap **Item** van het formulier in op **Gallery1.Selected**.
   
    Het formulier toont het record dat u hebt geselecteerd in de galerie, maar de standaardreeks velden komt mogelijk niet overeen met wat u in uw uiteindelijke product wilt.
4. Verberg elk van deze velden in het rechterdeelvenster door het selectievakje uit te schakelen:
   
   * **Verkoopordernummer**
   * **Account**
   * **Verkoper**
   * **Accountcontact**
5. Verplaats het veld **Orderstatus** door het naar links te slepen en het vervolgens neer te zetten aan de andere kant van het veld **Klantorderreferentie**.
   
    Het scherm moet lijken op het volgende voorbeeld:
   
    ![Verkooporder in een basisindeling met drie kolommen](./media/working-with-form-layout/sales-order-form-screen-3.png)

## <a name="select-a-data-card"></a>Selecteer een gegevenskaart
Elk weergegeven veld heeft een bijbehorende gegevenskaart op het formulier. Deze kaart omvat een set besturingselementen voor de titel van het veld, een invoervak, een ster (die wordt weergegeven als het veld vereist is) en een validatiefoutbericht.

U kunt ook rechtstreeks op het formulier kaarten selecteren. Als u een kaart selecteert, wordt erboven een zwart bijschrift weergegeven.

![Geselecteerde gegevenskaart](./media/working-with-form-layout/sales-order-data-card-selection.png)

> [!NOTE]
> Om een kaart te verwijderen (niet alleen te verbergen), selecteert u deze en drukt u vervolgens op Delete.

## <a name="arrange-cards-in-columns"></a>Kaarten in kolommen rangschikken
Standaard hebben formulieren in tablet-apps drie kolommen, en die in telefoonapps hebben er één. U kunt niet alleen het aantal kolommen in een formulier opgeven, maar ook of alle kaarten binnen de kolomgrenzen moeten passen.

In deze afbeelding is het aantal kolommen in het formulier gewijzigd van drie naar vier met het selectievakje **Uitlijnen op kolommen** geselecteerd. De kaarten in het formulier zijn automatisch gerangschikt om in de nieuwe indeling te passen.

![Verkooporder in basisindeling met vier kolommen](./media/working-with-form-layout/sales-order-form-screen-4.png)

## <a name="resize-cards-across-multiple-columns"></a>Formaat van kaarten aanpassen in meerdere kolommen
Afhankelijk van de gegevens op elke kaart wilt u misschien dat sommige kaarten in één kolom passen en andere kaarten meerdere kolommen in beslag nemen. Als een kaart meer gegevens bevat dan u wilt weergeven in één kolom, kunt u de kaart breder maken door deze te selecteren en vervolgens de handgreep op de rechter- of linkerrand van het selectievakje te slepen. Terwijl u de greep sleept, wordt de kaart uitgelijnd op kolomgrenzen.

Als u ervoor wilt zorgen dat uw ontwerp flexibeler is, maar een bepaalde structuur behoudt, kunt u het aantal kolommen verhogen naar 12. Met deze wijziging kunt u eenvoudig configureren dat elke kaart het volledige formulier, de helft van het formulier, een derde, een kwart, een zesde, enzovoorts bedekt. Laten we dit in actie zien.

1. Stel in het formulier in het rechterdeelvenster het aantal kolommen in op **12**.
   
    ![Aantal kolommen specificeren](./media/working-with-form-layout/12-columns.png)
   
    Het formulier verandert niet zichtbaar, maar u hebt meer uitlijnpunten als u de linker- of rechtergreep sleept.
2. Wijzig de breedte van de kaart **Orderdatum** door de rechterhandgreep naar het eerstvolgende uitlijnpunt aan de rechterkant te slepen.
   
    De kaart bedekt vier van 12 kolommen van het formulier (of 1/3 van het formulier), in plaats van slechts drie van de 12 kolommen van het formulier (of 1/4 van het formulier). Wanneer u een kaart uitbreidt met één uitlijnpunt, bedekt de kaart een extra 1/12 van het formulier.
   
    ![Het formaat van een kaart wijzigen met slepen en neerzetten](./media/working-with-form-layout/card-resize-1.png)
3. Herhaal de vorige stap met de kaarten **Bestelstatus** en **Klantorderreferentie**.
   
    ![Drie kaarten in de eerste rij](./media/working-with-form-layout/card-resize-2.png)

4. Pas het formaat van de kaarten **Naam** en **Beschrijving** aan, zodat er zes kolommen (of 1/2) van het formulier worden bedekt.

5. We laten de eerste twee regels van het bezorgadres over de hele breedte van het formulier lopen:

Dat is alles. Ons formulier is klaar, met een combinatie van rijen met verschillende aantallen kolommen:

![Verkooporder in indeling met 12 kolommen met aangepaste veldgrootte](./media/working-with-form-layout/card-resize-done.png)

## <a name="manipulate-controls-in-a-card"></a>Besturingselementen in een kaart bewerken
Het bezorgadres bevat verschillende soorten gegevens die we visueel willen groeperen voor de gebruiker. Elk veld blijft deel uitmaken van de eigen gegevenskaart, maar we kunnen de besturingselementen binnen de kaart manipuleren, zodat ze beter bij elkaar passen.

1. Selecteer de kaart **Eerste regel van het bezorgadres**, selecteer het label in deze kaart en verwijder vervolgens de eerste drie woorden uit de tekst.
   
    ![Tekst van eerste regel van afleveradres wijzigen](./media/working-with-form-layout/delivery-address-rename.png)
2. Selecteer de kaart **Tweede regel van het bezorgadres**, selecteer het label in deze kaart en verwijder vervolgens alle tekst.
   
    Het kan verleidelijk zijn om gewoon het labelbesturingselement verwijderen en in de meeste gevallen kan dat ook prima. De kans bestaat echter dat er formules in het formulier afhankelijk zijn van de aanwezigheid van dit besturingselement. Een veiligere aanpak is om de tekst te verwijderen of de eigenschap **Visible** van het besturingselement in te stellen op **false**.
   
    ![Tekst van tweede regel van afleveradres wijzigen](./media/working-with-form-layout/delivery-address-rename-2.png)
3. Verplaats in dezelfde kaart het invoervak over het label om de afstand tussen de eerste en tweede regel van het adres te verkleinen.
   
    De hoogte van de kaart wordt kleiner als de inhoud ervan minder ruimte inneemt.
   
    ![Tekst van tweede regel van afleveradres wijzigen](./media/working-with-form-layout/delivery-address-move-input.png)

Dan gaan we nu verder met de derde adresregel. Net als bij de andere adresregels, gaan we de tekst van de labels voor deze kaarten inkorten en plaatsen we het Tekstinvoervak rechts van elk label. Dit zijn de stappen voor de kaart **Staat**:

| Stap | Beschrijving | Resultaat |
| --- | --- | --- |
| 1 |Selecteer de kaart **Staat** zodat er selectiegrepen worden weergegeven rond de kaart. |![Een kaart selecteren](./media/working-with-form-layout/state-morph-2.png) |
| 2 |Selecteer het label in de kaart zodat er rondom selectiegrepen worden weergegeven. |![Een besturingselement selecteren binnen een kaart](./media/working-with-form-layout/state-morph-3.png) |
| 3 |Plaats de cursor rechts van de tekst en verwijder vervolgens het gedeelte dat we niet nodig hebben. |![De tekst in een besturingselement binnen een kaart wijzigen](./media/working-with-form-layout/state-morph-3b.png) |
| 4 |Gebruik de selectiegrepen aan de zijkant om het formaat van het labelbesturingselement aan te passen aan de nieuwe tekstgrootte. |![Het formaat van een besturingselement binnen een kaart wijzigen](./media/working-with-form-layout/state-morph-4b.png) |
| 5 |Selecteer het besturingselement voor tekstinvoer binnen deze kaart. |![Een ander besturingselement selecteren binnen de kaart](./media/working-with-form-layout/state-morph-6.png) |
| 6 |Gebruik de selectiegrepen aan de zijkanten om het formaat van het tekstinvoerbesturingselement aan te passen. |![Het formaat van een besturingselement binnen een kaart wijzigen](./media/working-with-form-layout/state-morph-6b.png) |
| 7 |Sleep het tekstinvoervak omhoog en rechts van het labelbesturingselement en zet het tekstinvoervak vervolgens neer. |![Een besturingselement verplaatsen binnen een kaart](./media/working-with-form-layout/state-morph-7b.png) |
| De kaart **Staat** is nu klaar. |![De kaart 'State' is nu klaar](./media/working-with-form-layout/state-morph-8.png) | |

De derde adresregel ziet er nu zo uit:

![Afleveradres met een meer beknopte derde regel](./media/working-with-form-layout/delivery-address-resize-city-1.png)

Houd er rekening mee dat veel van de kaarten standaard dynamische formules gebruiken voor hun eigenschappen. Het besturingselement voor tekstinvoer waarvoor we hierboven de grootte en positie hebben aangepast, had bijvoorbeeld een eigenschap **Width** op basis van de breedte van het bovenliggende besturingselement. Als u een besturingselement verplaatst of het formaat aanpast, worden deze dynamische formules vervangen door statische waarden. Desgewenst kunt u de dynamische formules herstellen met behulp van de formulebalk.

## <a name="turning-off-snap-to-columns"></a>Kaarten niet uitlijnen op kolommen
Soms is het handig om nog meer controle te hebben dan mogelijk is met het standaardaantal kolommen van 12. Voor deze gevallen kunt u **Uitlijnen op kolommen** uitschakelen en de kaarten handmatig positioneren. Het formulier wordt nog steeds uitgelijnd op 12 kolommen, maar u kunt ook de Alt-toets ingedrukt houden om de positie en grootte van een kaart handmatig te wijzigen.

In ons voorbeeld hebben de vier onderdelen die de derde adresregel vormen, allemaal exact dezelfde breedte. Maar dit hoeft niet per se de beste indeling te zijn, aangezien plaatsnamen vaak langer zijn dan de afkortingen van staten en het Tekstinvoervak voor land/regio kort is vanwege de lengte van het label.

Schakel **Uitlijnen op kolommen** in het rechterdeelvenster uit om deze ruimte te optimaliseren en houd vervolgens de Alt-toets ingedrukt terwijl u deze kaarten dimensioneert en plaatst. Zolang u de Alt-toets ingedrukt houdt, worden bij alle besturingselementen zwarte bijschriften weergegeven. Dit gedrag is zo ontworpen om u de namen van besturingselementen te tonen.

![Positie en grootte aanpassen met de Alt-toets ingedrukt](./media/working-with-form-layout/delivery-address-alt-resize.png)

Na zorgvuldige positionering van de kaarten, hebben de velden allemaal de juiste grootte, met een gelijke horizontale afstand tussen de velden:

![Derde regel van afleveradres met handmatig geplaatste velden](./media/working-with-form-layout/delivery-address-resize-city-2.png)

Kortom, wat zijn de verschillen tussen het wel of niet **Uitlijnen op kolommen**?

| Gedrag | Uitlijnen op kolommen AAN | Uitlijnen op kolommen UIT |
| --- | --- | --- |
| Formaatwijziging door uitlijnen op |Aantal geselecteerde kolommen:<br>(1, 2, 3, 4, 6 of 12) |12 kolommen |
| Automatische uitlijning kan worden onderdrukt |Nee |Ja, met de Alt-toets |
| De indeling van kaarten wordt automatisch aangepast tussen de rijen (hierover later meer) |Ja |Nee |

## <a name="set-width-and-height"></a>Breedte en hoogte instellen
Net als met alles in PowerApps, wordt de indeling van het formulier bepaald door eigenschappen in de besturingselementen van een kaart. Zoals al beschreven, kunt u de waarden van deze eigenschappen wijzigen door besturingselementen naar verschillende locaties te slepen of selectiegrepen te slepen om de grootte van besturingselementen aan te passen. Maar u ontdekt ook situaties waarin u deze eigenschappen beter wilt begrijpen en zelf preciezer wilt manipuleren, vooral wanneer u met behulp van formules dynamische formulieren maakt.

### <a name="basic-layout-x-y-and-width"></a>Basisindeling: X, Y en Width
De eigenschappen **X** en **Y** bepalen de positie van kaarten. Wanneer we met besturingselementen op het canvas werken, geven deze eigenschappen een absolute positie aan. Op een formulier hebben deze eigenschappen een andere betekenis:

* **X**: volgorde binnen een rij.
* **Y**: rijnummer.

Vergelijkbaar met besturingselementen op het canvas, bepaalt de eigenschap **Width** de minimale breedte van de kaart (verderop meer hierover).

Laten we eens kijken naar de eigenschappen **X**, **Y** en **Width** van de kaarten op ons formulier:

![X- en Y-coördinaten op verkooporderformulier](./media/working-with-form-layout/sales-order-xy.png)

### <a name="overflowing-rows"></a>Overlopende rijen
Wat gebeurt er als de kaarten op een rij te breed zijn voor de rij? Normaal gesproken hoeft u zich geen zorgen te maken over deze mogelijkheid. Als de optie **Uitlijnen op kolommen** is ingeschakeld, worden deze drie eigenschappen automatisch aangepast zodat alles mooi in de rijen past, zonder overloop.

Maar als deze functie **Uitlijnen op kolommen** is uitgeschakeld of een of meer kaarten een formule met **Width** bevatten, kan er overloop van een rij plaatsvinden. In dit geval lopen kaarten automatisch door en wordt er in feite een nieuwe rij gemaakt. Laten we bijvoorbeeld handmatig de waarde van de eigenschap **Width** van de kaart **Klantorderreferentie** (eerste rij, derde item) wijzigen in **500**:

![Handmatig het formaat van een kaart wijzigen voor overloop naar nieuwe rij](./media/working-with-form-layout/manual-size-500.png)

De drie kaarten op de bovenste rij passen niet meer in de horizontale ruimte en er is een nieuwe rij gemaakt om de overloop op te vangen. Het **Y**-coördinaat voor al deze kaarten is nog steeds 0, en de kaarten **Naam** en **Beschrijving** hebben nog steeds de waarde 1 voor **Y**. Kaarten die verschillende **Y**-waarden hebben worden niet samengevoegd in rijen.

U kunt dit gedrag inzetten om een volledig dynamische indeling te maken waarin kaarten worden geplaatst volgens een Z-volgorde, waarbij de horizontale ruimte zo veel mogelijk wordt opgevuld voordat er naar de volgende rij wordt gegaan. Om dit effect te bereiken, geeft u alle kaarten dezelfde **Y**-waarde en gebruikt u **X** voor de volgorde van de kaarten.

### <a name="filling-spaces-widthfit"></a>Ruimten opvullen: WidthFit
De overloop in het laatste voorbeeld resulteert in een ruimte na de kaart **Orderstatus**, de tweede kaart van de eerste rij. We kunnen dit oplossen door handmatig de eigenschap **Width** van de twee resterende kaarten aan te passen om deze ruimte op te vullen, maar dit is nogal omslachtig.

Een betere oplossing is om de eigenschap **WidthFit** te gebruiken. Als deze eigenschap is ingesteld op **true** voor een of meer kaarten op een rij, wordt eventuele witruimte op de rij evenredig verdeeld over de kaarten. Daarom hebben we eerder specifiek gezegd dat de eigenschap **Width** van een kaart een *minimale* waarde vertegenwoordigt. In de praktijk kan een kaart echter breder worden weergegeven. Door deze eigenschap wordt een kaart nooit verkleind, alleen uitgebreid.

Als we **WidthFit** op **true** hebben ingesteld op de kaart **Orderstatus**, wordt de beschikbare ruimte ingevuld terwijl de eerste kaart ongewijzigd blijft:

![WidthFit ingesteld op 'true' voor tweede kaart](./media/working-with-form-layout/manual-widthfit-1.png)

Als we **WidthFit** ook op **true** instellen voor de kaart **Orderdatum**,wordt de beschikbare ruimte gelijkmatig verdeeld over beide kaarten:

![WidthFit ingesteld op 'true' voor eerste en tweede kaart](./media/working-with-form-layout/manual-widthfit-2.png)

Houd er rekening mee dat selectiegrepen van deze kaarten rekening houden met de extra breedte die wordt verkregen met **WidthFit**, niet met de minimumbreedte die wordt verkregen met de eigenschap **Width**. Het kan verwarrend zijn om de eigenschap **Width** aan te passen terwijl **WidthFit** is ingeschakeld. U kunt de eigenschap daarom uitschakelen, **Width** wijzigen en dan de eigenschap weer inschakelen.

Wanneer kan **WidthFit** nuttig zijn? Als u een veld hebt dat alleen in bepaalde situaties wordt gebruikt, kunt u de eigenschap **Visible** van het veld instellen op **false**, zodat de andere kaarten in de rij automatisch de vrije ruimte rond het veld opvullen. U kunt een formule gebruiken waarmee een veld alleen wordt weergegeven als een ander veld een bepaalde waarde heeft.

Hier stellen we de eigenschap **Visible** van het veld **Orderstatus** in op de statische waarde **false**:

![WidthFit ingesteld op 'true' voor eerste kaart met het veld 'Order status' onzichtbaar](./media/working-with-form-layout/manual-widthfit-3.png)

Doordat de tweede kaart niet wordt weergegeven, kan de derde kaart nu weer in dezelfde rij als de eerste kaart worden weergegeven. De eigenschap **WidthFit** voor de eerste kaart is nog steeds ingesteld op **true**, dus wordt alleen deze kaart uitgebreid om de beschikbare ruimte op te vullen.

Omdat **Orderstatus** onzichtbaar is, kan deze niet zo gemakkelijk worden geselecteerd op het canvas. U kunt echter elk besturingselement, zichtbaar of niet, in een hiërarchische lijst van de besturingselementen aan de linkerkant van het scherm selecteren.

### <a name="height"></a>Height
De eigenschap **Height** bepaalt de hoogte van een kaart. Kaarten hebben een variant van **WidthFit** voor **Height** en deze eigenschap is altijd ingesteld op **true**. Stel dat er een eigenschap **HeightFit** bestaat, maar zoek er niet naar in het product omdat een dergelijke eigenschap nog niet wordt weergegeven.

U kunt dit gedrag niet uitschakelen, waardoor het aanpassen van de hoogte van kaarten lastig kan zijn. Alle kaarten in een rij worden weergegeven met de hoogte van de grootste kaart. Een rij kan er als volgt uitzien:

![WidthFit ingesteld op 'true' voor de eerste kaart met het veld 'Orderstatus' onzichtbaar](./media/working-with-form-layout/height-3.png)

Welke kaart is bepalend voor de rijhoogte? In de vorige afbeelding is de kaart **Totaalbedrag** geselecteerd en lijkt deze hoog, maar de eigenschap **Height** van de kaart is ingesteld op **80** (hetzelfde als de hoogte van de eerste rij). Als u de hoogte van een rij wilt verkleinen, moet u de **Height** van de grootste kaart in die rij verkleinen en u kunt de hoogste kaart niet identificeren zonder de eigenschap **Height** van elke kaart te controleren.

### <a name="autoheight"></a>AutoHeight
Een kaart is mogelijk ook hoger dan verwacht als deze een besturingselement bevat waarvoor de eigenschap **AutoHeight** is ingesteld op **true**. Veel kaarten bevatten bijvoorbeeld een label waarmee een foutbericht wordt weergegeven als de waarde van het veld een validatieprobleem veroorzaakt.

Als er geen tekst is om weer te geven (geen fout), wordt het label ingeklapt tot een hoogte van nul. U kunt dan met een enkele mogelijkheid zien dat de kaart ook dit label bevat, tenzij u het label zelf hebt toegevoegd natuurlijk:

![Kaarten die een besturingselement bevatten waarvoor AutoHeight is ingesteld op true, en zonder hoogte worden weergegeven](./media/working-with-form-layout/autoheight-0.png)

De lijst met besturingselementen aan de linkerkant van het scherm, toont **ErrorMessage1**, wat het besturingselement met het foutbericht is. Als u een app bijwerkt, kunt u dit besturingselement selecteren om het een bepaalde hoogte te geven en selectiegrepen te tonen waarmee u kunt de positie en grootte van het besturingselement kunt bewerken. De letter 'A' in een blauw vak geeft aan dat **AutoHeight** is ingesteld op **true** voor het besturingselement:

![Op het moment van ontwerpen hebben besturingselementen met het eigenschap AutoHeight wat hoogte om het besturingselement makkelijker te kunnen slepen](./media/working-with-form-layout/autoheight-1.png)

De eigenschap **Text** van dit besturingselement is ingesteld op **Parent.Error**, waarmee het mogelijk is om op basis van validatieregels dynamische foutberichten weer te geven. Laten we ter illustratie de eigenschap **Text** van dit besturingselement statisch instellen, waardoor de hoogte van het besturingselement (en, daardoor, de hoogte van de kaart) toeneemt en de tekst helemaal kan worden weergegeven:

![Door een foutbericht toe te voegen, worden het besturingselement en dus de kaart automatisch groter](./media/working-with-form-layout/autoheight-2.png)

Laten we het foutbericht iets langer maken. Het besturingselement en de kaart worden automatisch aangepast om de tekst weer te geven. De hoogte van de rij als geheel neemt toe, met behoud van verticale uitlijning tussen de kaarten:

![Met een langer foutbericht worden het besturingselement en de kaart nog groter, waarbij de kaarten in dezelfde rij evenredig hoger worden](./media/working-with-form-layout/autoheight-3.png)

