---
title: Complexe entiteiten waarvoor PowerApps Plan 2-licenties zijn vereist | Microsoft Docs
description: Een lijst met complexe entiteiten in Common Data Service (CDS) voor Apps waarvoor een PowerApps Plan 2-licentie vereist is.
author: clwesene
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 07/17/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="complex-entities-and-licensing"></a>Complexe entiteiten en licenties
Entiteiten die de volgende complexe serverlogica bevatten, vereisen dat gebruikers van een app of een stroom die deze entiteiten gebruiken, om een PowerApps Plan 2- of Microsoft Flow Plan 2-licentie hebben:

* Codeplug-ins. Meer informatie: [Ontwikkeling van plug-ins](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development)
* Realtime-werkstromen. Meer informatie: [Werkstroomprocessen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes)

    > [!IMPORTANT]
    >  Alleen werkstromen die naar een realtime-werkstroom worden geconverteerd, worden beschouwd als realtime en synchroon. Werkstromen die op de achtergrond worden uitgevoerd, kunnen nog steeds worden gebruikt met het juiste PowerApps-plan en vereisen geen aanvullende licenties.

Als u wilt weten of u complexe bedrijfslogica aan uw entiteiten hebt toegevoegd of niet, controleert u de lijst met plug-inassembly´s en werkstromen die in uw omgeving zijn geconfigureerd.

## <a name="complex-entities-installed-with-dynamics-365"></a>Complexe entiteiten die met Dynamics 365 zijn geïnstalleerd
In de volgende tabel ziet u een lijst met entiteiten die standaard complexe serverlogica bevatten als onderdeel van een Dynamics 365-toepassingsinstallatie. Deze lijst is bedoeld als een richtlijn. Afhankelijk van welke Dynamics 365-toepassingen en -versies in uw omgeving zijn geïnstalleerd, kan de lijst met complexe entiteiten variëren.

> [!NOTE]
>  Als u Common Data Service gebruikt en de Dynamics 365-toepassing of een oplossing van derden hebt geïnstalleerd, heeft uw organisatie geen entiteiten die complexe serverlogica bevatten.

* Account
* Overeenkomst
* Boekingsdatum voor overeenkomsten
* Boekingsincident voor overeenkomsten
* Boekingsproduct voor overeenkomsten
* Boekingsservice voor overeenkomsten
* Boekingsservicetaak voor overeenkomsten
* Boekingsinstellingen voor overeenkomsten
* Factuurdatum voor overeenkomsten
* Factuurproduct voor overeenkomsten
* Factuurinstelling voor overeenkomsten
* Substatus van overeenkomsten
* Boekbare resource
* Boeking van boekbare resources
* Header boeking van boekbare resource
* Categorie van boekbare resources
* Toewijzing van categorie van boekbare resources
* Kenmerk van boekbare resources
* Boekbare resourcegroep
* Boekingswaarschuwing
* Waarschuwingsstatus voor boekingen
* Boekingsstatus
* Kenmerk
* Competentievereiste (afgeschaft)
* Concurrent
* Contactpersoon
* Klantactivum
* Overdracht
* Onkosten
* Veldberekening
* Prijslijstitem voor Field Service
* Filter
* Volgen
* Incidenttype
* Product voor incidenttype
* Service voor incidenttype
* Servicetaak van incidenttypen
* Integratietaak
* Detail van integratietaak
* Voorraadaanpassing
* Product voor voorraadaanpassingen
* Voorraadoverboeking
* Factuur
* Factuurfrequentie
* Factuurregel
* Factuurregeldetail
* Logboek
* Journaalregel
* Potentiële klant
* Notitie
* OData v4-gegevensbron
* Verkoopkans
* Verkoopkansregel
* Detail van verkoopkansregels
* Order
* Product voor orderfacturering
* Instelling van orderfacturering
* Orderregel
* Betaling
* Betalingsdetail
* Berichtconfiguratie
* Berichtregelconfiguratie
* Postcode
* Prijslijst
* Prijslijstitem
* Product
* Project
* Projectgoedkeuring
* Detail van projectcontractregels
* Mijlpaal voor projectcontractregels
* Resourcecategorie voor projectcontractregels
* Transactiecategorie voor projectcontractregels
* Projectparameter
* Projectfasen
* Statusgebruiker van projecttaken
* Aanmelding van projectteamlid
* Inkooporder
* Factuur voor inkooporders
* Product voor inkooporders
* Inkooporderontvangst
* Product van inkooporderontvangst
* Substatus van inkooporders
* Wachtrij-item
* Prijsopgave
* Boekingsincident voor prijsopgaven
* Boekingsproduct voor prijsopgaven
* Boekingsservice voor prijsopgaven
* Boekingsservicetaak voor prijsopgaven
* Boekingsinstelling voor prijsopgaven
* Factureringsproduct voor prijsopgaven
* Factureringsinstelling voor prijsopgaven
* Prijsopgaveregel
* Details prijsopgaveregel
* Mijlpaal van prijsopgaveregels
* Resourcecategorie voor prijsopgaveregels
* Transactiecategorie voor prijsopgaveregels
* Projectprijslijst voor prijsopgaven
* Beoordelingsmodel
* Beoordelingswaarde
* Vereistekenmerk
* Vereisteresourcecategorie
* Voorkeur voor vereisteresources
* Vereistestatus
* Resourceaanvraag
* Resourcevereiste
* Resourcevereistedetail
* RMA
* RMA-product
* RMA-ontvangst
* RMA-ontvangstproduct
* Substatus van RMA
* Rolcompetentievereiste
* Rolprijs
* RTV
* RTV-product
* Substatus van RTV
* Belastingcode
* Belastingcodedetail
* Tijdsvermelding
* Tijdsgroep
* Detail van tijdsgroep
* Verlofaanvraag
* Prijs voor transactiecategorie
* Gebruiker
* weergave
* Prikbordweergave
* Magazijn
* Werkorder
* Werkorderincident
* Werkorderproduct
* Werkorderservice
* Servicetaak voor werkorders
* Substatus van werkorders
* Werksjabloon


## <a name="licensing"></a>Licenties
Zie de pagina [Licentieoverzicht](../../administrator/pricing-billing-skus.md) voor meer informatie over PowerApps- en Dynamics 365-licenties.

