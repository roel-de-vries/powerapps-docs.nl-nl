---
title: Toegang tot formulieren voor modelgestuurde apps beheren in PowerApps | MicrosoftDocs
description: Informatie over het beheren van de toegang tot hoofdformulieren
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
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="control-access-to-model-driven-app-forms"></a>Toegang tot formulieren voor modelgestuurde apps beheren

 Er zijn twee wijzen waarop u de toegang tot hoofdformulieren kunt beheren:  
  
- **Een hoofdformulier inactief maken**  
  
     U kunt een actieve of inactieve status voor hoofdformulieren instellen. Deze functie is primair opgenomen om nieuwe formulieren te kunnen beheren wanneer Dynamics 365 Customer Engagement-organisaties upgrades uitvoeren, maar u kunt deze gebruiken om te verhinderen dat gebruikers elk hoofdformulier kunnen gebruiken.   
  
- **Beveiligingsrollen toewijzen aan het hoofdformulier**  
  
     Gebruik deze optie om een hoofdformulier aan specifieke groepen beschikbaar te maken.  
  
 Verschillende gebruikers in uw organisatie kunnen met dezelfde gegevens op verschillende wijzen interacteren. Managers kunnen snel gegevens kunnen willen doorzoeken en servicepersoneel kan een formulier vereisen dat gegevensinvoer stroomlijnt. U kunt aan verschillende vereisten voldoen door formulieren aan de beveiligingsrollen toe te wijzen waartoe de verschillende gebruikersgroepen behoren.  
  
 Raadpleeg voor stapsgewijze procedures [Beveiligingsrollen toewijzen aan formulieren](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form).  
  
 Als u meer dan één hoofdformulier of mobiel formulier voor een entiteit hebt gedefinieerd, dan kunt u selecteren welke formulieren gebruikers kunnen gebruiken op basis van hun beveiligingsrollen. Doordat elke entiteit een formulier voor elke gebruiker moet kunnen weergeven, moet minstens één formulier als 'reserveformulier' worden aangewezen: een formulier dat zichtbaar is voor gebruikers met beveiligingsrollen waaraan niet expliciet formulieren zijn toegewezen.  
  
> [!NOTE]
>  Formulieren voor snelle invoer en snelle-weergaveformulieren kunnen niet aan beveiligingsrollen zijn toegewezen.  
  
 In de formuliereneditor of vanuit het formulierenraster kunt u beveiligingsrollen toewijzen aan een formulier. Als er echter slechts één formulier bestaat voor de entiteit, dan kunt u de optie **Ingeschakeld voor reserve** niet wissen in het dialoogvenster **Beveiligingsrollen toewijzen**. Ondanks dat u beveiligingsrollen aan het formulier hebt toegewezen, kan iedereen die is gekoppeld aan een beveiligingsrol die u niet hebt opgenomen toch het formulier weergeven, omdat het is ingesteld als terugvalformulier.  
  
 Nadat u een tweede hoofdformulier of mobiel formulier hebt gemaakt voor de entiteit, kunt u de optie **Ingeschakeld voor reserve** wel uitschakelen voor een van de formulieren. Het systeem zorgt ervoor dat minstens één formulier is ingeschakeld als reserve.  
  
 Als u meer dan één hoofdformulier hebt, dan kunt u een formuliervolgorde specificeren die zal bepalen welke van de formulieren een gebruiker gewoonlijk zal en mag zien. Als er meer dan één formulier is dat ze kunnen gebruiker, dan kunnen ze formulieren wijzigen en het formulier dat ze kiezen zal hun standaardformulier zijn totdat ze een andere kiezen. Deze voorkeur wordt opgeslagen in de browser. Als ze een andere computer of een andere browser gebruiken, dan zullen het oorspronkelijke standaardformulier zien.  
  
## <a name="strategies-to-manage-the-fallback-form"></a>Strategieën om het terugvalformulier te beheren  
 De strategieën om het terugvalformulier te beheren omvatten de volgende:  
  
<a name="BKMK_DoNotUseMultipleForms"></a>   
### <a name="all-users-view-the-same-form"></a>Alle gebruikers geven hetzelfde formulier weer  
 Als u niet meerdere formulieren nodig hebt voor een entiteit, dan hebt u niet een terugvalformulier nodig.  
  
<a name="BKMK_Contingecyform"></a>   
### <a name="create-a-contingency-form"></a>Een contigentieformulier maken  
 Als u op rollen gebaseerde formulieren gebruikt omdat u de informatiepersoon wilt beperken die gebruikers wellicht weergeven of bewerken, overweeg dan een formulier te maken met minimaal weergegeven informatie. Selecteer vervolgens in het dialoogvenster **Beveiligingsrollen toewijzen** de optie **Alleen aan deze geselecteerde beveiligingsrollen weergeven**, maar selecteer geen rollen behalve Systeembeheerder en selecteer **Ingeschakeld voor reserve**. Het resultaat is dat dit formulier door niemand zal worden gezien behalve de systeembeheerder en iedereen met beveiligingsrollen die niet zijn gekoppeld aan een specifiek formulier. U kunt een HTML-webresource in het formulier opnemen met gegevens over waarom weinig gegevens in het formulier zichtbaar zijn en een koppeling naar informatie over hoe toevoeging aan een beveiligingsrol die is gekoppeld aan een formulier kan worden aangevraagd of om een nieuwe beveiligingsrol voor een formulier op te nemen.  
  
> [!NOTE]
>  U kunt een webresource niet opnemen in een formulierkoptekst of -voettekst.  
  
<a name="BKMK_CreateGenericForm"></a>   
## <a name="create-a-generic-form"></a>Een generiek formulier maken  
 Als u op rollen gebaseerde formulieren gebruikt om een aangepaste gebruikerservaring te bieden die is gebaseerd op de rol van een gebruiker, dan kunt u het minst gespecialiseerde formulier instellen als het terugvalformulier en configureren dat het moet worden weergegeven voor iedereen. Vervolgens maakt u aangepaste formulieren aan voor specifieke beveiligingsrollen en configureert deze zodat ze alleen worden weergegeven voor beveiligingsrollen die ze nodig hebben. Schakel deze formulier niet voor reserve in. Ten slotte kunt u in de lijst **Formulieren** het dialoogvenster **Formuliervolgorde** gebruiken om te specificeren welke formulieren u wilt weergeven door ze in te delen van het meest exclusief naar het minst exclusief. Uw terugvalformulier zal onderaan de lijst zijn. Door deze strategie zullen gebruikers het formulier zien dat is aangepast voor hun rol als het standaardformulier, maar ze kunnen nog steeds de formulierselectie gebruiken om het meest gebruikelijke formulier te selecteren indien ze het willen. Het formulier dat ze selecteren zal hun standaardformulier blijven totdat ze een ander formulier selecteren.  
  
<a name="BKMK_UseFormScripting"></a>   
## <a name="use-form-scripting"></a>Formulierscripts gebruiken  

 Ten slotte is het in de webtoepassing mogelijk, maar niet aanbevolen, voor een ontwikkelaar om scripts te gebruiken in de gebeurtenis van het formulier Onload om gebruik te maken van de [verzameling Xrm.Page.ui.formSelector.items](http://go.microsoft.com/fwlink/p/?LinkID=513300) om beschikbare formulieren te doorzoeken en de navigatiemethode te gebruiken om gebruikers naar een specifiek formulier te sturen. Door de [navigatiemethode](http://go.microsoft.com/fwlink/p/?LinkID=513301) zal het formulier opnieuw worden geladen (en de Onload-gebeurtenis zal opnieuw gebeuren). Uw logica in de gebeurtenisverwerker moet in alle gevallen een voorwaarde controleren voordat u de navigatiemethode gebruikt om een eindeloze lus of onnodige restrictie te vermijden om tussen formulieren te navigeren.  
  
 Deze benadering werkt niet voor Dynamics 365 for tablets omdat meerdere formulieren niet beschikbaar zijn voor selectie.  

### <a name="next-steps"></a>Volgende stappen  

[Beveiligingsrollen toewijzen aan formulieren](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form)
