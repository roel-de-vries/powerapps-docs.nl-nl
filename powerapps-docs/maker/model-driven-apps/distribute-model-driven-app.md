---
title: Een modelgestuurde app distribueren via een oplossing | MicrosoftDocs
description: Leer hoe u een modelgestuurde app distribueert via oplossingen
keywords: ''
ms.date: 08/06/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 9
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="distribute-a-model-driven-app-using-a-solution"></a>Een modelgestuurde app distribueren via een oplossing

Modelgestuurde apps worden gedistribueerd als oplossingsonderdelen. Nadat u een modelgestuurde app hebt gemaakt, kunt u deze beschikbaar stellen voor gebruik door andere omgevingen door de app te verpakken in een oplossing en vervolgens te exporteren naar een zipbestand. Nadat de oplossing (zipbestand) in de doelomgeving is geïmporteerd, is de verpakte app beschikbaar voor gebruik. 
  
## <a name="add-an-app-to-a-solution"></a>Een app toevoegen aan een oplossing
Als u een app wilt distribueren, maakt u een oplossing zodat de app voor export kan worden verpakt.

1. Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

2. Selecteer **Oplossingen** en selecteer vervolgens **Nieuwe oplossing**.
3. Vul de velden op de pagina **Nieuwe oplossing** in en selecteer **Opslaan**. Meer informatie: [Een oplossing maken](../common-data-service/create-solution.md)
4. De pagina **Oplossing** wordt weergegeven. Selecteer achtereenvolgens **Bestaande toevoegen**, **App**, de app die u aan de oplossing wilt toevoegen en **OK**. 

    ![Oplossingsonderdelen selecteren](media/select-solution-components.png)

5. Als een pagina **Ontbrekende vereiste onderdelen** verschijnt, kunt u het beste **Ja, vereiste onderdelen toevoegen** selecteren om vereiste onderdelen, zoals entiteiten, weergaven, formulieren, diagrammen en siteoverzichten die deel uitmaken van de app, toe te voegen. Selecteer **OK**.
6. Selecteer op de pagina **Oplossing** de optie **Opslaan en sluiten**.

## <a name="export-a-solution"></a>Een oplossing exporteren
Als u de app wilt distribueren zodat deze in een andere omgeving kan worden geïmporteerd of beschikbaar kan worden gesteld op [Microsoft AppSource](https://appsource.microsoft.com/), exporteert u de oplossing naar een zipbestand. Vervolgens kan het zipbestand met de app en de onderdelen in andere omgevingen worden geïmporteerd.

1. Open de pagina [Oplossingen](advanced-navigation.md#solutions). 
2. Selecteer de oplossing die u wilt exporteren en selecteer **Exporteren** op de werkbalk. 
3. Selecteer op de pagina **Aanpassingen publiceren** de optie **Volgende**.
4. Als de pagina **Ontbrekende vereiste onderdelen** wordt weergegeven, selecteert u **Volgende**. 
5. Selecteer op de pagina **Systeeminstellingen exporteren** de optionele functies die u wilt opnemen en selecteer vervolgens **Volgende**. 
6. Selecteer op de pagina **Pakkettype** de optie **Onbeheerd** of **Beheerd** en vervolgens **Exporteren**. Zie [Oplossingsoverzicht](../common-data-service/solutions-overview.md) voor meer informatie over typen oplossingspakketten.
7. Afhankelijk van uw browser en instellingen, wordt een zippakket gemaakt en naar de standaardmap voor downloads gekopieerd. De bestandsnaam van het pakket is gebaseerd op de unieke naam van de oplossing, aangevuld met onderstrepingstekens en het versienummer van de oplossing.

    > [!NOTE]
    > Als u een app exporteert door een oplossing te gebruiken, wordt de app-URL niet geëxporteerd.
  
## <a name="import-a-solution"></a>Een oplossing importeren  
Wanneer u het zipbestand van een oplossing ontvangt dat de app bevat die u wilt importeren, opent u de pagina voor oplossingsonderdelen en importeert u de oplossing. Als de oplossing is geïmporteerd, wordt de app beschikbaar in uw omgeving.

1. Op de site [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) selecteert u **Modelgestuurd** (linkerbenedenhoek van het navigatievenster).  

    ![Modelgestuurde ontwerpmodus](media/model-driven-switch.png)

2. Selecteer **Oplossingen** en selecteer **Importeren** op de werkbalk.
3. Blader naar het bestand dat u wilt importeren en kies **Volgende**.
4. Selecteer **Importeren**.

## <a name="see-also"></a>Zie ook
[Het voorvoegsel voor de oplossingsuitgever wijzigen](../common-data-service/change-solution-publisher-prefix.md)
