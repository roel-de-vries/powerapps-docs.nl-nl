---
title: Gegevensgroepen | Microsoft Docs
description: Overzicht van hoe u gegevensgroepen gebruikt in PowerApps.
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 6a6217c0a344d0501c8a856b0632397044ceb465
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2018
ms.locfileid: "39349634"
---
# <a name="data-groups"></a>Gegevensgroepen
Gegevensgroepen zijn een eenvoudige manier om services te categoriseren binnen een [DLP-beleid](prevent-data-loss.md). DLP staat voor Data Loss Prevention, ofwel preventie van gegevensverlies. Deze twee groepen zijn beschikbaar: **Alleen zakelijke gegevens** en **Geen zakelijke gegevens toegestaan**. Organisaties kunnen zelf bepalen welke services ze in een van deze gegevensgroepen willen plaatsen. Een goede manier om services te categoriseren is door ze in groepen te plaatsen op basis van de impact op de organisatie. Standaard worden alle services opgenomen in de groep **Geen zakelijke gegevens toegestaan**. U beheert de services in een gegevensgroep wanneer u in het beheercentrum de eigenschappen van een DLP-beleid maakt of wijzigt.

## <a name="how-data-is-shared-between-data-groups"></a>Hoe gegevens worden gedeeld tussen gegevensgroepen
Gegevens kunnen niet worden gedeeld tussen services die zich in verschillende groepen bevinden. Als u bijvoorbeeld SharePoint en Salesforce in de groep **Alleen zakelijke gegevens** plaatst en Facebook en Twitter in de groep **Geen zakelijke gegevens toegestaan**, kunt u niet een PowerApp maken die gegevens verplaatst tussen SharePoint en Facebook. Hoewel gegevens niet kunnen worden gedeeld tussen services in verschillende groepen, kunt u gegevens wel delen tussen de services binnen een specifieke groep. Laten we even teruggaan naar het vorige voorbeeld. Aangezien SharePoint en Salesforce in dezelfde gegevensgroep zijn geplaatst, kunnen PowerApps die uw eindgebruikers maken gegevens uitwisselen tussen SharePoint en Salesforce. Samengevat komt het er dus op neer dat services in een specifieke groep gegevens kunnen delen, terwijl dit niet mogelijk is tussen services in verschillende groepen.

Daarnaast moet één gegevensgroep worden aangemerkt als de *standaard* groep. In eerste instantie is de groep **Geen zakelijke gegevens toegestaan** de *standaard* groep en bevinden alle services zich in deze gegevensgroep. Een beheerder kan de gegevensgroep **Alleen zakelijke gegevens** instellen als de standaardgegevensgroep. 

> [!NOTE]
> Nieuwe services die worden toegevoegd aan PowerApps, worden in de *standaard*groep geplaatst. Om die reden is het raadzaam om de groep **Geen zakelijke gegevens toegestaan** de standaardgroep te laten en services handmatig toe te voegen aan de groep **Alleen zakelijke gegevens** nadat is geanalyseerd wat de gevolgen zijn voor de organisatie als zakelijke gegevens mogen worden gedeeld met de nieuwe service.

## <a name="add-services-to-a-data-group"></a>Services toevoegen aan een gegevensgroep
In dit voorbeeld worden SharePoint en Salesforce toegevoegd aan de gegevensgroep **Alleen zakelijke gegevens** van een DLP-beleid.

1. Selecteer de koppeling **+ Toevoegen** in het groepsvak **Alleen zakelijke gegevens** van een DLP-beleid:    
   ![Afbeelding van koppeling Toevoegen](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Selecteer SharePoint en Salesforce en selecteer vervolgens **Services toevoegen** om beide services toe te voegen aan de groep Alleen zakelijke gegevens:    
   ![Afbeelding van Services toevoegen](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Selecteer **Beleid opslaan** in het menu bovenaan:  
   ![Beleid opslaan](./media/introduction-to-data-groups/add-to-data-group-4.png)
4. U ziet dat nu zowel SharePoint als Salesforce wordt weergegeven in de groep Alleen zakelijke gegevens:  
   ![Bijgewerkte groep Alleen zakelijke gegevens](./media/introduction-to-data-groups/add-to-data-group-3.png)   

In dit voorbeeld hebben we SharePoint en Salesforce toegevoegd aan de gegevensgroep **Alleen zakelijke gegevens** van een DLP-beleid. Als iemand die deel uitmaakt van de omgeving met dit DLP-beleid een app maakt die gegevens deelt tussen SharePoint of Salesforce en een service in de gegevensgroep **Geen zakelijke gegevens toegestaan**, wordt de app niet uitgevoerd.

## <a name="remove-services-from-a-data-group"></a>Services verwijderen uit een gegevensgroep
Aangezien alle services moeten worden ondergebracht in een van beide gegevensgroepen, kunt u een service alleen verwijderen uit een groep door de service over te brengen naar de andere groep en het beleid opnieuw op te slaan.  

## <a name="change-the-default-data-group"></a>De standaardgegevensgroep wijzigen
In dit voorbeeld wijzigen we de standaardgegevensgroep van **Geen zakelijke gegevens toegestaan** in **Alleen zakelijke gegevens**.  

> [!IMPORTANT]
> Nieuwe services die worden toegevoegd aan PowerApps, worden in de *standaard*groep geplaatst. Om die reden is het raadzaam om de groep **Geen zakelijke gegevens toegestaan** de standaardgroep te laten en services handmatig toe te voegen aan de groep **Alleen zakelijke gegevens**.

1. Selecteer de drie puntjes **...**  in de rechterbovenhoek van de gegevensgroep die u wilt instellen als de standaardgegevensgroep:    
   ![Een andere standaardgegevensgroep instellen](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Selecteer **Instellen als standaardgroep**:  
   ![Een andere standaardgegevensgroep instellen](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Selecteer **Beleid opslaan** in het menu bovenaan:  
   ![Een andere standaardgegevensgroep instellen](./media/introduction-to-data-groups/add-to-data-group-4.png)
4. U ziet dat de gegevensgroep nu is ingesteld als de standaardgegevensgroep:  
   ![een andere standaardgegevensgroep instellen](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Volgende stappen
* [Learn more about data loss prevention (DLP) policies](prevent-data-loss.md) (Meer informatie over DLP-beleid)
* [Meer informatie over omgevingen](environments-overview.md)
* [Meer informatie over Microsoft PowerApps](../maker/canvas-apps/getting-started.md)
