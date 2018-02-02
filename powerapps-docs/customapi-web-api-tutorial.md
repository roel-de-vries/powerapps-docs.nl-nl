---
title: Een aangepaste connector bouwen voor een Web-API | Microsoft Docs
description: Leer hoe u een ASP.NET-web-API maakt met Azure Active Directory-verificatie in PowerApps.
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
ms.date: 10/26/2016
ms.author: mblythe
ms.openlocfilehash: 4fc9fb1d183ec910d37383be6629aaa67cf3723d
ms.sourcegitcommit: 68eee592c351688e5d0bd458f33a70be507fa53f
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/30/2018
---
# <a name="build-a-custom-connector-for-a-web-api-in-powerapps"></a>Een aangepaste connector bouwen voor een Web-API in PowerApps
In deze zelfstudie leert u hoe u een ASP.NET-web-API maakt, hoe u deze in Azure Web Apps host, hoe u Azure Active Directory-verificatie inschakelt en hoe u de ASP.NET-web-API in PowerApps registreert. Nadat de API is geregistreerd, kunt u hiermee verbinding maken en deze aanroepen vanuit uw app.

## <a name="prerequisites"></a>Vereisten
* Een [Azure-abonnement](https://azure.microsoft.com/en-us/free/).
* Een [PowerApps-account](https://powerapps.microsoft.com).
* [Visual Studio](https://www.visualstudio.com/vs/) 2013 of hoger.

## <a name="create-an-aspnet-web-api-and-deploy-it-to-azure"></a>Een ASP.NET-web-API maken en implementeren in Azure
1. Klik in Visual Studio op **Bestand** > **Nieuw project** om een nieuwe C# ASP.NET-webtoepassing te maken.
   
    ![Nieuwe web-app](./media/customapi-web-api-tutorial/newwebapp.png)
2. Selecteer de sjabloon **Web-API**.  Houd **Host in the cloud** ingeschakeld.  Klik op **Change Authentication**.
   
    ![Nieuwe sjabloon voor webproject](./media/customapi-web-api-tutorial/new-web-api.png)
3. Selecteer **No Authentication** en klik op **OK**.
   
    ![Geen verificatie](./media/customapi-web-api-tutorial/noauth.png)
4. Klik op **OK** in het dialoogvenster **New ASP.NET Project**.  Het dialoogvenster Configure Microsoft Azure Web App wordt weergegeven.
   
    ![Microsoft Azure Web App configureren](./media/customapi-web-api-tutorial/azure-publishing.png)]
   
    Selecteer uw type Azure-account, typ een **web-app-naam** (of laat de standaardnaam staan) en selecteer uw **abonnement** op Azure.  Selecteer of maak een **App Service-plan** (een verzameling Web-apps binnen uw abonnement).  Selecteer of maak een **resourcegroep** (een groep Azure-resources voor uw abonnement).  Selecteer de regio waar de web-app moet worden geïmplementeerd.  Selecteer of maak een **databaseserver** voor Azure indien deze is vereist voor uw web-API.  Klik ten slotte op **OK**.
5. Breid uw web-API verder uit.
   
    > [!NOTE]
> Raadpleeg de zelfstudie [Aan de slag met ASP.NET Web API 2 (C#)](http://www.asp.net/web-api/overview/getting-started-with-aspnet-web-api/tutorial-your-first-web-api) als u nog geen code voor een web-API hebt.
6. Als u verbinding wilt maken met de web-API voor PowerApps, hebt u een [OpenAPI](http://swagger.io/)-bestand nodig, waarin de bewerkingen staan beschreven.  U kunt zelf een OpenAPI-bestand schrijven met de [online-editor](http://editor.swagger.io/), maar voor deze zelfstudie gebruikt u het open source-programma [Swashbuckle](https://github.com/domaindrivendev/Swashbuckle/blob/master/README.md).  Installeer het Swashbuckle Nuget-pakket in uw Visual Studio-project door op **Hulpprogramma's** > **NuGet Package Manager** > **Package Manager Console** te klikken. Typ vervolgens de opdracht `Install-Package Swashbuckle` in Package Manager Console.
   
    ![Install-Package Swashbuckle](./media/customapi-web-api-tutorial/swashbuckle-console.png)
   
    > [!TIP]
> Wanneer u de web-API-toepassing uitvoert na de installatie van Swashbuckle, wordt er een OpenAPI-bestand gegenereerd op de URL `http://<your root URL>/swagger/docs/v1`.  Er is ook een gegenereerde gebruikersinterface beschikbaar op `http://<your root URL>/swagger`.
7. Als de web-API klaar is, kunt u deze publiceren naar Azure. Als u vanuit Visual Studio wilt publiceren, klikt u met de rechtermuisknop op het webproject in Solution Explorer, vervolgens op **Publiceren...** en volgt u de aanwijzingen in het dialoogvenster Publiceren.
8. Haal de OpenAPI-JSON op door naar `https://<azure-webapp-url>/swagger/docs/v1` te navigeren.  Sla de inhoud als een JSON-bestand op.  Wellicht moet u de tekst kopiëren en in een leeg tekstbestand plakken. Dit is afhankelijk van uw browser.   
   
    > [!IMPORTANT]
> Een OpenAPI-document met dubbele bewerkings-id's is ongeldig. Als u de C#-voorbeeldsjabloon gebruikt, wordt bewerkings-id `Values_Get` tweemaal herhaald. U kunt dit herstellen door één exemplaar te wijzigen in `Value_Get` en opnieuw te publiceren. U kunt ook een [OpenAPI-voorbeeldbestand](http://pwrappssamples.blob.core.windows.net/samples/webAPI.json) uit deze zelfstudie downloaden. Verwijder de opmerkingen (beginnend met `//`) voordat u het gebruikt.

## <a name="set-up-azure-active-directory-authentication"></a>Azure Active Directory-verificatie instellen
U gaat nu twee Azure Active Directory-toepassingen (AAD) maken in Azure.  Zie de [zelfstudie over Azure Resource Manager](customapi-azure-resource-manager-tutorial.md#enable-authentication-in-azure-active-directory) voor een voorbeeld hiervan.

> [!IMPORTANT]
> Beide apps moeten zich in dezelfde map bevinden.

### <a name="first-aad-application-securing-the-web-api"></a>Eerste ADD-toepassing: de web-API beveiligen
De eerste ADD-toepassing wordt gebruikt om de web-API te beveiligen. Noem deze toepassing **webAPI**.  Volg de stappen in de zelfstudie via de koppeling hierboven (alleen de sectie getiteld 'Enable authentication in Azure Active Directory') met de volgende waarden:

* Aanmeldings-URL: `https://login.windows.net`
* Antwoord-URL: `https://<your-root-url>/.auth/login/aad/callback`
* U hebt geen clientsleutel nodig.
* U hoeft geen machtigingen te delegeren.

> [!IMPORTANT]
> Onthoud de toepassings-id.  Deze hebt u later nodig.

### <a name="second-aad-application-securing-the-custom-connector-and-delegated-access"></a>Tweede AAD-toepassing: de aangepaste connector beveiligen en gedelegeerde toegang
De tweede AAD-toepassing wordt gebruikt om de aangepaste connectorregistratie te beveiligen en gedelegeerde toegang te krijgen tot de web-API die door de eerste toepassing wordt beschermd. Noem deze toepassing **webAPI-customAPI**.

* Aanmeldings-URL: `https://login.windows.net`
* Antwoord-URL: `https://msmanaged-na.consent.azure-apim.net/redirect`
* Voeg machtigingen toe voor gedelegeerde toegang tot de web-API.
* U hebt de toepassings-id van deze toepassing ook later nog nodig, dus onthoud deze.
* Genereer een clientsleutel en bewaar deze op een veilige plaats. U hebt deze sleutel later nog nodig.

## <a name="add-authentication-to-your-azure-web-app"></a>Authenticatie toevoegen aan uw Azure-web-app

1. Meld u aan bij [Azure Portal](https://portal.azure.com) en zoek de web-app die u in de eerste sectie hebt geïmplementeerd.

2. Klik op **Instellingen** en selecteer **Verificatie/autorisatie**.

3. Schakel **App Service-verificatie** in en selecteer **Azure Active Directory**.  Op de volgende blade selecteert u **Express**.  

4. Klik op **Bestaande AD-app selecteren** en selecteer de AAD-toepassing **webAPI** die u eerder hebt gemaakt.

U moet nu gebruik kunnen maken van AAD om uw webtoepassing te verifiëren.

## <a name="add-the-custom-connector-to-powerapps"></a>De aangepaste connector aan PowerApps toevoegen
1. Wijzig het OpenAPI-bestand om het `securityDefintions`-object en de AAD-verificatie die voor de web-app wordt gebruikt toe te voegen. De sectie van het OpenAPI-bestand met de eigenschap **Host** moet er als volgt uitzien:

    ```javascript
    // File header should be above here...

    "host": "<your-root-url>",
    "schemes": [
        "https"         //Make sure this is https!
    ],
    "securityDefinitions": {
        "AAD": {
            "type": "oauth2",
            "flow": "implicit",
            "authorizationUrl": "https://login.windows.net/common/oauth2/authorize",
            "scopes": {}
        }
    },

    // The rest of the OpenAPI document follows...
    ```

2. Blader naar [PowerApps](https://web.powerapps.com) en voeg een aangepaste connector toe, zoals beschreven in het Engelstalige artikel [Register and use custom connectors in PowerApps](register-custom-api.md).

3. Zodra u het OpenAPI-bestand hebt geüpload, wordt door de wizard automatisch gedetecteerd dat u AAD-verificatie gebruikt voor uw web-API.

4. Configureer de AAD-verificatie voor de aangepaste connector.  
   
   * **Client-id**: *client-id van webAPI-CustomAPI*
   * **Geheim**: *clientsleutel van webAPI-CustomAPI*
   * **Aanmeldings-URL**: `https://login.windows.net`
   * **ResourceUri**: *client-id van webAPI*
5. Klik op **Maken** en maak verbinding met de aangepaste connector.

## <a name="next-steps"></a>Volgende stappen
Lees de Engelstalige [zelfstudie Azure Resource Manager custom connector](customapi-azure-resource-manager-tutorial.md).

