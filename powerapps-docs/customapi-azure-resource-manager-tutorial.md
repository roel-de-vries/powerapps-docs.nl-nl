---
title: Azure Active Directory gebruiken met een aangepaste connector | Microsoft Docs
description: Informatie over het maken van een aangepaste connector voor Azure Resource Manager met Azure Active Directory-verificatie.
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
ms.date: 05/03/2017
ms.author: mblythe
ms.openlocfilehash: c62a927ae6a7e7b6cf6b101d84e3ba1fe15cccc5
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="use-azure-active-directory-with-a-custom-connector-in-powerapps"></a>Azure Active Directory gebruiken met een aangepaste connector in PowerApps
Met Azure Resource Manager (ARM) kunt u de onderdelen van een oplossing, zoals databases, virtuele machines en web-apps, in Azure beheren. In deze zelfstudie ziet u hoe u verificatie in Azure Active Directory inschakelt, een van de ARM-API's als een aangepaste connector registreert en hier vervolgens verbinding mee maakt in PowerApps. Dit is handig als u Azure-bronnen rechtstreeks vanuit een app wilt beheren. Zie [Overzicht van Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview) voor meer informatie over ARM.

## <a name="prerequisites"></a>Vereisten
* Een [Azure-abonnement](https://azure.microsoft.com/free/).
* Een [PowerApps-account](https://powerapps.microsoft.com).
* Het [OpenAPI-voorbeeldbestand](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json) dat in deze zelfstudie wordt gebruikt.

## <a name="enable-authentication-in-azure-active-directory"></a>Verificatie inschakelen in Azure Active Directory
Eerst moet u een AAD-toepassing (Azure Active Directory) maken die de verificatie uitvoert wanneer het ARM-API-eindpunt wordt aangeroepen.

1. Meld u aan bij [Azure Portal](https://portal.azure.com).  Als u meer dan één Azure Active Directory-tenant hebt, zorg er dan voor dat u bent aangemeld bij de juiste map door te kijken naar uw gebruikersnaam in de rechterbovenhoek.
   
    ![Gebruikersnaam](./media/customapi-azure-resource-manager-tutorial/current-user.png)
2. Klik in het menu links op **Meer services**.  Typ **Azure Active Directory** in het tekstvak **Filter** en klik vervolgens op **Azure Active Directory**.
   
    ![Azure Active Directory](./media/customapi-azure-resource-manager-tutorial/azureaad.png)
   
    De blade Azure Active Directory wordt geopend.   
3. Klik in het menu op de blade Azure Active Directory op **App-registraties**.
   
    ![App-registraties](./media/customapi-azure-resource-manager-tutorial/azureapplication.png)
4. Klik in de lijst met geregistreerde toepassingen op **Toevoegen**.
   
    ![De knop toevoegen](./media/customapi-azure-resource-manager-tutorial/add-app-btn.png)   
5. Typ een naam voor uw toepassing, laat **Web-app/API** geselecteerd en typ `https://login.windows.net` voor **Aanmeldings-URL**.  Klik op **Maken**.  
   
    ![Nieuw app-formulier](./media/customapi-azure-resource-manager-tutorial/newapplication.png)
6. Klik op de nieuwe toepassing in de lijst.
   
    ![Nieuwe app in lijst](./media/customapi-azure-resource-manager-tutorial/newapplication2.png)
   
    De blade Geregistreerde app wordt geopend.  Noteer de **toepassings-id**.  Deze hebt u later nodig.
7. De blade Instellingen moet eveneens zijn geopend.  Als dit niet het geval is, klikt u op de knop **Instellingen**.
   
    ![De knop Instellingen](./media/customapi-azure-resource-manager-tutorial/settings-btn.png)
8. Klik op de blade Instellingen op **Antwoord-URL's**. Voeg `https://msmanaged-na.consent.azure-apim.net/redirect` toe in de lijst met URL's en klik op **Opslaan**.
   
    ![Antwoord-URL’s](./media/customapi-azure-resource-manager-tutorial/reply-urls.png)
9. Klik op de blade Instellingen op **Vereiste machtigingen**.  Klik op de blade Vereiste machtigingen op **Toevoegen**.
   
    ![Vereiste machtigingen](./media/customapi-azure-resource-manager-tutorial/permissions.png)
   
    De blade API-toegang toevoegen wordt geopend.
10. Klik op **Selecteer een API**. Klik op de blade die wordt geopend op de optie voor de Azure Service Management-API en klik op **Selecteren**.
    
    ![Een API selecteren](./media/customapi-azure-resource-manager-tutorial/permissions2.png)
11. Klik op **Machtigingen selecteren**.  Klik onder *Gedelegeerde machtigingen* op **Access Azure Service Management as organization users** en klik op **Selecteren**.
    
    ![Gedelegeerde machtigingen](./media/customapi-azure-resource-manager-tutorial/permissions3.png)
12. Klik op de blade API-toegang toevoegen op **Gereed**.
13. Klik op de blade Instellingen op **Sleutels**.  Typ op de blade Sleutels een beschrijving voor uw sleutel, selecteert een vervalperiode en klik op **Opslaan**.  Uw nieuwe sleutel wordt weergegeven.  Noteer de waarde van de sleutel, aangezien u die later ook nodig hebt.  U kunt Azure Portal nu sluiten.
    
    ![Een sleutel maken](./media/customapi-azure-resource-manager-tutorial/configurekeys.png)

## <a name="add-the-connection-in-powerapps"></a>De verbinding toevoegen in PowerApps
Nu de AAD-toepassing is geconfigureerd, gaat u de aangepaste connector toevoegen.

1. Selecteer op [powerapps.com](https://web.powerapps.com) in het menu aan de linkerkant de optie **Verbindingen**. Selecteer het beletselteken (**...** ) en selecteer **Aangepaste connectors beheren** in de rechterbovenhoek.
   
     **Tip**: als u de optie voor het beheren van aangepaste connectors niet kunt vinden in een mobiele browser, bevindt deze optie zich mogelijk in een menu in de linkerbovenhoek.
   
    ![Aangepaste connector maken](./media/customapi-azure-resource-manager-tutorial/managecustomapi.png)  
2. Selecteer **Aangepaste connector maken**.
   
    ![Eigenschappen van aangepaste connectors](./media/customapi-azure-resource-manager-tutorial/newcustomapi.png)
3. Typ een naam voor uw verbinding en upload het [OpenAPI-voorbeeldbestand voor ARM](http://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json).  Klik op **Doorgaan**.  
   
    ![Verbinding maken met een nieuw API-eindpunt](./media/customapi-azure-resource-manager-tutorial/createcustom.png)
4. Omdat het OpenAPI-bestand onze AAD-toepassing voor verificatie gebruikt, moet u in het volgende scherm enkele gegevens over de toepassing doorgeven aan PowerApps.  Typ onder **Client-id** de **toepassings-id** van de AAD-toepassing die u eerder hebt genoteerd.  Gebruik de **sleutel** als clientgeheim.  Typ ten slotte `https://management.core.windows.net/` voor **Bron-URL**.
   
    **Belangrijk**: zorg dat u de bron-URL exact toevoegt zoals die hierboven wordt weergegeven, inclusief de afsluitende schuine streep.
   
    ![OAuth-instellingen](./media/customapi-azure-resource-manager-tutorial/oauthsettings.png)
5. Uw aangepaste connector is nu geregistreerd en kan worden gebruikt in PowerApps of Microsoft Flow.
   
    ![Aangepaste connector toegevoegd](./media/customapi-azure-resource-manager-tutorial/createdcustomapi.png)
   
    **Opmerking**: het OpenAPI-voorbeeldbestand definieert niet de volledige set ARM-bewerkingen en bevat momenteel alleen de bewerking [Alle abonnementen vermelden](https://msdn.microsoft.com/library/azure/dn790531.aspx).  U kunt dit OpenAPI-bestand bewerken of een ander OpenAPI-bestand maken met de [online OpenAPI-editor](http://editor.swagger.io/). Dit proces kan worden gebruikt om toegang te krijgen tot een RESTful-API die wordt geverifieerd met AAD.

## <a name="next-steps"></a>Volgende stappen
Zie het Engelstalige artikel [Create an app from data](get-started-create-from-data.md) (Een app maken op basis van gegevens) voor meer uitgebreide informatie over het maken van apps.

Zie [Een stroom in een app starten](using-logic-flows.md) voor meer uitgebreide informatie over het gebruik van stromen in apps.

[Word lid van onze community](https://aka.ms/powerapps-community) als u vragen of opmerkingen hebt over aangepaste connectors.

