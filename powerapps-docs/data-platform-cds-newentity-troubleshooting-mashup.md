---
title: Probleemoplossing - kan geen mashup maken of ophalen voor deze database | Microsoft Docs
description: Problemen oplossen met het maken van een aangepaste entiteit met behulp van CDS en Power Query, door middel van beheerderswijzigingen in AAD-beperkingen.
services: 
suite: powerapps
documentationcenter: na
author: mllopis
manager: kfend
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/18/2017
ms.author: millopis
ms.openlocfilehash: b534400317e39dffec30f185c180de34098a378f
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="troubleshooting---unable-to-create-or-retrieve-a-mashup-for-this-database"></a>Probleemoplossing - kan geen mashup maken of ophalen voor deze database
Wanneer u de functie **Nieuwe entiteiten op basis van gegevens (Technical Preview)** gebruikt, kan er een fout optreden die er als volgt uitziet:

    *Unable to create or retrieve a mashup for the current database*

Dit kan gebeuren wanneer u de functie gebruikt om *Aangepaste entiteiten* te maken in de **Common Data Service (CDS)** op basis van externe gegevensbronnen met behulp van **Power Query**. De fout treedt op wanneer **Power Query** geen toegang heeft tot de gegevens van de organisatie in **PowerApps of CDS**. Er zijn twee scenario's waarin dit kan gebeuren:

* Een tenantbeheerder van **Azure Active Directory** (AAD) staat niet toe dat gebruikers apps toestemming geven om namens hen bedrijfsgegevens te benaderen.
* Er wordt gebruik gemaakt van een niet-beheerde Active Directory-tenant. Een niet-beheerde tenant is een directory zonder globale beheerder, die is gemaakt om een selfservice-aanbod tot inschrijving te doorlopen. Om dit scenario op te lossen, dienen gebruikers *eerst* omgezet te worden naar een beheerde tenant, om vervolgens een van de twee oplossingen voor dit probleem te volgen die in de volgende sectie worden beschreven.

Er zijn twee manieren om het hierboven beschreven probleem op te lossen:

* Laat de AAD-beheerder de stappen volgen die nodig zijn om gebruikers apps toegang te laten geven tot bedrijfsgegevens
* Laat de AAD-beheerder **Power Query** toegang tot deze gegevens geven

Alle vereiste stappen voor deze oplossingen worden hierna beschreven.

## <a name="allowing-users-to-give-apps-consent-to-access-company-data"></a>Gebruikers toestaan apps toegang tot bedrijfsgegevens te geven

U kunt contact opnemen met de AAD-tenantbeheerder en hem of haar de volgende stappen uit laten voeren, waardoor gebruikers toestemming krijgen om een app toegang te geven tot bedrijfsgegevens:

1. Ga naar [https://portal.azure.com](https://portal.azure.com)
2. Open de blade **Azure Active Directory**.
3. Selecteer **Gebruikersinstellingen**.
4. Selecteer **Ja** bij **Gebruikers kunnen apps namens hen toegang geven tot bedrijfsgegevens** en selecteer vervolgens **Opslaan**.
5. Zodra dit proces is voltooid, is het probleem opgelost.

Dit is mogelijk de eenvoudigste oplossing, maar geeft ruimere machtigingen dan de volgende optie.

## <a name="allowing-power-query-to-access-company-data"></a>Power Query toegang tot bedrijfsgegevens geven
Een andere oplossing is dat de tenantbeheerder **Power Query** toestemming geeft, zonder de machtigingen voor de hele tenant te wijzigen. Laat hiervoor de tenantbeheerder de volgende stappen uitvoeren:

1. Installeer [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps)
2. Voer de volgende PowerShell-opdrachten uit:
   * Login-AzureRmAccount (en meld u aan als de tenantbeheerder)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

Het voordeel van deze benadering (in tegenstelling tot de tenant-brede oplossing) is dat deze oplossing zeer afgebakend is. Het heeft alleen gevolgen voor de service-principal van **Power Query**, maar er worden geen andere machtigingen gewijzigd voor de tenant.

