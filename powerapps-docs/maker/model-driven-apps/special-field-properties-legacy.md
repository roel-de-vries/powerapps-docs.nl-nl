---
title: Speciale veldeigenschappen van modelgestuurde apps voor hoofdformulieren in PowerApps | MicrosoftDocs
description: De speciale veldeigenschappen voor hoofdformulieren begrijpen
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
ms.openlocfilehash: 0c4e67b14816ae6eaf100221ac0ac29269000f9b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674060"
---
# <a name="overview-of-model-driven-app-special-field-properties"></a>Overzicht van speciale veldeigenschappen van modelgestuurde apps

 Van alle velden staan de eigenschappen vermeld in [Algemene veldeigenschappen](common-field-properties-legacy.md), maar bepaalde velden hebben aanvullende eigenschappen, zoals dit veld Recht dat kan worden geopend vanuit het hoofdformulier voor de Case-entiteit.  

![special-properties-dialog](media/special-properties.png)
  
<a name="BKMK_LookupFieldProperties"></a>  
 
## <a name="lookup-field-properties"></a>Eigenschappen van opzoekveld  
  
> [!NOTE]
>  De opties die in de onderstaande tabel worden beschreven, zijn alleen beschikbaar voor opzoekvelden met één entiteit.  
  
|Sectie|Eigenschap|Beschrijving|  
|-------------|--------------|-----------------|  
|**Filtering van gerelateerde records**|**Alleen records weergeven waarin**|Wanneer dit is ingeschakeld, worden er aanvullende filters toegepast op de records die worden weergegeven wanneer gebruikers naar een record zoeken. Dit helpt relevantere zoekresultaten te retourneren wanneer de waarde van de zoekopdracht wordt ingesteld.<br /><br /> Standaard is dit uitgeschakeld.<br /><br /> In de tabel onder deze tabel staan de relatiecombinaties die mogelijk zijn wanneer u gerelateerde records filtert.*<br /><br /> In de eerste lijst staan alle potentiële relaties die u kunt gebruiken om deze zoekopdracht te filteren. Selecteer een relatie.<br /><br /> In de tweede lijst staan vervolgens alle relaties die de gerelateerde entiteit (geselecteerd in de eerste lijst) verbinden met de doelentiteit. Selecteer een relatie.<br /><br /> Schakel het selectievakje **Gebruikers toestaan het filter uit te schakelen** in om gebruikers de optie te geven het filter uit te schakelen dat u hier definieert.<br /><br /> Wanneer gebruikers de optie **Meer records opzoeken** selecteren terwijl ze de waarde voor een zoekopdracht instellen, zien ze dit dialoogvenster.<br /><br /> ![look-up-more-records](media/crm-ua-v-8-1-look-up-more-records.png) <br /><br /> Als u de optie **Gebruikers toestaan het filter uit te schakelen** hebt geselecteerd terwijl u het opzoekveld configureerde, zien gebruikers het selectievakje om het filter uit te schakelen.  Zo kunnen ze een breder scala aan records zien. Als u wilt verzekeren dat gebruikers alleen een beperkte reeks records zien die door dit filter wordt gedefinieerd, schakelt u het selectievakje **Gebruikers toestaan het filter uit te schakelen** uit.|  
|**Aanvullende eigenschappen**|**Zoekvak weergeven in opzoekvenster**|U kunt ervoor kiezen het zoekvak niet weer te geven in het opzoekvenster.|  
||**Standaardweergave**|Deze weergave wordt gebruikt om de resultaten van de inline zoekopdracht te filteren en de standaardweergave in te stellen die in het opzoekvenster wordt getoond wanneer gebruikers de optie **Meer records opzoeken** selecteren.<br /><br /> De standaardweergave bepaalt ook welke velden worden opgenomen in de inline zoekopdracht.<br /><br /> Voor zoekopdrachten die alleen selectie van één entiteitstype toestaan, worden de velden die in de inline zoekopdracht worden weergegeven ingesteld om als eerste twee in de standaardweergave te worden opgenomen. In dit voorbeeld zijn **Telefoonnummer 1** en **E-mail** de eerste twee kolommen in de standaardweergave die worden geconfigureerd voor een accountzoekopdracht.<br /><br /> Voor systeemzoekopdrachten die meerdere entiteitstypen toestaan, worden de eerste twee kolommen van de opzoekweergave voor de entiteit weergegeven.|  
||**Weergave selecteren**|U kunt kiezen uit drie opties:<br /><br /> -   **Uit**: Gebruikers niet toestaan een andere weergave te kiezen.<br />-   **Alle weergaven weergeven**: Alle weergaven zijn beschikbaar.<br />-   **Geselecteerde weergaven weergeven**: Wanneer u deze optie kiest, kunt u de Ctrl-toets en uw cursor gebruiken om te kiezen welke weergaven er worden weergegeven. De selectie van de opzoekweergave voor de entiteit kan niet worden opgeheven.|  
  
 **\*Mogelijke relatiecombinaties**  
  
|Relatie eerste lijst|Relatie tweede lijst|Beschikbaar?|  
|-----------------------------|------------------------------|----------------|  
|N:1|1:N|Ja|  
|N:1|N:1|Ja|  
|N:1|N:N|Ja|  
|1:N|1:N|Ja|  
|1:N|N:1|Nee|  
|1:N|N:N|Nee|  
|N:N|1:N|Ja|  
|N:N|N:1|Nee|  
|N:N|N:N|Nee|  
  
<a name="BKMK_TwoOptionProperties"></a>   

### <a name="two-option-field-properties"></a>Eigenschappen van velden met twee opties  
 Op het tabblad Opmaak hebben velden met twee opties de volgende opmaakkeuzes:  
  
- **Twee keuzerondjes**: Twee besturingselementen met labels. Er kan slechts één worden geselecteerd.  
  
- **Selectievakje**: Eén selectievakje om de waarde Waar of Onwaar in te stellen.  
  
- **Lijst**: Een vervolgkeuzelijst die beide waarden bevat.  
  
<a name="BKMK_MultipleLinesOfTextProperties"></a>   

### <a name="multiple-lines-of-text-field-properties"></a>Eigenschappen van velden met meerdere tekstregels  
 Velden met meerdere tekstregels en één tekstregel die de opmaak `Text Area` gebruiken, hebben een eigenschap **Rij-indeling**. Met deze eigenschap kunt u een waarde voor **Aantal rijen** opgeven of **Vouw automatisch uit om de beschikbare ruimte te gebruiken** selecteren.  

## <a name="next-steps"></a>Volgende stappen

[Het hoofdformulier en de bijbehorende onderdelen gebruiken](use-main-form-and-components.md)
