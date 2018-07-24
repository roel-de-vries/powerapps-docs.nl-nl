---
title: Een canvas-app controleren op toegankelijkheid | Microsoft Docs
description: Nagaan hoe een canvas-app toegankelijker kan worden gemaakt voor gebruikers met een visuele, auditieve of andere beperking
author: emcoope-msft
ms.service: powerapps
ms.topic: article
ms.date: 07/05/2018
ms.author: emcoope
ms.openlocfilehash: 33f5f8dfe9f6c6fe31e07c1b626dc627c7cd29b0
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023983"
---
# <a name="review-a-canvas-app-for-accessibility-in-powerapps"></a>Een canvas-app controleren op toegankelijkheid in PowerApps

Gebruikers met een visuele, auditieve of andere beperking kunnen uw canvas-app eenvoudiger en effectiever gebruiken als u bij het ontwerpen van het uiterlijk en de werking van de app rekening houdt met de toegankelijkheid. Als u niet zeker weet hoe u uw app toegankelijker kunt maken, kunt u de toegankelijkheidscontrole in PowerApps Studio uitvoeren. Met dit hulpprogramma worden niet alleen mogelijke toegankelijkheidsproblemen vastgesteld, maar wordt ook uitgelegd waarom ze een mogelijk probleem kunnen zijn voor gebruikers die een specifieke beperking hebben en worden suggesties geboden voor het oplossen van elk probleem.
De toegankelijkheidscontrole detecteert voor u problemen met de schermlezer en het toetsenbord en biedt informatie over het oplossen van problemen met kleurcontrast door [toegankelijke kleuren](accessible-apps-color.md) te gebruiken.

Met de toegankelijkheidscontrole kunt u vaststellen welke instellingen u misschien wilt aanpassen. U moet de suggesties echter altijd bekijken in het licht van de functionaliteit van uw app. Veel suggesties kunnen waardevol zijn, maar u kunt de suggesties negeren die meer kwaad dan goed doen.

## <a name="find-accessibility-issues"></a>Toegankelijkheidsproblemen vinden

1. Selecteer in de rechterbovenhoek van PowerApps Studio het pictogram voor de app-controle.

    ![Pictogram voor de app-controle](./media/accessibility-checker/app-checker-icon.png)

2. Selecteer in het menu dat wordt weergegeven de optie **Toegankelijkheid**.

    ![Lijst met opties van het deelvenster App-controle](./media/accessibility-checker/app-checker-menu.png)

    Er wordt een lijst met problemen weergegeven. Deze lijst wordt eerst gesorteerd op ernst en vervolgens op scherm.

    ![Het deelvenster Toegankelijkheidscontrole en een lijst met items](./media/accessibility-checker/accessibility-checker-pane.png)

3. Selecteer de pijl naast een item om de details hiervan weer te geven.

    ![Details van de toegankelijkheidscontrole](./media/accessibility-checker/details-pane.png)

4. Selecteer de pijl-terug om terug te keren naar de lijst met items.

5. Als u een probleem wilt oplossen, selecteert u dit om de betreffende eigenschap te openen.

6. Nadat u een of meer eigenschappen hebt gewijzigd, selecteert u **Opnieuw controleren** om de lijst met problemen bij te werken.

    Opgeloste items worden niet meer in de lijst weergegeven en nieuwe items kunnen worden vermeld.

## <a name="severity-of-issues"></a>Ernst van problemen

Elk probleem wordt door de toegankelijkheidscontrole op basis van de ernst van het probleem geclassificeerd als een fout, waarschuwing of tip.

- **Fouten** geven problemen aan die het voor gebruikers met een beperking moeilijk of onmogelijk maken om de app te gebruiken of te begrijpen.
- **Waarschuwingen** geven problemen aan die het voor de meeste, maar niet alle, gebruikers met een beperking moeilijk of onmogelijk maken om de app te gebruiken of te begrijpen.
- **Tips** helpen u bij het verbeteren van de gebruikservaring van gebruikers met een beperking.

## <a name="types-of-issues"></a>Soorten problemen

| Titel van het probleem                            | Ernst | Beschrijving van het probleem  | Hoe oplossen? | Waarom oplossen?|
| ------------------------------         |:---------| -----| ------|------ |
| **Ontbrekende eigenschap AccessibleLabel**           | Fout    | Wanneer de eigenschap accessible-label van een interactief besturingselement geen tekst bevat. Een interactief besturingselement kan van zichzelf interactief zijn, zoals een knop, of het kan interactieve eigenschappen hebben. U hebt bijvoorbeeld mogelijk de eigenschap **OnSelect** of de eigenschap **TabIndex** van een afbeelding ingesteld op 0 of hoger.  | Bewerk de eigenschap AccessibleLabel zo dat het item wordt beschreven. | Als de eigenschap AccessibleLabel geen tekst bevat, weten gebruikers die het scherm niet kunnen zien niet wat er in de afbeeldingen en op de besturingselementen wordt weergegeven. |
| **De focus wordt niet weergegeven**                | Fout    | Wanneer de **FocusBorderThickness** van een besturingselement is ingesteld op 0. U kunt het beste een goede kleurcontrastverhouding hanteren tussen de focusrand en het besturingselement zelf, zodat deze duidelijk zichtbaar is. | Wijzig de eigenschap **FocusedBorderThickness** in een waarde die groter is dan 0.  | Als de focus niet zichtbaar is, kunnen personen die geen muis gebruiken niet zien wanneer ze met de app werken.   |
| **Ontbrekende bijschriften**                   | Waarschuwing  | Wanneer de eigenschap **ClosedCaptionsURL** van een besturingselement voor **audio** of **video** leeg is. | Stel de eigenschap **ClosedCaptionsURL** in op de URL voor bijschriften. | Zonder bijschriften krijgen gebruikers met een beperking mogelijk geen informatie over een video- of audiosegment. |
| **Ontbrekende handige besturingselementinstellingen**   | Waarschuwing  | Wanneer een van de verschillende instellingen (zoals de weergave van labels en markeringen voor grafieken en de weergave van standaardbesturingselementen voor **audio**, **video** en **peninvoer**) is uitgeschakeld. | Selecteer de waarschuwing en stel vervolgens de eigenschap in op **Waar**. | Door deze eigenschapsinstelling te wijzigen, krijgt de gebruiker betere informatie over de werking van de besturingselementen in uw app. |
| **HTML is niet toegankelijk**           | Waarschuwing  | Wanneer een besturingselement dat geen HTML-tekstbesturingselement is HTML bevat. In dat geval biedt PowerApps geen ondersteuning voor de toegankelijkheid van aangepaste HTML-elementen. | Gebruik een andere methode dan HTML of verwijder de HTML uit dit element. | Uw app werkt niet correct en is niet toegankelijk als u interactieve HTML-elementen toevoegt. |
| **Automatisch starten uitschakelen**                 | Waarschuwing  | Wanneer de eigenschap **Autostart** van een besturingselement voor **audio** of **video** is ingesteld op **Waar**. | Stel de eigenschap **Autostart** van het besturingselement in op **Onwaar**. | Video- en audiobestanden die automatisch worden afgespeeld, kunnen gebruikers afleiden. Laat ze kiezen of een clip moet worden afgespeeld. |
| **De schermnaam aanpassen**                 | Tip      | Wanneer een scherm een standaardnaam heeft die wordt uitgesproken door schermlezers wanneer gebruikers door de app navigeren. | Geef het scherm een naam waarmee wordt beschreven wat er op het scherm te zien is of waarvoor het scherm wordt gebruikt.| Personen die blind of slechtziend zijn of moeite met lezen hebben, zijn afhankelijk van schermnamen om met de schermlezer te navigeren. |
| **Tekst toevoegen die de status aangeeft**          | Tip      |  Wanneer een besturingselement een status heeft, zoals een schakeloptie voor in-/uitschakelen, maar de waardelabels zijn uitgeschakeld. | Stel de eigenschap **ShowValue** van het besturingselement in op **Waar** om de huidige status weer te geven. | Gebruikers krijgen geen bevestiging van hun acties als de status van het besturingselement niet wordt weergegeven. |
| **De volgorde van de schermitems controleren**| Tip      | Wanneer de eigenschap **TabIndex** groter is dan 1. App-ontwikkelaars kunnen een aangepaste tabvolgorde instellen door de eigenschap **TabIndex** in te stellen op een numerieke waarde, zoals 1, 2, 3 en 4. Deze tip herinnert u eraan om de interactieve volgorde voor dit scherm nader te bekijken. U kunt het beste een ontwerp gebruiken waarin de eigenschap **TabIndex** is ingesteld op 0.  | Zorg ervoor dat uw schermelementen overeenkomen met de volgorde waarin volgens u met de Tab-toets door het scherm moet worden genavigeerd. | Wanneer een schermlezer de elementen van een app leest, moeten deze worden weergegeven in de volgorde waarin een gebruiker ze ziet, in plaats van een volgorde die minder intuïtief is.  |
| **Een andere invoermethode toevoegen**           | Tip      | Wanneer een app een **pen**besturingselement bevat. Deze tip herinnert u eraan om een andere invoermethode toe te voegen. | Voeg naast het **pen**besturingselement een besturingselement voor **tekstinvoer** toe zodat de toegankelijkheid van de app wordt verbeterd. | Sommige gebruikers kunnen geen pen gebruiken en hebben een andere manier nodig om gegevens in te voeren (bijvoorbeeld een handtekening typen). |

## <a name="next-steps"></a>Volgende stappen

- [Toegankelijke apps maken](accessible-apps.md)
- [Toegankelijke kleuren](accessible-apps-color.md)
- [Eigenschappen voor toegankelijkheid](controls/properties-accessibility.md)
