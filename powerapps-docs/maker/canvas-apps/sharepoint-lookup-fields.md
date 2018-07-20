---
title: Een relatie maken tussen SharePoint-lijsten via een opzoekveld | Microsoft Docs
description: Maak een relatie tussen SharePoint-lijsten met behulp van een opzoekveld.
author: skjerland
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/20/2017
ms.author: sharik
ms.openlocfilehash: 58097eec0bc483d8c38bf354513b70573e43049d
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023523"
---
# <a name="how-to-link-sharepoint-lists-using-lookup-fields"></a>SharePoint-lijsten koppelen met behulp van opzoekvelden
In deze zelfstudie leert hoe u twee SharePoint-lijsten kunt koppelen met opzoekvelden.

## <a name="overview"></a>Overzicht
SharePoint biedt twee soorten opzoekvelden:

* **Opzoeken**: maakt een koppeling met een andere lijst. Een lijst met *Orders* kan bijvoorbeeld zijn gekoppeld aan klanten in een lijst *Klanten*;
* **Keuze**: door op het veld te klikken of tikken wordt een klein menu met keuzeopties getoond.

In deze zelfstudie bouwt u een app die gebruikmaakt van dit soort opzoekvelden.

### <a name="what-do-you-use-lookup-fields-for"></a>Waar gebruikt u opzoekvelden voor?
De gegevens in een onderneming zijn uitgebreid en complex. Gegevens in de ene SharePoint-lijst zijn vaak gekoppeld aan gegevens in een andere lijst. Opzoekvelden zijn de belangrijkste manier om dergelijke bedrijfsgegevens samen te brengen.

Zo kunt u bijvoorbeeld een lijst met **Orders** hebben, met opzoekvelden die zijn gekoppeld aan een lijst met **Klanten**, om weer te geven welke klant een bestelling heeft geplaatst. Door het zoekveld in de lijst met **Orders** kunt u ook andere gegevens ophalen uit de lijst met **Klanten**. U zou ook een opzoekveld kunnen gebruiken om de lijst met **Orders** te koppelen aan een lijst met **Producten**, om zo de vereiste informatie over bestelde producten op te halen, zoals productafbeeldingen, specificaties, de details van de fabrikant, enzovoort.

### <a name="what-are-choice-fields-used-for"></a>Waar gebruikt u keuzevelden voor?
**Keuzevelden** worden gebruikt voor zeer korte lijsten. Echter, in plaats van een afzonderlijke lijst te maken, neemt u de lijstwaarden op in een klein menu dat wordt getoond wanneer op het **keuzeveld** wordt geklikt of getikt, zodat een van deze waarden kan worden geselecteerd.

Voorbeelden van een dergelijke toepassing zijn gegevens zoals de statuscode van de klant, beschikbaarheid of statuscodes: eigenlijk iedere vastgelegde lijst die relatief kort is. Deze gegevens kunnen ook worden geïmplementeerd als afzonderlijke lijsten, zodat u een **opzoekveld** kunt gebruiken om een koppeling te maken, maar het is meestal gemakkelijker en sneller om ze te implementeren als **keuzevelden**.

## <a name="create-the-lists-in-sharepoint"></a>De lijsten maken in SharePoint
In deze zelfstudie koppelt u twee aangepaste SharePoint-lijsten, **Assets** en **RepairShop**. De lijst **Assets** wordt gebruikt voor het bijhouden van hardware-apparatuur in een team. Aangezien hardware soms stukgaat, wordt de lijst **RepairShop** gebruikt om bij te houden welke lokale reparateurs deze kunnen repareren.

### <a name="the-lookup-fields-used-in-this-example"></a>De opzoekvelden die in dit voorbeeld worden gebruikt
De lijst **RepairShop** gebruik van het veld *ContactEmail* om de winkel te identificeren. Deze lijst wordt eerst gedefinieerd, zodat elke rij in de lijst **Assets** ergens naar kan verwijzen.

De lijst **Assets** bevat twee opzoekvelden:

* een met de naam *RepairShop*, van het type **Opzoeken**, die e-mailadressen gebruikt om te verwijzen naar items in de lijst **RepairShop**;
* een met de naam *AssetType*, van het type **Keuze**, waarmee wordt aangegeven wat voor soort hardware deze asset kan zijn.

In de praktijk zou u waarschijnlijk meer velden definiëren, afhankelijk van de informatie die u wilt bijhouden.

### <a name="define-the-repairshop-list-and-add-data"></a>De lijst RepairShop definiëren en gegevens toevoegen
U doet dit eerst, zodat u bij het toevoegen van gegevens aan de lijst **activa** in het opzoekveld *Assets.RepairShop* items kunt kiezen uit de lijst **RepairShop**.

1. Maak op uw SharePoint-site een nieuwe lijst, **RepairShop**.

    ![](./media/sharepoint-lookup-fields/new-list.png)

2. Voeg een veld *ContactEmail* toe, van het type **Eén tekstregel**.

    ![](./media/sharepoint-lookup-fields/add-email-field.png)

3. Voeg eventueel andere velden toe.

4. Klik of tik op **+ Nieuw** om voorbeeldgegevens aan de lijst toe te voegen; voeg ten minste 3 rijen toe met verschillende waarden voor *ContactEmail*. Wanneer een asset moet worden gerepareerd, kiest u een van deze reparateurs.

    ![](./media/sharepoint-lookup-fields/add-repair-shops.png)

### <a name="define-the-assets-list"></a>De lijst met Assets definiëren
1. Maak op uw SharePoint-site een nieuwe lijst, **Assets**.

2. Klik of tik op het plusteken en kies **Meer**.

    ![](./media/sharepoint-lookup-fields/choose-more-type.png)

3. Voeg een veld *AssetType* toe, van het type **Keuze**, en voer in het tekstvak **Typ elke keuze op een nieuwe regel** de waarden in die u wilt weergeven in het keuzemenu. Klik of tik op **OK**.

    ![](./media/sharepoint-lookup-fields/define-choice-column.png)

4. Voeg nu nog een ander veld toe, zoals u in stap 2 heeft gedaan: klik of tik op het plusteken en kies **Meer**.

5. Voeg een veld *RepairShop* toe, van het type **Opzoeken**, kies in het tekstvak **Informatie ophalen van** voor **RepairShop** en kies in het tekstvak **In deze kolom** voor *ContactEmail*. Klik of tik op **OK**.

    ![](./media/sharepoint-lookup-fields/setup-lookup-column.png)

6. Voeg eventueel nog andere velden toe.

## <a name="create-an-app-from-the-assets-list"></a>Een app maken op basis van de lijst Assets
U gebruikt deze app om gegevens toe te voegen aan de lijst **Assets**.

1. [Meld u aan bij PowerApps Studio](http://web.powerapps.com). Als u PowerApps nog niet eerder hebt gebruikt, kunt u zich [gratis aanmelden](https://powerapps.microsoft.com) met het e-mailadres van uw organisatie.

2. Klik of tik in het menu **Bestand** (aan de linkerkant) op **Nieuw** en klik of tik vervolgens op **SharePoint**.

    ![](./media/sharepoint-lookup-fields/create-app.png)

1. Kies uit SharePoint-site uit de lijst met **Recente sites** of voer de URL van uw site direct in het tekstvak in. Klik of tik op **Ga**.

    ![](./media/sharepoint-lookup-fields/choose-sharepoint-site.png)

1. Kies de belangrijkste lijst van uw SharePoint-site. In dit voorbeeld is dit **Assets**. Klik of tik op de knop **Verbinding maken**, in de rechterbenedenhoek.

    ![](./media/sharepoint-lookup-fields/choose-main-list.png)


## <a name="add-data-to-the-assets-list"></a>Gegevens toevoegen aan de lijst Assets
U kunt nu de app uitvoeren en kijken hoe het venster Details weergeven eruitziet voor de opzoekvelden.

1. Druk op F5 of selecteer Voorbeeld ( ![](./media/sharepoint-lookup-fields/preview.png) ).

2. Klik of tik op het pictogram **+**, in de rechterbovenhoek, om een vermelding toe te voegen.

3. Voer een **Titel** in voor deze asset.

4. Klik of tik op de vervolgkeuzepijl voor **AssetType**. De weergegeven waarden zijn de waarden die u hebt opgegeven tijdens het maken van dit veld. Kies een van de items.

    ![](./media/sharepoint-lookup-fields/fill-asset-type-3.png)

5. Klik of tik op de vervolgkeuzepijl voor **Repairshop**. Kies een van de items.

    ![](./media/sharepoint-lookup-fields/fill-repair-shop-3.png)

6. Klik of tik op het vinkje in de rechterbovenhoek om het nieuwe item op te slaan.

7. (optioneel) Herhaal deze stappen om zoveel items aan de lijst toe te voegen als u wilt.

8. Druk op Esc om terug te gaan naar de standaardwerkruimte.

## <a name="for-more-information"></a>Voor meer informatie
* [Introducing support for lookups and a new sample app (Introductie van ondersteuning voor opzoekacties en een nieuwe voorbeeldapp)](https://powerapps.microsoft.com/blog/support-for-lookups/)
* [Performance, Refresh button, ForAll, and multiple field lookups (Prestaties, de knop Vernieuwen, ForAll en opzoekacties voor meerdere velden)](https://powerapps.microsoft.com/blog/performance-refresh-forall-multiple-field-lookups-531/)
* [Generate an app by using a Common Data Service database (Een app genereren met behulp van een Common Data Service-database)](data-platform-create-app.md)
* [Create an app from scratch using a Common Data Service database (Een volledig nieuwe app maken met behulp van een Common Data Service-database)](data-platform-create-app-scratch.md)
