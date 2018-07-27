---
title: Een besturingselement toevoegen en configureren | Microsoft Docs
description: Stapsgewijze instructies voor het rechtstreeks toevoegen en configureren van besturingselementen, via de werkbalk, op het tabblad Eigenschappen of de formulebalk.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 07/10/2017
ms.author: anneta
ms.openlocfilehash: 24f0479db0707e667263f5b160d6785560fe604b
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2018
ms.locfileid: "39195583"
---
# <a name="add-and-configure-a-control-in-powerapps"></a>Een besturingselement toevoegen en configureren in PowerApps
U kunt een groot aantal verschillende UI-elementen toevoegen aan uw app en vervolgens direct aspecten van hun uiterlijk en gedrag configureren. Dit kan via de werkbalk, in het tabblad **Eigenschappen** of de formulebalk. Deze UI-elementen worden besturingselementen genoemd en de aspecten eigenschappen.

## <a name="prerequisites"></a>Vereisten
1. [Registreer u](../signup-for-powerapps.md) voor PowerApps en [meld u vervolgens aan](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) door dezelfde referenties in te voeren die u hebt gebruikt om u te registreren.

2. Klik of tik in PowerApps Studio op **Nieuw** in het menu **Bestand** (aan de linkerkant).

    ![De optie Nieuw in het menu Bestand](./media/add-configure-controls/file-new.png)

3. Klik of tik onder **Lege app** op **Telefoonindeling**.

    ![Een volledig nieuwe app maken](./media/add-configure-controls/blank-app.png)

4. Als u wordt voorgesteld de inleidende rondleiding te volgen, klikt of tikt u op **Volgende** om vertrouwd te raken met de belangrijkste gedeelten van de PowerApps-interface (of klik of tik op **Overslaan**).

    ![Scherm van de inleidende rondleiding openen](./media/add-configure-controls/quick-tour.png)

    U kunt de rondleiding altijd later volgen door op het vraagtekenpictogram in de rechterbovenhoek te klikken of tikken en vervolgens op **Take the intro tour**.

## <a name="add-a-control"></a>Een besturingselement toevoegen
U kunt besturingselementen uit allerlei verschillende categorieën toevoegen door eerst op de werkbalk te klikken of tikken op het tabblad **Invoegen**. Klik of tik vervolgens op een categorie en klik of tik ten slotte op het gewenste besturingselement. Bekijk in deze sectie de besturingselementen uit elke categorie, zodat u bekend bent met de typen besturingselementen die u kunt toevoegen en waar u een bepaald type kunt vinden.

Klik of tik op het tabblad **Invoegen** op een van deze categorieën en klik of tik vervolgens op het besturingselement dat u wilt toevoegen:

**Tekst**: label, tekstinvoer, HTML-tekst, peninvoer<br>
**Besturingselementen**: knop, vervolgkeuzelijst, datumkiezer, selectievakje, keuzerondje, wisselknop, schuifregelaar, classificatie, timer<br>
**Galerie**: verticaal, horizontaal, flexibele hoogte, leeg verticaal, leeg horizontaal, leeg flexibele hoogte<br>
**Gegevenstabel**<br>
**Formulieren**: bewerken, weergeven, formulier voor entiteit<br>
**Media**: afbeelding, camera, streepjescode, video, audio, microfoon, afbeelding toevoegen<br>
**Diagrammen**: kolomdiagram, lijndiagram, cirkeldiagram<br>
**Pictogrammen**

> [!TIP]
> Als u meer ruimte nodig hebt voor besturingselementen, [voegt u nog een scherm toe](add-screen-context-variables.md).

## <a name="configure-a-control-directly"></a>Een besturingselement rechtstreeks configureren
In deze procedure gaat u een besturingselement van het type **Label** toevoegen en configureren, maar de procedure is in grote lijnen ook geschikt voor veel andere besturingselementen.

1. Klik of tik op het tabblad **Invoegen** en klik of tik vervolgens op **Label**.

    ![Tabblad Invoegen](./media/add-configure-controls/insert-text-box.png)

    Wanneer u een besturingselement toevoegt, wordt dit automatisch geselecteerd. U kunt ook een bestaand besturingselement selecteren door erop te klikken of tikken. Als een besturingselement is geselecteerd, ziet u een selectiekader om het element. Andere gebieden van de gebruikersinterface worden aangepast, zodat u het geselecteerde besturingselement kunt configureren. Een geselecteerd besturingselement van het type **Label** ziet er bijvoorbeeld uit zoals in deze afbeelding.

    ![Een geselecteerde label](./media/add-configure-controls/selected-text-box.png)

    > [!IMPORTANT]
   > Als er een besturingselement is geselecteerd op het moment dat u een ander besturingselement of een leeg gebied van het scherm selecteert, wordt de selectie van het eerste element ongedaan gemaakt.
2. Maak het besturingselement **Label** smaller door een greep aan de rechterkant van het selectiekader naar links te slepen. (De middelste greep wordt alleen weergegeven als u inzoomt.)

    ![Een label waarvan het formaat is gewijzigd](./media/add-configure-controls/shorter-text-box.png)

     U kunt het formaat van een besturingselement ook wijzigen door de eigenschap **[Height](controls/properties-size-location.md)** of **[Width](controls/properties-size-location.md)** (of allebei) aan te passen. Dit wordt verderop beschreven.

3. Verplaats het besturingselement **Label** door het selectiekader zelf te slepen. U kunt ook de waarde voor **[X](controls/properties-size-location.md)** of **[Y](controls/properties-size-location.md)** (of allebei) aanpassen, zoals verderop in dit onderwerp wordt beschreven.

4. Klik of tik driemaal op de tekst die wordt weergegeven in het besturingselement **Label** en typ vervolgens **Hallo, wereld**.

    ![Een label met aangepaste tekst](./media/add-configure-controls/change-text-directly.png)

     U kunt deze tekst ook wijzigen door de eigenschap **[Text](controls/properties-core.md)** van dit besturingselement in te stellen, zoals verderop in dit onderwerp wordt beschreven.

## <a name="configure-a-control-from-the-toolbar"></a>Een besturingselement configureren via de werkbalk
Als u een besturingselement configureert via de werkbalk, kunt u uit meer opties kiezen dan bij een rechtstreekse configuratie van een besturingselement.

1. Selecteer het besturingselement **Label** en klik of tik op het tabblad **Start** op de werkbalk.

    ![Tabblad Start](./media/add-configure-controls/home-tab.png)

2. Klik of tik op **Opvullen**, en klik of tik vervolgens op een kleur zoals Aquamarijn.

    ![Optie Opvullen](./media/add-configure-controls/fill-option.png)

    Uw selectie wordt toegepast op het besturingselement **Label**.

    ![Een label opgevuld met de kleur aquamarijn](./media/add-configure-controls/change-fill.png)

3. Wijzig het lettertype en de grootte van de tekst (bijvoorbeeld in 18 punts Georgia).

    ![Lettertype-instellingen](./media/add-configure-controls/font-size.png)

    Uw selectie wordt toegepast op het besturingselement **Label**.

    ![18 punts Georgia](./media/add-configure-controls/change-font.png)

4. Klik of tik op het tabblad **Label**, klik of tik op **Verticaal uitlijnen** en klik of tik op **Boven**.

    ![Tabblad Tekstvak](./media/add-configure-controls/text-box-tab.png)

    Uw selectie wordt toegepast op het besturingselement **Label**.

    ![Een label met tekst uitgelijnd op de bovenzijde van het vak](./media/add-configure-controls/change-align.png)

## <a name="configure-a-control-from-the-properties-tab"></a>Een besturingselement configureren via het tabblad Eigenschappen
Met behulp van het tabblad **Eigenschappen** kunt u een besturingselement configureren zonder een formule te schrijven. In deze procedure gaat u een ander besturingselement van het type **Label** toevoegen en configureren, maar de procedure is in grote lijnen ook geschikt voor veel andere besturingselementen.

1. Voeg een ander besturingselement **Label** toe zoals eerder in dit onderwerp beschreven.

2. Selecteer het nieuwe besturingselement en klik of tik in het rechterdeelvenster op het tabblad **Eigenschappen**.

    ![Paneel Eigenschappen](./media/add-configure-controls/properties-panel.png)

3. Typ in het **Tekst**vak **Tabblad Eigenschappen**.

    ![Paneel Eigenschappen Tekstlabel](./media/add-configure-controls/properties-panel-text.png)

    Het besturingselement **Label** geeft de opgegeven tekst weer.

    ![Paneel Eigenschappen Tekstachtergrond](./media/add-configure-controls/properties-panel-canvas-text.png)

4. Klik of tik in het deelvenster **Eigenschappen** op het pictogram **Vullen** en klik of tik vervolgens op een kleur.

    ![Paneel Eigenschappen Tekstkleur](./media/add-configure-controls/properties-panel-color.png)

    Uw selectie wordt toegepast op het besturingselement **Label**.

    ![Paneel Eigenschappen Achtergrondkleur](./media/add-configure-controls/properties-panel-canvas-color.png)

5. Klik of tik in het deelvenster Eigenschappen op de eigenschap **Color**.

    ![Eigenschap paneel Eigenschappen](./media/add-configure-controls/properties-panel-property.png)

    De waarde van de eigenschap **Color** is gemarkeerd in de formulebalk.

    ![Eigenschapuitdrukking in paneel Eigenschappen](./media/add-configure-controls/properties-panel-property-expression.png)

6. Verwijder het tweede besturingselement **Label** door erop te klikken of tikken en vervolgens op Delete te drukken.

## <a name="configure-a-control-in-the-formula-bar"></a>Een besturingselement configureren via de formulebalk
Met behulp van de formulebalk kunt u eigenschappen instellen die u niet rechtstreeks, in het tabblad **Eigenschappen** of via de werkbalk kunt instellen. Zo kunt u op deze manier knopinfo instellen die wordt weergegeven wanneer een gebruiker het besturingselement aanwijst, maar er niet op klikt of tikt. U kunt ook complexe formules opgeven om de mogelijkheden van de app te vergroten.

Alle wijzigingen die u eerder in dit onderwerp hebt gemaakt, hebben ertoe geleid dat de waarde van een bepaalde [eigenschap](reference-properties.md) van het besturingselement is aangepast.

* Door het formaat van het besturingselement via slepen te wijzigen, is de waarde van de eigenschap **[Width](controls/properties-size-location.md)** aangepast.
* Door het besturingselement naar een andere positie te slepen, is de waarde van de eigenschappen **[X](controls/properties-size-location.md)** en **[Y](controls/properties-size-location.md)** gewijzigd.
* Door de tekst van het besturingselement rechtstreeks te wijzigen, is de eigenschap **[Text](controls/properties-core.md)** aangepast.

In plaats van een besturingselement rechtstreeks, in het tabblad **Eigenschappen** of via de werkbalk te configureren, kunt u de waarde van een eigenschap ook aanpassen door de eigenschap te selecteren in de lijst met eigenschappen en vervolgens een waarde op te geven op de formulebalk. Deze aanpak betekent dat u alfabetisch kunt zoeken naar eigenschappen, maar nog belangrijker is dat u meer mogelijkheden hebt.

1. Selecteer het resterende besturingselement **Label**, klik of tik op **[Text](controls/properties-core.md)** in de lijst met eigenschappen en typ vervolgens **"Mijn bedrijfsnaam"** (inclusief de aanhalingstekens) in de formulebalk.

    ![Een letterlijke tekenreeks in een label](./media/add-configure-controls/text-literal.png)

    Wanneer u een tekenreeks tussen aanhalingstekens zet, geeft u aan dat de invoer exact moet worden weergegeven zoals u deze hebt getypt. Een andere mogelijkheid is om de waarde van een eigenschap in te stellen op een formule.

2. Selecteer het besturingselement **Label**, klik of tik op **[Text](controls/properties-core.md)** in de lijst met eigenschappen en typ vervolgens **Today()** (zonder aanhalingstekens) in de formulebalk.

    U ziet nu de huidige datum in het besturingselement.

    ![Functie Today](./media/add-configure-controls/today-function.png)

    > [!TIP]
   > U kunt [verschillende notaties gebruiken voor datums en tijden](show-text-dates-times.md). Daarnaast kunt u berekeningen uitvoeren op datums en tijden.

## <a name="configure-two-controls-to-interact-with-each-other"></a>Twee besturingselementen configureren voor onderlinge interactie
In deze procedure gaat u een selectievakje toevoegen en vervolgens het eerder gemaakte label zo configureren dat dit vak alleen wordt weergegeven wanneer het selectievakje is ingeschakeld.

1. Klik of tik op het tabblad **Invoegen**.

    ![Tabblad Invoegen](./media/add-configure-controls/insert-tab.png)

2. Klik of tik op **Besturingselementen**, en klik of tik vervolgens op **Selectievakje**.

    ![Selectievakje invoegen](./media/add-configure-controls/insert-check-box.png)

3. Plaats het besturingselement **Selectievakje** onder het besturingselement **Label** en stel de eigenschap **[Text](controls/properties-core.md)** van het besturingselement **Selectievakje** in op **Tekst weergeven**.

    ![Selectievakje configureren](./media/add-configure-controls/configure-check-box.png)

4. Met het besturingselement **Selectievakje** nog steeds geselecteerd, klikt of tikt u op de naam ervan boven het tabblad **Eigenschappen** en typt u vervolgens **Mijnselectievakje**

    ![Naam van selectievakje wijzigen](./media/add-configure-controls/properties-panel-rename.png)

5. Klik of tik op het besturingselement **Label** om dat te selecteren.

6. Klik of tik in het tabblad **Eigenschappen** op de eigenschap **Visible**.

    ![Eigenschap Visible](./media/add-configure-controls/properties-panel-visible-property.png)

7. Verwijder **true** op de formulebalk, en typ of plak deze formule:

    **If(Mijnselectievakje.Value = true, true, false)**

    Deze **[If-functie](functions/function-if.md)** geeft aan dat het label alleen moet worden weergegeven wanneer het selectievakje is ingeschakeld. Omdat het selectievakje is uitgeschakeld, verdwijnt het besturingselement **Label** (het selectiekader is nog wel zichtbaar).

    ![Formule met Visible](./media/add-configure-controls/visible-formula.png)

8. Klik of tik op het besturingselement **Selectievakje** om het selectiekader eraan toe te voegen, en klik of tik er vervolgens nogmaals op om een vinkje toe te voegen.

    Het **label** wordt opnieuw weergegeven:

    ![Label wordt weergegeven wanneer het selectievakje is ingeschakeld](./media/add-configure-controls/show-text.png)

9. Schakel het besturingselement **Selectievakje** uit om het besturingselement **Label** te verbergen.

    ![Label verdwijnt wanneer het selectievakje wordt uitgeschakeld](./media/add-configure-controls/hide-text.png)

Dit is een eenvoudig voorbeeld, maar u kunt het gedrag en uiterlijk van uw app met behulp van een of [formules](formula-reference.md) variëren van eenvoudig tot complex.

## <a name="rename-a-screen-or-a-control"></a>De naam van een scherm of besturingselement wijzigen
Door de naam een scherm of besturingselement te wijzigen, kunt u formules maken die makkelijker zijn te lezen en te onderhouden.

1. Klik of tik op het scherm of het besturingselement waarvan u de naam wilt wijzigen.

2. Klik of tik in het rechterdeelvenster op de naam van de eigenschap (boven het tabblad **Eigenschappen**) en typ vervolgens de naam die u wilt gebruiken.

    ![Naam van selectievakje wijzigen](./media/add-configure-controls/properties-panel-rename.png)

## <a name="find-and-select-a-screen-or-a-control"></a>Een scherm of een besturingselement zoeken en selecteren
U kunt een scherm of besturingselement vinden en selecteren, zelfs als dit is verborgen of onder een ander besturingselement valt. Dit doet u door ernaar te zoeken in het linkerdeelvenster. In dit deelvenster ziet u ofwel een miniatuur van elk scherm in de app, ofwel een hiërarchische weergave van elk scherm en de besturingselementen die het bevat.

* **Als u wilt schakelen tussen de miniaturen en de hiërarchische weergave**, klikt of tikt u op een pictogram in de rechterbovenhoek van het deelvenster.

    ![Schakelen tussen weergaven](./media/add-configure-controls/toggle-view.png)

* **Als u een besturingselement wilt zoeken**, typt u één of meer tekens om de namen van besturingselementen te markeren die de tekst die u hebt getypt bevatten.

    Als u op een zoekresultaat klikt of tikt, selecteert u dit besturingselement in de app.

    ![Zoeken in de structuurweergave](./media/add-configure-controls/search.png)

* **Als u een scherm omhoog of omlaag wilt verplaatsen, dupliceren, verwijderen of de naam ervan wilt wijzigen**, klikt u erop met de rechtermuisknop (of klik of tik op het weglatingsteken ernaast). Klik of tik vervolgens op de gewenste optie.

    ![Structuurweergave van het contextmenu](./media/add-configure-controls/context.png)

* **Als u een scherm wilt kopiëren/plakken, verwijderen of de naam ervan wilt wijzigen**, klikt u erop met de rechtermuisknop (of klik of tik op het weglatingsteken ernaast). Klik of tik vervolgens op de gewenste optie.
