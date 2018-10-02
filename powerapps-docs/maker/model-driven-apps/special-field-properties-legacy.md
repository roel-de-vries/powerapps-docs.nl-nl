---
title: Speciale veldeigenschappen voor hoofdformulieren voor modelgestuurde apps in PowerApps | MicrosoftDocs
description: Verkrijg inzicht in de eigenschappen van speciale velden voor hoofdformulieren
Keywords: Main forms; Special field properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 6ad7e43c-b6a1-48c4-9dfb-ed830142a841
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="overview-of-model-driven-app-special-field-properties"></a>Overzicht van speciale veldeigenschappen voor modelgestuurde apps

 Alle velden hebben de genoemde eigenschappen in [Algemene veldeigenschappen](common-field-properties-legacy.md), maar bepaalde velden hebben aanvullende eigenschappen, zoals dit rechtenveld dat vanuit het hoofdformulier voor de aanvraagentiteit kan worden geopend.  

![special-properties-dialog](media/special-properties.png)
  
<a name="BKMK_LookupFieldProperties"></a>  
 
## <a name="lookup-field-properties"></a>Opzoekveldeigenschappen  
  
> [!NOTE]
>  De opties die in de tabel hieronder worden beschreven, zijn alleen beschikbaar voor opzoekvelden met één entiteit.  
  
|Sectie|Eigenschap|Beschrijving|  
|-------------|--------------|-----------------|  
|**Filtering van gerelateerde records**|**Alleen records weergeven waar**|Als dit is ingesteld, wordt op de records die worden weergegeven wanneer gebruikers een record zoeken, aanvullende filtering toegepast. Dit lever meer relevante zoekacties op wanneer de waarde van de zoekactie wordt ingesteld.<br /><br /> Gewoonlijk is dit uitgeschakeld.<br /><br /> In de tabel na de volgende tabel worden de relatiecombinaties aangegeven die mogelijk zijn als u gerelateerde records filtert.*<br /><br /> De eerste lijst bevat alle potentiële relaties die u kunt gebruiken om deze opzoekweergave te filteren. Selecteer er één.<br /><br /> De tweede lijst bevat vervolgens alle relaties die de gerelateerde entiteit (geselecteerd in de eerste lijst) verbinden met de doelentiteit. Selecteer er één.<br /><br /> Schakel het selectievakje **Gebruikers toestaan om het filter uit te schakelen** in om gebruikers de mogelijkheid te geven het filter dat u hier definieert, uit te schakelen.<br /><br /> Als gebruikers de optie **Meer records opzoeken** selecteren als ze een opzoekwaarde instellen, zien ze dit dialoogvenster.<br /><br /> ![Meer records opzoeken](media/crm-ua-v-8-1-look-up-more-records.png) <br /><br /> Als u de optie **Gebruikers toestaan om het filter uit te schakelen** hebt ingeschakeld tijdens het configureren van het opzoekveld, zien gebruikers het selectievakje voor het uitschakelen van het filter.  Hierdoor wordt het voor hen mogelijk om meer records te zien. Als u zeker wilt weten dat gebruikers alleen een beperkt aantal records kunnen zien dat wordt gedefinieerd door dit filter, schakelt u het selectievakje **Gebruikers toestaan om het filter uit te schakelen** uit.|  
|**Aanvullende eigenschappen**|**Zoekvak weergeven in opzoekvenster**|U kunt ervoor kiezen het zoekvak niet weer te geven in het dialoogvenster Opzoeken.|  
||**Standaardweergave**|Deze weergave wordt gebruikt om de resultaten van de inlinezoekopdracht te filteren en de standaardweergave in te stellen die in het dialoogvenster wordt weergegeven wanneer gebruikers de optie **Meer records opzoeken** selecteren.<br /><br /> De standaardweergave beheert ook welke velden in de inlinezoekopdracht zijn opgenomen.<br /><br /> Voor zoekopdrachten waarbij slechts één entiteitstype kan worden geselecteerd, zijn de velden die worden weergegeven in de inlinezoekopdracht de eerste twee velden die zijn opgenomen in de standaardweergave. In dit voorbeeld zijn **Telefoonnummer** en **E-mail** de eerste twee kolommen die in de standaardweergave voor een accountzoekopdracht zijn geconfigureerd.<br /><br /> Voor systeemzoekopdrachten die meerdere entiteitstypen toestaan, worden de eerste twee kolommen van de opzoekweergave van de entiteit weergegeven.|  
||**Weergave selecteren**|U kunt uit drie opties kiezen:<br /><br /> -   **Uit**: Sta gebruikers niet toe een andere weergave te kiezen.<br />-   **Alle weergaven weergeven**: Alle weergaven zijn beschikbaar.<br />-   **Geselecteerde weergaven weergeven**: Als u deze optie kiest, kunt u met de Ctrl-toets en uw cursor kiezen welke weergaven worden weergegeven. De opzoekweergave voor de entiteit kan niet gedeselecteerd worden.|  
  
 **\*Mogelijke relatiecombinaties**  
  
|Eerste-lijstrelatie|Tweede-lijstrelatie|Beschikbaar?|  
|-----------------------------|------------------------------|----------------|  
|N:1|1:N|Ja|  
|N:1|N:1|Ja|  
|N:1|N:N|Ja|  
|1:N|1:N|Ja|  
|1:N|N:1|No|  
|1:N|N:N|No|  
|N:N|1:N|Ja|  
|N:N|N:1|No|  
|N:N|N:N|No|  
  
<a name="BKMK_TwoOptionProperties"></a>   

### <a name="two-option-field-properties"></a>Twee eigenschappen van het optieveld  
 Op het tabblad Opmaak bieden twee optievelden de volgende indelingsopties:  
  
- **Twee keuzerondjes**: Twee gelabelde besturingselementen met labels. Er kan er slechts één worden geselecteerd.  
  
- **Selectievakje**: De waarde va één selectievakje kan op true worden gezet, anders false.  
  
- **Lijst**: Een vervolgkeuzelijst die beide waarden bevat.  
  
<a name="BKMK_MultipleLinesOfTextProperties"></a>   

### <a name="multiple-lines-of-text-field-properties"></a>Meerdere regels van tekstveldeigenschappen  
 Tekstvelden met meerdere regels of één regel die de indeling `Text Area` gebruiken, hebben een **Rij-indeling**-eigenschap. Met deze eigenschap u kunt een waarde opgeven voor **Aantal rijen** of **Vouw automatisch uit om de beschikbare ruimte te gebruiken** selecteren.  

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de onderdelen ervan gebruiken](use-main-form-and-components.md)
