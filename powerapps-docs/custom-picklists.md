---
title: Aangepaste selectielijsten maken | Microsoft Docs
description: Een aangepaste selectielijst maken.
services: powerapps
documentationcenter: na
author: pvillads
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/09/2017
ms.author: kfend
ms.openlocfilehash: cfa00b804df884ff9c5f1b4a96e0e8b4dc2088ba
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="create-custom-picklists"></a>Aangepaste selectielijsten maken
Het is nu mogelijk om uw eigen selectielijsten te maken ter aanvulling op de lijsten die standaard beschikbaar zijn. Selectielijsten, in feite een benoemde lijst met items die een naam en beschrijvingen bevatten, vormen een eenvoudig concept. Als de selectielijstvelden worden weergegeven, verschijnt er een vervolgkeuzelijst die de weergavenamen van de items bevat. 

Selectielijsten worden toegevoegd door het menu-item **Selectielijsten** op het tabblad **Common Data Service** onder het menu **Entiteiten** te gebruiken. Klik op het menu om alle selectielijsten weer te geven die momenteel in uw omgeving zijn gedefinieerd. Er zijn al verschillende veelgebruikte selectielijsten voor u gedefinieerd; u kunt ze gemakkelijk herkennen aan hun type, **Standaard**. Degene die u zelf maakt, hebben het type **Aangepast**.

1. Klik op **Nieuwe selectielijst** boven aan de pagina om een nieuwe selectielijst te maken. Definieer op de pagina die wordt geopend uw selectielijst door de naam en weergavenaam en een beschrijving in te voeren.
   > [!IMPORTANT]
> De naam van de selectielijst kan niet worden gewijzigd nadat u de selectielijst hebt gemaakt. Er zijn enkele vereisten voor de naam van de selectielijst. De naam moet eenvoudig zijn en mag geen speciale tekens bevatten. Ook kunt u maar één selectielijst met een bepaalde naam hebben. U ontvangt een foutmelding als u een andere selectielijst met dezelfde naam probeert te maken. Deze beperkingen gelden niet voor de **weergavenaam**.
   
    In dit onderwerp gaan we een selectielijst maken die kan worden gebruikt om een transportmodus te kiezen.
2. Geef de selectielijst de naam **Transport** en voeg de informatie toe aan de verplichte velden.
3. Klik op **Volgende** en geef op de volgende pagina de verschillende elementen van de selectielijst op, in dit voorbeeld de transportaanbieders. Als de pagina wordt geopend, ziet u dat er al één item is gemaakt. Werk het regelitem bij met relevante informatie voor de selectielijst die u maakt. Bewerken vindt plaats in de regel. Er is geen afzonderlijke lijst voor elk selectielijstitem. Klik in het veld **Nieuw item** om het eerste item toe te voegen. Klik elke keer wanneer u een nieuw selectielijstelement nodig hebt op **Item toevoegen** rechtsboven in het scherm om een nieuwe rij toe te voegen. 

U kunt een item verwijderen door op het pictogram met de prullenbak, uiterst rechts van elk regelitem, te klikken. Klik op **Maken** als u alle vereiste items hebt toegevoegd om de lijst te maken en naar de server te verzenden. U ziet dat de selectielijsten aan de lijst met bestaande selectielijsten wordt toegevoegd.

U kunt de selectielijst nu gebruiken om velden voor uw entiteiten te definiëren door een veldtype **Selectielijst** toe te voegen en daarna de **weergavenaam** in het deelvenster **Eigenschappen** voor het veld te gebruiken. 

