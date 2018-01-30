---
title: Een API-connector ontwikkelen | Microsoft Docs
description: De API beschrijven, het verificatietype opgeven, triggers en acties bouwen, en testen.
services: 
suite: powerapps
documentationcenter: na
author: asavaritayal
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/06/2017
ms.author: astay
ms.openlocfilehash: 68a0be6c6be91ff5b89b3e06aecc242f987a4cf4
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/12/2018
---
# <a name="develop-an-api-connector-powerapps"></a>Een API-connector ontwikkelen (PowerApps)
Het bouwen van een connector vindt in meerdere stappen plaats. Als u aan de slag wilt gaan, klikt of tikt u in [PowerApps](https://web.powerapps.com/) op de knop **Instellingen** (het tandwielpictogram) rechtsboven op de pagina. Klik of tik vervolgens op **Aangepaste connectors**.

![API-connectors zoeken](./media/api-connectors-dev/finding-custom-apis.png)

## <a name="describe-your-api"></a>Uw API beschrijven
API-connectors worden beschreven met behulp van de [OpenAPI standard](https://swagger.io/) voor het definiëren van de interface van een HTTP-API. U kunt het bouwen beginnen met een bestaand OpenAPI-bestand, maar u kunt ook een [Postman Collection](https://www.getpostman.com/docs/collections) importeren, waarmee het OpenAPI-bestand automatisch voor u wordt gegenereerd. 

![Het API-diagram definiëren](./media/api-connectors-dev/build-your-api-updated.png)

Als u uitgaat van een van deze API-beschrijvingen, worden de velden voor de metagegevens automatisch gevuld. U kunt deze altijd aanpassen.  

## <a name="build-security"></a>Beveiliging bouwen
Kies het verificatietype dat door uw service wordt ondersteund en geef aanvullende details op, zodat identiteit op de juiste manier tussen uw service en clients kan stromen. 

![Beveiligingsdiagram](./media/api-connectors-dev/security.png)

[Meer informatie](register-custom-api.md) over de beveiliging van connectors.

## <a name="build-triggers-and-actions"></a>Triggers en acties bouwen
1. Schakel over naar het tabblad **Definitie** als u triggers en acties voor uw connector wilt bouwen. 
   
    ![Diagram Definitie](./media/api-connectors-dev/definition.png)
2. Met de wizard kunt u nieuwe bewerkingen toevoegen of het schema en de respons voor bestaande bewerkingen bewerken. Met de **algemene** eigenschappen voor elke bewerking kunt u de werking voor eindgebruikers voor uw connector bepalen. Meer informatie over de verschillende typen bewerkingen vindt u via de onderstaande koppelingen:
   
   * [Triggers](https://flow.microsoft.com/documentation/customapi-webhooks) (niet zichtbaar in PowerApps)
   * [Acties](register-custom-api.md)
     
     Zie [OpenAPI-extensies voor aangepaste connectors](https://flow.microsoft.com/documentation/customapi-how-to-swagger/) als u de geavanceerde functionaliteit voor Microsoft Flow wilt implementeren. 
3. Klik of tik ten slotte op **Connector maken** om de API-connector te registreren.

Neem contact op met [condevhelp@microsoft.com](mailto:condevhelp@microsoft.com) voor aanvullende functies die niet in de wizard beschikbaar zijn.

## <a name="test-the-connector"></a>De connector testen
Voor dat u de API-connector indient, moet u deze testen. Dat kan op meerdere manieren: 

* Met de [Testing wizard](https://flow.microsoft.com/blog/new-updates-custom-api/) voor de API-connector, kunt u een bewerking aanroepen om de functionaliteit en het responsschema ervan te controleren.
* In de ontwerpfunctie voor Microsoft Flow kunt u visueel stromen bouwen met behulp van de API-connector. Dankzij deze testmethode hebt u meer inzicht in de functionaliteit van de gebruikersinterface en de functies van de connector.
* In PowerApps Studio kunt u een bewerking aanroepen via de formulebalk en de respons aan de besturingselementen op het scherm verbinden.

Dit onderwerp biedt een overzicht. Zie [Aangepaste API's registreren in PowerApps](register-custom-api.md) voor meer informatie.

