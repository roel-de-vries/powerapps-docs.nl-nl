---
title: Zelfstudie voor het maken van een aangepaste entiteit die onderdelen met PowerApps heeft | Microsoft Docs
description: Zelfstudie met stapsgewijze instructies voor het maken en configureren van een entiteit om een PowerApps-app te gebruiken.
author: Mattp123
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: tutorial
ms.date: 06/22/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-a-custom-entity-that-has-components-in-powerapps"></a>Zelfstudie: een aangepaste entiteit maken die onderdelen heeft in PowerApps

Met PowerApps kunt u uw app aanpassen voor een betere aansluiting met de branche van uw organisatie, nomenclatuur en unieke bedrijfsprocessen. Ontwikkeling van de PowerApps-app omvat het toevoegen van gebruiksklare standaardentiteiten of het maken van aangepaste entiteiten. Met een entiteit worden de gegevens gedefinieeerd die u in de vorm van records wilt bijhouden. Dit omvat meestal eigenschappen zoals bedrijfsnaam, locatie, producten, e-mail en telefoon. 

In deze zelfstudie maakt u een entiteit en vervolgens voegt u belangrijke onderdelen toe of past u deze aan. Deze onderdelen zijn bijvoorbeeld velden, weergaven, relaties en formulieren. U leert het volgende:

- Een aangepaste entiteit maken
- Aangepaste velden aan uw entiteit toevoegen
- Een entiteitsrelatie toevoegen
- Een weergave aanpassen 
- Een formulier aanpassen

In de zelfstudie wordt het bedrijf Contoso gevolgd, een bedrijf dat handelt in producten voor de cosmetische verzorging van honden en katten. Contoso heeft een app nodig voor het bijhouden van klanten en huisdieren die kan worden gebruikt door medewerkers op allerlei apparaten.

## <a name="prerequisites"></a>Vereisten

Meld u aan bij [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Als u nog geen PowerApps-account hebt, selecteert u de koppeling **Gratis aan de slag** van [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="create-a-custom-entity"></a>Een aangepaste entiteit maken

1. Vouw in het linkernavigatiedeelvenster **Gegevens** uit, selecteer **Entiteiten** en selecteer vervolgens **Nieuwe entiteit**.
    > [!div class="mx-imgBorder"] 
    > ![Nieuwe entiteit](media/create-custom-entity/create-new-entity.png)
2. In het rechterdeelvenster voert u de volgende waarden in, en selecteert u daarna **Volgende**.
  - **Weergavenaam**: *Huisdier* 
  - **Beschrijving**: *Aangepaste entiteit om services voor huisdieren bij te houden*
3. Selecteer **Entiteit opslaan**.

## <a name="add-and-customize-fields"></a>Velden toevoegen en aanpassen
 
1. In de lijst met entiteiten selecteert u de entiteit **Huisdier** die in de vorige sectie is gemaakt.
2. Selecteer op het tabblad **Velden** het veld **Huisdier**.
3. Breng in het rechterdeelvenster de volgende wijzigingen aan in het veld **Weergavenaam**: 
  - Wijzig de **Weergavenaam** van **Huisdier** in *Naam huisdier*
  - Selecteer **Kan worden doorzocht**.  
  
    > [!div class="mx-imgBorder"] 
    > ![Primair veld wijzigen](media/create-custom-entity/primary-field.png)
3. Selecteer **Gereed**.
4. Selecteer op het tabblad **Velden** **Veld toevoegen** op de werkbalk van de entiteitontwerper. Voer in het deelvenster **Veldeigenschappen** de volgende waarden en de opties in of selecteer deze.
  - **Weergavenaam**. *Soort*
  - **Gegevenstype**. *Optieset*
  - **Optieset**. *Nieuwe optieset*
5. De optieset maken

  a. Selecteer **Nieuw item toevoegen**. 
  
  b. Vervang **Nieuwe optie** met *Hond*. 
   
  c. Selecteer **Nieuw item toevoegen**. 
    
  d.  Vervang **Nieuwe optie** met *Kat*. 
    
  e. Selecteer **Opslaan**. 

  > [!div class="mx-imgBorder"] 
  > ![Nieuwe optieset](media/create-custom-entity/optionset-add-items.png)

6. Selecteer **Kan worden doorzocht** en selecteer vervolgens **Gereed**.

7. Selecteer **Veld toevoegen** op de werkbalk van de entiteitontwerper. Voer in het deelvenster **Veldeigenschappen** de volgende waarden in of selecteer deze en selecteer vervolgens **Gereed**.
  - **Weergavenaam**. *Ras*
  - **Gegevenstype**. *Tekst*
  - **Kan worden doorzocht**. *Ja*

8. Selecteer **Veld toevoegen** op de werkbalk van de entiteitontwerper. 

9. Voer in het deelvenster **Veldeigenschappen** de volgende waarden in of selecteer deze en selecteer vervolgens **Gereed**. 
  - **Weergavenaam**. *Afspraakdatum*
  - **Gegevenstype**. *Datum en tijd*

10. Selecteer **Entiteit opslaan**.

## <a name="add-a-relationship"></a>Een relatie toevoegen

1. Selecteer het tabblad **Relaties** en selecteer **Relatie toevoegen** op de werkbalk van de entiteitontwerper. Selecteer vervolgens **Veel-op-één**. 
2. Selecteer in het rechterdeelvenster in de lijst **Gerelateerd** de optie **Account**.
3. Selecteer **Gereed**.
4. Selecteer **Entiteit opslaan**.

  Als u een veel-op-één relatie toevoegt, wordt het veld **Account** met het gegevenstype automatisch **Opzoeken** automatisch toegevoegd aan uw lijst met velden op het tabblad **Velden**.
  > [!div class="mx-imgBorder"]
  > ![Opzoekveld Account](media/create-custom-entity/account-lookup-field.png)

## <a name="customize-a-view"></a>Een weergave aanpassen

1. Selecteer het tabblad **Weergaven** en selecteer vervolgens de weergave **Actieve huisdieren**. Als u de weergave **Actieve huisdieren** niet ziet, selecteert u **Filter verwijderen**.
2. Selecteer in de weergaveontwerper **Kolommen toevoegen**, selecteer de volgende kolommen en selecteer vervolgens **OK**
  - Account
  - Afspraakdatum 
  - Ras 
  - Soort
3. Selecteer de kolom **Gemaakt op**, selecteer **Verwijderen** en selecteer vervolgens **OK** om de kolomverwijdering te bevestigen.
4. Als u de kolommen wilt rangschikken, selecteert u de kolom die u wilt verplaatsen en gebruikt u de pijlknoppen < - en - > totdat uw weergave er als volgt uitziet.
    > [!div class="mx-imgBorder"] 
    > ![Weergave Actieve huisdieren](media/create-custom-entity/active-pets-view.png)
5. Selecteer **Opslaan en sluiten** op de werkbalk van de weergaveontwerper.  

## <a name="model-driven-apps-only-customize-the-main-form"></a>Alleen modelgestuurde apps: pas het hoofdformulier aan

Sla deze stap over als u alleen de entiteit Huisdier in een canvasapp wilt gebruiken. 

1. Selecteerin het linkernavigatiedeelvenster van PowerApps **Modelgestuurd**.
2. Vouw in het linkernavigatiedeelvenster **Gegevens** uit, selecteer **Entiteiten** en selecteer vervolgens **Huisdier**.
3. Selecteer het tabblad **Formulieren** en vervolgens **Informatie** naast het formuliertype **Hoofd** om de formuliereneditor te openen.
    > [!div class="mx-imgBorder"] 
    > ![Hoofdformulier bewerken](media/create-custom-entity/main-form-edit.png)
4. Gebruik in de formuliereneditor slepen en neerzetten voor de velden **Soort**, **Ras**, **Afspraakdatum** en **Account**, die zich bevinden in het deelvenster Veldverkenner van de sectie Algemeen van het formuliercanvas, totdat het formulier er als volgt uitziet.
    > [!div class="mx-imgBorder"] 
    > ![Velden selecteren voor hoofdformulier](media/create-custom-entity/main-form-edit2.png) 
5. Selecteer **Opslaan**.
6. Selecteer **Publiceren**.
7. Selecteer **Opslaan en sluiten** om de formulierontwerper te sluiten.

## <a name="add-the-custom-entity-to-an-app"></a>De aangepaste entiteit aan een app toevoegen

Nu is uw entiteit gereed om te worden gebruikt voor het maken van een canvasapp of een modelgestuurde app. 

## <a name="next-steps"></a>Volgende stappen

In deze zelfstudie hebt u geleerd hoe u een entiteit maakt die kan worden gebruikt om een handige app te maken. 
- Als u wilt leren hoe u een modelgestuurde app maakt, raadpleegt u [Uw eerste modelgestuurde app maken](../model-driven-apps/build-first-model-driven-app.md).
- Als u wilt leren hoe u een canvasapp maakt, raadpleegt u [Een compleet nieuwe app maken](../canvas-apps/get-started-create-from-blank.md).
