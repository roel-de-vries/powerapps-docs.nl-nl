---
title: Overzicht van de verbinding met Microsoft Translator | Microsoft Docs
description: Lees hoe u verbinding maakt met Microsoft Translator, doorloop enkele voorbeelden en bekijk alle functies
services: 
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/12/2017
ms.author: archanan
ms.openlocfilehash: 9d5ccfd11399188e739353e2994f779347377de4
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="connect-to-microsoft-translator-from-powerapps"></a>Verbinding maken met Microsoft Translator vanuit PowerApps
![Microsoft Translator](./media/connection-microsoft-translator/translatoricon.png)

Voeg de Microsoft Translator-connector toe om vertaalde tekst in een besturingselement **Label**in uw app weer te geven. U kunt bijvoorbeeld een invoertekstvak maken waarin de gebruiker tekst kan invoeren die moet worden vertaald. In een ander label kunt u de vertaalde tekst weergeven.

In dit onderwerp wordt uitgelegd hoe u de Microsoft Translator-verbinding maakt en hoe u de Microsoft Translator-verbinding gebruikt in een app en worden de beschikbare functies toegelicht.

**Opmerking**: deze connector is beperkt tot 150 aanroepen per gebruiker per dag.

&nbsp;

[!INCLUDE [connection-requirements](../../includes/connection-requirements.md)]

## <a name="connect-to-microsoft-translator"></a>Verbinden met Microsoft Translator
1. Open PowerApps, selecteer **Nieuw** en maak vervolgens een **lege app**. Kies de telefoon- of tabletindeling. De tabletindeling biedt meer werkruimte:  
   
   ![Een lege app openen](./media/connection-microsoft-translator/blank-app.png)
2. Klik of tik in het rechterdeelvenster op het tabblad **Gegevens** en klik of tik vervolgens op **Gegevensbron toevoegen**.
3. Selecteer **Nieuwe verbinding** en selecteer vervolgens **Microsoft Translator**:  
   
    ![Verbinden met Microsoft Translator](./media/connection-microsoft-translator/addconnection.png)
   
    ![Verbinden met Microsoft Translator](./media/connection-microsoft-translator/add-translator.png)
4. Selecteer **Verbinden**. De verbinding wordt weergegeven onder **Gegevensbronnen**:  
   
    ![Verbinden met Microsoft Translator](./media/connection-microsoft-translator/translatordatasource.png)

## <a name="use-the-microsoft-translator-connection-in-your-app"></a>De Microsoft Translator-verbinding gebruiken in uw app
### <a name="translate-text"></a>Tekst vertalen
1. Selecteer **Text** in het menu **Insert** en selecteer vervolgens **Text input**. Wijzig de naam van het besturingselement voor tekstinvoer in **Source**:  
   
    ![Naam wijzigen](./media/connection-microsoft-translator/renametosource.png)
2. Voeg een **vervolgkeuzelijst** toe (menu **Invoegen** > **Besturingselementen**), wijzig de naam in **TargetLang** en plaats deze onder **Source**.
3. Stel de eigenschap **[Items](../controls/properties-core.md)** van **TargetLang** in op de volgende formule:  
   
    `MicrosoftTranslator.Languages()`
4. Voeg een label toe, plaats dit onder **TargetLang** en stel de eigenschap **[Text](../controls/properties-core.md)** in op de volgende formule:  
   
    `MicrosoftTranslator.Translate(Source.Text, TargetLang.Selected.Value)`
5. Typ tekst in het vak **Source** en selecteer een taal in **TargetLang**. In het label wordt de tekst die u hebt ingevoerd, weergegeven in de gekozen taal:  
   
    ![Tekst vertalen van het Engels naar het Spaans](./media/connection-microsoft-translator/translate-text.png)

### <a name="speak-translated-text"></a>Vertaalde tekst uitspreken
Als u dat nog niet hebt gedaan, voert u de stappen in de vorige sectie uit om tekst te vertalen. In de volgende stappen worden dezelfde besturingselementen gebruikt.

1. Stel de eigenschap **[Items](../controls/properties-core.md)** van de vervolgkeuzelijst **TargetLang** in op de volgende formule:  
   
    `MicrosoftTranslator.SpeechLanguages()`
2. Wijzig de naam van het tweede label (niet het vak **Source**) in **Target**.
3. Voeg een **audio**besturingselement toe (menu **Invoegen** > **Media**) en stel de eigenschap **Media** in op de volgende formule:  
   
    `MicrosoftTranslator.TextToSpeech(Target.Text, TargetLang.Selected.Value)`
4. Druk op F5 of selecteer de knop Voorbeeld (![](./media/connection-microsoft-translator/preview.png)). Typ tekst in het vak **Source**, selecteer een taal in **TargetLang** en selecteer vervolgens de afspeelknop in het audiobesturingselement.
   
    De app speelt een audioversie van de ingevoerde tekst af in de gekozen taal.
5. Druk op Esc om terug te gaan naar de standaardwerkruimte.

### <a name="detect-the-source-language"></a>De brontaal detecteren
In de volgende stappen worden dezelfde tekstbesturingselementen **Source** en **Target** gebruikt. U kunt desgewenst nieuwe besturingselementen maken door enkel de namen in de formule bij te werken.

1. Selecteer het tekstbesturingselement **Target** en stel de eigenschap **[Text](../controls/properties-core.md)** in op de volgende formule:  
   
    `MicrosoftTranslator.Detect(Source.Text).Name`
2. Typ tekst in **Source**.
   
    Het label geeft de taal aan van de tekst die u hebt getypt. Het label geeft bijvoorbeeld **Frans** aan als u **bonjour** typt of **Italiaans** als u **ciao** typt.

## <a name="view-the-available-functions"></a>De beschikbare functies weergeven
Deze verbinding bevat de volgende functies:

| Functienaam | Beschrijving |
| --- | --- |
| [Languages](connection-microsoft-translator.md#languages) |Hiermee worden alle talen opgehaald die Microsoft Translator ondersteunt |
| [Translate](connection-microsoft-translator.md#translate) |Vertaalt tekst naar een opgegeven taal met Microsoft Translator |
| [Detect](connection-microsoft-translator.md#detect) |Detecteert de brontaal van de tekst |
| [SpeechLanguages](connection-microsoft-translator.md#speechlanguages) |Hiermee worden de beschikbare talen voor spraaksynthese opgehaald |
| [TextToSpeech](connection-microsoft-translator.md#texttospeech) |Zet een opgegeven tekst om in spraak als een audiostream in de wave-indeling |

### <a name="languages"></a>Talen
Get languages: hiermee worden alle talen opgehaald die Microsoft Translator ondersteunt

#### <a name="input-properties"></a>Invoereigenschappen
Geen.

#### <a name="output-properties"></a>Uitvoereigenschappen
| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| Coderen |Tekenreeks |Nee | |
| Naam |Tekenreeks |Nee | |

### <a name="translate"></a>Translate
Tekst vertalen: vertaalt tekst naar een opgegeven taal met Microsoft Translator

#### <a name="input-properties"></a>Invoereigenschappen
| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| query |Tekenreeks |Ja |Te vertalen tekst |
| languageTo |Tekenreeks |Ja |Code van doeltaal (bijvoorbeeld: 'fr') |
| languageFrom |Tekenreeks |Nee |Brontaal (indien niet opgegeven probeert Microsoft Translator deze automatisch te detecteren) (bijvoorbeeld: en) |
| categorie |Tekenreeks |Nee |Vertaalcategorie (standaard: 'algemeen') |

#### <a name="output-properties"></a>Uitvoereigenschappen
Geen.

### <a name="detect"></a>Detect
Taal detecteren: detecteert de brontaal van de tekst

#### <a name="input-properties"></a>Invoereigenschappen
| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| query |Tekenreeks |Ja |Tekst waarvan de taal wordt geïdentificeerd |

#### <a name="output-properties"></a>Uitvoereigenschappen
| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| Coderen |Tekenreeks |Nee | |
| Naam |Tekenreeks |Nee | |

### <a name="speechlanguages"></a>SpeechLanguages
Talen voor spraak ophalen: hiermee worden de beschikbare talen voor spraaksynthese opgehaald

#### <a name="input-properties"></a>Invoereigenschappen
Geen.

#### <a name="output-properties"></a>Uitvoereigenschappen
| Eigenschapsnaam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| Coderen |Tekenreeks |Nee | |
| Naam |Tekenreeks |Nee | |

### <a name="texttospeech"></a>TextToSpeech
Tekst-naar-spraak: zet een opgegeven tekst om in spraak als een audiostream in de wave-indeling

#### <a name="input-properties"></a>Invoereigenschappen
| Naam | Gegevenstype | Vereist | Beschrijving |
| --- | --- | --- | --- |
| query |Tekenreeks |Ja |Te converteren tekst |
| taal |Tekenreeks |Ja |Taalcode om spraak te genereren (bijvoorbeeld: 'en-us') |

#### <a name="output-properties"></a>Uitvoereigenschappen
Geen.

## <a name="helpful-links"></a>Nuttige koppelingen
Bekijk alle [beschikbare verbindingen](../connections-list.md).  
Meer informatie over het [toevoegen van verbindingen](../add-manage-connections.md) aan uw apps.

