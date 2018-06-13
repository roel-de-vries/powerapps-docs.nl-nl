---
title: Gegevensintegratie voor klantgegevens van beheerders
description: Persoonsgegevens in gegevensintegratie identificeren, exporteren en verwijderen voor CDS for Apps-beheerders
author: sabinn-msft
ms.service: powerapps
ms.topic: how-to
ms.component: cds
ms.date: 05/20/2018
ms.author: sabinn
ms.openlocfilehash: 01dafceacff89cb9b3a400caad5dde07a0995f1c
ms.sourcegitcommit: e59c849a88c6fc0ed333ef4ce2d982a5b8623c97
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34754133"
---
# <a name="responding-to-data-subject-rights-dsr-requests-for-data-integration-for-common-data-service-for-apps-customer-data"></a>Reageren op aanvragen van betrokkenen voor gegevensintegratie voor CDS for Apps-klantgegevens (Common Data Service)

## <a name="introduction-to-dsr-requests"></a>Inleiding tot DSR-aanvragen

De AVG (Algemene verordening gegevensbescherming) van de EU (Europese Unie) verleent rechten aan personen (in de verordening betrokkenen genoemd) om de persoonsgegevens te beheren die zijn verzameld door een werkgever of een andere instantie of organisatie (verwerkingsverantwoordelijke of gewoon verantwoordelijke). Volgens de AVG zijn persoonsgegevens een breed begrip. Hieronder vallen alle gegevens die verband houden met een geïdentificeerde of identificeerbare natuurlijke persoon. De AVG biedt betrokkenen het recht om het volgende te doen, wanneer dit betrekking heeft op hun persoonsgegevens:

- Kopieën opvragen
- Correcties aanvragen
- Verwerking beperken
- Gegevens verwijderen
- Gegevens in digitale vorm ontvangen, zodat ze aan een andere verwerker kunnen worden overgedragen

Een formele aanvraag van een betrokkene aan een verwerker om actie te ondernemen met betrekking tot zijn of haar persoonsgegevens wordt een aanvraag van de betrokkene genoemd.

In dit artikel wordt beschreven hoe Microsoft zich voorbereidt op de AVG. Het bevat tevens voorbeelden van stappen die u kunt uitvoeren om AVG-naleving te ondersteunen bij gebruik van Data Integration for Admins via de beheerdersportal in CDS for Apps. U leert hoe u producten, services en beheerprogramma's van Microsoft kunt gebruiken om onze klanten te helpen bij het vinden van persoonsgegevens in de Microsoft-cloud als reactie op aanvragen van betrokkenen.

### <a name="searching-for-and-identifying-personal-data"></a>Persoonsgegevens zoeken en identificeren

Met gegevensintegratie voor beheerders in CDS for Apps kunnen gebruikers van de integratietoepassing hun gegevens weergeven met het tabblad Gegevensintegratie op:

[https://admin.powerapps.com/dataintegration](https://admin.powerapps.com/dataintegration)

De gegevens die voor de gebruiker zijn opgeslagen, worden weergegeven in de portal. Alle projecten zijn zichtbaar op het tabblad Projecten:

![Projecten weergeven op het tabblad Projecten](./media/data-integration-gdpr-dsr/projects-tab.png)

Alle verbindingssets zijn zichtbaar op het tabblad Verbindingssets:

![Verbindingssets weergeven op het tabblad Verbindingssets](./media/data-integration-gdpr-dsr/connections-tab.png)

Alle sjablonen zijn zichtbaar op het tabblad Sjablonen:

![Sjablonen weergeven op het tabblad Sjablonen](./media/data-integration-gdpr-dsr/templates-tab.png)

## <a name="securing-and-controlling-access-to-personal-information"></a>Toegang tot persoonsgegevens beveiligen en controleren

In de gegevensintegratie voor beheerders in CDS for Apps zijn gegevens die door de gegevensintegratietoepassing zijn opgeslagen alleen toegankelijk via de beheerdersportal.

## <a name="deleting-personal-data"></a>Persoonlijke gegevens verwijderen

In gegevensintegratie voor beheerders in CDS for Apps kunnen door de gebruiker geautoriseerde gegevens, projecten en verbindingssets worden verwijderd door de gebruiker waaraan de gegevens zijn gekoppeld. Voor het verwijderen van hun persoonsgegevens kunnen gebruikers zich aanmelden bij de beheerdersportal: [https://admin.powerapps.com](https://admin.powerapps.com)

Gebruikers kunnen projecten verwijderen door naar het tabblad Projecten te navigeren, op het beletselteken naast het project te klikken en vervolgens de optie Verwijderen te selecteren:

![Projecten verwijderen door op het beletselteken te klikken](./media/data-integration-gdpr-dsr/projects-del.png)

Gebruikers kunnen sjablonen verwijderen door naar het tabblad Sjablonen te navigeren, op het beletselteken naast de sjabloon te klikken en vervolgens de optie Verwijderen te selecteren:

![Sjablonen verwijderen door op het beletselteken te klikken](./media/data-integration-gdpr-dsr/templates-del.png)

Gebruikers kunnen verbindingssets verwijderen door naar het tabblad Verbindingssets te navigeren, op het beletselteken naast de verbindingsset te klikken en vervolgens de optie Verwijderen te selecteren:

![Verbindingssets verwijderen door op het beletselteken te klikken](./media/data-integration-gdpr-dsr/connsets-del.png)

## <a name="exporting-personal-data"></a>Persoonlijke gegevens exporteren

In gegevensintegratie voor beheerders in CDS for Apps kunnen door de gebruiker geautoriseerde gegevens worden geëxporteerd door de gebruiker waaraan de gegevens zijn gekoppeld. Voor het exporteren van hun persoonsgegevens kunnen gebruikers zich aanmelden bij de beheerdersportal:

[https://admin.powerapps.com](https://admin.powerapps.com)

Voor het exporteren van projecten of projecten met een uitvoeringsgeschiedenis kunnen gebruikers naar het tabblad Projecten navigeren, op het beletselteken naast het project klikken en vervolgens de gewenste exportoptie selecteren:

![Projecten exporteren door op het beletselteken te klikken](./media/data-integration-gdpr-dsr/projects-exp.png)

Voor het exporteren van sjablonen kunnen gebruikers naar het tabblad Sjablonen navigeren, op het beletselteken naast de sjabloon klikken en vervolgens de optie Verwijderen selecteren:

![Sjablonen exporteren door op het beletselteken te klikken](./media/data-integration-gdpr-dsr/templates-exp.png)

Voor het exporteren van verbindingssets kunnen gebruikers naar het tabblad Verbindingsset navigeren, op het beletselteken naast de verbindingsset klikken en vervolgens de optie Verwijderen selecteren:

![Verbindingssets exporteren door op het beletselteken te klikken](./media/data-integration-gdpr-dsr/connsets-exp.png)
