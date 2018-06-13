---
title: De functie ShowError | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie ShowError in PowerApps
author: gregli-msft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 06/05/2018
ms.author: gregli
ms.openlocfilehash: 5b75c2cabedba4caf11aa3f922acc0a71ffca377
ms.sourcegitcommit: 045c96df42405c60c7675edbadac93455270a021
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2018
ms.locfileid: "34822530"
---
# <a name="notify-function-in-powerapps"></a>De meldingsfunctie in PowerApps
Hiermee wordt een bannerbericht weergegeven voor de gebruiker.

## <a name="description"></a>Beschrijving
De functie **Notify** geeft bovenaan het scherm een bannerbericht weer aan de gebruiker. Dit bericht valt over de huidige weergave.  

Er worden een geschikte kleur en pictogram gebruikt, afhankelijk van het type bericht.   Het type wordt opgegeven door het tweede argument van de functie:

| Het argument NotificationType | Beschrijving |
| --- | --- |
| **NotificationType.Error** | Geeft het bericht weer als een fout. |
| **NotificationType.Information** (standaard) | Geeft het bericht weer als informatief.  |
| **NotificationType.Success** | Geeft het bericht weer als geslaagd. |
| **NotificationType.Warning** | Geeft het bericht weer als een waarschuwing. |

Er worden berichten weergegeven bij het schrijven van de app en wanneer eindgebruikers gebruikmaken van de app.

**Notify** kan alleen worden gebruikt in [gedragsformules](../working-with-formulas-in-depth.md).

**Notify** kan worden gekoppeld aan de functie [**IfError**](function-iferror.md) om fouten met een aangepast foutbericht te detecteren en rapporteren.

PowerApps kan ook pushmeldingen versturen met behulp van een compleet ander mechanisme uit **Notify**.  Raadpleeg [Een melding versturen in PowerApps](../add-notifications.md) voor meer informatie.

Met **Notify** wordt altijd *true* geretourneerd.

Opmerking: deze functie werd voorheen **ShowError** genoemd; er konden alleen foutmeldingen worden weergegeven.

## <a name="syntax"></a>Syntaxis
**Notify**( *Message*, [ *NotificationType* ] )

* *Message*: vereist.  Bericht dat wordt weergegeven aan de gebruiker.
* *NotificationType*: optioneel.  Type van het bericht dat moet worden weergegeven in de bovenstaande tabel.  De standaardinstelling is **NotificationType.Information**.  

## <a name="examples"></a>Voorbeelden

### <a name="step-by-step"></a>Stap voor stap

1. Voeg een **knop**besturingselement toe aan het scherm.

2. Stel de eigenschap **OnSelect** van de **knop** in op:

    **Notify(Hello, World)**

3. Klik of druk op de knop.  

    Steeds wanneer op de knop wordt geklikt, wordt het bericht **Hello, World** ter informatie aan de gebruiker weergegeven.

    ![In de ontwerpomgeving Button.OnSelect weergeven, Notify aanroepen en het bericht Hello, World in een blauwe banner weergegeven aan de gebruiker](media/function-showerror/hello-world.png)

4. Wijzig het type bericht om een fout aan te geven.  Voeg een tweede argument toe aan onze formule:

    **Notify(Hello, World, NotificationType.Error )**

5. Klik of druk op de knop.

    Steeds wanneer op de knop wordt geklikt, wordt nu het bericht **Hello, World** als fout aan de gebruiker weergegeven.

    ![In de ontwerpomgeving Button.OnSelect weergeven, Notify aanroepen en het bericht Hello, World in een rode banner weergegeven aan de gebruiker](media/function-showerror/hello-world-error.png)

4. Wijzig het type bericht om een waarschuwing aan te geven.  Wijzig het tweede argument in onze formule:

    **Notify(Hello, World, NotificationType.Warning )**

5. Klik of druk op de knop.

    Steeds wanneer op de knop wordt geklikt, wordt nu het bericht **Hello, World** als waarschuwing aan de gebruiker weergegeven.

    ![In de ontwerpomgeving Button.OnSelect weergeven, Notify aanroepen en het bericht Hello, World in een oranje banner weergegeven aan de gebruiker](media/function-showerror/hello-world-warning.png)

4. Wijzig het type bericht om aan te geven dat de bewerking is geslaagd.  Wijzig het tweede argument in onze formule:

    **Notify(Hello, World, NotificationType.Success )**

5. Klik of druk op de knop.

    Steeds wanneer op de knop wordt geklikt, wordt nu het bericht **Hello, World** als geslaagde actie aan de gebruiker weergegeven.

    ![In de ontwerpomgeving Button.OnSelect weergeven, Notify aanroepen en het bericht Hello, World in een groene banner weergegeven aan de gebruiker](media/function-showerror/hello-world-success.png)
