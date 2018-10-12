---
title: Met oplossingen werken in PowerApps | MicrosoftDocs
description: Ontdek hoe oplossingen worden gedistribueerd
ms.custom: ''
ms.date: 06/21/2018
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
ms.assetid: ece68f5f-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
ms.openlocfilehash: 47fb64e650da2f3e1a9e0cf523060cf7d9f5a03b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675407"
---
<a name="BKMK_Solutions"></a>   
# <a name="solutions-overview"></a>Overzicht van oplossingen  

 Oplossingen bestaan zodat een modelgestuurde app kan worden gekocht, gedeeld of anderszins getransporteerd van het ene bedrijf naar het andere. U kunt oplossingen ophalen van [AppSource](https://appsource.microsoft.com/) of van een onafhankelijke softwareleverancier (ISV). Een oplossing is een bestand dat u kunt importeren in een omgeving als een app of om een set van aanpassingen aan te brengen aan een bestande app.  
  
Meer informatie: Meer informatie: [technisch document: patronen en beginselen voor oplossingenbouwers](http://go.microsoft.com/fwlink/p/?LinkID=533946)  
  
> [!NOTE]
>  Als u een ISV bent die een app maakt die u wilt distribueren, moet u oplossingen gebruiken. Zie [Pakket- en distributie-extensies die oplossingen gebruiken](https://msdn.microsoft.com/library/gg334530.aspx) voor meer informatie over oplossingen.  
  
 Als u alleen interesse hebt in het maken van PowerApps-apps voor zakelijk gebruik of het aanpassen van Dynamics 365, moet u dit weten over oplossingen:  
  
-   Het maken van oplossingen is optioneel. U kunt apps rechtstreeks in uw PowerApps-omgeving bouwen of aanpassen, zonder een oplossing te hoeven maken.  
  
-   Als u de PowerApps-omgeving rechtstreeks aanpast, werkt u met een speciale oplossing genaamd de **Algemene Data Services-standaardoplossing**. Deze oplossing bevat alle componenten in uw systeem.  
  
-   U kunt uw standaardoplossing exporteren om een back-up te maken van de aanpassingen die u in uw bedrijf hebt gedefinieerd. Dat is handig te hebben voor het geval dat.  
  
<a name="BKMK_SolutionComponents"></a>   
### <a name="solution-components"></a>Oplossingsonderdelen  
 Een oplossingsonderdeel vertegenwoordigt iets dat u potentieel kunt aanpassen. Alles dat kan worden opgenomen in een oplossing is een oplossingsonderdeel. Hier volgt een lijst met oplossingsonderdelen die u in een oplossing kunt zien:  
  
-   Toepassingslint  

-   App 
  
-   Artikelsjabloon  
  
-   Bedrijfsregel  
  
-   Grafiek  
  
-   Verbindingsrol  
  
-   Contractsjabloon  
 
-   Aangepast besturingselement
  
-   Dashboard  
  
-   E-mailsjabloon  
  
-   Entiteit  
  
-   Entiteitsrelatie  
  
-   Veld  
  
-   Veldbeveiligingsprofiel  
  
-   Formulier  
  
-   Samenvoegsjabloon  
  
-   Bericht  
  
-   Optieset  
  
-   Assembly van invoegtoepassing  
  
-   Proces  
  
-   Verwerkingsstap Sdk-bericht  
  
-   Beveiligingsrol  
  
-   Service-eindpunt  
  
-   Sitemap  

-   Aanbieder van virtuele-entiteitsgegevens

-   Virtuele-entiteitsgegevensbron
  
-   Webresource  
  
 De meeste oplossingsonderdelen zijn genest binnen andere oplossingsonderdelen. Een entiteit bevat bijvoorbeeld formulieren, weergaven, diagrammen, velden, entiteitsrelaties, berichten en bedrijfsregels. Elk van deze oplossingsonderdelen vereisen een bestaande entiteit. Een veld kan niet bestaan zonder entiteit. We zeggen dat een veld afhankelijk is van de entiteit. Er zijn feitelijk twee keer meer typen oplossingsonderdelen dan weergegeven in voorgaande lijst, maar de meeste zijn niet zichtbaar in de toepassing.  
  
 Het doel van oplossingsonderdelen is het bijhouden van beperkingen van wat kan worden aangepast met Beheerde eigenschappen en alle oplossingsafhankelijkheden, zodat die kunnen worden geëxporteerd, geïmporteerd en (in beheerde oplossingen) verwijderd zonder iets achter te laten.  
  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
### <a name="managed-and-unmanaged-solutions"></a>Beheerde en onbeheerde oplossingen  
 Een **beheerde** oplossing kan worden verwijderd nadat die is geïmporteerd. Alle onderdelen van die oplossing worden verwijderd door de oplossing te verwijderen.  
  
 Wanneer u een **onbeheerde** oplossing importeert, voegt u alle onderdelen van die oplossing toe aan uw standaardoplossing. U kunt de onderdelen niet verwijderen door de oplossing te verwijderen.  
  
 Wanneer u een **onbeheerde** oplossing importeert die oplossingsonderdelen bevat die u al hebt aangepast, worden uw aanpassingen overschreven door de aanpassingen in de onbeheerde oplossing. U kunt dit niet ongedaan maken.  
  
> [!IMPORTANT]
>  Installeer alleen een onbeheerde oplossing als u alle onderdelen aan uw standaardoplossing wilt toevoegen en bestaande aanpassingen wilt overschrijven.  
  
 Zelfs als u niet van plan bent uw oplossing te distribueren, is het raadzaam een onbeheerde oplossing te maken en gebruiken om een afzonderlijke weergave te hebben die alleen die onderdelen van de toepassing bevat die u hebt aangepast. Wanneer u iets aanpast, voegt u het gewoon toe aan de onbeheerde oplossing die u hebt gemaakt.  
  
 U kunt uw Standaardoplossing alleen exporteren als onbeheerde oplossing.  
  
 Om een **beheerde** oplossing te maken, kiest u de optie beheerde oplossing wanneer u de oplossing exporteert. Als u een beheerde oplossing maakt, kunt u die niet opnieuw importeren in hetzelfde bedrijf dat u hebt gebruikt om die te maken. U kunt die alleen importeren in een ander bedrijf.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### <a name="how-solutions-are-applied"></a>Hoe oplossingen worden toegepast  
 Alle oplossingen worden geëvalueerd als lagen om vast te stellen wat uw app daadwerkelijk doet. Het volgende diagram laat zien hoe beheerde en onbeheerde oplossingen worden geëvalueerd en hoe veranderingen erin zullen worden weergegeven in uw bedrijf.  
  
 ![Laaggebruik van oplossingen](media/solution-layering.png "Laaggebruik van oplossingen")  
  
 Van onder naar boven:  
  
 **Systeemoplossing**  
 De systeemoplossing is als een beheerde oplossing die elk bedrijf heeft. De systeemoplossing is de definitie van alle kant-en-klare onderdelen in het systeem.  
  
 **Beheerde oplossingen**  
 Beheerde oplossingen kunnen de systeemoplossingsonderdelen bewerken en nieuwe onderdelen toevoegen. Als meerdere beheerde oplossingen zijn geïnstalleerd, wordt de eerste geïnstalleerd onder de later geïnstalleerde beheerde oplossing. Dit betekent dat de tweede oplossing die wordt geïnstalleerd de eerdere oplossing kan aanpassen. Wanneer twee beheerde oplossingen conflicterende definities hebben, is de algemene regel ‘de laatste wint’. Als u een beheerde oplossing verwijdert, wordt de beheerde oplossing daaronder van kracht. Als u alle beheerde oplossingen verwijdert, wordt het standaardgedrag dat is bepaald in de systeemoplossing van kracht.  
  
 **Onbeheerde aanpassingen**  
 Onbeheerde aanpassingen zijn alle wijzigingen die u hebt aangebracht aan uw bedrijf via een onbeheerde oplossing. De systeemoplossing definieert wat u wel en niet kunt aanpassen met beheerde eigenschappen. Uitgevers van beheerde oplossingen hebben dezelfde mogelijkheid om te beperken welke oplossingsonderdelen die zij in hun oplossing hebben toegevoegd u kunt aanpassen. U kunt alle oplossingsonderdelen aanpassen die geen beheerde eigenschappen hebben die verhinderen dat u ze aanpast.  
  
 **Toepassingsgedrag**  
 Dit is wat u daadwerkelijk ziet in uw bedrijf. De standaardsysteemoplossing plus eventuele beheerde oplossingen, plus eventuele onbeheerde aanpassingen die u hebt aangebracht.  
  
<a name="BKMK_ManagedProperties"></a>   
### <a name="managed-properties"></a>Beheerde eigenschappen  
 Bepaalde onderdelen kunnen niet worden aangepast. Deze onderdelen in de systeemoplossing hebben metagegevens die verhinderen dat u ze aanpast. Dit worden **beheerde eigenschappen** genoemd. De uitgever van een beheerde oplossing kan ook de beheerde eigenschappen instellen om te voorkomen dat u hun oplossing aanpast op een manier dat zij niet willen.  
  
<a name="BKMK_Dependencies"></a>   
### <a name="solution-dependencies"></a>Oplossingsafhankelijkheden  
 Omdat de manier waarop beheerde oplossingen gelaagd zijn, kunnen bepaalde beheerde oplossingen afhankelijk zijn van oplossingsonderdelen in andere beheerde oplossingen. Bepaalde oplossingsuitgevers profiteren hiervan om oplossingen te bouwen die modulair zijn. Mogelijk moet u eerst een beheerde ‘basis’oplossing installeren voordat u een tweede beheerde oplossing kunt installeren die de onderdelen in de beheerde basisoplossing verder aanpassen. De tweede beheerde oplossing is afhankelijk van oplossingsonderdelen die onderdeel uitmaken maken van de eerste oplossing.  
  
 Het systeem volgt deze afhankelijkheden tussen oplossingen. Als u probeert een oplossing te installeren die een basisoplossing vereist die niet is geïnstalleerd, kunt u die oplossing niet installeren. U krijgt een melding te zien dat er voor de oplossing eerst een andere oplossing moet zijn geïnstalleerd. Op dezelfde manier kunt u, vanwege de afhankelijkheden, geen basisoplossing verwijderen als er een oplossing is geïnstalleerd die daarvan afhankelijk is. U moet de afhankelijke oplossing eerst verwijderen voor u de basisoplossing kunt verwijderen.  
  
  
## <a name="next-steps"></a>Volgende stappen  
[Oplossingen importeren, bijwerken en exporteren](import-update-export-solutions.md) <br/>
[Naar een specifieke oplossing navigeren](navigate-specific-solution.md)
 
