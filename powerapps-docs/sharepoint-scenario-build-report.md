---
title: Een Power BI-rapport maken voor projectanalyse | Microsoft Docs
description: In deze taak wordt een Power BI-rapport gemaakt op basis van twee SharePoint-lijsten.
services: 
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/10/2018
ms.author: mblythe
ms.openlocfilehash: 1b22885a6ff97b1ffcf67da291ab89d091863981
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="create-a-power-bi-report-to-analyze-projects"></a>Een Power BI-rapport maken voor projectanalyse
> [!NOTE]
> Dit artikel maakt deel uit van een reeks zelfstudies over het gebruik van PowerApps, Microsoft Flow en Power BI met SharePoint Online. Lees de [inleiding tot de reeks](sharepoint-scenario-intro.md) zodat u een idee van het geheel krijgt en van de betreffende downloads.

In deze taak wordt een Power BI-rapport gemaakt op basis van de twee SharePoint-lijsten. We brengen de lijstgegevens over naar Power BI Desktop en schonen de lijst enigszins op, voeren wat eenvoudige gegevensmodellering uit en maken een set visualisaties die ons iets over de gegevens duidelijk maken.

> [!TIP]
> Het [downloadpakket](https://aka.ms/o4ia0f) voor dit scenario omvat een voltooide versie van dit rapport: project-analysis.pbix.

## <a name="quick-review-of-power-bi-desktop"></a>Kort overzicht van Power BI Desktop
Voordat we beginnen met het maken van het rapport, kijken we nog een keer naar Power BI Desktop. Dit is een krachtig hulpprogramma, met talloze functies. We richten ons dus op een overzicht van de gebieden die u in deze taak zult gebruiken. Er zijn drie belangrijke werkgebieden of *weergaven* in Power BI Desktop: de weergave **Rapport**, de weergave **Gegevens** en de weergave **Relaties**. Power BI Desktop bevat ook **Query-editor**, dat in een afzonderlijk venster wordt geopend.

In het volgende scherm ziet u aan de linkerkant van Power BI Desktop, van boven naar onder, de drie weergavepictogrammen: **Rapport**, **Gegevens** en **Relaties**. De gele balk aan de linkerkant geeft de huidige weergave aan. In dit geval wordt de weergave **Rapport** weergegeven. U kunt een weergave kiezen door een van de drie pictogrammen te selecteren.

![Weergaven in Power BI Desktop](./media/sharepoint-scenario-build-report/05-00-00-tabs.png)

De weergave **Rapport** bevat vijf hoofdgebieden:

1. Het lint, waarop de algemene taken worden weergegeven in verband met rapporten en visualisaties.
2. De weergave **Rapport**, of het canvas, waar visualisaties worden gemaakt en gerangschikt.
3. Het tabblad **Pagina's** onderaan, waar u een rapportpagina kunt selecteren of toevoegen.
4. Het deelvenster **Visualisaties**, waar u visualisaties kunt wijzigen, kleuren of assen kunt aanpassen, filters kunt toepassen, velden heen kunt slepen, en nog veel meer.
5. Het deelvenster **Velden**, waarvandaan query-elementen en filters naar de weergave **Rapport** kunnen worden gesleept of naar het gebied **Filters** van het deelvenster **Visualisaties**.

![Tabbladen, weergaven en deelvensters in Power BI Desktop](./media/sharepoint-scenario-build-report/05-00-01-report.png)

De weergave **Gegevens** bevat drie hoofdgebieden:

1. Het lint, met het tabblad **Modelleren**, dat in de afbeelding hieronder is geselecteerd. Op dit tabblad kunt u berekende tabellen en kolommen maken en wijzigingen aan het gegevensmodel aanbrengen.
2. Het middelste deelvenster, met de gegevens voor de geselecteerde tabel.
3. Het deelvenster **Velden**, waar u bepaalt hoe velden in uw rapporten worden weergegeven.

![Gegevensweergave in Power BI Desktop](./media/sharepoint-scenario-build-report/05-00-02-data.png)

In deze taak gebruiken we de weergave **Relaties** niet, maar u kunt deze later bekijken als we de lijstgegevens naar Power BI Desktop hebben overgebracht.

In **Query-editor** maakt u query's en transformeert u gegevens om het verfijnde gegevensmodel vervolgens in Power BI Desktop te laden. **Query-editor** bevat vier hoofdgebieden:

1. Het lint, dat veel opties bevat voor het vormgeven en transformeren van de opgehaalde gegevens.
2. Het linkerdeelvenster, waar query's worden vermeld en beschikbaar gemaakt om te worden geselecteerd, weergegeven en vormgegeven.
3. Het middelste deelvenster, waar gegevens uit de geselecteerde query worden weergegeven en beschikbaar gemaakt om te worden vormgegeven.
4. Het venster **Queryinstellingen**, waarin de query-eigenschappen worden vermeld en tevens de transformatiestappen die op de gegevens zijn toegepast.

![Query-editor in Power BI Desktop](./media/sharepoint-scenario-build-report/05-00-03-query.png)

## <a name="step-1-get-data-into-power-bi-desktop"></a>Stap 1: Gegevens laden in Power BI Desktop
In deze stap gaan we eerst verbinding maken met de twee lijsten. Vervolgens schonen we de gegevens op door de kolommen te verwijderen die we voor de gegevensanalyse niet nodig hebben. We wijzigen ook de gegevenstypen van sommige resterende kolommen, zodat de berekeningen goed kunnen worden uitgevoerd. Zie de sectie [Getting Data](https://powerbi.microsoft.com/guided-learning/powerbi-learning-1-1-overview-of-power-bi-desktop) (Gegevens ophalen) in de cursus Guided Learning (Gestuurd leren) voor meer informatie over het ophalen en opschonen van gegevens in Power BI Desktop.

### <a name="connect-to-sharepoint-lists"></a>Verbinding maken met SharePoint-lijsten
1. Klik of tik in Power BI Desktop, op het tabblad **Start**, op **Gegevens ophalen** en vervolgens op **Meer...**
   
    ![Gegevens ophalen](./media/sharepoint-scenario-build-report/05-01-01-get-data.png)
2. Klik of tik in het dialoogvenster **Gegevens ophalen** op **SharePoint Online-lijst** en vervolgens op **Verbinding maken**.
   
    ![Verbinding maken met SharePoint-lijst](./media/sharepoint-scenario-build-report/05-01-02-sharepoint-list.png)
3. Voer de URL in voor uw SharePoint-site en klik of tik op **OK**.
   
    ![URL voor SharePoint-lijst](./media/sharepoint-scenario-build-report/05-01-03-sharepoint-url.png)
4. Als u het volgende dialoogvenster ziet, controleer dan of u met de juiste referenties bent aangemeld en klik of tik op **Verbinding maken**.
   
    ![Referenties voor SharePoint-lijst](./media/sharepoint-scenario-build-report/05-01-04-credentials.png)
5. Selecteer **Projectdetails** en **Projectaanvragen** en klik of tik op **Bewerken**.
   
    ![SharePoint-lijsten selecteren](./media/sharepoint-scenario-build-report/05-01-05-list-navigator.png)
   
    De lijsten worden nu in Query-editor weergegeven als tabellen.
   
    ![Tabellen in Query-editor](./media/sharepoint-scenario-build-report/05-01-06-query-editor.png)

### <a name="remove-unnecessary-columns-from-the-tables"></a>Overbodige kolommen uit de tabellen verwijderen
1. Klik of tik in het linker navigatiedeelvenster op **Projectdetails**.
2. Selecteer in het middelste deelvenster de kolom **FileSystemObjectType** en klik of tik op **Kolommen verwijderen**.
   
    ![Kolommen verwijderen](./media/sharepoint-scenario-build-report/05-01-07-remove-column.png)
3. Verwijder de twee kolommen na de kolom **Id**: **ServerRedirectedEmbedURL** en **ContentTypeId**. 
> [!TIP]
> Gebruik de Shift-toets om beide kolommen te selecteren. Klik vervolgens op **Kolommen verwijderen**.
4. Verwijder alle kolommen rechts van de kolom **PMAssigned** (totaal 22 kolommen). De tabel moet met de volgende afbeelding overeenkomen:
   
    ![Tabel Projectdetails in Query-editor](./media/sharepoint-scenario-build-report/05-01-08-table-details.png)
5. Herhaal het proces dat u zojuist hebt doorlopen, nu voor **Project aanvragen**: verwijder **FileSystemObjectType**, **ServerRedirectedEmbedURL**,  **ContentTypeId** en alle kolommen aan de rechterkant van de kolom **Goedgekeurd** (in totaal 22 kolommen). De tabel moet met de volgende afbeelding overeenkomen:
   
    ![ Tabel Projectaanvragen in Query-editor](./media/sharepoint-scenario-build-report/05-01-09-table-requests.png)

### <a name="change-the-data-type-on-project-details-columns"></a>Het gegevenstype wijzigen in kolommen met projectdetails
1. Selecteer de kolom **ProjectedDays**, klik of tik op **Gegevenstype: willekeurig** en vervolgens op **Geheel getal**.
   
    ![Gegevenstype wijzigen in geheel getal](./media/sharepoint-scenario-build-report/05-01-10-datatype-number.png)
2. Herhaal de vorige stap voor de kolom **ActualDays**.
3. Selecteer de kolom **ApprovedDate**, klik of tik op **Gegevenstype: willekeurig** en vervolgens op **Datum**.
   
    ![ Gegevenstype wijzigen in datum](./media/sharepoint-scenario-build-report/05-01-11-datatype-date.png)

4. Herhaal de vorige stap voor de kolommen **ProjectedStartDate** en **ProjectedEndDate**.

### <a name="change-the-data-type-on-project-requests-columns"></a>Het gegevenstype wijzigen in kolommen met projectaanvragen

1. Selecteer de kolom **EstimatedDays**, klik of tik op **Gegevenstype: willekeurig** en vervolgens op **Geheel getal**.

2. Selecteer de kolom **RequestDate**, klik of tik op **Gegevenstype: willekeurig** en vervolgens op **Datum**.

### <a name="apply-and-save-changes"></a>Wijzigingen toepassen en opslaan

1. Klik op het tabblad **Start** op **Sluiten en toepassen** om Query-editor te sluiten en terug te gaan naar het hoofdvenster van Power BI Desktop.
   
    ![Sluiten en wijzigingen toepassen](./media/sharepoint-scenario-build-report/05-01-12-close-apply.png)

2. Klik of tik op **Bestand** en vervolgens op **Opslaan**. Sla het bestand op onder de naam project-analysis.pbix.

## <a name="step-2-improve-the-data-model"></a>Stap 2: Het gegevensmodel verbeteren
Nu we de gegevens uit de SharePoint-lijsten naar Power BI Desktop hebben overgebracht, gaan we verder met het modelleren van de gegevens. Gegevensmodellering kan een tijdrovend proces zijn. We laten u echter een paar interessante dingen zien waarmee u meer uit de lijstgegevens in Power BI Desktop kunt halen:

* De relatie tussen de twee tabellen wijzigen
* Een gegevenstabel toevoegen zodat we berekeningen kunnen maken op basis van doordeweekse dagen
* Berekende kolommen toevoegen om de perioden tussen projectmijlpalen te berekenen
* Metingen toevoegen om de afwijking tussen het verwachte en het werkelijke aantal dagen voor een project te berekenen

Na het voltooien van deze stappen kunnen we visualisaties maken die gebruikmaken van de verbeteringen aan ons model. Zie de sectie [Modeling](https://powerbi.microsoft.com/guided-learning/powerbi-learning-2-1-intro-modeling-data) (Modellering) in de cursus Guided Learning (Gestuurd leren) voor meer informatie over het modelleren van gegevens in Power BI Desktop.

### <a name="change-table-relationships"></a>Tabelrelaties wijzigen
Bij het laden van de lijsten in Power BI Desktop is er een relatie tussen de lijsten gemaakt op basis van de kolom **Id** in beide tabellen. De relatie zou eigenlijk moeten worden gemaakt tussen de kolom **Id** in de tabel **Projectaanvragen** en de kolom **RequestId** in de tabel **Projectdetails**. Dat gaan we nu oplossen:

1. Klik of tik op het pictogram **Gegevensweergave**.
   
    ![Gegevensweergave](./media/sharepoint-scenario-build-report/05-02-01-data-view.png)

2. Klik of tik op het tabblad **Modelleren** op **Relaties beheren**. Voor alle stappen met betrekking tot gegevensmodellering blijven we op dit tabblad in de weergave **Gegevens**.
   
    ![Relaties beheren](./media/sharepoint-scenario-build-report/05-02-02-manage-relationships.png)

3. Controleer of de bestaande relatie is geselecteerd, klik of tik op **Verwijderen** en vervolgens opnieuw op **Verwijderen** om te bevestigen.
   
    ![Relatie verwijderen](./media/sharepoint-scenario-build-report/05-02-03-delete-relationship.png)

4. Klik op **Nieuw** om een andere relatie te maken.

5. Voer de volgende handelingen uit in het dialoogvenster **Relatie maken**:
   
   1. Selecteer **Projectaanvragen** en de kolom **Id** voor de eerste tabel.
   
   2. Selecteer **Projectdetails** en de kolom **RequestId** voor de tweede tabel.
   
   3. Het scherm moet lijken op de volgende afbeelding. Klik of tik op **OK** als u klaar bent en vervolgens op **Sluiten**.
      
       ![Relatie maken](./media/sharepoint-scenario-build-report/05-02-04-create-relationship.png)

### <a name="add-a-date-table-to-make-date-based-calculations-easier"></a>Een datumtabel toevoegen om berekeningen op basis van datums te vereenvoudigen
1. Klik of tik op **Nieuwe tabel**.
   
    ![Nieuwe tabel](./media/sharepoint-scenario-build-report/05-02-05-modeling-table.png)
2. Voer deze formule in de formulebalk in: **Dates = CALENDARAUTO()**.
   
    ![Formulebalk met Dates = CALENDARAUTO()](./media/sharepoint-scenario-build-report/05-02-06-formula-bar.png)
   
    Met deze formule wordt een tabel met de naam **Dates** gemaakt. Deze bevat één datumkolom. De tabel omvat alle datums uit de andere tabel en wordt automatisch bijgewerkt als er extra datums worden toegevoegd (dat wil zeggen als er gegevens worden vernieuwd).
   
    Deze formule (en de andere in deze sectie) maakt gebruik van DAX (Data Analysis Expressions), een formuletaal voor Power BI en andere technologieën. Zie [DAX basics in Power BI Desktop](https://powerbi.microsoft.com/documentation/powerbi-desktop-quickstart-learn-dax-basics/) (Basisbeginselen van DAX in Power BI Desktop) voor meer informatie.
3. Druk op Enter om de tabel **Dates** te maken.
   
    ![Tabel Dates](./media/sharepoint-scenario-build-report/05-02-07-date-table.png)

### <a name="add-a-calculated-column-to-the-dates-table"></a>Een berekende kolom toevoegen aan de tabel Dates
1. Terwijl u nog steeds in de tabel Dates bent, klikt of tikt u op **Nieuwe kolom**.
   
    ![Nieuwe kolom](./media/sharepoint-scenario-build-report/05-02-00-modeling-column.png)
2. Voer deze formule in de formulebalk in: **IsWeekDay = SWITCH(WEEKDAY(Dates[Date]), 1;0;7;0;1)**.
   
    Met deze formule wordt bepaald of een datum in de kolom **Date** een doordeweekse dag is. Als de datum op een doordeweekse dag valt, krijgt de kolom **IsWeekDay** de waarde 1; anders krijgt de kolom de waarde 0.
3. Druk op Enter om de kolom **IsWeekDay** toe te voegen aan de tabel **Dates**.
   
    ![Kolom IsWeekDay toevoegen](./media/sharepoint-scenario-build-report/05-02-08-column-isweekday.png)

### <a name="add-a-calculated-column-to-the-project-details-table"></a>Een berekende kolom toevoegen aan de tabel Projectdetails
1. Klik of tik in het rechterdeelvenster op de tabel **Projectdetails** en vervolgens op **Nieuwe kolom**.
   
    ![Nieuwe kolom](./media/sharepoint-scenario-build-report/05-02-00-modeling-column.png)
2. Voer deze formule in de formulebalk in:
   
    ```
    ApprovedStartDiff = CALCULATE(SUM(Dates[IsWeekday]),
   
       DATESBETWEEN(Dates[Date],
   
          'Project Details'[ApprovedDate],
   
          'Project Details'[ProjectedStartDate]
   
      )
   
    )
    ```
   
    Met deze formule wordt het verschil in dagen berekend tussen de dag waarop een project is goedgekeurd en de dag waarop het begint. De kolom **IsWeekday** in de tabel **Datums** wordt gebruikt, zodat er dus alleen doordeweekse dagen worden geteld.
3. Druk op Enter om de kolom **ApprovedStartDiff** aan de tabel **Projectdetails** toe te voegen.
   
    ![Kolom ApprovedStartDiff toevoegen](./media/sharepoint-scenario-build-report/05-02-09-column-approvedstartdiff.png)

### <a name="add-a-calculated-column-to-the-project-requests-table"></a>Een berekende kolom toevoegen aan de tabel Projectaanvragen
1. Klik of tik in het rechterdeelvenster op de tabel **Projectaanvragen** en vervolgens op **Nieuwe kolom**.
   
    ![Nieuwe kolom](./media/sharepoint-scenario-build-report/05-02-00-modeling-column.png)
2. Voer deze formule in de formulebalk in:
   
    ```
    RequestDateAge = CALCULATE(SUM(Dates[IsWeekday]),
   
       DATESBETWEEN(Dates[Date],
   
          'Project Requests'[RequestDate],
   
          NOW()
   
       )
   
    )
    ```
   
    Met deze formule wordt het verschil in dagen berekend tussen de dag waarop een project is aangevraagd en de huidige dag (NOW()). Ook deze formule telt alleen de doordeweekse dagen. Deze kolom wordt gebruikt om het project te zoeken dat het langst in de wachtrij heeft gestaan.
3. Druk op Enter om de kolom **RequestDateAge** aan de tabel **Projectaanvragen** toe te voegen.
   
    ![Kolom RequestDateAge toevoegen](./media/sharepoint-scenario-build-report/05-02-10-column-requestdateage.png)

### <a name="add-a-measure-to-the-project-details-table"></a>Een meting toevoegen aan de tabel Projectdetails
1. Klik of tik in het rechterdeelvenster op de tabel **Projectdetails** en vervolgens op **Nieuwe meting**.
   
    ![Nieuwe meting](./media/sharepoint-scenario-build-report/05-02-00-modeling-measure.png)
2. Voer deze formule in de formulebalk in:
   
    ```
    VarProjectedActual = DIVIDE(
   
        SUM('Project Details'[ActualDays]) - SUM('Project Details'[ProjectedDays]),
   
        SUM('Project Details'[ProjectedDays])
   
    )
    ```
   
    Met deze formule wordt het verschil berekend tussen het werkelijke en het verwachte aantal dagen voor een project. We voegen deze meting toe in plaats van een berekende kolom, zodat de juiste resultaten worden teruggegeven, ongeacht hoe de gegevens worden gefilterd of in een rapport samengevoegd.
3. Druk op Enter om de meting **VarProjectedActual** aan de tabel **Projectdetails** toe te voegen.
   
    ![Meting VarProjectedActual toevoegen](./media/sharepoint-scenario-build-report/05-02-11-measure-varprojectedactual.png)

### <a name="add-a-measure-to-the-project-requests-table"></a>Een meting toevoegen aan de tabel Projectaanvragen
1. Klik of tik in het rechterdeelvenster op de tabel **Projectaanvragen** en vervolgens op **Nieuwe meting**.
   
    ![Nieuwe meting](./media/sharepoint-scenario-build-report/05-02-00-modeling-measure.png)
2. Voer deze formule in de formulebalk in:
   
    ```
    MaxDaysPending = MAXX(
   
        FILTER('Project Requests', 'Project Requests'[Approved]="Pending"),
   
        'Project Requests'[RequestDateAge]
   
    )
    ```
   
    Met deze formule wordt het project gevonden dat het langst in de wachtrij heeft gestaan, en wel op basis van de eerder gedefinieerde berekende kolom.
3. Druk op Enter om de meting **MaxDaysPending** aan de tabel **Projectaanvragen** toe te voegen.
   
    ![Meting MaxDaysPending toevoegen](./media/sharepoint-scenario-build-report/05-02-12-measure-maxdayspending.png)

## <a name="step-3-create-report-visualizations"></a>Stap 3: Rapportvisualisaties maken
We zijn nu aanbeland bij de stap waaraan de meeste personen denken als ze aan gegevensanalyse denken: het maken van visualisaties om patronen in onze gegevens te vinden. In deze stap maken we vier visualisaties:

* Een kolomdiagram met het verwachte aantal dagen versus het werkelijke aantal dagen voor projecten
* Een kolomdiagram met de afwijking voor elk project
* Een kaart met het project dat het langs in de wachtrij heeft gestaan
* Een tabel met de tijd tussen de goedkeuring van een project en de beoogde begindatum van dat project

Nadat we deze rapportvisualisaties in Power BI Desktop hebben gemaakt, publiceren we de gegevens en rapporten in de Power BI-service, zodat we dashboards kunnen maken en delen. Zie de sectie [Visualizations](https://powerbi.microsoft.com/guided-learning/powerbi-learning-3-1-intro-visualizations) (Visualisaties) in de cursus Guided Learning (Gestuurd leren) voor meer informatie over het maken van rapporten in Power BI Desktop.

### <a name="create-a-bar-chart-to-show-projected-versus-actual"></a>Een staafdiagram maken voor het weergeven van verwacht versus werkelijk
1. Klik of tik op het weergavepictogram **Rapport**. We blijven voor het vervolg in deze weergave in Power BI Desktop.
   
    ![Weergave Rapport](./media/sharepoint-scenario-build-report/05-03-01-report-view.png)
2. Klik of tik in het deelvenster **Visualisaties** aan de rechterkant op **Gegroepeerd kolomdiagram**.
   
    ![Visualisaties: gegroepeerd kolomdiagram](./media/sharepoint-scenario-build-report/05-03-00-visuals-column.png)
3. Sleep **PMAssigned** en **Title** vanuit **Projectdetails** in het deelvenster **Velden** naar **As** in het deelvenster **Visualisaties**.
   
    ![As in het deelvenster Visualisaties](./media/sharepoint-scenario-build-report/05-03-00-axis.png)
4. Sleep **ActualDays** en **ProjectedDays** vanuit **Projectdetails** in het deelvenster **Velden** naar **Waarde** in het deelvenster **Visualisaties**.
   
    ![Waarde in het deelvenster Visualisaties](./media/sharepoint-scenario-build-report/05-03-03-value-projected.png)
5. De visualisatie moet er nu uitzien als in de volgende afbeelding.
   
    ![ProjectedDays en ActualDays op PMAssigned](./media/sharepoint-scenario-build-report/05-03-04-chart-projected.png)
6. Sleep **Status** vanuit **Projectdetails** in het deelvenster **Velden** naar het gebied **Filters** van het deelvenster **Visualisaties** en selecteer het selectievakje **Voltooid**.
   
   ![Kolom Filteren op status](./media/sharepoint-scenario-build-report/05-03-05-filters-projected.png)
   
   Het diagram wordt nu gefilterd om alleen de voltooide projecten te laten zien. Dat is logisch, want we vergelijken immers het verwachte aantal dagen met het werkelijke aantal dagen.
7. Klik op de pijlen in de linkerbovenhoek van het diagram om in de hiërarchie van projectmanagers en projecten omhoog of omlaag te gaan. In de volgende afbeelding ziet u het resultaat van inzoomen op de projecten.
   
   ![Inzoomen op kolomdiagram](./media/sharepoint-scenario-build-report/05-03-06-chart-projected-drill.png)

### <a name="create-a-bar-chart-to-show-variance-from-projected"></a>Een staafdiagram maken om de afwijking van verwacht te tonen
1. Klik of tik op het canvas buiten de visualisatie die u zojuist hebt gemaakt.
2. Klik of tik in het deelvenster **Visualisaties** aan de rechterkant op **Gegroepeerd kolomdiagram**.
   
    ![Visualisaties: gegroepeerd kolomdiagram](./media/sharepoint-scenario-build-report/05-03-00-visuals-column.png)
3. Sleep **PMAssigned** en **Title** vanuit **Projectdetails** in het deelvenster **Velden** naar **As** in het deelvenster **Visualisaties**.
   
    ![As in het deelvenster Visualisaties](./media/sharepoint-scenario-build-report/05-03-00-axis.png)
4. Sleep **VarProjectedActual** vanuit **Projectdetails** in het deelvenster **Velden** naar **Waarde** in het deelvenster **Visualisaties**.
   
    ![Waarde in het deelvenster Visualisaties](./media/sharepoint-scenario-build-report/05-03-07a-value-variance.png)
5. Sleep **Status** vanuit **Projectdetails** in het deelvenster **Velden** naar het gebied **Filters** van het deelvenster **Visualisaties** en selecteer het selectievakje **Voltooid**.
   
    ![Kolom Filteren op status](./media/sharepoint-scenario-build-report/05-03-07b-filters-variance.png)
   
    De visualisatie moet er nu uitzien als in de volgende afbeelding.
   
    ![VarProjectedActual op PMAssigned](./media/sharepoint-scenario-build-report/05-03-08-chart-variance.png)
   
    In dit diagram kunt u zien dat de variatie voor projecten die door Quentin van Groesen zijn uitgevoerd, groter is dan de variatie voor projecten die door Femke van Nuil zijn uitgevoerd. Zoom in om de variatie per project te zien en of het aantal verwachte dagen meer of minder is dan het aantal werkelijke dagen.
   
    ![VarProjectedActual op Title](./media/sharepoint-scenario-build-report/05-03-09-chart-variance-drill.png)
6. Voordat we nog meer visualisaties gaan maken, gaan we de al gemaakte verplaatsen en de grootte ervan aanpassen, zodat ze naast elkaar passen.
   
    ![Diagrammen naast elkaar passen](./media/sharepoint-scenario-build-report/05-03-10-two-charts.png)

### <a name="create-a-card-that-shows-the-longest-pending-project"></a>Een kaart maken waarop het project dat het langst in de wacht staat
1. Klik of tik op het canvas buiten de visualisatie die u zojuist hebt gemaakt.
2. Klik of tik in het deelvenster **Visualisaties** aan de rechterkant op **Kaart**.
   
    ![Visualisaties: kaart](./media/sharepoint-scenario-build-report/05-03-11-visuals-card.png)
3. Sleep **MaxDaysPending** vanuit **Projectaanvragen** in het deelvenster **Velden** naar **Velden** in het deelvenster **Visualisaties**.
   
    ![Velden in het deelvenster Visualisaties](./media/sharepoint-scenario-build-report/05-03-12-value-max.png)
4. Klik of tik op **Opmaak** (verfroller) en stel **Rand** in op **Aan**.
   
    ![Opmaak kopiëren/plakken: rand](./media/sharepoint-scenario-build-report/05-03-13a-format.png)
5. Stel **Title** in op **Aan** en voeg de titel 'Maximum aantal dagen in wachtrij' toe.
   
    ![Titel toevoegen](./media/sharepoint-scenario-build-report/05-03-13b-title.png)
   
    De visualisatie moet er nu uitzien als in de volgende afbeelding.
   
    ![ Maximaal aantal dagen wachtend op goedkeuring](./media/sharepoint-scenario-build-report/05-03-14-chart-max.png)
   
    Nadat we dit rapport hebben gepubliceerd, gebruiken we deze tegel om een waarschuwing te activeren als de maximumwaarde voor een wachtend project een bepaalde drempelwaarde bereikt.

### <a name="create-a-table-that-shows-the-time-between-project-approval-and-projected-start-date"></a>Een tabel maken met de tijd tussen de goedkeuring en de begindatum van een project
1. Klik of tik op het canvas buiten de visualisatie die u zojuist hebt gemaakt.
2. Klik of tik in het deelvenster **Visualisaties** aan de rechterkant op **Tabel**.
   
    ![Visualisaties: tabel](./media/sharepoint-scenario-build-report/05-03-15-visuals-table.png)
3. Sleep **PMAssigned**, **Title** en **ApprovedStartDiff** vanuit **Projectdetails** in het deelvenster **Velden** naar **Waarden** in het deelvenster **Visualisaties**.
   
    ![Waarden in het deelvenster Visualisaties](./media/sharepoint-scenario-build-report/05-03-16-value-diff.png)
4. Sleep **ProjectedStartDate** vanuit **Projectdetails** in het deelvenster **Velden** naar het gebied **Filters** van het deelvenster **Visualisaties**. Selecteer vervolgens alle datums, behalve voor **(Leeg)**.
   
    ![Filter op ProjectedStartDate](./media/sharepoint-scenario-build-report/05-03-17-filters-diff.png)
5. Wijzig de grootte van de kolommen van de tabel zodat u alle gegevens kunt zien en sorteer op **ApprovedStartDiff**, aflopend. De visualisatie moet er nu uitzien als in de volgende afbeelding.
   
    ![Tabel met ApprovedStartDiff-waarden](./media/sharepoint-scenario-build-report/05-03-18-chart-diff.png)
6. Klik of tik in het gebied **Waarden** op de pijl-omlaag voor **ApprovedStartDiff** en klik of tik vervolgens op **Gemiddelde**. Nu zien we de gemiddelde duur tussen de goedkeuring van een project en de beoogde begindatum.
   
    ![Gemiddelde berekenen](./media/sharepoint-scenario-build-report/05-03-20a-average-menu.png)
7. Klik of tik opnieuw op de pijl-omlaag voor **ApprovedStartDiff**, klik of tik op **Voorwaardelijke opmaak** en vervolgens op **Achtergrondkleurschalen**.
   
   ![Voorwaardelijke opmaak](./media/sharepoint-scenario-build-report/05-03-20b-conditional-menu.png)
8. Stel kleuren in voor de velden **Minimum** en **Maximum** zoals hieronder aangegeven en klik of tik vervolgens op **OK**.
   
   ![Opties voor voorwaardelijke opmaak](./media/sharepoint-scenario-build-report/05-03-21-conditional-dialog.png)
   
   De visualisatie moet er nu uitzien als in de volgende afbeelding.
   
   ![Voorwaardelijke opmaak voltooid](./media/sharepoint-scenario-build-report/05-03-22-chart-diff-completed.png)
   
   Zoals u ziet hebben de projecten van Quentin van Groesen de neiging een stuk later te beginnen na de goedkeuring ervan. Mogelijk spelen er andere factoren dan de toegewezen manager, maar het is de moeite waard hier eens naar te kijken.

Hiermee zijn we bij het eind van de sectie over rapporten gekomen. U zou nu een volledig rapport moeten hebben op basis van gegevens die zijn geïmporteerd vanuit SharePoint en opgeschoond en gemodelleerd in Power BI Desktop. Als alles volgens plan is verlopen, zou uw rapport er moeten uitzien zoals in de volgende afbeelding.

![Voltooid rapport](./media/sharepoint-scenario-build-report/05-03-23-report-completed.png)

## <a name="next-steps"></a>Volgende stappen
De volgende stap in deze reeks zelfstudies bestaat uit het [publiceren van het Power BI-projectrapport en het maken van een dashboard](sharepoint-scenario-publish-report.md).

