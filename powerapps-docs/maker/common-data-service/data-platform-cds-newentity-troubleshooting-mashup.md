---
title: Problemen oplossen met Power Query | Microsoft Docs
description: Problemen oplossen met Power Query om een aangepaste entiteit te maken in Common Data Service voor Apps.
author: mllopis
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/16/2018
ms.author: millopis
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="troubleshoot-power-query"></a>Problemen met Power Query oplossen
Als u Power Query voor Excel gebruikt om een aangepaste entiteit te maken die gegevens van externe bronnen bevat, kan de volgende fout mogelijk worden weergegeven:

>"Uw Azure Active Directory-beheerder heeft een beleid ingesteld dat u deze functie niet kunt gebruiken. Neem contact op met uw beheerder die machtigingen voor deze functie namens u kan verlenen."

De fout verschijnt als Power Query geen toegang kan krijgen tot de gegevens van de organisatie in PowerApps of Common Data Service voor Apps. Deze situatie doet zich in twee soorten omstandigheden voor:

* Een beheerder van de Azure Active Directory-tenant (Azure AD) heeft de mogelijkheid van gebruikers uitgeschakeld om toestemming te geven aan apps die namens hen toegang kunen krijgen tot bedrijfsgegevens.
* Een onbeheerde Active Directory-tenant gebruiken. Een onbeheerde tenant is een directory zonder een algemene beheerder die is gemaakt om een aanbieding van een selfserviceaanmelding te voltooien. Als u dit scenario wilt herstellen, moeten gebruikers eerst converteren naar een beheerde tenant en vervolgens een van de twee oplossingen voor dit probleem volgen. De oplossingen worden beschreven in het volgende gedeelte.

Als u dit probleem wilt oplossen, moet de Azure Active Directory-beheerder een van de twee procedures volgen die verderop in dit artikel worden weergegeven.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>Gebruikers toestaan om toestemming te verlenen aan apps die toegang hebben tot bedrijfsgegevens
Deze methode is misschien gemakkelijker dan de volgende, maar hiermee zijn ruimere machtigingen mogelijk.

1. Open in [Azure portal](https://portal.azure.com) het deelvenster **Azure Active Directory** en selecteer vervolgens **Gebruikersinstellingen**.
2. Selecteer naast **Gebruikers kunnen toestemming verlenen aan apps om namens hen toegang te krijgen tot bedrijfsgegevens** **Ja** en selecteer vervolgens **Opslaan**.

## <a name="allow-power-query-to-access-company-data"></a>Power Query toestaan om toegang te krijgen tot bedrijfsgegevens
Als alternatief kan de de tenantbeheerder aan Power Query toestemming verlenen zonder tenantbrede machtigingen te wijzigen.

1. Installeer [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps).
2. Voer de volgende PowerShell-opdrachten uit:
   * Login-AzureRmAccount (en meld u aan als de tenantbeheerder)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

Het voordeel van deze methode (versus de tenantbrede oplossing) is dat deze oplossing zeer gericht is. Het verschaft alleen de **Power Query**-serviceprincipal, maar er worden geen andere machtigingswijzigingen in de tenant aangebracht.

## <a name="update-personal-data"></a>Persoonlijke gegevens bijwerken

Gebruikers kunnen mashups en andere informatie (zoals querynamen en mashupmetagegevens) bijwerken met de query-editor en via het dialoogvenster **Opties** dat via de query-editor toegankelijk is.

In PowerApps hebt u toegang tot de query-editor door het volgende te doen:
1. Ga naar het deelvenster **Gegevens**, vouw het uit en selecteer **Entiteiten**. 
2. Selecteer de drie puntjes (...) en selecteer vervolgens **Query´s bewerken**.
3. Selecteer in het lint de knop **Opties** en selecteer vervolgens de knop **Diagnose exporteren**.


## <a name="delete-personal-data"></a>Persoonlijke gegevens verwijderen

De meeste gegevens worden automatisch binnen 30 dagen verwijderd. Voor gegevens en metagegevens over mashups moeten gebruikers al hun mashups via PowerApps verwijderen. Alle gekoppelde gegevens en metagegevens worden binnen 30 dagen verwijderd.

Mashups van PowerApps verwijderen:
1. Verwijder de Data Integrator-projecten die van het tabblad kunnen worden verwijderd.
2. Selecteer de drie puntjes (...) en selecteer vervolgens de optie **Verwijderen**.

Als u een mashup hebt gemaakt via de functie "Nieuwe entiteiten van gegevens (technische proefversie)", kunt u deze verwijderen door het volgende te doen:
1. Selecteer de drie puntjes (...) en selecteer vervolgens **Query´s bewerken**.
2. Selecteer de knop **Opties** in het lint.
3. Selecteer de knop **Alle query's verwijderen**.  
    Nadat u hebt bevestigd dat u uw query´s wilt verwijderen, worden ze verwijderd.

## <a name="export-personal-data"></a>Persoonlijke gegevens exporteren

Als u persoonlijke gegevens wilt exporteren, kunnen gebruikers het volgende doen:
1. Open de query-editor.
2. Selecteer de knop **Opties** in het lint.
3. Selecteer de knop **Diagnose exporteren**.

In PowerApps kunt u toegang verkrijgen tot de query-editor door het volgende te doen:
1. Ga naar het deelvenster **Gegevens**, vouw het uit en selecteer **Entiteiten**.
2. Selecteer de drie puntjes (...) en selecteer vervolgens **Query´s bewerken**. 
3. Selecteer in het lint de knop **Opties** en selecteer vervolgens de knop **Diagnose exporteren**.

Tot de door het systeem gegenereerde logboeken over gebruikersacties in de gebruikersinterface (UI) kan toegang worden verkregen in de Azure-portal.



