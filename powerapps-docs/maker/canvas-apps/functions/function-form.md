---
title: De functies EditForm, NewForm, SubmitForm, ResetForm en ViewForm| Microsoft Docs
description: Referentie-informatie, inclusief syntaxis en voorbeelden, voor de functies EditForm, NewForm, SubmitForm, ResetForm en ViewForm in PowerApps
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 07/06/2017
ms.author: gregli
ms.openlocfilehash: 6a32068d0de49ea0a6cf752fde0fd486159f39e9
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "31836460"
---
# <a name="editform-newform-submitform-resetform-and-viewform-functions-in-powerapps"></a>De functies EditForm, NewForm, SubmitForm, ResetForm en ViewForm in PowerApps
Hiermee kunt u een item bekijken, bewerken of maken, de inhoud opslaan en de besturingselementen opnieuw instellen in een besturingselement **[Formulier bewerken](../controls/control-form-detail.md)**.

## <a name="overview"></a>Overzicht
Deze functies wijzigen de status van het besturingselement **Formulier bewerken**.  Het besturingselement kan worden gebruikt in een van deze modi:

| Modus | Beschrijving |
| --- | --- |
| **FormMode.Edit** |Het formulier wordt gevuld met een bestaand record, en de gebruiker kan de waarden van de velden wijzigen.  Als de gebruiker klaar is, kan die de wijzigingen opslaan naar het record. |
| **FormMode.New** |Het formulier is gevuld met standaardwaarden en de gebruiker kan de waarden van de velden wijzigen.  Als de gebruiker klaar is, kan die het record toevoegen aan de gegevensbron. |
| **FormMode.View** |Het formulier wordt gevuld met een bestaand record, maar de gebruiker kan de waarden van de velden niet wijzigen. |

## <a name="description"></a>Beschrijving
Deze functies worden vaak aangeroepen vanuit de formule **[OnSelect](../controls/properties-core.md)** voor een besturingselement van een **[knop](../controls/control-button.md)** of **[afbeelding](../controls/control-image.md)**, zodat de gebruiker wijzigingen kan opslaan, bewerkingen kan weggooien of een record kan maken. U kunt [besturingselementen en deze functies samen gebruiken](../working-with-forms.md) om een volledige oplossing te maken.

Deze functies retourneren geen waarden.

### <a name="submitform"></a>SubmitForm
Gebruik de functie **SubmitForm** in de eigenschap **[OnSelect](../controls/properties-core.md)** van een knopbesturingselement om wijzigingen in een formulierbesturingselement op te slaan naar de gegevensbron.

Voordat wijzigingen worden verzonden, controleert deze functie of er validatieproblemen zijn voor velden die als vereist zijn gemarkeerd of waarvoor een of meer beperkingen gelden op de waarde ervan. Dit gedrag komt overeen met de functie **[Validate](function-validate.md)**.

**SubmitForm** controleert ook de eigenschap **[Valid](../controls/control-form-detail.md)** van het formulier, die een aggregatie is van alle **[Valid](../controls/control-card.md)**-eigenschappen van de besturingselementen voor **[kaart](../controls/control-card.md)** die het formulierbesturingselement bevat. Als er een probleem optreedt, worden de gegevens niet verzonden en worden de eigenschappen **[Error](../controls/control-form-detail.md)** en **[ErrorKind](../controls/control-form-detail.md)** van het formulierbesturingselement dienovereenkomstig ingesteld.

Als de validatie is geslaagd, verzendt **SubmitForm** de wijziging naar de gegevensbron.

* Als dit lukt, wordt het **[OnSuccess](../controls/control-form-detail.md)**-gedrag van het formulier uitgevoerd, en worden de eigenschappen **[Error](../controls/control-form-detail.md)** en **[ErrorKind](../controls/control-form-detail.md)** uitgeschakeld.  Als het formulier zich in de modus **FormMode.New** bevindt, wordt deze geretourneerd naar de modus **FormMode.Edit**.
* Als dit niet lukt, wordt het **[OnFailure](../controls/control-form-detail.md)**-gedrag van het formulier uitgevoerd en worden de eigenschappen **[Error](../controls/control-form-detail.md)** en **[ErrorKind](../controls/control-form-detail.md)** aan de hand hiervan ingesteld.  De modus van het formulier blijft ongewijzigd.  

### <a name="editform"></a>EditForm
De functie **EditForm** wijzigt de modus van het formulierbesturingselement in **FormMode.Edit**. In deze modus wordt de inhoud van de eigenschap **[Item](../controls/control-form-detail.md)** van het formulierbesturingselement gebruikt om het formulier in te vullen.  Als de functie **SubmitForm** wordt uitgevoerd wanneer het formulier zich in deze modus bevindt, wordt er een record gewijzigd, niet een nieuwe gemaakt.  **FormMode.Edit** is de standaardinstelling voor het formulierbesturingselement.

### <a name="newform"></a>NewForm
De functie **NewForm** wijzigt de modus van het formulierbesturingselement in **FormMode.New**. In deze modus wordt de inhoud van de eigenschap **[Item](../controls/control-form-detail.md)** van het formulierbesturingselement genegeerd, en wordt het formulier ingevuld met de standaardwaarden van de eigenschap **[DataSource](../controls/control-form-detail.md)** van het formulier. Als de functie **SubmitForm** wordt uitgevoerd wanneer het formulier zich in deze modus bevindt, wordt er een nieuwe record gemaakt, niet een bestaande gewijzigd.

### <a name="resetform"></a>ResetForm
Met de functie **ResetForm** wordt de inhoud van een formulier teruggezet naar de oorspronkelijke waarden, van voordat de gebruiker wijzigingen aanbracht. Als het formulier zich in de modus **FormMode.New** bevindt, wordt het formulier teruggezet naar de modus **FormMode.Edit**. Daarnaast wordt het **[OnReset](../controls/control-form-detail.md)**-gedrag van het formulierbesturingselement uitgevoerd.  U kunt ook afzonderlijke besturingselementen opnieuw instellen met de functie **[Reset](function-reset.md)** maar alleen vanuit het formulier.

### <a name="viewform"></a>ViewForm
De functie **ViewForm** wijzigt de modus van het formulierbesturingselement in **FormMode.View**. In deze modus wordt de inhoud van de eigenschap **[Item](../controls/control-form-detail.md)** van het formulierbesturingselement gebruikt om het formulier in te vullen.  De functies **SubmitForm** en **RestForm** hebben geen effect in deze modus.

### <a name="displaymode-poperty"></a>DisplayMode Poperty
De huidige modus kan worden gelezen door de eigenschap **Mode**.  De modus bepaalt ook de waarde van de eigenschap **DisplayMode** die kan worden gebruikt door gegevenskaarten en besturingselementen in het formulierbesturingselement.  Vaak wordt de eigenschap **DisplayMode** van de gegevenskaart ingesteld op **Parent.DisplayMode** (refererend aan het formulier) net als de eigenschap **DisplayMode** van het besturingselement (refererend aan de gegevenskaart): 

| Modus | DisplayMode | Beschrijving |
| --- | --- | --- |
| **FormMode.Edit** |**DisplayMode.Edit** |Gegevenskaarten en besturingselementen zijn bewerkbaar, klaar om wijzigingen aan een record te accepteren. |
| **FormMode.New** |**DisplayMode.Edit** |Gegevenskaarten en besturingselementen zijn bewerkbaar, klaar om een nieuw record te accepteren. |
| **FormMode.View** |**DisplayMode.View** |Gegevenskaarten en besturingselementen zijn niet bewerkbaar en geoptimaliseerd om weer te geven. |

## <a name="syntax"></a>Syntaxis
**SubmitForm**( *FormName* )

* *FormName* - vereist. Formulierbesturingselement dat moet worden verzonden naar de gegevensbron.

**EditForm**( *FormName* )

* *FormName* - vereist.  Formulierbesturingselement dat moet worden overgeschakeld naar de modus **FormMode.Edit**.

**NewForm**( *FormName* )

* *FormName* - vereist. Formulierbesturingselement dat moet worden overgeschakeld naar de modus **FormMode.New**.

**ResetForm**( *FormName* )

* *FormName* - vereist. Formulierbesturingselement dat moet worden teruggezet naar de beginwaarden. Daarnaast wordt het formulier overgeschakeld van de modus **FormMode.New** naar de modus **FormMode.Edit**.

**ViewForm**( *FormName* )

* *FormName* - vereist.  Formulierbesturingselement om over te schakelen naar de modus **FormMode.View**.

## <a name="examples"></a>Voorbeelden
Zie [Gegevensformulieren begrijpen](../working-with-forms.md) voor volledige voorbeelden.

1. Voeg een knopbesturingselement toe, stel de eigenschap **[Text](../controls/properties-core.md)** in op de weergave van **Opslaan** en stel de bijbehorende eigenschap **[OnSelect](../controls/properties-core.md)** in op deze formule:
   
    **SubmitForm( EditForm )**
2. Maak de eigenschap **[OnFailure](../controls/control-form-detail.md)** van een formulierbesturingselement leeg en stel de bijbehorende eigenschap **[OnSuccess](../controls/control-form-detail.md)** in op deze formule:
   
    **Back()**
3. Wijzig de naam van een besturingselement **[Label](../controls/control-text-box.md)** in **ErrorText** en stel de eigenschap **[Text](../controls/properties-core.md)** ervan in op deze formule:
   
    **EditForm.Error**
   
    Wanneer de gebruiker de knop **Opslaan** selecteert, worden de wijzigingen in het formulierbesturingselement verzonden naar de onderliggende gegevensbron.
   
   * Als de verzending is geslaagd, worden alle wijzigingen opgeslagen. Als het formulierbesturingselement in de modus **Nieuw** staat, wordt er een record gemaakt. **ErrorText** is *leeg* en het vorige scherm wordt opnieuw weergegeven.
   * Als het verzenden is mislukt, toont **ErrorText** een gebruiksvriendelijk foutbericht en blijft het huidige scherm zichtbaar, zodat de gebruiker het probleem kan oplossen en het opnieuw kan proberen.
4. Voeg een knopbesturingselement toe, stel de eigenschap **[Text](../controls/properties-core.md)** in op de weergave van **Annuleren** en stel de bijbehorende eigenschap **[OnSelect](../controls/properties-core.md)** in op deze formule:
   
    **ResetForm( EditForm ); Back()**
   
    Wanneer de gebruiker de knop **Annuleren** selecteert, worden de waarden in het formulierbesturingselement teruggezet naar de waarden van voordat de gebruiker begon met bewerken, wordt het vorige scherm opnieuw weergegeven en wordt het formulierbesturingselement teruggezet naar de modus **Bewerken** als deze in de modus **Nieuw** stond.
5. Voeg een knopbesturingselement toe, stel de eigenschap **[Text](../controls/properties-core.md)** in op de weergave van **Nieuw** en stel de bijbehorende eigenschap **[OnSelect](../controls/properties-core.md)** in op deze formule:
   
    **NewForm( EditForm ); Navigate( EditScreen, None )**
   
    Wanneer de gebruiker de knop **Nieuw** selecteert, wordt het formulierbesturingselement overgeschakeld naar de modus **Nieuw**, wordt het besturingselement ingevuld met de standaardwaarden voor de gegevensbron van het formulierbesturingselement en wordt het scherm met het formulierbesturingselement weergegeven. Wanneer de functie **SubmitForm** wordt uitgevoerd, wordt er een nieuwe record gemaakt in plaats van dat een bestaande wordt bijgewerkt.

