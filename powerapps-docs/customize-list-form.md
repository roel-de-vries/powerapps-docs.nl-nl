---
title: Een SharePoint-lijstformulier aanpassen met PowerApps | Microsoft Docs
description: U kunt PowerApps gebruiken om een lijstformulier in SharePoint aan te passen.
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/13/2017
ms.author: sharik
ms.openlocfilehash: 162314b1bb94e8358e5ddb290adf9db9f43950a0
ms.sourcegitcommit: ce66ba8eadc41d5f260217d164f8317b90ae1504
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2017
---
# <a name="customize-a-sharepoint-list-form-using-powerapps"></a>Een SharePoint-lijstformulier aanpassen met PowerApps

U kunt nu eenvoudig een SharePoint-lijstformulier aanpassen in PowerApps. Veel taken voor het aanpassen van SharePoint-lijstformulieren die u in InfoPath uitvoert, kunt u nu inline in een browser met PowerApps uitvoeren. Bovendien biedt PowerApps u de mogelijkheid om nog veel meer te doen.

PowerApps is rechtstreeks geïntegreerd met SharePoint - u hoeft dus geen andere app naar uw computer te downloaden. Met PowerApps kunt u aangepaste formulieren maken zonder dat u hiervoor code hoeft te schrijven. Na het publiceren worden de formulieren ingesloten in de SharePoint-lijst en zijn ze beschikbaar voor alle gebruikers van de lijst.

En omdat PowerApps naadloos is geïntegreerd in SharePoint, is niet nodig formulieren op twee plekken te beheren: machtigingen worden overgenomen van en beheerd via SharePoint. En wellicht is het grootste pluspunt van de integratie tussen PowerApps en SharePoint dat u toegang hebt tot veel krachtige functies, zoals Analytics-rapporten, regels voor aanwijzen en klikken voor voorwaardelijke opmaak en verbindingen met andere gegevensbronnen.

Klaar om te beginnen met het aanpassen van uw formulieren? Aan de slag!

> [!NOTE]
> Deze functionaliteit wordt in fasen geïmplementeerd voor SharePoint-klanten. Als u de optie **Formulieren aanpassen** op dit moment niet ziet in uw SharePoint-lijst, zal de optie binnenkort in uw versie worden geïmplementeerd.

## <a name="create-a-custom-list-form-app-in-powerapps"></a>Een aangepaste lijstformulier-app maken in PowerApps

> [!NOTE]
> De optie **Formulieren aanpassen** is niet beschikbaar of werkt mogelijk niet op de juiste manier als de SharePoint-lijst gegevenstypen bevat die niet worden ondersteund in PowerApps.

Open uw SharePoint-lijst, klik of tik op **PowerApps** op de opdrachtbalk en klik of tik vervolgens op **Formulieren aanpassen**. Hiermee wordt de webversie van PowerApps Studio in een browser geopend, met een door PowerApps gegenereerde formulier-app met één scherm, zoals u in het volgende voorbeeld kunt zien.

![Formulier-app met één scherm](./media/customize-list-form/list-form-app.png)

Als u op een willekeurig moment wilt teruggaan naar uw SharePoint-lijst, klikt of tikt u op **Terug naar SharePoint** in de linkerbovenhoek van de webversie van PowerApps Studio.

## <a name="customize-the-list-form"></a>Het lijstformulier aanpassen

PowerApps biedt verschillende manieren voor het aanpassen van formulieren. U kunt bijvoorbeeld de lay-out wijzigen, de tekst opmaken, afbeeldingen of grafieken toevoegen, aangepaste gegevensvalidatie toevoegen, regels toevoegen of aanvullende weergaven maken.

Stel dat uw formulier het veld **AccountID** bevat. U wilt het veld niet weergeven in het formulier.

![Het veld AccountID selecteren](./media/customize-list-form/select-card.png)

Het is in PowerApps zeer eenvoudig om dit veld te verbergen. Hiervoor gaat u naar de opties voor het aanpassen van formulieren en schakelt u het selectievakje **AccountID** uit.

![Het selectievakje AccountID uitschakelen](./media/customize-list-form/checkbox.png)

Zie [Formulieren aanpassen in PowerApps](customize-forms-sharepoint.md) voor stapsgewijze instructies voor het verbergen van velden en het aanbrengen van andere formulierwijzigingen.

## <a name="save-and-publish-the-list-form-back-to-sharepoint"></a>Het lijstformulier weer publiceren naar SharePoint

1. Als u klaar bent, klikt of tikt u op **Bestand** en vervolgens op **Opslaan**. Hiermee worden uw wijzigingen in de PowerApps-formulier-app opgeslagen.

1. Als u uw formulier weer naar SharePoint wilt publiceren zodat anderen dit kunnen gebruiken, klikt of tikt u op **Publiceren naar SharePoint**. U hoeft zich geen zorgen te maken over het delen van het formulier: de machtigingen voor het formulier worden overgenomen van de SharePoint-lijst.

    ![Publiceren naar SharePoint](./media/customize-list-form/publish-to-sharepoint.png)  

## <a name="view-your-list-form-in-sharepoint"></a>Uw lijstformulier in SharePoint weergeven

1. Als u uw aangepaste formulier wilt weergeven, klikt of tikt u op **Terug naar SharePoint** en vervolgens op een item in de SharePoint-lijst. Het formulier wordt inline aan de rechterkant van het browservenster geopend.

    ![Formulier inline openen in SharePoint](./media/customize-list-form/list-form-open.png)

1. Als u [uw formulier verder wilt aanpassen](sharepoint-form-integration.md), klikt of tikt u op **Aanpassen** en brengt u de gewenste wijzigingen aan. Zorg dat u uw wijzigingen opslaat wanneer u klaar bent.

    ![De knop Aanpassen](./media/customize-list-form/customize-button.png)

    U kunt uw formulier zo vaak aanpassen en opslaan als u wilt, maar uw wijzigingen worden pas zichtbaar in SharePoint nadat u op **Publiceren naar SharePoint** hebt geklikt of getikt.

## <a name="toggle-between-using-the-default-sharepoint-form-and-the-custom-form"></a>Schakelen tussen het standaard-SharePoint-formulier en het aangepaste formulier

1. Klik of tik in uw lijst in SharePoint op **Instellingen**, klik of tik op **Lijstinstellingen** en klik of tik vervolgens op **Formulierinstellingen**.

1. Klik of tik op de pagina **Formulierinstellingen** op een van de volgende opties en klik of tik daarna op **OK**.

    * **Het standaard-SharePoint-formulier gebruiken**: in SharePoint wordt het standaard-SharePoint-formulier voor uw lijst gebruikt.

    * **Een aangepast formulier gebruiken dat is gemaakt in PowerApps**: In SharePoint wordt het formulier gebruikt dat u in PowerApps hebt aangepast. (U kunt ook het formulier opnieuw publiceren via de pagina **Opslaan** in de webversie van PowerApps Studio.)

    Desgewenst kunt u tussen de opties wisselen.

    ![Opties voor formulierinstellingen](./media/customize-list-form/form-settings.png)

## <a name="delete-the-custom-list-form"></a>Het aangepaste lijstformulier verwijderen

1. Klik of tik in uw lijst in SharePoint op **Instellingen**, klik of tik op **Lijstinstellingen** en klik of tik vervolgens op **Formulierinstellingen**.

1. Klik of tik op de pagina **Formulierinstellingen** op **Het standaard-SharePoint-formulier gebruiken** en klik of tik onder de optie **Een aangepast formulier gebruiken dat is gemaakt in PowerApps** op **Aangepaste formulier verwijderen**. Hiermee wordt het aangepaste formulier verwijderd dat u in PowerApps hebt gemaakt en wordt het standaard-SharePoint-formulier hersteld.

    ![Het aangepaste formulier verwijderen](./media/customize-list-form/use-default-sharepoint.png)

## <a name="top-questions-about-list-form-customization"></a>Veelgestelde vragen over het aanpassen van lijstformulieren

### <a name="customizing-forms-versus-creating-apps"></a>Verschil tussen het aanpassen van formulieren en het maken van apps

**V:** Wat is het verschil tussen een aangepast lijstformulier en een zelfstandige app die ik vanuit SharePoint of PowerApps maak?

**A:** De lijstformulier-app die u vanuit SharePoint maakt, is een speciaal type PowerApps-app dat alleen kan worden gebruikt in een SharePoint-lijst. Deze lijstformulier-apps worden niet in uw app-lijst in de webversie van PowerApps Studio of in PowerApps Mobile weergegeven. Daarnaast kunt u deze apps niet buiten de SharePoint-lijst uitvoeren.

**V:** Wanneer moet ik een aangepast lijstformulier maken en wanneer moet ik een zelfstandige app maken?

**A:** Als u wilt dat gebruikers met behulp van SharePoint toegang tot het formulier kunnen krijgen en de manier wilt aanpassen waarop gebruikers lijstitems kunnen maken, weergeven of bewerken, kunt u het beste een aangepast lijstformulier maken vanuit SharePoint. Als u voor uw gebruikers een volledig aangepaste ervaring wilt maken die los van de SharePoint-site kan worden gebruikt, kunt u het beste een zelfstandige app maken.

**V:** Kan ik een lijstformulier aanpassen en een zelfstandige app voor dezelfde lijst maken?

**A:** Ja. Zelfstandige apps en aangepaste lijstformulieren zijn onafhankelijk van elkaar; u kunt ze los van elkaar aanpassen en beheren.

**V:** Zijn de aanpassingsfuncties voor het aanpassen van lijsten hetzelfde als die voor het aanpassen van zelfstandige apps?

**A:** Ja. U kunt [besturingselementen toevoegen en configureren](add-configure-controls.md), [verbinding maken met beschikbare gegevensbronnen](add-data-connection.md) of [uw eigen gegevensbronnen toevoegen](register-custom-api.md), taken die u ook voor zelfstandige apps kunt uitvoeren.

**V:** Kan ik aangepaste lijstformulieren in een andere omgeving maken dan in de standaardomgeving van mijn organisatie?

**A:** Nee. Momenteel kunt u aangepaste lijstformulieren alleen in de standaard-PowerApps-omgeving van uw organisatie maken. U kunt geen aangepaste lijstformulieren maken in (of migreren naar) andere omgevingen.

### <a name="managing-your-custom-list-form"></a>Uw aangepaste lijstformulier beheren

**V:** Hoe kan ik een directe koppeling krijgen naar mijn lijstformulier die ik met anderen kan delen?

**A:** Open het formulier in de SharePoint-lijst en klik of tik op **Koppeling kopiëren**.

**V:** Kan ik mijn lijstformulier bijwerken zonder mijn wijzigingen zichtbaar te maken voor anderen?

**A:** Ja. U kunt zo vaak u wilt wijzigingen in uw formulier aanbrengen. Uw wijzigingen worden echter pas zichtbaar voor anderen nadat u op **[Publiceren naar SharePoint](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint)** hebt geklikt of getikt.

**V:** Als ik een lijstformulier aanpas en per ongeluk een fout maak, kan ik dan de vorige versie herstellen?

**A:** Ja. Als u wijzigingen in uw formulier aanbrengt, deze wijzigingen opslaat en er vervolgens vaststelt dat u een fout hebt gemaakt, kunt u een vorige versie van het formulier herstellen met PowerApps:

1. Open uw SharePoint-lijst, klik of tik op **PowerApps** op de opdrachtbalk en klik of tik vervolgens op **Formulieren aanpassen**.

1. Klik of tik in de webversie van PowerApps Studio op **Bestand** en klik of tik op de pagina **Opslaan** op **Alle versies weergeven**. De pagina **Versies** wordt op een nieuw browsertabblad geopend.

    > [!NOTE]
    > Als u de knop **Alle versies weergeven** niet ziet, klikt of tikt u op **Opslaan**. Als het goed is, wordt de knop dan weergegeven.

1. Laat de pagina **Versies** of het browsertabblad geopend, ga terug naar de pagina **Opslaan** op het andere browsertabblad en klik of tik op de pijl boven het linkernavigatiedeelvenster. Klik of tik op **Terug naar SharePoint** om uw formulier te ontgrendelen en de webversie van PowerApps Studio af te sluiten.

1. Ga terug naar de pagina **Versies** op het andere browsertabblad, zoek de versie die u wilt herstellen en klik vervolgens op **Herstellen**.

    > [!NOTE]
    > Als u een foutmelding krijgt dat het herstel is mislukt omdat het formulier door een andere gebruiker is vergrendeld, wacht u totdat de gebruiker het formulier heeft ontgrendeld en probeert u het opnieuw.

**V:** Kan ik mijn aangepaste lijstformulier van de ene lijst naar de andere verplaatsen?

**A:** Nee. Deze functionaliteit wordt op dit moment niet ondersteund.

### <a name="administering-your-custom-list-form"></a>Beheer van uw aangepaste lijstformulier

**V:** Hoe kan ik mijn aangepaste lijstformulier delen met anderen?

**A:** U hoeft zich geen zorgen te maken over het delen van het formulier: de machtigingen voor het formulier worden overgenomen van de SharePoint-lijst. Wanneer u alle gewenste aanpassingen hebt uitgevoerd, [publiceert u uw formulier weer naar SharePoint](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint) zodat anderen dit kunnen gebruiken.

**V:** Wie kan lijstformulieren aanpassen?

**A:** Iedereen met SharePoint-machtigingen voor het beheren, ontwerpen of bewerken van de bijbehorende lijst.

**V:** Wat gebeurt er als gastgebruikers toegang krijgen tot een lijst dat een aangepast formulier bevat?

**A:** Gastgebruikers krijgen een foutmelding als zij een lijstformulier proberen te openen dat is aangepast met PowerApps.

**V:** Hoe kan ik als beheerder een lijst met alle aangepaste formulieren in mijn organisatie bekijken?

**A:** Als u een tenantbeheerder voor PowerApps bent of omgevingsbeheerdersmachtigingen voor de standaard-PowerApps-omgeving van uw organisatie hebt, gaat u als volgt te werk:

1. Ga naar het [PowerApps-beheercentrum](https://admin.powerapps.com) en selecteer de standaardomgeving voor uw organisatie in de lijst met omgevingen.

1. Klik of tik boven aan de pagina met de standaardomgeving op **Resources**.

1. Zoek in de lijst met apps de apps met app-type **SharePoint-formulier** (dit zijn de aangepaste formulieren).

    ![Lijst met aangepaste formulieren](./media/customize-list-form/all-customized-forms.png)
