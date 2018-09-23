---
title: Preview-functies en experimentele functies | Microsoft Docs
description: Test nieuwe functies en neem deze op in apps.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/16/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 741cec402c6a5b5ea30700badd265f5e950203e9
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42858470"
---
# <a name="understand-experimental-and-preview-features-in-powerapps"></a>Experimentele functies en preview-functies in PowerApps

Met elke release brengen we wijzigingen aan en voegen we functies toe om PowerApps nog beter te maken en op uw behoeften af te stemmen. We blijven het product voortdurend verbeteren.  

We nemen compatibiliteit met eerdere versies zeer serieus. Met wijzigingen of verbeteringen kunnen echter onbedoelde neveneffecten optreden die er voor zorgen dat uw app niet meer precies werkt als voorheen.

Om deze neveneffecten bij bestaande apps zo veel mogelijk te vermijden, moeten grotere functies meerdere fasen doorlopen. In dit artikel wordt deze procedure beschreven en wordt uitgelegd hoe u de blootstelling aan functies die nog in ontwikkeling zijn, kunt regelen.

## <a name="feature-roll-out-stages"></a>Implementatiefasen voor functies

Functies doorlopen drie fasen voordat ze officieel onderdeel van een product worden:

1. **Experimenteel**: er wordt aan de functie gewerkt. Vertrouw nog niet te veel op de functie. Deze kan nog op veel punten worden gewijzigd.
1. **Preview**: de functie is bijna klaar en is stabiel. U kunt nu bestaande apps naar deze functie gaan migreren.
1. **Geïmplementeerd**: de functie is gereed. De functie is voor alle apps ingeschakeld en kan niet worden uitgeschakeld.

Bij elke opeenvolgende fase neemt het aantal gebruikers van de functie toe, zodat we kunnen controleren of de functie aansluit op uw behoeften en of er geen onbedoelde neveneffecten optreden.

**Uw feedback is essentieel bij deze procedure.**  Plaats uw feedback in het [forum voor de PowerApps-community](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1).

Hoe lang blijft een functie in elke fase? Dit verschilt per functie. We kijken naar vele factoren, waaronder het aantal apps dat gebruikmaakt van de functie, het aantal problemen dat wordt gerapporteerd en hoe dringend de behoefte naar de functie is. Functies kunnen een aantal weken tot vele maanden in een fase blijven.

U kunt aan de hand van de volgende tabel bepalen welke fase u moet hanteren: 

| Fase | Wanneer kan ik dat het beste gebruiken? | Kan ik de functie probleemloos gebruiken? | Wordt de functie standaard ingeschakeld voor nieuwe apps? | 
|----|----|----|-----|------|
| **Experimenteel** | Als u graag in een vroeg stadium instapt, de functie nuttig vindt en graag meehelpt om de functie te testen. | Nee.  Experimentele functies kunnen fundamentele wijzigingen ondergaan of op elk moment volledig uit de roulatie worden genomen. | Nee. U moet u expliciet aanmelden voor de functie.  |  
| **Preview** | De functie wordt automatisch in nieuwe apps opgenomen.  Begin met het inschakelen en testen van de functie in bestaande apps, omdat de functie uiteindelijk ook voor die apps wordt ingeschakeld. | Ja. Deze functie wordt uiteindelijk een definitief onderdeel van het product.  | Ja. Mogelijk wilt u de functie uitschakelen als er een probleem optreedt.  Rapporteer problemen. Dit is de belangrijkste reden waarom de functie in de preview-fase zit. | 
| **Geïmplementeerd** (wordt niet meer weergegeven in **Geavanceerde instellingen**) | Alle apps hebben deze functie. | Ja. | Ja.  De meeste functies kunnen niet worden uitgeschakeld.  |  

Tegen het einde van de preview-fase is het mogelijk dat we de functie voor alle apps één keer inschakelen en aangeven dat voor de functie de **laatste validatie** wordt uitgevoerd.  Op deze manier krijgen veel gebruikers de laatste kans om de functie uit te proberen en kunnen ze de functie nog steeds uitschakelen. Tijdige feedback is van essentieel belang in deze periode, omdat de functie in de volgende fase volledig is geïmplementeerd en u deze niet kunt uitschakelen.  

## <a name="documentation"></a>Documentatie

Waar vindt u informatie over deze functies?  We behandelen preview-functies als voltooide functies en u kunt hierover, net als voor alle andere productfuncties, meer informatie vinden: 
- [PowerApps-documentatie](https://docs.microsoft.com/powerapps/maker/canvas-apps/getting-started). Wij stellen de basisinformatie voor de nieuwe functie beschikbaar: de voordelen, hoe u aan de slag gaat en naslaginformatie.
- [Forum van de PowerApps-community](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1).  U gaat de nieuwe functie samen met anderen verkennen. Leer van hun ervaringen en deel uw ervaringen met hen.
- [PowerApps-blog](https://powerapps.microsoft.com/blog/).  Wanneer er een nieuwe functie in gebruik wordt genomen, wordt hierover vaak, maar niet altijd, een blogpost geplaatst.

Experimentele functies zijn anders.  Het zijn functies waaraan wordt gewerkt en we beschouwen ze niet als voltooid. De korte beschrijving in het deelvenster **App-instellingen** (zie hieronder) is mogelijk de enige informatie over de functie. Experimentele functies worden normaal gesproken niet in de documentatie beschreven. Het communityforum is waarschijnlijk uw beste informatiebron.  In sommige gevallen wordt de functie in een vroegtijdige blogpost beschreven.  Als u onvoldoende informatie vindt, kunt u vragen stellen in de forums of wachten totdat de functie naar de preview-fase overgaat.

## <a name="controlling-which-features-are-enabled"></a>Bepalen welke functies worden ingeschakeld

Experimentele functies en preview-functies worden in de **geavanceerde instellingen** van de app vermeld.  Selecteer in de app het menu **Bestand** en selecteer achtereenvolgens **App-instellingen** en **Geavanceerde instellingen**. Schuif omlaag naar de gedeelten **Preview-functies** en **Experimentele functies**:

![](media/working-with-experimental/advanced-settings.png)

Elke functie heeft een schakeloptie voor in-/uitschakelen.  **Uit** houdt in dat de functie is uitgeschakeld.  Bij de standaardinstelling zijn alle schakelopties uitgeschakeld. Dat is de veiligste manier om uw app uit te voeren.

In sommige gevallen moet u de app mogelijk sluiten en opnieuw openen nadat u een instelling hebt gewijzigd.  In de functiebeschrijving moet zijn aangegeven wanneer u deze stap moet uitvoeren.

Boven in het deelvenster **Geavanceerde instellingen** vindt u de instellingen voor volledig geïmplementeerde functies die niet onder een preview-functie of experimentele functie vallen en waar u volledig op kunt vertrouwen. 

Deze instellingen zijn specifiek voor elke app. Wanneer u de stand van de schakeloptie wijzigt, heeft dat alleen betrekking op de app die op dat moment is geopend. Als u een app maakt, worden deze schakelopties teruggezet naar de standaardinstellingen voor die app.
