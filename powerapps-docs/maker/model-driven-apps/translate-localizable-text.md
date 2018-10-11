---
title: Lokaliseerbare tekst voor modelgestuurde apps vertalen | MicrosoftDocs
description: Informatie over het laten vertalen van lokaliseerbare tekst ter ondersteuning van meerdere talen
ms.custom: ''
ms.date: 06/03/2018
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
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
ms.openlocfilehash: e2e305313f3b86be2ea410f6668676b56aa79d95
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674615"
---
# <a name="translate-localizable-text-for-model-driven-apps"></a>Lokaliseerbare tekst voor modelgestuurde apps vertalen

Als u entiteits- of veldtekst hebt aangepast, zoals veldlabels of keuzelijsten, kunt u de gebruikers in uw omgeving die niet met de basistaalversie van uw omgeving werken, voorzien van deze aangepaste tekst in de door u gewenste talen. 

Het proces heeft de volgende stappen:
1. Andere talen inschakelen voor uw omgeving
2. De lokaliseerbare tekst exporteren
3. De lokaliseerbare tekst vertalen
4. De lokaliseerbare tekst importeren

## <a name="enable-other-languages-for-your-environment"></a>Andere talen inschakelen voor uw omgeving

Als u de talen voor uw omgeving nog niet hebt ingeschakeld, gebruikt u de stappen die worden beschreven in [De taal activeren](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) om ze in te schakelen.

> [!IMPORTANT]
> Het kan enkele minuten duren om een taal in te schakelen. Gedurende deze periode kunnen andere gebruikers van de omgeving uw app mogelijk niet gebruiken. Schakel talen in op het moment dat gebruikers er het minste last van hebben.

> [!TIP]
> Terwijl u de talen inschakelt, noteert u de LCID-waarden die voor elke taal worden gebruikt. Deze waarde vertegenwoordigt de taal in de geëxporteerde gegevens voor de lokaliseerbare tekst. Taalcodes zijn viercijferige of vijfcijferige landinstelling-id's. Geldige waarden voor landinstelling-id’s zijn te vinden in [Grafiek Landinstelling-id’s](http://go.microsoft.com/fwlink/?LinkId=122128).

## <a name="export-the-localizable-text"></a>De lokaliseerbare tekst exporteren

Het bereik van de lokaliseerbare tekst die wordt geëxporteerd, is de onbeheerde oplossing die de lokaliseerbare tekst bevat. Dit kan alleen worden gedaan met Solution Explorer

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Open de onbeheerde oplossing die de lokaliseerbare tekst bevat en selecteer **Vertalingen** > **Vertalingen exporteren** in de menubalk. 

![Vertalingen exporteren](media/export-localizable-text.png)

De volgende waarschuwing wordt weergegeven:
> Het exporteren van aangepaste labels voor vertaling kan enkele minuten duren. Klik niet opnieuw op de koppeling voor exporteren totdat de eerste export is voltooid. Weet u zeker dat u nu wilt exporteren? 

Klik op **OK** als u wilt doorgaan.

Wanneer het exporteren is voltooid, staat er een bestand met de naam `CrmTranslations_{0}_{1}.zip` in uw downloadmap, waarbij `{0}` de unieke naam van de oplossing is en `{1}` het versienummer van de oplossing.

## <a name="get-the-localizable-text-translated"></a>De lokaliseerbare tekst vertalen

U kunt dit bestand naar een taalkundige, vertaalbureau of lokalisatiebedrijf sturen.

Als u zelf voldoende kennis hebt om de tekst te vertalen, of als u alleen de indeling wilt bekijken, kunt u het geëxporteerde zipbestand uitpakken en ziet u dat het twee XML-bestanden bevat. 
 - `[Content_Types].xml`
 - `CrmTranslations.xml`

U kunt het bestand CrmTranslations.xml openen met Microsoft Office Excel.

> [!TIP]
> Tenzij u normaal gesproken XML-bestanden opent met Excel, kan het eenvoudiger zijn om Excel te openen en vervolgens het bestand te openen door het pad naar het uitgepakte bestand CrmTranslations.xml te plakken.

> [!IMPORTANT]
> Zorg ervoor dat u de bestandsindeling niet wijzigt. Als u het bestand in een andere indeling opslaat kunt u het niet importeren.

Bekijk het tabblad **Gelokaliseerd labels** bij het weergeven van de gegevens in Excel.

![Geëxporteerde tekst voor lokalisatie](media/localized-labels-tab-exported-languages.png)

Alle aangepaste entiteiten of velden hebben lege cellen voor de lokaliseerbare tekst. Voeg de gelokaliseerde waarden voor die items toe.

> [!NOTE]
> Als u de weergavenaam of beschrijving van een standaardentiteit of entiteitsveld hebt gewijzigd, geven de gelokaliseerde tekenreeksen nog steeds de vertalingen voor de oorspronkelijke waarde weer. Die moeten worden gelokaliseerd om de nieuwe waarde weer te geven.

Het tabblad **Weergavereeksen** bevat tekst die wordt weergegeven voor andere interface-elementen, zoals lintopdrachten, foutberichten en formulierlabels.

### <a name="updating-localizable-text-in-the-base-language"></a>Lokaliseerbare tekst in de standaardtaal bijwerken

Als u de weergavenaam wijzigt van een standaardentiteit of entiteitsveld dat deel uitmaakt van een speciaal bericht, kunt u informatie bijwerken op het tabblad **Weergavereeksen** om de aangepaste naam te gebruiken.

> [!TIP]
> De gebruikersinterface die wordt gebruikt bij het bewerken van berichten van systeementiteiten bevat veel maar niet alle entiteitsnamen. Met deze methode vindt u er mogelijk meer. Meer informatie: [Berichten van systeementiteiten bewerken](../common-data-service/edit-system-entity-messages.md)

Als u bijvoorbeeld de weergavenaam voor de entiteit Account wijzigt in *Bedrijf*, zoekt u in de basistaalkolom in **Weergavereeksen** naar de volgende overeenkomsten: `account`, `accounts`, `Account` en `Accounts` en brengt u vervolgens de juiste wijzigingen aan in respectievelijk `company`, `companies`, `Company` en `Companies`.

> [!IMPORTANT]
> Gebruik hiervoor geen algemene zoek- en vervangactie in het bestand. Zorg ervoor dat de overeenkomende tekst daadwerkelijk verwijst naar de namen die u hebt gewijzigd.


## <a name="import-the-localized-text"></a>De lokaliseerbare tekst importeren
Voor het importeren van de tekst moeten de bestanden worden gecomprimeerd en geïmporteerd in het systeem.

### <a name="compress-the-files"></a>Bestanden comprimeren

Nadat het bestand `CrmTranslations.xml` is gewijzigd, moet u het bestand samen met het bestand `[Content_Types].xml` in de zip-indeling comprimeren. Selecteer *beide bestanden* en klik vervolgens met de rechtermuisknop om het contextmenu te openen. Kies in het contextmenu **Verzenden naar** > **Gecomprimeerde (gezipte) map**.

### <a name="import-the-files"></a>De bestanden importeren

In dezelfde niet-beheerde oplossing waaruit u de vertalingen hebt geëxporteerd, kiest u in het menu **Vertalingen** > **Vertalingen importeren**. 

![Vertalingen importeren](media/import-translations.png)

Selecteer het bestand met de gecomprimeerde vertaalde tekst en selecteer **Importeren**.

![Geselecteerd bestand importeren](media/import-translated-text-dialog.png)

Nadat de vertaalde tekst is geïmporteerd, moet u alle aanpassingen publiceren om de wijzigingen in uw app(s) te zien.

## <a name="community-tools"></a>Communityhulpprogramma’s

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) is een hulpprogramma ontwikkeld door de XrmToolBox-community. Gebruik Easy Translator om vertalingen te exporteren en importeren met contextuele informatie. 

> [!NOTE]
> Hulpprogramma's die door de community zijn gemaakt, worden niet ondersteund door Microsoft.
> Als u vragen over het hulpprogramma hebt, neemt u contact op met de uitgever. Meer informatie: [XrmToolBox](https://www.xrmtoolbox.com).


## <a name="next-steps"></a>Volgende stappen
[Landinstellingen voor uw organisatie](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages)<br />
[Berichten van systeementiteiten bewerken](../common-data-service/edit-system-entity-messages.md)

