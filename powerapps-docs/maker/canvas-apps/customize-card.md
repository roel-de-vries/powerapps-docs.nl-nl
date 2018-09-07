---
title: Een kaart aanpassen | Microsoft Docs
description: Het standaardbesturingselement wijzigen dat wordt weergegeven in een kaart op een Details- of Bewerken-formulier in PowerApps
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 31c0810b9da5a52bcd5cc3b28b6def858541e15b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42841781"
---
# <a name="customize-a-card-in-powerapps"></a>Een kaart aanpassen in PowerApps
Basisaanpassingen uitvoeren (zonder een kaart te ontgrendelen) door bijvoorbeeld het besturingselement te wijzigen. Geavanceerde aanpassingen uitvoeren door de kaart te ontgrendelen en bijvoorbeeld een besturingselement toe te voegen dat niet standaard beschikbaar is voor die kaart.

Zie [Informatie over gegevenskaarten](working-with-cards.md) voor een overzicht.

## <a name="prerequisites"></a>Vereisten

* Ontdek hoe u [besturingselementen toevoegt en configureert](add-configure-controls.md).
* U kunt in dit onderwerp alleen de algemene concepten doorlezen, of u kunt de stappen precies volgen door de procedures in deze onderwerpen uit te voeren:

  1. [Genereer een app](data-platform-create-app.md).
  2. [Pas de bijbehorende galerie aan](customize-layout-sharepoint.md).
  3. [Pas de bijbehorende formulieren aan](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Een vergrendelde kaart aanpassen
In deze procedure gaat u een besturingselement **[Tekstinvoer](controls/control-text-input.md)** vervangen door een besturingselement **[Schuifelement](controls/control-slider.md)** zonder de kaart te ontgrendelen.

1. Meld u aan bij [PowerApps](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    ![Startpagina van PowerApps](./media/customize-card/sign-in.png)

1. Open de app die u hebt gegenereerd en aangepast, selecteer **EditForm1** en open vervolgens het deelvenster **Gegevens** door **Accounts** te selecteren in het rechterdeelvenster.

1. Selecteer in de lijst met velden de pijl omlaag voor **Aantal werknemers** om een lijst met opties weer te geven en selecteer vervolgens **Schuifregelaar bewerken**.

    ![Vervolgkeuzelijst met opties voor een aantalkaart](./media/customize-card/card-selector.png)

    De wijziging wordt in het scherm weergegeven.

    ![EditForm1 met schuifregelaar](./media/customize-card/add-slider.png)

## <a name="unlock-and-customize-a-card"></a>Een kaart ontgrendelen en aanpassen
In deze procedure ontgrendelt u kaart en vervangt u vervolgens het besturingselement **[In-/uitschakelen](controls/control-toggle.md)** door een besturingselement **[Selectievakje](controls/control-check-box.md)**.

1. Geef in **EditForm1** het veld **Marketingmateriaal verzenden** weer.

    ![Veld voor Marketingmateriaal verzenden weergeven](./media/customize-card/show-field.png)

2. Klik of tik, terwijl u deze kaart hebt geselecteerd, op **Geavanceerd** boven in het rechterdeelvenster en klik of tik op het vergrendelingspictogram om de kaart te ontgrendelen.

    ![Veld voor Marketingmateriaal verzenden weergeven](./media/customize-card/unlock-card.png)

1. Verwijder in de kaart het besturingselement **In-/uitschakelen**, voeg het besturingselement **Selectievakje** toe en noem het nieuwe besturingselement **chkMktg**.

    ![In-/ uitschakelen door selectievakje vervangen](./media/customize-card/add-checkbox.png)

1. Selecteer de kaart die u zojuist hebt bijgewerkt.

    ![Kaart selecteren](./media/customize-card/select-card.png)

1. Controleer of in het rechterdeelvenster het tabblad **Geavanceerd** nog steeds wordt weergegeven en klik of tik vervolgens op **Meer opties**.

    ![De knop Meer opties](./media/customize-card/more-options.png)

1. Wijzig de waarde van de eigenschap **Update** van de kaart in deze expressie:
<br>`chkMktg.Value`

1. Wijzig de waarde van de eigenschap **Y** van het foutbericht voor deze kaart in deze expressie:<br>
`chkMktg.Y + chkMktg.Height`

    ![Een foutbericht voor een nieuwe kaart selecteren](./media/customize-card/select-error.png)

1. Wijzig de waarde van de eigenschap **Tekst** van **chkMktg** in **Ja**.

    Het scherm weerspiegelt uw wijzigingen en de fouten zijn opgelost.

    ![Uiteindelijk scherm waarin de fouten zijn opgelost](./media/customize-card/final-screen.png)

## <a name="next-steps"></a>Volgende stappen
Nu u over enige basiskennis beschikt over het genereren van een app en het aanpassen van een galerie, een formulier en een kaart, kunt u [uw eigen app helemaal vanaf het begin bouwen](data-platform-create-app-scratch.md).
