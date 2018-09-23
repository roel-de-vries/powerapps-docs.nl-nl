---
title: Modelgestuurde voorbeeld-apps
description: Krijg inzicht in het ophalen, aanpassen en verwijderen van modelgestuurde voorbeeld-apps.
documentationcenter: na
author: caburk
manager: kvivek
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/08/2018
ms.author: caburk
ms.openlocfilehash: 0b34a32281fb4f64bc918de81b3920edf5a7000b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39664422"
---
# <a name="model-driven-sample-apps"></a>Modelgestuurde voorbeeld-apps

Gebruik in [powerapps.com](https://powerapps.com) een voorbeeld-app om ontwerpmogelijkheden te verkennen en concepten te ontdekken die u kunt toepassen tijdens het ontwikkelen van uw eigen apps. Elke voorbeeld-app werkt met fictieve gegevens om een praktijkscenario te laten zien. 

Zorg ervoor dat u de documentatie leest die specifiek is voor elke voorbeeld-app voor meer informatie. 

![Voorbeeld-app inzamelingsactie](media/overview-model-driven-samples/fundraiser-app1.png)


## <a name="get-sample-apps"></a>Voorbeeld-apps ophalen

Als u modelgestuurde voorbeeld-apps wilt afspelen of bewerken, moeten de apps eerst worden ingericht in een Common Data Service-database. Maak eerst een proefomgeving en -database en zorg ervoor dat u **Voorbeeld-apps en gegevens opnemen** inschakelt.

![Een database maken](media/overview-model-driven-samples/create-database1.png)


> [!IMPORTANT]
> Met deze optie worden alle beschikbare voorbeeld-apps in uw database geïnstalleerd. Voorbeeld-apps zijn voor onderwijs- en demonstratiedoeleinden. Het wordt niet aanbevolen deze in productiedatabases te installeren. 

## <a name="customize-a-sample-app"></a>Een voorbeeld-app aanpassen

1. Aanmelden bij [powerapps.com](https://powerapps.com) en kies **Modelgestuurd** als ontwerpmodus. 

    ![De ontwerpmodus kiezen](media/overview-model-driven-samples/choose-design-mode.png)

2. Beweeg vanaf de startpagina de muisaanwijzer over de voorbeeld-app en klik op **Aanpassen**.
3. De app-ontwerpfunctie wordt geopend waarin u meerdere opties voor het aanpassen van de app krijgt. 
4. Klik voor extra functies voor aanpassen op **Geavanceerd** in de linkernavigatiebalk in de portal.

## <a name="remove-sample-apps-and-data"></a>Voorbeeld-apps en gegevens verwijderen 
- Voor het verwijderen van een voorbeeld-app moet de overeenkomstige [beheerde oplossing](https://docs.microsoft.com/dynamics365/customer-engagement/developer/uninstall-delete-solution) worden verwijderd. 
- Bij het verwijderen van de oplossing worden tevens voorbeeldgegevens verwijderd die specifiek zijn voor de aangepaste entiteiten van de app.
- Als er aanpassingen zijn aangebracht in de voorbeeld-app, kunnen er [afhankelijkheden](https://docs.microsoft.com/dynamics365/customer-engagement/developer/dependency-tracking-solution-components) zijn die moeten worden verwijderd voordat u de oplossing verwijdert.

### <a name="steps"></a>Stappen
1. Meld u aan bij de [PowerApps-beheerportal](https://admin.powerapps.com).

2. Selecteer een omgeving.

3. Klik op **Dynamics 365-beheercentrum** 

    ![Dynamics 365-beheercentrum](media/overview-model-driven-samples/admin-center.png)

4. Selecteer uw Database in de lijst en klik op **OPENEN**.

    ![Database selecteren](media/overview-model-driven-samples/select-database.png)

5. Navigeer naar **Instellingen/Oplossingen**.

6. Selecteer de oplossing voor de app die moet worden verwijderd en klik op **Verwijderen**.

    ![Oplossing verwijderen](media/overview-model-driven-samples/delete-solution.png)

*U kunt ook naar de lijst met oplossingen navigeren door te klikken op **Geavanceerd** in de portal van de maker en alles in de URL verwijderen na .dynamics.com/*

> [!IMPORTANT]
> Verwijder geen andere systeemoplossingen, tenzij u van het effect op de hoogte bent.

## <a name="install-or-uninstall-sample-data"></a>Voorbeeldgegevens installeren of verwijderen
1. Volg de stappen 1 tot en met 4 hierboven.
2. Navigeer naar **Instellingen/Gegevensbeheer/Voorbeeldgegevens**.
3. Als er voorbeeldgegevens zijn geïnstalleerd, is de optie voor verwijderen beschikbaar. Anders is de optie voor installeren beschikbaar. 

    ![voorbeeldgegevens verwijderen](media/overview-model-driven-samples/remove-sample-data.png)




