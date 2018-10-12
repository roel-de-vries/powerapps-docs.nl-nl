---
title: Vereiste bevoegdheden voor modelgestuurde app-aanpassing | MicrosoftDocs
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
ms.openlocfilehash: dd0c7e05d756145a701bb6bfb137dc07cb8c45fb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675964"
---
# <a name="privileges-required-for-model-driven-app-customization"></a>Vereiste bevoegdheden voor modelgestuurde app-aanpassing

App-gebruikers kunnen het systeem personaliseren en zelfs sommige van hun aanpassingen delen met anderen, maar alleen gebruikers met de juiste bevoegdheden kunnen wijzigingen voor iedereen toepassen.  
  
> [!NOTE]
>  In deze sectie wordt ervan uitgegaan dat u weet hoe u met beveiligingsrollen moet werken. Zie voor meer informatie over het werken met beveiligingsrollen [Gebruikers maken en beveiligingsrollen toewijzen](https://docs.microsoft.com/dynamics365/customer-engagement/admin/create-users-assign-online-security-roles).  
  
<a name="BKMK_SysAdminAndSysCustomizer"></a>   
## <a name="system-administrator-and-system-customizer-security-roles"></a>De beveiligingsrollen Systeembeheerder en Systeemaanpasser  
 Iedereen die aanpast moet de beveiligingsrol Systeembeheerder of Systeemaanpasser hebben gekoppeld aan zijn/haar account. Deze beveiligingsrollen geven u de machtigingen die u nodig hebt om de app aan te passen.  
  
|Systeembeheerder|Systeemaanpasser|  
|--------------------------|-----------------------|  
|Heeft alle machtigingen voor het aanpassen van het systeem|Heeft alle machtigingen voor het aanpassen van het systeem|  
|Kan alle gegevens in het systeem weergeven|Kan alleen records weergeven voor systeementiteiten die hij/zij maakt|  
  
 Het verschil tussen de beveiligingsrollen Systeembeheerder en Systeemaanpassing is dat een systeembeheerder leesrechten heeft voor de meeste records in het systeem en alles kan zien. Wijs de functie Systeemaanpasser toe aan iemand die aanpassingstaken moet uitvoeren, maar geen gegevens in de systeementiteiten mag zien. Testen is echter een belangrijk onderdeel van het aanpassen van het systeem. Als systeemaanpassers geen gegevens kunnen zien, moeten ze records maken om hun aanpassingen te testen. Systeemaanpassers hebben standaard volledige toegang tot aangepaste entiteiten. Als u dezelfde beperkingen wilt hebben als voor systeementiteiten, moet u de beveiligingsrol Systeemaanpasser zo aanpassen dat het toegangsniveau voor aangepaste entiteiten **Gebruiker** in plaats van **Organisatie** is.  
  
<a name="BKMK_DelegatingCustomizationTasks"></a>   
## <a name="delegate-customization-tasks"></a>Aanpassingstaken delegeren  
 Misschien wilt u sommige taken delegeren aan vertrouwde mensen, zodat ze de benodigde wijzigingen kunnen toepassen. Houd er rekening mee dat aan iedereens account meerdere beveiligingsrollen kunnen zijn gekoppeld, en dat de bevoegdheden en toegangsrechten die beveiligingsrollen bieden, gebaseerd zijn op het *minst beperkende* beveiligingsniveau.  
  
 Dit betekent dat u de beveiligingsrol van Systeemaanpasser kunt geven aan iemand die al een andere beveiligingsrol heeft, bijvoorbeeld een verkoopmanager. Hierdoor kan deze het systeem aanpassen naast andere privileges die hij/zij al heeft. U hoeft de beveiligingsrol die deze persoon al heeft niet te bewerken, en u kunt de beveiligingsrol van Systeemaanpasser verwijderen van het gebruikersaccount van de persoon wanneer u dat wilt.  
  
<a name="BKMK_UsingTwoUserAccounts"></a>   
## <a name="test-customizations-without-customization-privileges"></a>Aanpassingen testen zonder aanpassingsbevoegdheden  
 U moet alle aanpassingen die u maakt, altijd testen met een gebruikersaccount zonder aanpassingsrechten. Op deze manier kunt u ervoor zorgen dat mensen zonder de beveiligingsrol Systeembeheerder of Systeemaanpasser uw aanpassingen kunnen gebruiken. Om dit effectief te doen, hebt u toegang nodig tot twee gebruikersaccounts: één account met de beveiligingsrol Systeembeheerder en één met de beveiligingsrollen die de mensen vertegenwoordigen die de aanpassingen zullen gebruiken.  
  
> [!IMPORTANT]
>  Probeer niet de beveiligingsrol Systeembeheerder te verwijderen als u slechts één gebruikersaccount hebt. Het systeem zal u waarschuwen als u dat probeert, maar als u doorgaat, zou u kunnen merken dat u deze rol niet meer terug kunt krijgen. Met de meeste beveiligingsrollen is het niet toegestaan de beveiligingsrollen van een gebruiker te bewerken.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Aan de slag met aanpassen](getting-started-customization.md)

