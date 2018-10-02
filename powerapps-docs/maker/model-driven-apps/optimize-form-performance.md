---
title: Prestaties van formulier voor modelgestuurde apps optimaliseren in PowerApps | MicrosoftDocs
description: Leer hoe u formulierontwerpen kunt vermijden die ervoor zorgen dat een formulier langzaam wordt geladen
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="optimize-model-driven-app-form-performance"></a>Prestaties van formulier voor modelgestuurde apps optimaliseren

Formulieren die langzaam laden kunnen de productiviteit en het aanvaardingsproces beperken. Volg deze aanbevelingen om het laden van uw formulieren te versnellen. Veel van deze aanbevelingen gaan over hoe een ontwikkelaar formulierscripts kan implementeren voor uw organisatie. Zorg ervoor dat u deze aanbevelingen met ontwikkelaars bespreekt die formulierscripts maken voor uw formulieren.  
  
<a name="BKMK_FormDesign"></a>   
## <a name="form-design"></a>Formulierontwerp  
 Denk na over de interactie die de gebruiker zal hebben met het formulier en de hoeveelheid gegevens erin moeten worden weergegeven.  
  
 **Beperk het aantal velden tot een minimum**  
 Hoe meer velden u hebt in een formulier, hoe meer gegevens via internet of intranet moeten worden overgebracht om elk record weer te geven.  
  
<a name="BKMK_FormScripts"></a>   
## <a name="form-scripts"></a>Formulierscripts  
 Als u aanpassingen hebt met formulierscript, zorg er dan voor dat de ontwikkelaar deze strategieën voor prestatieverbetering begrijpt.  
  
 **Vermijd het omvatten van overbodige JavaScript-webresourcebibliotheken**  
 Hoe meer scripts u aan het formulier toevoegt, hoe meer tijd het kost om ze te downloaden. Meestal worden de scripts in cache in uw browser bewaard nadat ze voor het eerst zijn geladen, maar de prestaties bij de eerste keer dat een formulier wordt weergegeven, maakt vaak een aanzienlijke indruk.  
  
 **Laad niet alle scripts in de gebeurtenis Onload**  
 Als u code gebruikt dat alleen gebeurtenissen voor `OnChange` velden ondersteunt of de gebeurtenis `OnSave`, zorg er dan voor dat u de scriptbibliotheek instelt met de gebeurtenismanager voor die gebeurtenissen in plaats van de gebeurtenis `OnLoad`. Op deze manier kan het laden van die bibliotheken worden uitgesteld en worden de prestaties tijdens het laden van het formulier vergroot.  
  
 **Gebruik samengevouwen tabbladen om het laden webresources uit te stellen**  
 Wanneer webresources of IFRAMES toegevoegd worden in secties in een samengevouwen tabblad, dan worden ze niet geladen wanneer het tabblad wordt samengevouwen. Ze worden geladen wanneer het tabblad wordt uitgevouwen. Als de tabbladstatus verandert, treedt de gebeurtenis `TabStateChange` op. Code dat vereist is om webresources of IFRAMEs te ondersteunen binnen samengevouwen tabbladen, kunnen gebeurtenismanagers gebruiken voor de gebeurtenis **TabStateChange** en code verminderen dat anders moet optreden in de gebeurtenis `OnLoad`.  
  
 **Standaard zichbaarheidopties instellen**  
 Het gebruik van formulierscripts vermijden in de gebeurtenis `OnLoad` die formulierelementen verbergt. Stel in plaats hiervan de standaard zichbaarheidopties voor formulierelementen die verborgen kunnen zijn in op niet standaard zichtbaar wanneer het formulier wordt geladen. Gebruikt vervolgens scripts in de gebeurtenis `OnLoad` om die formulierelementen weer te geven die u wilt tonen.  
  
<a name="BKMK_CommandBar"></a>   
## <a name="command-bar-or-ribbon"></a>Opdrachtbalk of lint  
 Houd deze aanbevelingen in uw achterhoofd wanneer u de opdrachtbalk of het lint bewerkt.  
  
 **Beperk het aantal besturingselementen tot een minimum**  
 Controleer in de opdrachtbalk of het lint voor het formulier welke besturingselementen nodig zijn en verberg degene die u niet nodig hebt. Elk besturingselement dat wordt weergegeven, vergroot het aantal resources die naar de browser moeten worden gedownload.  
  
## <a name="next-steps"></a>Volgende stappen  
 [Formulieren maken en ontwerpen](create-design-forms.md)    
    
 
