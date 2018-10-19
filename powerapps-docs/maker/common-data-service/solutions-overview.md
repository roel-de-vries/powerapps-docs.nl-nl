---
title: Werken met oplossingen in PowerApps | MicrosoftDocs
description: Lees hoe oplossingen worden gedistribueerd
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

<a name="BKMK_Solutions"></a>   
# <a name="solutions-overview"></a>Oplossingsoverzicht  

 Er bestaan oplossingen die het mogelijk maken een modelgestuurde app aan te schaffen, te delen of anderszins over te brengen van de ene organisatie naar de andere. U kunt oplossingen ophalen uit [AppSource](https://appsource.microsoft.com/) of van een softwareleverancier (ISV). Een oplossing is een bestand dat u kunt importeren in een omgeving als een app of die u kunt toepassen om een reeks van aanpassingen toe te passen op een bestaand app.  
  
Meer informatie: [Whitepaper: Patronen en principes voor oplossingenbouwers](http://go.microsoft.com/fwlink/p/?LinkID=533946)  
  
> [!NOTE]
>  Als u een ISV bent en een app maakt die u wilt distribueren, moet u oplossingen gebruiken. Zie voor meer informatie over het gebruiken van oplossingen: [Uitbreidingen inpakken en verdelen met oplossingen](https://msdn.microsoft.com/library/gg334530.aspx).  
  
 Als u alleen maar PowerApps-apps wilt maken voor gebruik binnen de organisatie of Dynamics 365 wilt aanpassen, moet u het volgende weten over oplossingen:  
  
-   Oplossingen maken is optioneel. U kunt apps maken of aanpassen in uw PowerApps-omgeving, zonder ooit een oplossing te hoeven maken.  
  
-   Als u de PowerApps-omgeving direct aanpast, werkt u met een speciale oplossing die de **Common Data Services-standaardoplossing** wordt genoemd. Deze oplossing bevat alle onderdelen in uw systeem.  
  
-   U kunt uw standaardoplossing exporteren om een back-up te maken van de aanpassingen die u in uw organisatie hebt gedefinieerd. Dit is goed om te hebben in het ergste geval.  
  
<a name="BKMK_SolutionComponents"></a>   
### <a name="solution-components"></a>Oplossingsonderdelen  
 Een oplossingsonderdeel is iets dat u kunt mogelijk aanpassen. Alles wat in een oplossing kan worden opgenomen, is een oplossingsonderdeel. Hier volgt een lijst met oplossingsonderdelen die u in een oplossing kunt weergeven:  
  
-   Toepassingslint  

-   App 
  
-   Artikelsjabloon  
  
-   Bedrijfsregel  
  
-   Diagram  
  
-   Verbindingsrol  
  
-   Contractsjabloon  
 
-   Aangepast besturingselement
  
-   Dashboard  
  
-   E-mailsjabloon  
  
-   Entity  
  
-   Entiteitsrelatie  
  
-   Veld  
  
-   Veldbeveiligingsprofiel  
  
-   formulier  
  
-   Sjabloon voor afdruk samenvoegen  
  
-   Bericht  
  
-   Optieset  
  
-   Invoegtoepassingassembly  
  
-   Proces  
  
-   SDK-berichtverwerkingsstap  
  
-   Beveiligingsrol  
  
-   Service-eindpunt  
  
-   Siteoverzicht  

-   Virtuele aanbieder van entiteitsgegevens

-   Virtuele bron voor entiteitsgegevens
  
-   Webresource  
  
 De meeste oplossingsonderdelen worden genesteld in andere oplossingsonderdelen. Een entiteit bevat bijvoorbeeld formulieren, weergaven, grafieken, velden, entiteitsrelaties, berichten en bedrijfsregels. Elk van die oplossingsonderdelen vereist een entiteit om te bestaan. Een veld kan niet buiten een entiteit bestaan. We zeggen dat het veld afhankelijk is van de entiteit. Er zijn twee keer zoveel typen oplossingsonderdelen dan wordt weergegeven in de voorafgaande lijst hierboven, maar de meeste zijn niet zichtbaar in de toepassing.  
  
 Het doel van oplossingsonderdelen is het bijhouden van eventuele beperkingen of wat kan worden aangepast met Beheerde eigenschappen en alle afhankelijkheden van oplossingen, zodat het kan worden geëxporteerd, geïmpoteerd en (in beheerde oplossingen) verwijderd zonder iets achter te laten.  
  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
### <a name="managed-and-unmanaged-solutions"></a>Beheerde en onbeheerde oplossingen  
 Een **beheerde** oplossing kan worden gedeïnstalleerd nadat deze is geïmporteerd. Alle onderdelen van die oplossing worden verwijderd als de oplossing wordt gedeïnstalleerd.  
  
 Wanneer u een **onbeheerde** oplossing importeert, voegt u alle onderdelen van die oplossing toe aan uw standaardoplossing. U kunt de onderdelen niet verwijderen door de oplossing te deïnstalleren.  
  
 Als u een **onbeheerde** oplossing importeert die oplossingsonderdelen bevat die u al hebt aangepast, worden uw aanpassingen overschreven door de aanpassingen in de onbeheerde oplossing. U kunt dit niet ongedaan maken.  
  
> [!IMPORTANT]
>  Installeer een onbeheerde oplossing alleen als u alle onderdelen aan uw standaardoplossing wilt toevoegen en de bestaande aanpassingen overschrijven.  
  
 Zelfs als u niet van plan bent uw oplossing te distribueren, wilt u misschien een onbeheerde oplossing maken en gebruiken om een andere weergave te krijgen die alleen die onderdelen van de toepassing opneemt die u hebt aangepast. Als u iets aanpast, voegt u het gewoon toe aan de onbeheerde oplossing die u hebt gemaakt.  
  
 U kunt uw standaardoplossing alleen als beheerde oplossing exporteren.  
  
 Om een **beheerde** oplossing te maken, kiest u de optie beheerde oplossing als u de oplossing exporteert. Wanneer u een beheerde oplossing maakt, kunt u die niet weer importeren in dezelfde organisatie als waar u die hebt gemaakt. U kunt de oplossing alleen in een andere organisatie importeren.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### <a name="how-solutions-are-applied"></a>De manier waarop oplossingen worden toegepast  
 Alle oplossingen worden geëvalueerd als lagen om te bepalen wat uw app gaat doen. Het onderstaande schema geeft weer hoe beheerde en onbeheerde oplossingen worden geëvalueerd en de manier waarop veranderingen in de oplossingen in uw organisatie worden weergegeven.  
  
 ![Opeenstapeling van oplossingen](media/solution-layering.png "Opeenstapeling van oplossingen")  
  
 Onderaan beginnen en naar boven werken:  
  
 **Systeemoplossing**  
 De systeemoplossing is als een beheerde oplossing die elke organisatie heeft. De systeemoplossing is de definitie van alle kant-en-klare oplossingen in het systeem.  
  
 **Beheerde oplossingen**  
 Beheerde oplossingen kunnen de systeemoplossingsonderdelen wijzigen en nieuwe onderdelen toevoegen. Als er meerdere beheerde oplossingen zijn geïnstalleerd, is de eerste geïnstalleerde oplossing onder de later geïnstalleerde beheerde oplossing. Dit betekent dat de tweede geïnstalleerde oplossing de oplossing die daarvoor is geïnstalleerd kan aanpassen. Wanneer twee beheerde oplossingen conflicterende definities hebben, geldt over het algemeen “de laatste wint“. Als u een beheerde oplossing verwijdert, wordt de beheerde oplossing eronder van kracht. Als u alle beheerde oplossing deïnstalleert, wordt het standaardgedrag dat definieerd is in de systeemoplossing toegepast.  
  
 **Onbeheerde aanpassingen**  
 Onbeheerde aanpassingen zijn de wijzigingen die u in uw organisatie met een onbeheerde oplossing hebt gemaakt. De systeemoplossing bepaalt wat u wel of niet kunt aanpassen door beheerde eigenschappen te gebruiken. Uitgevers van beheerde oplossingen hebben dezelfde mogelijkheid om uw mogelijkheid te beperken om oplossingsonderdelen aan te passen die zij in hun oplossing toevoegen. U kunt oplossingsonderdelen aanpassen die geen beheerde eigenschappen hebben die voorkomen dat uw ze kunt aanpassen.  
  
 **Toepassingsgedrag**  
 Dit is wat u in uw organisatie ziet. De standaardsysteemoplossing plus eventuele beheerde oplossingen, plus eventuele onbeheerde aanpassingen die u hebt toegepast.  
  
<a name="BKMK_ManagedProperties"></a>   
### <a name="managed-properties"></a>Beheerde eigenschappen  
 Sommige onderdelen kunnen niet worden aangepast. Deze onderdelen in de systeemoplossing hebben metagegevens die voorkomen dat u ze kunt aanpassen. Deze worden **beheerde eigenschappen** genoemd. De uitgever van een beheerde oplossing kan de beheerde eigenschappen ook zo instellen dat u hun oplossing niet kunt aanpassen op manieren die zij niet willen.  
  
<a name="BKMK_Dependencies"></a>   
### <a name="solution-dependencies"></a>Afhankelijkheden van oplossingen  
 Vanwege de manier waarop beheerde oplossingen zijn opgebouwd, kunnen sommige beheerde oplossingen afhankelijk zijn van oplossingsonderdelen in andere beheerde oplossingen. Sommige oplossingsuitgevers maken hier gebruik van om oplossingen te bouwen die modulair zijn. U moet misschien eerst een beheerde "basisoplossing" installeren. Daarna kunt u een tweede beheerde oplossing installeren die de onderdelen in de beheerde basisoplossing verder aanpast. De tweede beheerde oplossing is afhankelijk van oplossingsonderdelen die deel uitmaken van de eerste oplossing.  
  
 Het systeem houdt deze afhankelijkheden tussen oplossingen bij. Als u een oplossing probeert te installeren die een basisoplossing vereist die niet is geïnstalleerd, kunt u de oplossing niet installeren. U krijgt een bericht waarin wordt aangegeven dat er een andere oplossing nodig is voordat de oplossing kan worden geïnstalleerd. Vanwege de afhankelijkheden kunt u de basisoplossing ook niet deïnstalleren terwijl er een oplossing is geïnstalleerd die ervan afhankelijk is. U moet de afhankelijke oplossing deïnstalleren voordat u de basisoplossing kunt verwijderen.  
  
  
## <a name="next-steps"></a>Volgende stappen  
[Oplossingen importeren, bijwerken en exporteren](import-update-export-solutions.md) <br/>
[Navigeer naar een specifieke oplossing](navigate-specific-solution.md)
 
