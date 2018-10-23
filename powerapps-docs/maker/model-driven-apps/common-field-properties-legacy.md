---
title: Algemene veldeigenschappen voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: De algemene veldeigenschappen voor hoofdformulieren in Dynamics 365 voor Customer Engagement begrijpen
Keywords: Main form; Common field properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 2b91ee28-7f09-435e-9fae-5225aa698e22
ms.openlocfilehash: 74e67dd4299d06a54d5ec85765e4e5d03710b432
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675020"
---
# <a name="model-driven-app-common-field-properties"></a>Algemene veldeigenschappen van modelgestuurde apps

 Velden in een formulier geven besturingselementen weer die mensen gebruiken om gegevens in een entiteitsrecord te bekijken of te bewerken. Velden kunnen zo worden opgemaakt dat deze maximaal vier kolommen in een sectie bevatten.  

U kunt toegang krijgen tot **Algemene veldeigenschappen** in Solution Explorer. Vouw onder **Onderdelen** de optie **Entiteiten** uit. Vouw de gewenste entiteit uit en selecteer vervolgens **Formulieren**. Open in de lijst met formulieren het formulier van het type **Hoofd**. Dubbelklik vervolgens op één van de velden om de algemene veldeigenschappen weer te geven.

![common-field-properties](media/common-field-properties.png)
  
In de volgende tabel worden de eigenschappen beschreven die alle velden hebben. Bepaalde veldtypen hebben speciale eigenschappen. Deze worden beschreven in [Speciale veldeigenschappen](special-field-properties-legacy.md).  
  
|Tabblad|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Weergave**|**Label**|**Vereist**: standaard komt het label overeen met de weergavenaam van het veld. U kunt die naam voor het formulier overschrijven door hier een ander label in te voeren.|  
||**Label weergeven op het formulier**|U kunt ervoor kiezen het label helemaal niet weer te geven.|  
||**Veldgedrag**|Hiermee wordt het veldniveaugedrag opgegeven met behulp van de selectievakjes.|  
||**Vergrendelen**|Hierdoor voorkomt u dat het veld per ongeluk uit het formulier wordt verwijderd. Hierdoor voorkomt u dat configuratie die u op het veld hebt toegepast, zoals gebeurtenis-handlers, wordt gewist als het veld wordt verwijderd. Als u dit veld wilt verwijderen, moet deze instelling eerst door een aanpasser worden gewist.|  
||**Zichtbaarheid**|Weergave van het veld is optioneel en kan worden beheerd met behulp van scripts. Meer informatie: [Opties voor zichtbaarheid](visibility-options-legacy.md)|  
||**Beschikbaarheid**|Kies of u het tabblad beschikbaar wilt maken op de telefoon.|
|**Opmaak**|**Selecteer het aantal kolommen dat het besturingselement in beslag neemt**|Als de sectie die de velden bevat uit meer dan een kolom bestaat, kunt u het veld zo instellen dat het evenveel kolommen in beslag neemt als de sectie.|  
|**Details**|**Weergavenaam**, **Naam** en **Beschrijving**|Deze alleen-lezenvelden zijn alleen bedoeld als referentie. Klik op de knop **Bewerken** voor handige toegang tot de velddefinitie als u deze wilt bewerken.<br /><br /> Elk exemplaar van een veld in het formulier heeft een naameigenschap, zodat hier in formulierscripts naar kan worden verwezen. Deze naam wordt echter beheerd door de toepassing. Het eerste exemplaar van het veld is de naam van het veld dat is opgegeven toen dit werd gemaakt. Meer informatie: [Velden maken en bewerken](../common-data-service/create-edit-fields.md)<br /><br /> Steeds wanneer een veld opnieuw in een formulier wordt ingevoegd, krijgt de naam een nummer als achtervoegsel, te beginnen met 1. Als de veldnaam dus ‘new_cost’ is, is ‘new_cost’ het eerste exemplaar, ‘new_cost1’ het tweede exemplaar enzovoort voor elk exemplaar van het veld in het formulier.<br /><br />**Opmerking:** de veldwaarde **Beschrijving** biedt knopinfo voor het veld wanneer gebruikers hun cursor erboven plaatsen.|  
|**Gebeurtenissen**|**Formulierbibliotheken**|Geef JavaScript-webresources op die worden gebruikt in de gebeurtenis-handler van het veld `OnChange`.<br /><br />|  
||**Event Handlers**|Configureer de functies vanuit de formulierbibliotheken die moeten worden aangeroepen voor de gebeurtenis van het veld `OnChange`. Meer informatie: [Gebeurtenis-handlers configureren](configure-event-handlers-legacy.md)|  
|**Bedrijfsregels**|**Bedrijfsregels**|Bekijk en beheer bedrijfsregels die naar dit veld verwijzen. Meer informatie: [Bedrijfsregels maken en aanbevelingen doen](create-business-rules-recommendations-apply-logic-form.md)|  
|**Besturingselementen**|**Besturingselementen**|Voeg besturingselementen toe en geef hun beschikbaarheid op internet, telefoons en tablets op.|  

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de bijbehorende onderdelen gebruiken](use-main-form-and-components.md)
