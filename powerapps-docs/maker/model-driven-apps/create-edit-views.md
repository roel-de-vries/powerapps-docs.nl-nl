---
title: Een weergave van een modelgestuurde app maken of bewerken in PowerApps | MicrosoftDocs
description: Instructies voor het maken of bewerken van een weergave
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
ms.openlocfilehash: 215f927b68decac864a2f1b667f64a7649827682
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39678559"
---
# <a name="understand-model-driven-app-views"></a>Weergaven van modelgestuurde apps begrijpen

<a name="BKMK_CreatingAndEditingViews"></a>   

Met PowerApps-apps gebruikt u weergaven om te definiëren hoe een lijst met records voor een specifieke entiteit moet worden weergegeven in de toepassing. Een weergave definieert:

- Weer te geven kolommen
- Hoe breed elke kolom moet zijn
- Hoe de lijst met records standaard moet worden gesorteerd
- Welke standaardfilters moeten worden toegepast om te beperken welke records in de lijst worden weergegeven

Een vervolgkeuzelijst met weergaven wordt regelmatig weergegeven in de toepassing zodat gebruikers opties hebben voor verschillende weergaven van entiteitsgegevens.

De records die zichtbaar zijn in afzonderlijke weergaven, worden weergegeven in een lijst (ook wel raster genoemd) die regelmatig opties biedt zodat gebruikers de standaardsortering, kolombreedten en filters kunnen wijzigen om de gegevens die voor hun belangrijk zijn gemakkelijker te kunnen zien. Met weergaven definieert u bovendien de gegevensbron voor grafieken die in de toepassing worden gebruikt.  
  
## <a name="types-of-views"></a>Weergavetypen  
  
Er zijn drie weergavetypen: *persoonlijk*, *systeem* en *openbaar*.

Dit onderwerp gaat over de manier waarop systeembeheerders en systeemaanpassers met systeemweergaven en openbare weergaven werken. 
  
### <a name="personal-views"></a>Persoonlijke weergaven  
  
 U en verder iedereen die minimaal op gebruikersniveau toegang heeft tot acties voor de entiteit Opgeslagen weergave kan ook persoonlijke weergaven maken. Als systeembeheerder kunt u het toegangsniveau aanpassen voor elke actie in de beveiligingsrol om te bepalen tot in hoeverre gebruikers persoonlijke weergaven kunnen maken, lezen, schrijven, verwijderen, toewijzen of delen.

Persoonlijke weergaven zijn het eigendom van afzonderlijke gebruikers en vanwege hun gebruikerstoegang op standaardniveau zijn ze alleen zichtbaar voor die gebruiker of anderen waarmee ze hun persoonlijke weergaven willen delen. U kunt persoonlijke weergaven maken door een query op te slaan die u definieert met behulp van Geavanceerd zoeken of met behulp van de opties Filters opslaan als nieuwe weergaven en Filters opslaan naar huidige weergave in de lijst met weergaven. Deze weergaven worden doorgaans ingevoegd onder aan de lijsten van systeemweergaven of openbare weergaven die beschikbaar zijn in de toepassing. U kunt een nieuwe persoonlijke weergave maken op basis van een systeemweergave of openbare weergave, maar u kunt geen systeemweergave of openbare weergave maken op basis van een persoonlijke weergave.
  
### <a name="system-views"></a>Systeemweergaven
Als systeembeheerder of systeemaanpasser kunt u systeemweergaven bewerken. Systeemweergaven zijn speciale weergaven waarvan de toepassing afhankelijk is, die voor systeementiteiten bestaan of die automatisch worden gemaakt wanneer u aangepaste entiteiten maakt. Deze weergaven hebben specifieke doelen en een aantal extra mogelijkheden. 


|Systeemweergaven  |Beschrijving  |
|---------|---------|
|Snel zoeken     | De standaardweergave die wordt gebruikt wanneer zoekopdrachten worden uitgevoerd met behulp van Snel zoeken. Met deze weergave definieert u ook welke velden worden doorzocht wanneer u de zoekmogelijkheden van Snel zoeken en Weergaven zoeken gebruikt.        |
|Geavanceerd zoeken     |  De standaardweergave die wordt gebruikt om resultaten weer te geven wanneer Geavanceerd zoeken wordt gebruikt. Met deze weergave definieert u ook de kolommen die standaard worden gebruikt wanneer nieuwe aangepaste openbare weergaven of persoonlijke weergaven worden gemaakt zonder een weergave te definiëren die als sjabloon moet worden gebruikt.       |
|Bijbehorend     |  De standaardweergave waarin de gerelateerde entiteiten voor een record worden vermeld.       |
|Opzoeken     | De weergave die u ziet wanneer u een recordset voor een zoekveld selecteert.        |

Deze weergaven worden niet in de weergavekiezer weergegeven. U kunt ze bovendien niet gebruiken in sublijsten in een formulier of als lijst in een dashboard. U kunt deze weergaven niet verwijderen of deactiveren. Meer informatie: [Weergaven verwijderen](remove-views.md)

Systeemweergaven zijn het eigendom van de organisatie zodat iedereen ze kan zien. Iedereen heeft bijvoorbeeld toegang op organisatieniveau om records voor de entiteit Weergave (savedquery) te lezen. Deze weergaven worden gekoppeld aan specifieke entiteiten en worden zichtbaar in de Solution Explorer. U kunt deze weergaven insluiten in oplossingen omdat ze worden gekoppeld aan de entiteit.

### <a name="public-views"></a>Openbare weergaven

Openbare weergaven zijn weergaven voor algemeen gebruik die u desgewenst kunt aanpassen. Deze weergaven zijn beschikbaar in de weergavekiezer en u kunt ze in subrasters in een formulier of als lijst in een dashboard gebruiken. Sommige openbare weergaven zijn standaard beschikbaar voor systeementiteiten en voor aangepaste entiteiten. Wanneer u bijvoorbeeld een nieuwe aangepaste entiteit maakt, heeft deze de volgende combinatie van openbare weergaven en systeemweergaven.


|Naam  |Type  |
|---------|---------|
|Actieve *meervoudsvorm van entiteit*     |  Openbaar       |
|Inactieve *meervoudsvorm van entiteit*    |  Openbaar       |
|Snel zoeken naar actieve *meervoudsvorm van entiteit*     | Snel zoeken        |
|Geavanceerde zoekweergave van *entiteitnaam*     | Geavanceerd zoeken        |
|Gekoppelde weergave van *entiteitnaam*     |  Bijbehorend       |
|Zoekweergave voor *entiteitsnamen*     | Opzoeken        |

U kunt aangepaste openbare weergaven maken. U kunt aangepaste openbare weergaven verwijderen die u in een onbeheerde oplossing maakt. U kunt door het systeem gedefinieerde openbare weergaven niet verwijderen. Aangepaste openbare weergaven die zijn toegevoegd door het importeren van een beheerde oplossing bevatten mogelijk een beheerde eigenschappenset waardoor wordt voorkomen dat ze worden verwijderd, behalve door het verwijderen van de beheerde oplossing.

## <a name="places-where-you-can-access-the-view-editor-to-create-or-edit-views"></a>Plaatsen waar u toegang hebt tot de weergaveneditor om weergaven te maken of bewerken

- PowerApps-website: u hebt toegang tot de weergaveontwerper in het gebied **Modelgestuurd** > **Gegevens** > **Entiteiten** > **Weergave**. Open een bestaande weergave of maak een nieuwe weergave. Meer informatie: [Een weergave maken of bewerken](create-and-edit-views.md)
- App Designer: als u in een app werkt, kunt u gebruikmaken van App Designer. Dit programma biedt een eenvoudige en intuïtieve gebruikersinterface met mogelijkheden voor slepen en neerzetten voor gemaakte weergaven. Meer informatie: [Zelfstudie: Openbare weergaven of systeemweergaven maken en bewerken met behulp van App Designer](create-edit-views-app-designer.md)
- Solution Explorer: als u al ervaring hebt met Dynamics 365, kunt u gebruikmaken van de Solution Explorer. Meer informatie: [Navigeren naar geavanceerde gebieden voor het maken van apps en aanpassingen](advanced-navigation.md#solution-explorer)
 
## <a name="customize-views"></a>Weergaven aanpassen

Als systeemaanpasser kunt u de weergaven aanpassen via besturingselementen door rasters (lijsten) bewerkbaar en compatibel te maken voor Unified Interface. De volgende besturingselementen worden gebruikt:

- Bewerkbare rasters: hiermee kunnen gebruikers uitgebreide inline bewerkingen rechtstreeks vanuit rasters en subrasters uitvoeren, of ze nu een web-app, tablet of telefoon gebruiken. Meer informatie: [Rasters bewerkbaar maken met behulp van het aangepaste besturingselement Bewerkbaar raster](make-grids-lists-editable-custom-control.md)
- Alleen-lezenraster: biedt gebruikers door middel van responsieve ontwerpprincipes een optimale weergave- en interactie-ervaring voor elke schermgrootte of -richting, zoals mobiele telefoons en tablets. Meer informatie: [Eigenschappen opgeven voor Unified Interface-apps](specify-properties-for-unified-interface-apps.md)

## <a name="next-steps"></a>Volgende stappen

[Weergaven maken of bewerken](create-and-edit-views.md)
