---
title: Aan de slag met formules | Microsoft Docs
description: Formules gebruiken voor het aanpassen van een app.
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: ed4e83fab0cf5a08c4b274863f11070471fc44a4
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898698"
---
# <a name="get-started-with-formulas"></a>Aan de slag met formules
Configureer de app met formules die niet alleen waarden kunnen berekenen en andere taken uitvoeren (zoals in Excel), maar ook reageren op invoer van gebruikers (zoals van een app vereist).

* In Excel construeert u formules waarmee u bijvoorbeeld cellen kunt vullen en tabellen en grafieken maken.
* In PowerApps maakt u soortgelijke formules terwijl u besturingselementen in plaats van cellen configureert. Daarnaast maakt u formules die specifiek van toepassing zijn op apps in plaats van spreadsheets.

U maakt bijvoorbeeld een formule om vast te stellen hoe uw app reageert als gebruikers een knop selecteren, een schuifregelaar aanpassen of ander invoer opgeven. Deze formules kunnen een ander scherm te zien geven, een gegevensbron bijwerken die extern is voor de app of een tabel maken die een deelverzameling bevat van de gegevens in een bestaande tabel.

U kunt formules maken voor een groot aantal scenario's. U kunt bijvoorbeeld de GPS-functie van uw apparaat gebruiken, een besturingselement voor kaarten en een formule die gebruikmaakt van **Location.Latitude** en **Location.Longitude** om de huidige locatie weer te geven. Op de kaart wordt automatisch uw locatie bijgehouden terwijl u zich verplaatst.

Dit onderwerp geeft slechts een overzicht van het werken met formules. Blader door de [naslag met formules](formula-reference.md) voor meer details en een volledige lijst met functies, operatoren en andere bouwstenen die u kunt gebruiken.

## <a name="prerequisites"></a>Vereisten

* [Registreer u](../signup-for-powerapps.md) voor PowerApps en [meld u vervolgens aan](https://web.powerapps.com) door dezelfde referenties in te voeren die u hebt gebruikt om u te registreren.
* Lees hoe u [een besturingselement kunt configureren](add-configure-controls.md) in PowerApps.

## <a name="show-a-simple-value"></a>Een eenvoudige waarde weergeven
In Excel kunt u bepaalde gegevens, zoals het getal **42** of de woorden **Hello world**, opgeven door deze in een cel te typen. Deze cel toont die gegevens precies zoals u ze erin hebt getypt. In PowerApps kunt u op soortgelijke wijze gegevens opgeven die niet worden gewijzigd, door de eigenschap **[Tekst](controls/properties-core.md)** van een label in te stellen op de exacte volgorde voor de gewenste tekens, ingesloten tussen dubbele aanhalingstekens.

1. Selecteer in het menu **Bestand** (aan de linkerkant van het scherm) de optie **Nieuw**.
2. Selecteer onder **Een app maken**, op de tegel **Blank app**, de optie **Phone layout**.
   
    De formulebalk bevindt zich boven aan het scherm.
   
    ![Formulebalk](./media/working-with-formulas/formula-bar.png)
   
    Deze balk bestaat uit twee delen:
   
   * *Lijst met eigenschappen*: elk besturingselement en elk scherm kent een [verzameling eigenschappen](reference-properties.md).  Gebruik deze lijst om een bepaalde eigenschap te selecteren.  
   * *Formule*: de voor deze eigenschap te berekenen formule, bestaande uit [waarden, operatoren en functies](formula-reference.md).
     
     In de formulebalk kunt u de eigenschappen bekijken of bewerken voor het geselecteerde besturingselement (of voor het scherm als er geen besturingselementen zijn geselecteerd).  U kunt de naam van het geselecteerde besturingselement zien in het tabblad **Inhoud**:
     
     ![Inhoudsbalk met het momenteel geselecteerde besturingselement](./media/working-with-formulas/content-tab-selection.png)
     
     Op het tabblad **Inhoud** kunt u de naam van het geselecteerde besturingselement wijzigen door op de naam te klikken.
3. Voeg een besturingselement **[Label](controls/control-text-box.md)** aan het scherm toe.
   
    ![Een besturingselement voor een tekstvak toegevoegd](./media/working-with-formulas/add-a-label.png)
   
    Als u een label toevoegt, wordt in de lijst met eigenschappen automatisch de eigenschap **[Text](controls/properties-core.md)** getoond, hetgeen aanstuurt wat het besturingselement toont. Standaard is **Tekst** de waarde van deze eigenschap.  
4. Stel de waarde van de eigenschap **[Tekst](controls/properties-core.md)** in op **"Hello world"** door deze tekenreeks in de formulebalk te typen, ingesloten door dubbele aanhalingstekens:
   
    ![Gebruik van het label "Hello world"](./media/working-with-formulas/label-hello-world.png)
   
    Terwijl u deze waarde typt, wordt deze in het label weergegeven.  Terwijl u typt, kunnen in het scherm gele uitroeptekens worden getoond. Deze symbolen geven fouten aan, maar ze verdwijnen als u een geldige waarde hebt ingevoerd. Zo is bijvoorbeeld een tekenreeks zonder dubbele aanhalingstekens aan weerszijden niet geldig.
   
    In Excel kunt u een getal weergeven, bijvoorbeeld **42**, door het in een cel te typen of door een formule te typen die dat getal als resultaat geeft, bijvoorbeeld **=SOM(30;12)**. In PowerApps kunt u hetzelfde resultaat bereiken door de eigenschap **Text** van een besturingselement, zoals een label, in te stellen op **42** of **Sum(30,12)**. In de cel en het label wordt dit getal altijd weergegeven, ongeacht overige wijzigingen aan het werkblad of de app.
   
    > [!NOTE]
   > In PowerApps wordt een formule niet voorafgegaan door een gelijkteken of een plusteken, zoals in Excel wel het geval is. De formulebalk beschouwt alles wat u erin typt standaard als een formule. Een formule wordt ook niet ingesloten tussen dubbele aanhalingstekens (") zoals u gewend bent bij het invoeren van een tekenreeks of tekst.
5. Vervang in de eigenschap **[Text](controls/properties-core.md)** van het label **Hello World** door **Sum(1,2,3)**.
   
    ![Het gedeeltelijke Som(1;2;3 typen zonder haakje sluiten, veroorzaakt een fout](./media/working-with-formulas/label-sum-partial.png)
   
    Terwijl u typt, worden op de formulebalk een beschrijving en de verwachte argumenten voor deze functie getoond.  Net als bij de dubbele aanhalingstekens sluiten in **"Hello World"**, worden op het scherm uitroeptekens weergegeven om een fout aan te geven totdat u het laatste haakje achter de formule hebt ingetypt:
   
    ![Het gebruik van de volledige formule, Som(1;2;3)](./media/working-with-formulas/label-sum.png)

## <a name="change-a-value-based-on-input"></a>Een waarde wijzigen op basis van invoer
In Excel typt u **=SOM(A1:A2)** in een cel als u de som wilt van de waarden in de cellen A1 en A2. Als een van deze waarden (of beide) wordt gewijzigd, dan wordt in de cel met de formule automatisch het bijgewerkte resultaat weergegeven.

![Voorbeeld van een herberekening in Excel waarbij twee getallen worden opgeteld](./media/working-with-formulas/excel-recalc.png)

In PowerApps kunt u een soortgelijk resultaat verkrijgen door besturingselementen toe te voegen en de eigenschappen ervan in te stellen. Dit voorbeeld laat het label uit de vorige procedure zien en twee besturingselementen **[Tekstinvoer](controls/control-text-input.md)**, **Tekstinvoer1** en **Tekstinvoer2** genoemd.

![Voorbeeld van een herberekening in PowerApps waarbij twee getallen worden opgeteld](./media/working-with-formulas/recalc1.png)

Ongeacht de ingevoerde getallen in de besturingselementen voor tekstinvoer, geeft het label altijd de som van die getallen weer omdat de eigenschap **[Text](controls/properties-core.md)** is ingesteld op deze formule:
<br>**Tekstinvoer1 + Tekstinvoer2**

![Voorbeeld van een herberekening in PowerApps waarbij twee getallen worden opgeteld](./media/working-with-formulas/recalc2.png)

In Excel kunt u voorwaardelijke opmaak gebruiken om bijvoorbeeld negatieve waarden in rood weer te geven. In PowerApps gebruikt u een formule die de functie **[Als](functions/function-if.md)** bevat, die zich op soortgelijke wijze gedraagt als in Excel.

1. Stel de eigenschap **[Color](controls/properties-color-border.md)** van het label in op deze formule:<br>**Als( Waarde(Tekstvak1.Tekst) < 0, Rood, Zwart )**
   
    > [!NOTE]
   > Geef in een formule de eigenschap van een besturingselement op door de naam van het besturingselement op te geven, gevolgd door een punt, gevolgd door de naam van de eigenschap. Voorbeeld: geef de eigenschap **[Tekst](controls/properties-core.md)** van **Tekstvak1** op door **Tekstvak1.Tekst** te typen.
   
    ![Voorbeeld van een herberekening in PowerApps waarbij de kleur van een label wordt gewijzigd op basis van de waarde](./media/working-with-formulas/recalc-color1.png)
2. Geef in **Tekstinvoer1** en **Tekstinvoer2** twee getallen op die opgeteld tot een negatieve waarde leiden.
   
    ![Voorbeeld van een herberekening in PowerApps waarbij de kleur van een label wordt gewijzigd op basis van de waarde](./media/working-with-formulas/recalc-color2.png)
   
    De waarde in het label wordt rood weergegeven.

## <a name="change-a-color-based-on-user-input"></a>Een kleur wijzigen op basis van invoer door een gebruiker
U kunt de app configureren met formules, zodat gebruikers het uiterlijk of gedrag van de app kunnen wijzigen. U kunt bijvoorbeeld een filter maken zodat alleen gegevens worden getoond die een tekenreeks of tekst bevatten die de gebruiker opgeeft. U kunt ook gebruikers een verzameling gegevens laten sorteren op basis van een bepaalde kolom in de gegevensverzameling. In deze procedure laat u gebruikers de kleur van het scherm wijzigen door een of meer schuifregelaars aan te passen.

1. Verwijder de besturingselementen van de vorige procedures of maak een lege app, zoals u eerder hebt gedaan, en voeg drie schuifregelaars toe:
   
    ![Een schuifregelaar invoegen](./media/working-with-formulas/insert-slider.png)
2. Plaats de schuifregelaars zodanig dat ze niet overlappen en voeg drie labels toe. Configureer ze zodanig dat ze de kleuren **Rood**, **Groen** en **Blauw** tonen:
   
    ![Schuifregelaars rangschikken en labels toevoegen voor elke kleurcomponent](./media/working-with-formulas/three-sliders.png)
3. Stel de eigenschap **Max** van elke schuifregelaar in op 255, de maximumwaarde van een kleurcomponent voor de functie **[RGBA](functions/function-colors.md)**.
   
    U kunt de eigenschap **Max** opgeven door deze te selecteren op het tabblad **Inhoud** of in de lijst met eigenschappen:
   
    ![De maximumwaarde van de schuifregelaars wijzigen](./media/working-with-formulas/three-sliders-max.png)
4. Selecteer het scherm door vanaf een schuifregelaar te klikken en stel de eigenschap **[Opvullen](controls/properties-color-border.md)** van het scherm in op deze formule:<br>**RGBA( Schuifregelaar1.Waarde, Schuifregelaar2.Waarde, Schuifregelaar3.Waarde, 1 )**
   
    Zoals al eerder beschreven, opent u de eigenschappen van de besturingselementen door gebruik te maken van de operator **.** .  **Schuifregelaar1.Waarde** verwijst naar de eigenschap **[Waarde](controls/properties-core.md)** van de schuifregelaar. Deze geeft aan waar de gebruiker de schuifregelaar tussen de waarden **Min** en **Max** heeft geplaatst. Terwijl u de formule typt, krijgt elk besturingselement dat erin is opgenomen een kleurcode (tussen het scherm en de formulebalk):
   
    ![De formule voor de opvulkleur van de achtergrond van het scherm wordt gewijzigd, maar is nog niet klaar](./media/working-with-formulas/three-sliders-partial-rgba.png)
   
    Terwijl u haakje sluiten typt, wordt de achtergrond van het scherm gewijzigd in donkergrijs volgens standaardwaarden van de schuifregelaars, **50**. Als u klaar bent met het typen van de formule, wordt de waarde berekend en gebruikt als de waarde voor de opvulkleur van de achtergrond. U kunt de app gebruiken vanuit de standaardwerkruimte zonder dat u Preview hoeft te openen:
   
    ![De maximumwaarde van de schuifregelaars wijzigen](./media/working-with-formulas/three-sliders-complete-rgba.png)
5. Pas de schuifregelaars aan en kijk hoe de wijzigingen de achtergrondkleur beïnvloeden.
   
    Terwijl de schuifregelaars worden gewijzigd, wordt een nieuwe berekening uitgevoerd met de formule die de functie **[RGBA](functions/function-colors.md)** bevat. Hierdoor wordt onmiddellijk het nieuwe uiterlijk van het scherm bepaald.
   
    ![De formule voor de opvulkleur van de achtergrond van het scherm is nu gewijzigd](./media/working-with-formulas/three-sliders-example-colors.png)

## <a name="manage-app-behavior"></a>App-gedrag beheren
U kunt formules gebruiken voor het uitvoeren van berekeningen en het wijzigen van het uiterlijk, maar u kunt er ook acties mee uitvoeren. U kunt bijvoorbeeld de eigenschap **[OnSelect](controls/properties-core.md)** van een knop instellen op een formule waarin de functie **[Navigeren](functions/function-navigate.md)** is opgenomen. Als een gebruiker die knop selecteert, verschijnt het scherm dat u in de formule hebt opgegeven.

Sommige functies, zoals **[Navigeren](functions/function-navigate.md)** en **[Collect](functions/function-clear-collect-clearcollect.md)**, kunnen alleen in gedragsformules worden gebruikt.  U krijgt een melding als u een formule alleen in deze context kunt gebruiken.  

Met een gedragsformule kunt u meerdere acties uitvoeren als u de afzonderlijke functies scheidt door middel van een puntkomma (;). U kunt bijvoorbeeld een contextvariabele bijwerken, gegevens naar een gegevensbron pushen en ten slotte naar een ander scherm navigeren.

## <a name="view-a-list-of-properties-by-category"></a>Een lijst met eigenschappen op categorie weergeven
In de lijst met eigenschappen worden de eigenschappen alfabetisch getoond, maar u kunt alle eigenschappen van een besturingselement ook op categorie weergeven als u de optie **Advanced** op het tabblad **View** selecteert:

![Geavanceerde weergave](./media/working-with-formulas/advanced-open.png)

In deze weergave kunt u formules rechtstreeks bewerken.  Met de besturingselementselectie boven aan het scherm kunt u snel een besturingselement vinden.  En via de zoekfunctie voor eigenschappen kunt u snel een eigenschap van dat besturingselement vinden.

Deze weergave toont in eerste instantie alleen de belangrijkste eigenschappen.  Als u alle eigenschappen wilt zien, klikt u op de pijl-omlaag onder aan het deelvenster.  Elk besturingselement heeft een lange lijst met eigenschappen die alle aspecten van het gedrag en het uiterlijk van het besturingselement bepalen. U kunt door de lijst schuiven of een eigenschap zoeken door deze in het vak boven aan het deelvenster te typen.

## <a name="formula-syntax"></a>De syntaxis van de formule
Tijdens het typen van een formule in de formulebalk worden diverse syntaxiselementen in verschillende kleuren weergegeven om ervoor te zorgen dat u lange formules begrijpt en gemakkelijker kunt lezen. Dit is de lijst met kleurcodes in PowerApps.

![syntaxismarkering](./media/working-with-formulas/syntax-highlighting.png)

