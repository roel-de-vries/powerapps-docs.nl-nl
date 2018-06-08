---
title: Entiteitsgegevens openen in Excel | Microsoft Docs
description: Entiteitsgegevens openen in Excel voor interactief weergeven en bewerken.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
ms.openlocfilehash: 8dbf6088104270d9251b70eec9adf0642de2f879
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34445854"
---
# <a name="open-entity-data-in-excel"></a>Entiteitsgegevens openen in Excel
Als u entiteitsgegevens opent in Microsoft Excel, kunt u snel en eenvoudig gegevens weergeven en bewerken met behulp van de Excel-invoegtoepassing van Microsoft PowerApps. Voor de Excel-invoegtoepassing van PowerApps is Microsoft Excel 2016 vereist.

![Excel-invoegtoepassing](./media/data-platform-cds-excel-addin/ExcelAddin.png "Excel-invoegtoepassing van PowerApps")

## <a name="open-entity-data-in-excel"></a>Entiteitsgegevens openen in Excel
1. Vouw op [powerapps.com](https://web.powerapps.com) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster. Alle entiteiten worden weergegeven.
2. Klik op de drie puntjes (...) aan de rechterkant van de entiteit waarin u geïnteresseerd bent.
3. Klik op **Openen in Excel** en open de werkmap die is gegenereerd. De werkmap bevat bindende informatie voor de entiteit, een verwijzing naar de omgeving en een verwijzing naar de Excel-invoegtoepassing van PowerApps.  
4. Klik in Excel op **Bewerken inschakelen** om de Excel-invoegtoepassing van PowerApps uit te kunnen voeren. De Excel-invoegtoepassing wordt uitgevoerd in een deelvenster aan de rechterkant van het Excel-venster.
5. Als u de Excel- invoegtoepassing van PowerApps voor het eerst uitvoert, klikt u op **Deze invoegtoepassing vertrouwen** om de Excel-invoegtoepassing uit te kunnen voeren.
6. Als u wordt gevraagd u aan te melden, klikt u op **Aanmelden** en meldt u zich aan met dezelfde referenties die u hebt gebruikt voor [powerapps.com](https://web.powerapps.com). De Excel-invoegtoepassing maakt gebruik van een vorige context voor aanmelden en meldt u automatisch aan als dat mogelijk is. Controleer daarom de gebruikersnaam rechtsboven in de Excel-invoegtoepassing.

De gegevens voor de door u gekozen entiteit worden automatisch gelezen. Houd er rekening mee dat de werkmap geen gegevens bevat totdat deze door de Excel-invoegtoepassing worden ingelezen.

## <a name="view-and-refresh-data-in-excel"></a>Gegevens in Excel weergeven en vernieuwen
Nadat de entiteitsgegevens in de werkmap zijn gelezen, kunt u de gegevens altijd bijwerken door in de Excel-invoegtoepassing op **Vernieuwen** te klikken.

## <a name="edit-data-in-excel"></a>Gegevens in Excel bewerken
U kunt de entiteitsgegevens naar wens wijzigen en ze opnieuw publiceren door in de Excel-invoegtoepassing op **Publiceren** te klikken.

Als u een record wilt bewerken, selecteert u een cel in de werkmap en wijzigt u de waarde ervan.

Voer een van de volgende stappen uit als u een nieuwe record wilt toevoegen:

* Klik in het werkblad en vervolgens op **Nieuw** in de Excel-invoegtoepassing.
* Klik in de laatste rij van het werkblad en druk vervolgens op de Tab-toets totdat de cursor uit de laatste kolom van die rij wordt verplaatst en een nieuwe rij wordt gemaakt.
* Klik in de rij direct onder het werkblad en begin met het invoeren van gegevens in een cel. Wanneer u de focus buiten die cel verplaatst, wordt het werkblad uitgebreid met de nieuwe rij.

Voer een van de volgende stappen uit als u een nieuwe record wilt verwijderen:

* Klik met de rechtermuisknop op het rijnummer naast de rij in het werkblad die u wilt verwijderen en klik vervolgens op **Verwijderen**.
* Klik met de rechtermuisknop op de rij in het werkblad die u wilt verwijderen en klik vervolgens op **Verwijderen** > **Tabelrijen**.

## <a name="add-or-remove-columns"></a>Kolommen toevoegen of verwijderen
Met de ontwerpfunctie kunt u de kolommen en entiteiten aanpassen die automatisch aan het werkblad worden toegevoegd.

1. Schakel de ontwerpfunctie van de gegevensbron in de Excel-invoegtoepassing in door op de knop **Opties** (het tandwielsymbool) te klikken en het selectievakje **Enable design** in te schakelen.
2. Klik op **Design** in de Excel-invoegtoepassing. Alle gegevensbronnen worden weergegeven.
3. Klik naast de gegevensbron op de knop **Bewerken** (het potloodsymbool).
4. Pas de lijst naar wens aan in het veld **Geselecteerde velden**:
   * Als u een veld wilt toevoegen vanuit het veld **Beschikbare velden** in het veld **Geselecteerde velden**, klik op het veld en vervolgens op **Toevoegen**. U kunt ook op het veld dubbelklikken.
   * Als u veld wilt verwijderen uit het veld **Geselecteerde velden**, klikt u op het veld en vervolgens op **Verwijderen**. U kunt ook op het veld dubbelklikken.
   * Als u de volgorde van de velden wilt wijzigen, klikt u in het betreffende veld in het veld **Geselecteerde velden** en vervolgens op **Omhoog** of **Omlaag**.
5. Pas de wijzigingen op de gegevensbron toe door op **Bijwerken** te klikken en vervolgens op **Gereed**. Als u een veld (kolom) hebt toegevoegd, klikt u op **Vernieuwen** om een bijgewerkte set gegevens op te halen.

> [!NOTE]
> Neem altijd de id en de vereiste velden in uw werkmap op, anders kunt u fouten krijgen wanneer u gaat publiceren.

> [!NOTE]
> Wanneer u zoekvelden toevoegt, moet u zowel het veld Id als Weergave toevoegen.

## <a name="troubleshooting"></a>Problemen oplossen
Bepaalde problemen kunnen worden opgelost via een paar eenvoudige stappen.

* Niet alle entiteiten ondersteunen het bewerken en maken van nieuwe records. U kunt deze entiteiten wel openen in Excel en de gegevens weergeven, maar publicatie is uitgeschakeld.
* Zoekvelden moeten worden bewerkt met de invoegtoepassing om ervoor te zorgen dat naar de juiste record wordt verwezen. U kunt deze velden niet bijwerken via kopiëren en plakken of door rechtstreeks in het veld te typen.


Als u een probleem ondervindt dat hier niet wordt beschreven, neemt u dan contact met ons op via de [ondersteuningspagina](https://powerapps.microsoft.com/support/).

## <a name="next-steps"></a>Volgende stappen
* [Velden in een entiteit beheren](data-platform-manage-fields.md)
* [Relaties tussen entiteiten definiëren](data-platform-entity-lookup.md)
* [Een app genereren met behulp van Common Data Service voor apps](../canvas-apps/data-platform-create-app.md)
* [Een volledig nieuwe app maken met behulp van Common Data Service voor apps](../canvas-apps/data-platform-create-app-scratch.md)

