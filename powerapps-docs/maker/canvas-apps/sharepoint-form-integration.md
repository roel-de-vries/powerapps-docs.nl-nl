---
title: Integratie met SharePoint-formulieren begrijpen | Microsoft Docs
description: Begrijpen hoe aangepaste formulieren werken met SharePoint
documentationcenter: na
author: sarafankit
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 11/11/2017
ms.author: ankitsar
ms.openlocfilehash: 8ae6bd0e576abd3a4115e452b286607b5c695acb
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/26/2018
---
# <a name="understand-sharepoint-forms-integration"></a>Integratie met SharePoint-formulieren begrijpen
U kunt nu eenvoudig [een SharePoint-lijstformulier aanpassen](customize-list-form.md) in PowerApps. In dit artikel vindt u meer informatie over de werking van de formulieren en de manier waarop u deze verder kunt aanpassen.

Als u een formulier voor een SharePoint-lijst hebt aangepast, hebt u waarschijnlijk al gemerkt dat u voor alle bewerkingen (zoals het maken, weergeven of bewerken van een item) het formulier kunt gebruiken dat standaard wordt gegenereerd. Dit is mogelijk dankzij gegenereerde formules en het besturingselement **SharePointIntegration**.

## <a name="understand-the-default-generated-form"></a>Het formulier dat standaard wordt gegenereerd, begrijpen

Het formulier dat standaard wordt gegenereerd, bestaat uit de volgende besturingselementen en de bijbehorende standaardwaarden:

* **FormScreen1**: dit is het [scherm](controls/control-screen.md) dat het formulier bevat.

* **SharePointForm1**: dit is het [formulier](working-with-forms.md) dat wordt gebruikt voor het maken, weergeven of bewerken van het lijstitem.

    * **Data Source**: de lijst waarvoor het formulier is aangepast.

    * **Item**: het geselecteerde item in de lijst. Wanneer u in PowerApps Studio werkt, wordt deze waarde voor uw gemak ingesteld op het eerste item in de lijst, First().

        **If(IsBlank(SharePointIntegration.Selected) || IsEmpty(SharePointIntegration.Selected),First('*YourListName*'),SharePointIntegration.Selected)**

    * **OnSuccess**: nadat het item is gemaakt of is opgeslagen, wordt het formulier opnieuw ingesteld en wordt het formulier in SharePoint verborgen.

        **ResetForm(SharePointForm1); RequestHide()**

* **SharePointIntegration**: het besturingselement dat verantwoordelijk is voor de communicatie van gebruikersacties tussen SharePoint en PowerApps.

    * **Data Source**: de lijst waarvoor het formulier is aangepast.

        **'*YourListName*'**

    * **OnNew**: hiermee activeert u de modus Nieuw voor **SharePointForm1**.

        **NewForm(SharePointForm1)**

    * **OnView**: hiermee activeert u de modus Weergeven voor **SharePointForm1**.

        **ViewForm(SharePointForm1)**

    * **OnEdit**: hiermee activeert u de modus Bewerken voor **SharePointForm1**.

        **EditForm(SharePointForm1)**

    * **OnSave**: hiermee worden de wijzigingen opgeslagen in **SharePointForm1**. Wanneer het formulier wordt verzonden, wordt de formule **SharePointForm1.OnSuccess** uitgevoerd.

        **SubmitForm(SharePointForm1)**

    * **OnCancel**: Hiermee maakt u de wijzigingen in **SharePointForm1** ongedaan. Het formulier wordt in SharePoint altijd verborgen wanneer een gebruiker in SharePoint op **Annuleren** klikt of tikt.

        **SubmitForm(SharePointForm1)**

Deze standaardinstellingen zorgen ervoor dat het formulier werkt wanneer dit in SharePoint wordt uitgevoerd. Met de instellingen wordt de PowerApps-formuliermodus gewijzigd wanneer de gebruiker het formulier gebruikt in SharePoint. Daarnaast zorgen deze instellingen ervoor dat de wijzigingen naar SharePoint worden verzonden.

## <a name="understand-the-sharepointintegration-control"></a>Het besturingselement SharePointIntegration begrijpen
Het besturingselement **SharePointIntegration** is verantwoordelijk voor de communicatie van gebruikersacties tussen SharePoint en PowerApps.

![](./media/sharepoint-form-integration/sharepointintegration-object.png)

>[!NOTE]
>De eigenschappen voor het besturingselement **SharePointIntegration** zijn alleen beschikbaar wanneer het formulier wordt uitgevoerd in SharePoint en zijn niet toegankelijk wanneer u het formulier aanpast in PowerApps studio.

Het besturingselement **SharePointIntegration** bevat de volgende eigenschappen:

**Selected**: het selecteerde item in de SharePoint-lijst.

**OnNew**: de manier waarop een app reageert wanneer een gebruiker op de knop **Nieuw** klikt of tikt, of het formulier **Item maken** in SharePoint opent.

**OnView**: de manier waarop een app reageert wanneer een gebruiker op een **item** klikt of tikt, of het formulier **Itemgegevens** in SharePoint opent.

**OnEdit**: de manier waarop een app reageert wanneer een gebruiker klikt of tikt op de knop **Alles bewerken**, of het formulier **Item bewerken** in SharePoint opent.

**OnSave**: de manier waarop een app reageert wanneer een gebruiker op de knop **Opslaan** in SharePoint klikt of tikt.

**OnCancel**: de manier waarop een app reageert wanneer een gebruiker op de knop **Annuleren** in SharePoint klikt of tikt.

**SelectedListItemID**: de item-ID voor het geselecteerde item in een SharePoint-lijst.

**DataSource**: De lijst die de record bevat die via het formulier wordt weergegeven, bewerkt of gemaakt. Houd er rekening mee dat als u deze eigenschap wijzigt, de eigenschappen **Selected** en **SelectedItemID** mogelijk niet meer werken.

## <a name="customize-the-default-form"></a>Het standaardformulier aanpassen
Nu u een beter inzicht hebt in het formulier dat standaard wordt gegenereerd en het besturingselement **SharePointIntegration**, kunt u de formules wijzigen om de formulieren verder aan te passen. Hier volgt een aantal zaken waarmee u rekening moet houden wanneer u formulieren aanpast:

* Als u afzonderlijke aangepaste ervaringen voor het maken, weergeven of bewerken van een item wilt maken, geeft u voor de formules **OnNew**, **OnView** of **OnEdit** van het besturingselement **SharePointIntegration** op dat variabelen moeten worden ingesteld of dat naar verschillende schermen moet worden genavigeerd.

* Gebruik de formule **OnSave** van het besturingselement **SharePointIntegration** om aan te passen wat er gebeurt wanneer een gebruiker in SharePoint op **Opslaan** klikt of tikt. Als u meerdere formulieren hebt, moet u ervoor zorgen dat u alleen de wijzigingen verzendt voor het formulier dat momenteel wordt gebruikt.

    >[!TIP]
     Stel verschillende waarden in voor een variabele in de formules **OnNew**, **OnView** en **OnEdit**. U kunt deze variabele in de formule **OnSave** gebruiken om te bepalen welk formulier wordt gebruikt.

* Zorg dat u voor alle formulieren **RequestHide()** opneemt in de formule **OnSuccess**. Als u dit vergeet, kan het formulier niet worden verborgen met SharePoint.

* U kunt niet bepalen of een formulier wordt verborgen wanneer een gebruiker in SharePoint op **Annuleren** klikt of tikt, dus zorg ervoor dat u uw formulieren opnieuw instelt in de formule **OnCancel** van het besturingselement **SharePointIntegration**.
