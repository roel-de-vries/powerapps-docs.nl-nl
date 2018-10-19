---
title: Pictogrammen voor aangepaste entiteiten voor modelgestuurde apps wijzigen in PowerApps | MicrosoftDocs
definition: Learn how to change the icon for a custom entity
ms.custom: ''
ms.date: 05/17/2018
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
ms.assetid: 477f9792-8207-49ef-8968-45274b5355a8
caps.latest.revision: 19
ms.author: matp
manager: kvivek
tags:
  - Links to topic not migrated
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="change-model-driven-app-custom-entity-icons"></a>Pictogrammen voor aangepaste entiteiten voor modelgestuurde apps wijzigen 

Als u een aangepaste entiteit maakt, wordt hieraan automatisch een standaardpictogram toegewezen. Alle aangepaste entiteiten gebruiken standaard hetzelfde pictogram. Gebruik aangepaste pictogrammen om onderscheid tussen uw aangepaste entiteiten te maken. U kunt de pictogrammen die zijn toegewezen aan systeementiteiten, niet wijzigen.  
  
 U kunt drie typen entiteitspictogrammen voor elke aangepaste entiteit uploaden. 

|Pictogramtype  |Beschrijving  |
|---------|---------|
|**Unified Interface-pictogram**|Moet een schaalbare vectorafbeelding (pictogram) zijn |
|**Pictogram in webtoepassing**|Een SVG-, GIF-, PNG- of JPG-afbeelding van 16x16 pixels.|
|**Pictogram voor entiteitsformulieren**|Een SVG-, GIF-, PNG- of JPG-afbeelding van 32x32 pixels.|

> [!NOTE]
> Alle afbeeldingsbestanden mogen niet groter dan 10 kilobytes zijn.
>
> Als u een schaalbare vectorafbeelding (SVG-afbeelding) instelt als **Pictogram in webtoepassing** of **Pictogram voor entiteitsformulieren**, moet de standaardgrootte zijn ingesteld. Omdat SVG een XML-document is, kunt u het element [svg](https://developer.mozilla.org/docs/Web/SVG/Element/svg) en de waarde voor [breedte](https://developer.mozilla.org/docs/Web/SVG/Attribute/width) en [hoogte](https://developer.mozilla.org/docs/Web/SVG/Attribute/height) met een teksteditor bewerken om de standaardgrootte voor de afbeelding te definiëren.

Elk type pictogram wordt opgeslagen als webresource. U kunt eerst de webresources maken en vervolgens de pictogrammen instellen om ze te gebruiken, maar u kunt de nieuwe webresource ook in het dialoogvenster **Opzoekrecord** maken door **Nieuw** te selecteren terwijl u de waarde instelt. Meer informatie: [Webresources voor modelgestuurde apps maken of bewerken om een app uit te breiden](create-edit-web-resources.md)

## <a name="set-the-icons-for-a-custom-entity"></a>Stel de pictogrammen voor een aangepaste entiteit in.

U moet de oplossingenverkenner gebruiken om entiteitspictogrammen in te stellen.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="set-entity-icons"></a>Entiteitspictogrammen instellen

1. Selecteer **Pictogrammen bijwerken** op de opdrachtbalk.  
  
2. In het dialoogvenster **Nieuwe pictogrammen selecteren** selecteert u op het tabblad **Webclient** onder **Pictogram in webtoepassing** of **Pictogram voor entiteitsformulieren** rechts van **Nieuw pictogram** de knop **Bladeren** ![Knop Opzoeken](media/lookup-button-4.gif).
3. Selecteer of maak de webresource en selecteer **OK**. 
4. Doe op het tabblad **Unified Interface** hetzelfde voor het veld **Nieuw pictogram**.
5. Selecteer **OK** om het dialoogvenster **Nieuwe pictogrammen selecteren** te sluiten.
6. Selecteer op de opdrachtbalk **Opslaan** in het menu **Bestand**.  
7. Als de wijzigingen zijn voltooid, publiceert u deze. Selecteer **Publiceren** op de opdrachtbalk wanneer de entiteit is geselecteerd in de oplossingenverkenner.
  
## <a name="community-tools"></a>Community-hulpprogramma's

**[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)** is een hulpprogramma dat de XrmToolbox-community heeft ontwikkeld voor Dynamics 365 Customer Engagement. Raadpleeg het onderwerp [Ontwikkelaarshulpprogramma´s voor Common Data Service voor Apps](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) voor meer hulpprogramma´s die door de community zijn ontwikkeld.

> [!NOTE]
> De community-hulpprogramma's zijn geen product van Microsoft en Microsoft biedt geen ondersteuning voor de community-hulpprogramma's. Als u vragen hebt over het hulpprogramma, raadpleegt u de uitgever hiervan. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Volgende stappen  
[Een entiteit maken](../common-data-service/create-edit-entities.md)<br />
[Een entiteit bewerken](../common-data-service/edit-entities.md)
