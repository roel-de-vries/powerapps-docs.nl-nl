---
title: Aangepaste connectors registreren en gebruiken | Microsoft Docs
description: Registreer en gebruik aangepaste connectors in PowerApps met OpenAPI en Postman.
services: 
suite: powerapps
documentationcenter: 
author: mgblythe
manager: anneta
editor: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/05/2017
ms.author: mblythe
ms.openlocfilehash: 80f56a849dca7488f5b38908a7ec87b3a0916187
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="register-and-use-custom-connectors-in-powerapps"></a>Aangepaste connectors registreren en gebruiken in PowerApps
Met PowerApps kunt u complete apps maken zonder traditionele toepassingscode. Maar in bepaalde gevallen kan het nodig zijn om de mogelijkheden van PowerApps uit te breiden en webservices zijn hier uitermate geschikt voor. Met uw app kunt u verbinding maken met een service, bewerkingen uitvoeren en gegevens ophalen. Als er een webservice is waarmee u verbinding wilt maken via PowerApps, kunt u de service registreren als een aangepaste connector. Dit proces zorgt ervoor dat PowerApps op de hoogte is van de kenmerken van uw web-API, waaronder de verificatie die de web-API vereist, de bewerkingen die de web-API ondersteunt en de parameters en uitvoer voor elk van deze bewerkingen.

In dit onderwerp bekijken we welke stappen u moet nemen om een aangepaste connector te registreren en te gebruiken en gebruiken we de [Tekstanalyse-API](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api) van Azure Cognitive Services als voorbeeld. Met deze API worden de taal, het sentiment en de sleutelzinnen herkend in een tekst die u aanbiedt. In de volgende afbeelding ziet u de interactie tussen de service, de aangepaste connector die we op basis van de service hebben gemaakt en de app die de API aanroept.

![API, aangepaste connector en app](./media/register-custom-api/intro-graphic.png)

## <a name="prerequisites"></a>Vereisten
* Een [PowerApps-account](https://powerapps.microsoft.com).
* Een OpenAPI-bestand in de JSON-indeling, een URL naar een OpenAPI-definitie of een Postman Collection voor uw API. Als u hier niet over beschikt, geven we aan hoe u deze in uw bezit kunt krijgen.
* Een afbeelding die u als pictogram voor de aangepaste connector kunt gebruiken (optioneel).

## <a name="steps-in-the-custom-connector-process"></a>Stappen in het proces voor het registreren van een aangepaste connector
Het registratieproces voor de aangepaste connector bestaat uit meerdere stappen die we hieronder kort beschrijven. In dit artikel wordt ervan uitgegaan dat u al een RESTful-API hebt met een bepaalde vorm van geverifieerde toegang, dus we richten ons nu op de stappen 3 tot en met 6 in het resterende deel van het artikel. Zie [Een aangepaste Web-API maken voor PowerApps](customapi-web-api-tutorial.md) voor een voorbeeld van de stappen 1 en 2.

1. **Maak een RESTful-API** in de taal en voor het platform van uw keuze. Voor Microsoft-technologieën raden wij een van de volgende opties aan.
   
   * Azure Functions
   * Azure Web Apps
   * Azure API Apps
2. **Beveilig uw API** met een van de volgende verificatiemechanismen. U kunt niet-geverifieerde toegang tot uw API's toestaan, maar dit raden we niet aan.
   
   * Azure Active Directory Zie, voor meer informatie, [Azure Active Directory gebruiken met een aangepaste connector in PowerApps](customapi-azure-resource-manager-tutorial.md).
   * OAuth 2.0 voor specifieke services zoals Dropbox, Facebook en SalesForce
   * Algemene OAuth 2.0
   * API-sleutel
   * Basisverificatie
3. **Beschrijf uw API** op een manier die voldoet aan een van de twee industrienormen, zodat PowerApps verbinding kan maken met de API.
   
   * Een OpenAPI-bestand (ook wel 'Swagger-bestand' genoemd)
   * Een Postman Collection
     
     U kunt ook in stap 4 een OpenAPI-bestand maken als onderdeel van het registratieproces.
4. **Registreer uw aangepaste connector** met een wizard in PowerApps, waarin u een beschrijving van de API, beveiligingsdetails en andere informatie opgeeft.
5. **Gebruik uw aangepaste connector** in een app. Maak een verbinding met de API in uw app en roep bewerkingen aan die de API biedt, op dezelfde manier waarop u in PowerApps systeemeigen functies aanroept.
6. **Deel uw aangepaste connector**, zoals u ook andere gegevensverbindingen in PowerApps deelt. Deze stap is optioneel, maar het is vaak zinvol om aangepaste connectors met meerdere makers van apps te delen.

## <a name="describe-your-api"></a>Uw API beschrijven
Als u een API hebt met een bepaalde vorm van geverifieerde toegang, moet u de API zo beschrijven dat PowerApps verbinding kan maken met de API. U doet dit door een OpenAPI-bestand of Postman Collection te maken. U kunt dit doen vanuit *elk* REST API-eindpunt, waaronder:

* Openbaar beschikbare API's. Enkele voorbeelden zijn [Spotify](https://developer.spotify.com/), [Uber](https://developer.uber.com/), [Slack](https://api.slack.com/), [Rackspace](http://docs.rackspace.com/), enzovoort.
* Een API die u maakt en implementeert op een cloudhostingprovider, zoals Azure, Amazon Web Services (AWS), Heroku en Google Cloud en meer.
* De implementatie van een aangepaste line-of-business-API op uw netwerk, zolang de API wordt weergegeven op internet.

OpenAPI-bestanden en Postman Collections hebben verschillende indelingen, maar zijn beide taalonafhankelijke, machineleesbare documenten waarin de bewerkingen en parameters van uw API worden beschreven:

* U kunt deze documenten met een aantal hulpprogramma's genereren, afhankelijk van de taal waarin en het platform waarop uw API is gemaakt. Zie de [documentatie van de Tekstanalyse-API](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/export?DocumentFormat=Swagger&ApiName=Azure) voor een voorbeeld van een OpenAPI-bestand.
* Als u nog geen OpenAPI-bestand voor uw API hebt en geen bestand wilt maken, kunt u nog steeds heel eenvoudig een aangepaste connector maken met behulp van een Postman Collection. Zie [Een Postman Collection maken](postman-collection.md) voor meer informatie.
* PowerApps gebruikt OpenAPI uiteindelijk achter de schermen, dus er wordt een Postman Collection geparseerd en vertaald naar een OpenAPI-definitiebestand.

**Opmerking**: de bestandsgrootte moet minder dan 1 MB zijn.

### <a name="getting-started-with-openapi-and-postman"></a>Aan de slag met OpenAPI en Postman
* Als u nog geen ervaring hebt met OpenAPI, raadpleegt u [Aan de slag met OpenAPI](http://swagger.io/getting-started/) op de site swagger.io.
* Als u nog geen ervaring hebt met Postman, installeert u de [Postman-app](https://www.getpostman.com/apps) van de Postman-website.
* Als uw API is gemaakt met Azure API Apps of Azure Functions, raadpleegt u [Exporting an Azure hosted API to PowerApps and Microsoft Flow](https://docs.microsoft.com/azure/app-service/app-service-export-api-to-powerapps-and-flow) (Een door Azure gehoste API exporteren naar PowerApps en Microsoft Flow) voor meer informatie.

## <a name="register-your-custom-connector"></a>Uw aangepaste connector registreren
U gebruikt nu het OpenAPI-bestand of de Postman Collection om uw aangepaste connector te registreren in PowerApps.

1. Selecteer op [powerapps.com](https://web.powerapps.com) in het menu aan de linkerkant de optie **Verbindingen**. Selecteer het beletselteken (**...** ) en selecteer **Aangepaste connectors beheren** in de rechterbovenhoek.
   
     **Tip**: als u de optie voor het beheren van aangepaste connectors niet kunt vinden in een mobiele browser, bevindt deze optie zich mogelijk in een menu in de linkerbovenhoek.
   
    ![Aangepaste connector maken](./media/register-custom-api/managecustomapi.png)  
2. Selecteer **Aangepaste connector maken**.
   
    ![Eigenschappen van aangepaste connectors](./media/register-custom-api/newcustomapi.png)
3. Geef op het tabblad **Algemeen** aan hoe u de aangepaste connector wilt maken.
   
   * OpenAPI-bestand uploaden
   * OpenAPI-URL gebruiken
   * Postman Collection V1 uploaden
     
     ![Een aangepaste connector maken](./media/register-custom-api/choosehowtocreate.png)
     
     Upload een pictogram voor uw aangepaste connector. De velden Beschrijving, Host en Basis-URL worden doorgaans automatisch gevuld met de gegevens van het OpenAPI-bestand. Als de velden niet automatisch worden gevuld, kunt u gegevens aan deze velden toevoegen. Selecteer **Doorgaan**.
4. Voer op het tabblad **Beveiliging** eventuele verificatie-eigenschappen in.
   
    ![Verificatietypen](./media/register-custom-api/authenticationtypes.png)
   
   * Het verificatietype wordt automatisch ingevuld op basis van de waarde die is gedefinieerd in uw OpenAPI-object `securityDefinitions`. Hieronder volgt een OAuth2.0-voorbeeld.
     
       ```
       "securityDefinitions": {
           "AAD": {
           "type": "oauth2",
           "flow": "accessCode",
           "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
           "scopes": {}
           }
       },
       ```
   * Als het OpenApi-bestand geen gebruik maakt van het object `securityDefintions`, zijn er geen aanvullende waarden nodig.
   * Wanneer u een Postman Collection gebruikt, wordt het verificatietype alleen automatisch ingevuld als u ondersteunde verificatietypen, zoals OAuth 2.0 of Basic gebruikt.
   * Zie [Een aangepaste Web-API maken voor PowerApps](customapi-web-api-tutorial.md#set-up-azure-active-directory-authentication) voor een voorbeeld van het instellen van AAD-verificatie (Azure Active Directory).
5. Op het tabblad **Definities** worden alle bewerkingen die zijn gedefinieerd in uw OpenAPI-bestand of Postman Collection, automatisch ingevuld samen met de aanvraag- en -responswaarden. Als al uw vereiste bewerkingen zijn gedefinieerd, kunt u naar stap 6 van het registratieproces gaan zonder wijzigingen in dit scherm aan te brengen.
   
    ![Tabblad Definitie](./media/register-custom-api/definitiontab.png)
   
    Als u bestaande acties wilt bewerken of nieuwe acties aan uw aangepaste connector wilt toevoegen, leest u hieronder verder.
   
   1. Als u een nieuwe actie wilt toevoegen die nog niet in uw OpenAPI-bestand of Postman Collection is opgenomen, selecteert u **Nieuwe actie** in het linkerdeelvenster en vult u in de sectie **Algemeen** de naam, beschrijving en zichtbaarheid van uw bewerking in.
   2. Selecteer in de sectie **Aanvragen** in de rechterbovenhoek de optie **Importeren vanuit voorbeeld**. Plak in het formulier aan de rechterkant een voorbeeldaanvraag. Voorbeeldaanvragen zijn gewoonlijk beschikbaar in de API-documentatie, waarin u informatie kunt krijgen om de velden **Bewerking**, **Aanvraag-URL**, **Kopteksten** en **Hoofdtekst** in te vullen. Zie de [documentatie van de Tekstanalyse-API](https://westus.dev.cognitive.microsoft.com/docs/services/TextAnalytics.V2.0/operations/56f30ceeeda5650db055a3c6) voor een voorbeeld.
      
       ![Importeren vanuit voorbeeld](./media/register-custom-api/importfromsample.png)
   3. Selecteer **Importeren** om de aanvraagdefinitie te voltooien. Definieer de respons op een vergelijkbare manier.
6. Zodra u al uw bewerkingen hebt gedefinieerd, selecteert u **Maken** om uw aangepaste connector te maken.
7. Als u uw aangepaste connector eenmaal hebt gemaakt, gaat u naar het tabblad **Testen** om de bewerkingen die in de API zijn gedefinieerd, te testen. Kies een verbinding en geef invoerparameters op voor het testen van een bewerking.
   
    ![Aangepaste connector testen](./media/register-custom-api/testcustomapi.png)
   
    Als de aanroep is gelukt, krijgt u een geldige respons.
   
    ![API-respons testen](./media/register-custom-api/testapiresponse.png)

## <a name="use-your-custom-connector"></a>Uw aangepaste connector gebruiken
Nu u de API hebt geregistreerd, voegt u de aangepaste connector toe aan uw app, zoals u elke andere gegevensbron zou toevoegen. We bekijken hier een beknopt voorbeeld. Zie [Een gegevensverbinding toevoegen in PowerApps](add-data-connection.md) voor meer informatie over gegevensverbindingen.

1. Klik of tik in PowerApps Studio in het rechterdeelvenster op **Gegevensbron toevoegen**.
   
    ![](./media/register-custom-api/data-source.png)
2. Klik of tik op de aangepaste connector die u hebt gemaakt.
   
    ![](./media/register-custom-api/connector.png)
3. Neem alle noodzakelijke stappen om u aan te melden bij de service waarmee u verbinding maakt. Als u verificatie met API OAuth gebruikt, wordt er mogelijk een aanmeldingsscherm weergegeven. Als u verificatie met een API-sleutel gebruikt, wordt u mogelijk om een sleutelwaarde gevraagd.
4. Roep de API in uw app aan. In ons voorbeeld hebben we een app gemaakt die tekst naar Cognitive Services verzendt en een sentimentscore terugkrijgt van 0 tot 1. Deze score wordt in de app weergegeven als een percentage.
   
   * Met deze connector ziet u, als u 'Az' begint te typen, in de formulebalk de API en de bewerkingen die door deze API beschikbaar worden gemaakt.
     
       ![](./media/register-custom-api/formula.png)
   * De volledige aanroep ziet er als volgt uit, waarbij we tekst invoeren via het besturingselement `TextInput` en een score terugkrijgen die in de app moet worden weergegeven:
     
       ```
       'AzureMachineLearning-TextAnalytics'.Sentiment({documents:Table({language:"en",id:"1",text:TextInput.Text})}).documents.score)
       ```
   * We werken nog wat verder aan de app om de gegevens die terugkomen, te verwerken, maar dat is niet al te ingewikkeld.

De voltooide app ziet eruit als in de volgende afbeelding. Het is een eenvoudige app, maar met een krachtige functionaliteit, omdat de app in staat is Cognitive Services aan te roepen via een aangepaste connector.

![](./media/register-custom-api/finished-app.png)

### <a name="quota-and-throttling"></a>Quota en beperkingen
* Raadpleeg de pagina met [PowerApps-prijzen](https://powerapps.microsoft.com/pricing/) voor meer informatie over quota voor het maken van aangepaste connectors. Aangepaste connectors die met u worden gedeeld, worden niet in mindering gebracht op dit quotum.
* Voor elke verbinding die voor een aangepaste connector wordt gemaakt, kunnen gebruikers maximaal 500 aanvragen per minuut doen.

## <a name="share-your-custom-connector"></a>Uw aangepaste connector delen
Nu u een aangepaste connector hebt, kunt u de connector delen met andere gebruikers in uw organisatie. Houd er rekening mee dat wanneer u een API deelt, anderen er afhankelijk van kunnen worden en dat bij het verwijderen van een aangepaste connector alle verbindingen met de API worden verwijderd. Als u gebruikers buiten uw organisatie een connector wilt bieden, raadpleegt u [Overview of certifying custom connectors in PowerApps](api-connector-overview.md) (Overzicht van het certificeren van aangepaste connectors in PowerApps).

1. Selecteer op [powerapps.com](https://web.powerapps.com) in het menu aan de linkerkant de optie **Verbindingen**. Selecteer het beletselteken (**...** ) en selecteer **Aangepaste connectors beheren** in de rechterbovenhoek.
   
    ![Nieuwe verbinding](./media/register-custom-api/managecustomapi.png)
2. Selecteer de knop met het beletselteken (**...** ) voor uw connector en selecteer vervolgens **Eigenschappen weergeven**.  
   
    ![Connectoreigenschappen weergeven](./media/register-custom-api/view-properties.png)
3. Selecteer de API, selecteer **Delen** en voer de gebruikers of groepen in die u toegang wilt verlenen tot de API.  
   
    ![Aangepaste connector delen](./media/register-custom-api/sharecustomapi.png)
4. Selecteer **Opslaan**.

## <a name="next-steps"></a>Volgende stappen
[Een Postman Collection maken](postman-collection.md)

[Een ASP.NET-web-API gebruiken](customapi-web-api-tutorial.md).

[Een Azure Resource Manager-API registreren](customapi-azure-resource-manager-tutorial.md).

