---
title: Een kaart aanpassen | Microsoft Docs
description: Basisaanpassingen en geavanceerde aanpassingen voor kaarten
services: 
suite: powerapps
documentationcenter: 
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/30/2016
ms.author: sharik
ms.openlocfilehash: 5104b82fde14e3aa6960d752d2c15310dfcf5729
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="customize-a-card-in-microsoft-powerapps"></a>Een kaart aanpassen in Microsoft PowerApps
Basisaanpassingen uitvoeren (zonder een kaart te ontgrendelen) door bijvoorbeeld het besturingselement te wijzigen. Geavanceerde aanpassingen uitvoeren door de kaart te ontgrendelen en bijvoorbeeld een besturingselement toe te voegen dat niet standaard beschikbaar is voor die kaart.

Zie [Informatie over gegevenskaarten](working-with-cards.md) voor een overzicht.

**Vereisten**

* Ontdek hoe u [besturingselementen toevoegt en configureert](add-configure-controls.md).
* U kunt dit onderwerp raadplegen voor alleen algemene concepten. Volg de stappen in deze onderwerpen om het proces exact (stap voor stap) te volgen:
  
  1. [Een app maken vanuit SharePoint](app-from-sharepoint.md).
  2. [De indeling aanpassen](customize-layout-sharepoint.md).
  3. [Het formulier aanpassen](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Een vergrendelde kaart aanpassen
In deze procedure gaat u een besturingselement **[Wisselknop](controls/control-toggle.md)** vervangen door een besturingselement **[Keuzerondje](controls/control-radio.md)** zonder de kaart te ontgrendelen.

1. Klik of tik in **EditScreen1** op de kaart **Betaald** om deze te selecteren.
   
    ![](./media/customize-card/select-paid-card.png)
2. Klik of tik in het rechterdeelvenster op de kaartselector voor de kaart **Betaald** en klik of tik daarna op **Bewerkingsopties**.
   
    ![](./media/customize-card/select-toggle-paid.png)
   
    De wijziging wordt in het scherm weergegeven.
   
    ![](./media/customize-card/display-radio.png)
   
    Zie [Bekende problemen](connections/connection-sharepoint-online.md#known-issues) voor informatie over welke typen kolommen in SharePoint welke typen kaarten ondersteunen.

## <a name="unlock-and-customize-a-card"></a>Een kaart ontgrendelen en aanpassen
In deze procedure gaat u een kaart ontgrendelen en vervangt u vervolgens een besturingselement **[Tekstinvoer](controls/control-text-input.md)** door een besturingselement **[Schuifregelaar](controls/control-slider.md)**.

1. Klik of tik in **EditScreen1** op de kaart **Hoeveelheid**.
2. Klik of tik in het rechterdeelvenster op het pictogram met het beletselteken voor die kaart en klik of tik daarna op **Geavanceerde opties**.
   
    ![Geavanceerde opties openen](./media/customize-card/advanced-options.png)
3. Klik of tik op het hangslotpictogram bovenaan het rechter deelvenster om de kaart te ontgrendelen.
   
    ![Een kaart ontgrendelen](./media/customize-card/unlock-card.png)
4. Verwijder in de kaart het besturingselement **Invoertekst**, voeg een besturingselement **Schuifregelaar** toe en noem het nieuwe besturingselement **QtySlider**.
5. Stel in het rechterdeelvenster de eigenschap **Bijwerken** van de kaart **Hoeveelheid** in op deze formule:<br>
   **QtySlider.Value**
   
   **Opmerking**: klik of tik op **Meer optie** onder aan de sectie **Gegevens** als de eigenschap **Bijwerken** niet wordt weergegeven.
   
   ![De eigenschap Update instellen](./media/customize-card/set-qty-update.png)
6. Klik of tik op de schuifregelaar om deze te selecteren en open vervolgens de lijst met besturingselementen boven aan het rechterdeelvenster.
7. Klik of tik op **ErrorMessage4** en stel de eigenschap **Hoogte** vervolgens in op deze formule:<br>
   **QtySlider.Y + QtySlider.Height**

