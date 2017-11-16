---
title: Een pushmelding verzenden | Microsoft Docs
description: Informatie over het verzenden van native pushmeldingen naar een app in PowerApps.
services: 
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/08/2017
ms.author: jamesol
ms.openlocfilehash: f588a6fa9952f3d40d51fbedbd672031b9c837f5
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="send-a-push-notification-in-powerapps"></a>Een pushmelding verzenden in PowerApps
Pushmeldingen worden gebruikt in mobiele apps voor zakelijk en consumentengebruik, voornamelijk om app-gebruikers te benaderen en hun aandacht te trekken naar belangrijke taken. Het verzenden van meldingen in PowerApps vindt plaats via de PowerApps-meldingsconnector. U kunt native pushmeldingen verzenden naar alle apps die u in PowerApps maakt. We zullen in de toekomst meer meldingstypen toevoegen.

![Voorbeeld van een pushmelding](./media/add-notifications/pic1-notification-screenshot.png)

Voeg een pushmelding aan uw app toe als:

* uw gebruikers informatie direct moeten krijgen;
* uw gebruikers uw app moeten gebruiken om belangrijke taken uit te voeren, wanneer deze app vooraf is geladen;
* u uw gebruikers regelmatig wilt benaderen of uw gebruikers de app in een specifieke situatie moeten openen.

**Opmerking**: om pushmeldingen te ontvangen, dient iedere gebruiker de app in ieder geval eenmaal in PowerApps Mobile te hebben geopend of de app te hebben verkregen via AppSource in [Dynamics 365](https://home.dynamics.com/).

## <a name="before-you-start"></a>Voordat u begint
Voeg de PowerApps-meldingsconnector toe aan een app waarvoor u rechten als **Inzender** hebt. Als u nog geen app hebt, kunt u snel [een app maken op basis van een sjabloon](get-started-test-drive.md). U hebt de vereiste rechten dan standaard. Die zelfstudie en deze gebruiken allebei een app op basis van het sjabloon Case Management.

## <a name="send-a-notification-from-a-flow"></a>Een pushmelding versturen vanuit een stroom
**Opmerking**: als u een pushmelding activeert vanuit een stroom, kunt u de melding op dit moment enkel naar één gebruiker of beveiligingsgroep tegelijk verzenden.

1. Maak in [Microsoft Flow](https://flow.microsoft.com) een trigger die aangeeft wanneer de pushmelding wordt verzonden.
   
    U kunt bijvoorbeeld een melding verzenden wanneer in de Common Data Service een record wordt toegevoegd aan de entiteit **Case**.
   
    ![Schermopname van het maken van een stroom met een trigger op basis van de Common Data Service](./media/add-notifications/pic4-step1-flowupdated.png)
2. Maak een actie voor de stroom met behulp van de **PowerApps-meldingsconnector** en voer de **App-id** in van de app waar u meldingen naar wilt verzenden.
   
    U kunt de naam van de verbinding ook aanpassen aan uw scenario.
   
    ![Schermopname van het maken van een verbinding met de PowerApps die deze pushmeldingen ontvangen](./media/add-notifications/pic5-step2-create-connection.jpg)
3. (optioneel) Geef parameters door aan de app wanneer deze wordt geopend (nadat de gebruiker op de pushmelding tikt).
   
    In dit voorbeeld geven we de velden **Case-id** en **Eerste eigenaar** door voor de geselecteerde contactpersoon.
   
    ![Schermopname van het doorgeven van optionele parameters in de pushmelding](./media/add-notifications/pic6-step3-configure-notif.jpg)

## <a name="send-a-notification-from-an-app"></a>Een pushmelding verzenden vanuit een app
U kunt een pushmelding verzenden van een app naar een andere app of binnen dezelfde app.

1. Ga in [PowerApps](https://web.powerapps.com/) naar de app die u wilt gebruiken om pushmeldingen te verzenden.
2. Kopieer op het tabblad **Details** de **App-id** van deze app.
   
    ![App-id ophalen](./media/add-notifications/grab-id.png)
3. Maak op het tabblad **Verbindingen** een verbinding naar de PowerApps-meldingsconnector en plak hier de app-id uit de vorige stap.
   
    ![Verbinding maken](./media/add-notifications/create-connection.png)
4. De verbinding naar de trigger-app toevoegen.
   
    In ons voorbeeld gebruiken we dezelfde app als de trigger-app. De gebruiker die de case opnieuw toewijst activeert ook een pushmelding naar de nieuwe case-eigenaar.
   
    ![Verbinding toevoegen](./media/add-notifications/add-connection.png)
5. Roep via de pushmeldingverbinding de methode **SendPushNotification** aan.
   
    In ons voorbeeld activeren we deze melding met behulp van de eigenschap **OnSuccess** in een formulier.
   
    ![PowerApps-formule](./media/add-notifications/powerapps-function.png)

## <a name="load-a-specific-page-and-context-when-a-user-taps-the-notification"></a>Een specifieke pagina en context openen wanneer een gebruiker op de melding tikt
### <a name="pass-parameters"></a>Parameters doorgeven
De pushmelding kan bepaalde parameters doorgeven aan de app. Zo kunt u bijvoorbeeld de waarde **CaseID** uitlezen met behulp van *Param("CaseID")*. Voeg een besturingselement **Label** toe aan uw app om deze parameter snel te identificeren. Stel de eigenschap **Text** van dit besturingselement in op **Param("CaseID")**. Als de gebruiker de app vanuit opent de lijst **Alle apps** is deze waarde leeg. Als de gebruiker de app vanaf een andere locatie op het apparaat opent, wordt de waarde is gevuld met de waarde **CaseID**.

### <a name="set-the-start-page"></a>De startpagina instellen
U kunt uw app bijvoorbeeld instellen om na het openen direct naar de pagina **Case-details** te gaan:

1. Voeg een besturingselement van het type **Timer** toe en stel de bijbehorende eigenschap **OnTimerEnd** in op deze formule:
   <br>**Navigate(EditCase, ScreenTransition.None)**
2. (optioneel) Verberg het **Timer**-besturingselement door de eigenschap **Visible** in te stellen op **false**.
3. Stel de eigenschap **OnVisible** van het scherm in op **Timer.Start()**.

**Tip**: het is een goed idee om een unieke eerste pagina in de app te maken voor de melding:

1. Maak een lege pagina die uw app niet standaard opent, voeg een besturingselement van het type **Text Input** in en stel de waarde **timer.Duration** in.
2. Wanneer u de app maakt, moet u de timer instellen op een andere waarde dan nul. Wanneer u klaar bent om de app te publiceren, stelt u de waarde in op **0** om de timer direct te activeren.

## <a name="syntax"></a>Syntaxis
| Naam | Beschrijving |
| --- | --- |
| Pushmelding verzenden |Verzend een pushmelding naar de app die is opgegeven in de verbindingsinstellingen voor de melding. |

### <a name="parameters"></a>Parameters
| Naam | Type | Beschrijving |
| --- | --- | --- |
| ontvangers |String-matrix, vereist |Een lijst met: <ul> <li>E-mailadressen voor gebruikers of beveiligingsgroepen</li> <li>Object-id's voor gebruikers of beveiligingsgroepen in Azure Active Directory</li></ul> |
| bericht |Tekenreeks, vereist |De berichttekst voor de pushmelding. |
| openApp |Booleaans, optioneel |Of de app wel of niet moet worden geopend wanneer de gebruiker op de pushmelding tikt. |
| parameters |Parameters, optioneel |Sleutelwaarde-parameters die met de melding worden doorgegeven. Deze kunnen verder worden verwerkt in de app om een bepaalde pagina te openen en een specifieke status te laden. |

### <a name="sample-formulas"></a>Voorbeeldformules
Verzend een eenvoudige melding.

```
PowerAppsNotification.SendPushNotification(
{
  recipients: [""f60ccf6f-7579-4f92-967c-2920473c966b", 72f988bf-86f1-41af-91ab-2d7cd011db47],
  message: "A new case was assigned to you."
 }
)
```

Een melding verzenden die een app opent en bepaalde parameters doorgeeft.

```
PowerAppsNotification.SendPushNotification(
{
  recipients:["email1@contoso.com", "email2@contoso.com"],
  message:"message in the notif toast",
  params:Table({key:"notificationKey", value:"The value for notificationKey"}),
  openApp:true
 }
)
```

## <a name="known-limitations"></a>Bekende beperkingen
* Meldingen worden op dit moment niet weergegeven op PowerApps Mobile voor Windows Phone.
* Op dit moment bieden we geen pushmeldingen voor gebruikers die alleen apps in een webbrowser uitvoeren.
* Meldingen tonen het algemene PowerApps-pictogram in plaats van het pictogram van een specifieke app.
* Wanneer u Microsoft Flow gebruikt, kunt u een pushmelding aan slechts één ontvanger tegelijk verzenden.

Zie voor meer informatie [Referentie voor PowerApps-meldingen](https://docs.microsoft.com/en-us/connectors/powerappsnotification/).

