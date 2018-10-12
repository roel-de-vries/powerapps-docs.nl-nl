---
title: Pictogrammen van aangepaste entiteiten voor modelgestuurde apps wijzigen in PowerApps | MicrosoftDocs
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
ms.openlocfilehash: c625ac14905e49879eb6dc93eff706a7dab18433
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680564"
---
# <a name="change-model-driven-app-custom-entity-icons"></a>Pictogrammen van aangepaste entiteiten voor modelgestuurde apps wijzigen 

Wanneer u een aangepaste entiteit maakt, krijgt deze automatisch een standaardpictogram toegewezen. Alle aangepaste entiteiten hebben standaard hetzelfde pictogram. Gebruik aangepaste pictogrammen zodat uw aangepaste entiteiten er verschillend uitzien. De pictogrammen die aan systeementiteiten zijn toegewezen, kunt u niet wijzigen.  
  
 U kunt voor elke aangepaste entiteit drie typen entiteitspictogrammen uploaden. 

|Pictogramtype  |Beschrijving  |
|---------|---------|
|**Unified Interface-pictogram**|Moet een .svg-pictogram (Scalable Vector Graphic) zijn |
|**Pictogram in webtoepassing**|Een .svg-, .gif-, .png- of .jpg-afbeelding met een grootte van 16 x 16 pixels.|
|**Pictogram voor entiteitsformulieren**|Een .svg-, .gif-, .png- of .jpg-afbeelding met een grootte van 32 x 32 pixels.|

> [!NOTE]
> Alle afbeeldingsbestanden mogen niet groter dan 10 kilobyte zijn.
>
> Wanneer u een .svg-afbeelding (Scalable Vector Graphic) als **Pictogram in webtoepassing** of **Pictogram voor entiteitsformulieren** gebruikt, moet de standaardgrootte ervan worden ingesteld. Aangezien SVG een XML-document is, kunt u het [svg](https://developer.mozilla.org/docs/Web/SVG/Element/svg)-element bewerken door de waarden voor [breedte](https://developer.mozilla.org/docs/Web/SVG/Attribute/width) en [hoogte](https://developer.mozilla.org/docs/Web/SVG/Attribute/height) met een teksteditor aan te passen om de standaardgrootte voor de afbeelding te definiëren.

Elk pictogramtype wordt opgeslagen als een webresource. U kunt eerst de webresources maken en vervolgens de pictogrammen instellen om ze te gebruiken, of u kunt de nieuwe webresource maken in het dialoogvenster **Record opzoeken** door **Nieuw** te selecteren terwijl u de waarde instelt. Meer informatie: [Webresources maken of bewerken om een app uit te breiden](create-edit-web-resources.md)

## <a name="set-the-icons-for-a-custom-entity"></a>Stel de pictogrammen in voor een aangepaste entiteit.

U moet de oplossingsverkenner gebruiken om entiteitspictogrammen in te stellen.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="set-entity-icons"></a>Entiteitspictogrammen instellen

1. Selecteer **Pictogrammen bijwerken** op de opdrachtbalk.  
  
2. In het dialoogvenster **Nieuwe pictogrammen selecteren** selecteert u op het tabblad **Webclient** onder **Pictogram in webtoepassing** of **Pictogram voor entiteitsformulieren** rechts van **Nieuw pictogram** de knop **Bladeren** ![knop Opzoeken](media/lookup-button-4.gif).
3. Selecteer of maak de toepasselijke webresource en selecteer vervolgens **OK**. 
4. Doe op het tabblad **Unified Interface** hetzelfde voor het veld **Nieuw pictogram**.
5. Selecteer **OK** om het dialoogvenster **Nieuwe pictogrammen selecteren** te sluiten.
6. Selecteer in het menu **Bestand** op de opdrachtbalk de optie **Opslaan**.  
7. Wanneer uw wijzigingen zijn voltooid, publiceert u ze. Selecteer **Publiceren** in de opdrachtbalk terwijl de entiteit is geselecteerd in de oplossingsverkenner.
  
## <a name="community-tools"></a>Communityhulpprogramma’s

**[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)** is een hulpprogramma dat de XrmToolbox-community heeft ontwikkeld voor Dynamics 365 Customer Engagement. Lees het onderwerp [Ontwikkelhulpprogramma’s voor Common Data Service for Apps](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) voor hulpprogramma’s die door de community zijn ontwikkeld.

> [!NOTE]
> De communityhulpprogramma’s zijn geen product van Microsoft, en Microsoft biedt er dus geen ondersteuning voor. Als u vragen over het hulpprogramma hebt, neemt u contact op met de uitgever. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Volgende stappen  
[Een entiteit maken](../common-data-service/create-edit-entities.md)<br />
[Een entiteit bewerken](../common-data-service/edit-entities.md)
