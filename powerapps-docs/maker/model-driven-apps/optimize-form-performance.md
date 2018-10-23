---
title: De formulierprestaties in modelgestuurde apps optimaliseren in PowerApps | Microsoft Docs
description: Ontdek hoe u voorkomt dat formulieren traag worden geladen wegens het formulierontwerp
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
ms.assetid: 59cfa5e6-638a-437f-a462-fddfd26fb07d
caps.latest.revision: 8
ms.author: matp
manager: kvivek
ms.openlocfilehash: c9dd764fe565b59e68411dabf453207c4e01a320
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674492"
---
# <a name="optimize-model-driven-app-form-performance"></a>De formulierprestaties in modelgestuurde apps optimaliseren

Als formulieren traag worden geladen, kan dit de productiviteit verlagen en zullen minder gebruikers er gebruik van maken. Volg deze aanbevelingen op om ervoor te zorgen dat uw formulieren zo snel mogelijk worden geladen. Veel van deze aanbevelingen hebben betrekking op hoe een ontwikkelaar formulierscripts kan implementeren voor uw organisatie. Zorg ervoor dat u deze aanbevelingen bespreekt met ontwikkelaars die formulierscripts maken voor uw formulieren.  
  
<a name="BKMK_FormDesign"></a>   
## <a name="form-design"></a>Formulierontwerp  
 Denk na over hoe de gebruiker het formulier gaat gebruiken en hoeveel gegevens erin moeten worden weergegeven.  
  
 **Houd het aantal velden beperkt tot een minimum**  
 Hoe meer velden er in een formulier staan, hoe meer gegevens er via internet of het intranet moeten worden verzonden voor het weergeven van records.  
  
<a name="BKMK_FormScripts"></a>   
## <a name="form-scripts"></a>Formulierscripts  
 Als u aanpassingen hebt doorgevoerd met gebruik van formulierscripts, zorgt u ervoor dat de ontwikkelaar op de hoogte is van de strategieën om de prestaties te verbeteren.  
  
 **Vermijd het gebruik van onnodige JavaScript-webresourcebibliotheken**  
 Hoe meer scripts u toevoegt aan het formulier, hoe langer het duurt om ze te downloaden. Meestal worden scripts in de cache van uw browser opgeslagen nadat ze voor het eerst zijn geladen, maar de eerste indruk van de prestaties zijn enorm belangrijk.  
  
 **Voorkom dat alle scripts worden geladen tijdens de gebeurtenis OnLoad**  
 Als u over code beschikt die alleen ondersteuning biedt voor `OnChange`-gebeurtenissen of de gebeurtenis `OnSave`, zorgt u ervoor dat u de scriptbibliotheek koppelt aan de gebeurtenis-handler voor die betreffende gebeurtenissen in plaats van de gebeurtenis `OnLoad`. Op die manier wordt het laden van bibliotheken uitgesteld en zijn de prestaties tijdens het laden van het formulier beter.  
  
 **Gebruik samengevouwen tabbladen om het laden van webresources uit te stellen**  
 Als er webresources of IFRAMES worden gebruikt in bepaalde secties in een samengevouwen tabblad, worden deze niet geladen zo lang het tabblad samengevouwen blijft. Ze worden pas geladen wanneer het tabblad wordt uitgevouwen. Wanneer de status van het tabblad verandert, treedt de gebeurtenis `TabStateChange` op. Bij alle code die nodig is ter ondersteuning van webresources en IFRAMES in samengevouwen tabbladen, kunnen er gebeurtenis-handlers worden gebruikt voor de gebeurtenis **TabStateChange**. De hoeveelheid code die nodig is in de gebeurtenis `OnLoad`, wordt dan beperkt.  
  
 **Stel tandaardopties voor zichtbaarheid in**  
 Vermijd het gebruik van formulierscripts in de gebeurtenis `OnLoad` waarmee formulierelementen worden verborgen. Gebruik in plaats daarvan de standaardopties voor zichtbaarheid voor formulierelementen die u wilt verbergen. De elementen zijn dan standaard niet zichtbaar wanneer het formulier wordt geladen. Gebruik vervolgens scripts in de gebeurtenis `OnLoad` om de formulierelementen weer te geven die u wél wilt tonen.  
  
<a name="BKMK_CommandBar"></a>   
## <a name="command-bar-or-ribbon"></a>Opdrachtbalk of lint  
 Houd rekening met deze aanbevelingen wanneer u de opdrachtbalk of het lint bewerkt.  
  
 **Houd het aantal besturingselementen beperkt tot een minimum**  
 Controleer in de opdrachtbalk of het lint van het formulier welke besturingselementen echt nodig zijn. Verberg de elementen die niet nodig zijn. Voor elk besturingselement dat wordt weergegeven, moeten er extra resources naar de browser worden gedownload.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Formulieren maken en ontwerpen](create-design-forms.md)    
    
 
