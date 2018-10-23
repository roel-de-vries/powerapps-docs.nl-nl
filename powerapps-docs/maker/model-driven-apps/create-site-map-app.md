---
title: Een siteoverzicht voor modelgestuurde apps voor een app maken in PowerApps | MicrosoftDocs
description: Informatie over het maken van een siteoverzicht voor uw app
keywords: ''
ms.date: 05/29/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 2461bd71-6cb4-46b7-8d1f-6a0aa3dca809
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 18
topic-status: Drafting
ms.openlocfilehash: 2c3f1f4f22df6ed8b4824f1942e3fd202362ea9d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39676356"
---
# <a name="tutorial-create-a-model-driven-app-site-map-for-an-app-using-the-site-map-designer"></a>Zelfstudie: een siteoverzicht voor modelgestuurde apps voor een app maken met de siteoverzichtontwerper

In deze zelfstudie voert u verschillende taken voor siteoverzichten uit, zoals het maken van een nieuw siteoverzicht en het toevoegen van een gebied, groep en subgebied.

Met siteoverzichten definieert u de navigatie voor uw app. Maak gemakkelijk een siteoverzicht voor uw app door de siteoverzichtontwerper op basis van een tegel te gebruiken. Gebruik de ontwerper om onderdelen naar het ontwerpcanvas te slepen, een voorbeeld van uw werk weer te geven en het siteoverzicht direct te publiceren. Systeemaanpassers en gebruikers met de vereiste bevoegdheden kunnen snel siteoverzichten voor apps maken.  
  
U kunt met de siteoverzichtontwerper ook het gebied, het subgebied of de groepstitels definiëren in de talen die door de omgeving worden ondersteund.  
  
Er is een standaardsiteoverzicht beschikbaar. U kunt dit siteoverzicht bewerken of siteoverzichten voor nieuwe apps configureren met behulp van de siteoverzichtontwerper. De siteoverzichtontwerper is geïntegreerd met de appontwerper.  

## <a name="prerequisites"></a>Vereisten
Controleer of u de beveiligingsrol Systeembeheerder of Systeemaanpasser of equivalente machtigingen hebt.  Ook kunnen gebruikers met de volgende bevoegdheden apps maken:  
-   Maak-, lees- en schrijfbevoegdheden voor de App-entiteit  
-   Lees- en schrijfbevoegdheden voor de Aanpassingen-entiteit  
-   Leesbevoegdheden voor de Oplossing-entiteit

U kunt deze bevoegdheden weergeven of instellen op het tabblad **Aanpassing** van een beveiligingsrol.
  
## <a name="create-a-site-map-for-an-app"></a>Een siteoverzicht voor een app maken  
  
1. Selecteer op het canvas van de appontwerper in het gebied **Siteoverzicht** **De siteoverzichtontwerper openen** ![Knop Siteoverzichtontwerper openen](media/dynamics365-open-designer.PNG "Knop Siteoverzichtontwerper openen").  
  
     Hierop wordt een canvas geopend dat vooraf is ingevuld met één gebied, één groep en één subgebied. Selecteer de tegel voor het gebied, de groep of het subgebied om de eigenschappen ervan te wijzigen.  
  
    > [!NOTE]
    >  Als u **De siteoverzichtontwerper openen** ![Knop Siteoverzichtontwerper](media/dynamics365-open-designer.PNG "Knop Siteoverzichtontwerper") vanuit het canvas van de appontwerper selecteert, wordt automatisch een nieuw siteoverzicht gemaakt (als er geen bestaand siteoverzicht is) en krijgt het nieuwe siteoverzicht dezelfde naam als de naam van de app en dezelfde unieke naam als de unieke naam van de app. 

   ![Een siteoverzicht selecteren](media/app-designer-sitemap-location.png "Een siteoverzicht selecteren") 
  
2.  [Een gebied toevoegen aan het siteoverzicht](create-site-map-app.md#bkmk_AddArea).  
  
3.  [Een groep toevoegen aan het siteoverzicht](create-site-map-app.md#bkmk_AddGroup).  
  
4.  [Een subgebied toevoegen aan een groep in het siteoverzicht](create-site-map-app.md#bkmk_AddSubarea).  
  
5.  Selecteer **Opslaan**.  
  
    > [!NOTE]
    >  Het nieuwe siteoverzicht is gekoppeld aan de app als u naar de appontwerper teruggaat en **Opslaan** selecteert. Wanneer een siteoverzicht is geconfigureerd, wordt **Geconfigureerd** op de siteoverzichttegel weergegeven; anders wordt **Niet geconfigureerd** op de tegel weergegeven.  Als u de siteoverzichtontwerper vanuit de appontwerper opent en een nieuw siteoverzicht configureert maar de browser sluit voordat u het siteoverzicht aan de app koppelt, wordt het siteoverzicht automatisch op basis van de unieke naam van de app aan de app gekoppeld wanneer u de appontwerper opnieuw opent.  
  
6.  Selecteer **Publiceren**.  
  
## <a name="edit-the-default-site-map"></a>Het standaardsiteoverzicht bewerken 

 Uw omgeving wordt geleverd met een standaardsiteoverzicht.  
  
1. Open Solution Explorer.  
  
2. Selecteer in het oplossingenvenster onder **Onderdelen** de optie **Clientextensies**.  

3. Selecteer op de werkbalk van het onderdeel **Bestaande toevoegen** > **Siteoverzicht**.

4. Selecteer in de lijst met oplossingsonderdelen het siteoverzicht met de naam **Siteoverzicht** en selecteer vervolgens **OK**.
  
5.  Dubbelklik om het siteoverzicht te selecteren dat u hebt toegevoegd. Het siteoverzicht heeft de weergavenaam **Siteoverzicht** en de status **Beheerd**. U kunt het siteoverzicht ook selecteren en vervolgens op de werkbalk **Bewerken** selecteren.  
  
     Het siteoverzicht wordt geopend in de siteoverzichtontwerper.  
  
6.  [Een gebied toevoegen aan het siteoverzicht](create-site-map-app.md#bkmk_AddArea).  
  
7.  [Een groep toevoegen aan het siteoverzicht](create-site-map-app.md#bkmk_AddGroup).  
  
8.  [Een subgebied toevoegen aan een groep in het siteoverzicht](create-site-map-app.md#bkmk_AddSubarea).  
  
9. Selecteer **Opslaan**.  
  
10. Selecteer **Publiceren**.  
  
<a name="bkmk_AddArea"></a>   
## <a name="add-an-area-to-the-site-map"></a>Een gebied toevoegen aan het siteoverzicht  
  
1.  Selecteer **Toevoegen** ![Knop Toevoegen in de ontwerper](media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") op het canvas van de siteoverzichtontwerper en selecteer vervolgens **Gebied**.  
  
     of  
  
     Sleep vanaf het tabblad **Onderdelen** de tegel **Gebied** naar het lege vak op het canvas. U ziet het lege vak wanneer u de tegel naar de juiste plaats op het canvas verplaatst.  
  
2.  Selecteer het gebied dat u zojuist hebt toegevoegd. Het tabblad **Eigenschappen** is gemarkeerd in het deelvenster aan de rechterkant van het canvas.  
  
3.  Voeg gebiedseigenschappen toe of bewerk gebiedseigenschappen.  
  
     Ga onder **Algemeen** als volgt te werk:  
  
    - **Titel**: voer de titel in voor het gebied in de standaardtaal van de organisatie.  
  
    - **Pictogram**: er is een standaardtoepassingspictogram geselecteerd. Selecteer een ander pictogram voor het gebied in de lijst met webresources die beschikbaar zijn in de oplossing.  
  
    - **Id**: er wordt automatisch een unieke id gegenereerd, maar u kunt desgewenst een andere id invoeren. U wordt aangeraden de geleverde id te gebruiken. Als u namelijk een niet-unieke id invoert, kan er een foutbericht worden weergegeven wanneer gebruikers de app gebruiken of wanneer u een oplossing importeert die dit siteoverzicht bevat.  
  
    - **Groepen weergeven**: schakel dit selectievakje in om groepen subgebieden in het navigatievenster weer te geven.  
  
     Ga onder **Geavanceerd** als volgt te werk:  
  
    - **Meer titels**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal (Landinstellingen) voor de titel, voert u de titel in en selecteert u vervolgens **Toevoegen** ![Knop Toevoegen in de siteoverzichtontwerper](media/add-icon-sitemap-designer.png "Knop Toevoegen in de siteoverzichtontwerper"). U kunt titels maken, bewerken of verwijderen voor alle talen die door uw organisatie worden gebruikt. U kunt echter slechts één titel per taal hebben.  
  
    - **Meer beschrijvingen**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal voor de beschrijving, voert u de beschrijving in en selecteert u vervolgens **Toevoegen** ![Knop Toevoegen in de siteoverzichtontwerper](media/add-icon-sitemap-designer.png "Knop Toevoegen in de siteoverzichtontwerper"). U kunt beschrijvingen maken, bewerken of verwijderen voor alle talen die door uw organisatie worden gebruikt. U kunt echter slechts één beschrijving per taal hebben.  
  
    - **URL**: voer de URL in die moet worden weergegeven voor de Dynamics 365 voor Outlook-map die het gebied vertegenwoordigt.  
  
<a name="bkmk_AddGroup"></a>   
## <a name="add-a-group-to-the-site-map"></a>Een groep toevoegen aan het siteoverzicht  
  
1.  Selecteer op het canvas van de siteoverzichtontwerper het gebied waaraan u de groep wilt toevoegen.  
2.  Selecteer **Toevoegen** ![Knop Toevoegen in de ontwerper](media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") en selecteer vervolgens **Groep**.  
  
     of  
  
     Sleep vanaf het tabblad **Onderdelen** de tegel **Groep** naar een leeg vak onder **Gebied** op het canvas. U ziet het lege vak wanneer u de tegel naar de juiste plaats op het canvas verplaatst.  
  
3.  Selecteer de groep die u zojuist hebt toegevoegd.  
  
4.  Op het tabblad **Eigenschappen** kunt u groepseigenschappen toevoegen of bewerken:  
  
     Ga onder **Algemeen** als volgt te werk:  
  
    - **Titel**: voer de titel in voor de groep in de standaardtaal van de organisatie.  
  
    - **Id**: er wordt automatisch een unieke id gegenereerd. Voer desgewenst een andere id in. U wordt aangeraden de automatische id te gebruiken. Wanneer u namelijk een niet-unieke id invoert, kan er een foutbericht worden weergegeven wanneer u een oplossing met dit siteoverzicht importeert.  
  
     Ga onder **Geavanceerd** als volgt te werk:  
  
    - **Meer titels**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal (Landinstellingen) voor de titel, voert u de titel voor de groep in en selecteert u vervolgens **Toevoegen** ![Knop Toevoegen in de siteoverzichtontwerper](media/add-icon-sitemap-designer.png "Knop Toevoegen in de siteoverzichtontwerper"). U kunt titels maken, bewerken of verwijderen voor alle talen die door uw organisatie worden gebruikt. U kunt echter slechts één titel per taal hebben.  
  
    - **Meer beschrijvingen**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal voor de beschrijving, voert u de beschrijving voor de groep in en selecteert u vervolgens **Toevoegen** ![Knop Toevoegen in de siteoverzichtontwerper](media/add-icon-sitemap-designer.png "Knop Toevoegen in de siteoverzichtontwerper"). U kunt beschrijvingen maken, bewerken of verwijderen voor alle talen die door uw organisatie worden gebruikt. U kunt echter slechts één beschrijving per taal hebben.  
  
    - **URL**: voer de URL in die moet worden weergegeven voor de Dynamics 365 voor Outlook-map die de groep vertegenwoordigt.  
  
    - **Instellen als profiel**: schakel dit selectievakje in om aan te geven of deze groep een door de gebruiker te selecteren profiel voor de werkplek vertegenwoordigt. De groep die is ingesteld als een door de gebruiker te selecteren profiel, is als optie beschikbaar in uw persoonlijke opties. Dit geldt alleen voor groepen binnen het gebied **Werkplek**.  
  
<a name="bkmk_AddSubarea"></a>   
## <a name="add-a-subarea-to-a-group-in-the-site-map"></a>Een subgebied toevoegen aan een groep in het siteoverzicht  
  
1.  Selecteer **Toevoegen** ![Knop Toevoegen in de ontwerper](media/dynamics365-designer-addbutton.PNG "Knop Toevoegen in de ontwerper") op het canvas van de siteoverzichtontwerper en selecteer vervolgens **Subgebied**.  
  
     of  
  
     Sleep vanaf het tabblad **Onderdelen** de tegel **Subgebied** naar een leeg vak onder de sectie **Groep** op het canvas. U ziet het lege vak wanneer u de tegel naar de juiste plaats op het canvas verplaatst.  
  
2.  Selecteer het subgebied dat u zojuist hebt toegevoegd.  
  
3.  Op het tabblad **Eigenschappen** kunt u eigenschappen voor subgebieden toevoegen of bewerken:  
  
     Ga onder **Algemeen** als volgt te werk:  
  
    - **Type**: geef aan of het subgebied dat u toevoegt, een dashboard, entiteit, webresource of URL is.  
  
    - **Entiteit**: selecteer de entiteit waarvoor het subgebied bedoeld is. Dit veld is uitgeschakeld als het type subgebied anders is dan **Entiteit** in de vervolgkeuzelijst **Type**.  
  
    - **URL**: geef een URL voor de hoofdpagina van de toepassing op die moet worden weergegeven wanneer dit subgebied wordt geselecteerd. Dit veld is uitgeschakeld als u **Entiteit** hebt geselecteerd in de vervolgkeuzelijst **Type**.  
  
    - **Standaarddashboard**: selecteer het standaarddashboard dat voor dit subgebied moet worden weergegeven. Dit veld is uitgeschakeld als u **Dashboard** niet hebt geselecteerd in de vervolgkeuzelijst **Type**.  
  
    - **Titel**: voer de titel in voor het subgebied in de standaardtaal van de organisatie.  
  
    - **Pictogram**: er is een standaardtoepassingspictogram geselecteerd. Selecteer een ander pictogram voor het subgebied in de lijst met webresources die beschikbaar zijn in de oplossing.  
  
    - **Id**. Er wordt automatisch een unieke id gegenereerd. Voer desgewenst een andere unieke id in.  
  
    - **Parameters doorgegeven**. Schakel dit selectievakje in om gegevens over de organisatie en taalcontext aan de URL door te geven. Dit selectievakje is alleen ingeschakeld wanneer het type subgebied een webresource of een subgebied op basis van een URL is.  
  
     Ga onder **Geavanceerd** als volgt te werk:  
 
    - **Bevoegdheden**: hiermee definieert u of een subgebied wordt weergegeven op basis van bevoegdheden die beschikbaar zijn in beveiligingsrollen die zijn toegewezen aan de gebruiker. Selecteer de naam van de entiteit waar op bevoegdheden moet worden gecontroleerd en schakel vervolgens de selectievakjes in om bevoegdheden toe te wijzen. 
  
    - **Meer titels**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal voor de titel, voert u de titel voor het subgebied in en selecteert u vervolgens **Toevoegen**. U kunt titels maken, bewerken of verwijderen voor alle talen die door uw organisatie worden gebruikt. U kunt echter slechts één titel per taal hebben.  
  
    - **Meer beschrijvingen**: als uw organisatie gebruikmaakt van meerdere talen, selecteert u een taal voor de beschrijving, voert u de beschrijving voor het subgebied in en selecteert u vervolgens **Toevoegen**. U kunt beschrijvingen maken, bewerken of verwijderen voor alle talen die door uw organisatie worden gebruikt. U kunt echter slechts één beschrijving per taal hebben.  
  
    - **SKU's**: selecteer de versies van Dynamics 365 Customer Engagement waarmee dit subgebied wordt weergegeven.  
  
    - **Client**: selecteer het type client waarmee dit subgebied wordt weergegeven.  
  
    - **Outlook-snelkoppeling**: selecteer het pictogram dat in Dynamics 365 voor Outlook moet worden weergegeven.  
  
    - **Offline beschikbaar**: schakel dit selectievakje in om dit subgebied beschikbaar te stellen aan gebruikers als ze offline zijn in Dynamics 365 voor Outlook.  
  
## <a name="organize-areas-groups-and-subareas"></a>Gebieden, groepen en subgebieden indelen  
 U kunt uw gebieden, groepen en subgebieden indelen door ze naar een nieuwe positie te slepen. Er wordt een containervak weergegeven waar u de tegels kunt neerzetten. U kunt onder andere het volgende doen:  
  
-   Een subgebied verplaatsen naar een nieuwe positie binnen dezelfde groep of een andere groep in hetzelfde gebied.  
  
-   Een subgebied verplaatsen naar een nieuwe positie binnen een groep in een ander gebied.  
  
-   Een groep verplaatsen naar een nieuwe positie in hetzelfde gebied.  
  
-   Een groep verplaatsen naar een nieuwe positie in een ander gebied.  
  
-   Een gebied naar een nieuwe positie verplaatsen.  
  
## <a name="clone-a-component-in-a-site-map"></a>Een onderdeel in een siteoverzicht klonen  
 Als u een kopie van een bestaand onderdeel wilt maken, selecteert u het onderdeel en selecteert u vervolgens op de werkbalk **Klonen**.  Alle details van het gekloonde onderdeel zijn gelijk aan het basisonderdeel, behalve de id en titel. De id wordt willekeurig gegenereerd. 
  
 Wanneer u een gebied kloont, wordt het gekloonde gebied toegevoegd aan de rechterkant van het momenteel geselecteerde gebied. Wanneer u een groep kloont, wordt de gekloonde groep toegevoegd aan de rechterkant van de momenteel geselecteerde groep. Wanneer u een subgebied kloont, wordt het gekloonde subgebied toegevoegd onder het momenteel geselecteerde gebied.  
  
## <a name="delete-an-area-group-or-subarea-from-a-site-map"></a>Een gebied, groep of subgebied uit een siteoverzicht verwijderen  
 Als u een siteoverzichtonderdeel wilt verwijderen, selecteert u de onderdeeltitel en selecteert u vervolgens op de werkbalk **Verwijderen**. Wanneer u een gebied verwijdert, worden alle groepen en subgebieden in het gebied ook verwijderd. Op dezelfde manier worden bij het verwijderen van een groep ook de subgebieden verwijderd.  
  
## <a name="clients-supported"></a>Ondersteunde clients  
 U ziet in de volgende tabel welke clients worden ondersteund voor verschillende siteoverzichten.  
 
|Siteoverzichten|Ondersteunde clients|  
|---------------|-----------------------|  
|Nieuwe apps| Unified Interface en Dynamics 365 Customer Engagement-web-app |  
|Siteoverzicht voor de Dynamics 365 - aangepaste app | Dynamics 365 Customer Engagement-web-app en Dynamics 365 voor Outlook |  
|Standaard zakelijke apps (Sales, Sales Hub, Customer Service, Customer Service Hub, Field Service, Project Service Automation)| Dynamics 365 Customer Engagement-web-app en Unified Interface|  
 
  
### <a name="next-steps"></a>Volgende stappen  
 [Een app maken of bewerken](create-edit-app.md)   
 [App-onderdelen toevoegen of bewerken](add-edit-app-components.md)
