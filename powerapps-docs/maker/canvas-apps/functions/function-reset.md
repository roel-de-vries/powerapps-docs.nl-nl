---
title: De functie Reset | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie Reset in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/06/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9c032c237018fbd564dd1143f20951dfb42d9795
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42832874"
---
# <a name="reset-function-in-powerapps"></a>De functie Reset in PowerApps
Hiermee stelt u een besturingselement in op de standaardwaarde en worden gebruikerswijzigingen genegeerd.  

## <a name="description"></a>Beschrijving
De functie **Reset** functie herstelt de **standaard**waarde van een eigenschap van een besturingselement.  Gebruikerswijzigingen worden genegeerd.

U kunt besturingselementen binnen een [**Galerie**](../controls/control-gallery.md) of [**Formulier bewerken**](../controls/control-form-detail.md) niet opnieuw instellen buiten die besturingselementen.  U kunt besturingselementen van formules op besturingselementen binnen dezelfde galerie of formulier opnieuw instellen.  U kunt ook alle besturingselementen in een formulier opnieuw instellen met de functie [**ResetForm**](function-form.md). 

De functie **Reset** vormt een alternatief voor het uitschakelen van de eigenschap **Reset** van de invoerbesturingselementen en geniet over het algemeen de voorkeur.  De eigenschap **Reset**is mogelijk een betere keuze als veel besturingselementen uit meerdere formules samen opnieuw moeten worden ingesteld.  De eigenschap **Reset** kan worden geschakeld via een [**knop**](../controls/control-button.md)besturingselement met de formule **Reset = Button.Pressed** of via een variabele met **Reset = MyVar** en **MyVar** schakelen met de formule **Button.OnSelect = Set( MyVar, true ); Set( MyVar, false )**.    

Invoerbesturingselementen worden ook opnieuw ingesteld wanneer hun eigenschap **Default** wijzigt.

**Reset** heeft geen retourwaarde en u kunt deze functie alleen gebruiken in [gedragsformules](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaxis
**Reset**( *besturingselement* )

* *Besturingselement*: vereist. Het besturingselement dat moet worden ingesteld.

## <a name="example"></a>Voorbeeld
1. Voeg een **Tekstinvoer**besturingselement toe aan een scherm.  Standaard worden de naam **Tekstinvoer1** en de bijbehorende eigenschap **Default** ingesteld op **'Tekstinvoer'**.
2. Typ een nieuwe waarde in het tekstvak.  
3. Voeg een **knop**besturingselement toe aan het scherm.
4. Stel de eigenschap **OnSelect** van de knop in op **Reset( Tekstinvoer1 )**.
5. Selecteer de knop.  Dit kan zelfs bij het ontwerpen worden gedaan door voor het einde van het besturingselement te selecteren.
6. De inhoud van het tekstvak wordt ingesteld op de waarde van de eigenschap **Default**.

