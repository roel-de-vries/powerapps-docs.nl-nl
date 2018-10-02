---
title: Een weergave voor modelgestuurde apps maken of bewerken in PowerApps | MicrosoftDocs
description: Een weergave maken of bewerken
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: bd1d393d-16ea-40ac-8136-26643c37dd2a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="understand-model-driven-app-views"></a>Modelgestuurde appweergaven begrijpen

<a name="BKMK_CreatingAndEditingViews"></a>   

Met PowerApps-apps gebruikt u weergaven om te definiëren hoe een lijst met records voor een bepaalde entiteit in de toepassing wordt weergegeven. Een weergave bepaalt:

- De kolommen die moeten worden weergegeven
- De breedte van elke kolom
- De manier waarop de lijst met records standaard moet worden gesorteerd
- Welke standaardfilters moeten worden toegepast om te beperken welke records worden weergegeven in de lijst

Een vervolgkeuzelijst met weergaven wordt veelvuldig weergegeven in de toepassing zodat gebruikers opties hebben voor verschillende weergaven van entiteitgegevens.

De records die in afzonderlijke weergaven zichtbaar zijn worden weergegeven in een lijst, ook wel raster genoemd, die vaak opties bevat waarmee gebruikers de standaard sorteervolgorde, kolombreedte en filters kunnen wijzigen om gemakkelijker de gegevens te kunnen bekijken die belangrijk voor hen zijn. Weergaven bepalen ook de gegevensbron voor grafieken die in de toepassing worden gebruikt.  
  
## <a name="types-of-views"></a>Typen weergaven  
  
Er zijn drie typen weergaven: *persoonlijk*, *systeem* en *openbaar*.

Dit onderwerp gaat over systeembeheerders en systeemaanpassers werken met systeem- en openbare weergaven. 
  
### <a name="personal-views"></a>Persoonlijke weergaven  
  
 U en alle andere gebruikers die ten minste toegang op gebruikersniveau hebben tot acties voor de entiteit Opgeslagen weergaven kunnen ook persoonlijke weergaven maken. Als systeembeheerder, kunt u het toegangsniveau voor elke actie in de beveiligingsrollen wijzigen om te bepalen tot op welke diepte gebruikers persoonlijke weergaven kunnen maken, lezen, schrijven, verwijderen, toewijzen of delen.

Persoonlijke weergaven zijn eigendom van personen en, vanwege hun standaardgebruikerstoegang, zijn deze alleen zichtbaar voor die persoon of iemand anders waarmee zij hun persoonlijke weergaven delen. U kunt persoonlijke weergaven maken door een query op te slaan die u definieert door Geavanceerd zoeken te gebruiken of door de opties Filters als nieuwe weergave opslaan en Filters bij huidige weergave opslaan in de lijst met weergaven te gebruiken. Deze weergaven worden gewoonlijk onderaan weergegeven in lijsten met systeem- of openbare weergaven die beschikbaar zijn in de toepassing. Hoewel u een nieuwe persoonlijke weergave kunt maken op basis van een systeem- of openbare weergave, kunt u geen systeem- of openbare weergave maken op basis van een persoonlijke weergave.
  
### <a name="system-views"></a>Systeemweergaven
Als systeembeheerder of systeemaanpasser kunt u systeemweergaven bewerken. Systeemweergaven zijn speciale weergaven waarvan de toepassing afhankelijk is, die voor systeementiteiten bestaan of die automatisch worden gemaakt bij het maken van aangepaste entiteiten. Deze weergaven hebben specifieke doelen en enkele aanvullende mogelijkheden. 


|Systeemweergaven  |Beschrijving  |
|---------|---------|
|Snel zoeken     | De standaardweergave die wordt gebruikt als zoekacties worden uitgevoerd met Snel zoeken. Deze weergave bepaalt ook welke velden worden doorzocht bij gebruik van zoekmogelijkheden van de weergave van Snel zoeken en Opzoeken.        |
|Geavanceerd zoeken     |  De standaardweergave die wordt gebruikt voor het weergeven van resultaten bij gebruik van Geavanceerd zoeken. Deze weergave bepaalt ook welke kolommen standaard worden gebruikt wanneer nieuwe aangepaste openbare weergaven of persoonlijke weergaven worden gemaakt zonder dat een weergave wordt gedefinieerd voor gebruik als sjabloon.       |
|Gekoppeld     |  De standaardweergave die de gerelateerde entiteiten voor een record bevat.       |
|Opzoeken     | De weergave die u ziet wanneer u een record selecteert voor het instellen van een opzoekveld.        |

Deze weergaven worden niet weergegeven in de weergaveselectie en u kunt ze niet in sublijsten in een formulier gebruiken of als lijst in een dashboard. U kunt deze weergaven niet verwijderen of deactiveren. Meer informatie: [Weergaven verwijderen](remove-views.md)

Systeemweergaven zijn het eigendom van de organisatie dus iedereen kan deze zien. Zo heeft bijvoorbeeld iedereen toegang op organisatieniveau voor het lezen van records voor de entiteit Weergave (savedquery). Deze weergaven zijn gekoppeld aan bepaalde entiteiten en zijn zichtbaar in de oplossingenverkenner. U kunt deze weergaven opnemen in oplossingen omdat zij aan de entiteit zijn gekoppeld.

### <a name="public-views"></a>Openbare weergaven

openbare weergaven zijn algemene weergaven die u naar eigen wens kunt aanpassen. Deze weergaven zijn beschikbaar in de weergaveselectie en u kunt ze gebruiken in subrasters in een formulier of als lijst in een dashboard. Sommige openbare weergaven zijn standaard ontworpen voor systeementiteiten en voor een eventuele aangepaste entiteit. Als u bijvoorbeeld een nieuwe aangepaste entiteit maakt, beschikt deze over de volgende combinatie van openbare en systeemweergaven.


|Naam  |Type  |
|---------|---------|
|Actieve *meervoudsnaam voor entiteit*     |  Openbaar       |
|Inactieve *meervoudsnaam voor entiteit*    |  Openbaar       |
|Snel zoeken actieve *meervoudsnaam voor entiteit*     | Snel zoeken        |
|*entiteitsnaam* Weergave voor geavanceerd zoeken     | Geavanceerd zoeken        |
|*entiteitsnaam* Gekoppelde weergave     |  Gekoppeld       |
|*entiteitsnaam* Opzoekweergave     | Opzoekveld        |

U kunt aangepaste openbare weergaven maken. U kunt eventuele aangepaste openbare weergaven verwijderen die u in een onbeheerde oplossing maakt. U kunt geen door het systeem gedefinieerde openbare weergaven verwijderen. Voor aangepaste openbare weergaven die worden toegevoegd door een beheerde oplossing te importeren zijn mogelijk eigenschappen ingesteld om te voorkomen dat zij worden verwijderd, behalve door de beheerde oplossing te verwijderen.

## <a name="places-where-you-can-access-the-view-editor-to-create-or-edit-views"></a>Plaatsen waar u de weergave-editor kunt openen om weergaven te maken of te bewerken

- PowerApps-site: u hebt toegang tot de weergaveontwerper in het gebied **Modelgestuurd** > **Gegevens** > **Entiteiten** > **tabblad Weergave**. Open een bestaande weergave of maak een nieuwe weergave. Meer informatie: [Een weergave maken of bewerken](create-and-edit-views.md)
- Appontwerper: als u in een app werkt, kunt u wellicht de appontwerper gebruiken die een eenvoudige en intuïtieve gebruikersinterface op basis van slepen en neerzetten biedt. Meer informatie: [Zelfstudie: Openbare weergaven of systeemweergaven in modelgestuurde apps maken of bewerken met de appontwerper in PowerApps](create-edit-views-app-designer.md)
- Oplossingenverkenner: als u al ervaring hebt met Dynamics 365, wilt u wellicht liever de oplossingenverkenner gebruiken. Meer informatie: [Navigeren naar gebieden met geavanceerde opties voor het maken en aanpassen van modelgestuurde apps](advanced-navigation.md#solution-explorer)
 
## <a name="customize-views"></a>Weergaven aanpassen

Als systeemaanpasser kunt u de weergaven aanpassen via besturingselementen door rasters (lijsten) bewerkbaar en compatibel voor Unified Interface te maken. De volgende besturingselementen worden gebruikt:

- Bewerkbaar raster: hiermee kunnen gebruikers uitgebreide opmaak rechtstreeks in-line bewerken vanuit rasters en subrasters, ongeacht of zij een webapp, tablet of telefoon gebruiken. Meer informatie: [Rasters bewerkbaar maken met het aangepaste besturingselement Bewerkbare rasters](make-grids-lists-editable-custom-control.md)
- Alleen-lezen raster: biedt gebruikers een optimale weergave- en interactie-ervaring bij elk schermformaat of elke weergavestand, zoals mobiele telefoons of tablet door gebruik te maken van responsieve ontwerpprincipes. Meer informatie: [Eigenschappen voor Unified Interface-apps opgeven](specify-properties-for-unified-interface-apps.md)

## <a name="next-steps"></a>Volgende stappen

[Weergaven maken of bewerken](create-and-edit-views.md)
