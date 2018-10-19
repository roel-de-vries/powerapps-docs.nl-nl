---
title: Uw eerste nieuwe modelgestuurde app maken met PowerApps | Microsoft Docs
description: Leer hoe u een eenvoudige modelgestuurde app maakt
documentationcenter: ''
author: Mattp123
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 04/18/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="build-your-first-model-driven-app-from-scratch"></a>Uw eerste nieuwe modelgestuurde app maken
Het ontwerp van modelgestuurde apps is een onderdeelgerichte methode voor het ontwikkelen van apps. In dit onderwerp maakt u op een vereenvoudigde manier een modelgestuurde app met behulp van een van de standaardentiteiten die in uw PowerApps-omgeving beschikbaar is.

> [!TIP]
> Als u alles wilt weten over het maken van modelgestuurde apps, begint u hier: [Inzicht krijgen in onderdelen van modelgestuurde apps](model-driven-app-components.md). 

## <a name="sign-in-to-powerapps"></a>Aanmelden bij PowerApps
Meld u aan bij [PowerApps](https://web.powerapps.com/). Als u nog geen [!INCLUDE [powerapps](../../includes/powerapps.md)]-account hebt, selecteert u de koppeling **Gratis aan de slag**. 

## <a name="create-your-model-driven-app"></a>Uw modelgestuurde app maken

1.  Selecteer de gewenste omgeving of ga naar het [PowerApps-beheercentrum](https://admin.powerapps.com/) om een nieuwe te maken..
2.  Selecteer in het linkernavigatiedeelvenster **Modelgestuurd**. 

    ![Modelgestuurd](media/build-first-model-driven-app/choose-design-mode.png)

  > [!IMPORTANT]
  > Als de **modelgestuurde** ontwerpmodus niet beschikbaar is, moet u mogelijk [een omgeving maken](https://docs.microsoft.com/powerapps/administrator/create-environment).   

3. Selecteer **Apps** in het linkerdeelvenster en selecteer vervolgens **Een app maken**.

4.  Voer op de pagina **Een nieuwe app** maken de volgende gegevens in en selecteer vervolgens **Gereed**: 
  - **Naam**: geef een naam op voor de app, bijvoorbeeld *Mijneersteapp*. 
  - **Beschrijving**: typ een korte beschrijving van de app of wat deze doet, zoals *Dit is mijn eerste app*.
Zie [Een app maken](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-app#create-an-app) voor meer informatie over de andere eigenschappen van de app.
 
    ![Nieuwe app maken](media/build-first-model-driven-app/create-new-app.png)

## <a name="add-components-to-your-app"></a>Onderdelen toevoegen aan uw app
Via de appontwerper kunt u onderdelen aan uw app toevoegen.
1.  Selecteer de pijl bij **Siteoverzichtontwerper openen** om de siteoverzichtontwerper te openen. 

    ![Nieuw siteoverzicht maken](media/build-first-model-driven-app/new-sitemap.png)

2.  Selecteer **Nieuw subgebied** in de siteoverzichtontwerper, selecteer in het rechterdeelvenster het tabblad **Eigenschappen** en selecteer de volgende eigenschappen.
  - **Type**: entiteit
  - **Entiteit**: account

    ![Onderdelen toevoegen aan siteoverzicht](media/build-first-model-driven-app/sitemap.png)

3.  Selecteer **Opslaan en sluiten**.
4.  Selecteer **Formulieren** in het canvas van de appontwerper en selecteer vervolgens in het rechterdeelvenster onder de groep **Hoofdformulieren** het formulier **Account**.

    ![Hoofdformulier Account](media/build-first-model-driven-app/main-form.png)

5.  Selecteer **Weergaven** in het canvas van de appontwerper en selecteer vervolgens de weergaven **Actieve accounts**, **Alle accounts** en **Mijn actieve accounts**.

    ![Accountweergaven](media/build-first-model-driven-app/views.png)

6. Selecteer **Grafieken** in het canvas van de appontwerper en selecteer vervolgens de grafiek **Accounts per branche**.
7. Selecteer **Opslaan** op de werkbalk van de appontwerper.

    ![Opslaan op werkbalk van appontwerper](media/build-first-model-driven-app/app-designer-toolbar.png)
 
<!-- ##  Validate your app
This step checks for component dependencies that are required for the app to work, but haven't yet been added to the app. 

1. On the app designer canvas, select the component that indicates a dependency, such as the **Forms** component. Then, on the right-pane select the **Required** tab, expand **Entity Dependencies** and then select all required dependencies. 

    ![Add dependencies](media/build-first-model-driven-app/resolve-dependencies.png)

2. Select **Add Dependencies**.
3. On the app designer toolbar, select **Save**.  -->

## <a name="publish-your-app"></a>Uw app publiceren
Selecteer **Publiceren** op de werkbalk van de appontwerper.

Nadat u de app hebt gepubliceerd, kunt u deze uitvoeren of met anderen delen.

![Eenvoudige app voor entiteit Account](media/build-first-model-driven-app/accounts-quickstart-app.png)

## <a name="next-steps"></a>Volgende stappen
In dit onderwerp bouwt u een eenvoudige modelgestuurde app. 
- Om te zien hoe uw app eruit ziet wanneer u deze uitvoert, raadpleegt u [Een modelgestuurde app uitvoeren op een mobiel apparaat](../../user/run-app-client-model-driven.md).
- Zie [Een modelgestuurde app delen](share-model-driven-app.md) om te leren hoe u uw app deelt.
- Zie [Inzicht krijgen in onderdelen van modelgestuurde apps](model-driven-app-components.md) als u aan de slag wilt gaan met en alles wilt weten over het maken van modelgestuurde apps.
