---
title: Zelfstudie voor het maken van een aangepaste entiteit voorzien van componenten met PowerApps | Microsoft Docs
description: Zelfstudie met stapsgewijze instructies voor het maken en configureren van een entiteit voor gebruik met een PowerApps-app.
services: ''
suite: powerapps
documentationcenter: na
author: Mattp123
manager: bycho
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: 3fd8b262849fb1f6bf2a7ff70d9d9af8b082efac
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="tutorial-create-a-custom-entity-that-has-components-in-powerapps"></a>Zelfstudie: Een aangepaste entiteit met componenten in PowerApps maken

Met [!INCLUDE [powerapps](../../includes/powerapps.md)] kunt u uw app naadloos laten aansluiten op de bedrijfstak, naamgeving en unieke zakelijke processen van uw organisatie. Ontwikkeling van [!INCLUDE [powerapps](../../includes/powerapps.md)]-apps bestaat onder meer uit het toevoegen van standaard kant-en-klare entiteiten of het maken van aangepaste entiteiten. Een entiteit definieert de gegevens die u wilt bijhouden in de vorm van records, waaronder doorgaans eigenschappen zoals de bedrijfsnaam, locatie, producten, e-mailadres en telefoonnummer. 

In deze zelfstudie maakt u een entiteit en voegt u vervolgens belangrijke onderdelen zoals velden, relaties, weergaven en formulieren toe of past u deze aan. U leert het volgende:

- Een aangepaste entiteit maken
- Aangepaste velden toevoegen aan uw entiteit
- Een entiteitsrelatie toevoegen
- Een weergave aanpassen 
- Een formulier aanpassen

> [!IMPORTANT]
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]

De zelfstudie volgt het bedrijf Contoso: een bedrijf voor de cosmetische verzorging van honden en katten. Contoso heeft een app nodig voor het bijhouden van klanten en huisdieren die kan worden gebruikt door werknemers op een verscheidenheid aan apparaten.

## <a name="prerequisites"></a>Vereisten

Meld u aan bij [PowerApps](https://powerapps.microsoft.com/). Als u nog geen [!INCLUDE [powerapps](../../includes/powerapps.md)]-account hebt, selecteert u de koppeling **Gratis aan de slag** van [PowerApps.com](https://web.powerapps.com).

## <a name="create-a-custom-entity"></a>Een aangepaste entiteit maken

1. Selecteer in het linkernavigatiedeelvenster onder **Common Data Service** de optie **Entiteiten** en selecteer vervolgens **Nieuwe entiteit**.
    ![Nieuwe entiteit](media/create-custom-entity/create-new-entity.png)
2. Geef de volgende waarden op in het rechterdeelvenster en selecteer vervolgens **Volgende**.
  - **Weergavenaam**: *Huisdier* 
  - **Beschrijving**: *Aangepaste entiteit voor het bijhouden van huisdierservices*
3. Selecteer **Entiteit opslaan**.

## <a name="add-and-customize-fields"></a>Velden toevoegen en aanpassen

1. Selecteer op het tabblad **Velden** het veld **Primaire naam**.
2. Breng in het rechterdeelvenster de volgende wijzigingen aan in het veld **Primaire naam**: 
  - Wijzig de **Weergavenaam** van **Primaire naam** in *Huisdiernaam*
  - Selecteer **Niet doorzoekbaar**

    ![Het primaire veld wijzigen](media/create-custom-entity/primary-field.png)
3. Selecteer **Gereed**.
4. Selecteer op de werkbalk van de entiteitsdesigner het veld **Toevoegen**. Geef in het deelvenster **Veldeigenschappen** de volgende waarden en opties op of selecteer deze.
  - **Weergavenaam**. *Soorten*
  - **Gegevenstype**. *Optieset*
  - **Optieset**. *Nieuw*
5. De optieset maken

  a. Selecteer **Nieuw item toevoegen**. 
  
  b. Vervang **Nieuwe optie** door *Hond*. 
   
  c. Selecteer **Nieuw item toevoegen**. 
    
  d.  Vervang **Nieuwe optie** door *Kat*. 
    
  e. Selecteer **Opslaan**. 

  ![Nieuwe optieset](media/create-custom-entity/optionset-add-items.png)

6. Selecteer **Doorzoekbaar** en selecteer vervolgens **Gereed**.

7. Selecteer in de werkbalk van de entiteitsdesigner het veld **Toevoegen**. Geef in het deelvenster **Veldeigenschappen** de volgende waarden op of selecteer deze, en selecteer daarna **Gereed**.
  - **Weergavenaam**. *Ras*
  - **Gegevenstype**. *Tekst*
  - **Doorzoekbaar**. *Ja*

8. Selecteer in de werkbalk van de entiteitsdesigner het veld **Toevoegen**. 

9. Geef in het deelvenster **Veldeigenschappen** de volgende waarden op of selecteer deze en selecteer daarna **Gereed**. 
  - **Weergavenaam**. *Afspraakdatum*
  - **Gegevenstype**. *Datum en tijd*

10. Selecteer **Entiteit opslaan**.

## <a name="add-a-relationship"></a>Een relatie toevoegen

1. Selecteer het tabblad **Relaties** en selecteer vervolgens op de werkbalk van de entiteitsdesigner **Relatie toevoegen**. 
2. Selecteer in de lijst **Gerelateerde entiteit** van het rechterdeelvenster **Account** en selecteer vervolgens **Gereed**.
3. Selecteer **Entiteit opslaan**.

U ziet dat wanneer u een relatie toevoegt, er automatisch een veld met het gegevenstype **Zoekopdracht** wordt toegevoegd aan de lijst met velden op het tabblad **Velden**. ![Opzoekveld voor accounts](media/create-custom-entity/account-lookup-field.png)

## <a name="customize-a-view"></a>Een weergave aanpassen

1. Selecteer het tabblad **Weergaven** en selecteer vervolgens de weergave **Actieve huisdieren**.
2. Selecteer in de weergaveontwerper **Kolommen toevoegen** de volgende kolommen en selecteer vervolgens **OK**.
  - Account
  - Afspraakdatum 
  - Ras 
  - Soorten
3. Selecteer de kolom **Gemaakt op**, selecteer **Verwijderen** en selecteer vervolgens **OK** om de verwijdering van de kolom te bevestigen.
4. Als u de kolommen wilt rangschikken, selecteert u de kolom die u wilt verplaatsen en gebruikt u vervolgens de pijltjesknoppen <- en -> totdat uw weergave er als volgt uitziet.
    ![Weergave Actieve huisdieren](media/create-custom-entity/active-pets-view.png)
5. Selecteer in de werkbalk weergaveontwerper **Opslaan en sluiten**.  
6. Selecteer **Entiteit opslaan**.

## <a name="model-driven-apps-only-customize-the-main-form"></a>Alleen voor modelgestuurde apps: het hoofdformulier aanpassen

Sla deze stap over als u de entiteit Huisdier alleen wilt gebruiken in een canvas-app. 

1. Selecteer in het linkernavigatiedeelvenster [!INCLUDE [powerapps](../../includes/powerapps.md)] **Modelgestuurd**.
2. Selecteer in het linkernavigatiedeelvenster **Geavanceerd**.
3. Selecteer **Entiteiten** in de linkernavigatiebalk van het venster van de oplossing, vouw **Huisdier** uit en selecteer vervolgens **Formulieren**.
4. Selecteer **Informatie** naast het formuliertype **Hoofd** om de formuliereneditor te openen.
    ![Hoofdformulier bewerken](media/create-custom-entity/main-form-edit.png)
5. Sleep op de formuliereneditor de velden **Soorten**, **Ras**, **Afspraakdatum** en **Account** die zich in het deelvenster Veldverkenner bevinden en zet deze in de sectie Algemeen van het formuliercanvas, totdat het formulier er als volgt uitziet.
    ![Velden selecteren voor het hoofdformulier](media/create-custom-entity/main-form-edit2.png) 
6. Selecteer **Opslaan en sluiten**.
7. Selecteer in het venster van de oplossing **Alle aanpassingen publiceren**.
    ![Alle aanpassingen publiceren](media/create-custom-entity/publish-all-customizations.png)

## <a name="add-the-custom-entity-to-an-app"></a>De aangepaste entiteit toevoegen aan een app

De entiteit is nu gereed om te worden gebruikt voor het bouwen van een canvas-app of een modelgestuurde app. 

## <a name="next-steps"></a>Volgende stappen

In deze zelfstudie hebt u geleerd hoe u een entiteit kunt maken die kan worden gebruikt voor het maken van een nuttige app. Zie voor meer informatie over het maken van een canvas-app [Een volledig nieuwe app maken](../canvas-apps/get-started-create-from-blank.md).
