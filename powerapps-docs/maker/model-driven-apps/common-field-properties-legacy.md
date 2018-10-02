---
title: Algemene veldeigenschappen voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: De algemene veldeigenschappen voor hoofdformulieren in Dynamics 365 for Customer Engagement begrijpen
Keywords: Main form; Common field properties; Dynamics 365
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: crm-online
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 2b91ee28-7f09-435e-9fae-5225aa698e22
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-common-field-properties"></a>Algemene veldeigenschappen voor modelgestuurde apps

 Velden in een formulier geven de besturingselementen weer die mensen gebruiken om gegevens in een entiteitsrecord weer te geven of te bewerken. Velden kunnen zo worden opgemaakt dat ze maximaal vier kolommen binnen een sectie in beslag nemen.  

U kunt **Algemene veldeigenschappen** openen in de oplossingenverkenner. Vouw onder **Onderdelen** achtereenvolgens **Entiteiten** en de gewenste entiteit uit en selecteer vervolgens **Formulieren**.. In de lijst met formulieren opent u het formulier van het type **Hoofd**. Dubbelklik op een van de velden om Algemene veldeigenschappen weer te geven.

![algemene-veldeigenschappen](media/common-field-properties.png)
  
In de volgende tabel worden eigenschappen beschreven die alle velden hebben. Bepaalde typen velden hebben speciale eigenschappen. Deze worden beschreven in [Speciale veldeigenschappen](special-field-properties-legacy.md).  
  
|Tab|Eigenschap|Beschrijving|  
|---------|--------------|-----------------|  
|**Weergave**|**Label**|**Vereist**: Het label geeft standaard de weergavenaam van het veld weer. U kunt die naam voor het formulier overschrijven door hier een ander label in te voeren.|  
||**Label in het formulier weergeven**|U kunt besluiten de naam helemaal niet weer te geven.|  
||**Veldgedrag**|Geef het veldniveaugedrag op met de selectievakjes.|  
||**Vergrendelen**|Hierdoor wordt voorkomen dat het veld per ongeluk uit het formulier wordt verwijderd. Hiervoor wordt voorkomen dat de configuratie die u op het veld heb toegepast, zoals gebeurtenis-handlers, wordt gewist als het veld wordt verwijderd. Om dit veld te verwijderen, moet een aanpasser eerst deze instelling uitschakelen.|  
||**Zichtbaarheid**|Weergave van het veld is optioneel en kan worden beheerd met behulp van scripts. Meer informatie: [Zichtbaarheidsopties](visibility-options-legacy.md)|  
||**Beschikbaarheid**|Geef op of het tabblad beschikbaar moet zijn op de telefoon.|
|**Opmaak**|**Selecteer het aantal kolommen dat het besturingselement in beslag neemt**|Als de sectie die de velden bevat meer dan één kolom heeft, kunt u het veld zo instellen dat het evenveel kolommen bezet als sectie.|  
|**Details**|**Weergavenaam**, **Naam** en **Beschrijving**|Deze velden met het kenmerk Alleen-lezen dienen ter referentie. Klik op de knop **Bewerken** voor gemakkelijke toegang tot de velddefinitie als u die wilt bewerken.<br /><br /> Elk exemplaar van een veld op het formulier heeft een naameigenschap zodat ernaar kan worden verwezen in formulierscripts, maar deze naam wordt beheerd door de toepassing. Het eerste exemplaar van het veld is de naam van het opgegeven veld toen het werd gemaakt. Meer informatie: [Velden maken en bewerken](../common-data-service/create-edit-fields.md)<br /><br /> Voor elke extra keer dat een veld in een formulier wordt opgenomen, voegt de naam aan het eind een getal toe dat begint bij 1. Dus als de veldnaam "new_cost" is, is het eerste exemplaar "new_cost", het tweede "new_cost1", enzovoort voor elk exemplaar van het veld in het formulier.<br /><br />**Opmerking:** De waarde van het veld **Beschrijving** biedt tekst van knopinfo voor het veld als mensen hun cursor erover plaatsen.|  
|**Gebeurtenissen**|**Formulierbibliotheken**|Geef JavaScript-webresources op die worden gebruikt in de gebeurtenishandler van het veld `OnChange`.<br /><br />|  
||**Gebeurtenishandlers**|Configureer de functies van de formulierbibliotheken die moeten worden aangevraagd voor de gebeurtenis van het veld `OnChange`. Meer informatie: [Gebeurtenishandlers configureren](configure-event-handlers-legacy.md)|  
|**Bedrijfsregels**|**Bedrijfsregels**|Bedrijfsregels die naar dit veld verwijzen weergeven en beheren. Meer informatie: [Bedrijfsregels en aanbevelingen maken](create-business-rules-recommendations-apply-logic-form.md)|  
|**Besturingselementen**|**Besturingselementen**|Voeg besturingselementen toe en geef hun beschikbaarheid op het web, telefoon en tablet op.|  

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
