---
title: Een modelgestuurde app maken of bewerken met de appontwerper in PowerApps | MicrosoftDocs
description: Apps maken of bewerken met de appontwerper
keywords: ''
ms.date: 05/23/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 2a44229e-44f0-4c4e-ba21-a476210d0a12
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 19
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-a-model-driven-app-by-using-the-app-designer"></a>Zelfstudie: Een modelgestuurde app maken of bewerken met de appontwerper

In deze zelfstudie leert u de grondbeginselen voor het maken en bewerken van een modelgestuurde app met de op tegels gebaseerde appontwerper.

## <a name="prerequisites"></a>Vereisten
Controleer of u aan de volgende vereisten voldoet voordat u begint met het maken van een app:
- Een PowerApps-omgeving. Meer informatie: [Een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment)
- Beveiligingsrol Systeembeheerder of Systeemaanpasser. Meer informatie: [Vooraf gedefinieerde beveiligingsrollen](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app#about-predefined-security-roles)
 
<a name="createApp"></a>   
## <a name="create-an-app"></a>Een app maken  

1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2. Selecteer **Apps** en **Een app maken**.

3. Voer op de pagina **Een nieuwe app maken** de volgende gegevens in: 

    - **Naam**: voer een naam in voor de app.  
  
    - **Unieke naam**: de unieke naam wordt automatisch ingevuld op basis van de appnaam die u opgeeft. De naam wordt voorafgegaan door een voorvoegsel van de uitgever. U kunt het bewerkbare deel van de unieke naam wijzigen. De unieke naam mag alleen Engelse tekens en getallen bevatten.  
  
        > [!NOTE]
        >  Het uitgeversvoorvoegsel is de tekst die wordt toegevoegd aan entiteiten of velden die worden gemaakt voor een oplossing met deze uitgever.   
  
    - **Beschrijving**: typ een korte beschrijving van wat de app is of doet.  
  
    - **Pictogram**: standaard is het selectievakje **Standaardapp gebruiken** ingeschakeld. Als u een andere webresource als pictogram voor de app wilt selecteren, schakelt u het selectievakje uit en selecteert u een pictogram in de vervolgkeuzelijst. Dit pictogram wordt weergegeven op de voorbeeldtegel van de app.  
  
    - Selecteer het clienttype waarvoor de app wordt gebruikt.  
  
        - **Unified Interface**: dit is de nieuwere responsieve webbrowserclient die een soortgelijke interface heeft voor pc's en mobiele apparaten.  

        - **Web**: dit is de klassieke webbrowserclient voor Dynamics 365 Customer Engagement.  
    
    - **Achtervoegsel van app-URL**: de app-URL wordt automatisch ingevuld op basis van de appnaam die u opgeeft. U krijgt een voorbeeld van de volledige URL te zien. De app-URL moet uniek zijn.  
  
         Bijvoorbeeld: https://\<org>.crm#.dynamics.com/Apps/\<App URL>

         Voor on-premises: http://\<server>/\<orgnaam>/Apps/\<App-URL> 
  
      > [!NOTE]
      >  Als u de inhoud van het veld **Achtervoegsel van app-URL** wist en vervolgens de app opslaat, wordt de URL van de app automatisch gegenereerd op basis van de app-id.  
  
    - **Bestaande oplossing gebruiken om de app te maken**: selecteer deze optie om de app te maken op basis van een lijst met geïnstalleerde oplossingen. Als u deze optie selecteert, verandert **Gereed** in **Volgende** in de koptekst. Als u **Volgende** selecteert, wordt de pagina **App maken op basis van bestaande oplossing** geopend. Selecteer in de vervolgkeuzelijst **Oplossing selecteren** een oplossing van waaruit u de app wilt maken. Als een siteoverzicht beschikbaar is voor de geselecteerde oplossing, wordt de vervolgkeuzelijst **Siteoverzicht selecteren** weergegeven. Selecteer het siteoverzicht en selecteer vervolgens **Gereed**.

      > [!NOTE]
      > Als u **Standaardoplossing** selecteert tijdens het toevoegen van een siteoverzicht, worden de onderdelen die aan dat siteoverzicht zijn gekoppeld automatisch toegevoegd aan de app.  

      ![Pagina Bestaande oplossing gebruiken om de app te maken](media/use-existing-solution-to-create-the-app.png "Bestaande oplossing gebruiken om de app te maken") 

    - **Een welkomstpagina kiezen**: met deze optie kunt u kiezen uit de webresources die beschikbaar zijn in uw organisatie. De welkomstpagina's die u maakt, kunnen nuttige informatie voor gebruikers bevatten zoals koppelingen naar video's, upgrade-instructies of informatie om aan de slag te gaan. De welkomstpagina wordt weergegeven wanneer een app wordt geopend. Gebruikers kunnen op de welkomstpagina **Dit welkomstscherm de volgende keer niet weergeven** selecteren zodat de pagina niet meer wordt getoond wanneer de app een volgende keer wordt gestart. Voor meer informatie over het maken van een webresource, zoals een HTML-bestand die u als welkomstpagina kunt gebruiken, raadpleegt u: [Webresources maken en bewerken om de webtoepassing uit te breiden](create-edit-web-resources.md).  
      
    Als u appeigenschappen later wilt bewerken, gaat u naar het tabblad **Eigenschappen** in de appontwerper. Meer informatie: [Appeigenschappen beheren](manage-app-properties.md)  
  
     > [!NOTE]
     >  U kunt de unieke naam en het achtervoegsel van de app-URL niet wijzigen op het tabblad **Eigenschappen**.  
  
4. Selecteer **Gereed** of, als u **Bestaande oplossing gebruiken om de app te maken** hebt geselecteerd, de optie **Volgende** om een keuze te maken uit de beschikbare oplossingen die in de organisatie zijn geïmporteerd.  
  
    Er wordt een nieuwe app met de status Concept gemaakt. Het canvas van de appontwerper voor de nieuwe app wordt weergegeven. Hier kunt u onderdelen toevoegen, bijvoorbeeld entiteiten, weergaven en dashboards, om uw app nuttig te maken. Meer informatie: [Apponderdelen toevoegen of bewerken](add-edit-app-components.md)  
   
<a name="editApp"></a>   
## <a name="edit-an-app"></a>Een app bewerken  
  
1.  Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

> [!IMPORTANT]
> Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2. In het linkernavigatiedeelvenster selecteert u **Apps**. Vervolgens selecteert u een app en selecteert u **Bewerken** op de werkbalk.   

3. In de appontwerper kunt u onderdelen toevoegen of bewerken. Meer informatie: [Apponderdelen toevoegen of bewerken](add-edit-app-components.md)  
 
  
### <a name="next-steps"></a>Volgende stappen  
 [Apponderdelen toevoegen of bewerken](add-edit-app-components.md)   


