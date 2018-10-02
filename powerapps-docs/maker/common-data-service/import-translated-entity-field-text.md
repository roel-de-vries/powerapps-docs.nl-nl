---
title: Vertaalde entiteit- en veldtekst importeren met PowerApps | MicrosoftDocs
description: Lees hoe u vertaalde entiteit- en veldtekst kunt importeren
ms.custom: ''
ms.date: 06/19/2018
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
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="import-translated-entity-and-field-text-back-into-an-app"></a>Vertaalde entiteit- en veldtekst terug importeren in een app

Als u aangepaste entiteit- of veldtekst hebt, zoals veldlabels of vervolgkeuzelijstwaarden, kunt u de gebruikers in uw organisatie die niet met de basistaalversie van uw omgeving werken, deze aangepaste tekst in hun eigen taal bieden. Dit kunt u doen door de teksttekenreeksen voor al uw aanpassingen te exporteren, zodat deze kunnen worden vertaald in de talen die in uw organisatie worden gebruikt.  
  
 Na de vertaling, moet u de vertaalde teksttekenreeksen in uw omgeving importeren voordat gebruikers van de wijzigingen kunnen profiteren.  
  
> [!IMPORTANT]
> - Het bestand dat u wilt importeren moet een gecomprimeerd bestand zijn dat CrmTranslations.xml en [Content_Types].xml-bestand in de hoofdmap bevat.  
> - U kunt geen vertaalde tekst van meer dan 500 tekens importeren. Als uw bestand items van meer dan 500 tekens bevat, mislukt het importproces. Als het importproces mislukt, controleert u de regel in het bestand die de fout heeft veroorzaakt, verkleint u het aantal tekens en probeert u het bestand opnieuw te importeren. Houd er tevens rekening mee dat nadat u vertaalde tekst hebt geïmporteerd, u aanpassingen opnieuw moet publiceren.  
  
1. Open [oplossingenverkenner](../model-driven-apps/advanced-navigation.md#solution-explorer).  
  
2. Selecteer in de oplossingsverkenner de optie **Vertalingen importeren**.  
3.  Geef in het dialoogvenster **Vertaalde tekst importeren** het bestand met de vertaalde tekst op en selecteer vervolgens **Importeren**.  
  
4.  Selecteer **Sluiten** wanneer de import is voltooid.  
  
> [!NOTE]
>  Het publiceren van aanpassingen kan een probleem veroorzaken met de normale werking van het systeem. We adviseren u om het publiceren te plannen wanneer dit minimale gevolgen heeft voor gebruikers.  

## <a name="community-tools"></a>Community-hulpprogramma's

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) is een hulpprogramma dat de XrmToolBox-community heeft ontwikkeld voor Dynamics 365 Customer Engagement. Gebruik Easy Translator om vertalingen met contextuele gegevens te exporteren en te importeren. 

> [!NOTE]
> De community-hulpprogramma's worden niet ondersteund door Microsoft. Als u vragen hebt over het hulpprogramma, raadpleegt u de uitgever hiervan. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Volgende stappen  
 [Aangepaste entiteit- en veldtekst exporteren voor vertaling](export-customized-entity-field-text-translation.md)
