---
title: Een oplossing maken | Microsoft Docs
description: Ontdek hoe u een oplossing kunt maken
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
author: Mattp123
ms.assetid: e21a4876-08b4-417a-a644-c577a27c5cf1
caps.latest.revision: 12
ms.author: matp
manager: kvivek
ms.openlocfilehash: 26ecc9b2f83375ba10e6b32dfc12d6cc37342cf4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681207"
---
# <a name="create-a-solution"></a>Een oplossing maken

Omdat de standaardoplossing alle oplossingsonderdelen bevat, is het wellicht eenvoudiger om alleen de oplossingsonderdelen te zoeken die u hebt aangepast, als u een afzonderlijke oplossing maakt, en alle aanpassingen daar aan te brengen. Hierdoor kunt u ook eenvoudig een back-up van de oplossing exporteren als een kleiner bestand. Als u hiervoor kiest, moet u alleen nooit vergeten om alle oplossingsonderdelen die u bewerkt, toe te voegen aan de oplossing. Als u nieuwe oplossingsonderdelen maakt, moet u deze altijd in de context van deze oplossing maken. Op deze manier wordt het aanpassingsvoorvoegsel van de uitgever van de oplossing consistent toegepast. Nadat u oplossingsonderdelen hebt gemaakt in uw oplossing, of bestaande oplossingsonderdelen aan deze oplossing hebt toegevoegd, kunt u ze ook bewerken in de standaardoplossing, als u wilt.  
  
 Zie [Werken met oplossingen](solutions-overview.md) voor meer informatie over concepten voor oplossingen.  
  
1.  Navigeer naar **[Instellingen](../model-driven-apps/advanced-navigation.md#settings)** > **Oplossingen**. 
  
2.  Kies **Nieuw** en vul de vereiste velden voor de oplossing in  
  
    |Veld|Beschrijving|  
    |-----------|-----------------|  
    |**Weergavenaam**|De naam die wordt weergegeven in de lijst met oplossingen. U kunt deze later wijzigen.|  
    |**Naam**|De unieke naam van de oplossing. Deze wordt gegenereerd met behulp van de waarde die u invoert in het veld Weergavenaam. U kunt deze naam bewerken voordat u de oplossing opslaat, maar nadat u de oplossing hebt opgeslagen, kunt u de naam niet meer wijzigen.|  
    |**Uitgever**|U kunt de standaarduitgever selecteren of een nieuwe uitgever maken. Tenzij u van plan bent om de oplossing te distribueren, kunt u het beste de standaarduitgever voor uw organisatie gebruiken.|  
    |**Versie**|Voer een versienummer voor de oplossing in. Dit is alleen van belang als u de oplossing gaat exporteren. Het versienummer wordt opgenomen in de bestandsnaam wanneer u de oplossing exporteert.|  
  
3.  Kies **Opslaan**.  
  
 Nadat u de oplossing hebt opgeslagen, wilt u misschien gegevens toevoegen aan velden die niet zijn vereist. Deze stappen zijn optioneel. Gebruik het veld **Beschrijving** om de oplossing te beschrijven en kies een HTML-webresource als een **Configuratiepagina** voor de oplossing. De configuratiepagina wordt doorgaans gebruikt door ISV’s die de oplossingen distribueren. Wanneer dit is ingesteld, verschijnt er een nieuw knooppunt **Configuratie** onder het knooppunt **Gegevens** om deze webresource weer te geven. Ontwikkelaars gebruiken deze pagina om instructies of besturingselementen op te nemen waarmee u configuratiegegevens kunt instellen of hun oplossing kunt starten.  
  
<a name="BKMK_AddSolutionComponents"></a>   

## <a name="add-solution-components"></a>Oplossingsonderdelen toevoegen  
 Nadat u de oplossing hebt gemaakt, bevat deze nog geen oplossingsonderdelen. U kunt nieuwe oplossingsonderdelen maken of de knop **Bestaande toevoegen** in het lijstmenu gebruiken om oplossingsonderdelen uit de standaardoplossing toe te voegen.  
  
 Als u dit doet, ziet u mogelijk het dialoogvenster **Vereiste onderdelen ontbreken**.  
   
 ![Dialoogvenster Vereiste onderdelen toevoegen](media/crm-itpro-cust-addrequiredcomponents.PNG "Dialoogvenster Vereiste onderdelen toevoegen")  
  
 Dit dialoogvenster laat u weten dat het oplossingsonderdeel afhankelijkheden heeft in andere oplossingsonderdelen. Als u **Nee, vereiste onderdelen niet opnemen** selecteert, kan de oplossing mislukken als u deze importeert in een andere organisatie waar al deze vereiste onderdelen niet bestaan. Als het importeren van de oplossing is geslaagd, is het gedrag van de andere oplossing mogelijk niet hetzelfde als in de oorspronkelijke organisatie, omdat de onderdelen in de bronoplossing anders zijn geconfigureerd.  
  
 Over het algemeen is het veiliger om de vereiste onderdelen op te nemen als u van plan bent om de oplossing te exporteren in een andere organisatie. Als u deze onderdelen niet toevoegt wanneer u een afzonderlijk oplossingsonderdeel toevoegt, kunt u later terugkomen, het toegevoegde oplossingsonderdeel selecteren, en in het menu de optie **Vereiste onderdelen toevoegen** kiezen.  
  
 Als u niet van plan bent om de oplossing te exporteren, of als u deze alleen wilt exporteren als een onbeheerde oplossing en weer wilt importeren in dezelfde organisatie, hoeft u de vereiste onderdelen niet op te nemen. Als u de oplossing ooit exporteert, verschijnt er nog een waarschuwing dat bepaalde vereiste onderdelen ontbreken. Als u deze oplossing alleen wilt weer importeren in dezelfde organisatie, kunt u deze waarschuwing negeren. Bij de stappen voor het bewerken van de navigatie of het lint van de toepassing, zonder een hulpprogramma voor bewerken van derden, wordt ervan uitgegaan dat u de oplossing weer gaat exporteren in dezelfde organisatie.  

> [!IMPORTANT]
>  Als u van plan bent om afspraken op te nemen in oplossingen, raden we u sterk aan om alleen afspraken of alleen terugkerende afspraken op te nemen in afzonderlijke oplossingen. Als u afzonderlijke oplossingen met verschillende typen afspraken installeert en verwijdert, treedt er een fout op in SQL Server en moet u de afspraken opnieuw maken. 
