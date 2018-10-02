---
title: De formuliereneditor voor modelgestuurde apps openen in PowerApps | MicrosoftDocs
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="open-the-model-driven-app-form-editor"></a>De formuliereneditor voor modelgestuurde apps openen 
In de formuliereneditor kunt u formulieren ontwerpen door onderdelen zoals secties, tabbladen, velden en besturingselementen te slepen naar het canvas van de formuliereneditor. In dit onderwerp leert u hoe u de formuliereneditor op verschillende manieren opent.
 
Als u nieuwe oplossingsonderdelen maakt tijdens het bewerken van het formulier, bijvoorbeeld webresources, dan zullen de namen van de onderdelen het aanpassingsvoorvoegsel van de oplossingsuitgever voor de standaardoplossing gebruiken en worden deze onderdelen alleen opgenomen in de standaardoplossing. Als u wilt dat nieuwe oplossingsonderdelen worden opgenomen in een specifieke onbeheerde oplossing, moet u de formuliereneditor openen via die onbeheerde oplossing.  

## <a name="access-the-form-editor-from-the-powerapps-site"></a>De formuliereneditor openen via de PowerApps-site

1. Meld u aan bij [PowerApps](https://web.powerapps.com/). 

2. Selecteer **Modelgestuurd** > **Gegevens** > **Entiteiten** en selecteer de gewenste entiteit, bijvoorbeeld Account. 

3. Selecteer het tabblad **Formulieren** en open het gewenste formulier, bijvoorbeeld het hoofdformulier **Account**.

## <a name="access-the-form-editor-from-solution-explorer"></a>De formuliereneditor openen via de oplossingenverkenner
  
1.  Open [oplossingenverkenner](advanced-navigation.md#solution-explorer).
  
2.  Vouw onder **Onderdelen** achtereenvolgens **Entiteiten** en de gewenste entiteit uit en klik op **Formulieren**.  
  
3.  Klik in de lijst met formulieren op het formulier dat u wilt bewerken.  
  

## <a name="access-the-form-editor-through-the-command-bar-within-a-model-driven-app"></a>De formuliereneditor openen via de opdrachtbalk in een modelgestuurde app 
  
1.  Open een record.  
  
2.  Als er meerdere hoofdformulieren voor de entiteit zijn, controleer dan het formulier dat u wilt bewerken. Als dit niet zo is, gebruikt u de formulierkiezer om het formulier te kiezen dat u wilt bewerken.  
  
3.  Selecteer de knop **Meer opdrachten** ![Knop Meer opdrachten in Afspraakactiviteit](media/more-commands.gif "Knop Meer opdrachten in Afspraakactiviteit").  
  
4.  Selecteer **Formuliereneditor**.  

## <a name="access-the-form-editor-from-within-dynamics-365-customer-engagement"></a>De formuliereneditor openen vanuit Dynamics 365 Customer Engagement
  
 U kunt toegang krijgen tot de formuliereneditor in Dynamics 365 Customer Engagement middels de opdrachtbalk of het lint, afhankelijk van de entiteit. Met beide methoden wordt het formulier in de context van de standaardoplossing geopend. 

## <a name="access-the-form-editor-for-an-unmanaged-solution"></a>De formuliereneditor voor een onbeheerde oplossing openen  
  
1.  Open [Oplossingen](advanced-navigation.md#solutions).  
  
2.  Dubbelklik op de onbeheerde oplossing waarmee u wilt werken.  
  
3.  Zoek de entiteit met het formulier dat u wilt bewerken. Als de entiteit er niet is, moet u die toevoegen. Meer informatie: [Een entiteit toevoegen aan een onbeheerde oplossing](#add-an-entity-to-an-unmanaged-solution) 
  
### <a name="add-an-entity-to-an-unmanaged-solution"></a>Een entiteit toevoegen aan een onbeheerde oplossing  
  
1.  Selecteer het knooppunt **Entiteiten** en klik in de werkbalk boven de lijst op **Bestaande entiteit toevoegen**.  
  
2.  Selecteer de entiteit die u wilt toevoegen in het dialoogvenster **Oplossingsonderdelen selecteren**, waarbij de schakelaar **Onderdeeltype** is ingesteld op **Entiteit** en klik op **OK**.  
  
3.  Als het dialoogvenster **Er ontbreken vereiste onderdelen** wordt weergegeven, kunt u op de optie **Nee, vereiste onderdelen niet toevoegen** klikken als u niet van plan bent de onbeheerde oplossing naar een andere omgeving te exporteren. Als u ervoor kiest om ontbrekende vereiste onderdelen op dit moment niet op te nemen, kunt u ze later toevoegen. U ontvangt opnieuw een melding als u deze oplossing in de toekomst exporteert.  
  
5.  Vouw in de oplossingsverkenner de entiteit uit met het formulier dat u wilt bewerken en selecteer **Formulieren**.  
  
6.  Dubbelklik in de lijst met formulieren op het formulier dat u wilt bewerken.  

## <a name="next-steps"></a>Volgende stappen

[Formulieren maken en ontwerpen](create-design-forms.md)
