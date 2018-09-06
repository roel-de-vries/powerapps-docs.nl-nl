---
title: Een SharePoint-lijstformulier aanpassen | Microsoft Docs
description: Gebruik PowerApps om het formulier aan te passen waarmee gebruikers vermeldingen in een SharePoint-lijst maken en bijwerken.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/11/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fc2940f726c23c79bcf894bb61c3e6b884ca7112
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42865772"
---
# <a name="customize-a-sharepoint-list-form-by-using-powerapps"></a>Een SharePoint-lijstformulier aanpassen met PowerApps

U kunt eenvoudig het formulier voor een SharePoint-lijst aanpassen door PowerApps te openen in een browser. U hoeft geen traditionele code, zoals C#, te schrijven of een andere app, zoals InfoPath, te downloaden. Wanneer u de wijzigingen publiceert, wordt het formulier ingesloten in de SharePoint-lijst voor gebruik door alle gebruikers ervan. In PowerApps kunt u ook analyserapporten bekijken, eenvoudig voorwaardelijke opmaak maken en verbinding maken met andere gegevensbronnen.

Als u de stappen in dit onderwerp wilt volgen, maakt u een eenvoudige lijst zodat u kunt zien hoe aanpassing werkt. U kunt dan vervolgens dezelfde concepten toepassen op uw eigen lijst.

> [!NOTE]
> Als de optie **Formulieren aanpassen** niet beschikbaar is of niet correct werkt voor uw lijst, bevat deze mogelijk gegevenstypen die [PowerApps niet ondersteunt](connections/connection-sharepoint-online.md#known-issues). U kunt uw formulier ook niet verplaatsen naar een andere lijst of [omgeving](working-with-environments.md).

## <a name="prerequisites"></a>Vereisten

Maak op een SharePoint-site een lijst die deze kolommen bevat:

- **ProductNaam** (één tekstregel)
- **Details** (ja/nee)
- **Prijs** (valuta)
- **Beschikbaarheid** (datum zonder tijd)
- **Kleur** (keuze)

## <a name="open-the-form-in-powerapps"></a>Open het formulier in PowerApps

1. Open de lijst die u hebt gemaakt en selecteer vervolgens **Nieuw** op de opdrachtbalk.

    Het formulier wordt geopend en geeft de velden weer die u hebt toegevoegd, plus **Titel** en **Bijlagen**.

1. Selecteer bovenaan het formulier **Aanpassen**.

    PowerApps Studio wordt geopend in hetzelfde browsertabblad.

1. Selecteer **Overslaan** in het dialoogvenster **Welkom bij PowerApps Studio**.

## <a name="hide-extra-fields"></a>Extra velden verbergen

In het midden van het scherm geeft PowerApps uw formulier weer. Het bevat echter enkele velden die u mogelijk niet wilt weergeven.

- Schakel in het deelvenster **Gegevens** de selectievakjes voor deze velden uit.

  - **Title**
  - **Gewijzigd**
  - **Gemaakt**
  - **Gemaakt door**
  - **Gewijzigd door**
  - **Id**

    Deze velden verdwijnen van het formulier, zodat alleen de velden overblijven die u hebt gemaakt.

    ![Lijst met velden](./media/customize-list-form/field-list.png)

## <a name="set-conditional-formatting"></a>Voorwaardelijke opmaak instellen

U kunt instellen dat de velden **Prijs**, **Beschikbaarheid** en **Kleuren** alleen worden weergegeven als **Details** is ingesteld op ja.

1. Selecteer de kaart **Prijs** door er op te klikken of te tikken.

    ![De kaart Beschikbaarheid selecteren](./media/customize-list-form/select-card.png)

1. Selecteer **Zichtbaar** in de lijst met eigenschappen.

    ![De eigenschap Zichtbaar selecteren](./media/customize-list-form/select-property.png)

1. Typ of plak deze formule in de formulebalk:

    **If(DataCardValue3.Value = true, true)**

    ![De waarde instellen van de eigenschap Zichtbaar](./media/customize-list-form/build-formula.png)

1. Herhaal de laatste drie stappen met de kaarten **Beschikbaarheid** en **Kleur**.

1. Houd de Alt-toets ingedrukt en selecteer de wisselknop **Details** meerdere malen (door erop te klikken of te tikken).

    De drie velden die u hebt geconfigureerd, worden weergegeven en verdwijnen van het formulier.

1. (optioneel) Pas uw formulieren aan op verschillende andere manieren, zoals:

    - Wijzig de grootte, stand of beide (bijvoorbeeld om [het formulier breder te maken](set-aspect-ratio-portrait-landscape.md)).
    - Voeg een besturingselement toe zodat gebruikers [bijlagen kunnen uploaden](controls/properties-text.md).
    - Maak een [opzoekveld](sharepoint-lookup-fields.md).

## <a name="save-publish-and-show-the-form"></a>Het formulier opslaan, publiceren en weergeven

1. Open het menu **Bestand**, selecteer **Opslaan** en selecteer vervolgens twee keer **Publiceren naar SharePoint**.

1. Selecteer de pijl-terug in de linkerbovenhoek en selecteer vervolgens **Terug naar SharePoint**.

1. Selecteer **Nieuw** op de opdrachtbalk om uw aangepaste formulier te openen.

1. Selecteer de wisselknop **Details** meerdere keren om de laatste drie velden te verbergen en weer te geven.

Als u [uw formulier verder wilt aanpassen](sharepoint-form-integration.md), opent u het en selecteert u **Aanpassen** bovenaan het formulier. Maak, bewaar en publiceer uw wijzigingen vervolgens.

## <a name="use-the-default-form"></a>Het standaardformulier gebruiken

1. Vanaf uw lijst in SharePoint opent u de instellingenpagina (door het tandwielpictogram in de rechterbovenhoek te selecteren) en selecteert u vervolgens **Lijstinstellingen**.

2. Selecteer onder **Algemene instellingen** de optie **Formulierinstellingen**.

3. Selecteer op de pagina **Formulierinstellingen** een van deze opties en selecteer vervolgens **OK**.

    - **Het standaard SharePoint-formulier gebruiken**: wanneer een gebruiker uw lijst opent en **Nieuw** selecteert op de opdrachtbalk, wordt het standaardformulier voor de lijst weergegeven.

    - **Een aangepast formulier gebruiken dat is gemaakt in PowerApps**: wanneer een gebruiker uw lijst opent en **Nieuw** selecteert op de opdrachtbalk, wordt uw aangepaste formulier weergegeven. (Als alternatief kunt u het formulier ook opnieuw publiceren in PowerApps.)

    Desgewenst kunt u tussen de opties wisselen.

    ![Opties voor formulierinstellingen](./media/customize-list-form/form-settings.png)

## <a name="delete-the-custom-form"></a>Het aangepaste formulier verwijderen

1. Vanaf uw lijst in SharePoint opent u de instellingenpagina (door het tandwielpictogram in de rechterbovenhoek te selecteren) en selecteert u vervolgens **Lijstinstellingen**.

1. Selecteer onder **Algemene instellingen** de optie **Formulierinstellingen**.

1. Selecteer op de pagina **Formulierinstellingen** de optie **Het standaard SharePoint-formulier gebruiken** en selecteer vervolgens **Aangepast formulier verwijderen**.

    ![Het aangepaste formulier verwijderen](./media/customize-list-form/use-default-sharepoint.png)

## <a name="q--a"></a>Vragen en antwoorden

### <a name="forms-vs-apps"></a>Formulieren versus apps

**V:** Wat is het verschil tussen een aangepast formulier en een zelfstandige app die ik vanuit SharePoint of PowerApps maak?

**A:** Als u het formulier voor een SharePoint-lijst aanpast, wordt het formulier niet weergegeven als een app in PowerApps Studio of PowerApps Mobile. U kunt het formulier alleen openen vanuit de lijst waarvoor u het hebt gemaakt.

**V:** Wanneer moet ik een formulier voor het beheren van gegevens in een SharePoint-lijst aanpassen en wanneer moet ik een zelfstandige app maken?

**A:** U kunt een formulier aanpassen als u wilt dat uw gebruikers gegevens kunnen beheren zonder SharePoint (bijvoorbeeld in een desktopbrowser). Maak een app als u wilt dat uw gebruikers gegevens kunnen beheren buiten SharePoint (bijvoorbeeld op een mobiel apparaat).

**V:** Kan ik een lijstformulier aanpassen en een app voor dezelfde lijst maken?

**A:** Ja.

**V:** Kan ik een lijst aanpassen en een app maken met dezelfde functies?

**A:** Ja.

**V:** Kan ik een formulier aanpassen in een andere omgeving dan in de standaardomgeving van mijn organisatie?

**A:** Nee.

### <a name="manage-your-custom-form"></a>Uw aangepaste formulier beheren

**V:** Hoe kan ik eenvoudig mijn formulier delen met anderen?

**A:** Openen het formulier, selecteer **Koppeling kopiëren** en stuur vervolgens de koppeling naar iedereen die het formulier moet kunnen gebruiken.

**V:** Kan ik mijn formulier bijwerken zonder mijn wijzigingen zichtbaar te maken voor anderen?

**A:** Ja. U kunt uw formulier wijzigen en zo vaak u wilt opslaan. Uw wijzigingen worden echter pas zichtbaar voor anderen nadat u op tweemaal **Publiceren naar SharePoint** hebt geselecteerd.

**V:** Als ik een lijstformulier aanpas en per ongeluk een fout maak, kan ik dan de vorige versie herstellen?

**A:** Ja.

1. Open de lijst, selecteer **PowerApps** op de opdrachtbalk en selecteer vervolgens **Formulieren aanpassen**.

1. Selecteer in PowerApps Studio de optie **Bestand** en selecteer vervolgens **Alle versies weergeven**. De pagina **Versies** wordt op een nieuw browsertabblad geopend.

    > [!NOTE]
    > Als u de knop **Alle versies weergeven** niet ziet, selecteert u **Opslaan**. Als het goed is, wordt de knop dan weergegeven.

1. Laat de pagina **Versies** of het browsertabblad geopend, ga terug naar de pagina **Opslaan** op het andere browsertabblad en klik of tik op de pijl boven in het linkernavigatiedeelvenster. Klik of tik op **Terug naar SharePoint** om uw formulier te ontgrendelen en PowerApps Studio te sluiten.

1. Ga terug naar de pagina **Versies** op het andere browsertabblad, zoek de versie die u wilt herstellen en selecteer vervolgens **Herstellen**.

    > [!NOTE]
    > Als u een foutmelding krijgt dat het herstel is mislukt omdat het formulier door een andere gebruiker is vergrendeld, wacht u totdat de gebruiker het formulier heeft ontgrendeld en probeert u het opnieuw.

**V:** Kan ik mijn aangepaste formulier van de ene lijst naar de andere verplaatsen?

**A:** Nee.

### <a name="administer-your-custom-form"></a>Uw aangepaste formulier beheren

**Q:** Hoe kan ik mijn formulier delen?

**A:** U hoeft zich geen zorgen te maken over het delen van het formulier: de machtigingen voor het formulier worden overgenomen van de SharePoint-lijst. Wanneer u alle gewenste aanpassingen hebt uitgevoerd, [publiceert u uw formulier weer naar SharePoint](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint) zodat anderen dit kunnen gebruiken.

**V:** Wie kan lijstformulieren aanpassen?

**A:** Iedereen met SharePoint-machtigingen voor het beheren, ontwerpen of bewerken van de bijbehorende lijst.

**V:** Heb ik een PowerApps-licentie nodig om aangepaste lijstformulieren te maken en te gebruiken?

**A:** U hebt een [Office 365-abonnement nodig dat PowerApps](../../administrator/pricing-billing-skus.md#licenses) bevat.

**V:** Wat gebeurt er als gastgebruikers toegang krijgen tot een lijst dat een aangepast formulier bevat?

**A:** Gastgebruikers krijgen een foutmelding als zij een lijstformulier proberen te openen dat is aangepast met PowerApps.

**V:** Hoe kan ik als beheerder een lijst met alle aangepaste formulieren in mijn organisatie bekijken?

**A:** Als u een tenantbeheerder voor PowerApps bent of omgevingsbeheerdersmachtigingen voor de standaard-PowerApps-omgeving van uw organisatie hebt, gaat u als volgt te werk:

1. Selecteer in het [PowerApps-beheercentrum](https://admin.powerapps.com) de standaardomgeving voor uw organisatie in de lijst met omgevingen.

1. Selecteer bovenaan de pagina met de standaardomgeving **Resources**.

1. Zoek in de lijst met apps de apps met app-type **SharePoint-formulier** (dit zijn de aangepaste formulieren).

    ![Lijst met aangepaste formulieren](./media/customize-list-form/all-customized-forms.png)
