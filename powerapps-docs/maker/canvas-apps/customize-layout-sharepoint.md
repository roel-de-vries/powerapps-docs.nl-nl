---
title: 'Zelfstudie: Een galerie aanpassen in een gegenereerde app | Microsoft Docs'
description: In deze zelfstudie past u de gegevens die worden weergegeven in de galerie en andere elementen aan van een app die automatisch is gegenereerd in PowerApps.
author: AFTOwen
ms.service: powerapps
ms.topic: tutorial
ms.component: canvas
ms.date: 04/24/2018
ms.author: anneta
ms.openlocfilehash: 6206d520e8bb07c0919f482700c1af861e41109d
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="tutorial-customize-a-gallery-in-powerapps"></a>Zelfstudie: Een galerie aanpassen in PowerApps
In deze zelfstudie past u de galerie aan en brengt u andere wijzigingen aan in een app die automatisch is gegenereerd in Microsoft PowerApps. Gebruikers kunnen gegevens in de app beheren, zelfs als u deze wijzigingen niet aanbrengt. De app wordt echter eenvoudiger in gebruik als u deze aanpast aan de behoeften van uw organisatie:

> [!div class="checklist"]
> * De indeling van de galerie wijzigen
> * Het type gegevens wijzigen dat wordt weergegeven in de galerie
> * De kolommen wijzigen waarvoor gebruikers gegevens kunnen sorteren en zoeken
> * De titel van het scherm wijzigen
> * Een schuifbalk weergeven

Deze zelfstudie begint met een app die is gegenereerd op basis van een specifieke gegevensbron. Dezelfde concepten gelden echter voor elke app die u in PowerApps genereert op basis van een SharePoint-lijst, een Excel-tabel of een andere gegevensbron. 

Als u geen licentie voor PowerApps hebt, kunt u zich [gratis registreren](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Vereisten
U kunt dit onderwerp raadplegen voor alleen algemene concepten of u kunt elke stap uitvoeren als u [deze app voor de eerste keer genereert](data-platform-create-app.md).

## <a name="open-the-generated-app"></a>De gegenereerde app openen
1. Meld u aan bij [PowerApps](https://web.powerapps.com) en selecteer bij de linkerrand **Apps**.

    ![PowerApps-startpagina](./media/customize-layout-sharepoint/sign-in.png)

1. Zoek de app op die u hebt gegenereerd, selecteer het pictogram van het weglatingsteken (**...** ) voor de app en selecteer vervolgens **Bewerken**.

## <a name="change-the-layout"></a>De indeling wijzigen
1. Selecteer in het bladerscherm de galerie door op een willekeurig item te klikken of tikken, met uitzondering van het bovenste item in de lijst met accounts.

    Wanneer de galerie is geselecteerd, wordt het omgeven door een selectiekader met grepen.

    ![Geselecteerde galerie](./media/customize-layout-sharepoint/select-gallery.png)

1. Selecteer bij de rechterrand de optie **Accounts** om het deelvenster **Gegevens** te openen.

    ![Open het deelvenster **Gegevens**](./media/customize-layout-sharepoint/open-data-pane.png)

1. Open in het deelvenster **Gegevens** de lijst met opties onder **Indeling**.

    ![Indelingsopties weergeven](./media/customize-layout-sharepoint/show-layouts.png)

1. Selecteer in de lijst met opties de optie die alleen een titel toont.

    ![Indeling met alleen titel selecteren](./media/customize-layout-sharepoint/choose-layout.png)

1. Open in het deelvenster **Gegevens** de lijst met opties voor de titel.

    ![Indeling met alleen titel selecteren](./media/customize-layout-sharepoint/show-title-options.png)

1. Selecteer in de lijst met opties **Accountnaam (naam)** en sluit het deelvenster **Gegevens** vervolgens.

    De galerie geeft de naam van elke account weer.

    ![Definitieve galerie](./media/customize-layout-sharepoint/final-gallery.png)

## <a name="change-the-sort-and-search-columns"></a>De sorteer- en zoekkolommen wijzigen
1. Selecteer de galerie zoals in de vorige sectie wordt beschreven.

    ![Galerie selecteren](./media/customize-layout-sharepoint/select-gallery-title.png)

2. Controleer of de eigenschappenlijst linksboven de optie **Items** bevat.

    ![Eigenschap Items](./media/customize-layout-sharepoint/items-property.png)

    De waarde van deze eigenschap wordt weergegeven in de formulebalk. U stelt deze eigenschap in op het niet alleen opgeven van de gegevensbron voor de galerie, maar ook de kolommen waarvoor gebruikers gegevens kunnen sorteren en zoeken.

1. Kopieer deze formule en plak deze in de formulebalk.

    ```SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, Descending, Ascending))```

    Met deze formule kunt u zorgen voor het volgende:

    - Als een gebruiker een of meer tekens in de zoekbalk typt, toont de galerie alleen de accountnamen die de tekst bevatten die de gebruiker heeft ingetypt.
    - Als een gebruiker het sorteerpictogram selecteert, wordt de galerie alfabetisch gesorteerd op accountnaam in oplopende of aflopende volgorde, afhankelijk van hoe vaak de gebruiker het pictogram selecteert.

    Zie de [naslaginformatie over formules](formula-reference.md) voor meer informatie over deze en andere functies.

## <a name="test-sorting-and-searching"></a>Sorteren en zoeken testen
1. Open de preview-modus door op F5 te drukken (of door de afspeelknop bij de rechterbovenhoek te selecteren ).

    ![Preview-modus openen](./media/customize-layout-sharepoint/open-preview.png)

1. Selecteer in de hoek rechtsboven van het scherm voor bladeren het sorteerpictogram om de alfabetische sorteervolgorde te wijzigen in oplopend of aflopend.

    ![Het sorteerpictogram testen](./media/customize-layout-sharepoint/sort-button.png)

1. Typ in het zoekvak de letter **k** om alleen de accountnamen weer te geven die de letter bevatten die u hebt getypt.

    ![De zoekbalk testen](./media/customize-layout-sharepoint/test-filter.png)

1. Verwijder alle tekst uit de zoekbalk en sluit de preview-modus vervolgens door op Esc te drukken (of selecteer het pictogram voor sluiten in de rechterbovenhoek).

## <a name="change-the-screen-title"></a>De titel van het scherm wijzigen
1. Selecteer de titel van het scherm door erop te klikken of te tikken.

    ![Schermtitel selecteren](./media/customize-layout-sharepoint/select-title.png)

1. Controleer of in de eigenschappenlijst **Tekst** wordt weergegeven en vervang in de formulebalk vervolgens **Accounts** door **Bladeren** (behoud hierbij de dubbele aanhalingstekens).

    ![Schermtitel bijwerken](./media/customize-layout-sharepoint/change-screen-title.png)

    De wijziging wordt in het scherm weergegeven.

    ![Nieuwe schermtitel](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="show-a-scroll-bar"></a>Een schuifbalk weergeven
Als uw gebruikers mogelijk niet over een aanraakscherm of muiswiel beschikken, configureert u de galerie om een schuifbalk weer te geven wanneer de gebruiker de muisaanwijzer erover beweegt. Op die manier kunnen gebruikers alle accounts weergeven, zelfs als het scherm deze niet in één keer kan weergegeven.

1. Selecteer de galerie zoals in de eerste procedure wordt beschreven.

    ![Galerie selecteren](./media/customize-layout-sharepoint/select-gallery-sorted.png)

1. Selecteer op het tabblad **Galerie** de optie **Schuifbalk weergeven** en bevestig dat de waarde van deze eigenschap is gewijzigd in **true**. 

    ![Schuifbalk weergeven](./media/customize-layout-sharepoint/show-scrollbar.png)

## <a name="next-steps"></a>Volgende stappen
In deze zelfstudie hebt u de galerie aangepast en andere wijzigingen aangebracht in het standaardscherm voor het bladeren door records in een gegenereerde app. U kunt ook de standaardschermen aanpassen om details weer te geven en voor het maken of bijwerken van accounts. Omdat het scherm voor bladeren een galerie bevat, bevatten de andere twee schermen in de app formulieren. U kunt bijvoorbeeld wijzigen welke gegevenstypen de formulieren weergeven en in welke volgorde.

> [!div class="nextstepaction"]
> [Formulieren aanpassen](customize-forms-sharepoint.md)