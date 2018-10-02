---
title: Vereiste bevoegdheden voor aanpassing van modelgestuurde apps | MicrosoftDocs
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
  - PowerApps
ms.assetid: 43cf7f3a-7e26-4990-8b5a-c817ac6d51bb
caps.latest.revision: 13
ms.author: matp
manager: kvivek
author: Mattp123
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="privileges-required-for-model-driven-app-customization"></a>Vereiste bevoegdheden voor aanpassing van modelgestuurde apps

Appgebruikers kunnen het systeem aanpassen en zelfs bepaalde aanpassingen met anderen delen, maar alleen gebruikers met de juiste bevoegdheden kunnen wijzigingen toepassen voor iedereen.  
  
> [!NOTE]
>  In dit gedeelte wordt ervan uitgegaan dat u weet hoe u met beveiligingsrollen werkt. Voor meer informatie over het werken met beveiligingsrollen raadpleegt u [Gebruikers maken en beveiligingsrollen toewijzen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles).  
  
<a name="BKMK_SysAdminAndSysCustomizer"></a>   
## <a name="system-administrator-and-system-customizer-security-roles"></a>Beveiligingsrollen van systeembeheerder en systeemaanpasser  
 Voor iedereen die aanpassingen doorvoert, is de beveiligingsrol Systeembeheerder of Systeemaanpasser gekoppeld aan de account. Deze beveiligingsrollen geven u de machtigingen die u nodig hebt om de app aan te passen.  
  
|Systeembeheerder|Systeemaanpasser|  
|--------------------------|-----------------------|  
|Heeft volledige bevoegdheid om het systeem aan te passen|Heeft volledige bevoegdheid om het systeem aan te passen|  
|Kan alle gegevens in het systeem weergeven|Kan alleen records voor systeementiteiten weergeven die zij maken|  
  
 Het verschil tussen de beveiligingsrollen systeembeheerder en systeemaanpasser is dat een systeembeheerder leesbevoegdheden op de meeste records in het systeem heeft en alles kan zien. Wijs de rol systeemaanpasser aan iemand toe die aanpassingstaken moet uitvoeren, maar geen gegevens in de systeementiteiten hoeft te bekijken. Het testen is echter een belangrijk aspect van het aanpassen van het systeem. Als systeemaanpassers geen gegevens kunnen zien, moeten ze records maken om hun aanpassingen testen. Systeemaanpassers hebben gewoonlijk volledige toegang tot aangepaste entiteiten. Als u dezelfde beperkingen wilt hebben die voor systeementiteiten bestaan, dan moet u de beveiligingsrol Systeemaanpasser aanpassen zodat het toegangsniveau **Gebruiker** is in plaats van **Organisatie** voor aangepaste entiteiten.  
  
<a name="BKMK_DelegatingCustomizationTasks"></a>   
## <a name="delegate-customization-tasks"></a>Aanpassingstaken delegeren  
 U kunt een aantal taken aan betrouwbare mensen delegeren, zodat zij wijzigingen kunnen toepassen die ze nodig hebben. Houd er rekening mee dat iedereen meerdere beveiligingsrollen gekoppeld kan hebben aan hun gebruikersaccount en dat bevoegdheden en toegangsrechten toegekend door de beveiligingsrollen worden gebaseerd op de *minst beperkende* niveau van bevoegdheden.  
  
 Dit betekent dat u de beveiligingsrol van systeemaanpasser aan iemand kunt geven die al een andere beveiligingsrol heeft, zoals een verkoopdirecteur. Hierdoor kunnen ze het systeem aanpassen naast andere bevoegdheden die ze al hebben. U hoeft de beveiligingsrol die ze al hebben niet te bewerken, en u kunt de beveiligingsrol systeemaanpasser van de gebruikersaccount van de persoon verwijderen wanneer u wilt.  
  
<a name="BKMK_UsingTwoUserAccounts"></a>   
## <a name="test-customizations-without-customization-privileges"></a>Testaanpassingen zonder aanpassingsbevoegdheden  
 U zou elke aanpassing die u maakt met een gebruikersaccount dat geen aanpassingsbevoegdheden heeft, altijd moeten testen. Zo kunt u ervoor zorgen dat personen zonder de beveiligingsrollen systeembeheerder of systeemaanpasser uw aanpassingen kunnen gebruiken. U hebt toegang tot twee gebruikersaccounts nodig om dit te doen: één account met de beveiligingsrol systeembeheerder en een andere met de beveiligingsrollen die de personen vertegenwoordigen die de aanpassingen zullen gebruiken.  
  
> [!IMPORTANT]
>  Probeer uw beveiligingsrol systeembeheerder niet te verwijderen als u maar één gebruikersaccount hebt. Het systeem geeft u een waarschuwing als u dat probeert, maar als u verder gaat, zou het kunnen dat u dit niet terug kunt krijgen. De meeste beveiligingsrollen staan het bewerken van beveiligingsrollen van een gebruiker niet toe.  
  
## <a name="next-steps"></a>Volgende stappen  
[Inzicht krijgen in onderdelen van modelgestuurde apps](model-driven-app-components.md)

