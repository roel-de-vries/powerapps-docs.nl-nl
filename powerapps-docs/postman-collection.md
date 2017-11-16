---
title: Een aangepaste connector beschrijven met Postman | Microsoft Docs
description: Een Postman Collection maken voor het registreren van aangepaste connectors
services: 
suite: powerapps
documentationcenter: 
author: archnair
manager: anneta
editor: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/28/2017
ms.author: archanan
ms.openlocfilehash: fd060ff873ee376b7ca886f721d360372c1d13ed
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="describe-a-custom-connector-with-postman"></a>Een aangepaste connector beschrijven met Postman
[Postman](https://www.getpostman.com/) is een hulpprogramma om het ontwikkelen van een API sneller een eenvoudiger te maken. In deze zelfstudie wordt getoond hoe u een Postman Collection kunt maken, die u vervolgens kunt gebruiken om eenvoudig [aangepaste connectors](register-custom-api.md) in PowerApps te maken.

## <a name="prerequisites"></a>Vereisten
* De [Postman-app](https://www.getpostman.com/apps) installeren

## <a name="create-a-postman-collection"></a>Een Postman Collection maken
We gaan een Postman Collection maken voor de [Tekstanalyse-API](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api) van Azure Cognitive Services. Met deze API worden de taal, het sentiment en de sleutelzinnen herkend in een tekst die u aanbiedt.

1. De eerste stap bij het maken van een Postman Collection bestaat uit het maken van een aanvraag. Als u een aanvraag maakt, kunt u het HTTP-woord, de aanvraag-URL, de parameters voor de query of het pad, de koppen en de hoofdtekst instellen. Zie [Sending Requests](https://www.getpostman.com/docs/requests) (Aanvragen verzenden) in de documentatie van Postman voor meer informatie. Voor het API-eindpunt Taal detecteren stelt u de waarden als volgt in:
   
    ![Postman-aanvraag](./media/postman-collection/request.png)
   
    Details van de gebruikte parameters en waarden:
   
   | Parameter | Waarde |
   | --- | --- |
   | Woord |POST |
   | Aanvraag-URL |https://westus.api.cognitive.microsoft.com/text/analytics/v2.0/languages |
   | Parameters |numberOfLanguagesToDetect |
   | Autorisatie |'No Auth' |
   | Koppen |Ocp-Apim-Subscription-Key = <your subscription key> <br/>Content-Type = application/json |
   | Hoofdtekst |<code>{<br/>&nbsp;&nbsp;&nbsp;"documents": [<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": "1",<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"text": "Hello World"<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;]<br/>}<code> |
2. Klik op **Verzenden** om de aanvraag te maken en een reactie te krijgen.
3. Klik op **Opslaan** om de aanvraag op te slaan in een Postman Collection.
   
    ![Reactie van Postman](./media/postman-collection/request-response-save.png)
4. Geef in het dialoogvenster **Aanvraag opslaan** een **Aanvraagnaam** en een **Aanvraagomschrijving** op. U gebruikt deze waarden in de aangepaste connector.
   
    ![Opslaan in Postman Collection](./media/postman-collection/save-request-note.png)
   
    U kunt ook de reactie op de aanvraag opslaan. Aangepaste connectors ondersteunen momenteel slechts één reactie per aanvraag. Als u meerdere reacties per aanvraag opslaat, wordt alleen de eerste gebruikt.
   
    ![Reactie opslaan in Postman](./media/postman-collection/save-response.png)
5. Blijf de Postman Collection ontwikkelen door andere reacties en aanvragen te maken en op te slaan.
6. Als u de ontwikkeling van de Postman Collection voor al uw aanvragen en reacties hebt voltooid, kunt u de Collection exporteren.
   
    ![Exporteren in Postman](./media/postman-collection/export.png)
7. Kies **Collection v1** als exportindeling.
   
    ![Exporteren in Postman](./media/postman-collection/export2.png)

U kunt deze Postman Collection nu gebruiken om een aangepaste connector in PowerApps te maken. Zie [Aangepaste API’s registreren in PowerApps](register-custom-api.md) voor meer informatie. 

