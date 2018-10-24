---
title: Procedures voor het bouwen van Common Data Service for Apps-apps | Microsoft Docs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e9810433-224b-4bde-851a-e581cf5fb8a4
caps.latest.revision: 21
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1eda4b591a3296001ffa62b16e185b421a197e75
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865036"
---
# <a name="common-data-service-for-apps-supported-and-unsupported-app-building-practices"></a>Door Common Data Service for Apps ondersteunde en niet-ondersteunde procedures voor het bouwen van apps

<!--
The way your organization works is unique. Some organizations have well-defined business processes that they apply using PowerApps apps. Others aren’t happy with their current business processes and use PowerApps to apply new data and processes to their business. Whatever situation you find yourself in, you’ll find a lot of customization capabilities in PowerApps so that it can work for your organization.  
  
 Of course you’re eager to get started, but please take a few minutes to read the content in this section. This will introduce you to important terms, give you some background about why things are done a certain way, and help you avoid potential problems in the future.  

## What is metadata and why should you care?  
 In the past, you may have customized business applications by editing the source code. This created complications because each organization had unique changes and it was very difficult, or extremely expensive, to upgrade. Then application developers started exposing application programming interfaces (APIs) so that other developers could interact with the application and add their own logic without touching the source code. This was moderately better because it means developers can extend the application without changing it. But it still requires a developer to write code.  -->
  
 Moderne zakelijke toepassingen gebruiken een architectuur op basis van metagegevens, zodat gebruikers apps kunnen maken zonder code te schrijven. Metagegevens betekent 'gegevens over gegevens'. Deze gegevens bepalen de structuur van de gegevens die zijn opgeslagen in Common Data Service for Apps. Met deze metagegevens wordt een toepassing op de hoogte gebracht van eventuele wijzigingen in de gegevensstructuur en kan de toepassing worden aangepast als de gegevensstructuur wordt gewijzigd. Omdat de metagegevens bekend zijn, kunnen aanvullende mogelijkheden worden opgenomen die aan de metagegevens zijn gekoppeld.  

Het wijzigen van de Common Data Service for Apps-onderdelen, zoals entiteiten, weergaven, velden, grafieken en dashboards, om apps zo te bouwen dat ze op de gewenste manier werken, wordt *aanpassing* genoemd.  
 
Wanneer u uw apps met behulp van de hulpprogramma's in PowerApps bouwt en aanpast, worden metagegevens of gegevens toegevoegd of aangepast die worden gebruikt door functies die afhankelijk zijn van de metagegevens. Omdat we weten welke soorten gegevens worden gebruikt om apps te maken, kunnen we met deze gegevens rekening houden en nieuwe functies toevoegen aan uw Common Data Service for Apps-omgeving zonder dat dit tot fouten voor uw apps leidt. <!-- This way you should always be able to apply an update rollup or upgrade to the latest version and enjoy the best new features.  -->

<!--  
> **Customize or Configure?**   
> Most people say they want to customize the application, so we use the word “customize” to describe changing the system to make it work the way you want. Some people prefer to use the word “configure” because it suggests that no code was required to make changes. Call it whatever you like, we just want to make it clear that you don’t need to be a developer to customize or create PowerApps apps.  -->
  
U hoeft geen ontwikkelaar te zijn om PowerApps-apps te bouwen en aan te passen. Wel biedt PowerApps een set met webservices en API's waarmee ontwikkelaars code kunnen schrijven. Wanneer code wordt geschreven met ondersteunde methoden, kunt u verwachten dat deze blijft werken als uw Common Data Service for Apps-omgeving wordt bijgewerkt.  
  
<a name="BKMK_SupportedCust"></a>   
## <a name="what-kinds-of-customizations-are-supported"></a>Welke soorten aanpassingen worden ondersteund?  
 We verwachten dat u apps grotendeels kunt bouwen en aanpassen met behulp van de beschikbare PowerApps-hulpprogramma's. Als de aanpassingsprogramma's niet voldoen aan uw behoeften, kunt u een oplossing van derden installeren of een ontwikkelaar vragen code voor uw app te schrijven. Als u wilt investeren in een oplossing waarvoor code vereist is, moet u controleren of de code wordt geschreven met alleen ondersteunde API's. Dit helpt u uw investering in zowel de apps als in eventuele aangeschafte oplossingen te beschermen.  
  
 Ontwikkelaars die PowerApps-apps uitbreiden, hebben een verantwoordelijkheid om zich te houden aan regels en aanbevolen procedures die worden beschreven in de SDK: [Aanbevolen procedures voor het ontwikkelen met Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/developer/best-practices-sdk). In de SDK wordt vermeld welke API's voor ontwikkelaars beschikbaar zijn en hoe de API's optimaal kunnen worden gebruikt. Microsoft ondersteunt alleen de API's en procedures die worden beschreven in de SDK. Mogelijk vindt u iets op internet waarmee wordt beschreven hoe u een probleem kunt oplossen, maar als hierbij geen gebruik wordt gemaakt van API's die worden beschreven in de SDK, wordt er geen ondersteuning door Microsoft geboden. Controleer voordat een ontwikkelaar een wijziging toepast of er ondersteunde methoden worden gebruikt.  
  
 Als ontwikkelaars de API's en aanbevolen procedures gebruiken die worden beschreven in de SDK, kunnen we testen of een van de wijzigingen die we aan Common Data Service for Apps hebben aangebracht, mogelijk tot fouten voor bestaande aanpassingen leidt. Ons doel is dat code-aanpassingen die zijn geschreven met behulp van ondersteunde methoden, blijven werken wanneer er nieuwe versies of updates voor Common Data Service for Apps worden uitgebracht. Dit is handig omdat u zo naar nieuwe versies met verbeterde functies kunt bijwerken zonder dat ontwikkelaars hun code steeds hoeven te wijzigen.  
  
 Als wij vaststellen dat een wijziging in een nieuwe versie van Common Data Service for Apps tot fouten bij een ondersteunde aanpassing leidt, zullen we documenteren wat wordt beïnvloed en hoe de code kan worden gewijzigd om dit op te lossen.  
  
<a name="BKMK_Unsupported"></a>   
## <a name="what-kinds-of-customizations-arent-supported"></a>Welke soorten aanpassingen worden niet ondersteund?  
 Wanneer bepaalde API's en programmeerprocedures niet worden ondersteund door Microsoft, betekent dat niet dat ze niet werken. <!--  “Unsupported by Microsoft” means exactly what it says: you can’t get support about these APIs or programming practices from Microsoft. We don’t test them and we don’t know if something we change will break them. We can’t predict what will happen if someone changes code in our application.  --> Ontwikkelaars die gebruikmaken van niet-ondersteunde API's en programmeerprocedures nemen de verantwoordelijkheid voor de ondersteuning van hun code. Ze moeten hun code testen om te controleren of deze werkt.  
  
 Als u niet-ondersteunde aanpassingen in uw Common Data Service for Apps-omgeving wilt gebruiken, moet u ervoor zorgen dat wordt gedocumenteerd wat er is gedaan en moet u een strategie hebben om deze aanpassingen te verwijderen voordat u contact opneemt met de technische ondersteuning van Microsoft. Als u hulp nodig hebt met niet-ondersteunde aanpassingen, neemt u contact op met de ontwikkelaar of organisatie die de aanpassingen heeft voorbereid.  
  
<a name="BKMK_CommonUnsupportedCustomizations"></a>   
### <a name="common-unsupported-customization-practices"></a>Algemene niet-ondersteunde aanpassingsprocedures  
 Hieronder volgt een lijst met algemene aanpassingsprocedures die niet worden ondersteund. Dit is geen volledige lijst. Meer informatie: [Ondersteunde extensies voor Dynamics 365: niet-ondersteunde aanpassingen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/supported-extensions#Unsupported). 
 
**Interactie met de DOM-elementen (Document Object Model) van een webtoepassing met behulp van JavaScript**  
 Alle JavaScript-bibliotheken die in de toepassing worden gebruikt, mogen alleen werken met de gedocumenteerde API's. Als JavaScript-ontwikkelaars met toepassingen werken, wordt er vaak toegang verschaft tot DOM-elementen met behulp van specifieke namen. Omdat PowerApps-apps webtoepassingen zijn, werken deze technieken wel, maar leidt een update waarschijnlijk tot fouten omdat de namen van de elementen waarnaar wordt verwezen op elk moment kunnen worden gewijzigd. We behouden ons het recht voor wijzigingen aan te brengen die in de toepassing nodig zijn. Dit betekent vaak dat wordt gewijzigd hoe de pagina is opgebouwd. Het toevoegen van eventuele wijzigingen die afhankelijk zijn van de huidige structuur van de pagina betekent dat u moet investeren in testen en mogelijk steeds wanneer u een update op uw toepassing toepast, de aangepaste code in deze scripts moet wijzigen.  
  
 jQuery is een zeer algemene bibliotheek die wordt gebruikt door JavaScript-ontwikkelaars. Het grootste voordeel van het gebruik van jQuery is dat ontwikkelaars hiermee gemakkelijk toegang tot DOM-elementen kunnen krijgen en DOM-elementen kunnen maken. Dit is nou precies wat niet wordt ondersteund in de Common Data Service for Apps-toepassingspagina's. jQuery wordt aanbevolen wanneer ontwikkelaars aangepaste gebruikersinterfaces met HTML-webresources maken, maar binnen de PowerApps-toepassingspagina's is het gebruik van jQuery niet vereist voor de ondersteunde API's.  
  
 **Niet-gedocumenteerde interne objecten of methoden gebruiken met JavaScript**  
Common Data Service for Apps gebruikt veel JavaScript-objecten in pagina's. Een JavaScript-ontwikkelaar kan deze objecten detecteren door een pagina te debuggen en vervolgens toegang tot deze objecten verkrijgen en de objecten opnieuw gebruiken. We behouden ons het recht voor de benodigde wijzigingen aan deze objecten aan te brengen, inclusief het verwijderen van de objecten of het wijzigen van de namen van de methoden. Als een script naar deze objecten verwijst, leidt het tot fouten voor het script als de objecten niet worden gevonden.  <a name="BKMK_Metadata"></a>   
 
<a name="BKMK_CombineCustomizations"></a>   
## <a name="combine-customization-capabilities"></a>Aanpassingsmogelijkheden combineren  
 In de onderwerpen in deze secties worden de afzonderlijke aanpassingsmogelijkheden uitgebreid beschreven. Maar vergeet niet dat de oplossingen voor uw bedrijfsbehoeften vaak een van de mogelijkheden samen met een of meer andere mogelijkheden gebruiken.  
  
<a name="BKMK_ChooseTheRightCustomization"></a>   
### <a name="choose-the-right-customization-capability-for-the-job"></a>De juiste aanpassingsmogelijkheid voor de taak kiezen  
 Met alle verschillende aanpassingsmogelijkheden die beschikbaar zijn in PowerApps is het eenvoudig met een hiervan vertrouwd te raken en proberen deze te gebruiken om elk probleem te verhelpen. Als u de bedrijfsproblemen die u wilt oplossen evalueert, moet u voor ogen houden welk eindresultaat u wilt bereiken en vervolgens terugwerken naar hoe u dit doel kunt behalen.  
 
<a name="BKMK_changesinperformance"></a>   
## <a name="changes-that-affect-common-data-service-for-apps-environment-performance"></a>Wijzigingen die van invloed zijn op Common Data Service voor Apps-omgevingsprestaties  
 Het importeren van oplossingen en toepassen van aanpassingen waarmee metagegevens worden gewijzigd, kan van invloed zijn op Common Data Service voor Apps-omgevingsprestaties. Acties die de normale werking van het systeem kunnen verstoren zijn onder andere:  
  
-   Entiteiten, alternatieve sleutels, kenmerken of relaties toevoegen, verwijderen of wijzigen.   
-   Oplossingen importeren
  
-   Aanpassingen publiceren 
  
Als u deze wijzigingen op een productiesysteem toepast, wordt aanbevolen deze bewerkingen te plannen op een tijdstip waarop gebruikers het minst worden gehinderd.   
  
  
## <a name="next-steps"></a>Volgende stappen  
[Wat zijn modelgestuurde apps in PowerApps?](../../maker/model-driven-apps/model-driven-app-overview.md)

