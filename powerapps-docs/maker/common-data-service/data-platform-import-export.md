---
title: Gegevens importeren in of exporteren uit Common Data Service for Apps
description: De functionaliteit Gegevens ophalen uit Excel en Gegevens exporteren gebruiken om gegevens in bulk van en uit Excel- of CSV-bestanden te importeren en exporteren in entiteiten in CDS for Apps (Common Data Service)
author: sabinn-msft
ms.service: powerapps
ms.topic: conceptual
ms.component: cds
ms.date: 05/14/2018
ms.author: sabinn
ms.openlocfilehash: 7f3e16be5bba1874759e0f9e40dc455f1e29c2bc
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697457"
---
# <a name="import-or-export-data-from-the-common-data-service-for-apps"></a>Gegevens importeren in of exporteren uit Common Data Service for Apps

Als u gegevens in bulk wilt kunnen importeren in en exporteren uit Excel- of CSV-bestanden, kunt u de functies Gegevens ophalen uit Excel-bestand en Gegevens exporteren gebruiken voor bijgewerkte CDS for Apps-omgevingen (Common Data Service).

U kunt op twee manieren inhoud uit Excel- of CSV-bestanden importeren in een entiteit

## <a name="option-1-import-by-creating-and-modifying-a-file-template"></a>Optie 1: importeren door een bestandssjabloon te maken en aan te passen

Elke entiteit bevat vereiste velden die in uw invoerbestand moeten bestaan. Om het naadlozer te laten verlopen, is het raadzaam een sjabloon te maken door eerst gegevens uit de entiteit te exporteren en met hetzelfde bestand (aangepast met uw gegevens) gegevens in de entiteit te importeren. Dit bespaart u tijd en moeite omdat u niet meer voor elke entiteit de vereiste velden hoeft in te vullen.

1. Het bestandssjabloon voorbereiden

    - Exporteer eerst de entiteitsgegevens naar een CSV-bestand aan de hand van de stappen onder Gegevens exporteren naar CSV
    - Definieer een plan om ervoor te zorgen dat de gegevens uniek zijn door ofwel primaire sleutels of alternatieve sleutels te gebruiken.
    - Raadpleeg het onderstaande gedeelte voor informatie over het garanderen van unieke gegevens voordat u gegevens in de entiteit gaat importeren

1. Het bestand aanpassen met uw gegevens

    - Gegevens uit uw Excel- of CSV-bestand kopiëren naar de zojuist gemaakte sjabloon

1. Het bestand importeren
    - Vouw op [powerapps.com](https://web.powerapps.com/) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster
    - Selecteer de entiteit waarnaar u gegevens wilt importeren
    - Klik op het beletselteken of het menu aan de bovenkant en selecteer **Gegevens ophalen** en klik of tik op **Gegevens ophalen uit Excel**

> [!NOTE]
> Als u gegevens in meerdere entiteiten wilt importeren, selecteert u in het menu aan de bovenkant de optie **Gegevens ophalen** en klikt of tikt u op **Gegevens ophalen uit Excel**. U kunt uit meerdere entiteiten kiezen. Druk op **Volgende**

![Voorbeeld van het importeren van gegevens naar een Account-entiteit](./media/data-platform-import-export/import-data-to-account.png)

- Hiermee wordt het scherm **Gegevens importeren** geopend, waar u kunt kiezen om gegevens te importeren via een Excel- of CSV-bestand
- Klik of tik op **Uploaden**
- Kies uw bestand en volg de opdrachten om uw bestand te gaan uploaden

![Voorbeeld van het uploaden van een bestand naar een Account-entiteit](./media/data-platform-import-export/upload-account.png)

- Nadat het bestand is geüpload en Toewijzingsstatus groen is, klikt u op **Importeren** in de rechterbovenhoek. Als er fouten worden gedetecteerd tijdens het toewijzen, raadpleegt u het onderstaande gedeelte om naar de toewijzingsfouten te navigeren en deze op te lossen

![Voorbeeld van geslaagde Toewijzingsstatus en de knop Importeren](./media/data-platform-import-export/success-map-imp.png)

- Zodra **het importeren is voltooid**, worden het totale aantal invoegingen en bijwerkingen weergegeven

![Voorbeeld van geslaagde importeerbewerking met het aantal invoegingen en bijwerkingen](./media/data-platform-import-export/success-imp-insert.png)

> [!NOTE]
> We gebruiken de Upsert-logica (bijwerken of invoegen) om de record bij te werken als deze al bestaat, of een nieuwe record in te voegen.

## <a name="option-2-import-by-bringing-your-own-source-file"></a>Optie 2: importeren door uw eigen bronbestand te gebruiken

Als u een geavanceerde gebruiker bent en bekend bent met de vereiste velden voor een bepaalde entiteit voor de Common Data Service for Apps-entiteit, kunt u uw eigen Excel- of CSV-bronbestand definiëren en de stappen onder **Het bestand importeren** uitvoeren

## <a name="navigating-mapping-errors"></a>Naar toewijzingsfouten navigeren

Als er toewijzingsfouten worden gedetecteerd, klikt u na het uploaden van uw bestand op **Toewijzingsstatus** en voert u de volgende stappen uit om de veldtoewijzingsfouten te inspecteren en op te lossen.

- Gebruik de vervolgkeuzelijst aan de rechterkant, onder **Weergeven** om door de **Niet-toegewezen velden** of **Velden met fout** of **Vereiste velden** te navigeren

> [!TIP]
> Afhankelijk van de vraag of u een waarschuwing of foutmelding krijgt, begint u met het inspecteren van **Niet-toegewezen velden** of **Velden met fout** met de vervolgkeuzelijstervaring in **Veldtoewijzingen**

![Voorbeeld van een gedeeltelijke overeenkomst vanwege waarschuwingen met veldtoewijzingen](./media/data-platform-import-export/partial-match.png)

![Voorbeeld van navigatie door problemen met veldtoewijzingen](./media/data-platform-import-export/navigate-mappings.png)

![ Voorbeeld van het inspecteren en oplossen van waarschuwingen met veldtoewijzingen](./media/data-platform-import-export/inspect-warnings.png)

- Zodra u alle fouten en/of waarschuwingen hebt opgelost, klikt u op **Wijzigingen opslaan** in de rechterbovenhoek. Hiermee keert u terug naar het scherm **Gegevens importeren**
- Zodra in de kolom **Toewijzingsstatus** **Voltooid** in het groen wordt aangegeven, klikt u op **Importeren** in de rechterbovenhoek
- Zodra het bericht **Het importeren is voltooid** wordt weergegeven, wordt het totale aantal invoegingen en bijwerkingen weergegeven

## <a name="ensuring-uniqueness-while-importing-data-into-entity-from-excel-or-csv"></a>Unieke gegevens garanderen tijdens het importeren van gegevens in de entiteit vanuit Excel of CSV

Common Data Service for Apps-entiteiten gebruiken een primaire sleutel voor de unieke identificatie van records in een tabel in een CDS-entiteit. De primaire sleutel voor een CDS-entiteit is een Globally Unique Identifier (GUID) en deze vormt de standaardbasis voor recordidentificatie. Door gegevensbewerkingen zoals het importeren van gegevens in de CDS-entiteit worden de primaire standaardsleutels gebruikt.

Voorbeeld: de primaire sleutel voor een Account-entiteit is accountid

![Voorbeeld van een exportbestand uit een Account-entiteit waarin accountid als primaire sleutel wordt weergegeven](./media/data-platform-import-export/export-pk.png)

In sommige gevallen volstaat een primaire sleutel niet en/of voldoet deze niet aan de behoefte tijdens het integreren van gegevens uit een externe bron. Hiervoor kunt u in CDS alternatieve sleutels definiëren voor de unieke identificatie van records in plaats van de primaire sleutel.

Voorbeeld: voor een Account-entiteit kunt u transactioncurrencyid instellen als een alternatieve sleutel door een id op basis van een natuurlijke sleutel te gebruiken (bijvoorbeeld US Dollar in plaats van een GUID-waarde *88c6c893-5b45-e811-a953-000d3a33bcb9* zoals hierboven is weergegeven). U kunt ook een valutasymbool of valutanaam als sleutel gebruiken.

![Voorbeeld van het maken van een alternatieve sleutel bij de Valuta-entiteit](./media/data-platform-import-export/create-ak.png)

![Voorbeeld van een exportbestand uit een Account-entiteit met de valutanaam als natuurlijke sleutel](./media/data-platform-import-export/export-nk.png)

De gebruiker kan nog steeds primaire sleutels gebruiken als id nadat er alternatieve sleutels zijn opgegeven. In het bovenstaande voorbeeld is het eerste bestand nog steeds geldig en zijn de opgegeven GUID’s geldige gegevens.

## <a name="export-data-to-csv"></a>Gegevens exporteren naar CSV

U kunt eenmalig gegevens exporteren van een standaardentiteit of aangepaste entiteit, en u kunt gegevens exporteren van meerdere entiteiten tegelijk. Als u gegevens exporteert uit meer dan één entiteit, worden de gegevens van elke entiteit geëxporteerd naar een apart CSV-bestand.

1. Vouw op [powerapps.com](https://web.powerapps.com/) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster
1. Selecteer de entiteit waaruit u gegevens wilt exporteren
1. Klik op het beletselteken of het menu aan de bovenkant en selecteer **Exporteren** en klik of tik op **Gegevens**

    ![Voorbeeld van het exporteren van gegevens uit een Account-entiteit](./media/data-platform-import-export/export-account.png)

    > [!NOTE]
    > Voor het exporteren van gegevens uit meerdere entiteiten selecteert u in het menu aan de bovenkant de optie **Exporteren** en klikt of tikt u op **Gegevens**. Als het goed is, kunt u uit meerdere entiteiten kiezen

1. Zodra het exporteren is voltooid, kunt u **geëxporteerde gegevens downloaden** en krijgt u een koppeling naar het downloadbare CSV-bestand

    ![Voorbeeldexport met geslaagde export en koppeling naar downloadbaar bestand](./media/data-platform-import-export/export-success.png)

## <a name="unsupported-data-types"></a>Niet-ondersteunde gegevenstypen

De volgende gegevenstypen worden momenteel niet ondersteund

- Tijdzone
- Meervoudige selectie voor optieset
- Afbeelding
