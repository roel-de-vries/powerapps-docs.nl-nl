---
title: Gegevens integreren in Common Data Service voor apps
description: Gegevens uit meerdere bronnen integreren in Common Data Service voor apps
author: sabinn-msft
ms.service: powerapps
ms.topic: how-to
ms.component: cds
ms.date: 09/19/2018
ms.author: sabinn
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: b8cebc6f9db8a1a7c1a060aad461f4f32fcee05b
ms.sourcegitcommit: 2bcf40aeaa35420dc43f5803f4e57ff0f6afb57b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/19/2018
ms.locfileid: "46469098"
---
# <a name="integrate-data-into-common-data-service-for-apps"></a>Gegevens integreren in Common Data Service voor apps

<!--note from editor: the style guide says not to use "the" in front of Common Data Service for Apps, so I'm removing that.-->

De Gegevensintegrator (voor beheerders) is een point-to-point-integratieservice die wordt gebruikt om gegevens te integreren in Common Data Service voor apps. Deze biedt ondersteuning voor integratie van gegevens uit meerdere bronnen (bijvoorbeeld: Dynamics 365 for Finance and Operations, Dynamics 365 for Sales en SalesForce (Preview), SQL (Preview)) in Common Data Service voor apps. Het ondersteunt ook de integratie van gegevens in Dynamics 365 for Finance and Operations en Dynamics 365 for Sales. Deze service is algemeen beschikbaar sinds juli 2017.  

We zijn begonnen met eigen apps, bijvoorbeeld Dynamics 365 for Finance and Operations en Dynamics 365 for Sales. Met behulp van Power Query of op M gebaseerde connectoren kunnen we nu ook aanvullende bronnen ondersteunen, zoals SalesForce (Preview) en SQL (Preview). In de nabije toekomst wordt dit uitgebreid met meer dan twintig bronnen. 

> [!div class="mx-imgBorder"]
> ![Gegevensbron naar doel](media/data-integrator/DataIntegratorP2P-new.PNG "Gegevensbron naar doel")

## <a name="how-can-you-use-the-data-integrator-for-your-business"></a>Hoe kunt u de Gegevensintegrator gebruiken voor uw bedrijf?

De Gegevensintegrator (voor beheerders) biedt ook ondersteuning voor op proces gebaseerde integratiescenario's als Prospect to Cash. Dergelijke scenario's bieden directe synchronisatie tussen Dynamics 365 for Finance and Operations en Dynamics 365 for Sales. De Prospect to Cash-sjablonen die beschikbaar zijn met de functie voor gegevensintegratie maken de stroom van gegevens mogelijk voor accounts, contactpersonen, producten, offertes, verkooporders en facturen tussen Finance en Operations and Sales. Terwijl gegevens stromen tussen Finance and Operations en Sales, kunt u verkoop- en marketingactiviteiten uitvoeren in Sales en kunt u orders verwerken met behulp van Voorraadbeheer in Finance and Operations. 

> [!div class="mx-imgBorder"]
> ![Prospect to Cash](media/data-integrator/ProspectToCash631.png "Prospect to Cash")

Dankzij de Prospect to Cash-integratie kunnen verkopers hun verkoopprocessen verwerken en controleren met de sterke punten van Dynamics 365 for Sales. Tegelijkertijd vinden alle aspecten van de uitvoering en facturering plaats met behulp van de uitgebreide functionaliteit in Finance and Operations. Met Microsoft Dynamics 365 Prospect to Cash-integratie ontvangt u de gecombineerde kracht van beide systemen. 

Zie de video: [Prospect to Cash-integratie](https://www.youtube.com/watch?v=AVV9x5x-XCg)

Zie voor meer informatie over de Prospect to Cash-integratie de documentatie over de [Prospect to Cash-oplossing](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/prospect-to-cash).

We ondersteunen ook [Field Service-integratie](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order) en [PSA-integratie (Project Service Automation)](https://docs.microsoft.com/dynamics365/unified-operations/financials/project-management/psa-integration?toc=/fin-and-ops/toc.json) naar Dynamics 365 voor Financiën and Operations.

## <a name="data-integrator-platform"></a>Gegevensintegratorplatform

De Gegevensintegrator (voor beheerders) bestaat uit het platform Gegevensintegratie, gebruiksklare sjablonen geleverd door onze toepassingsteams (bijvoorbeeld Dynamics 365 for Finance and Operations en Dynamics 365 for Sales) en aangepaste sjablonen die zijn gemaakt door onze klanten en partners. We hebben een platform met agnostische apps gebouwd dat op verschillende bronnen kan worden geschaald. U maakt verbindingen (met integratie-eindpunten) en kiest u een van de aanpasbare sjablonen met vooraf gedefinieerde toewijzingen (die u verder kunt aanpassen). Vervolgens maakt u het project voor gegevensintegratie en voert u het uit.  

Sjablonen voor integratie fungeren als een blauwdruk met vooraf gedefinieerde entiteiten en veldtoewijzingen om de stroom van gegevens van bron naar doel mogelijk te maken. Het biedt ook de mogelijkheid om de gegevens te transformeren voordat ze worden geïmporteerd. In veel gevallen kan het schema tussen de bron- en doel-apps heel verschillend zijn. Een sjabloon met vooraf gedefinieerde entiteiten en veldtoewijzingen fungeert dan als een goed startpunt voor een integratieproject.  

> [!div class="mx-imgBorder"]
> ![Gegevensintegratieplatform](media/data-integrator/DIPlatform.PNG "Gegevensintegratieplatform")

## <a name="how-to-set-up-a-data-integration-project"></a>Over het instellen van een project voor gegevensintegratie

Er zijn drie belangrijke stappen:

1. Maak een verbinding (geef referenties aan gegevensbronnen).

2. Maak een verbindingsset (identificeer omgevingen voor verbindingen die u in de vorige stap hebt gemaakt).

3. Maak een project voor gegevensintegratie met behulp van een sjabloon (maak of gebruik vooraf gedefinieerde toewijzingen voor een of meer entiteiten).

Zodra u een project voor gegevensintegratie hebt gemaakt, kunt u het project handmatig uitvoeren en voor de toekomst een op schema gebaseerde vernieuwing instellen. In de rest van dit artikel worden deze drie stappen verder uitgelegd.

### <a name="how-to-create-a-connection"></a>Een verbinding maken

Voordat u een project voor gegevensintegratie kunt maken, moet u een verbinding inrichten voor elk systeem waarmee u wilt werken in de Microsoft PowerApps-portal. U kunt deze verbindingen beschouwen als uw integratiepunten.

**Een verbinding maken**

1. Ga naar [PowerApps-beheercentrum](https://admin.powerapps.com).

2. Selecteer onder gegevens **Verbindingen** en selecteer vervolgens **Nieuwe verbinding**.

3. U kunt een verbinding selecteren in de lijst met verbindingen of zoeken naar uw verbinding.

    > [!div class="mx-imgBorder"] 
    > ![Verbinding maken](media/data-integrator/CreateConnection780.png "Verbinding maken")

4. Als u de verbinding hebt geselecteerd, selecteert u **Maken**. Vervolgens wordt u gevraagd om referenties.

5. Nadat u uw referenties hebt opgegeven, wordt de verbinding weergegeven onder uw verbindingen.

    > [!div class="mx-imgBorder"] 
    > ![Lijst met verbindingen](media/data-integrator/CreateConnection1780.png "Lijst met verbindingen")

### <a name="how-to-create-a-connection-set"></a>Een verbindingsset maken

Verbindingssets zijn een verzameling van twee verbindingen, omgevingen voor de verbindingen, toewijzingsinformatie over de organisatie en integratiesleutels die in andere projecten kunnen worden hergebruikt. U kunt een verbindingsset eerst gebruiken voor ontwikkeling en vervolgens voor productie overschakelen op een andere. Een belangrijk stukje informatie dat wordt opgeslagen met een verbindingsset, bestaat uit de toewijzingen van de organisatie-eenheid, bijvoorbeeld toewijzingen tussen de juridische entiteit Finance and Operations (of het bedrijf) en Dynamics 365 for Sales-organisatie of -business units. U kunt meerdere organisatie-toewijzingen opslaan in een verbindingsset.

**Een verbindingsset maken**

1. Ga naar [PowerApps-beheercentrum](https://admin.powerapps.com).

2. Selecteer het tabblad **Gegevensintegratie** in het navigatiedeelvenster links.

3. Selecteer het tabblad **Verbindingssets** en selecteer **Nieuwe verbindingsset**.

4. Geef uw verbindingsset een naam.
  
    > [!div class="mx-imgBorder"] 
    > ![Verbindingsset maken](media/data-integrator/CreateConnectionSet1780.png "Verbindingsset maken")
  
5. Kies de verbindingen die u eerder hebt gemaakt en selecteer de juiste omgeving.

6. Herhaal de stappen door uw volgende verbinding te kiezen (beschouw deze als bron en doel in geen specifieke volgorde).

7. Geef de organisatie naar Business Unit-toewijzing op (als u tussen integreert tussen Finance and Operations- en Sales-systemen).
  
    > [!NOTE]
    > U kunt meerdere toewijzingen opgeven voor elke verbindingsset.
  
8. Nadat u alle velden hebt ingevuld, selecteert u **Maken**.

9. U ziet de nieuwe verbindingsset die u zojuist hebt gemaakt op de lijstpagina Verbindingssets.
    
    > [!div class="mx-imgBorder"] 
    > ![Lijst Verbindingsset](media/data-integrator/CreateConnectionSet2780.png "Lijst Verbindingsset")

De verbindingsset kan worden gebruikt voor verschillende integratieprojecten.

### <a name="how-to-create-a-data-integration-project"></a>Een project voor gegevensintegratie maken

Projecten maken de stroom van gegevens tussen systemen mogelijk. Een project bevat toewijzingen voor een of meer entiteiten. Toewijzingen geven aan welke velden worden toegewezen aan welke andere velden.

**Een project voor gegevensintegratie maken**

1. Ga naar [PowerApps-beheercentrum](https://admin.powerapps.com).

2. Selecteer het tabblad **Gegevensintegratie** in het linker navigatiedeelvenster.

3. Selecteer op het tabblad **Projecten** de optie **Nieuw Project** in de rechterbovenhoek.

    > [!div class="mx-imgBorder"] 
    > ![Project maken](media/data-integrator/CreateNewProject780.png "project maken")

4. Geef uw project voor gegevensintegratie een naam.

5. Selecteer een van de beschikbare sjablonen (of [maak uw eigen sjabloon](#how-to-customize-or-create-your-own-template)). In dit geval verplaatsen we de entiteit Producten uit Finance and Operations naar Sales.

    > [!div class="mx-imgBorder"] 
    > ![Sjabloon selecteren om nieuw project te maken](media/data-integrator/CreateNewProjectSelectTemplate780.png "Sjabloon selecteren om nieuw project te maken")

6. Selecteer **Volgende** en kies een verbindingsset die u eerder hebt gemaakt (of [maak een nieuwe verbindingsset](#how-to-create-a-connection-set)).

7. Controleer of u de juiste hebt gekozen door de namen van de verbinding en omgeving te bevestigen.

    > [!div class="mx-imgBorder"] 
    > ![Een nieuwe verbindingsset maken](media/data-integrator/CreateNewProjectSelectConnectionSet780.png "Een nieuwe verbindingsset maken")

8. Selecteer **Volgende** en kies vervolgens de rechtspersoon naar Business Unit-toewijzingen.

    > [!div class="mx-imgBorder"] 
    > ![Nieuwe rechtspersoontoewijzing maken](media/data-integrator/CreateNewProjectLegalEntityMapping780.png "Nieuwe rechtspersoontoewijzing maken")

9. Lees en accepteer de privacyverklaring en geef toestemming in het volgende scherm.

10. Ga verder met het maken van het project. Voer vervolgens het project uit waarna op zijn beurt het project wordt uitgevoerd.

    > [!div class="mx-imgBorder"] 
    > ![Project uitvoeren](media/data-integrator/RunProject780.png "Project uitvoeren")

    In dit scherm ziet u meerdere tabbladen, **Planning** en **Uitvoeringsgeschiedenis**, samen met enkele knoppen, **Taak toevoegen**, **Entiteiten vernieuwen** en **Geavanceerde query**, die verderop in dit artikel worden beschreven.

### <a name="execution-history"></a>Uitvoeringsgeschiedenis

<!--note from editor: Do you think most people reading this will know what "upsert" means?-->

Uitvoeringsgeschiedenis geeft de geschiedenis weer van alle uitvoeringen met de naam van het project, timestamp van wanneer het project was uitgevoerd en de status van de uitvoering, samen met het aantal upsert-bewerking en/of fouten.

-   Voorbeeld van de projectuitvoeringsgeschiedenis.

    > [!div class="mx-imgBorder"] 
    > ![Projectuitvoeringsgeschiedenis](media/data-integrator/ExecutionHistorySuccessFailures4780.png "Projectuitvoeringsgeschiedenis")

-   Voorbeeld van geslaagde uitvoering, waarbij de status wordt weergegeven als voltooid met \# upsert-bewerking. (Update Insert is een logica om de record bij te werken, als deze al bestaat, of een nieuwe record in te voegen.)

    > [!div class="mx-imgBorder"] 
    > ![Uitvoering geslaagd](media/data-integrator/ExecutionHistorySuccess2780.png "Uitvoering geslaagd")

-   In het geval van uitvoeringsfouten kunt u inzoomen om de hoofdoorzaken te zien.

    Hierna volgt een voorbeeld van een fout met projectvalidatiefouten. In dit geval is de projectvalidatiefout ontstaan door ontbrekende bronvelden in de entiteitstoewijzingen.

    > [!div class="mx-imgBorder"] 
    > ![Fout in uitvoeringsgeschiedenis](media/data-integrator/ExecutionHistoryFailures3780.png "Fout in uitvoeringsgeschiedenis")

-   Als de projectuitvoering de status 'FOUT' heeft, probeert deze de uitvoering opnieuw tijdens de volgende geplande uitvoering.

-   Als de projectuitvoering de status 'WAARSCHUWING' heeft, moet u problemen op de bron oplossen. De uitvoering wordt opnieuw geprobeerd bij de volgende geplande uitvoering.

    In beide gevallen kunt u er ook voor kiezen om handmatig de 'uitvoering opnieuw uit te voeren’.

### <a name="how-to-set-up-a-schedule-based-refresh"></a>Een vernieuwing op basis van een planning instellen

We ondersteunen tegenwoordig twee typen uitvoeringen/schrijfbewerkingen:

-   Handmatige schrijfbewerkingen (project handmatig uitvoeren en vernieuwen)

-   Schrijfbewerkingen op basis van een schema (automatisch vernieuwen)

Nadat u een project voor gegevensintegratie hebt gemaakt, krijgt u de optie om het handmatig uit te voeren of om schrijfbewerkingen op basis van een schema te configureren, waarmee u automatische vernieuwingen van uw projecten kunt instellen.

**Op schema gebaseerde schrijfbewerkingen instellen**

1. Ga naar [PowerApps-beheercentrum](https://admin.powerapps.com).

2. U kunt projecten op twee verschillende manieren plannen.<br>

    U kunt het project selecteren en het tabblad **Schema** selecteren. U kunt ook de scheduler starten vanaf de pagina met de projectlijst door te klikken op het weglatingsteken naast de naam van het project.

    > [!div class="mx-imgBorder"] 
    > ![Schrijfbewerkingen op basis van een schema](media/data-integrator/Schedulebasedwrites780.png "Schrijfbewerkingen op basis van een schema")

3. Selecteer **Herhalen elke** en selecteer **Planning opslaan** nadat u alle velden hebt ingevuld.

    > [!div class="mx-imgBorder"] 
    > ![Schrijfbewerkingen op basis van een schema](media/data-integrator/Schedulebasedwrites1780.png "Schrijfbewerkingen op basis van een schema")

U kunt een frequentie zo vaak als 1 minuut instellen. U kunt ook om een bepaald aantal uren, dagen, weken of maanden laten herhalen. Houd er rekening mee dat de volgende vernieuwing pas start als de vorige projecttaak is uitgevoerd.

Houd er ook rekening mee dat u onder Meldingen kunt kiezen voor op e-mailadres gebaseerde waarschuwingsmeldingen. Dergelijke meldingen waarschuwen u bij taakuitvoeringen die ofwel zijn voltooid met waarschuwingen en/of mislukt vanwege fouten. U kunt meerdere ontvangers opgeven, inclusief groepen gescheiden door komma's.

> [!div class="mx-imgBorder"] 
> ![E-mailmelding](media/data-integrator/EmailNotification780.png "E-mailmelding")

## <a name="customizing-projects-templates-and-mappings"></a>Projecten, sjablonen en toewijzingen aanpassen 

U kunt een sjabloon gebruiken om een project voor gegevensintegratie te maken. Een sjabloon standaardiseert de verplaatsing van gegevens die op zijn beurt een zakelijke gebruiker of beheerder helpt de integratie van gegevens uit bronnen naar de bestemming te versnellen en de algemene overhead en kosten vermindert. Een zakelijke gebruiker of beheerder kan beginnen met een gebruiksklare sjabloon die is gepubliceerd door Microsoft of haar partners. Deze sjabloon kan vervolgens verder worden aangepast voordat een project wordt gemaakt. U kunt het project opslaan als een sjabloon en delen met uw organisatie en/of een nieuw project maken. 

Een sjabloon voorziet u in bron, doel en richting van de gegevensstroom. Houd dit in gedachten wanneer u uw eigen sjabloon aanpast en/of maakt.  

U kunt projecten en sjablonen op de volgende manieren aanpassen:

-   Veldtoewijzingen aanpassen.

-   U kunt een sjabloon aanpassen door een entiteit van uw keuze toe te voegen.

### <a name="how-to-customize-field-mappings"></a>Veldtoewijzingen aanpassen

**Een verbindingsset maken**

1. Ga naar [PowerApps-beheercentrum](https://admin.powerapps.com).

2. Selecteer het project waarvoor u veldtoewijzingen wilt aanpassen en selecteer vervolgens de pijl tussen de bron- en doelvelden.

    > [!div class="mx-imgBorder"] 
    > ![Veldtoewijzing](media/data-integrator/FieldMapping780.png "Veldtoewijzing")

3. Hiermee gaat u naar het toewijzingsscherm waar u een nieuwe toewijzing kunt toevoegen door **Toewijzing toevoegen** te selecteren in de rechterbovenhoek of **Bestaande toewijzingen aanpassen** in de vervolgkeuzelijst.

    > [!div class="mx-imgBorder"] 
    > ![Veldtoewijzing aanpassen](media/data-integrator/FieldMappingCustomize780.png "Veldtoewijzing aanpassen")

4. Als u uw veldtoewijzingen hebt aangepast, selecteert u **Opslaan**.

### <a name="how-to-customize-or-create-your-own-template"></a>Uw eigen sjabloon maken of aanpassen 

**Uw eigen sjabloon maken**

1. Ga naar [PowerApps-beheercentrum](https://admin.powerapps.com).

2. Identificeer de bron- en doel en richting van de stroom voor de nieuwe sjabloon.

3. Maak een project door een bestaande sjabloon te kiezen die overeenkomt met uw gekozen bron en doel en stroomrichting.

<!--note from editor: Didn't we create the project in step 3? Step 4 tells us to create the project.-->

4. Maak het project na de juiste verbinding te hebben gekozen.

5. Voordat u het project opslaat en/of uitvoert, selecteert u in de rechterbovenhoek **Taak toevoegen**.

    > [!div class="mx-imgBorder"] 
    > ![Sjabloon aanpassen](media/data-integrator/CustomizeTemplate780.png "Sjabloon aanpassen")

    Hiermee wordt het dialoogvenster **Taak toevoegen** geopend.

6. Geef de taak een betekenisvolle naam en voeg bron- en doelentiteiten toe.

    > [!div class="mx-imgBorder"] 
    > ![Sjabloon aanpassen taak toevoegen](media/data-integrator/CustomizeTemplateAddtask75.png "Sjabloon aanpassen taak toevoegen")

7. In de vervolgkeuzelijst staan al uw bron- en doelentiteiten.

    > [!div class="mx-imgBorder"] 
    > ![Sjabloon aanpassen taak toevoegen](media/data-integrator/CustomizeTemplateAddtask175.png "Sjabloon aanpassen taak toevoegen")

    In dit geval werd een nieuwe taak gemaakt om de gebruikersentiteit van SalesForce te synchroniseren met de gebruikersentiteit in Common Data Service voor apps.

    > [!div class="mx-imgBorder"] 
    > ![Sjabloon aanpassen taak toevoegen](media/data-integrator/CustomizeTemplateAddtask275.png "Sjabloon aanpassen taak toevoegen")

8. Wanneer u de taak hebt gemaakt, wordt de nieuwe taak weergegeven en kunt u de oorspronkelijke taak verwijderen.

    > [!div class="mx-imgBorder"] 
    > ![Sjabloon aanpassen taak toevoegen](media/data-integrator/CustomizeTemplateAddtask3780.png "Sjabloon aanpassen taak toevoegen")

9. U hebt net een nieuwe sjabloon gemaakt: in dit geval een sjabloon om gegevens over de gebruikersentiteit uit SalesForce te halen en naar Common Data Service over te brengen. Selecteer **Opslaan** om uw aanpassing op te slaan.

10. Volg de stappen om de veldtoewijzingen voor deze nieuwe sjabloon aan te passen. U kunt dit project uitvoeren en/of het project opslaan als een sjabloon vanaf de pagina **Projectlijst**.

    > [!div class="mx-imgBorder"] 
    > ![Sjabloon aanpassen opslaan als sjabloon](media/data-integrator/CustomizeTemplateSaveAsTemplate780.png "Sjabloon aanpassen opslaan als sjabloon")

11. Geef een naam en beschrijving en/of deel met anderen in uw organisatie.

    > [!div class="mx-imgBorder"] 
    > ![Sjabloon aanpassen opslaan als sjabloon](media/data-integrator/CustomizeTemplateSaveAsTemplate175.png "Sjabloon aanpassen opslaan als sjabloon")

## <a name="advanced-data-transformation-and-filtering"></a>Geavanceerde gegevenstransformatie en filteren 

Met Power Query-ondersteuning bieden we nu geavanceerd filteren en transformatie van brongegevens. Met Power Query kunnen gebruikers de vorm van hun gegevens wijzigen zodat deze bij hun behoeften passen, met een eenvoudig te gebruiken, aantrekkelijke en codeloze gebruikerservaring. U kunt dit per project inschakelen. 

### <a name="how-to-enable-advanced-query-and-filtering"></a>Geavanceerde query’s en filters inschakelen

**Geavanceerde filters en gegevenstransformatie instellen**

1. Ga naar [PowerApps-beheercentrum](https://admin.powerapps.com).

2. Selecteer het project waar u geavanceerde query’s wilt inschakelen en selecteer vervolgens **Geavanceerde query**.

    > [!div class="mx-imgBorder"] 
    > ![Geavanceerde query selecteren](media/data-integrator/EnablePQ1780.png "Geavanceerde query selecteren")

3. U krijgt een waarschuwing dat het inschakelen van geavanceerde query’s een eenmalige bewerking is en niet ongedaan kan worden gemaakt. Selecteer **OK** om verder te gaan en selecteer vervolgens de bron- en bestemmingstoewijzingpijl.

    > [!div class="mx-imgBorder"] 
    > ![Waarschuwing](media/data-integrator/EnablePQ275.png "Waarschuwing")

4. U ziet nu de vertrouwde pagina met entiteitstoewijzing met een koppeling om Geavanceerde query's en filteren te starten.

    > [!div class="mx-imgBorder"] 
    > ![Geavanceerde query's en filters](media/data-integrator/EnablePQ3780.png "Geavanceerde query's en filters")

5. Selecteer **Koppelen** om de gebruikersinterface Geavanceerde query’s en filteren te starten. Hier vindt u bronveldgegevens in kolommen van het type Microsoft Excel.

    > [!div class="mx-imgBorder"] 
    > ![Geavanceerde query's en filters](media/data-integrator/EnablePQ4780.png "Geavanceerde query's en filters")

6. In het menu bovenaan staan verschillende opties om gegevens te transformeren, zoals **Voorwaardelijke kolom toevoegen**, **Dubbele kolom**, en **Extraheren**.

    > [!div class="mx-imgBorder"] 
    > ![Kolom toevoegen](media/data-integrator/EnablePQAddColumn75.png "Kolom toevoegen")

7. U kunt ook met de rechtermuisknop klikken op een andere kolom voor meer opties, zoals **Kolommen verwijderen**, **Dubbele waarden verwijderen** en **Kolom splitsen**.

    > [!div class="mx-imgBorder"] 
    > ![Met de rechtermuisknop op kolom klikken](media/data-integrator/EnablePQAddColumn180.png "Met de rechtermuisknop op kolom klikken")

8. U kunt ook filteren door op elke kolom te klikken en filters van het type Excel te gebruiken.

    > [!div class="mx-imgBorder"] 
    > ![Filteren inschakelen](media/data-integrator/EnablePQFiltering80.png "Filteren inschakelen")

<!--note from editor: I don't see an "otherwise" in the screenshot. I see "else".-->

9. Met de voorwaardelijke kolom kunnen transformaties van standaardwaarden worden bereikt. Om dit te doen, selecteert u in de vervolgkeuzelijst **Kolom toevoegen** de optie **Voorwaardelijke kolom toevoegen** en voert u de naam van de nieuwe kolom in. Vul in zowel **Dan** als **Anders** de standaardwaarde in met behulp van elk veld en waarde voor **Als** en **Gelijk aan**.

    > [!div class="mx-imgBorder"] 
    > ![Voorwaardelijke kolom toevoegen](media/data-integrator/EnablePQDefaultValueTransforms2780.png "Voorwaardelijke kolom toevoegen")

10. U ziet de component **elke** in de *fx* -editor, aan de bovenkant.

    > [!div class="mx-imgBorder"] 
    > ![fx-editor](media/data-integrator/EnablePQDefaultValueTransforms2780.png "fx-editor")

11. Verbeter de component **elke** in de *fx* -editor en selecteer **OK**.

    > [!div class="mx-imgBorder"] 
    > ![De component elke verbeteren](media/data-integrator/EnablePQDefaultValueTransforms5780.png "De component elke verbeteren")

<!--note from editor: The sentence that starts with "Additionally" is confusing - not sure where the "same steps" fit in.-->

12. Telkens wanneer u een wijziging aanbrengt, past u een stap toe. U ziet de toegepaste stappen in het rechter deelvenster (schuif naar beneden om de laatste stap te zien). U kunt een stap ongedaan maken als u moet bewerken. Verder kunt u naar de geavanceerde editor door met de rechtermuisknop te klikken op **QrySourceData** bovenaan in het linkerdeelvenster om de M-taal weer te geven die op de achtergrond wordt uitgevoerd, met dezelfde stappen.

    > [!div class="mx-imgBorder"] 
    > ![Geavanceerde editor](media/data-integrator/EnablePQDefaultValueTransforms4780.png "Geavanceerde editor")

13. Selecteer **OK** om de interface Geavanceerde query's en filters te sluiten en kies vervolgens op de taakoverzichtpagina de zojuist gemaakte kolom als de bron om de toewijzing dienovereenkomstig te maken.

    > [!div class="mx-imgBorder"] 
    > ![Nieuwe kolom kiezen](media/data-integrator/EnablePQDefaultValueTransforms6780.png "Nieuwe kolom kiezen")

Zie [Power Query-documentatie](https://docs.microsoft.com/power-query/) voor meer informatie over Power Query.
