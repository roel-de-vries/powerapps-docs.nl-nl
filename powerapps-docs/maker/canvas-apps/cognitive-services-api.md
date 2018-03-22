---
title: Cognitive Services gebruiken in PowerApps | Microsoft Docs
description: Maak een eenvoudige app die de tekstanalyse-API van Microsoft Cognitive Services gebruikt om tekst te analyseren.
services: ''
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/08/2017
ms.author: mblythe
ms.openlocfilehash: 2e82feb9df4121b24ffd1f5cad7669c6aa58c8e8
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="use-cognitive-services-in-powerapps"></a>Cognitive Services gebruiken in PowerApps
In dit artikel leert u hoe u een eenvoudige app kunt maken die de tekstanalyse-API van [Microsoft Cognitive Services](https://docs.microsoft.com/azure/cognitive-services/text-analytics/overview) gebruikt om tekst te analyseren. We laten u zien hoe u de tekstanalyse-API kunt instellen en hoe u deze aan de [connector voor tekstanalyse](https://docs.microsoft.com/connectors/cognitiveservicestextanalytics/) kunt koppelen. Vervolgens laten we u zien hoe u een app kunt maken die de API oproept.

> [!NOTE]
> We raden u aan om [Een volledig nieuwe app maken](get-started-create-from-blank.md) te lezen voordat u dit artikel leest als u nog niet eerder apps in PowerApps hebt gemaakt.

## <a name="introduction-to-microsoft-cognitive-services"></a>Kennismaking met Microsoft Cognitive Services
Microsoft Cognitive Services vormt een reeks API's, SDK's en services om uw applicaties slimmer, meer betrokken en vindbaar te maken. Deze services stellen u in staat om gemakkelijk intelligente functies, zoals emotie- en videodetectie, gezichts-, spraak- en zichtherkenning, en kennis van spraak en taal, aan uw applicaties toe te voegen.

We richten ons in dit artikel op 'taalbegrip' en gebruiken de tekstanalyse-API. Deze API stelt u in staat om stemming, sleutelfrasen, onderwerpen en taal in uw tekst te detecteren. Laten we beginnen met een demo van de API en ons daarna aanmelden voor een preview-versie.

### <a name="try-out-the-text-analytics-api"></a>De tekstanalyse-API verkennen
De API heeft een online demo, zodat u kunt zien hoe deze werkt. Kijk ook naar de JSON die door de service wordt geretourneerd.

1. Ga naar de pagina [Tekstanalyse-API](https://azure.microsoft.com/services/cognitive-services/text-analytics/).

2. Gebruik in de sectie **Zie het in actie** de voorbeeldtekst of voer uw eigen tekst in. Klik of tik vervolgens op **analyseren**. 
   
    ![Demo van Tekstanalyse-API](./media/cognitive-services-api/text-analytics-demo.png)

3. De pagina geeft opgemaakte resultaten weer op het tabblad **Geanalyseerde tekst** en het JSON-antwoord op het tabblad **JSON**. [JSON](http://json.org/) is een manier om gegevens weer te geven. In dit geval zijn het gegevens die door de tekstanalyse-API zijn geretourneerd.

## <a name="sign-up-for-the-text-analytics-api"></a>Aanmelden voor de tekstanalyse-API
De API is beschikbaar als gratis preview en gekoppeld aan een Azure-abonnement. U beheert de API via de Azure Portal.

1. [Meld u aan voor een gratis abonnement](https://azure.microsoft.com/free/) als u nog geen Azure-abonnement hebt.

2. Meld u aan bij uw Azure-account.

3. Ga in de Azure Portal naar [Cognitive Services-blade maken](https://go.microsoft.com/fwlink/?LinkId=761108).

4. Vul informatie in voor de tekstanalyse-API, zoals in de volgende afbeelding. Selecteer de prijscategorie **F0** (gratis).
   
    ![Tekstanalyse-API maken](./media/cognitive-services-api/azure-create.png)

5. Klik of tik in de linkerbenedenhoek op **Maken**.

6. Klik of tik op het **Dashboard** op de API die u zojuist hebt gemaakt.
   
    ![Azure-dashboard](./media/cognitive-services-api/azure-dashboard.png)

7. Klik of tik op **Sleutels**.
   
    ![Menu van Azure](./media/cognitive-services-api/azure-menu-keys.png)

8. Kopieer een van de sleutels aan de rechterkant van het scherm. U gebruikt deze sleutel later als u een verbinding met de API maakt.
   
    ![API-sleutels](./media/cognitive-services-api/azure-keys.png)

## <a name="build-the-app"></a>De app bouwen
U hebt nu de tekstanalyse-API aan de praat gekregen en kunt deze nu via PowerApps koppelen en een app maken die de API aanroept. Dit is een app met één scherm die dezelfde functionaliteit biedt als de demo op de pagina Tekstanalyse-API. Laten we beginnen met het bouwen!

### <a name="create-the-app-and-add-a-connection"></a>De app maken en een verbinding toevoegen
U maakt eerst een lege telefoonapp en voegt een verbinding met de **Tekstanalyse**-connector toe. Raadpleeg [Een volledig nieuwe app maken](get-started-create-from-blank.md) en [Uw verbindingen beheren in PowerApps](add-manage-connections.md) als u meer informatie over deze taken wilt.

1. In [web.powerapps.com](https://web.powerapps.com) kiest u **Beginnen met een lege app** > ![pictogram telefoon-app](./media/cognitive-services-api/icon-phone-app.png) (telefoonnummer) > **Deze app maken**.

    ![Beginnen met een lege app](./media/cognitive-services-api/start-from-blank.png)

2. Kies in het middelste deelvenster van de PowerApps Studio **Verbinding maken met gegevens**.

3. Klik of tik in het deelvenster **Gegevens** op **Nieuwe verbinding** > **Tekstanalyse**.

4. Kopieer uw sleutel naar **Accountsleutel** en klik of tik vervolgens op **Maken**.
   
    ![Tekstanalyse-connector](./media/cognitive-services-api/create-connection-ta.png)

### <a name="add-controls-to-the-app"></a>Besturingselementen toevoegen aan de app
De volgende stap voor het maken van de app bestaat uit het toevoegen van alle besturingselementen. Normaal gesproken als ik apps bouw, voeg ik gaandeweg formules aan de besturingselementen toe. In dit geval richten we ons eerst op de besturingselementen en voegen we in het volgende deel een paar formules toe. In de volgende afbeelding ziet u de app met alle besturingselementen.

![Voltooide app](./media/cognitive-services-api/finished-app-no-data.png)

Volg de onderstaande stappen om dit scherm te maken. Als er een naam voor een besturingselement wordt opgegeven, wordt die naam in een formule in het volgende deel gebruikt.

1. Klik op het tabblad **Start** op **Nieuw scherm** en vervolgens op **Doorscrolbaar scherm**. 

2. Selecteer op **Scherm2** **[Titel]** en wijzig deze in **Tekstanalyse**.

3. Voeg een besturingselement **Label** toe voor de inleidende tekst.

4. Voeg een besturingselement **Tekstinvoer** toe, zodat u tekst kunt invoeren die moet worden geanalyseerd. Noem het besturingselement **tiTekstVoorAnalyse**. De app moet er nu uitzien zoals in de volgende afbeelding.
   
    ![App met titel, subtitel en tekstinvoer](./media/cognitive-services-api/partial-app-step1.png)

5. Voeg drie **Selectievakje**-besturingselementen toe, zodat u kunt kiezen welke API-bewerkingen moeten worden uitgevoerd. Noem de besturingselementen **chkTaal**, **chkFrasen** en **chkStemming**.

6. Voeg een knop toe, zodat u de API kunt aanroepen nadat is geselecteerd welke bewerkingen moeten worden uitgevoerd. De app moet er nu uitzien zoals in de volgende afbeelding.
   
    ![App met selectievakjes en knop](./media/cognitive-services-api/partial-app-step2.png)

7. Voeg drie **Label**-besturingselementen toe. De eerste twee bevatten de resultaten van de API-oproepen voor taal en stemming. De derde is alleen een inleiding voor de galerie aan de onderkant van het scherm.

8. Voeg een besturingselement **Lege verticale galerie** toe en voeg daarna een besturingselement **Label** aan de galerie toe. De galerie bevat de resultaten voor de API-aanroep voor sleutelfrasen. De app moet er nu uitzien zoals in de volgende afbeelding.
   
    ![App met labels en galerie](./media/cognitive-services-api/partial-app-step3.png)

9. Selecteer in het linkerdeelvenster **Scherm1** > beletselteken (**...**) > **Verwijderen** (u hebt dit scherm niet nodig voor de app).

We houden deze app eenvoudig en richten ons op het aanroepen van de tekstanalyse-API. U kunt echter items toevoegen, zoals logica voor het weergeven en verbergen van besturingselementen op basis van de geselecteerde selectievakjes, foutafhandeling als de gebruiker geen opties selecteert, enzovoort.

### <a name="add-logic-to-make-the-right-api-calls"></a>Logica toevoegen om de juiste API-aanroepen te doen
U hebt nu een app die er goed uitziet, maar hij doet nog niets. Dat gaan we zo oplossen. Voordat we echter in detail treden, moeten we eerst begrijpen welk patroon de app volgt:

1. De app doet specifieke API-aanroepen op basis van de selectievakjes die in de app zijn geselecteerd. Als u op **Tekst analyseren** klikt of tikt, doet de app 1, 2 of 3 API-aanroepen.

2. De app slaat gegevens op die de API retourneert, in drie verschillende [verzamelingen](working-with-variables.md#create-a-collection) op: **languageCollect**, **sentimentCollect** en **phrasesCollect**.

3. De eigenschap **Tekst** voor twee van de labels en de eigenschap **Items** voor de galerie worden door de app bijgewerkt op basis van de inhoud van de drie verzamelingen.

Laten we vanuit die gedachte de formule voor de eigenschap **OnSelect** van de knop toevoegen. Hier gebeurt alles.

```
If(chkLanguage.Value=true,

        ClearCollect(languageCollect, TextAnalytics.DetectLanguage({numberOfLanguagesToDetect:1, text:tiTextToAnalyze.Text}).detectedLanguages.name)

);

If(chkPhrases.Value=true,

        ClearCollect(phrasesCollect, TextAnalytics.KeyPhrases({language:"en", text:tiTextToAnalyze.Text}).keyPhrases)

);

If(chkSentiment.Value=true,

        ClearCollect(sentimentCollect, TextAnalytics.DetectSentiment({language:"en", text:tiTextToAnalyze.Text}).score)

)
```

Er gebeurt nogal wat, dus laten we de inhoud even opsplitsen:

* De **If**-instructies zijn simpel: als er een specifiek selectievakje wordt geselecteerd, moet de API-aanroep voor die bewerking worden uitgevoerd.

* Geef binnen elke aanroep de juiste parameters op:

  * U specificeert in alle drie de aanroepen **tiTextToAnalyze.Text** als de invoertekst.

  * In **DetectLanguage()** programmeert u **numberOfLanguagesToDetect** als 1, maar u kunt deze parameter doorgeven op basis van bepaalde logica in de app.

  * In **KeyPhrases()** en **DetectSentiment()**, wordt**taal** in code vastgelegd als "en", maar u kunt deze parameter doorgeven op basis van bepaalde logica in de app. U kunt bijvoorbeeld eerst de taal detecteren en vervolgens deze parameter instellen op basis van wat **DetectLanguage()** retourneert.

* Voeg voor elke aanroep die plaatsvindt de resultaten toe aan de juiste verzameling:

    * Voor **languageCollect** voegt u de **naam** toe van de taal die in de tekst werd geïdentificeerd.

    * Voor **phrasesCollect** voegt u de **sleutelzinnen** toe die in de tekst werden geïdentificeerd.

    * Voor **sentimentCollect** voegt u de **score** voor de stemming in de tekst toe; deze is een waarde van 0-1, waarbij 1 100% positief betekent.

### <a name="display-the-results-of-the-api-calls"></a>De resultaten van de API-aanroepen weergeven
U kunt de resultaten van de API-aanroepen weergeven door in elk besturingselement naar de juiste verzameling te verwijzen:

1. Stel de eigenschap **Tekst** van het taallabel in op: `"The language detected is " & First(languageCollect).name`.
   
    De functie **First()** retourneert de eerste (en in dit geval de enige) record in **languageCollect**. Vervolgens geeft de app de **naam** (het enige veld) weer die aan deze record is gekoppeld.

2. Stel de eigenschap **Tekst** van het label voor stemming in op: `"The sentiment score is " & Round(First(sentimentCollect.Value).Value, 3)\*100 & "% positive."`.
   
    Deze formule gebruikt ook de functie **First()**, haalt de **waarde** (0-1) van de eerste en enige record op en maakt deze vervolgens op als percentage.

3. Stel de eigenschap **Items** van de galerie voor sleutelzinnen in op: `phrasesCollect`.
   
    U werkt nu met een galerie en hebt dus niet de functie **First()** nodig om een enkele waarde op te halen. U verwijst naar de verzameling. De galerie geeft de sleutelzinnen weer als een lijst.

## <a name="run-the-app"></a>De app uitvoeren

Nu de app is voltooid, voert u deze uit om te zien hoe deze werkt: klik of tik op de knop Uitvoeren in de rechterbovenhoek. ![De app uitvoeren](./media/cognitive-services-api/icon-run-app.png). In de volgende afbeelding zijn alle drie de opties geselecteerd en is de tekst hetzelfde als de standaardtekst op de pagina Tekstanalyse-API.

![Voltooide app met gegevens](./media/cognitive-services-api/finished-app.png)

Als u de uitvoer van deze app met de pagina Tekstanalyse-API aan het begin van dit artikel vergelijkt, ziet u dat we dezelfde resultaten krijgen.

We hopen dat u nu iets meer begrijpt van de tekstanalyse-API en dat u het leuk vond om te zien hoe deze in een app kan worden opgenomen. We horen het graag als er andere Cognitive Services (of andere services in het algemeen) zijn waar we op in moeten gaan in onze artikelen. Laat zoals altijd uw feedback en eventuele vragen achter in de opmerkingen.

