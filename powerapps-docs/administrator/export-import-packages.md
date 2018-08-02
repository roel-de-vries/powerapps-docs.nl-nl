---
title: Resources exporteren en importeren | Microsoft Docs
description: Leer hoe u resources exporteert en importeert in PowerApps
author: nimakms
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 07/28/2017
ms.author: nimak
ms.openlocfilehash: db5861b9f598045436ad0bf796f04ed1df4b8903
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2018
ms.locfileid: "39349749"
---
# <a name="export-and-import-resources"></a>Resources exporteren en importeren
Als u meerdere omgevingen hebt gemaakt om de ontwikkeling van uw database en apps te ondersteunen, moet u wijzigingen uitwisselen tussen omgevingen. U kunt **Resources exporteren** en **Resources importeren** gebruiken om resources te verplaatsen tussen omgevingen.

## <a name="why-use-multiple-environments"></a>Waarom meerdere omgevingen gebruiken?
Elke omgeving bevat resources, zoals entiteiten, stromen en apps, die u maakt of wijzigt tijdens het ontwikkelingsproces. 

Meestal vindt de ontwikkeling plaats in de omgeving die ook wordt gebruikt door de eindgebruikers van de organisatie. Deze omgeving wordt ook wel de standaardomgeving omgeving genoemd. Het is relatief gemakkelijk om wijzigingen van resources in dezelfde omgeving te beheren. U valideert de wijzigingen om er zeker van te zijn dat alle essentiële bedrijfsprocessen en toepassingen werken en vervolgens publiceert u de app.

Soms worden er verschillende omgevingen gebruikt voor ontwikkelen en testen. Wijzigingen worden dan overgebracht naar de standaardomgeving wanneer ze klaar zijn voor gebruik door eindgebruikers. Er zijn verschillende redenen waarom u afzonderlijke omgevingen kunt gebruiken. Het is bijvoorbeeld mogelijk dat u een afzonderlijke omgeving hebt gebruikt bij de eerste evaluatie van het systeem. Een andere mogelijkheid is dat u het risico wilt beperken van het doorvoeren van wijzigingen in de standaardomgeving. Afzonderlijke omgevingen bieden isolatie, omdat u de wijzigingen aanbrengt in een omgeving die niet de standaardomgeving is. Afhankelijk van de omvang van de risico's, kunt u nog een extra faseringsomgeving inrichten. In dit geval hebt u een ontwikkelingsomgeving, een faseringsomgeving en een standaardomgeving.

## <a name="moving-resource-changes"></a>Wijzigingen van resources uitwisselen
U verplaatst resources via afzonderlijke processen voor exporteren en importeren met behulp van een pakketbestand (.zip). Het pakketbestand wordt geëxporteerd, lokaal opgeslagen, verzonden naar de beheerder van de doelomgeving en vervolgens geïmporteerd in de doelomgeving. Het importproces wordt vaak gevolgd door een validatieproces om er zeker van te zijn dat alle essentiële bedrijfsprocessen nog werken.

De functionaliteit voor zowel het importeren als exporteren van resources is beschikbaar in sectie **Omgevingen** van het beheercentrum. U importeert en exporteert resources voor de geselecteerde omgeving.

### <a name="export-resources"></a>Resources exporteren
Het exportpakket bevat alle wijzigingen van **entiteiten en selectielijsten**. We zijn bezig om ook ondersteuning te bieden voor het exporteren van andere resourcetypen, zoals apps, stromen, rollen en connectors. Met deze optie kunt u inhoud van de ene naar de andere omgeving verplaatsen.

1. Klik in het linkernavigatiedeelvenster van het [beheercentrum](https://admin.powerapps.com) op **Omgevingen**.
2. Selecteer de bronomgeving.
3. Klik in de rechterbovenhoek op **Resources exporteren**.
4. Kies de resources waarmee u wilt beginnen:
   1. Selecteer het tabblad dat overeenkomt met een resourcetype dat u wilt selecteren, zoals **Entiteiten**.
   2. Selecteer alle resources onder het type door op het selectievakje in de koptekst te klikken of selecteer afzonderlijke resources.
   3. Klik op **Volgende**.
5. Neem zo nodig gerelateerde resources op:
   1. Als we gerelateerde resources ontdekken, zullen we u een vooraf geselecteerde lijst presenteren.
   2. Sluit alle gerelateerde resources uit door op het selectievakje in de koptekst te klikken of vink afzonderlijke resources uit.
   3. Klik op **Volgende**.
6. Voeg een **Naam** toe voor het geëxporteerde pakket.
7. U kunt eventueel configuratieacties aanpassen die tijdens het importeren van resources moeten worden uitgevoerd:
   1. Klik voor elke resource op **Importinstellingen** om een dialoogvenster weer te geven.
   2. Selecteer de configuratieactie die u standaard wilt laten uitvoeren als dit pakket wordt geïmporteerd
   3. Klik op **Opslaan**.
8. Klik op **Exporteren**.
9. Sla het pakketbestand in lokale opslag op als het exporteren is voltooid.

U kunt ook op **Alle resources selecteren** op de pagina voor het selecteren van resources klikken om alle resources van alle ondersteunde typen in het definitieve pakket op te nemen en direct naar de pagina voor het exporteren van het eindresultaat te gaan.

### <a name="import-resources"></a>Resources importeren
De eerste stap bestaat uit het selecteren van een pakketbestand dat is geëxporteerd uit de bronomgeving. Tijdens het importproces wordt het pakket gevalideerd, geanalyseerd en geïmporteerd.

1. Klik in het navigatiedeelvenster van het [beheercentrum](https://admin.powerapps.com) op **Omgevingen**.
2. Selecteer de doelomgeving.
3. Klik in de rechterbovenhoek op **Resources importeren**.
4. Klik op **Uploaden** en blader naar een pakketbestand in de lokale opslag.
5. Klik op **Volgende** naar de laatste pagina voor het importeren te gaan.
6. Fouten en waarschuwingen voor het valideren van het importproces oplossen:
   1. Kijk of er waarschuwingen of fouten zijn. Deze worden aangeduid door het pictogram links naast de **Naam** van een resource.
   2. Klik op het veld **Importinstellingen** of op het pictogram onder **Actie** voor meer informatie.
   3. Selecteer een geschikte actie voor de importinstellingen.
   4. Het geïmporteerde pakket wordt automatisch opnieuw gevalideerd.
7. Ga naar **Importeren** als er geen fouten zijn.

Als het pakket slechts gedeeltelijk wordt toegepast, ziet u een foutbericht waarin wordt beschreven wat er wel en wat er niet is geïmporteerd.

## <a name="resource-types"></a>Resourcetypen
Tijdens het ontwikkelingsproces kunnen er allerlei typen resources worden gewijzigd. Als u bijvoorbeeld een app bijwerkt, worden er misschien verschillende entiteiten of verbindingen toegevoegd, verwijderd of bijgewerkt. Wijzigingen van sommige resourcetypen (niet allemaal) kunnen worden uitgewisseld tussen omgevingen. In de volgende secties wordt beschreven welke typen resources u kunt verplaatsen.

### <a name="entities-picklists"></a>Entiteiten, selectielijsten
U kunt entiteiten en selectielijsten als volgt exporteren en importeren:

* **Standaardentiteiten** - Alleen aanpassingen worden verplaatst tussen omgevingen. (U kunt de standaardvelden van standaardentiteiten niet wijzigen.)
* **Aangepaste entiteiten**: aangepaste entiteiten worden verplaatst tussen omgevingen.
* **Aangepaste selectielijsten**: aangepaste selectielijsten worden verplaatst tussen omgevingen.

## <a name="data"></a>Gegevens
Het is niet mogelijk om databasegegevens tijdens het exporteren en importeren van resources te verplaatsen. Als gegevens wilt verplaatsen, kunt u Microsoft Excel gebruiken. 

