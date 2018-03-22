---
title: Gegevens weergeven, sorteren en filteren in een galerie | Microsoft Docs
description: Een galerie gebruiken om tekst en afbeeldingen weer te geven. Afbeeldingen sorteren en filteren in PowerApps.
services: ''
suite: powerapps
documentationcenter: ''
author: lonu
manager: anneta
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/02/2015
ms.author: lonu
ms.openlocfilehash: 5bf013ffb77b757aed7a900ac4c35c2693859285
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/22/2018
---
# <a name="show-sort-and-filter-data-in-a-powerapps-gallery"></a>Gegevens weergeven, sorteren en filteren in een PowerApps-galerie
Maak een galerie om afbeeldingen en tekst over verschillende producten weer te geven en sorteer en filter deze informatie.

In PowerApps kunt u een galerie gebruiken om meerdere verwante items weer te geven, net zoals in een catalogus gebeurt. Galerieën zijn ideaal voor het tonen van informatie over producten, zoals namen en prijzen. Dit onderwerp behandelt het maken van een galerie en het sorteren en filteren van informatie met behulp van Excel-achtige functies. Wanneer een item is geselecteerd, wordt er een rand om het item weergegeven.

> [!NOTE]
> In dit onderwerp wordt een tablet-app gebruikt. U kunt ook een smartphone-app gebruiken, maar dan zult u de maat van sommige besturingselementen moeten aanpassen.
> 
> 

### <a name="prerequisites"></a>Vereisten
* [Registreer u](../signup-for-powerapps.md) voor PowerApps en [installeer](http://aka.ms/powerappsinstall) PowerApps. Meld u bij het openen van PowerApps aan met dezelfde referenties die u hebt gebruikt om u te registreren.
* Maak een tablet-app op basis van een [sjabloon](get-started-test-drive.md), op basis van [gegevens](get-started-create-from-data.md) of maak een [volledig nieuwe](get-started-create-from-blank.md) app.
* Lees hoe u [een besturingselement kunt configureren](add-configure-controls.md).
* Deze stappen gebruiken de inhoud van de map [CreateFirstApp](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip) als voorbeeld van invoergegevens, welke ook JPG-afbeeldingen bevat. Het zip-bestand bevat een XML-bestand dat naar Excel kan worden geconverteerd. Anders leest PowerApps automatisch de bestanden in de .zip-bestanden, waarna deze worden geïmporteerd. U kunt deze voorbeeldgegevens downloaden en gebruiken of uw eigen gegevens importeren.

## <a name="show-data-in-a-gallery"></a>Gegevens weergeven in een galerie
1. Maak een verzameling met de naam **Inventaris**, op basis van de voorbeeldgegevens. Volg hiervoor onder andere de volgende stappen:  
   
   1. Selecteer op het tabblad **Invoegen** de optie **Besturingselementen** en selecteer vervolgens **Importeren**:
      
      ![][1]  
   2. Stel de eigenschap **[OnSelect](controls/properties-core.md)** van het besturingselement voor importeren in op de volgende formule:  
      **Collect(Inventory, Import1!Data)**
      
      ![][12]  
   3. Selecteer de knop **Gegevens importeren** op Windows Verkenner te openen. Selecteer *CreateFirstApp.zip* en selecteer **Openen**.
   4. Selecteer **Verzamelingen** in het menu **Bestand**. De verzameling Inventaris wordt getoond, met daarin de gegevens die u hebt geïmporteerd:
      
      ![][3]  
      
      U hebt zojuist verzameling Inventaris gemaakt, met daarin informatie over vijf producten, zoals een afbeelding van het ontwerp, de naam van het product en het aantal artikelen in voorraad.
      
      > [!NOTE]
      > Het besturingselement importeren wordt gebruikt om op Excel-achtige wijze gegevens te importeren en de verzameling te maken. Het besturingselement importeren importeert gegevens wanneer u uw app maakt en wanneer u een voorbeeldweergave van uw app genereert. Het besturingselement importeren importeert momenteel geen gegevens wanneer u uw app publiceert.
      > 
      > 
2. Selecteer de pijl naar links om terug te keren naar de ontwerpfunctie.
3. Ga naar het tabblad **Invoegen**, klik of tik op **Galerie** en klik of tik vervolgens op de galerie **Horizontaal**.
   
    ![][4]
4. Klik of tik in het rechterdeelvenster op de optie waarbij de titel en de ondertitel over de afbeelding heen worden weergegeven:
   
    ![][15]
5. Stel de eigenschap **[Items](controls/properties-core.md)** van de galerie in op **Inventory**:
   
    ![][5]
6. Wijzig de naam van de galerie naar **ProductGallery**, en verplaats de galerie, zodat de andere besturingselementen niet worden geblokkeerd. Pas het formaat van de galerie aan, zodat er drie producten worden weergegeven:
   
    ![][6]
7. Selecteer het label onder het eerste item in de galerie:  
   
    ![][7]  
   
   > [!NOTE]
   > Wanneer u het eerste item in een galerie wijzigt, wijzigt u automatisch alle andere items in de galerie.  
   > 
   > 
8. Stel de eigenschap **[Text](controls/properties-core.md)** van het label in op de volgende expressie:  
    **ThisItem!UnitsInStock** <br/>
   
    Hierdoor toont het label voor ieder product hoeveel artikelen er op voorraad zijn:

![][8]  

> [!NOTE]
> Standaard is de eigenschap **[Text](controls/properties-core.md)** van het bovenste label ingesteld op ```ThisItem!ProductName```. U kunt dit wijzigen naar ieder ander item in uw verzameling. Als uw verzameling bijvoorbeeld velden heeft voor *ProductDescription* of *Price*, kunt u het label instellen op ```ThisItem!ProductDescription``` of ```ThisItem!Price```.
> 
> 

Met behulp van deze stappen hebt u een set gegevens, waarom een aantal JPG-afbeeldingen, geïmporteerd naar een verzameling. U hebt vervolgens een galerie toegevoegd die deze gegevens weergeeft en een label geconfigureerd om voor elk product te tonen hoeveel artikelen er op voorraad zijn.

## <a name="highlight-the-gallery-item-you-select"></a>Het galerie-item dat u selecteert markeren
1. Selecteer een willekeurig item in de galerie, *behalve* het eerste item. Het bewerkingspictogram wordt weergegeven (linkerbovenhoek). Selecteer het bewerkingspictogram:  
   ![][9]  
2. Selecteer op het tabblad **Invoegen** de optie **Vormen** en selecteer vervolgens de rechthoek. Er verschijnt een egaal blauwe rechthoek in elk galerie-item.
3. Selecteer op het tabblad **Start** de optie **Opvulling** en selecteer vervolgens **Geen opvulling**.
4. Selecteer **Rand**, selecteer den **Randstijl** en selecteer vervolgens de ononderbroken lijn.
5. Selecteer nogmaals **Rand** en stel de dikte in op 3. Wijzig de grootte van de rechthoek, zodat deze het galerie-item omringt. De items in uw galerie hebben nu een blauwe rand en zouden moeten lijken op de onderstaande afbeelding:  
   ![][10]  
6. Selecteer op het tabblad **Vormen** de optie **Zichtbaar** en voer in de formulebalk de volgende formule in:  
   
    **If(ThisItem!IsSelected, true)**
   
    De huidige selectie in een galerie wordt omringd door een blauwe rechthoek. Selecteer enkele galerie-items om te controleren of de rechthoek inderdaad wordt weergegeven rond elk item dat u selecteert. Denk eraan dat u ook het **Voorbeeld** ![][2]kunt openen om wat u maakt te bekijken en testen.

> [!TIP]
> Selecteer de rechthoek, selecteert dan op het tabblad **Start** de optie **Volgorde wijzigen** en selecteer vervolgens **Naar achtergrond**. Met deze functie kunt u een galerie-item selecteren zonder dat de rand iets blokkeert.
> 
> 

Met behulp van deze stappen hebt u een rand om de huidige selectie in de galerie toegevoegd.

## <a name="sort-and-filter-items-in-the-gallery"></a>Items in de galerie sorteren en filteren
In deze stappen gaan we de galerie-items in oplopende of aflopende volgorde sorteren. Bovendien gaan we een schuifregelaar toevoegen om de galerie-items te filteren op basis van een op te geven aantal artikelen dat op voorraad is.

#### <a name="sort-in-ascending-or-descending-order"></a>In oplopende of aflopende volgorde sorteren
1. Selecteer een willekeurig item in de galerie, *behalve* het eerste item.
2. De eigenschap **[Items](controls/properties-core.md)** is momenteel ingesteld op Inventory (de naam van uw verzameling). Verander dit naar:  
   
    **Sort(Inventory, ProductName)**
   
    Als u dit doet, worden de items in de galerie op productnaam gesorteerd, in oplopende volgorde: ![][11]  
   
    Probeer eens te sorteren op aflopende volgorde. Stel de eigenschap **[Items](controls/properties-core.md)** van de galerie in op de volgende formule:  
   
    Sort(Inventory, ProductName, Descending)  

#### <a name="add-a-slider-control-and-filter-items-in-the-gallery"></a>Een schuifregelaar toevoegen en items in de galerie filteren
1. Voeg een schuifregelaar toe (tabblad **Invoegen** > **Besturingselementen**), wijzig de naam naar **StockFilter** en verplaats deze naar onder de galerie.
2. Configureer de schuifregelaar zo, dat gebruikers deze niet kunnen instellen op een waarde buiten het waardebereik van de voorraadaantallen:  
   
   1. Selecteer op het tabblad **Inhoud** de eigenschap **Min** en voer de volgende expressie in:  
      ```Min(Inventory, UnitsInStock)```  
   2. Selecteer op het tabblad **Inhoud** de eigenschap **Max** en voer de volgende expressie in:  
      ```Max(Inventory, UnitsInStock)```
3. Selecteer een willekeurig item in de galerie, *behalve* het eerste item. Stel de eigenschap **[Items](controls/properties-core.md)** van de galerie in op de volgende expressie:  
   ```Filter(Inventory, UnitsInStock<=StockFilter!Value)```
4. Verschuif in het **Voorbeeld** de schuifregelaar naar een waarde tussen het hoogste en het laagste voorraadaantal in de galerie. Als u de schuifregelaar aanpast, worden alleen producten getoond waarvan de voorraadwaarde kleiner is dan de waarde die u hebt gekozen:  
   ![][13]  

Nu gaan we ons filter toevoegen:

1. Ga terug naar de ontwerpomgeving.
2. Selecteer op het tabblad **Invoegen** de optie **Tekst**, selecteer dan **Tekstinvoer** en wijzig de naam van het nieuwe besturingselement naar **NameFilter**. Plaats het tekstbesturingselement onder de schuifregelaar.
3. Stel de eigenschap **[Items](controls/properties-core.md)** van de galerie in op de volgende expressie:  
   ```Filter(Inventory, UnitsInStock<=StockFilter!Value && NameFilter!Text in ProductName)```
4. Stel in de **Preview** de schuifregelaar in op *30* en typ in het besturingselement voor tekstinvoer de letter *g*. De galerie toont nu het enige product met minder dan 30 artikelen op voorraad *en* een naam met de letter "g":  
   ![][14]  

## <a name="tips-and-tricks"></a>Tips en trucs
* U kunt op ieder moment de knop Voorbeeld (![][2]) gebruiken om te zien wat u hebt gemaakt en om dit te testen.
* Wanneer u uw app ontwerpt, kunt u de grootte van de besturingselementen aanpassen en ze verplaatsen door te klikken en te slepen.
* Druk op **Esc** of selecteer de **X** om het voorbeeldvenster te sluiten.
* Wanneer u een galerie gebruikt, selecteert u het eerste item in de galerie om alle items in de galerie te wijzigen. Selecteer bijvoorbeeld het eerste item om een rand toe te voegen aan alle items in de galerie.
* Om de eigenschappen van de galerie bij te werken, selecteert u een willekeurig item in de galerie, *behalve* het eerste item. Selecteer bijvoorbeeld het tweede item voor het bijwerken van eigenschappen als *Items*, *ShowScrollbar* en andere eigenschappen die betrekking hebben op de galerie zelf (en niet op de items in de galerie).  

## <a name="what-you-learned"></a>Wat u hebt geleerd
In dit onderwerp hebt u het volgende geleerd:

* Een verzameling maken, gegevens importeren naar die verzameling, waaronder JPG-afbeeldingen, en het weergeven van deze gegevens in een galerie.
* Het configureren van een tabel onder elke afbeelding in de galerie, met daarin de voorraadaantallen per item.
* Het toevoegen van een rand rondom het item dat wordt geselecteerd.
* De items sorteren op productnaam, in oplopende of aflopende volgorde.
* Een schuifregelaar en een tekstbesturingselement toevoegen om producten te filteren op basis van de productnaam en het aantal items op voorraad.

[1]: ./media/show-images-text-gallery-sort-filter/import.png
[2]: ./media/show-images-text-gallery-sort-filter/preview.png
[3]: ./media/show-images-text-gallery-sort-filter/inventorycollection.png
[4]: ./media/show-images-text-gallery-sort-filter/insert-vertical.png
[5]: ./media/show-images-text-gallery-sort-filter/itemsinventory.png
[6]: ./media/show-images-text-gallery-sort-filter/threeimages.png
[7]: ./media/show-images-text-gallery-sort-filter/firstitem.png
[8]: ./media/show-images-text-gallery-sort-filter/bottomlabel.png
[9]: ./media/show-images-text-gallery-sort-filter/editgallery.png
[10]: ./media/show-images-text-gallery-sort-filter/border.png
[11]: ./media/show-images-text-gallery-sort-filter/sort.png
[12]: ./media/show-images-text-gallery-sort-filter/onselect.png
[13]: ./media/show-images-text-gallery-sort-filter/slider.png
[14]: ./media/show-images-text-gallery-sort-filter/inputandslider.png
[15]: ./media/show-images-text-gallery-sort-filter/select-overlay.png
