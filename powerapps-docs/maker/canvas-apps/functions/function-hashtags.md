---
title: Functie HashTags | Microsoft Docs
description: Naslaginformatie, inclusief syntaxis en voorbeelden, voor de functie HashTags in PowerApps
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 16226203262d5ecacc8fc49a88c9934dd0f673e6
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/24/2018
ms.locfileid: "42862859"
---
# <a name="hashtags-function-in-powerapps"></a>De functie HashTags in PowerApps
Pakt de hashtags (#strings) van een tekenreeks uit.

## <a name="description"></a>Beschrijving
De functie **HashTags** scant een tekenreeks op hashtags. Hashtags beginnen met een hekje (#), dat wordt gevolgd door een willekeurige combinatie van:

* hoofdletters en kleine letters
* cijfers
* onderstrepingstekens
* valutasymbolen (zoals $)

**HashTags** retourneren een [tabel](../working-with-tables.md) met één kolom die de hashtags in de tekenreeks bevat.  Als de tekenreeks geen hashtags bevat, retourneert de functie een tabel met één kolom die [leeg](function-isblank-isempty.md) is.

## <a name="syntax"></a>Syntaxis
**HashTags**( *tekenreeks* )

* *String* - vereist.  Tekenreeks die moet worden gescand op hashtags.

## <a name="examples"></a>Voorbeelden
### <a name="step-by-step"></a>Stap voor stap
1. Voeg een besturingselement **[Tekstinvoer](../controls/control-text-input.md)** toe, geef dit de naam **Tweet** en typ de volgende zin erin:
   
    **Deze #app is #GEWELDIG en kan #123teLLen of #123abc bevatten, maar niet #1-23 of #$\*(#\@")**
2. Voeg een verticale aangepaste galerie toe en stel de eigenschap **[Items](../controls/properties-core.md)** ervan in op deze functie:
   
    **HashTags(Tweet.Text)**
3. Voeg een besturingselement **[Label](../controls/control-text-box.md)** toe aan de galeriesjabloon.
   
    In de galerie worden deze hashtags weergegeven:
   
   * **\#app**
   * **\#GEWELDIG**
   * **\#123teLLen**
   * **\#123abc**
   * **\#1**

