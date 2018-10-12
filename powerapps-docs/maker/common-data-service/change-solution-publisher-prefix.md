---
title: Het publicatievoorvoegsel van de oplossing wijzigen | MicrosoftDocs
ms.custom: ''
ms.date: 05/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: ece684h8-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
ms.openlocfilehash: 5881dd6742dd441d135768d3a96fd36dbef9e700
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677655"
---
# <a name="change-the-solution-publisher-prefix"></a>Het publicatievoorvoegsel van de oplossing wijzigen

Elke aanpassing die u maakt, maakt deel uit van een oplossing. Elke oplossing heeft een uitgever. Standaard is de oplossing waarmee u in PowerApps werkt de **Common Data Services-standaardoplossing** die is gekoppeld aan de **CDS-standaarduitgever**.

Het standaardvoorvoegsel voor aanpassing wordt willekeurig toegewezen voor deze uitgever. Het zou bijvoorbeeld `cr8a3` kunnen zijn. Dit betekent dat de naam van elk nieuw item van metagegevens dat is gemaakt voor uw organisatie, dit voorvoegsel krijgt om de items van elkaar te onderscheiden. Als u een nieuwe entiteit maakt met de naam **Dier**, wordt `cr8a3_animal` de unieke naam die wordt gebruikt door CDS voor Apps. Hetzelfde geldt voor alle nieuwe velden (kenmerken), relaties of optiesetopties.

Tenzij u uw oplossing wilt distribueren zodat deze samen met metagegevensitems die zijn gemaakt voor een andere oplossingsuitgever, wordt geïnstalleerd, is het niet echt belangrijk wat het aanpassingsvoorvoegsel is. Het is niet zichtbaar voor de meeste mensen die uw apps gebruiken. Maar het is wel zichtbaar voor ontwikkelaars en andere technische mensen die taken uitvoeren als het maken van rapporten. Het biedt een snelle manier om te begrijpen welke oplossing het item heeft toegevoegd.

Om deze reden willen veel mensen het voorvoegsel van de uitgever van de oplossing wijzigen zodat deze meer betekenis heeft, met name wanneer u metagegevensitems bekijkt die zijn geïmporteerd uit andere oplossingen. 

> [!NOTE]
> Als u het voorvoegsel van de uitgever van de oplossing wijzigt, moet u dit doen voordat u nieuwe metagegevensitems maakt. U kunt de namen van de metagegevensitems niet wijzigen.
> Wanneer u de waarde van het aanpassingsvoorvoegsel wijzigt, zorg u er dan voor dat u met de Tab-toets naar het volgende veld gaat. Het **optiewaardevoorvoegsel** genereert automatisch een nummer op basis van het aanpassingsvoorvoegsel. Dit nummer wordt gebruikt wanneer u opties aan optiesets toevoegt en geeft aan welke oplossing is gebruikt voor het toevoegen van de optie. 

## <a name="change-the-solution-publisher-prefix-for-the-cds-default-publisher"></a>Het publicatievoorvoegsel van de oplossing wijzigen voor de CDS Default Publisher  

 1. Selecteer in de PowerApps-portal **Modelgestuurd** in de linkerbenedenhoek.
 2. Klik op **Geavanceerd** in het linkernavigatievenster om de **Common Data Services Default Solution** te openen.
 3. Selecteer in de Solution Explorer het **informatiegebied** in het linkernavigatievenster.
 4. Klik op de koppeling **Uitgever** om het formulier **CDS Default Publisher** te openen.
 5. Bewerk de waarde in het veld **Voorvoegsel** voor het gewenste aanpassingsvoorvoegsel.
 6. Klik op **Opslaan en sluiten**.
  
## <a name="change-the-solution-publisher-prefix-for-any-publisher"></a>Het publicatievoorvoegsel van de oplossing wijzigen voor een uitgever

Mensen die hun oplossingen distribueren werken doorgaans binnen een oplossing die ze maken, in plaats van in de **Common Data Services Default Solution**. Het aanpassingsvoorvoegsel wordt meestal ingesteld bij het maken van de oplossing. U kunt het aanpassingsvoorvoegsel voor een andere niet-beheerde oplossing waarmee u werkt, wijzigen door deze stappen te volgen: 

 1. Selecteer in de PowerApps-portal **Modelgestuurd** in de linkerbenedenhoek.
 2. Klik op **Geavanceerd** in het linkernavigatievenster om de **Common Data Services Default Solution** te openen.
 3. Bewerk de URL van de pagina als u alles wilt verwijderen na `dynamics.com` en laad de pagina opnieuw.
 4. Navigeer naar **Instellingen** > **Aanpassing** > **Aanpassingen**. 
 5. Klik op **Uitgevers**. U ziet nu een lijst met beschikbare uitgevers.
 6. Klik op de uitgever die u wilt bewerken om het formulier Uitgever te openen.
 7. Bewerk de waarde in het veld **Voorvoegsel** voor het gewenste aanpassingsvoorvoegsel.
 6. Klik op **Opslaan en sluiten**.
  