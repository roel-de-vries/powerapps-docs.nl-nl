---
title: Problemen met Power Query oplossen | Microsoft Docs
description: Problemen oplossen met Power Query om een aangepaste entiteit in Common Data Service (CDS) voor Apps te maken.
author: mllopis
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/16/2018
ms.author: millopis
ms.openlocfilehash: b89d7a59406d19759b84c34dbda84b98b10d5e58
ms.sourcegitcommit: f236364ecb06dd86244cd9a607c31e0d716912e2
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/22/2018
---
# <a name="troubleshooting-power-query"></a>Problemen met Power Query oplossen
Als u Power Query gebruikt om een aangepaste entiteit te maken die gegevens uit externe bronnen bevat, kan deze fout worden weergegeven:

`Your Azure Active Directory administrator has set a policy that prevents you from using this feature. Please contact your administrator, who can grant permissions for this feature on your behalf.`

De foutmelding verschijnt wanneer Power Query geen toegang heeft tot de gegevens van de organisatie in PowerApps of Common Data Service (CDS) voor Apps. Deze situatie doet zich voor onder twee sets omstandigheden:

* Een tenantbeheerder van Azure Active Directory (AAD) staat niet toe dat gebruikers apps toestemming geven om namens hen bedrijfsgegevens te benaderen.
* Er wordt gebruik gemaakt van een niet-beheerde Active Directory-tenant. Een niet-beheerde tenant is een directory zonder globale beheerder, die is gemaakt om een selfservice-aanbod tot inschrijving te doorlopen. Om dit scenario op te lossen, dienen gebruikers eerst omgezet te worden naar een beheerde tenant, om vervolgens een van de twee oplossingen voor dit probleem te volgen die in de volgende sectie worden beschreven.

Om dit probleem op te lossen moet de beheerder van Azure Active Directory de stappen volgen in één van de procedures die later in dit onderwerp worden genoemd.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>Toestaan dat gebruikers toestemming geven voor apps geven die toegang hebben tot bedrijfsgegevens
Deze aanpak is mogelijk eenvoudiger dan de volgende, maar geeft ruimere machtigingen.

1. Open in [https://portal.azure.com](https://portal.azure.com) de blade **Azure Active Directory** en selecteer vervolgens **Gebruikersinstellingen**.
2. Selecteer **Ja** bij **Gebruikers kunnen apps namens hen toegang geven tot bedrijfsgegevens** en selecteer vervolgens **Opslaan**.

## <a name="allow-power-query-to-access-company-data"></a>Power Query toestaan bedrijfsgegevens te openen
Als alternatief kan de tenantbeheerder Power Query toestemming geven zonder de machtigingen voor de gehele tenant te wijzigen.

1. Installeer [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps).
2. Voer de volgende PowerShell-opdrachten uit:
   * Login-AzureRmAccount (en meld u aan als de tenantbeheerder)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

Het voordeel van deze benadering (in tegenstelling tot de tenant-brede oplossing) is dat deze oplossing zeer afgebakend is. Het heeft alleen gevolgen voor de service-principal van **Power Query**, maar er worden geen andere machtigingen gewijzigd voor de tenant.

## <a name="updating-personal-data"></a>Persoonlijke gegevens bijwerken

Gebruikers kunnen mashups en andere gegevens (zoals querynamen en mashup-metagegevens) bijwerken via de Query Editor en via het `Options`-dialoogvenster dat toegankelijk is vanuit de Query Editor.

In PowerApps kan de Query Editor nu worden geopend via het gegevensvenster, door dit uit te vouwen en te klikken op het menu-item in het deelvenster Entiteiten. Klik hier op het menu '...' en kies Query's bewerken. Klik vervolgens op de knop `Options` in het lint en klik op de knop `Export Diagnostics`.


## <a name="deleting-personal-data"></a>Persoonlijke gegevens verwijderen

De meeste gegevens worden automatisch binnen 30 dagen verwijderd. Voor gegevens en metagegevens rond mashups moet de gebruiker alle mashups verwijderen via PowerApps. Alle gerelateerde gegevens en metagegevens worden binnen 30 dagen verwijderd.

Mashups kunnen vanuit Power Apps worden verwijderd door de Data Integrator-projecten te verwijderen. U kunt deze verwijderen door op het gelijknamige tabblad te klikken op de knop ... en de optie `Delete` te kiezen.

Als u een mashup hebt gemaakt via de functie Nieuwe entiteiten van gegevens (Technical Preview), kunt u deze verwijderen door te klikken op de knop ..., vervolgens Query's bewerken te kiezen en tenslotte op de knop Alle query's verwijderen te klikken. Zodra u bevestigt dat u uw query's wilt verwijderen, worden deze verwijderd.


## <a name="exporting-personal-data"></a>Persoonlijke gegevens exporteren

Gebruikers kunnen de Query Editor openen, vervolgens klikken op de knop `Options` in het lint en op de knop `Export Diagnostics` te klikken.

In PowerApps kan de Query Editor nu worden geopend via het gegevensvenster, door dit uit te vouwen en te klikken op het menu-item in het deelvenster Entiteiten. Klik hier op het menu '...' en kies Query's bewerken. Klik vervolgens op de knop `Options` in het lint en klik op de knop `Export Diagnostics`.

Door het systeem gegenereerde logboeken met betrekking tot gebruikersacties in de gebruikersinterface (UI) kunnen worden geopend in Azure Portal.


