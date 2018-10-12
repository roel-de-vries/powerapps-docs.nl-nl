---
title: Vertaalde entiteit en veldtekst met PowerApps importeren | MicrosoftDocs
description: Meer informatie over het importeren van vertaalde entiteit en veldteksten
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
ms.openlocfilehash: e2417f7ad75e327fdfc54d4cd4fdd3f62395326b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681558"
---
# <a name="import-translated-entity-and-field-text-back-into-an-app"></a>Vertaalde entiteit en veldteksten weer in een app importeren

Als u entiteits- of veldtekst hebt aangepast, zoals veldlabels of keuzelijsten, kunt u de gebruikers in uw organisatie die niet met de basistaalversie van uw omgeving werken, voorzien van deze aangepaste tekst in hun eigen taal. Om dit te doen, exporteert u de tekenreeksen voor al uw aanpassingen zodat ze kunnen worden vertaald naar de talen die u in uw organisatie worden gebruikt.  
  
 Na de vertaling moet u de vertaalde tekenreeksen in uw omgeving importeren voordat gebruikers van de wijzigingen kunnen profiteren.  
  
> [!IMPORTANT]
> - Het bestand dat u importeert moet een gecomprimeerd bestand zijn dat CrmTranslations.xml en het .xml-bestand [Content_Types] in de hoofdmap bevat.  
> - U kunt geen vertaalde tekst importeren die meer dan 500 tekens lang is. Als een van de items in uw vertaalbestand langer is dan 500 tekens, mislukt het importproces. Als het importproces mislukt, bekijk dan de regel in het bestand die de fout heeft veroorzaakt, verminder het aantal tekens en probeer opnieuw te importeren. Houd er ook rekening mee wanneer u de vertaalde tekst hebt geïmporteerd, u aanpassingen moet importeren.  
  
1. Open [Solution Explorer](../model-driven-apps/advanced-navigation.md#solution-explorer).  
  
2. Selecteer in de Solution Explorer **Vertalingen importeren** op de werkbalk Acties.  
3.  Geef in het dialoogvenster **Vertaalde tekst importeren** het bestand op met de vertaalde tekst en selecteer vervolgens **Importeren**.  
  
4.  Wanneer het importeren is voltooid, selecteert u **Sluiten**.  
  
> [!NOTE]
>  Het publiceren van aanpassingen kan de normale werking van het systeem verstoren. Het wordt aanbevolen aanpassingen te publiceren wanneer dit het minst verstorend is voor gebruikers.  

## <a name="community-tools"></a>Communityhulpprogramma’s

[Easy Transltor](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) is een hulpprogramma dat de XrmToolbox-community heeft ontwikkeld voor Dynamics 365 Customer Engagement. Gebruik Easy Translator om vertalingen te exporteren en importeren met contextuele informatie. 

> [!NOTE]
> Hulpprogramma's die door de community zijn gemaakt, worden niet ondersteund door Microsoft. Als u vragen over het hulpprogramma hebt, neemt u contact op met de uitgever. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Volgende stappen  
 [Aangepaste entiteit en veldteksten voor vertaling exporteren](export-customized-entity-field-text-translation.md)
