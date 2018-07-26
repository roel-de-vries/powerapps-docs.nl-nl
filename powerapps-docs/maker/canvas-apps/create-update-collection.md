---
title: Een verzameling maken en bijwerken | Microsoft Docs
description: Verzamelingen maken en kolommen toevoegen aan bestaande verzamelingen in PowerApps
author: lonu
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/30/2015
ms.author: lonu
ms.openlocfilehash: 98407181bc654874d749bb57da22c9fde1259fb6
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/22/2018
ms.locfileid: "39195491"
---
# <a name="create-and-update-a-collection-in-your-app"></a>Een verzameling in uw app maken en bijwerken
U kunt een verzameling gebruiken om gegevens op te slaan die in uw app kunnen worden gebruikt. Een verzameling is een groep met items die vergelijkbaar zijn. U maakt bijvoorbeeld een verzameling MijnAfbeeldingen waarin alle foto's worden opgeslagen van producten die uw bedrijf verkoopt. U kunt uw verzameling MijnAfbeeldingen in PowerApps toevoegen en een app maken die alle foto's van deze producten weergeeft. Ander voorbeeld: u kunt een verzameling Prijslijst maken die een overzicht bevat van de producten en de prijs van elk product.

U kunt verzamelingen maken en gebruiken in PowerApps. Aan de slag.

### <a name="prerequisites"></a>Vereisten
* [Registreer u](../signup-for-powerapps.md) voor PowerApps en [meld u vervolgens aan](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) door dezelfde referenties in te voeren die u hebt gebruikt om u te registreren.
* Maak een app of open een bestaande app in PowerApps.
* Lees hoe u [een besturingselement kunt configureren](add-configure-controls.md) in PowerApps.
* Deze stappen gebruiken het bestand [PriceList.zip](http://pwrappssamples.blob.core.windows.net/samples/PriceList.zip) als voorbeeld voor invoergegevens. Het zip-bestand bevat een XML-bestand dat naar Excel kan worden geconverteerd. Anders leest PowerApps automatisch de bestanden in de .zip-bestanden, waarna deze worden geïmporteerd. U kunt deze voorbeeldgegevens downloaden en gebruiken of uw eigen gegevens importeren.

## <a name="create-a-single-column-collection"></a>Een verzameling met één kolom maken
De volgende stappen laten u zien hoe u een verzameling binnen uw app kunt maken met de functie Collect, en hoe u items aan uw verzameling kunt toevoegen.

1. Open uw app.
2. Selecteer op het tabblad **Invoegen** de optie **Tekst** en selecteer vervolgens **Tekstinvoer**:  
   ![][1]  
3. Selecteer in de linkerbovenhoek **Tekst1** en wijzig de naam van het besturingselement in **Bestemming**:  
   ![][2]  
4. Selecteer **Knop** op het tabblad **Invoegen** om een knopbesturingselement aan uw ontwerpomgeving toe te voegen. In de vervolgkeuzelijst wordt de eigenschap **[OnSelect](controls/properties-core.md)** weergegeven. Stel deze in op de volgende functie:  
   
    ```Collect(Destinations, Destination!Text)```
   
    De eigenschap moet er als volgt uitzien:  
    ![][3]  
5. Selecteer de knoptekst en vul **Toevoegen** in:  
   ![][5]  
6. Selecteer de knop **Toevoegen** en verplaats deze onder uw tekstbesturingselement. U kunt de knop op elke gewenste plek plaatsen:  
   ![][6]  

In deze stappen gebruikte u de functie Collect om een collectie met de naam **Bestemmingen** te maken. U hebt ook een knopbesturingselement toegevoegd. Wanneer deze wordt geselecteerd, worden hiermee nieuwe items aan uw verzameling toegevoegd. Bekijk nu wat u hebt gemaakt:

1. Selecteer Voorbeeld:  
   ![][7]  
2. Typ de naam van een plaats in het vak en selecteer vervolgens de knop **Toevoegen**.
3. Vul nog wat extra plaatsnamen in en selecteer steeds de knop **Toevoegen**.
4. Druk op de toets **Esc** om het voorbeeldvenster te sluiten.
5. Bekijk de verzameling Bestemmingen en de tekstwaarden die u hebt ingevoerd. Selecteer **Verzamelingen** op het tabblad **Bestand**. De tekst die u hebt ingevoerd, wordt weergegeven:  
   ![][8]

#### <a name="extra-credit"></a>Extra tegoed
Laten we de verzameling Bestemmingen nu koppelen aan een keuzelijst:

1. Ga terug naar uw ontwerpomgeving.
2. Selecteer op het tabblad **Invoegen** de optie **Besturingselementen** en selecteer vervolgens **Keuzelijst**:  
   ![][22]  
3. Verplaats de keuzelijst, zodat u deze gemakkelijk kunt zien. Stel de eigenschap **[Items](controls/properties-core.md)** in op de volgende expressie:  
   ```Destinations!Value```  <br/>
   
    Als u dit doet, wordt de keuzelijst automatisch gevuld met de items die u eerder in de verzameling Bestemmingen hebt ingevoerd:  
   ![][4]  

Bekijk uw wijzigingen: ![][7]. U kunt in de keuzelijst de verschillende plaatsen zien die u hebt ingevoerd. Voer in het besturingselement voor tekstinvoer een nieuwe plaats in en selecteer de knop **Toevoegen**. De keuzelijst wordt automatisch bijgewerkt met de nieuwe plaats die u hebt ingevoerd.

## <a name="create-a-multi-column-collection"></a>Een verzameling met meerdere kolommen maken
De volgende stappen laten u zien hoe u een verzameling binnen uw app kunt maken met de functie Collect, en hoe u meerdere rijen aan uw verzameling kunt toevoegen.

1. Open een nieuw scherm op het tabblad **Start**.
2. Selecteer op het tabblad **Invoegen** de optie **Tekst** en selecteer vervolgens **Tekstinvoer**.
3. Wijzig de naam van het tekstbesturingselement in **Plaats**:  
   ![][9]  
4. Voeg nog een besturingselement voor tekstinvoer toe en wijzig de naam ervan in **Staten**.
5. Verplaats de tekstbesturingselementen Plaats en Staten, zodat u ze allebei kunt zien:  
   ![][10]  
   
    > [!NOTE]
   > U kunt 'Tekstinvoer' vervangen door zoiets als 'Plaats' of 'Staat’, zoals in de afbeelding.  
6. Selecteer **Knop** op het tabblad **Invoegen**. Stel de eigenschap **[OnSelect](controls/properties-core.md)** in op de volgende functie:  
   ```Collect(Destinations, {Cities:City!Text, States:States!Text})```  
   
    De eigenschap moet er als volgt uitzien:  
    ![][11]  
   
    > [!NOTE]
   > U kunt deze zelfde functie gebruiken om extra kolommen aan deze verzameling toe te voegen. U kunt bijvoorbeeld nog een besturingselement voor tekstinvoer toevoegen voor Land om een kolom met landen toe te voegen:
   
    `Collect(Destinations, {Cities:City!Text, States:States!Text}, {Countries:Country!Text})`
7. Wijzig de naam van het knopbesturingselement **AddCityStateButton** en stel de eigenschap **[Tekst](controls/properties-core.md)** ervan in op **Plaats en staat toevoegen**:  
   ![][12]  

In deze stappen hebt u een kolom **Plaatsen** en een kolom **Staten** aan de verzameling **Bestemmingen** toegevoegd. Het knopbesturingselement voegt deze nieuwe tekstitems aan uw verzameling toe. Bekijk nu wat u hebt gemaakt:

1. Selecteer Voorbeeld:  
   ![][7]  
2. Typ wat tekst in de vakken Plaats en Staat en selecteer daarna de knop **Plaats en staat toevoegen**.
3. Voeg nog wat plaatsen en staten toe.
4. Druk op de toets **Esc** om het voorbeeldvenster te sluiten.
5. Selecteer het tabblad **Bestand** en selecteer vervolgens **Verzamelingen** om de items te zien die u aan de verzameling Bestemmingen hebt toegevoegd:  
   ![][13]

## <a name="add-columns-to-a-collection"></a>Kolommen toevoegen aan een verzameling
Er zijn een paar secties in dit stappenplan. Na het afronden weet u hoe u gegevens in uw verzameling moet importeren, hoe u een galerie moet maken die gegevens in een prijslijst weergeeft en hoe u een schuifregelaar moet gebruiken die de hoeveelheid van een product bepaalt.

### <a name="import-the-price-list-and-create-the-collection"></a>De prijslijst importeren en de verzameling maken
1. Download het zip-bestand [PriceList](http://pwrappssamples.blob.core.windows.net/samples/PriceList.zip).
2. Voeg op het tabblad **Start** een nieuw scherm toe.
3. Selecteer op het tabblad **Invoegen** de optie **Besturingselementen** en selecteer vervolgens **Importeren**:  
   ![][14]  
4. Selecteer op het tabblad **Actie** de optie **OnSelect**. Voer de volgende functie in:  
   
    ```Collect(PriceList, Import1!Data)```  
5. Bekijk een voorbeeld van uw app. Selecteer de knop **Gegevens importeren**, selecteer het bestand PriceList.zip en selecteer **Openen**.
6. Sluit het voorbeeldvenster.
7. Selecteer het tabblad **Bestand** en selecteer **Verzamelingen**. De PriceList-items die u hebt geïmporteerd, worden weergegeven:  
   ![][15]

### <a name="add-the-gallery-to-show-the-collection-items"></a>De galerie toevoegen om de items uit de verzameling weer te geven
1. Ga terug naar uw ontwerpomgeving.
2. Selecteer op het tabblad **Invoegen** de optie **Galerie**, schuif omlaag naar **Aangepaste galerieën** en selecteer vervolgens **Staand**:    
   ![][16]  
3. Wijzig de naam van de galerie in **Prijsgalerie** en stel de eigenschap **[Items](controls/properties-core.md)** in op **Prijslijst**:  
   ![][18]  
4. Verplaats de galerie Prijslijst onder het besturingselement **Gegevens importeren**. Selecteer de randen van de galerie en gebruik klikken en slepen om de galerie groter of kleiner te maken, zodat er drie vierkanten worden weergegeven.
5. Selecteer het eerste vierkant in de galerie en voeg drie labels toe (tabblad **Invoegen** > **Label**).
6. Pas de grootte aan en rangschik de labels in een rij bij de bovenkant van het eerste vierkant. Uw galerie ziet er ongeveer als volgt uit:  
   ![][19]
7. Stel de eigenschap **[Tekst](controls/properties-core.md)** van elk label in op de volgende expressie:  
   
   | Label | Stel de eigenschap Tekst in op |
   | --- | --- |
   | Label1 |``ThisItem!Name`` |
   | Label2 |``Text(ThisItem!Price, "$#")`` |
   | Label3 |``ThisItem!Maker`` |
   
    Als u dit doet, worden de labels automatisch bijgewerkt met de naam-, prijs- en makerwaarden in de verzameling Prijslijst.
8. Pas de grootte van de labels en de galerie aan om eventuele extra ruimte te verwijderen. Uw scherm ziet er nu ongeveer als volgt uit:  
   ![][17]

### <a name="add-the-quantity-slider-and-update-the-collection"></a>De schuifregelaar voor hoeveelheden toevoegen en de verzameling bijwerken
1. Selecteer in het menu **Invoegen** de optie **Besturingselementen** en selecteer **Schuifregelaar**. Wijzig de naam van de schuifregelaar naar **Bestelhoev** en verplaats hem onder de galerie.
2. Voeg een knop toe, stel de eigenschap **[Tekst](controls/properties-core.md)** in op **Toevoegen** en verplaats deze onder de schuifregelaar **Bestelhoev**. Uw app ziet er ongeveer als volgt uit:  
   ![][20]
3. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van de knop **Toevoegen** in op de volgende expressie:  
   
    ```Collect(OrderList, {Name:PriceGallery!Selected!Name, Qty:OrderQty!Value, Cost:OrderQty!Value*LookUp(PriceList, PriceGallery!Selected!Name in Name, Price)});SaveData(OrderList, "orderfile")```  
   
    > [!NOTE]
   > Als u deze knop later in deze procedure selecteert, maakt u een verzameling die wordt opgeslagen met de naam **Bestellijst**. De verzameling zal de naam bevatten van een product dat u in de galerie invoert, een hoeveelheid die u met de schuifregelaar kiest en de totale kosten die worden berekend door de hoeveelheid te vermenigvuldigen met de prijs van het product.
4. Selecteer het tabblad **Scherm** en stel de eigenschap **[OnVisible](controls/control-screen.md)** in op de volgende expressie:  
   
    ```If(IsEmpty(PriceList), LoadData(PriceList, "pricefile"));If(IsEmpty(OrderList), LoadData(OrderList, "orderfile"))```

Bekijk nu wat u hebt gemaakt:

1. Open **Voorbeeld**.
2. Selecteer een product in de galerie, verplaats de schuifregelaar naar de gewenste hoeveelheid en selecteer daarna de knop **Toevoegen**.  
   
   > [!IMPORTANT]
   > Als u een product selecteert, wordt dat product niet gemarkeerd om aan te geven dat u het hebt geselecteerd. We hebben deze functionaliteit niet toegevoegd tijdens het maken van de galerie. Weet dat het product wordt geselecteerd als u er op klikt.  
   > 
   > 
3. Herhaal deze stappen om nog wat producten toe te voegen. Druk op **Esc** om het voorbeeldvenster te sluiten.
4. Selecteer op het tabblad **Bestand** de optie **Verzamelingen** om een voorbeeld weer te geven van de verzameling **Bestellijst** die u hebt gemaakt:  
   ![][21]

> [!TIP]
> U kunt alle items uit de bestellijst verwijderen door een knop toe te voegen, de eigenschap **[Tekst](controls/properties-core.md)** ervan in te stellen op **Wissen** en de eigenschap **[OnSelect](controls/properties-core.md)** in te stellen op de volgende expressie:  
> ```Clear(OrderList);SaveData(OrderList, "orderfile")```  
> Geef de verzameling **Bestellijst** in een galerie weer en stel de eigenschap **[OnSelect](controls/properties-core.md)** van een label in die galerie vervolgens in op de volgende expressie om één item per keer te verwijderen:  
> ```Remove(OrderList, ThisItem);SaveData(OrderList, "orderfile")```
> 
> 

## <a name="tips-and-tricks"></a>Tips en trucs
* U kunt op elk gewenst moment de knop Voorbeeld (![][7]) selecteren om uw grafieken weer te geven en te zien hoe ze eruitzien met gegevens.
* Wanneer u uw app ontwerpt, kunt u de grootte van de besturingselementen aanpassen en ze verplaatsen door te klikken en te slepen.

## <a name="what-you-learned"></a>Wat u hebt geleerd
In dit onderwerp hebt u het volgende geleerd:

* U hebt de functie Collect() gebruikt om een verzameling in uw app te maken.
* U hebt een knopbesturingselement toegevoegd. Wanneer de knop wordt geselecteerd, worden nieuwe items aan uw verzameling toegevoegd.
* U hebt een keuzelijst gebruikt om items aan uw verzameling toe te voegen.
* U hebt een schuifregelaar toegevoegd om items in de verzameling bij te werken.

[1]: ./media/create-update-collection/insertmenu-inputtext.png
[2]: ./media/create-update-collection/renametext.png
[3]: ./media/create-update-collection/buttononselect.png
[4]: ./media/create-update-collection/listboxpreview.png
[5]: ./media/create-update-collection/buttontext.png
[6]: ./media/create-update-collection/buttonundertext.png
[7]: ./media/create-update-collection/preview.png
[8]: ./media/create-update-collection/existingcollections.png
[9]: ./media/create-update-collection/renametext-city.png
[10]: ./media/create-update-collection/citystate.png
[11]: ./media/create-update-collection/buttononselectcitystate.png
[12]: ./media/create-update-collection/buttononcitystate.png
[13]: ./media/create-update-collection/existingcollectionscitystate.png
[14]: ./media/create-update-collection/import.png
[15]: ./media/create-update-collection/pricelistcollection.png
[16]: ./media/create-update-collection/portrait.png
[17]: ./media/create-update-collection/resizedgallery.png
[18]: ./media/create-update-collection/galleryitems.png
[19]: ./media/create-update-collection/gallerylabels.png
[20]: ./media/create-update-collection/slider.png
[21]: ./media/create-update-collection/existingcollectionsorderlist.png
[22]: ./media/create-update-collection/listbox.png
