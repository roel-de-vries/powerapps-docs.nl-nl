---
title: De formuliereditor voor modelgestuurde apps openen in PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 8478a07a-c697-4784-874b-36958eb4f95d
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: e0fe15df88fccbaee3c13a344416a434e1f92923
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674959"
---
# <a name="open-the-model-driven-app-form-editor"></a>De formuliereditor voor modelgestuurde apps openen 
De formuliereditor is de plek waar u formulieren ontwerpt door onderdelen zoals secties, tabbladen, velden en besturingselementen op het canvas in de formuliereditor neer te zetten. In dit onderwerp maakt u kennis met een aantal verschillende manieren om toegang te krijgen tot de formuliereditor.
 
Als u nieuwe oplossingsonderdelen maakt tijdens het bewerken van het formulier, bijvoorbeeld webresources, wordt het aanpassingsvoorvoegsel van de oplossingsuitgever gebruikt voor de namen van de onderdelen voor de standaardoplossing en worden deze onderdelen alleen ingevoegd in de standaardoplossing. Als u nieuwe oplossingsonderdelen wilt invoegen in een specifieke onbeheerde oplossing, moet u de formuliereditor openen via die onbeheerde oplossing.  

## <a name="access-the-form-editor-from-the-powerapps-site"></a>Toegang tot de formuliereditor vanuit de PowerApps-site

1. Meld u aan bij [PowerApps](https://web.powerapps.com/). 

2. Selecteer **Modelgestuurd** > **Gegevens** > **Entiteiten** > en selecteer vervolgens de entiteit die u wilt, zoals de accountentiteit. 

3. Selecteer het tabblad **Formulieren** en open vervolgens het gewenste formulier, zoals het hoofdformulier **Account**.

## <a name="access-the-form-editor-from-solution-explorer"></a>Toegang tot de formuliereditor vanuit Solution Explorer
  
1.  Open de [oplossingsverkenner](advanced-navigation.md#solution-explorer).
  
2.  Vouw onder **Onderdelen** de optie **Entiteiten** uit, kies vervolgens de gewenste entiteit en klik op **Formulieren**.  
  
3.  Klik in de lijst met formulieren op het formulier dat u wilt bewerken.  
  

## <a name="access-the-form-editor-through-the-command-bar-within-a-model-driven-app"></a>Toegang tot de formuliereditor via de opdrachtbalk in een modelgestuurde app 
  
1.  Open een record.  
  
2.  Als er meerdere hoofdformulieren zijn voor de entiteit, moet u verifiëren dat het formulier het formulier is dat u wilt bewerken. Als dit niet het geval is, gebruik u de formulierkiezer om het formulier te selecteren dat u wilt bewerken.  
  
3.  Selecteer de knop **Meer opdrachten** ![Meer opdrachten-knop in Afspraakactiviteit](media/more-commands.gif "Meer opdrachten knop in Afspraakactiviteit").  
  
4.  Selecteer **Formuliereditor**.  

## <a name="access-the-form-editor-from-within-dynamics-365-customer-engagement"></a>Toegang tot de formuliereditor vanuit Dynamics 365 Customer Engagement
  
 U krijgt toegang tot de formuliereditor in Dynamics 365 Customer Engagement via de opdrachtbalk of het lint, afhankelijk van de entiteit. Met beide methoden wordt het formulier in de context van de standaardoplossing geopend. 

## <a name="access-the-form-editor-for-an-unmanaged-solution"></a>Toegang tot de formuliereditor voor een onbeheerde oplossing  
  
1.  Open [Oplossingen](advanced-navigation.md#solutions).  
  
2.  Dubbelklik op de onbeheerde oplossing waarmee u wilt werken.  
  
3.  Zoek de entiteit met het formulier dat u wilt bewerken. Als u de entiteit niet kunt vinden, moet u deze toevoegen. Meer informatie: [Een entiteit toevoegen aan een onbeheerde oplossing](#add-an-entity-to-an-unmanaged-solution) 
  
### <a name="add-an-entity-to-an-unmanaged-solution"></a>Een entiteit toevoegen aan een onbeheerde oplossing  
  
1.  Selecteer het knooppunt **Entiteiten** en klik in de werkbalk boven de lijst op **Bestaande toevoegen**.  
  
2.  Stel de kiezer **Onderdeeltype** in op **Entiteit**, selecteer in het dialoogvenster **Oplossingsonderdelen selecteren** de entiteit die u wilt toevoegen en klik op **OK**.  
  
3.  Als het dialoogvenster **Ontbrekende vereiste onderdelen** wordt weergegeven, kunt u klikken op **Nee, vereiste onderdelen niet invoegen** als u niet van plan bent deze onbeheerde oplossing naar een andere omgeving te exporteren. Als u ervoor kiest Ontbrekende vereiste onderdelen op dit moment niet in te voegen, kunt u ze later toevoegen. U ontvangt weer een melding zodra u deze oplossing later exporteert.  
  
5.  Vouw in de Solution Explorer de entiteit met het formulier dat u wilt bewerken uit en selecteer **Formulieren**.  
  
6.  Dubbelklik in de lijst met Formulieren op het formulier dat u wilt bewerken.  

## <a name="next-steps"></a>Volgende stappen

[Formulieren maken en ontwerpen](create-design-forms.md)
