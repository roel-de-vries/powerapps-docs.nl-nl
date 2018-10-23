---
title: Toegang tot formulieren regelen voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Leren hoe toegang tot hoofdformulieren wordt beheerd
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 15d123e0-b604-45dd-ab34-0b37787a04bb
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: a895bd9ea0257585f942840924a7044a4dcc23fb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675031"
---
# <a name="control-access-to-model-driven-app-forms"></a>Toegang tot modelgestuurde app-formulieren beheren

 Er zijn twee manieren waarop u toegang tot hoofdformulieren kunt regelen:  
  
- **Een hoofdformulier inactief maken**  
  
     U kunt een hoofdformulieren met een actieve of inactieve status instellen. Deze functie is met name ingevoegd voor het beheer van nieuwe formulieren die zijn ingevoegd tijdens de upgrade van Dynamics 365 Customer Engagement-organisaties. U kunt deze functie ook gebruiken om te voorkomen dat gebruikers elk willekeurig hoofdformulier kunnen gebruiken.   
  
- **Beveiligingsrollen toewijzen aan het hoofdformulier**  
  
     Gebruik deze methode om een hoofdformulier beschikbaar te maken voor specifieke groepen.  
  
 Verschillende gebruikers in uw organisatie kunnen op verschillende manieren met dezelfde gegevens werken. Managers moeten mogelijk snel informatie in een record kunnen scannen en servicemedewerkers hebben mogelijk een formulier nodig om de invoer van gegevens te stroomlijnen. U kunt een oplossing geven voor verschillende vereisten door formulieren toe te wijzen aan de beveiligingsrollen waarvan verschillende groepen gebruikers deel uitmaken.  
  
 Voor stapsgewijze procedures raadpleegt u [Beveiligingsrollen toewijzen aan formulieren](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form).  
  
 Wanneer u meer dan één hoofdformulier of mobiel formulier hebt gedefinieerd voor een entiteit, kunt u selecteren welke formulieren gebruikers mogen gebruiken op basis van hun beveiligingsrollen. Omdat in elke entiteit een formulier voor elke gebruiker moet kunnen worden weergegeven, moet er minimaal één formulier als ‘alternatief’ formulier worden aangewezen: een formulier dat zichtbaar is voor gebruikers aan wiens beveiligingsrollen geen expliciete formulieren zijn toegewezen.  
  
> [!NOTE]
>  Formulieren van het type Snel maken en Snel weergeven kunnen niet worden toegewezen aan beveiligingsrollen.  
  
 In de formuliereditor of vanuit het formulierenraster kunt u beveiligingsrollen toewijzen aan een formulier. Als er echter maar één formulier voor de entiteit is, kunt u de optie **Ingeschakeld als alternatief** in het dialoogvenster **Beveiligingsrollen toewijzen** niet wissen. In dit geval kan iedereen die aan een niet-ingevoegde beveiligingsrol is gekoppeld alsnog het formulier zien omdat dit als alternatief is ingeschakeld, zelfs als u beveiligingsrollen aan het formulier hebt toegewezen.  
  
 Nadat u een tweede hoofdformulier of mobiel formulier voor de entiteit hebt gemaakt, kunt u de optie **Ingeschakeld als alternatief** voor één van de formulieren wissen. Het systeem zorgt er altijd voor dat ten minste één formulier is ingeschakeld als alternatief.  
  
 Wanneer u meer dan één hoofdformulier hebt, kunt u een formuliervolgorde opgeven waarmee wordt bepaald welke van de formulieren die een gebruiker mag zien als standaard wordt weergegeven. Als er meer dan één formulier is dat ze mogen gebruiken, kunnen ze formulieren wijzigen; het formulier dat ze kiezen wordt hun standaardformulier totdat ze een ander formulier kiezen. Deze voorkeursinstelling wordt opgeslagen in de browser van de gebruiker. Als de gebruiker een andere computer of browser gebruikt, ziet deze het oorspronkelijke standaardformulier.  
  
## <a name="strategies-to-manage-the-fallback-form"></a>Strategieën voor het beheren van het alternatieve formulier  
 Strategieën voor het beheren van het alternatieve formulier zijn onder andere:  
  
<a name="BKMK_DoNotUseMultipleForms"></a>   
### <a name="all-users-view-the-same-form"></a>Alle gebruikers zien hetzelfde formulier  
 Als u niet meerdere formulieren voor een entiteit nodig hebt, hebt u geen alternatief formulier nodig.  
  
<a name="BKMK_Contingecyform"></a>   
### <a name="create-a-contingency-form"></a>Een noodformulier maken  
 Als u op rollen gebaseerde formulieren gebruikt omdat u de informatie wilt beperken die gebruikers kunnen zien of bewerken, kunt u een formulier maken waarop maar minimale informatie wordt weergegeven. Vervolgens selecteert u in het dialoogvenster **Beveiligingsrollen toewijzen** de optie **Alleen deze geselecteerde beveiligingsrollen weergeven** (selecteer, met uitzondering van systeembeheerder, geen andere rollen) en selecteer **Ingeschakeld als alternatief**. Hierdoor is dit formulier nooit zichtbaar voor anderen, behalve voor de systeembeheerder en gebruikers wiens beveiligingsrollen niet aan een specifiek formulier zijn gekoppeld. U kunt een HTML-webresource in het formulier insluiten met informatie over de reden waarom een aantal gegevens zichtbaar is in het formulier en een koppeling naar informatie over de manier waarop u kunt een aanvraag kunt indienen om te worden toegevoegd aan een beveiligingsrol die aan een formulier is gekoppeld of hoe u een nieuwe beveiligingsrol voor een formulier kunt insluiten.  
  
> [!NOTE]
>  U kunt geen webresource in de voet- of koptekst van een formulier invoegen.  
  
<a name="BKMK_CreateGenericForm"></a>   
## <a name="create-a-generic-form"></a>Een generiek formulier maken  
 Als u op rollen gebaseerde formulieren gebruikt om een aangepaste ervaring te bieden op basis van de rol van een gebruiker, kunt u uw minst specialistische formulier instellen als alternatief formulier en dit zodanig configureren dat dit voor iedereen wordt weergegeven. Maak vervolgens aangepaste formulieren voor specifieke beveiligingsrollen en configureer die formulieren zodat ze alleen worden weergegeven voor beveiligingsrollen die dergelijke formulieren nodig hebben. Schakel deze formulieren niet in als alternatief. Gebruik als laatste in de lijst **Formulieren** het dialoogvenster **Formuliervolgorde** om op te geven welke formulieren moeten worden weergegeven, op volgorde van meest exclusief naar minst exclusief. Uw alternatieve formulier staat onderaan de lijst. Door deze strategie zien gebruikers het formulier dat voor hun rol is aangepast als standaardformulier. Ze kunnen echter nog wel de formulierkiezer gebruiken om desgewenst het meestgebruikte formulier te selecteren. Het formulier dat een gebruiker selecteert, blijft het standaardformulier totdat een ander formulier wordt geselecteerd.  
  
<a name="BKMK_UseFormScripting"></a>   
## <a name="use-form-scripting"></a>Formulierscripts gebruiken  

 Als laatste is het voor ontwikkelaars in de webtoepassing mogelijk (maar niet aanbevolen) om scripts in het formulier Gebeurtenis laden te gebruiken, zodat de [ Xrm.Page.ui.formSelector.items-verzameling](http://go.microsoft.com/fwlink/p/?LinkID=513300) kan worden gebruikt om een query uit te voeren voor beschikbare formulieren en de navigatiemethode te gebruiken om gebruikers naar een specifiek formulier te verwijzen. Vergeet niet dat het formulier door de [navigatiemethode](http://go.microsoft.com/fwlink/p/?LinkID=513301) opnieuw wordt geladen (en de gebeurtenis Laden weer optreedt). Uw logica in de gebeurtenis-handler moet altijd controleren of er sprake is van een bepaalde voorwaarde voordat u de navigatiemethode gebruikt, om een oneindige lus te voorkomen of te voorkomen dat gebruikersopties voor navigeren tussen formulieren onnodig worden beperkt.  
  
 Deze benadering werkt niet voor Dynamics 365 voor tablets omdat meerdere formulieren niet beschikbaar zijn om te selecteren.  

### <a name="next-steps"></a>Volgende stappen  

[Beveiligingsrollen aan formulieren toewijzen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form)
