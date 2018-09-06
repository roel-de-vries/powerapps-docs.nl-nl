---
title: Details over de huidige gebruiker in een canvas-app weergeven | Microsoft Docs
description: In PowerApps de naam en het e-mailadres van de aangemelde gebruiker in een canvas-app weergeven
author: lonu
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/16/2016
ms.author: lonu
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ef38ef00ed72eb59b459d3e9b71a6efbb6568d6b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833968"
---
# <a name="show-information-about-a-powerapps-user-in-a-canvas-app"></a>Gegevens over een PowerApps-gebruiker in een canvas-app weergeven

Geef in PowerApps de volledige naam, het e-mailadres en de afbeelding die is gekoppeld aan de aangemelde gebruiker in een canvas-app weer. U kunt deze informatie bijvoorbeeld gebruiken om automatisch een formulier in te vullen.

U kunt deze functie bijvoorbeeld gebruiken voor:

* Het maken van een formulier waarmee gebruikers zich kunnen aanmelden voor trainingen of evenementen, kunnen inchecken bij een reclamezuil en nog veel meer.
* De volledige naam weergeven voor een Human Resources-app.
* Automatisch een e-mailadres invoeren wanneer contact wordt opgenomen met uw helpdesk.

U kunt deze functie eigenlijk overal gebruiken waar gebruikers er baat bij hebben dat formulieren of labels automatisch worden ingevuld.

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="show-user-details"></a>Gebruikersdetails weergeven

1. Klik of tik op het tabblad **Invoegen** op **Media** en klik of tik vervolgens op **Afbeelding**.
   
   ![][2]
2. Stel de eigenschap **[Image](controls/properties-visual.md)** in op deze formule:
   <br>**User().image**
   
    ![][3]
3. Ga naar het tabblad **Invoegen** en klik of tik op **Tekst** en vervolgens op **Label**:  
   
    ![][4]
4. Stel de eigenschap **[Text](controls/properties-core.md)** in op deze formule:
   <br>**Gebruiker().VolledigeNaam**
   
   ![][6]
   
   Als u dit doet, wordt het label automatisch ingevuld met uw volledige naam. Verplaats het label zodat deze zich onder het besturingselement voor afbeeldingen bevindt, zoals in deze afbeelding:
   
   ![][5]
5. Voeg nog een label toe en stel de eigenschap **[Text](controls/properties-core.md)** in op deze formule:
   <br>**User().Email**  
   
    ![][8]
   
    Als u dit doet, wordt het label automatisch ingevuld met uw e-mailadres. Verplaats het label zodat deze zich onder het eerste label bevindt, zoals in deze afbeelding:  
   
    ![][7]

[2]: ./media/show-current-user/add-image.png
[3]: ./media/show-current-user/imageproperty.png
[4]: ./media/show-current-user/insertlabel.png
[5]: ./media/show-current-user/label.png
[6]: ./media/show-current-user/textproperty.png
[7]: ./media/show-current-user/secondlabel.png
[8]: ./media/show-current-user/email.png
[9]: ./media/show-current-user/preview.png
