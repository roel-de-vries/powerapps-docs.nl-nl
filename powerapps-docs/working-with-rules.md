---
title: Een regel maken | Microsoft Docs
description: Stapsgewijze instructies voor het ontwikkelen van app-logica door regels te maken
services: 
suite: PowerApps
documentationcenter: na
author: karthik-1
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/14/2017
ms.author: karthikb
ms.openlocfilehash: c6b7141c20591c1fdbb5278b1fe4d75bfb6a4ebb
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="create-a-rule-in-powerapps"></a>Een regel maken in PowerApps
Maak regels om een app automatisch te wijzigen op basis van criteria die u opgeeft. U kunt bijvoorbeeld lijstitems in rood, geel of groen weergeven op basis van hun status, of een goedkeuringsknop alleen weergeven voor bepaalde gebruikers (zoals managers).

U kunt regels toevoegen aan verschillende besturingselementen. In dit onderwerp voegt u een regel toe om de tekstkleur van een **Label**-besturingselement te wijzigen als de waarde van een **Schuifregelaar**-besturingselement groter dan 70 is.

## <a name="add-a-rule"></a>Een regel toevoegen
1. Selecteer een besturingselement (of voeg een besturingselement toe en laat het geselecteerd).
   
    Voor dit onderwerp [voegt u een label en een schuifregelaar toe](add-configure-controls.md), stelt u de eigenschap **Tekst** van het label in op **Slider1.Value** en selecteert u vervolgens de schuifregelaar.
2. Klik of tik in het rechterdeelvenster op **Regels** en klik of tik vervolgens op **Nieuwe regel**.
   
    ![Nieuwe regel maken](./media/working-with-rules/new-rule.png)
   
    Als u een besturingselement selecteert waarvoor al één of meer regels zijn gedefinieerd, kunt u deze bewerken door erop te klikken of tikken.  

## <a name="add-a-condition"></a>Een voorwaarde toevoegen
Een voorwaarde is een expressie die evalueert als true of false, zoals of een waarde groter dan 70 is. U kunt de expressie schrijven op basis van een sjabloon of van begin af aan, en u kunt de expressie aanpassen op basis van instructies in de UI (Intellisense).

1. Klik of tik op **Een voorwaarde toevoegen** en klik vervolgens op een sjabloon of op **Aangepaste voorwaarde**.
   
    Voor dit onderwerp klikt of tikt u op **Groter dan**.
   
    ![Voorwaarde toevoegen](./media/working-with-rules/rule-conditions.png)
2. Voltooi de expressie om te definiëren wanneer de regel wordt toegepast.
   
    Voor dit onderwerp gebruikt u deze expressie:  <br>**Waarde(Slider1.Value) > 70**
   
    **Opmerking**: Op het moment van schrijven moet u de eigenschap opgeven van het besturingselement dat in de vergelijking wordt gebruikt. In toekomstige versies kan PowerApps misschien algemene eigenschappen van het besturingselement afleiden (zoals **Tekst** of **Waarde**).

## <a name="add-an-action"></a>Een actie toevoegen
Acties definiëren wat er gebeurt wanneer de regel wordt toegepast. PowerApps kan acties automatisch maken op basis van wijzigingen die u aanbrengt in besturingselementen.

1. Klik of tik op **Acties definiëren**.
   
    ![Acties definiëren](./media/working-with-rules/rule-define-actions.png)
2. Klik of tik in het bevestigingsdialoogvenster op **Laten we beginnen**, zodat PowerApps uw volgende wijziging of wijzigingen als één of meer acties vastlegt.
3. Configureer één of meer besturingselementen zodanig dat aan uw verwachtingen wordt voldaan wanneer de voorwaarde true is.
   
    Voor dit onderwerp wijzigt u de kleur van het label.
   
    ![Eigenschappen vastleggen](./media/working-with-rules/rule-capture-properties.png)
4. (Optioneel) Controleer uw wijzigingen door op **Acties weergeven** te klikken of tikken.
   
    ![Acties controleren](./media/working-with-rules/rule-review-actions.png)
5. Wanneer u klaar bent met het toevoegen van acties, klikt of tikt u op **Gereed**.
6. Controleer de voorwaarde en acties voor de regel en klik of tik vervolgens op **Gereed** om ze op te slaan.
   
    ![Regel controleren](./media/working-with-rules/rule-review.png)

## <a name="test-the-rule"></a>De regel testen
1. Bekijk een voorbeeld van de app door op F5 te drukken (of door rechtsboven op de afspeelknop te klikken).
   
    ![Voorbeeld openen](./media/working-with-rules/open-preview.png)
2. Maak de voorwaarde die u hebt opgegeven true en bevestig vervolgens dat de acties op de verwachte manier werken.
   
    Voor dit onderwerp stelt u de schuifregelaar in op een waarde die groter dan 70 is en bevestigt u dat de labeltekst van kleur verandert.

## <a name="known-limitations"></a>Bekende beperkingen
Op het moment van schrijven:

* Kunt u de naam van een regel niet wijzigen.
* Kunt u de eigenschap **ThisItem** van een formulier of galerie niet als onderdeel van een voorwaarde opgeven.

