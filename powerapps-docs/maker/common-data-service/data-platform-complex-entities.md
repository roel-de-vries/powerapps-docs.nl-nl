---
title: Complexe entiteiten waarvoor licenties voor PowerApps-abonnement 2 zijn vereist | Microsoft Docs
description: Een lijst met complexe entiteiten in Common Data Service (CDS) voor apps waarvoor PowerApps 2-licenties zijn vereist.
author: clwesene
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 07/17/2018
ms.author: clwesene
ms.openlocfilehash: 76c101f35e236ac6bf037d2b5b748ca1b943d61d
ms.sourcegitcommit: efea7ed5ad8e80c87ba423fb094fa94b4e864d75
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/26/2018
ms.locfileid: "39266252"
---
# <a name="complex-entities-and-licensing"></a>Complexe entiteiten en licenties
Voor entiteiten die de volgende complexe serverlogica bevatten, hebben gebruikers van een app of stroom die gebruikmaakt van deze entiteiten een licentie nodig voor PowerApps-abonnement 2 of Microsoft Flow-abonnement 2:

* Code-invoegtoepassingen. Meer informatie: [ontwikkeling van invoegtoepassingen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development))
* Werkstromen in realtime. Meer informatie: [werkstroomprocessen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes))

    > [!IMPORTANT]
    >  Alleen de werkstromen die worden geconverteerd naar een realtimewerkstroom worden beschouwd als realtime en synchroon. Werkstromen die op de achtergrond worden uitgevoerd, kunnen nog steeds worden gebruikt met het juiste PowerApps-abonnement, zonder dat er aanvullende licenties nodig zijn.

Als u wilt weten of u complexe bedrijfslogica aan uw entiteiten hebt toegevoegd, bekijkt u de lijst met invoegtoepassingsassembly's en werkstromen die in uw omgeving zijn geconfigureerd.

## <a name="complex-entities-installed-with-dynamics-365"></a>Complexe entiteiten die zijn geïnstalleerd met Dynamics 365
In de volgende tabel staat een lijst entiteiten met complexe logica aan de serverzijde, als onderdeel van de installatie van een Dynamics 365-toepassing. Deze lijst is bedoeld als richtlijn. Afhankelijk van welke Dynamics 365-toepassingen en -versies zijn geïnstalleerd in uw omgeving, kan de lijst met complexe entiteiten variëren.

> [!NOTE]
>  Als u gebruikmaakt van de Common Data Service en u geen Dynamics 365-toepassing of een toepassing van een derde hebt geïnstalleerd, bevat uw omgeving geen entiteiten met complexe logica aan de serverzijde.

* Account
* Overeenkomst
* Boekingsdatum overeenkomst
* Incident boeking overeenkomst
* Product boeking overeenkomst
* Service boeking overeenkomst
* Servicetaak boeking overeenkomst
* Opzet boeking overeenkomst
* Factuurdatum overeenkomst
* Factuurproduct overeenkomst
* Factuuropzet overeenkomst
* Substatus overeenkomst
* Boekbare resource
* Boekbare resourcereservering
* Header boekbare resourcereservering
* Categorie boekbare resource
* Toegewezen categorie boekbare resource
* Kenmerk boekbare resource
* Boekbare resourcegroep
* Boekingswaarschuwing
* Status boekingswaarschuwing
* Boekingsstatus
* Case
* Kenmerk
* Competentievereiste (afgeschaft)
* Concurrent
* Contact
* Asset klant
* Delegering
* Uitgave
* Berekening op locatie
* Item prijslijst services op locatie
* Filter
* Volgen
* Incidenttype
* Product incidenttype
* Service incidenttype
* Servicetaak incidenttype
* Integratietaak
* Gegevens integratietaak
* Aanpassing inventaris
* Product aanpassing inventaris
* Inventarisoverdracht
* Factuur
* Factuurfrequentie
* Factuurregel
* Gegevens factuurregel
* Logboek
* Logboekregel
* Lead
* Opmerking
* OData v4-gegevensbron
* Verkoopkans
* Verkoopkansregel
* Gegevens verkoopkansregel
* Bestelling
* Product bestellingsfactuur
* Opzet bestellingsfactuur
* Bestellingsregel
* Betaling
* Betalingsgegevens
* Postconfiguratie
* Postregelconfiguratie
* Postcode
* Prijslijst
* Item van prijslijst
* Product
* Project
* Projectgoedkeuring
* Gegevens projectcontractregel
* Mijlpaal projectcontractregel
* Resourcecategorie projectcontractregel
* Transactiecategorie projectcontractregel
* Projectparameter
* Projectfasen
* Projecttaakstatus gebruiker
* Registratie projectteamleden
* Inkooporder
* Inkooporderfactuur
* Inkooporderproduct
* Ontvangstbewijs inkooporder
* Ontvangstbewijs product inkooporder
* Substatus inkooporder
* Wachtrij-item
* Offerte
* Incident offerteboeking
* Product offerteboeking
* Service offerteboeking
* Servicetaak offerteboeking
* Opzet offerteboeking
* Product offertefactuur
* Opzet offertefactuur
* Offerteregel
* Gegevens offerteregel
* Mijlpaal offerteregel
* Resourcecategorie offerteregel
* Transactiecategorie offerteregel
* Prijslijst projectofferte
* Beoordelingsmodel
* Beoordelingswaarde
* Kenmerk vereiste
* Resourcecategorie vereiste
* Resourcevoorkeur vereiste
* Status vereiste
* Resourceaanvraag
* Resourcevereiste
* Gegevens resourcevereiste
* RMA
* RMA-product
* RMA-ontvangstbevestiging
* Product RMA-ontvangstbevestiging
* RMA-substatus
* Competentievereiste rol
* Prijs rol
* RTV
* RTV-product
* RTV-substatus
* Btw-code
* Gegevens btw-code
* Tijdsvermelding
* Tijdgroep
* Gegevens tijdgroep
* Verlofaanvraag
* Prijs transactiecategorie
* User
* Weergeven
* Muurweergave
* Magazijn
* Werkorder
* Incident werkorder
* Product werkorder
* Service werkorder
* Servicetaak werkorder
* Substatus werkorder
* Werksjabloon


## <a name="licensing"></a>Licentieverlening
Zie de pagina [Licentieoverzicht](../../administrator/pricing-billing-skus.md) voor meer informatie over PowerApps- en Dynamics 365-licenties.

