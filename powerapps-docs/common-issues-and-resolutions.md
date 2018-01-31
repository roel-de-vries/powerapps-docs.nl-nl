---
title: Veelvoorkomende problemen en oplossingen voor PowerApps | Microsoft Docs
description: Informatie over problemen met PowerApps en oplossingen
services: 
suite: powerapps
documentationcenter: na
author: skjerland
manager: anneta
editor: 
tags: 
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/08/2017
ms.author: sharik
ms.openlocfilehash: b359a4f5dcc930b344ded68d5ffcd3ae72c007c6
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/23/2018
---
# <a name="common-issues-and-resolutions-for-powerapps"></a>Veelvoorkomende problemen en oplossingen voor PowerApps
## <a name="recently-addedchanged"></a>Onlangs toegevoegd/gewijzigd
1. **Besturingselement voor gegevenstabel**

    Als u een besturingselement voor een **gegevenstabel** kopieert en plakt waarvoor de eigenschap **Items** is ingesteld op een formule die een **filterfunctie** bevat, krijgt de formule voor de eigenschap **Items** op de nieuwe **gegevenstabel** veldnamen die het achtervoegsel **_1** bevatten. Hierdoor worden de veldnamen ongeldig en worden er geen gegevens weergegeven in de tabel. U kunt dit probleem omzeilen door voordat u het besturingselement kopieert, te controleren of de **filterfunctie** niet verwijst naar een veld in de gegevensbron met dezelfde naam als een kolom in het besturingselement voor de **gegevenstabel**. Als dit het geval is, wijzigt u de naam van de kolom in het besturingselement voor de **gegevenstabel**. U kunt het achtervoegsel **_1** ook uit de ongeldige veldnamen verwijderen, zodat ze overeenkomen met de namen in de entiteit.

1. **Camerabesturingselementen in PowerApps Studio voor Windows**

    PowerApps Studio voor Windows kan crashen als u een camerabesturingselement toevoegt of een app opent die gebruikmaakt van een camerabesturingselement. Om dit probleem te vermijden, kunt u [PowerApps Studio voor internet](create-app-browser.md) gebruiken wanneer u een camerabesturingselement toevoegt of opent.

2. **Versie 2.0.700 op Android-apparaten**

    Als u versie 2.0.700 op een Android-apparaat installeert en apps vervolgens niet meer kunnen worden geopend (of niet meer reageren), verwijdert u PowerApps, start u het apparaat opnieuw op en installeert u PowerApps opnieuw.

3. **'Lege' galerie als er een app wordt geopend**

    Als u automatisch een app genereert op basis van gegevens en deze opslaat en daarna opnieuw opent, kan de galerie voor het bladeren mogelijk geen gegevens weergeven. U kunt dit probleem oplossen door minimaal één teken in het zoekvak te typen en de getypte tekst vervolgens te verwijderen. De galerie zal dan gegevens weergeven zoals dat wordt verwacht.

4. **Upgrade uitvoeren van PowerApps in Windows 8.1**

    Als u PowerApps installeert op een computer met Windows 8 of Windows 8.1, houdt u de Windows Store-app open en actief, gebruikt u de charm Instellingen om op updates te controleren en installeert u ze.

5. **Aangepaste connectors en Common Data Service**

   Als een app die is gemaakt met behulp van PowerApps-build 2.0.540 of eerder, afhankelijk is van een database in Common Data Service en ten minste één aangepaste connector in een andere omgeving, moet u de connector implementeren in dezelfde omgeving als de database en de app bijwerken voor het gebruik van de nieuwe connector. Anders wordt een dialoogvenster weergegeven met een melding dat de API is niet gevonden. Zie het [overzicht van omgevingen](environments-overview.md) voor meer informatie.

6. **Een app uitvoeren in Windows 8.1**

    Als u [deze update voor Windows 8.1](https://technet.microsoft.com/library/security/ms16-118) installeert, kunt u apps die u in PowerApps Studio opent, niet uitvoeren op dat besturingssysteem. U kunt nog wel apps uitvoeren in [powerapps.com](https://web.powerapps.com) of met behulp van PowerApps Mobile.

7. **Kolomnamen met spaties**

    Als u een SharePoint-lijst of een Excel-tabel gebruikt waarin de naam van een kolom een spatie bevat, wordt deze door PowerApps vervangen door **'\_x0020\_'**. **'Kolom twaalf'** in SharePoint of Excel wordt bijvoorbeeld weergegeven als **'Kolom_x0020_twaalf'** in PowerApps wanneer de naam wordt weergegeven in de gegevensindeling of wordt gebruikt in een formule.

## <a name="older"></a>Ouder
1. **Een stroom wijzigen in een gedeelde app**

    Als u een stroom aan een app toevoegt, deze deelt, en vervolgens een service toevoegt of een verbinding in de stroom wijzigt, moet u de stroom uit de gedeelde app verwijderen, de stroom opnieuw aan de app toevoegen, en de app opnieuw delen. Anders treedt er een verificatiefout op voor gebruikers die de stroom activeren.

2. **Een gelokaliseerde versie gebruiken**.

    Als u release 2.0.531 onder Windows 8.1 uitvoert, kunt u geen **Tekstinvoer**-besturingselement invoeren als het apparaat is ingesteld op een taal waarvoor een IME-venster nodig is.

3. **Camerabesturing op een Windows Phone**

    Een app met camerabesturing kan vastlopen als u de app opent op een Windows Phone met build 10.0.10586.107. U kunt dit probleem voorkomen door een upgrade naar de meest recente build uit te voeren (bijvoorbeeld door [Upgrade-assistent](https://www.microsoft.com/store/p/upgrade-advisor/9nblggh0f5g4) uit te voeren).

4. **Een app openen vanuit een sjabloon**.

    Als u werkt met release 2.0.5.00 of ouder, wordt een foutbericht weergegeven wanneer u probeert een app te maken op basis van een sjabloon. U moet upgraden om deze functie te kunnen gebruiken.

    Als u werkt met release 2.0.5.10 of ouder, wordt een foutbericht weergegeven wanneer u probeert een app te maken op basis van een sjabloon. U kunt dit bericht sluiten en verdergaan met het maken van de app.

5. **Een streepjescode scannen**

    Zie [Een streepjescode scannen](scan-barcode.md) voor informatie over de beperkingen en aanbevolen procedures bij gebruik van het besturingselement **Streepjescode**.

6. **Apps maken en wijzigen in een browser**

    U kunt in PowerApps Studio voor internet veel, maar niet alle, dingen doen die u ook in PowerApps Studio voor Windows kunt. Zie [Een app maken in een browser](create-app-browser.md) voor meer informatie.

7. **Een titelveld in een entiteit wijzigen**

    Als u het titelveld wijzigt van een entiteit waarnaar wordt verwezen door andere entiteiten via een of meer opzoekbewerkingen, treedt er een fout op wanneer u de wijziging probeert op te slaan. Om dit probleem tijdelijk op te lossen, verwijdert u de opzoekbewerkingen naar de entiteit waarvan u het titelveld wilt wijzigen, brengt u de wijzigingen aan, en maakt u de opzoekbewerkingen opnieuw. Zie [Een relatie bouwen tussen entiteiten](data-platform-entity-lookup.md) voor meer informatie over opzoekbewerkingen.

8. **Apps die verbinding maken met on-premises SharePoint**

    Als u een app deelt die gebruikmaakt van verbindingen die niet automatisch worden gedeeld (zoals een on-premises SharePoint-site), krijgen gebruikers die de app in een browser openen een leeg dialoogvenster te zien wanneer ze klikken of tikken op **Aanmelden**. Klik of tik op het pictogram Sluiten (X) rechtsboven om het dialoogvenster te sluiten. Het dialoogvenster wordt niet weergegeven wanneer u de app in PowerApps Studio of PowerApps Mobile opent. Zie [App-resources delen](share-app-resources.md) voor meer informatie over gedeelde verbindingen.

9. **Wanneer PowerApps een app genereert op basis van gegevens, wordt het veld voor sorteren en zoeken niet automatisch geconfigureerd**.

   Als u dit veld wilt configureren, bewerkt u de formule **[Items](controls/properties-core.md)** voor de galerie, zoals beschreven in de secties voor filteren en sorteren in [Een galerie toevoegen](add-gallery.md).

10. **Voor apps die zijn gemaakt op basis van gegevens, zijn alleen de eerste 500 records van een gegevensbron toegankelijk**.

     In het algemeen werkt PowerApps met databronnen van elke omvang, omdat bewerkingen worden gedelegeerd naar de gegevensbron. Als het delegeren van bewerkingen niet mogelijk is, geeft PowerApps een waarschuwing weer bij het maken van de app, en worden alleen de eerste 500 records van de gegevensbron gebruikt.  Zie het artikel [Filterfunctie](functions/function-filter-lookup.md) voor meer informatie over delegeren.

11. **Excel-gegevens moeten zijn opgemaakt als tabel**.

     Zie [Verbindingen met cloudopslag](connections/cloud-storage-blob-connections.md#known-limitations) voor de beperkingen bij het gebruik van Excel als gegevensbron.

12. **Aangepaste lijsten van SharePoint worden ondersteund, maar niet bibliotheken, bepaalde typen lijstkolommen en kolommen die meerdere waarden of selecties ondersteunen**.

     Zie [SharePoint Online](connections/connection-sharepoint-online.md#known-issues) voor meer informatie.

13. **Cocreatie wordt niet ondersteund. Eén auteur tegelijk graag**.

     Als er gelijktijdig wijzigingen worden aangebracht in een app door meerdere personen, kunt u de app mogelijk beschadigen of de wijzigingen van de ander overschrijven. Sluit de app voordat iemand anders die gaat bewerken.

14. **Het duurt soms even voordat een net gedeelde app kan worden gebruikt**.

     In sommige gevallen is een app die u net hebt gedeeld, niet direct beschikbaar. De app is na enige ogenblikken klaar voor gebruik.

15. **In het [besturingselement Formulier](controls/control-form-detail.md) kunt u geen gegevens wijzigen met een aangepaste kaart**.

     In de aangepaste kaart ontbreekt de eigenschap **[Update](controls/control-card.md)**, die vereist is voor het terugschrijven van wijzigingen. U kunt dit als volgt tijdelijk oplossen:

    * Selecteer het besturingselement Formulier en voeg een kaart toe via het deelvenster aan de rechterkant, op basis van het veld dat u de kaart wilt laten weergeven.  
    * Ontgrendel de kaart zoals beschreven in [Informatie over gegevenskaarten](working-with-cards.md#unlock-a-card).
    * Verwijder of verplaats besturingselementen in de kaart zoals u wilt, net zoals u dat zou doen met de aangepaste kaart.

16. **Een app die wordt uitgevoerd op Android 5.0, Nexus 6 met Webview-versies v48 of v49, kan vastlopen**.

     Gebruikers kunnen dit probleem oplossen door terug te gaan naar een lagere versie van Webview (3x) of bij te werken naar Android 6.0.

17. **De camera kan tijdelijk niet worden gebruikt als er weinig geheugen is**.

     Als uw mobiele apparaat weinig geheugen heeft, wordt de camera tijdelijk uitgeschakeld om te voorkomen dat het apparaat vastloopt.

18. **De Office 365 Video-connector wordt niet ondersteund**.

19. **De kaartengalerie is afgeschaft**.

     Bestaande apps die deze functie gebruiken, blijven voorlopig nog werken maar u kunt geen kaartengalerie toevoegen. Vervang de kaartengalerieën met de nieuwe besturingselementen **[Formulier bewerken](controls/control-form-detail.md)** en **[Formulier weergeven](controls/control-form-detail.md)**.
