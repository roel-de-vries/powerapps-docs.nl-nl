---
title: Laat klanten uw apps uitproberen op AppSource | Microsoft Docs
description: Gebruik AppSource om apps te delen met klanten en leads te genereren voor uw bedrijf.
author: linhtranms
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/08/2017
ms.author: litran
ms.openlocfilehash: fb51ab2c671d695350e452dc6fb29efa583adfea
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023684"
---
# <a name="let-customers-test-drive-your-apps-on-appsource"></a>Klanten uw apps laten uitproberen op AppSource
Houdt u van het bouwen van apps in PowerApps? Hebt u een app die u met klanten wilt delen? We ondersteunen nu PowerApps Test Drive-oplossingen op [AppSource.com](https://appsource.microsoft.com), zodat u apps met klanten kunt delen en leads voor uw bedrijf kunt genereren.

## <a name="what-is-a-test-drive-solution"></a>Wat is een Test Drive-oplossing?
Met een Test Drive-oplossing kunt u uw klanten een echte app laten uitproberen zonder dat ze zich hoeven aan te melden voor een PowerApps-abonnement of dat ze toepassingen hoeven te installeren. Klanten melden zich gewoon aan bij AppSource.com met hun Azure Active Directory (AAD)-account en voeren de app uit in een webbrowser. Zonder Test Drive kunnen klanten alleen over de app lezen of een video met een beschrijving ervan bekijken. Met Test Drive krijgen klanten een beter idee van wat de oplossing inhoudt en welke functionaliteit de app bevat. En ze kunnen de app zelf uitproberen. Klanten kunnen er niet achter komen hoe de app feitelijk werkt, dus uw intellectueel eigendom is beschermd. Wij verzamelen en delen informatie over leads voor gebruikers die uw Test Drive-app uitproberen, zodat uw bedrijf kan groeien.

Hier ziet u een voorbeeld van een [app-beschrijving](https://go.microsoft.com/fwlink/?linkid=848867) op AppSource.com:

![Voorbeeld van een beschrijving op AppSource ](./media/dev-appsource-test-drive/sample-app-source-listing.png)

Als de gebruiker de koppeling **Gratis proefversie** in de bovenstaande app-beschrijving selecteert, wordt de eraan gekoppelde PowerApps Test Drive-app rechtstreeks vanuit de browser gestart:

![Voorbeeld van app-webspeler](./media/dev-appsource-test-drive/sample-app-web-player.png)

## <a name="how-do-i-build-a-test-drive-solution"></a>Hoe bouw ik een Test Drive-oplossing?
Het bouwen van een Test Drive-oplossing werkt net zo als die van andere apps in PowerApps, maar u gebruikt ingesloten gegevens in plaats van externe gegevensverbindingen. Het gebruik van ingesloten gegevens verlaagt de drempel voor het implementeren van de app voor uw klant. Niets staat hen dus meer in de weg om de app uit te proberen. De volledige oplossing die u ten slotte onder klanten distribueert, omvat gewoonlijk gegevensverbindingen, maar ingesloten gegevens werken prima voor een Test Drive-oplossing.

PowerApps ondersteunt het bouwen van apps met ingesloten gegevens, dus u hebt alleen maar voorbeeldgegevens voor de app nodig. Deze gegevens moeten als een of meer tabellen in een Excel-bestand worden geplaatst. In PowerApps haalt u vervolgens de gegevens uit de tabel om er in de app mee te werken. U gebruikt dus geen externe verbinding. Het onderstaande driestapsproces laat zien hoe u gegevens uit een Excel-bestand haalt en in de app gebruikt.

### <a name="step-1-import-data-into-the-app"></a>Stap 1: gegevens in de app importeren
Stel dat u een Excel-bestand hebt met twee tabellen: **SiteInspector** en **SitePhotos**.

![Te importeren Excel-tabellen](./media/dev-appsource-test-drive/excel-file.png)

Importeer deze twee tabellen in PowerApps met de optie **Statische gegevens toevoegen aan uw app**.

![Statische gegevens toevoegen aan uw app](./media/dev-appsource-test-drive/static-data.png)

De tabellen zijn nu als gegevensbronnen in de app aanwezig.

![Excel-tabellen als geïmporteerde gegevensbronnen](./media/dev-appsource-test-drive/data-sources.png)

### <a name="step-2-handling-read-only-and-read-write-scenarios"></a>Stap 2: omgaan met alleen-lezen- en lezen/schrijvenscenario's
De gegevens die u importeert zijn *statisch* en dus alleen-lezen. Als uw app alleen-lezen is (dat wil zeggen dat de gegevens alleen voor de gebruiker worden weergegeven), verwijst u rechtstreeks vanuit de app naar de tabellen. Als u bijvoorbeeld toegang wilt hebben tot het veld **Titel** in de tabel **SiteInspector**, gebruikt u **SiteInspector.Title** in uw formule.

Als uw app lezen/schrijven is, importeert u de gegevens uit de tabellen eerst in een *verzameling*, een gegevensstructuur in tabelvorm in PowerApps. Werk vervolgens verder met de verzameling in plaats van de tabel. Ga als volgt te werk als u gegevens wilt halen uit de tabellen **SiteInspector** en **SitePhotos** en in de verzamelingen **SiteInspectorCollect** en **SitePhotosCollect** importeren:

```
ClearCollect(SiteInspectorCollect,SiteInspector); ClearCollect(SitePhotosCollect,SitePhotos)
```

Met de formule worden beide verzamelingen gewist, waarna de gegevens vervolgens vanuit elke tabel in de bijbehorende verzameling worden geplaatst:

* Roep de formule ergens in de app aan om de gegevens te laden.
* Bekijk alle verzamelingen in de app door naar **Bestand** > **Verzamelingen** te navigeren.
* Zie [Een verzameling in uw app maken en bijwerken](../canvas-apps/create-update-collection.md) voor meer informatie.

Als u nu toegang wilt tot het veld **Titel**, gebruikt u **SiteInspectorCollect.Title** in uw formule.

### <a name="step-3-add-update-and-delete-data-in-your-app"></a>Stap 3: gegevens aan de app toevoegen, gegevens bijwerken en verwijderen
U hebt gezien hoe gegevens zowel rechtstreeks als vanuit een verzameling kunnen worden gelezen. Nu zult u zien hoe u gegevens aan een verzameling toevoegt, ze bijwerkt en verwijdert:

**Als u een rij aan een verzameling wilt toevoegen**, gebruikt u [Collect( DataSource, Item, ... )](../canvas-apps/functions/function-clear-collect-clearcollect.md):

```
Collect(SiteInspectorCollect,{ID:Value(Max(SiteInspectorCollect, ID)+1),
    Title:TitleText.Text,SubTitle:SubTitleText.Text,Description:DescriptionText.Text)
```

**Als u een rij in een verzameling wilt bijwerken**, gebruikt u [UpdateIf( DataSource, Condition1, ChangeRecord1 [, Condition2, ChangeRecord2, ...] )](../canvas-apps/functions/function-update-updateif.md):

```
UpdateIf(SiteInspectorCollect,ID=record.ID,
    {Title:TitleEditText.Text,SubTitle:SubTitleEditText.Text,Description:DescriptionEditText.Text)
```

**Als u een rij uit een verzameling wilt verwijderen**, gebruikt u [RemoveIf( DataSource, Condition [, ...] )](../canvas-apps/functions/function-remove-removeif.md):

```
RemoveIf(SiteInspectorCollect,ID=record.ID)
```

> [!NOTE]
> Verzamelingen houden de gegevens alleen vast als de app wordt uitgevoerd; eventuele wijzigingen worden genegeerd als de app wordt gesloten.

In het kort komt het er op neer dat u een versie van uw app kunt maken met ingesloten gegevens. Deze simuleren het verbinden van de app aan externe gegevens. Als de gegevens zijn ingesloten, kunt u de app publiceren als een Test Drive-oplossing op AppSource.com.

## <a name="how-do-i-list-my-test-drive-solution-on-appsourcecom"></a>Hoe vermeld ik mijn Test Drive-oplossing op AppSource.com?
Als de app klaar is, kan deze worden gepubliceerd op AppSource.com. Als u dit proces wilt starten, vul dan het [aanmeldingsformulier](https://powerapps.microsoft.com/partners/get-listed/) in op PowerApps.com.

Als u zich hebt aangemeld, ontvangt u een e-mail met instructies voor het indienen van de app voor publicatie op AppSource.com. De inleidende documentatie waarin het volledige proces is vastgelegd, kan ook [hier](https://go.microsoft.com/fwlink/?linkid=851031) worden gedownload.

