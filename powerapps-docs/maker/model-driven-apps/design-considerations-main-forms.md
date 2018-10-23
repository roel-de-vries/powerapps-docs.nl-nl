---
title: Ontwerpoverwegingen voor hoofdformulieren van modelgestuurde apps met PowerApps | MicrosoftDocs
description: Informatie over het ontwerpen van hoofdformulieren
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
ms.openlocfilehash: 68915af214b86511f7fba4bbb05ee59f598340b0
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681679"
---
# <a name="design-considerations-for-model-driven-app-main-forms"></a>Ontwerpoverwegingen voor hoofdformulieren van modelgestuurde apps

Hoofdformulieren zijn de primaire gebruikersinterface waar gegevens worden bekeken en met de gegevens wordt gewerkt. Hoofdformulieren bieden het breedste scala aan opties en zijn beschikbaar voor modelgestuurde apps, met uitzondering van Dynamics 365 voor telefoons.  
  
 Een van de belangrijkste doelstellingen voor het ontwerpen van hoofdformulieren is dat u ze één keer ontwerpt en ze vervolgens overal implementeert. Hetzelfde hoofdformulier dat u ontwerpt voor een modelgestuurde app of de Dynamics 365 Customer Engagement-web-app, wordt ook gebruikt in Dynamics 365 voor Outlook en Dynamics 365 voor tablets. Het voordeel van deze benadering is dat u wijzigingen niet in meerdere formulieren hoeft te integreren. Er zijn echter enkele belangrijke factoren om te overwegen bij het ontwerp van formulieren.  
  
<a name="BKMK_CustomFormsForGroups"></a>   

## <a name="custom-forms-for-different-groups"></a>Aangepaste formulieren voor verschillende groepen  
 Omdat u meerdere hoofdformulieren kunt maken en verschillende beveiligingsrollen aan elk formulier kunt toewijzen, kunt u aan verschillende groepen in uw organisatie een formulier toewijzen dat wordt geoptimaliseerd voor de manier waarop deze groepen de toepassing gebruiken. U kunt zelfs voor elke groep verschillende opties opgeven, zodat ze uit verschillende formulieren kunnen kiezen. Meer informatie: [Toegangsbeheer voor formulieren](control-access-forms.md)  
  
 Managers en beslissers willen doorgaans formulieren die zijn geoptimaliseerd voor het leveren van snelle verwijzingen naar belangrijke gegevenspunten. Ze zullen eerder grafieken dan lijsten willen zien en ze willen waarschijnlijk niet veel gegevens hoeven in te voeren.  
  
 Gebruikers die rechtstreeks met klanten werken, hebben doorgaans formulieren nodig die zijn afgestemd op de taken die ze het vaakst uitvoeren. Ze werken het liefst met formulieren waarbij de gegevens efficiënt kunnen worden ingevoerd.  
  
 U moet nagaan wat de mensen in uw organisatie willen en wat ze nodig hebben. Dit is vaak een iteratief proces waarbij u invoer verzamelt, verschillende dingen probeert en formulieren maakt die personen kunnen gebruiken. U kunt bij uw werk gebruikmaken van verschillende hulpmiddelen en niet alles hoeft in het formulier te worden uitgevoerd. Gebruik samen met uw formulieren bedrijfsregels, werkstroomprocessen, dialoogvensters en zakelijke processtromen om een oplossing te bieden die geschikt is voor uw organisatie.  
  
 Ga na hoeveel tijd u aan het beheer van formulieren wilt besteden. U kunt vrij eenvoudig formulieren maken en bewerken, maar als u meer formulieren maakt, moeten er ook meer formulieren worden beheerd.  
  
<a name="BKMK_PresentationDifferences"></a>   
## <a name="presentation-differences"></a>Presentatieverschillen  
 Hoewel u niet voor elke presentatie meerdere formulieren hoeft te beheren, moet u wel bepalen hoe verschillen in de presentatie in het hoofdformulier worden verwerkt. In [Presentaties van het hoofdformulier](main-form-presentations.md) worden de verschillende manieren beschreven waarop het hoofdformulier kan worden gepresenteerd. Belangrijke zaken waarmee u rekening moet houden, zijn:  
  
- Met Dynamics 365 voor tablets is het niet mogelijk het volgende toe te voegen aan formulieren: afbeeldingen, HTML of Silverlight-webresources.  
  
-   De indeling van Dynamics 365 voor tablets-formulieren wordt automatisch gegenereerd op basis van het hoofdformulier. Er is geen speciale formuliereditor voor Dynamics 365 voor tablets-formulieren. U moet controleren of de formulierpresentatie voor beide clients goed werkt.  
  
-   Niet-ondersteunde scripts die werken met DOM-elementen in de webtoepassing, werken niet in de Dynamics 365 voor tablets-formulieren omdat dezelfde DOM-elementen niet beschikbaar zijn.  
  
- Bij formulieren in het Dynamics 365 voor Outlook-leesvenster kunnen geen scripts worden gebruikt. De zichtbaarheid van formulierelementen is afhankelijk van de standaardinstellingen en kan niet met behulp van scripts tijdens de uitvoering worden gewijzigd.  
  
<a name="BKMK_FormPerformance"></a>   
## <a name="form-performance"></a>Formulierprestaties  
 Formulieren die langzaam worden geladen of niet snel reageren, beïnvloeden de productiviteit en de acceptatie van de app door de gebruiker. [Formulierprestaties optimaliseren](optimize-form-performance.md) biedt een aantal aanbevelingen die u bij het ontwerpen van formulieren in aanmerking kunt nemen, zodat uw aanpassingen geen nadelige invloed op de formulierprestaties hebben.  
  
### <a name="next-steps"></a>Volgende stappen 
 [Formulieren maken en ontwerpen](create-design-forms.md)    
 [Formulieren voor snelle invoer maken en bewerken](create-edit-quick-create-forms.md)   

 
