---
title: Snelstartgids om uw eerste modelgestuurde app te bouwen met PowerApps | Microsoft Docs
description: Meer informatie over hoe u een eenvoudige modelgestuurde app bouwt
documentationcenter: ''
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 04/18/2018
ms.author: matp
ms.openlocfilehash: 3d7aa26696adb187906c9c793c546abd1b97764f
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2018
ms.locfileid: "34583481"
---
# <a name="quickstart-build-your-first-model-driven-app-from-scratch"></a>Snelstartgids: Uw eerste modelgestuurde app bouwen
Het ontwerp van modelgestuurde apps is een componentgerichte methode voor het ontwikkelen van apps. In deze snelstartgids maakt u op een vereenvoudigde manier een modelgestuurde app met behulp van een van de standaardentiteiten die in uw [!INCLUDE [powerapps](../../includes/powerapps.md)]-omgeving beschikbaar is. 

## <a name="sign-in-to-powerapps"></a>Meld u aan bij PowerApps
Meld u aan bij [PowerApps](https://web.powerapps.com/). Als u nog geen [!INCLUDE [powerapps](../../includes/powerapps.md)] account hebt, selecteert u de koppeling **Gratis aan de slag**. 

## <a name="create-your-model-driven-app"></a>Uw modelgestuurde app maken

1.  Selecteer de gewenste omgeving of ga naar het [PowerApps-beheercentrum](https://admin.powerapps.com/) om een nieuwe te maken.
2.  Selecteer in het linkernavigatiedeelvenster **Modelgestuurd**. 

    ![Modelgestuurd](media/build-first-model-driven-app/choose-design-mode.png)

  > [!IMPORTANT]
  > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment).   

3. Selecteer **Apps** in het linkerdeelvenster en selecteer vervolgens **Een app maken**.

4.  Voer op de pagina **Een nieuwe app maken** de volgende gegevens in en selecteer vervolgens **Gereed**: 
  - **Naam**: voer een naam in voor de app, zoals *Mijneersteapp*. 
  - **Beschrijving**: typ een korte beschrijving van de app of wat deze doet, zoals *Dit is mijn eerste app*.
Zie [Een app maken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app#create-an-app) voor meer informatie over de andere eigenschappen van de app.
 
    ![Nieuwe-app-maken](media/build-first-model-driven-app/create-new-app.png)

## <a name="add-components-to-your-app"></a>Onderdelen toevoegen aan uw app
Vanaf de app-ontwerper voegt u onderdelen toe aan uw app.
1.  Selecteer de pijl **Open de Sitemapontwerper** om de sitemapontwerper te openen. 

    ![Nieuwe-sitemap-maken](media/build-first-model-driven-app/new-sitemap.png)

2.  Selecteer **Nieuw subgebied** in de sitemapontwerper, selecteer in het rechterdeelvenster het tabblad **Eigenschappen** en selecteer dan de volgende eigenschappen.
  - **Type**: entiteit
  - **Entiteit**: account

    ![Onderdelen toevoegen aan uw sitemap](media/build-first-model-driven-app/sitemap.png)

3.  Selecteer **Opslaan en sluiten**.
4.  Selecteer **Formulieren** in het canvas van de app-ontwerper en selecteer vervolgens in het rechterdeelvenster onder de groep **Hoofdformulieren** het formulier **Account**.

    ![Account hoofdformulier](media/build-first-model-driven-app/main-form.png)

5.  Selecteer **Weergaven** in het canvas van de app-ontwerper en selecteer vervolgens de weergaven **Actieve accounts**, **Alle accounts** en **Mijn actieve accounts**.

    ![Accountweergaven](media/build-first-model-driven-app/views.png)

6. Selecteer **Grafieken** in het canvas van de app-ontwerper en selecteer vervolgens de grafiek **Accounts op branche**.
7. Selecteer in de werkbalk van de app-ontwerper **Opslaan en sluiten**.

    ![De werkbalk opslaan van de app-ontwerper](media/build-first-model-driven-app/app-designer-toolbar.png)
 
<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## <a name="publish-your-app"></a>Uw app publiceren
Selecteer in de werkbalk van de app-ontwerper **Publiceren**.

Nadat u de app hebt gepubliceerd, kunt u deze uitvoeren of met anderen delen.

![Eenvoudige accountentiteit-app](media/build-first-model-driven-app/accounts-quickstart-app.png)

## <a name="next-steps"></a>Volgende stappen
In deze snelstartgids bouwt u een eenvoudige modelgestuurde app. Om te zien hoe uw app eruit ziet wanneer u deze uitvoert, raadpleegt u [Snelstartgids: Een modelgestuurde app uitvoeren op een mobiel apparaat](../../user/run-app-client-model-driven.md).
Voor meer informatie over hoe u uw app deelt, gaat u naar de zelfstudie [Een modelgestuurde app delen](share-model-driven-app.md) waarin u leest hoe u een modelgestuurde app deelt.
