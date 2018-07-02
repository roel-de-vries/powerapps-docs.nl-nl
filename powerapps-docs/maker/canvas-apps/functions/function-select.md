---
title: De functie Select | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis, voor de functie Select in PowerApps
author: gregli-msft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 06/11/2018
ms.author: gregli
ms.openlocfilehash: 8d84dcf1496e9f8f21ba059deb89549b6f238c97
ms.sourcegitcommit: 63351b1bda5a8dd00786912f95aba9fb3ebfe75c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2018
ms.locfileid: "36261754"
---
# <a name="select-function-in-powerapps"></a>De functie Select in PowerApps
Met deze functie simuleert u een select-actie op een besturingselement, waardoor de formule **OnSelect** wordt geëvalueerd.

## <a name="description"></a>Beschrijving
De functie **Select** simuleert een select-actie op een besturingselement alsof de gebruiker op het besturingselement heeft geklikt of getikt. Als gevolg hiervan wordt de formule **OnSelect** voor het doelbesturingselement geëvalueerd.

Gebruik **Select** om een select-actie door te geven aan een bovenliggend besturingselement. Deze manier van doorgeven is de standaardinstelling in bijvoorbeeld galerieën. De eigenschap **OnSelect** van een besturingselement in een **[galerie](../controls/control-gallery.md)** is standaard ingesteld op **Select(Parent)**. Op die manier kunt u de waarde van de eigenschap **OnSelect** van het besturingselement in de galerie zelf instellen, waarna die formule wordt geëvalueerd ongeacht waar in de galerie een gebruiker klikt of tikt.

Als een of meer besturingselementen in de galerie verschillende acties moeten uitvoeren vanuit de galerie zelf, stelt u de eigenschap **OnSelect** voor deze besturingselementen in op iets anders dan de standaardwaarde. Voor de meeste besturingselementen in de galerie kunt u de standaardwaarden voor de eigenschap **OnSelect** ongewijzigd laten als ze dezelfde actie moeten uitvoeren als de galerie zelf.

**Select** plaats de eigenschap **OnSelect** van het doelbesturingselement in de wachtrij voor latere verwerking, die plaats kan vinden nadat de evaluatie van de huidige formule is voltooid. **Select** heeft niet tot gevolg dat de eigenschap **OnSelect** van het doelbesturingselement direct wordt geëvalueerd. Het is evenmin zo dat **Select** wacht totdat **OnSelect** is geëvalueerd.

**Select** werkt niet voorbij de grenzen van containerbesturingselementen, zoals een galerie of formulier. Besturingselementen in een containerbesturingselement kunnen alleen het onderwerp zijn van een **Select**-functie in formules die zich in hetzelfde containerbesturingselement bevinden. U kunt **Select** niet gebruiken tussen schermen.

U kunt **Select** alleen gebruiken met besturingselementen die een eigenschap **OnSelect** hebben.

U kunt **Select** alleen gebruiken in [gedragsformules](../working-with-formulas-in-depth.md).

Een besturingselement kan **Select** niet op zichzelf toepassen en ook niet indirect via andere besturingselementen.

## <a name="syntax"></a>Syntaxis
**Select**( *Besturingselement* )

* *Besturingselement*: vereist.  Het besturingselement dat moet worden geselecteerd namens de gebruiker.

## <a name="examples"></a>Voorbeelden

#### <a name="basic-usage"></a>Basisgebruik

1. Voeg een besturingselement van het type **[Knop](../controls/control-button.md)** toe en geef dit de naam **Button1** als het een andere naam heeft.

1. Stel de eigenschap **OnSelect** van **Button1** in op deze formule:

    **Notify( "Hallo wereld" )**

1. Voeg op hetzelfde scherm een tweede besturingselement **Knop** toe en stel de eigenschap **OnSelect** van dit element in op deze formule:

    **Select( Button1 )**

1. Selecteer de tweede knop terwijl u de Alt-toets ingedrukt houdt.

    U ziet bovenaan de app een melding. Deze melding is gegenereerd door de eigenschap **OnSelect** van **Button1**.

    ![Een animatie met de instellingen van de eigenschap OnSelect voor de twee knoppen en de melding die wordt weergegeven wanneer op de tweede knop wordt geklikt](media/function-select/basic-select.gif)

#### <a name="gallery-control"></a>Besturingselement Galerie

1. Voeg een verticaal besturingselement **[Galerie](../controls/control-gallery.md)** toe dat andere besturingselementen bevat.

    ![Selecteer een verticale galerie met besturingselementen](media/function-select/select-gallery.png)

2. Stel de eigenschap **OnSelect** van de galerie in op deze formule:
 
    **Notify( "Galerie geselecteerd" )**

3. Klik of tik met de Alt-toets ingedrukt op de achtergrond van de galerie of een besturingselement in de galerie.

    In alle gevallen ziet u de melding **Galerie geselecteerd** bovenaan de app.

    Gebruik de eigenschap **OnSelect** van de galerie om de standaardactie op te geven die moet worden uitgevoerd wanneer de gebruiker op een item in de galerie klikt of tikt.

5. Stel de eigenschap **OnSelect** van het besturingselement Image in op deze formule:

    **Notify( "Afbeelding geselecteerd", Success )**

6. Klik of tik met de Alt-toets ingedrukt op de verschillende elementen van de galerie.

    Wanneer u op een besturingselement in de galerie klikt of tikt buiten de afbeelding, wordt **Galerie geselecteerd** gewoon weergegeven. Wanneer u echter op de afbeelding klikt of tikt, wordt **Afbeelding geselecteerd** weergegeven.
 
    Gebruik afzonderlijke besturingselementen in de galerie om acties uit te voeren die anders zijn dan de standaardactie van de galerie.

    ![Een animatie waarin de standaardwaarde van de eigenschap OnSelect voor een galeriebesturingselement wordt weergegeven, evenals een besturingselement waarmee een andere actie wordt uitgevoerd](media/function-select/gallery-select.gif)
