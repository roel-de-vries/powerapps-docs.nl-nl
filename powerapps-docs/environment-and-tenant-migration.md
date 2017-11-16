---
title: Apps migreren tussen omgevingen en tenants | Microsoft Docs
description: Apps migreren tussen omgevingen en tenants
services: 
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: jamesol
ms.openlocfilehash: 2d25e6ddbaf15991655ffa94bbf9578946504f0e
ms.sourcegitcommit: 43be6a4e08849d522aabb6f767a81c092419babc
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/07/2017
---
# <a name="environment-and-tenant-app-migration-through-packaging"></a>Apps migreren tussen omgevingen en tenants via pakketten
Lees hoe u resources van de ene omgeving naar de andere migreert met pakketten. Deze omgevingen kunnen zich in dezelfde tenant bevinden of in andere tenants.

## <a name="the-scenario"></a>Het scenario
Een veelvoorkomend scenario waarin u mogelijk resources wilt migreren, is als u test- of ontwikkelingsomgevingen hebt en een productieomgeving. Ontwikkelaars en testers hebben uitgebreide toegang tot de apps in hun omgevingen. Maar wanneer een nieuwe app naar de productieomgeving moet worden gemigreerd, heeft deze omgeving strengere controle over machtigingen voor bijwerken en wijzigen.

Een ander scenario is wanneer elke klant een eigen omgeving en eigen gegevens heeft. Wanneer een nieuwe klant wordt toegevoegd, wordt er een nieuwe omgeving voor hem gemaakt en migreert u apps naar zijn omgeving.

## <a name="which-resources-can-i-migrate-through-packaging"></a>Welke resources kan ik migreren via pakketten?
Als u een app exporteert, worden ook de afhankelijke resources voor uw app in het pakket geëxporteerd.  Zoals in de onderstaande tabel wordt beschreven, wordt in eerste instantie alleen een subset van alle mogelijke resourcetypen ondersteund.

| Resourcetype | Ondersteund | Opties voor importeren |
| --- | --- | --- |
| App |Ja |Er zijn twee opties om een app in een omgeving te importeren: <ol><li><b>Nieuwe maken</b> – De app wordt als nieuwe app gemaakt in de omgeving waarin het pakket wordt geïmporteerd.</li> <li><b>Bijwerken</b> – De app bestaat al in de omgeving en wordt bijgewerkt als dit pakket wordt geïmporteerd.</li></ol> |
| Stroom |Ja |Er zijn twee opties om een stroom in een omgeving te importeren: <ol><li><b>Nieuwe maken</b> – De stroom wordt als een nieuwe stroom gemaakt in de omgeving waarin het pakket wordt geïmporteerd.</li> <li><b>Bijwerken</b> – De stroom bestaat al in de omgeving en wordt bijgewerkt als dit pakket wordt geïmporteerd.</li></ol> <div> <i> OPMERKING: Ook alle resources waarvan de stroom afhankelijk is, worden opgenomen in het app-pakket dat wordt geëxporteerd. Ze moeten worden geconfigureerd wanneer het pakket wordt geïmporteerd. </i> |
| CDS-entiteitsaanpassingen en selectielijsten |Ja |Er zijn twee opties voor het importeren van CDS-entiteiten of -selectielijsten in een omgeving: <ol><li><b>Overschrijven</b> – Als er een resource met dezelfde naam is, zal deze importactie die vervangen. Als er geen overeenkomende resource is, wordt er een nieuwe resource gemaakt. <li><b>Samenvoegen</b> – Als er een entiteit of selectielijst met dezelfde naam is, worden er nieuwe velden of items toegevoegd. Ontbrekende velden of items worden echter niet verwijderd.</li></ol> |
| Aangepaste connectors |Nee |We ondersteunen op dit moment <b>geen</b> aangepaste connector als onderdeel van het pakket als een app daarvan afhankelijk is. <p></p> Als u een app hebt die afhankelijk is van een aangepaste connector, kunt u de connector op dit moment alleen handmatig opnieuw maken of bijwerken in uw doelomgeving en die connector selecteren als u het pakket importeert. |
| Verbindingen |Nee |Als een app afhankelijk is van een verbinding (zoals een SQL-verbinding met referenties), ondersteunen we op dit moment de verbinding of referenties niet als onderdeel van het pakket. <p></p> Als u een app hebt die afhankelijk is van een gedeelde verbinding (zoals SQL), kunt u op dit moment alleen die verbinding handmatig opnieuw maken in uw doelomgeving met de juiste referenties en die connector selecteren als u het pakket importeert. |
| Aangepaste rollen en machtigingensets voor CDS |Nee |Op dit moment wordt het exporteren van aangepaste rollen en/of machtigingensets voor CDS niet ondersteund. U kunt u dus alleen handmatig deze entiteiten opnieuw maken in uw doelomgeving. |
| Gateways |Nee |Gateways worden alleen ondersteund in de standaardomgevingen (en {tenant name} (van preview)). Exporteren/migreren is dus niet mogelijk. |
| CDS-gegevensrijen |Nee |Op dit moment wordt het exporteren van rijen uit CDS-entiteiten niet ondersteund. U kunt nu dus alleen handmatig gegevens [exporteren en importeren](data-platform-export-data.md) nadat de wijzigingen in uw CDS-schema in een nieuwe omgeving zijn toegepast. |

## <a name="how-do-i-get-access-to-packaging-for-my-app"></a>Hoe kan ik toegang krijgen tot pakketten voor mijn app?
De mogelijkheid om een app te exporteren, is beschikbaar voor elke gebruiker met 'Kan bewerken'-machtigingen voor de app.

De mogelijkheid om een app te importeren, is beschikbaar voor elke gebruiker met 'Omgevingsmaker'-machtigingen in de doelomgeving.

Een gebruiker moet een licentie of proeflicentie voor PowerApps-abonnement 2 hebben om een app te kunnen exporteren of importeren.

*Opmerking: Het maken van pakketten is nog in preview, maar elke gebruiker met een geldige PowerApps-licentie kan pakketten voor zijn apps en omgevingen proberen.*

## <a name="exporting-an-app"></a>Een app exporteren
1. Klik of tik op http://web.powerapps.com op **Apps**, selecteer het beletselteken voor de app die u wilt migreren en selecteer vervolgens **Exporteren (preview)**.
   
    ![Selecteer Exporteren](./media/environment-and-tenant-migration/select-export.png)
2. Vul een naam en beschrijving voor het exportpakket in als de bijbehorende pagina wordt geopend.
   
    ![De pakketgegevens controleren](./media/environment-and-tenant-migration/package-details.png)
3. U kunt onder 'Pakketinhoud controleren' eventueel opmerkingen of notities toevoegen of wijzigen hoe elke afzonderlijke resource tijdens het importeren van het pakket in de doelomgeving wordt geïmporteerd.
   
    ![Pakketinhoud configureren](./media/environment-and-tenant-migration/export-package-content.png)
4. Selecteer **Exporteren** als u klaar bent. Er wordt binnen een paar seconden begonnen met het downloaden van het pakketbestand.

## <a name="importing-an-app"></a>Een app importeren
1. Tik of klik op http://web.powerapps.com op **Apps** en selecteer vervolgens **Pakket importeren (preview)**.
   
    ![Selecteer importeren](./media/environment-and-tenant-migration/select-import.png)
2. Selecteer **Uploaden** en kies het app-pakketbestand dat u wilt importeren.
   
    ![Selecteer het pakketbestand](./media/environment-and-tenant-migration/select-file.png)
3. Nadat het pakket is geüpload, moet u de pakketinhoud controleren en extra invoer bieden voor elk item dat is gemarkeerd met een rood pictogram. U kunt dit doen door het pictogram met de moersleutel achter elk item te selecteren en de vereiste gegevens in te voeren.
   
    ![De pakketinhoud controleren](./media/environment-and-tenant-migration/import-package-content.png)
4. Selecteer **Importeren** nadat u alle vereiste gegevens hebt verstrekt.
   
    ![Bijgewerkte verpakte inhoud](./media/environment-and-tenant-migration/import-package-content-dirty.png)
5. Na het uitvoeren van het importproces wordt u automatisch doorverwezen naar een pagina (vergelijk het onderstaande voorbeeld) waarop wordt beschreven of de importbewerking wel of niet is geslaagd.
   
    ![Resultaten van de importbewerking controleren](./media/environment-and-tenant-migration/import-results.png)

> **OPMERKING** Als u een app importeert en ervoor kiest om een bestaande app **bij te werken**, worden de nieuwe wijzigingen opgeslagen als een concept van de applicaties.  U moet deze wijzigingen [publiceren](http://powerapps.microsoft.com/tutorials/save-publish-app/#publish-an-app) voordat ze beschikbaar zijn voor alle andere gebruikers van de applicaties.
> 
> 

## <a name="known-limitations"></a>Bekende beperkingen
| Beperking | Status |
| --- | --- |
| Het importeren van app-pakketten die meer dan ongeveer 3 resources bevatten, duurt enkele minuten. |Dit is een bekend probleem waarvoor binnenkort een oplossing wordt uitgerold. |

