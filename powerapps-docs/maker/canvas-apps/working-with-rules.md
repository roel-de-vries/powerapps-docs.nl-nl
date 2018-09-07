---
title: Een regel maken | Microsoft Docs
description: Stapsgewijze instructies voor het ontwikkelen van app-logica door regels te maken
author: karthik-1
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/10/2017
ms.author: sharik
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 32643de711321e7c604ef9e3ffc82c2502234a1f
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42860388"
---
# <a name="create-a-rule-in-powerapps"></a>Een regel maken in PowerApps
Maak regels om een app automatisch te wijzigen op basis van criteria die u opgeeft. U kunt bijvoorbeeld lijstitems in rood, geel of groen weergeven op basis van hun status, of een goedkeuringsknop alleen weergeven voor bepaalde gebruikers (zoals managers).

U kunt regels toevoegen aan verschillende besturingselementen. In dit onderwerp voegt u een regel toe om de tekstkleur van een **Label**-besturingselement te wijzigen als de waarde van een **Schuifregelaar**-besturingselement groter dan 70 is.

## <a name="add-a-rule"></a>Een regel toevoegen
1. Selecteer een besturingselement (of voeg een besturingselement toe en laat het geselecteerd).

    Voor dit onderwerp [voegt u een label en een schuifregelaar toe](add-configure-controls.md), stelt u de eigenschap **Tekst** van het label in op **Slider1.Value** en selecteert u vervolgens de schuifregelaar.

1. Klik of tik in het rechterdeelvenster op **Regels** en klik of tik vervolgens op **Nieuwe regel**.

    ![Nieuwe regel maken](./media/working-with-rules/new-rule.png)

    Als u een besturingselement selecteert waarvoor al één of meer regels zijn gedefinieerd, kunt u deze bewerken door erop te klikken of tikken.  

## <a name="add-a-condition"></a>Een voorwaarde toevoegen
Een voorwaarde is een expressie die evalueert als true of false, zoals of een waarde groter dan 70 is. U kunt de expressie schrijven op basis van een sjabloon of van begin af aan, en u kunt de expressie aanpassen op basis van instructies in de UI (Intellisense).

1. Klik of tik op **Een voorwaarde toevoegen** en klik vervolgens op een sjabloon of op **Aangepaste voorwaarde**.

    Voor dit onderwerp klikt of tikt u op **Groter dan**.

    ![Voorwaarde toevoegen](./media/working-with-rules/rule-conditions.png)

1. Voltooi de expressie om te definiëren wanneer de regel wordt toegepast.

    Voor dit onderwerp moet u 0 wijzigen in 70 als u deze expressie wilt krijgen: <br>**Slider1.Value > 70**

## <a name="add-an-action"></a>Een actie toevoegen
Acties definiëren wat er gebeurt wanneer de regel wordt toegepast. PowerApps kan acties automatisch maken op basis van wijzigingen die u aanbrengt in besturingselementen.

1. Klik of tik op **Acties definiëren**.

    ![Acties definiëren](./media/working-with-rules/rule-define-actions.png)

1. Klik of tik in het bevestigingsdialoogvenster op **Laten we beginnen**, zodat PowerApps uw volgende wijziging of wijzigingen als één of meer acties vastlegt.

1. Configureer één of meer besturingselementen zodanig dat aan uw verwachtingen wordt voldaan wanneer de voorwaarde true is.

    Voor dit onderwerp wijzigt u de kleur van het label.

    ![Eigenschappen vastleggen](./media/working-with-rules/rule-capture-properties.png)

1. (Optioneel) Controleer uw wijzigingen door op **Acties weergeven** te klikken of tikken.

    ![Acties controleren](./media/working-with-rules/rule-review-actions.png)

1. Wanneer u klaar bent met het toevoegen van acties, klikt of tikt u op **Gereed**.

1. Bekijk de voorwaarde en acties voor de regel.

    ![Regel controleren](./media/working-with-rules/rule-review.png)

## <a name="rename-the-rule"></a>De naam van de regel wijzigen

1. Beweeg de muisaanwijzer over **Rule1** en klik of tik op de knop Bewerken.

    ![Beweeg de muisaanwijzer over de naam van een regel](./media/working-with-rules/hover-over-rules_name.png)

1. Voer een nieuwe naam in voor de regel.

    ![Naam van regel wijzigen](./media/working-with-rules/rename-rule.png)

1. Klik of tik **Gereed** om de editor te sluiten.

## <a name="test-the-rule"></a>De regel testen
1. Bekijk een voorbeeld van de app door op F5 te drukken (of door rechtsboven op de afspeelknop te klikken).

    ![Voorbeeld openen](./media/working-with-rules/open-preview.png)

1. Maak de voorwaarde die u hebt opgegeven true en bevestig vervolgens dat de acties op de verwachte manier werken.

    Voor dit onderwerp stelt u de schuifregelaar in op een waarde die groter dan 70 is en bevestigt u dat de labeltekst van kleur verandert.

## <a name="see-all-rules"></a>Alle regels weergeven
Standaard worden op het tabblad **Regels** alleen de regels weergegeven voor het geselecteerde besturingselement en alle onderliggende besturingselementen die worden gebruikt in een regelvoorwaarde of -actie. Als u alle regels in de app wilt weergeven, schakelt u het selectievakje **Alleen regels voor dit besturingselement weergeven** uit.

![Filter verwijderen](./media/working-with-rules/rules-filter.png)

## <a name="known-limitations"></a>Bekende beperkingen
Op het moment van schrijven:

* Kunt u de eigenschap **ThisItem** van een formulier of galerie niet als onderdeel van een voorwaarde opgeven.
