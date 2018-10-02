---
title: Entiteitsgegevens openen in Excel | Microsoft Docs
description: Open entiteitsgegevens in Excel voor interactief weergeven en bewerken.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="open-entity-data-in-excel"></a>Entiteitsgegevens openen in Excel
Door entiteitsgegevens in Microsoft Excel te openen, kunt u snel en eenvoudig gegevens weergeven en bewerken met de invoegtoepassing Microsoft PowerApps Excel. Voor de invoegtoepassing PowerApps Excel is Microsoft Excel 2016 vereist.

![Excel-invoegtoepassing](./media/data-platform-cds-excel-addin/ExcelAddin.png "PowerApps Excel-invoegtoepassing")

## <a name="open-entity-data-in-excel"></a>Entiteitsgegevens openen in Excel
1. Vouw in [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) de sectie **Gegevens** uit en klik of tik op **Entiteiten** in het linkernavigatiedeelvenster. Alle entiteiten worden weergegeven.
2. Klik op de drie puntjes (...) rechts van de entiteit waarin u geïnteresseerd bent.
3. Klik op **Openen in Excel** en open de werkmap die wordt gegenereerd. Deze werkmap heeft bindingsgegevens voor de entiteit, een aanwijzer naar uw omgeving, en een aanwijzer naar de PowerApps Excel-invoegtoepassing.  
4. Klik in Excel op **Bewerking inschakelen** om de PowerApps Excel- invoegtoepassing in te schakelen voor uitvoering. De Excel-invoegtoepassing wordt uitgevoerd in een deelvenster rechts van het Excel-venster.
5. Als dit de eerste keer is dat u de PowerApps Excel-invoegtoepassing hebt uitgevoerd, klikt u op **Deze invoegtoepassing vertrouwen** om toe te staan dat de Excel-invoegtoepassing wordt uitgevoerd.
6. Als u wordt gevraagd u aan te melden, klikt u op **Aanmelden** en meldt u zich vervolgens aan met dezelfde referenties die u hebt gebruikt in [powerapps.com](https:///?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). In de Excel-invoegtoepassing wordt een eerdere aanmeldingscontext gebruikt en wordt u indien mogelijk automatisch aangemeld. Daarom moet u de gebruikersnaam verifiëren rechtsboven van de Excel-invoegtoepassing.

De Excel-invoegtoepassing leest de gegevens automatisch voor de entiteit die u hebt geselecteerd. Houd er rekening mee dat er pas gegevens in de werkmap zijn als de Excel-invoegtoepassing deze inleest.

## <a name="view-and-refresh-data-in-excel"></a>Gegevens weergeven en vernieuwen in Excel
Nadat de Excel-invoegtoepassing entiteitsgegevens in de Excel-werkmap heeft ingelezen, kunt u de gegevens op elk gewenst moment bijwerken door te klikken op **Vernieuwen** in de Excel-invoegtoepassing.

## <a name="edit-data-in-excel"></a>Gegevens bewerken in Excel
U kunt entiteitsgegevens desgewenst wijzigen en deze vervolgens weer publiceren door te klikken op **Publiceren** in de Excel-invoegtoepassing.

Als u een record wilt bewerken, selecteert u een cel in het werkblad en wijzig u de celwaarde.

Als u een nieuwe record wilt toevoegen, voert u een van de volgende stappen uit:

* Klik ergens in het werkblad en klik vervolgens op **Nieuw** in de Excel-invoegtoepassing.
* Klik in de laatste rij van het werkblad en druk op de Tab-toets totdat de cursor weggaat uit de laatste kolom van die rij, waarna er een nieuwe rij wordt gemaakt.
* Klik in de rij direct onder het werkblad en de begin met het invoeren van gegevens in een cel. Als u de focus buiten die cel plaatst, wordt het werkblad uitgevouwen om de nieuwe rij op te nemen.

Als u een record wilt verwijderen, voert u een van de volgende stappen uit:

* Klik met de rechtermuisknop op het te verwijderen rijnummer naast de werkbladrij en klik op **Verwijderen**
* Klik met de rechtermuisknop in de te verwijderen werkbladrij en klik vervolgens op **Verwijderen** > **Tabelrijen**.

## <a name="add-or-remove-columns"></a>Kolommen toevoegen of verwijderen
U kunt de ontwerpfunctie gebruiken om de kolommen en entiteiten aan te passen die automatisch aan het werkblad worden toegevoegd.

1. Schakel de gegevensbronontwerper van de Excel-invoegtoepassing in door te klikken op de knop **Opties** (het tandwielsymbool) en schakel vervolgens het selectievakje **Ontwerp inschakelen** in.
2. Klik op **Ontwerp** in de Excel-invoegtoepassing. Alle gegevensbronnen worden weergegeven.
3. Klik naast de gegevensbron op de knop **Bewerken** (het potloodsymbool).
4. Pas de lijst in het veld **Geselecteerde velden** desgewenst aan:
   * Als u een veld van het veld **Beschikbare velden** aan het veld **Geselecteerde velden** wilt toevoegen, klikt u op het veld en klikt u vervolgens op **Toevoegen**. U kunt ook dubbelklikken op het veld.
   * Als u een veld uit het veld **Geselecteerde velden** wilt verwijderen, klikt u op het veld en klikt u vervolgens op **Verwijderen**. U kunt ook dubbelklikken op het veld.
   * Als u de volgorde van velden wilt wijzigen, klikt u op het veld in het veld **Geselecteerde velden** en klikt u vervolgens op **Omhoog** of **Omlaag**.
5. Pas uw wijzigingen op de gegevensbron toe door te klikken op **Bijwerken** en klik vervolgens op **Gereed** om de ontwerpfunctie te sluiten. Als u een veld (kolom) hebt toegevoegd, klikt u op **Vernieuwen** om een bijgewerkte gegevensset op te halen.

> [!NOTE]
> Zorg ervoor dat u altijd de id en de vereiste velden in uw werkmap opneemt, aangezien u fouten kunt ontvangen tijdens het publiceren.

> [!NOTE]
> Als u opzoekvelden toevoegt, moet u ervoor zorgen zowel de id als de weergavevelden toe te voegen.

## <a name="troubleshooting"></a>Problemen oplossen
Er zijn enkele problemen die via eenvoudige stappen kunnen worden opgelost.

* Niet alle entiteiten ondersteunen het bewerken en maken van nieuwe records. Deze entiteiten worden geopend in Excel en u mag er gegevens in weergeven, maar publicatie wordt uitgeschakeld.
* Opzoekvelden moeten worden bewerkt met de invoegtoepassing om ervoor te zorgen dat er naar de juiste record wordt verwezen. Bijwerken van deze velden via kopiëren en plakken en rechtstreeks in het veld typen worden niet ondersteund.


Als u een probleem tegenkomt dat hier niet wordt beschreven, neemt u contact met ons op via de [ondersteuningpagina's](https://powerapps.microsoft.com/support/).

## <a name="next-steps"></a>Volgende stappen
* [Velden in een entiteit beheren](data-platform-manage-fields.md)
* [Relaties tussen entiteiten definiëren](data-platform-entity-lookup.md)
* [Een app genereren met behulp van Common Data Service voor Apps](../canvas-apps/data-platform-create-app.md)
* [Een compleet nieuwe app maken met behulp van Common Data Service voor Apps](../canvas-apps/data-platform-create-app-scratch.md)

