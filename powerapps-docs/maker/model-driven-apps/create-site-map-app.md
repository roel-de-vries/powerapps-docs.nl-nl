---
title: Een siteoverzicht voor een modelgestuurde app maken in PowerApps | MicrosoftDocs
description: Een siteoverzicht voor uw app maken
keywords: ''
ms.date: 05/29/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 2461bd71-6cb4-46b7-8d1f-6a0aa3dca809
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 18
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-a-model-driven-app-site-map-for-an-app-using-the-site-map-designer"></a>Zelfstudie: Een siteoverzicht voor een modelgestuurde app maken met de siteoverzichtontwerper

In deze zelfstudie voert u verschillende taken voor siteoverzichten uit, zoals het maken van een nieuw siteoverzicht en het toevoegen van een gebied, groep en subgebied.

Siteoverzichten bepalen de navigatie voor uw app. Maak eenvoudig een siteoverzicht voor uw app met de siteoverzichtontwerper met tegels. Gebruik de ontwerpfunctie om onderdelen naar het ontwerpcanvas te slepen, uw werk te bekijken en direct het siteoverzicht te publiceren. Systeemaanpassers of andere gebruikers met de vereiste bevoegdheden kunnen snel siteoverzichten voor apps maken.  
  
Met de siteoverzichtontwerper kunt u ook het gebied, subgebied of groepstitels opgeven in de talen die door de omgeving worden ondersteund.  
  
Een standaardsiteoverzicht is beschikbaar. U kunt dit siteoverzicht bewerken of siteoverzichten voor nieuwe apps configureren door de siteoverzichtontwerper te gebruiken. De siteoverzichtontwerper is geïntegreerd in de appontwerper.  

## <a name="prerequisites"></a>Vereisten
Zorg dat u de beveiligingsrol systeembeheerder of systeemaanpasser of gelijkwaardige machtigingen hebt.  Iedere gebruiker met de volgende bevoegdheden kan ook apps maken:  
-   De bevoegdheden Maken, Lezen en Schrijven voor de entiteit App  
-   De bevoegdheden Lezen en Schrijven voor de entiteit Aanpassingen  
-   Leesbevoegdheden voor de entiteit Oplossing

Deze bevoegdheden zijn te vinden of in te stellen op het tabblad **Aanpassing** van een beveiligingsrol.
  
## <a name="create-a-site-map-for-an-app"></a>Een siteoverzicht voor een app maken  
  
1. Selecteer op het canvas van de appontwerper in het gebied **Siteoverzicht** de knop **Siteoverzichtontwerper openen** ![Knop Siteoverzichtontwerper openen](media/dynamics365-open-designer.PNG "Knop Siteoverzichtontwerper openen").  
  
     De siteoverzichtontwerper wordt geopend met een canvas dat automatisch vooraf wordt gevuld met één gebied, één groep en één subgebied. Selecteer de tegel voor het gebied, de groep of het subgebied om de eigenschappen te wijzigen.  
  
    > [!NOTE]
    >  Wanneer u de knop **Siteoverzichtontwerper openen** ![Knop Siteoverzichtontwerper openen](media/dynamics365-open-designer.PNG "Knop Siteoverzichtontwerper openen") selecteert op het canvas van de appontwerper, wordt automatisch een nieuw siteoverzicht gemaakt (als er nog geen siteoverzicht voor de app bestaat) en krijgt het nieuwe siteoverzicht dezelfde naam als de appnaam en dezelfde unieke naam als de unieke naam van de app. 

   ![Siteoverzicht selecteren](media/app-designer-sitemap-location.png "Siteoverzicht selecteren") 
  
2.  [Een gebied toevoegen aan het siteoverzicht](create-site-map-app.md#bkmk_AddArea).  
  
3.  [Een groep toevoegen aan het siteoverzicht](create-site-map-app.md#bkmk_AddGroup).  
  
4.  [Een subgroep toevoegen aan een groep in het siteoverzicht](create-site-map-app.md#bkmk_AddSubarea).  
  
5.  Selecteer **Opslaan**.  
  
    > [!NOTE]
    >  Het nieuwe siteoverzicht wordt gekoppeld aan de app wanneer u in de appontwerper **Opslaan** selecteert. Wanneer een siteoverzicht is geconfigureerd, wordt **Geconfigureerd** weergegeven op de siteoverzichttegel; anders wordt **Niet geconfigureerd** weergegeven op de tegel.  Als u de siteoverzichtontwerper vanuit de appontwerper opent en een nieuw siteoverzicht configureert, maar de browser sluit voordat het siteoverzicht aan de app is gekoppeld, wordt het siteoverzicht automatisch aan de app gekoppeld zodra u de appontwerper weer opent, op basis van de unieke naam van de app.  
  
6.  Selecteer **Publiceren**.  
  
## <a name="edit-the-default-site-map"></a>Het standaardsiteoverzicht bewerken 

 Uw omgeving wordt geleverd met een standaardsiteoverzicht.  
  
1. Open de oplossingenverkenner.  
  
2. Selecteer in het oplossingslossingsvenster onder **Onderdelen** de optie **Clientuitbreidingen**.  

3. Selecteer op de werkbalk voor onderdelen de optie **Bestaande toevoegen** > **Siteoverzicht**.

4. In de lijst met oplossingsonderdelen selecteert u het siteoverzicht **Siteoverzicht** en vervolgens selecteert u **OK**.
  
5.  Dubbelklik om het toegevoegde siteoverzicht te selecteren met de weergavenaam **Siteoverzicht** en de status **Beheerd**. U kunt ook het siteoverzicht selecteren en op de werkbalk **Bewerken** selecteren.  
  
     Het siteoverzicht wordt geopend in de siteoverzichtontwerper.  
  
6.  [Een gebied toevoegen aan het siteoverzicht](create-site-map-app.md#bkmk_AddArea).  
  
7.  [Een groep toevoegen aan het siteoverzicht](create-site-map-app.md#bkmk_AddGroup).  
  
8.  [Een subgroep toevoegen aan een groep in het siteoverzicht](create-site-map-app.md#bkmk_AddSubarea).  
  
9. Selecteer **Opslaan**.  
  
10. Selecteer **Publiceren**.  
  
<a name="bkmk_AddArea"></a>   
## <a name="add-an-area-to-the-site-map"></a>Een gebied toevoegen aan het siteoverzicht  
  
1.  Selecteer de knop **Toevoegen** ![Knop Toevoegen in de ontwerper](media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") op het canvas van de siteoverzichtontwerper en selecteer vervolgens **Gebied**.  
  
     of  
  
     Sleep op het tabblad **Onderdelen** de tegel **Gebied** naar het lege vak in het canvas. U ziet het lege vak wanneer u de tegel naar de juiste plaats in het canvas verplaatst.  
  
2.  Selecteer het gebied dat u zojuist hebt toegevoegd. Het tabblad **Eigenschappen** wordt gemarkeerd in het deelvenster aan de rechterkant van het canvas.  
  
3.  Voeg de gebiedseigenschappen to of bewerk deze:  
  
     Doe het volgende onder **Algemeen**:  
  
    - **Titel**: voer de titel voor het gebied in, in de standaardtaal van de organisatie.  
  
    - **Pictogram**: er wordt een standaardpictogram voor toepassingen geselecteerd. Selecteer een ander pictogram voor het gebied in de lijst met webresources die beschikbaar zijn in de oplossing.  
  
    - **Id**: er wordt automatisch een unieke id gegenereerd, maar u kunt ook een andere id invoeren als u wilt. Het wordt aangeraden om de geleverde id te gebruiken. Als uw ingevoerde id niet uniek is, kunnen gebruikers een foutmelding krijgen tijdens het gebruik van de app, of u kunt een foutmelding krijgen wanneer u een oplossing met dit siteoverzicht importeert.  
  
    - **Groepen weergeven**: schakel dit selectievakje in om groepen van subgebieden in het navigatiedeelvenster weer te geven.  
  
     Doe het volgende onder **Geavanceerd**:  
  
    - **Meer titels**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal (Landinstellingen) voor de titel, voert u de titel in en selecteert u de knop **Toevoegen** ![Knop Toevoegen in de siteoverzichtontwerper](media/add-icon-sitemap-designer.png "Knop Toevoegen in de siteoverzichtontwerper"). U kunt titels maken, bewerken of verwijderen voor zoveel talen als uw organisatie gebruikt. U kunt echter slechts één titel per taal hebben.  
  
    - **Meer beschrijving**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal voor de beschrijving, voert u de beschrijving in en selecteert u de knop **Toevoegen** ![Knop Toevoegen in de siteoverzichtontwerper](media/add-icon-sitemap-designer.png "Knop Toevoegen in de siteoverzichtontwerper"). U kunt beschrijvingen maken, bewerken of verwijderen voor zoveel talen als uw organisatie gebruikt. U kunt echter slechts één beschrijving per taal hebben.  
  
    - **URL**: voer de URL in die moet worden gegenereerd voor de Dynamics 365 for Outlook-map voor het gebied.  
  
<a name="bkmk_AddGroup"></a>   
## <a name="add-a-group-to-the-site-map"></a>Een groep toevoegen aan het siteoverzicht  
  
1.  Selecteer in het canvas van de siteoverzichtontwerper het gebied waaraan u de groep wilt toevoegen.  
2.  Selecteer de knop **Toevoegen** ![Knop Toevoegen in de ontwerper](media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") en selecteer vervolgens **Groep**.  
  
     of  
  
     Sleep op het tabblad **Onderdelen** de tegel **Groep** naar een leeg vak onder het **Gebied** in het canvas. U ziet het lege vak wanneer u de tegel naar de juiste plaats in het canvas verplaatst.  
  
3.  Selecteer de groep die u zojuist hebt toegevoegd.  
  
4.  Op het tabblad **Eigenschappen** kunt u groepseigenschappen toevoegen of bewerken:  
  
     Doe het volgende onder **Algemeen**:  
  
    - **Titel**: voer de titel voor de groep in, in de standaardtaal van de organisatie.  
  
    - **Id**: er wordt automatisch een unieke id gegenereerd. Voer zo nodig een andere id in. Het wordt aangeraden om de automatische id te gebruiken, omdat een fout kan optreden als uw ingevoerde id niet uniek is en u een oplossing met dit siteoverzicht importeert.  
  
     Doe het volgende onder **Geavanceerd**:  
  
    - **Meer titels**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal (Landinstellingen) voor de titel, voert u de titel voor de groep in en selecteert u de knop **Toevoegen** ![Knop Toevoegen in de siteoverzichtontwerper](media/add-icon-sitemap-designer.png "Knop Toevoegen in de siteoverzichtontwerper"). U kunt titels maken, bewerken of verwijderen voor zoveel talen als uw organisatie gebruikt. U kunt echter slechts één titel per taal hebben.  
  
    - **Meer beschrijvingen**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal voor de beschrijving, voert u de beschrijving voor de groep in en selecteert u de knop **Toevoegen** ![Knop Toevoegen in de siteoverzichtontwerper](media/add-icon-sitemap-designer.png "Knop Toevoegen in de siteoverzichtontwerper"). U kunt beschrijvingen maken, bewerken of verwijderen voor zoveel talen als uw organisatie gebruikt. U kunt echter slechts één beschrijving per taal hebben.  
  
    - **URL**: voer de URL in die moet worden gegenereerd voor de Dynamics 365 for Outlook-map voor de groep.  
  
    - **Instellen als profiel**: schakel dit selectievakje in om aan te geven of deze groep een door de gebruiker te selecteren profiel voor de werkplek vertegenwoordigt. De groep die als door gebruikers te selecteren profiel is ingesteld, wordt beschikbaar als optie in uw persoonlijke opties. Dit geldt alleen voor groepen in het gebied **Werkplek**.  
  
<a name="bkmk_AddSubarea"></a>   
## <a name="add-a-subarea-to-a-group-in-the-site-map"></a>Een subgroep toevoegen aan een groep in het siteoverzicht  
  
1.  Selecteer de knop **Toevoegen** ![Knop Toevoegen in de ontwerper](media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") op het canvas van de siteoverzichtontwerper en selecteer vervolgens **Subgebied**.  
  
     of  
  
     Sleep op het tabblad **Onderdelen** de tegel **Subgebied** naar een leeg vak onder de sectie **Groep** in het canvas. U ziet het lege vak wanneer u de tegel naar de juiste plaats in het canvas verplaatst.  
  
2.  Selecteer het subgebied dat u zojuist hebt toegevoegd.  
  
3.  Op het tabblad **Eigenschappen** kunt u subgroepeigenschappen toevoegen of bewerken:  
  
     Doe het volgende onder **Algemeen**:  
  
    - **Type**: geef op of het subgebied dat u toevoegt een dashboard, entiteit, webresource of URL is.  
  
    - **Entiteit**: selecteer de entiteit waarvoor het subgebied bestemd is. Dit veld is uitgeschakeld als een ander subgebiedtype dan **Entiteit** is geselecteerd in de vervolgkeuzelijst **Type**.  
  
    - **URL**: geef de URL voor de hoofdpagina van de toepassing op die moet worden weergegeven als dit subgebied wordt geselecteerd. Dit veld is uitgeschakeld als u **Entiteit** in de vervolgkeuzelijst **Type** hebt geselecteerd.  
  
    - **Standaarddashboard**: selecteer het standaarddashboard dat voor dit subgebied moet worden weergegeven. Dit veld is uitgeschakeld als u in de vervolgkeuzelijst **Type** niet **Entiteit** hebt geselecteerd.  
  
    - **Titel**: voer de titel voor het subgebied in, in de standaardtaal van de organisatie.  
  
    - **Pictogram**: er wordt een standaardpictogram voor toepassingen geselecteerd. Selecteer een ander pictogram voor het subgebied in de lijst met webresources die beschikbaar zijn in de oplossing.  
  
    - **ID**. Er wordt automatisch een unieke id gegenereerd. Voer zo nodig een unieke id in.  
  
    - **Parameters doorgeven**. Schakel dit selectievakje in om informatie over de organisatie en taalcontext door te geven aan de URL. Dit selectievakje is alleen ingeschakeld als het subgebiedtype een webresource of een subgebied op URL-basis is.  
  
     Doe het volgende onder **Geavanceerd**:  
 
    - **Bevoegdheden**: hiermee bepaalt u of een subgebied moet worden weergegeven op basis van beschikbare bevoegdheden in de beveiligingsrollen die zijn toegewezen aan de gebruiker. Selecteer de naam van de entiteit om bevoegdheden te bekijken en schakel vervolgens de selectievakjes in om bevoegdheden toe te wijzen. 
  
    - **Meer titels**: als uw organisatie gebruik maakt van meerdere talen, selecteert u een taal (Landinstelling) voor de titel, voert u de titel voor het subgebied in en selecteert u **Toevoegen**. U kunt titels maken, bewerken of verwijderen voor zoveel talen als uw organisatie gebruikt. U kunt echter slechts één titel per taal hebben.  
  
    - **Meer beschrijvingen**: als uw organisatie gebruik maakt van meerdere talen, selecteert u een taal voor de beschrijving, voert u de beschrijving voor het subgebied in en selecteert u **Toevoegen**. U kunt beschrijvingen maken, bewerken of verwijderen voor zoveel talen als uw organisatie gebruikt. U kunt echter slechts één beschrijving per taal hebben.  
  
    - **SKU's**: selecteer de versies van Dynamics 365 Customer Engagement waarin dit subgebied wordt weergegeven.  
  
    - **Client**: selecteer het type client waarin dit subgebied wordt weergegeven.  
  
    - **Snelkoppeling naar Outlook**: selecteer het pictogram om weer te geven in Dynamics 365 for Outlook.  
  
    - **Offlinebeschikbaarheid**: schakel dit selectievakje in om dit subgebied beschikbaar te maken voor gebruikers als ze offline zijn in Dynamics 365 for Outlook.  
  
## <a name="organize-areas-groups-and-subareas"></a>Gebieden, groepen en subgebieden indelen  
 U kunt uw gebieden, groepen en subgebieden indelen door ze naar nieuwe posities te slepen. Er wordt een containervak weergegeven waarin u de tegels kunt neerzetten. U kunt onder andere het volgende doen:  
  
-   Verplaats een subgebied naar een nieuwe positie binnen dezelfde groep of een andere groep onder hetzelfde gebied.  
  
-   Verplaats een subgebied naar een nieuwe positie in een groep onder een ander gebied.  
  
-   Verplaats een groep naar een nieuwe positie in hetzelfde gebied.  
  
-   Verplaats een groep naar een nieuwe positie in een ander gebied.  
  
-   Verplaats een gebied naar een nieuwe positie.  
  
## <a name="clone-a-component-in-a-site-map"></a>Een onderdeel in een siteoverzicht klonen  
 Als u een kopie van een bestaand onderdeel wilt maken, selecteert u het onderdeel en selecteert u op de werkbalk Actie de optie **Klonen**.  Alle gegevens van het gekloonde onderdeel komen overeen met die van het basisonderdeel, met uitzondering van de id en titel. De id wordt willekeurig gegenereerd. 
  
 Wanneer u een gebied kloont, wordt het gekloonde gebied rechts van het geselecteerde gebied toegevoegd. Wanneer u een groep kloont, wordt de gekloonde groep rechts van de geselecteerde groep toegevoegd. Wanneer u een subgebied kloont, wordt het gekloonde subgebied onder het geselecteerde subgebied toegevoegd.  
  
## <a name="delete-an-area-group-or-subarea-from-a-site-map"></a>Een gebied, groep of subgebied uit een siteoverzicht verwijderen  
 Als u een siteoverzichtonderdeel wilt verwijderen, selecteert u de onderdeeltegel en selecteert u op de balk Actie de optie **Verwijderen**. Wanneer u een gebied verwijdert, worden alle groepen en subgebieden in het gebied ook verwijderd. En wanneer u een groep verwijdert, worden de groep en subgebieden hierin ook verwijderd.  
  
## <a name="clients-supported"></a>Ondersteunde clients  
 In de volgende tabel worden de clients beschreven die voor verschillende siteoverzichten worden ondersteund.  
 
|Siteoverzichten|Ondersteunde clients|  
|---------------|-----------------------|  
|Nieuwe apps| Webapp voor Unified Interface en Dynamics 365 Customer Engagement |  
|Siteoverzicht voor de aangepaste Dynamics 365-app | Webapp voor Dynamics 365 Customer Engagement en Dynamics 365 for Outlook |  
|Standaard bedrijfsapps (Sales, Sales Hub, Customer Service, Customer Service Hub, Field Service, Project Service Automation)| Webapp voor Dynamics 365 Customer Engagement en Unified Interface|  
 
  
### <a name="next-steps"></a>Volgende stappen  
 [Een app maken of bewerken](create-edit-app.md)   
 [Apponderdelen toevoegen of bewerken](add-edit-app-components.md)
