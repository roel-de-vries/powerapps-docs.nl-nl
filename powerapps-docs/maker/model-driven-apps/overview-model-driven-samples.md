---
title: Modelgestuurde voorbeeldapps
description: 'Leer hoe u modelgestuurde voorbeeldapps downloadt, aanpast en verwijdert.'
documentationcenter: na
author: caburk
manager: kvivek
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/08/2018
ms.author: caburk
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="model-driven-sample-apps"></a>Modelgestuurde voorbeeldapps

Gebruik in [powerapps.com](https://powerapps.com) een voorbeeldapp om ontwerpmogelijkheden te verkennen en concepten te ontdekken die u kunt toepassen tijdens het ontwikkelen van uw eigen apps. Elke voorbeeldapp werkt met fictieve gegevens om een praktijkscenario te laten zien. 

Lees de specifieke documentatie voor elke voorbeeldapp voor meer informatie. 

![Voorbeeldapp inzamelingsactie](media/overview-model-driven-samples/fundraiser-app1.png)


## <a name="get-sample-apps"></a>Voorbeeldapps downloaden

Als u modelgestuurde voorbeeldapps wilt afspelen of bewerken, moeten de apps eerst worden ingericht in een Common Data Service-database. Maak eerst een proefomgeving en -database en schakel **Voorbeeldapps en gegevens opnemen** in.

![Database maken](media/overview-model-driven-samples/create-database1.png)


> [!IMPORTANT]
> Met deze optie worden alle beschikbare voorbeeldapps in de database geïnstalleerd. Voorbeeldapps zijn voor onderwijs- en demonstratiedoeleinden. Het wordt niet aanbevolen deze in productiedatabases te installeren. 

## <a name="customize-a-sample-app"></a>Een voorbeeldapp aanpassen

1. Meld u aan bij [powerapps.com](https://powerapps.com) en kies **Modelgestuurd** voor de ontwerpmodus. 

    ![Ontwerpmodus kiezen](media/overview-model-driven-samples/choose-design-mode.png)

2. Beweeg vanaf de startpagina de muisaanwijzer over de voorbeeldapp en klik op **Aanpassen**.
3. De appontwerpfunctie wordt geopend waarin u meerdere opties voor het aanpassen van de app krijgt. 
4. Klik voor extra functies voor aanpassen op **Geavanceerd** in de linkernavigatiebalk in de portal.

## <a name="remove-sample-apps-and-data"></a>Voorbeeldapps en -gegevens verwijderen 
- Als u een voorbeeldapp wilt verwijderen, moet ook de bijbehorende [beheerde oplossing](https://docs.microsoft.com/dynamics365/customer-engagement/developer/uninstall-delete-solution) worden verwijderd. 
- Bij het verwijderen van de oplossing worden tevens de specifieke voorbeeldgegevens voor de aangepaste entiteiten van de app verwijderd.
- Als er aanpassingen zijn aangebracht in de voorbeeldapp, kunnen er [afhankelijkheden](https://docs.microsoft.com/dynamics365/customer-engagement/developer/dependency-tracking-solution-components) zijn die moeten worden verwijderd voordat u de oplossing verwijdert.

### <a name="steps"></a>Stappen
1. Meld u aan bij de [PowerApps-beheerportal](https://admin.powerapps.com).

2. Selecteer een omgeving.

3. Klik op **Dynamics 365 Administration Center** 

    ![Dynamics 365-beheercentrum](media/overview-model-driven-samples/admin-center.png)

4. Selecteer de database in de lijst en klik op **OPENEN**.

    ![Database selecteren](media/overview-model-driven-samples/select-database.png)

5. Navigeer naar **Instellingen/Oplossingen**.

6. Selecteer de oplossing voor de app die moet worden verwijderd en klik op **verwijderen**.

    ![Oplossing verwijderen](media/overview-model-driven-samples/delete-solution.png)

*U kunt ook naar de lijst met oplossingen navigeren door te klikken op **Geavanceerd** in de portal van de maker en alles in de URL na .dynamics.com/ te verwijderen*

> [!IMPORTANT]
> Verwijder geen andere systeemoplossingen, tenzij u van het effect op de hoogte bent.

## <a name="install-or-uninstall-sample-data"></a>Voorbeeldgegevens installeren of verwijderen
1. Voer stap 1-4 hierboven uit.
2. Navigeer naar **Instellingen/Gegevensbeheer/Voorbeeldgegevens**.
3. Als er voorbeeldgegevens zijn geïnstalleerd, is de optie voor verwijderen beschikbaar. Anders is de optie voor installeren beschikbaar. 

    ![voorbeeldgegevens verwijderen](media/overview-model-driven-samples/remove-sample-data.png)




