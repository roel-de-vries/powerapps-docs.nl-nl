---
title: Canvas-apps ontwikkelen die geschikt zijn voor offlinegebruik | Microsoft Docs
description: Ontwikkel canvas-apps die geschikt zijn voor offlinegebruik, zodat uw gebruikers altijd productief kunnen zijn, online en offline.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/09/2017
ms.author: mblythe
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a255489f243ca8586f349e617e5af2023e88732b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864397"
---
# <a name="develop-offline-capable-canvas-apps-with-powerapps"></a>Canvas-apps die geschikt zijn voor offlinegebruik ontwikkelen met PowerApps

Een van de meest voorkomende scenario's waarmee u als ontwikkelaar van mobiele apps te maken hebt, is uw gebruikers productief te laten zijn wanneer er een beperkte of helemaal geen verbinding is. PowerApps beschikt over een aantal functies en gedragingen waarmee u canvas-apps kunt ontwikkelen die geschikt zijn voor offlinegebruik. U kunt:

* PowerApps Mobile starten wanneer u offline bent.
* Door u ontwikkelde apps uitvoeren wanneer u offline bent.
* Het signaalobject [Verbinding](../canvas-apps/functions/signals.md#connection) gebruiken om te bepalen of een app offline is, online is of gebruikmaakt van een verbinding met een datalimiet.
* [Verzamelingen](../canvas-apps/create-update-collection.md) en functies zoals [LoadData en SaveData](../canvas-apps/functions/function-savedata-loaddata.md) gebruiken voor basisgegevensopslag wanneer u offline bent.

> [!NOTE]
> Deze functie is nog in ontwikkeling en werkt niet optimaal in alle huidige scenario's. De functies SaveData() op een lokaal apparaat en LoadData() vanaf een apparaat werken het beste in hun huidige implementatie en met relatief kleine hoeveelheden gegevens, zoals tientallen tekstrecords in een tabel waarvan de totale grootte de 2 MB niet overschrijdt. Dit is handig in sommige eenvoudige 'offlinescenario's' en om de opstartprestaties van een canvas-app te verbeteren (omdat gegevens lokaal in de cache worden opgeslagen). Met deze functie voor het opslaan van grote hoeveelheden gegevens (bijvoorbeeld duizenden rijen opslaan in een tabel of grote afbeeldingen of video's opslaan in de cache) kunnen er echter fouten of onverwachte gedragingen optreden met de huidige implementatie. Gebruik de functie dan ook niet. Met de functies worden samenvoegconflicten ook niet automatisch verholpen wanneer een apparaat weer verbinding maakt na offline te zijn geweest. De maker moet tijdens het schrijven van expressies configureren welke gegevens worden opgeslagen en wat er gebeurt wanneer er opnieuw verbinding wordt gemaakt.
>
> Er wordt aan gewerkt om de mogelijkheden van offline-apps uit te breiden, om de stabiliteit en groottelimieten te verhogen en om (in de toekomst) automatisch beslissingen te nemen over wat er moet worden opgeslagen en wat er wordt gedaan bij conflicten. Kom hier regelmatig terug en bekijk de [PowerApps-blog](https://powerapps.microsoft.com/blog/) om te controleren op updates.

## <a name="how-to-build-offline-capable-apps"></a>Apps bouwen die geschikt zijn voor offlinegebruik

Het eerste waaraan u moet denken in offlinescenario's is hoe uw apps met gegevens werken. Apps in PowerApps krijgen voornamelijk toegang tot gegevens via een reeks [connectors](../canvas-apps/connections-list.md) die het platform biedt, zoals SharePoint, Office 365 en Common Data Service. U kunt ook aangepaste connectors bouwen waarmee apps toegang kunnen krijgen tot elke service die een RESTful-eindpunt biedt. Dit kan een web-API of een service zoals Azure Functions zijn. Al deze connectors gebruiken HTTPS via het internet, wat betekent dat uw gebruikers online moeten zijn om toegang te kunnen krijgen tot gegevens en andere functionaliteiten die een service biedt.

![PowerApps-app met connectors](./media/offline-apps/online-app.png)

### <a name="handling-offline-data"></a>Offlinegegevens verwerken
Een van de meest interessante aspecten van PowerApps is de reeks functionaliteiten en formules waarmee u op een consistente manier gegevens kunt filteren, zoeken, sorteren, samenvoegen en manipuleren, ongeacht de gegevensbron. Bronnen variëren van verzamelingen in het geheugen in de app tot SharePoint-lijsten, SQL-databases en Common Data Service. Dankzij deze consistentie kunt u een app gemakkelijk opnieuw targeten om een andere back-end te gebruiken. Bovenal stelt het u in staat lokale verzamelingen te gebruiken voor gegevensbeheer met vrijwel geen veranderingen in de logica van een app. Lokale verzamelingen zijn zelfs het primaire mechanisme voor het verwerken van offlinegegevens.

## <a name="building-an-offline-twitter-app"></a>Een offline Twitter-app bouwen
Om de focus op de offlineaspecten van app-ontwikkeling te houden, zullen we u een eenvoudig scenario met betrekking tot Twitter laten zien. We zullen een app bouwen waarmee u tweets kunt lezen en indienen terwijl u offline bent. De app post tweets en laadt de lokale gegevens wanneer de app online gaat.

Op een hoog niveau doet de app het volgende:

1. Bij het starten van de app (gebaseerd op de eigenschap **OnVisible** op het eerste scherm):

   * Als het apparaat online is, verkrijgen we rechtstreeks toegang tot de Twitter-connector om gegevens op te halen en vullen we een verzameling met die gegevens.
   * Als het apparaat offline is, laden we de gegevens uit een lokaal cachebestand met behulp van [LoadData](../canvas-apps/functions/function-savedata-loaddata.md).
   * We stellen de gebruiker in staat tweets in te dienen. Als het apparaat online is, posten we die rechtstreeks op Twitter en vernieuwen we de lokale cache.
2. Elke 5 minuten (indien online):

   * Posten we tweets die in de lokale cache staan.
   * Vernieuwen we de lokale cache en slaan we deze op met behulp van [SaveData](../canvas-apps/functions/function-savedata-loaddata.md).

### <a name="step-1-create-a-new-phone-app"></a>Stap 1: Een nieuwe telefoon-app maken
1. Open PowerApps Studio.
2. Klik of tik op **Nieuw** > **Lege app** > **Telefoonindeling**.

    ![Lege app, telefoonindeling](./media/offline-apps/blank-app.png)

### <a name="step-2-add-a-twitter-connection"></a>Stap 2: Een Twitter-verbinding toevoegen

1. Klik of tik op **Inhoud** > **Gegevensbronnen** en kies vervolgens **Gegevensbron toevoegen** in het deelvenster **Gegevensbronnen**.

2. Klik of tik op **Nieuwe verbinding**, selecteer **Twitter** en klik of tik op **Maken**.

3. Voer uw referenties in en maak de verbinding.

    ![Een Twitter-verbinding toevoegen](./media/offline-apps/twitter-connection.png)

### <a name="step-3-load-tweets-into-a-localtweets-collection-on-app-startup"></a>Stap 3: Tweets laden in een LocalTweets-verzameling bij het starten van de app
Selecteer de eigenschap **OnVisible** voor **Screen1** in de app, en kopieer en plak de volgende formule:

```
If(Connection.Connected,

    ClearCollect(LocalTweets, Twitter.SearchTweet("PowerApps", {maxResults: 100}));

    UpdateContext({statusText: "Online data"})

    ,

    LoadData(LocalTweets, "Tweets", true);

    UpdateContext({statusText: "Local data"})

);

LoadData(LocalTweetsToPost, "LocalTweets", true);

SaveData(LocalTweets, "Tweets")
```

![Formule voor het laden van tweets](./media/offline-apps/load-tweets.png)

Deze formule controleert of het apparaat online is:

* Als het apparaat online is, laadt het maximaal 100 tweets in een **LocalTweets**-verzameling met de zoekterm "PowerApps".
* Als het apparaat offline is, laadt het de lokale cache uit een bestand genaamd "Tweets", indien beschikbaar.

### <a name="step-4-add-a-gallery-and-bind-it-to-the-localtweets-collection"></a>Stap 4: Een galerie toevoegen en met de LocalTweets-verzameling verbinden

1. Voeg een nieuwe galerie met flexibele hoogte in: **Invoegen** > **Galerie** > **Lege flexibele hoogte**.

2. Stel de eigenschap **Items** in op **LocalTweets**.

3. Voeg vier besturingselementen van het type **Label** toe om gegevens uit elke tweet weer te geven en stel de **Text**-eigenschappen in op:
   * **ThisItem.TweetText**
   * **ThisItem.UserDetails.FullName & " \@" & ThisItem.UserDetails.UserName**
   * **"RT: " & ThisItem.RetweetCount**
   * **Text(DateTimeValue(ThisItem.CreatedAtIso), DateTimeFormat.ShortDateTime)**
4. Voeg een besturingselement van het type **Afbeelding** toe en stel de eigenschap **Image** in op **ThisItem.UserDetails.ProfileImageUrl**.

### <a name="step-5-add-a-connection-status-label"></a>Stap 5: Een verbindingsstatuslabel toevoegen
Voeg een nieuw besturingselement van het type **Label** in en stel de bijbehorende eigenschap **Text** in op de volgende formule:

```
If (Connection.Connected, "Connected", "Offline")
```

Deze formule controleert of het apparaat online is. Zo ja, dan is de tekst van het label "Connected". Zo niet, dan is de tekst "Offline".

### <a name="step-6-add-a-text-input-to-compose-new-tweets"></a>Stap 6: Tekstinvoer toevoegen om nieuwe tweets op te stellen

1. Voeg een nieuw besturingselement van het type **Tekstinvoer** genaamd "NewTweetTextInput" in.

2. Stel de eigenschap **Reset** van de tekstinvoer in op **resetNewTweet**.

### <a name="step-7-add-a-button-to-post-the-tweet"></a>Stap 7: Een knop toevoegen om de tweet te posten
1. Voeg een besturingselement van het type **Knop** toe en stel de eigenschap **Text** in op "Tweet".
2. Stel de eigenschap **OnSelect** in op de volgende formule:

    ```
    If (Connection.Connected,

        Twitter.Tweet("", {tweetText: NewTweetTextInput.Text}),

        Collect(LocalTweetsToPost, {tweetText: NewTweetTextInput.Text});

        SaveData(LocalTweetsToPost, "LocalTweetsToPost")

    );

    UpdateContext({resetNewTweet: true});

    UpdateContext({resetNewTweet: false})
    ```  

Deze formule controleert of het apparaat online is:

* Als het apparaat online is, wordt de tekst onmiddellijk getweet.
* Als het apparaat offline is, wordt de tweet vastgelegd in een **LocalTweetsToPost**-verzameling en opgeslagen in de app.

Vervolgens stelt de formule de tekst in het tekstvak opnieuw in.

### <a name="step-8-add-a-timer-to-check-for-tweets-every-five-minutes"></a>Stap 8: Een timer toevoegen om elke vijf minuten op tweets te controleren
Voeg een nieuw besturingselement van het type **Timer** toe:

* Stel de eigenschap **Duration** in op 300000.

* Stel de eigenschap **AutoStart** in op 'true'.

* Stel de eigenschap **OnTimerEnd** in op de volgende formule:

    ```
    If(Connection.Connected,

        ForAll(LocalTweetsToPost, Twitter.Tweet("", {tweetText: tweetText}));

        Clear(LocalTweetsToPost);

        Collect(LocalTweetsToPost, {tweetText: NewTweetTextInput.Text});

        SaveData(LocalTweetsToPost, "LocalTweetsToPost");

        UpdateContext({statusText: "Online data"})
    )
    ```

Deze formule controleert of het apparaat online is. Zo ja, dan tweet de app alle items in de **LocalTweetsToPost**-verzameling. Vervolgens wist de app de verzameling.

Nu de app klaar is, laten we zien hoe deze eruitziet voordat we deze gaan testen. Links is de app online, en rechts is de app offline en staat er één tweet klaar om te posten zodra de app weer online is.

![Voltooide app met online- en offlinemodus](./media/offline-apps/finished-app.png)

## <a name="testing-the-app"></a>De app testen
Gebruik de volgende stappen om de app te testen:

1. Voer PowerApps uit op een mobiel apparaat terwijl u online bent. U moet de app ten minste eenmaal uitvoeren terwijl u online bent, zodat u de app op het apparaat kunt downloaden.
2. Start de Twitter-app.
3. U ziet dat de tweets worden geladen en dat de status **Connected** is.
4. Sluit PowerApps volledig.
5. Zet het apparaat in vliegtuigmodus om te verzekeren dat het offline is.
6. Voer PowerApps uit. U kunt de Twitter-app nu offline uitvoeren, en u hebt toegang tot alle andere apps die u eerder op dit apparaat hebt uitgevoerd terwijl u online was (d.w.z. PowerApps verbergt alle apps die nog niet op uw apparaat zijn gedownload).
7. Voer de app nogmaals uit.
8. Merk op hoe de app de verbindingsstatus **Offline** correct weergeeft.
9. Stel een nieuwe tweet op. De tweet wordt lokaal opgeslagen in de **LocalTweetsToPost**-verzameling.
10. Schakel de vliegtuigmodus uit. Nadat de timer is geactiveerd, post de app de tweet.

We hopen dat dit artikel u een idee geeft van de mogelijkheden die PowerApps biedt voor het bouwen van offline-apps. Zoals altijd kunt u feedback geven in ons [forum](https://powerusers.microsoft.com/t5/PowerApps-Forum/bd-p/PowerAppsForum1) en uw voorbeelden van offline-apps delen in de [PowerApps-communityblog](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/bg-p/PowerAppsBlog).

