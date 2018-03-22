---
title: Start een stroom in een app | Microsoft Docs
description: Maak een stroom die een of meer taken uitvoert wanneer een gebeurtenis plaatsvindt in een app, zoals wanneer een gebruiker een knop selecteert.
services: ''
suite: powerapps
documentationcenter: ''
author: stepsic-microsoft-com
manager: anneta
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/05/2017
ms.author: sharik
ms.openlocfilehash: 378394fe0c42d0418a62974c26b217ab473d40ed
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="start-a-flow-in-an-app"></a>Start een stroom in een app
U kunt Microsoft Flow gebruiken om logica te maken die een of meer taken uitvoert wanneer er een gebeurtenis optreedt in een app. U kunt bijvoorbeeld een knop zo configureren dat, wanneer een gebruiker deze selecteert, er een item wordt gemaakt in een SharePoint-lijst, een e-mailbericht of vergaderverzoek wordt verzonden, een bestand wordt toegevoegd aan de cloud of zelfs al deze dingen. U kunt elk besturingselement in de app configureren om de stroom te starten, die zelfs blijft lopen als u PowerApps sluit.

## <a name="prerequisites"></a>Vereisten

* [Meld u aan](../signup-for-powerapps.md) voor PowerApps en voer een van de volgende stappen uit:

  * Installeer PowerApps Studio voor Windows vanuit de [Windows Store](http://aka.ms/powerappsinstall), open het programma en meld u aan met de referenties die u ook hebt gebruikt om u te registreren.
  * Open PowerApps Studio voor internet in [powerapps.com](http://web.powerapps.com) door in de linkerbenedenhoek te klikken of tikken op **Nieuwe app**.
* Lees hoe u [een besturingselement kunt configureren](add-configure-controls.md).

## <a name="create-a-flow"></a>Een stroom maken
1. Meld u aan bij [powerapps.com](http://web.powerapps.com) en selecteer vervolgens **Flows** op de linkernavigatiebalk.

2. Selecteer op de pagina **Mijn stromen** de optie **Leeg item maken**.

    ![Optie om een stroom te maken zonder een sjabloon te gebruiken](./media/using-logic-flows/create-from-blank.png)

    **PowerApps** wordt toegevoegd als de standaard-trigger.

    ![PowerApps als de trigger waarmee de stroom wordt gestart](./media/using-logic-flows/set-trigger.png)

3. Selecteer **Nieuwe stap** en selecteer vervolgens **Een actie toevoegen**.

    ![Optie voor het toevoegen van een actie](./media/using-logic-flows/add-action.png)

4. Geef in het vak **Alle services en acties doorzoeken** een actie op voor uw stroom, zoals voor dit voorbeeld:

   1. typ **SharePoint** in het vak en selecteer vervolgens **SharePoint - Item maken** in de lijst onder **Acties**.

       ![Optie voor het maken van een SharePoint-item](./media/using-logic-flows/create-sharepoint-item.png)

   2. Voer uw referenties in om verbinding te maken met SharePoint, wanneer hierom wordt gevraagd.

   3. Typ of plak in het vak in het vak **Siteadres** de URL van een SharePoint Online-site die een lijst bevat.

       > [!NOTE]
> Geef de URL voor de site zelf op, zonder de lijst.

   4. Selecteer in het vak **Lijstnaam** de lijst die u wilt gebruiken.

   5. Klik of tik op het vak **Titel** en selecteer vervolgens **Dynamische inhoud toevoegen**.

       ![Voeg aan het titelveld de parameter Vraag in PowerApps toe](./media/using-logic-flows/ask-in-powerapps.png)

   6. Selecteer in de lijst met parameters **Vraag in PowerApps**.

       ![Parameter toevoegen](./media/using-logic-flows/add-parameter.png)

5. (Optioneel) Geef een of meer extra acties op, zoals het versturen van een e-mail met een verzoek om goedkeuring naar een adres dat u opgeeft of het toevoegen van een verwante vermelding in een andere gegevensbron.

6. Typ of plak boven aan het scherm een naam voor uw stroom en selecteer vervolgens **Stroom maken**.

    ![Geef uw stroom een naam en sla deze op.](./media/using-logic-flows/name-flow.png)

## <a name="add-a-flow-to-an-app"></a>Een stroom toevoegen aan een app
1. Selecteer in PowerApps **Nieuw** in het menu **Bestand**.

2. Selecteer op de tegel **Lege app** de optie **Telefoonindeling**.

3. Voeg een besturingselement **[Tekstinvoer](controls/control-text-input.md)** toe en geef het de naam **RecordTitle**.

4. Selecteer het besturingselement **[Knop](controls/control-button.md)** en plaats deze onder **RecordTitle**.

5. Selecteer het besturingselement **[Knop](controls/control-button.md)** en selecteer op het tabblad **Actie** de optie **Stromen**.

    ![De optie stromen op het tabblad actie](./media/using-logic-flows/action-tab.png)

6. Selecteer in het deelvenster de stroom die u in de vorige procedure hebt gemaakt.

    > [!NOTE]
> Als de stroom die u hebt gemaakt niet beschikbaar is, controleert u of PowerApps is ingesteld op de omgeving waarin u de stroom hebt gemaakt.

    ![Een stroom toevoegen vanuit het deelvenster Aanpassen](./media/using-logic-flows/add-flow-from-pane.png)

7. Typ of plak in de formulebalk **RecordTitle.Text)**, aan het einde van de formule die automatisch wordt toegevoegd.

    ![De eigenschap OnSelect met daarin de stroom](./media/using-logic-flows/onselect-with-flow.png)

## <a name="test-the-flow"></a>De stroom testen
1. Open de previewmodus door op F5 te drukken (of door de pijl in de rechterbovenhoek te selecteren).

    ![De eigenschap OnSelect met daarin de stroom](./media/using-logic-flows/open-preview.png)

2. Typ of plak tekst in **RecordTitle** en klik of tik vervolgens op het besturingselement **[Knop](controls/control-button.md)**.

    Er wordt een SharePoint-item gemaakt in de lijst die u hebt opgegeven, met de tekst die u hebt opgegeven als titel. Als de lijst was geopend op het moment dat de stroom werd uitgevoerd, moet u mogelijk het browservenster vernieuwen om de wijzigingen te zien.
