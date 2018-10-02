---
title: Aandachtspunten bij het ontwerpen van hoofdformulieren voor modelgestuurde apps met PowerApps | MicrosoftDocs
description: Hoofdformulieren ontwerpen
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
ms.assetid: a83872f4-9e36-413b-8561-41a1e5ffe5dd
caps.latest.revision: 17
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="design-considerations-for-model-driven-app-main-forms"></a>Aandachtspunten bij het ontwerpen van hoofdformulieren voor modelgestuurde apps

Hoofdformulieren zijn de de primaire gebruikersinterface waar personen hun gegevens bekijken en ermee communiceren. Hoofdformulieren bieden het breedste bereik aan opties en zijn beschikbaar voor modelgestuurde apps, met uitzondering van Dynamics 365 for phones.  
  
 Een van de belangrijkste ontwerpdoelstellingen voor hoofdformulieren is dat u deze eennmaal ontwerpt en ze overal distribueert. Hetzelfde hoofdformulier dat u ontwerpt voor een modelgestuurde app of de webtoepassing Dynamics 365 Customer Engagement wordt ook gebruikt in Dynamics 365 for Outlook en Dynamics 365 for tablets. Het voordeel van deze methode is dat u geen wijzigingen hoeft te integreren in meerdere formulieren. Er zijn echter verschillende belangrijke factoren om te overwegen bij het ontwerpen van deze formulieren.  
  
<a name="BKMK_CustomFormsForGroups"></a>   

## <a name="custom-forms-for-different-groups"></a>Aangepaste formulieren voor verschillende groepen  
 Omdat u meerdere hoofdformulieren kunt maken en verschillende beveiligingsrollen toe kunt wijzen aan elk formulier, kunt u verschillende groepen in uw organisatie een formulier presenteren dat is geoptimaliseerd voor de manier waarop zij de toepassing gebruiken. U kunt elke groep voorzien van verschillende opties, zodat ze uit verschillende formulieren kunnnen kiezen. Meer informatie: [Toegang tot formulieren beheren](control-access-forms.md)  
  
 U kunt verwachten dat managers en de beslissingenmakers formulieren willen die zijn geoptimaliseerd om een snelle verwijzing naar belangrijke gegevenspunten te bieden. Ze willen liever grafieken zien dan lijsten en doen misschien niet veel gegevensinvoering.  
  
 Personen die direct interactie hebben met klanten, kunnen formulieren nodig hebben die zijn aangepast aan de taken die zij het vaakst uitvoeren. Zij kunnen formulieren willen die de meest efficiënte gegevensinvoering toestaan.  
  
 U moet te weten komen wat de personen in uw organisatie willen en nodig hebben. Dit is vaak een herhalend proces waarbij u de invoer verzamelt, verschillende dingen uitprobeert en formuleren bouwt die personen kunnen gebruiken. Houd er rekening mee dat u een aantal verschillende hulpprogramma's beschikbaar hebt en dat niet alles in het formulier moet worden uitgevoerd. Gebruik bedrijfsregels, werkstroomprocessen, dialoogvensters en bedrijfsprocesstromen samen met uw formulieren om een oplossing te bieden die voor uw organisatie werkt.  
  
 U moet dit in evenwicht brengen met de hoeveelheid tijd die u wilt bestenden aan het beheren van formulieren. Het maken en bewerken van formulieren is vrij eenvoudig, maar des te meer formulieren u maakt, des te meer u er moet beheren.  
  
<a name="BKMK_PresentationDifferences"></a>   
## <a name="presentation-differences"></a>Presentatieverschillen  
 Hoewel u niet meerdere formulieren voor de presentatie hoeft te beheren, moet u overwegen hoe verschillen in de presentatie in rekenschap kunnen worden gebracht in het hoofdformulier. [Hoofdformulierpresentaties](main-form-presentations.md) beschrijft de verschillende manieren om het hoofdformulier te presenteren. De belangrijkste dingen om te overwegen, zijn:  
  
- Dynamics 365 for tablets biedt geen ondersteuning voor het toevoegen van afbeeldingen, HTML of Silverlight-webresources aan formulieren.  
  
-   De indeling van Dynamics 365 for tablets-formulieren wordt automatisch gemaakt op basis van het hoofdformulier. Er is geen speciale formuliereneditor voor Dynamics 365 for tablets-formulieren. U moet controleren of de formulierpresentatie goed werkt voor beide clients.  
  
-   Als u niet-ondersteunde scripts hebt die communiceren met DOM-elementen gevonden in de webtoepassing, werken die scripts niet in de Dynamics 365 for tablets-formulieren omdat diezelfde DOM-elementen niet beschikbaar zijn.  
  
- In formulieren in het leesvenster van Dynamics 365 for Outlook zijn scripts niet toegestaan. De zichtbaarheid van formulierelementen is afhankelijk van de standaardinstellingen en kunnen niet worden gewijzigd tijdens runtime met scripts.  
  
<a name="BKMK_FormPerformance"></a>   
## <a name="form-performance"></a>Formulierprestatie  
 Formulieren die langzaam laden of niet snel reageren, zijn van invloed op de productiviteit en de aanvaarding door gebruikers. [Formulierprestaties optimaliseren](optimize-form-performance.md) geeft een aantal aanbevelingen die u zou moeten overwegen bij het ontwerpen van formulieren zodat de aanpassingen geen negatieve invloed hebben op de formulierprestaties.  
  
### <a name="next-steps"></a>Volgende stappen 
 [Formulieren maken en ontwerpen](create-design-forms.md)    
 [Formulieren voor snelle invoer maken en bewerken](create-edit-quick-create-forms.md)   

 
