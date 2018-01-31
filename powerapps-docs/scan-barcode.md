---
title: Een streepjescode scannen | Microsoft Docs
description: Verschillende typen streepjescodes scannen, zoals UPC en Codabar
services: 
suite: powerapps
documentationcenter: na
author: aftowen
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/23/2016
ms.author: anneta
ms.openlocfilehash: fe7d10a6c74b664e9829c4e78a4a9001d3fe0925
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="scan-a-barcode-in-microsoft-powerapps"></a>Een streepjescode scannen in Microsoft PowerApps
U kunt verschillende soorten streepjescodes scannen door een app te maken en deze uit te voeren op een apparaat dat is uitgerust met een camera, bijvoorbeeld een telefoon. Het numerieke equivalent van de streepjescode wordt weergegeven in een besturingselement **Label** en u kunt deze gegevens uploaden naar diverse [gegevensbronnen](connections-list.md).

Zie [Aan de slag](getting-started.md) als u onbekend bent met PowerApps.

## <a name="known-limitations"></a>Bekende beperkingen
* Streepjescodes moeten minimaal 2,5 cm hoog en 4 cm breed zijn.
* Als u een streepjescode wilt scannen met een telefoon, houdt u de telefoon in verticale richting en beweegt u deze langzaam van een afstand van 18 cm tot 25 cm van de streepjescode af.
* Lange soorten streepjescodes (zoals I2of5, die uit 15 of meer tekens bestaan) leveren soms afgekapte of anderszins onjuiste resultaten op, met name als de streepjescode niet duidelijk is afgedrukt.
* Voor iPhones en Android-apparaten kunt u de eigenschap **Height** van het besturingselement **Streepjescode** opgeven, maar de breedte wordt bepaald door een vaste hoogte-breedteverhouding.
* Misschien moet u de eigenschap **Scanrate** van het besturingselement **Streepjescode** instellen op **35** of minder.
* Als u geheugentekort op apparaten met iOS wilt uitstellen, stelt u de eigenschap **Height** van het besturingselement **Streepjescode** in op **700** (of lager) en de eigenschap **Scanrate** op **30**.
* Start de app opnieuw op als het apparaat geheugen tekort heeft en de app vastloopt.

## <a name="create-a-blank-app"></a>Een lege app maken
1. [Meld u aan voor PowerApps](signup-for-powerapps.md) en voer dan *een* van de volgende handelingen uit:

   * [Open PowerApps](https://create.powerapps.com/api/start) in een browser op een apparaat dat een camera heeft.
   * [Installeer PowerApps](http://aka.ms/powerappsinstall) vanuit de Windows Store op een apparaat dat een camera heeft. Open PowerApps, meld u aan en klik of tik op **New** in het menu **File** (aan de linkerkant).

2. Klik of tik onder **Beginnen met een leeg canvas of een leeg sjabloon** op **Telefoonindeling** in de tegel **Lege app**.

    ![Een volledig nieuwe app maken](./media/scan-barcode/create-from-blank.png)

3. Als u PowerApps nooit eerder hebt gebruikt, kunt u belangrijke gebieden van de app bekijken door de inleidende rondleiding te volgen (of klik of tik op **Skip**).

    ![Scherm van de rondleiding openen](./media/scan-barcode/quick-tour.png)

    > [!NOTE]
> U kunt de rondleiding altijd later volgen door op het vraagtekenpictogram in de rechterbovenhoek te klikken of tikken en vervolgens op **Take the intro tour**.

## <a name="add-a-barcode-control"></a>Een streepjescode-besturingselement toevoegen
1. Klik of tik op het tabblad **Invoegen** op **Media** en klik of tik vervolgens op **Streepjescode**.

    ![Streepjescodescanner toevoegen](./media/scan-barcode/add-scanner.png)

2. Controleer of het **streepjescode**-besturingselement is geselecteerd door na te gaan of het in een selectievak staat (met grepen om de grootte van het besturingselement aan te passen).

    ![Selectievak](./media/scan-barcode/selection-box.png)

3. Klik of tik op het tabblad **Start** op **Streepjescode1** en typ of plak **MijnScanner** onder **Naam wijzigen**.

    > [!TIP]
> Het eerste **streepjescode**-besturingselement dat u toevoegt, heet standaard **Streepjescode1**. Als u dat besturingselement verwijdert en nog een **streepjescode**-besturingselement toevoegt, krijgt dat standaard de naam **Streepjescode2**. Door de naam van een besturingselement handmatig te wijzigen, zorgt u ervoor dat in formules met de juiste naam naar het besturingselement wordt verwezen.

    ![De naam van een streepjescode-besturingselement wijzigen](./media/scan-barcode/rename-barcode.png)

## <a name="add-a-text-input-control"></a>De besturingselement voor tekstinvoer toevoegen
1. Klik of tik op het tabblad **Invoegen** op **Tekst** en klik of tik vervolgens op **Tekstinvoer**.

    Maximaliseer het venster PowerApps als het tabblad **Invoer** niet wordt weergegeven.

    ![Besturingselement voor tekstinvoer toevoegen](./media/scan-barcode/add-text-input.png)

2. Sleep het selectievak (niet de formaatgrepen) rondom het besturingselement voor **tekstinvoer** omlaag totdat het wordt weergegeven onder **MyScanner**.

    ![Label met selectievak](./media/scan-barcode/move-input-text.png)

3. Terwijl het besturingselement voor **tekstinvoer** nog is geselecteerd, controleert u of **Default** in de lijst met eigenschappen wordt weergegeven en typt of plakt u **MyScanner.Text** in de formulebalk.

    ![Eigenschap Text van het besturingselement Label](./media/scan-barcode/default-text.png)

## <a name="change-the-barcode-type"></a>Het type streepjescode wijzigen
1. Klik of tik op het tabblad **Invoegen** op **Besturingselementen** en klik of tik vervolgens op **Vervolgkeuzelijst**.

    ![Vervolgkeuzelijst toevoegen](./media/scan-barcode/insert-dropdown.png)

2. Verplaats het besturingselement **Vervolgkeuzelijst** zo dat het onder de andere besturingselementen in het scherm wordt weergegeven.

    ![Vervolgkeuzelijst verplaatsen](./media/scan-barcode/move-dropdown.png)

3. Terwijl het besturingselement **Vervolgkeuzelijst** nog is geselecteerd, controleert u of **Items** in de lijst met eigenschappen wordt weergegeven en typt of plakt u de volgende tekenreeks in de formulebalk:<br>
    **[Codabar, Code128, Code39, Ean, I2of5, Upc]**

    ![De eigenschap Items van de vervolgkeuzelijst instellen](./media/scan-barcode/items-property.png)

4. Op het tabblad **Home** verandert u de naam van het besturingselement **Vervolgkeuzelijst** in **ChooseType**.

    ![De naam van de vervolgkeuzelijst wijzigen](./media/scan-barcode/rename-dropdown.png)

5. Klik of tik op **MyScanner** om deze te selecteren, controleer of **BarcodeType** in de lijst met eigenschappen wordt weergegeven en typ of plak de volgende tekenreeks in de formulebalk:<br>
    **ChooseType.Selected.Value**

## <a name="test-the-app"></a>De app testen
1. Open de Preview-modus door op F5 te drukken (of klik of tik op het afspeelpictogram rechtsboven).

    ![Preview-modus openen](./media/scan-barcode/open-preview.png)

2. Houd een streepjescode voor de camera op het apparaat totdat het numerieke onderdeel van de streepjescode in het besturingselement **Label** wordt weergegeven.

    Als het numerieke onderdeel niet wordt weergegeven, probeer dan een andere optie in de lijst **BarcodeType**. Als de juiste gegevens nog steeds niet worden weergegeven, typt u het juiste nummer in het besturingselement **Invoertekst**.

## <a name="next-steps"></a>Volgende stappen
* [Verbind de app met een gegevensbron](add-data-connection.md) en configureer de functie **[Patch](functions/function-patch.md)**, zodat gebruikers resultaten kunnen opslaan.
* Voeg een **[vervolgkeuzelijst](controls/control-drop-down.md)** toe en configureer deze, zodat gebruikers kunnen kiezen welk type streepjescode ze willen scannen.
* Voeg een **[schuifregelaar](controls/control-slider.md)** toe en configureer deze, zodat gebruikers de scanfrequentie of de hoogte van het **streepjescode**-besturingselement kunnen aanpassen.
