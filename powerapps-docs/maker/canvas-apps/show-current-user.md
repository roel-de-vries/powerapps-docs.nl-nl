---
title: Details over de huidige gebruiker weergeven | Microsoft Docs
description: Voeg de functie Gebruiker toe om de naam en het e-mailadres van de aangemelde gebruiker weer te geven in PowerApps
author: lonu
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/16/2016
ms.author: lonu
ms.openlocfilehash: 90a7ca39626e8eec8151bc3d5ced25a5701a126e
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39016255"
---
# <a name="show-information-about-a-powerapps-user"></a>Gegevens over een PowerApps-gebruiker weergeven
De functie Gebruiker kan de volledige naam, het e-mailadres en de afbeelding die gekoppeld zijn aan de aangemelde gebruiker weergeven. U kunt deze informatie gebruiken om automatisch formulieren in te vullen.

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
