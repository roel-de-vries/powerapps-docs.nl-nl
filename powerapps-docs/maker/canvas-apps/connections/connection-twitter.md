---
title: Overzicht van de Twitter-verbinding | Microsoft Docs
description: Lees hoe u verbinding maakt met Twitter, doorloop enkele voorbeelden en bekijk alle functies
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/12/2017
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 2ab480b0bb2aa61c65e33f67cca5a3b0974ca2c8
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42834521"
---
# <a name="connect-to-twitter-from-powerapps"></a>Verbinding maken met Twitter vanuit PowerApps
![Twitter](./media/connection-twitter/twittericon.png)

Met Twitter kunt u tweets posten en tweets, de tijdlijn, vrienden en volgers ophalen uit uw Twitter-account.

U kunt deze gegevens in een label in uw app weergeven. U kunt bijvoorbeeld een invoertekstvak toevoegen, de gebruiker vragen tekst voor een tweet in te voeren en vervolgens een knop toevoegen die de tweet 'post'. U kunt vergelijkbare methoden gebruiken om een tweet op te halen of naar een tweet te zoeken en vervolgens de tekst weer te geven in een tekstvak of galeriebesturingselement in uw app.

In dit onderwerp wordt uitgelegd hoe u de Twitter-verbinding maakt en hoe u de Twitter-verbinding gebruikt in een app en worden de beschikbare functies toegelicht.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="connect-to-twitter"></a>Verbinding maken met Twitter
1. Open PowerApps, selecteer **Nieuw** en maak vervolgens een **lege app**. Kies de telefoon- of tabletindeling. De tabletindeling biedt meer werkruimte:  

   ![Een lege app openen](./media/connection-twitter/blank-app.png)
2. Klik of tik in het rechterdeelvenster op het tabblad **Gegevens** en klik of tik vervolgens op **Gegevensbron toevoegen**.
3. Selecteer **Nieuwe verbinding** en selecteer vervolgens **Twitter**:  

    ![Verbinding maken met Twitter](./media/connection-twitter/addconnection.png)

    ![Verbinding maken met Twitter](./media/connection-twitter/add-twitter.png)
4. Selecteer **Verbinden**, voer uw aanmeldingsgegevens van Twitter in en selecteer **App machtigen**.
5. Selecteer **Een gegevensbron toevoegen**. De verbinding wordt weergegeven onder **Gegevensbronnen**:  
    ![Sluit het deelvenster Opties](./media/connection-twitter/twitterdatasource.png)

De Twitter-verbinding is gemaakt en aan uw app toegevoegd. U kunt de verbinding nu gebruiken.

## <a name="use-the-twitter-connection-in-your-app"></a>De Twitter-verbinding in uw app gebruiken
### <a name="show-a-timeline"></a>Een tijdlijn weergeven
1. Selecteer **Galerie** in het menu **Invoegen** en voeg een van de galeries van het type **Met tekst** toe.
2. We gaan enkele tijdlijnen weergeven:  

   * Als u de tijdlijn van de huidige gebruiker wilt weergeven, stelt u de eigenschap **[Items](../controls/properties-core.md)** van de galerie in op de volgende formules:

       `Twitter.HomeTimeline().TweetText`  
       `Twitter.HomeTimeline({maxResults:3}).TweetText`  
   * Als u de tijdlijn van een andere gebruiker wilt weergeven, stelt u de eigenschap **[Items](../controls/properties-core.md)** van de galerie in op de volgende formule:  

       `Twitter.UserTimeline( *TwitterHandle* ).TweetText`

       Voer een Twitter-handle tussen dubbele aanhalingstekens of een equivalente waarde in. Voer bijvoorbeeld `"satyanadella"` of `"powerapps"` rechtstreeks in de formule-expressie in.
   * Voeg een besturingselement voor tekstinvoer met de naam **Tweep** toe en stel de eigenschap Standaard in op `Tweep.Text`. Typ in het tekstvak Tweep een Twitter-handle zoals `satyanadella` (zonder aanhalingstekens en zonder het @-teken).

       Stel in het galeriebesturingselement de eigenschap Items in op de volgende formule:  

       `Twitter.UserTimeline(Tweep.Text, {maxResults:5}).TweetText`

       De tweets van de ingevoerde Twitter-handle worden automatisch weergegeven in het galeriebesturingselement.

     > [!TIP]
     > Sommige van deze formules gebruiken het argument **maxResults** om de *x* meest recente tweets in een tijdlijn weer te geven.
3. Stel de eigenschap **Items** van de galerie in op `Twitter.HomeTimeline()`.

    Als u de galerie selecteert, ziet u in het deelvenster aan de rechterkant de opties voor de galerie.
4. Selecteer **TweetText** in de eerste lijst, selecteer **TweetedBy** in de tweede lijst en selecteer **CreatedAt** in de derde lijst.

    In de galerie worden nu de waarden van de gekozen eigenschappen weergegeven.

### <a name="show-followers"></a>Volgers weergeven
1. Met behulp van een galerie van het type **Met tekst** kunt u enkele volgers weergeven:  

   * Als u de volgers van de huidige gebruiker wilt weergeven, stelt u de eigenschap **[Items](../controls/properties-core.md)** van de galerie in op de volgende formule:  

       `Twitter.MyFollowers()`  
       `Twitter.MyFollowers({maxResults:3})`
   * Als u de volgers van een andere gebruiker wilt weergeven, stelt u de eigenschap **[Items](../controls/properties-core.md)** van de galerie in op de volgende formule:  

       `Twitter.Followers( *TwitterHandle* )`

       Voer een Twitter-handle tussen dubbele aanhalingstekens of een equivalente waarde in. Voer bijvoorbeeld `"satyanadella"` of `"powerapps"` rechtstreeks in de formule-expressie in.
   * Voeg een besturingselement voor tekstinvoer met de naam **Tweep** toe en stel de eigenschap Standaard in op `Tweep.Text`. Typ in het tekstvak Tweep een Twitter-handle zoals `satyanadella` (zonder aanhalingstekens en zonder het @-teken).

       Stel in het galeriebesturingselement de eigenschap Items in op de volgende formule:  

       `Twitter.Followers(Tweep.Text, {maxResults:5})`

       In het galeriebesturingselement wordt automatisch weergegeven wie de ingevoerde Twitter-handle volgen.

     > [!TIP]
     > Sommige van deze formules gebruiken het argument **maxResults** om de *x* meest recente tweets in een tijdlijn weer te geven.
2. Stel de eigenschap **Items** van de galerie in op `Twitter.MyFollowers()`.

    Als u de galerie selecteert, ziet u in het deelvenster aan de rechterkant de opties voor de galerie.
3. Selecteer **UserName** in de tweede lijst en selecteer **FullName** in de derde lijst.

    In de galerie worden nu de waarden van de gekozen eigenschappen weergegeven.

### <a name="show-followed-users"></a>Gevolgde gebruikers weergeven
1. Met behulp van een galerie van het type **Met tekst** kunt u enkele gevolgde gebruikers weergeven:  

   * Als u wilt weergeven welke gebruikers de huidige gebruiker volgt, stelt u de eigenschap **[Items](../controls/properties-core.md)** van de galerie in op de volgende formule:  

       `Twitter.MyFollowing()`  
       `Twitter.MyFollowing({maxResults:3})`
   * Als u wilt weergeven welke gebruikers een andere gebruiker volgt, stelt u de eigenschap **[Items](../controls/properties-core.md)** van de galerie in op de volgende formule:

       `Twitter.Following( *TwitterHandle* )`

       Voer een Twitter-handle tussen dubbele aanhalingstekens of een equivalente waarde in. Voer bijvoorbeeld `"satyanadella"` of `"powerapps"` rechtstreeks in de formule-expressie in.
   * Voeg een besturingselement voor tekstinvoer met de naam **Tweep** toe en stel de eigenschap Standaard in op `Tweep.Text`. Typ in het tekstvak Tweep een Twitter-handle zoals `satyanadella` (zonder aanhalingstekens en zonder het @-teken).

       Stel in het galeriebesturingselement de eigenschap Items in op de volgende formule:  

       `Twitter.Following(Tweep.Text, {maxResults:5})`

       In het galeriebesturingselement worden automatisch de andere handles die u volgt weergegeven.

     Als u de galerie selecteert, ziet u in het deelvenster aan de rechterkant de opties voor de galerie.
2. Selecteer **Description** in de lijst **Body1**, **UserName** in de lijst **Heading1** en **FullName** in de lijst **Subtitle1**.

    In de galerie worden nu de waarden van de gekozen eigenschappen weergegeven.

### <a name="show-information-about-a-user"></a>Gegevens over een gebruiker weergeven
Voeg een label toe en stel vervolgens de eigenschap **[Text](../controls/properties-core.md)** in op een van deze formules:  

* `twitter.User( *TwitterHandle* ).Description`
* `twitter.User( *TwitterHandle* ).FullName`
* `twitter.User( *TwitterHandle* ).Location`
* `twitter.User( *TwitterHandle* ).UserName`
* `twitter.User( *TwitterHandle* ).FollowersCount`
* `twitter.User( *TwitterHandle* ).FriendsCount`
* `twitter.User( *TwitterHandle* ).Id`
* `twitter.User( *TwitterHandle* ).StatusesCount`

Voer een Twitter-handle tussen dubbele aanhalingstekens of een equivalente waarde in. Voer bijvoorbeeld `"satyanadella"` of `"powerapps"` rechtstreeks in de formule-expressie in.

U kunt ook een besturingselement voor tekstinvoer gebruiken om een Twitter-handle te typen zoals we in dit onderwerp hebben gedaan.

### <a name="search-tweets"></a>Tweets zoeken
1. Gebruik een galerie van het type **Met tekst** en stel de eigenschap **[Items](../controls/properties-core.md)** in op de volgende formule:  

    `Twitter.SearchTweet( *SearchTerm* ).TweetText`

    Voer een *zoekterm* tussen dubbele aanhalingstekens in of door te verwijzen naar een equivalente waarde. Voer bijvoorbeeld `"PowerApps"` of `"microsoft"` rechtstreeks in de formule in.

    U kunt ook een besturingselement voor **tekstinvoer** gebruiken om een zoekterm op te geven zoals we in dit onderwerp hebben gedaan.

    > [!TIP]
   > Geef de eerste vijf resultaten weer met behulp van maxResults:  

    `Twitter.SearchTweet(SearchTerm.Text, {maxResults:5}).TweetText`
2. Stel de eigenschap **Items** van de galerie in op `Twitter.SearchTweet(SearchTerm.Text, {maxResults:5})`.

    Als u de galerie selecteert, ziet u in het deelvenster aan de rechterkant de opties voor de galerie.
3. Selecteer **TweetText** in de eerste lijst, **TweetedBy** in de tweede lijst en **CreatedAt** in de derde lijst.

    In de galerie worden nu de waarden van de gekozen eigenschappen weergegeven.

### <a name="send-a-tweet"></a>Een tweet verzenden
1. Voeg een besturingselement voor tekstinvoer toe en wijzig de naam in **MijnTweet**.
2. Voeg een knop toe en stel de eigenschap **[OnSelect](../controls/properties-core.md)** in op de volgende formule:  
    `Twitter.Tweet({tweetText: MyTweet.Text})`
3. Druk op F5 of selecteer de knop Voorbeeld (![](./media/connection-twitter/preview.png)). Typ tekst in **MijnTweet** en selecteer de knop om de ingevoerde tekst te twitteren.
4. Druk op Esc om terug te gaan naar de standaardwerkruimte.

## <a name="view-the-available-functions"></a>De beschikbare functies weergeven
Deze verbinding bevat de volgende functies:

| Functienaam | Beschrijving |
| --- | --- |
| [UserTimeline](connection-twitter.md#usertimeline) |Haalt een verzameling met de meest recente tweets van de opgegeven gebruiker op |
| [HomeTimeline](connection-twitter.md#hometimeline) |Haalt de meest recente tweets en retweets van mij en mijn volgers op |
| [SearchTweet](connection-twitter.md#searchtweet) |Haalt een verzameling relevante tweets op die overeenkomen met een opgegeven query |
| [Followers](connection-twitter.md#followers) |Haalt gebruikers op die de opgegeven gebruiker volgen |
| [MyFollowers](connection-twitter.md#myfollowers) |Haalt gebruikers op die mij volgen |
| [Following](connection-twitter.md#following) |Haalt gebruikers op die de opgegeven gebruiker volgt |
| [MyFollowing](connection-twitter.md#myfollowing) |Haalt gebruikers op die ik volg |
| [User](connection-twitter.md#user) |Haalt gegevens op over de opgegeven gebruiker (voorbeeld: gebruikersnaam, beschrijving, aantal volgers enzovoort) |
| [Tweet](connection-twitter.md#tweet) |Twitteren |
| [OnNewTweet](connection-twitter.md#onnewtweet) |Activeert een werkstroom wanneer een nieuwe tweet wordt gepost die overeenkomt met uw zoekopdracht |

### <a name="usertimeline"></a>UserTimeline
Tijdlijn van gebruiker ophalen: Haalt een verzameling met de meest recente tweets van de opgegeven gebruiker op

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| userName |Tekenreeks |Ja |Twitter-handle |
| maxResults |Geheel getal |Nee |Maximum aantal tweets dat moet worden opgehaald, bijvoorbeeld {maxResults:5} |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| TweetText |Tekenreeks |Ja | |
| TweetId |Tekenreeks |Nee | |
| CreatedAt |Tekenreeks |Nee | |
| RetweetCount |Geheel getal |Ja | |
| TweetedBy |Tekenreeks |Ja | |
| MediaUrls |Matrix |Nee | |

### <a name="hometimeline"></a>HomeTimeline
Eigen tijdlijn ophalen: haalt de meest recente tweets en retweets van mij en mijn volgers op

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| maxResults |Geheel getal |Nee |Maximum aantal tweets dat moet worden opgehaald, bijvoorbeeld {maxResults:5} |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| TweetText |Tekenreeks |Ja | |
| TweetId |Tekenreeks |Nee | |
| CreatedAt |Tekenreeks |Nee | |
| RetweetCount |Geheel getal |Ja | |
| TweetedBy |Tekenreeks |Ja | |
| MediaUrls |Matrix |Nee | |

### <a name="searchtweet"></a>SearchTweet
Tweet zoeken: haalt een verzameling relevante tweets op die overeenkomen met een opgegeven query

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| searchQuery |Tekenreeks |Ja |Querytekst (u kunt elke query-operator gebruiken die door Twitter wordt ondersteund: http://www.twitter.com/search) |
| maxResults |Geheel getal |Nee |Maximum aantal tweets dat moet worden opgehaald, bijvoorbeeld {maxResults:5} |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| TweetText |Tekenreeks |Ja | |
| TweetId |Tekenreeks |Nee | |
| CreatedAt |Tekenreeks |Nee | |
| RetweetCount |Geheel getal |Ja | |
| TweetedBy |Tekenreeks |Ja | |
| MediaUrls |Matrix |Nee | |

### <a name="followers"></a>Followers
Volgers ophalen: haalt gebruikers op die de opgegeven gebruiker volgen

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| userName |Tekenreeks |Ja |Twitter-handle van de gebruiker |
| maxResults |Geheel getal |Nee |Maximum aantal gebruikers dat moet worden opgehaald, bijvoorbeeld {maxResults:5} |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| FullName |Tekenreeks |Ja | |
| Locatie |Tekenreeks |Ja | |
| Id |Geheel getal |Nee | |
| UserName |Tekenreeks |Ja | |
| FollowersCount |Geheel getal |Nee | |
| Beschrijving |Tekenreeks |Ja | |
| StatusesCount |Geheel getal |Nee | |
| FriendsCount |Geheel getal |Nee | |

### <a name="myfollowers"></a>MyFollowers
Mijn volgers ophalen: haalt gebruikers op die mij volgen

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| maxResults |Geheel getal |Nee |Maximum aantal gebruikers dat moet worden opgehaald, bijvoorbeeld {maxResults:5} |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| FullName |Tekenreeks |Ja | |
| Locatie |Tekenreeks |Ja | |
| Id |Geheel getal |Nee | |
| UserName |Tekenreeks |Ja | |
| FollowersCount |Geheel getal |Nee | |
| Beschrijving |Tekenreeks |Ja | |
| StatusesCount |Geheel getal |Nee | |
| FriendsCount |Geheel getal |Nee | |

### <a name="following"></a>Following
Gevolgde gebruikers ophalen: haalt gebruikers op die de opgegeven gebruiker volgt

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| userName |Tekenreeks |Ja |Twitter-handle van de gebruiker |
| maxResults |Geheel getal |Nee |Maximum aantal gebruikers dat moet worden opgehaald, bijvoorbeeld {maxResults:5} |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| FullName |Tekenreeks |Ja | |
| Locatie |Tekenreeks |Ja | |
| Id |Geheel getal |Nee | |
| UserName |Tekenreeks |Ja | |
| FollowersCount |Geheel getal |Nee | |
| Beschrijving |Tekenreeks |Ja | |
| StatusesCount |Geheel getal |Nee | |
| FriendsCount |Geheel getal |Nee | |

### <a name="myfollowing"></a>MyFollowing
Mijn gevolgde gebruikers ophalen: haalt gebruikers op die ik volg

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| maxResults |Geheel getal |Nee |Maximum aantal gebruikers dat moet worden opgehaald, bijvoorbeeld {maxResults:5} |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| FullName |Tekenreeks |Ja | |
| Locatie |Tekenreeks |Ja | |
| Id |Geheel getal |Nee | |
| UserName |Tekenreeks |Ja | |
| FollowersCount |Geheel getal |Nee | |
| Beschrijving |Tekenreeks |Ja | |
| StatusesCount |Geheel getal |Nee | |
| FriendsCount |Geheel getal |Nee | |

### <a name="user"></a>User
Gebruiker ophalen: haalt gegevens op over de opgegeven gebruiker (voorbeeld: gebruikersnaam, beschrijving, aantal volgers, enzovoort)

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| userName |Tekenreeks |Ja |Twitter-handle van de gebruiker |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| FullName |Tekenreeks |Ja | |
| Locatie |Tekenreeks |Ja | |
| Id |Geheel getal |Nee | |
| UserName |Tekenreeks |Ja | |
| FollowersCount |Geheel getal |Nee | |
| Beschrijving |Tekenreeks |Ja | |
| StatusesCount |Geheel getal |Nee | |
| FriendsCount |Geheel getal |Nee | |

### <a name="tweet"></a>Twitteren
Een nieuwe tweet posten: twitteren

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| tweetText |Tekenreeks |Nee |Tekst die moet worden gepost, bijvoorbeeld {tweetText:"Hallo"} |
| body |Tekenreeks |Nee |Media die moeten worden gepost |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| TweetId |Tekenreeks |Ja | |

### <a name="onnewtweet"></a>OnNewTweet
Wanneer een nieuwe tweet verschijnt: activeert een werkstroom wanneer een nieuwe tweet wordt gepost die overeenkomt met uw zoekopdracht

#### <a name="input-properties"></a>Invoereigenschappen

| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| searchQuery |Tekenreeks |Ja |Querytekst (u kunt elke query-operator gebruiken die door Twitter wordt ondersteund: http://www.twitter.com/search) |

#### <a name="output-properties"></a>Uitvoereigenschappen

| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| value |Matrix |Nee | |

## <a name="helpful-links"></a>Nuttige koppelingen
Bekijk alle [beschikbare verbindingen](../connections-list.md).  
Meer informatie over het [toevoegen van verbindingen](../add-manage-connections.md) aan uw apps.

